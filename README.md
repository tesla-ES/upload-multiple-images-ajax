<div class="container" style="padding-top: 50px;">
		<h3>Upload Multiple Images Ajax - <small>(PHP + jQuery + Bootstrap)</small></h3>
		<blockquote>
		This package can process uploaded images sent via AJAX requests.
		It comes with jQuery plugin that can upload the one or more images using AJAX requests.
		It can also display a preview of the selected images for upload, so the user can remove undesired images from the list of file to upload.
		The PHP class can validate the uploaded images to check for valid image file name extensions, size limits, and limit number of uploaded files.
		</blockquote>
		<hr />
		<h1><div class="label label-success">jQuery Plugins</label></h1>
		<hr />
		<h1>$(element).uploadImagesPreview(form [required], options [optional], callback [optional])</h1>
		<blockquote>For the preview and validate images in the client side</blockquote>
		<hr />
		<ul>
			<li><strong>form</strong> - the form selector</li>
			<li> 
			<strong>options</strong> - the defaults options are: 
			<pre>
				image_type: "jpg|jpeg|png|gif",
				min_size: 24,
				max_size: (1024*1024*3),
				max_files: 10
			</pre>
			</li>
			<li><strong>callback</strong> - for example, get the errors variable:
			<pre>
				switch(__errors__upload__) /* Check the possibles erros */
				{
					case 'ERROR_CONTENT_TYPE': alert("Error content type"); break;
					case 'ERROR_MIN_SIZE': alert("Error min size"); break;
					case 'ERROR_MAX_SIZE': alert("Error max size"); break;
					case 'ERROR_MAX_FILES': alert("Error max files"); break;
					default: $("#btn").removeAttr("disabled"); break; /* Activate the button Form */
				}
			</pre>
			</li>
		</ul>
		<hr />
		<h1>$(element).countImages()</h1>
		<blockquote>Return the number of images.</blockquote>
		<hr>
		<h1>$(element).uploadImagesAjax(url [required], options [optional])</h1>
		<blockquote>Upload the images and send parameters for an asynchronous HTTP (Ajax) request.</blockquote>
		<hr />
		<ul>
			<li><strong>url</strong> - A string containing the URL to which the request is sent.</li>
			<li> 
			<strong>options</strong> - the defaults options are: 
			<pre>
				params: {},
				type: 'POST',
				beforeSend: function(){},
				success: function(){},
				error: function(){},
				complete: function(){}
			</pre>
			</li>
		</ul>
		<h3>Events:</h3>
		<ul>
			<li><strong>$(document).on("createImage", function(e){console.log(e.file.name;); ...});</strong> - It happens when an image is created, the "e" argument gets information from the file. (e.file.name|e.file.size|e.file.type)</li>
			<li><strong>$(document).on("deleteImage", function(e){console.log(e.file.name;); ...});</strong> - It happens when an image is deleted, the "e" argument gets information from the file. (e.file.name|e.file.size|e.file.type)</li>
		</ul>
		<hr />
		<h1><div class="label label-success">PHP Class</label></h1>
		<h1>uploadImages() <small>class</small></h1>
		<blockquote>Validate, get the parameters and save the images.</blockquote>
		<hr />
		<h3>Publics properties and defaults values:</h3>
		<pre>
			public $image_type = "jpg|jpeg|png|gif";
			public $min_size = 24;
			public $max_size = (1024*1024*3);
			public $max_files = 10;
			public $error = array();
		</pre>
		<hr />
		<h3>Public functions:</h3>
			<hr />
			<h1>public function countImages()</h1> <blockquote>Return the number of images</blockquote>
			<hr />
			<h1>public function getImages()</h1><blockquote>Return one array with the images information -&gt;  "error", "name", "size", "tmp_name", "type"</blockquote>
			<hr />
			<h1>public function getParams()</h1><blockquote>Return one array with the extra parameters</blockquote>
			<hr />
			<h1>public function saveImage($tmp_name, $folder, $image_name)</h1><blockquote>Save the image</blockquote>
			<hr />
			<h1>public function validateImages()</h1><blockquote>Validate the images with the values of the public properties: $image_type, $min_size, $max_size and $max_files. If is valid return true. If an image is invalid, the error property is an array with that information.</blockquote>
		<hr />
		<br />
		<br />
		<br />
		<br />
	</div>
