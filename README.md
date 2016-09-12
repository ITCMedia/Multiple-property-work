<!-- ƒоп.свойство дополнительного изображени€ -->
<xsl:if test="property_value[property_id = 112]/file_small != ''">
	<a href="{dir}{property_value[property_id = 112]/file}">
		<img src="{dir}{property_value[property_id = 112]/file_small}"  alt="" />
	</a>
</xsl:if>

<!-- ћножественный вывод доп.свойства  -->
<xsl:for-each select="property_value[tag_name='additional-images'][file !='']">
	<a href="{../dir}{file}" class="lightbox">
		<img src="{../dir}{file_small}" />
	</a>
</xsl:for-each>

<!-- ‘ото + множественное свойсво дл€ слайдера -->
<xsl:if test="image_small != ''">
	<li class="current">
		<a href="{dir}{image_large}" rel="item_slider" class="fancy" title="{name}">
			<img border="0" src="{dir}{image_large}" alt="{name}" title="{name}" />
		</a>
	</li>
</xsl:if>
<xsl:for-each select="property_value[tag_name='additional-images'][file !='']">
	<li style="display: none;">
		<a href="{../dir}{file}" rel="item_slider" class="fancy" title="{name}">
			<img border="0" src="{../dir}{file}" alt="{name}" title="{name}" />
		</a>
	</li>
</xsl:for-each>