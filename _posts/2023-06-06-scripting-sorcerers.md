---
layout: post
title:  "Scripting Sorcerers"
categories: [ Team ]
image: assets/teams/scripting_sorcerers/group.jpg
comments: false
---


<div>
{% for team in site.data.teams.teams %}
    {% if team.teamname == "Scripting Sorcerers" %}
    
     <table>
    
  
    <tr style="border-bottom: 2px solid darkgrey;">
      <td style="vertical-align: top;">
        <img src="{{ team.image | relative_url }}" width="700px">

        <br>
        {% for image in team.images %}
        
        {{ image.name }}
        {% if image.url %}
        <a href="{{ image.url | relative_url }}"><img src="{{ image.imagelink | relative_url }}" width="300px"></a>
        {% else %}

        <img src="{{ image.imagelink | relative_url }}" width="300px">
        {% endif %}
        <br>
        {% endfor %}


      </td>
     <td> 
    
    <h2> Team Members: </h2>
   
    <ul>
    
        {% for member in team.members.names %}
            <li><strong>{{ member }}</strong> - <em>{{ team.members.major[forloop.index0] }}</em>  <br>{{ team.members.affiliation[forloop.index0 ] }} <br>
            </li>
        {% endfor %}
             
       </ul>  
    <h2> Links: </h2>
     <ul>
    
        {% for link in team.links%}
        <li>
            {% if link.url contains '://' -%}
                <a href="{{ link.url }}"> {{ link.name }} </a> 
            {%- else -%}
                <a href="{{ link.url | relative_url }}"><i class="{{ link.icon }}" 
                style="color: {{ link.iconcolor }}"></i> {{ link.name }} </a> 
            {% endif %}
         </li>   
        {% endfor %}
             
       </ul>  
  </td>
</tr>
<tr> </tr> 
{% endif %}
{% endfor %}

</table>
</div>

