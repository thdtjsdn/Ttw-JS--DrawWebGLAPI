# Ttw-JS--DrawWebGLAPI

---

# 문의 사항

- thdtjsdn@gmail.com

---

# Canvas Context의 WebGL Draw API 입니다.

- 많은 다량의 랜더링을 고려하여 성능 위주의 코드로 작성 되었습니다.

---

# 본 API는 '무료제공' 입니다.

- 자유롭게 사용하셔도 무방합니다.

---

# Sample source

- Example link
	- http://thdtjsdn.com:49310/app_tool/html_page/DrawWebGL/index.html

```javascript
const CANVAS = TAPI.ge('ID-CANVAS');
const CONTEXT = CANVAS.getContext('webgl');

const EVENT_LISTENERS = {

	Clear: function () {
		// 클리어 색상 설정 (예: 검은색)
		WEBGL.clearColor(0.0, 0.0, 0.0, 1.0);

		// 깊이 버퍼 클리어 설정 (필요한 경우)
		WEBGL.clearDepth(1.0);

		// 스텐실 버퍼 클리어 설정 (필요한 경우)
		WEBGL.clearStencil(0);

		// 클리어 명령 실행
		WEBGL.clear(WEBGL.COLOR_BUFFER_BIT | WEBGL.DEPTH_BUFFER_BIT | WEBGL.STENCIL_BUFFER_BIT);

		FRAME_BUFFER_OBJECT = APIS.initFramebufferObject(WEBGL, WEBGL.canvas.width, WEBGL.canvas.height);
	}
	, Arc: function () {
		APIS.drawArc(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
			, getArc_Random(), Math.PI / 2, false
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Circle: function () {
		APIS.drawCircle(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Rect: function () {
		const x = getX_Random();
		const y = getY_Random();
		const w = getX_Random() / 8;
		const h = getY_Random() / 8;
		APIS.drawRect(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, x, y, w, h
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, RegularPolygon: function () {
		const x = getX_Random();
		const y = getY_Random();
		const w = getX_Random() / 8;
		const h = getY_Random() / 8;
		APIS.drawRegularPolygon(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, RegularPolygonRotation: function () {
		const x = getX_Random();
		const y = getY_Random();
		const w = getX_Random() / 8;
		const h = getY_Random() / 8;
		APIS.drawRegularPolygon__Rotation(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random(), getRotation_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Triangle: function () {
		const x = getX_Random();
		const y = getY_Random();
		const w = getX_Random() / 8;
		const h = getY_Random() / 8;
		APIS.drawTriangle(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, TriangleRotation: function () {
		const x = getX_Random();
		const y = getY_Random();
		const w = getX_Random() / 8;
		const h = getY_Random() / 8;
		APIS.drawTriangle__Rotation(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random(), getRotation_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Line: function () {
		APIS.drawLine(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, LineDashed: function () {
		APIS.drawLine_Dashed(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getDashed_Random(), getDashed_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, LineThick: function () {
		APIS.drawLineThick(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, LineThickDashed: function () {
		APIS.drawLineThick_Dashed(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getDashed_Random(), getDashed_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, LineThickGradient: function () {
		const COLOR_STOPS = [
			getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random(),
			getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
		];

		// 두꺼운 라인 그리기
		APIS.drawLineThick_Gradient(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
			, getAlpha_Random()
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, COLOR_STOPS
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polygon: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolygonBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonBezierCurve(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a, 16
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolygonCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonCurve(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a, 0.5, 16
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polyline: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a, 16
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineBezierCurveThick: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		//APIS.drawPolylineBezierCurveThick(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
		APIS.drawPolylineBezierCurveThick(WEBGL, FRAME_BUFFER_OBJECT, 5
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			//, a, 30
			//, a, getRadius_Random()
			//, a, 2000
			, a, 10000
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve(WEBGL, FRAME_BUFFER_OBJECT
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, a, 0.5, 16
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineCurveThick: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		//APIS.drawPolylineCurveThick(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
		APIS.drawPolylineCurveThick(WEBGL, FRAME_BUFFER_OBJECT, 5
		//APIS.drawPolylineCurveThick0(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
		//APIS.drawPolylineCurveThick0(WEBGL, FRAME_BUFFER_OBJECT, 5
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			//, a, 30
			//, a, getRadius_Random()
			//, a, 2000
			, a, 10000
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineCurveThickCircleType: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurveThick__CircleType(WEBGL, FRAME_BUFFER_OBJECT, getLineWidth_Random()
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			//, a, 30
			, a, getRadius_Random()
			, 20, 10
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}



	//----------------------------------------------------------------------------------------------------;

	, Bitmap: function () {
		var img = new Image();
		function drawImage(bitmap) {
			APIS.drawImageBitmap(WEBGL, FRAME_BUFFER_OBJECT
				, bitmap
				, getX_Random(), getY_Random()
				, 100, 100
			);
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		img.onload = function () { createImageBitmap(img).then(drawImage); };
		img.src = 'index.photo.png'; // 사용할 이미지의 URL
	}
	, BitmapRotation: function () {
		var img = new Image();
		function drawImage(bitmap) {
			APIS.drawImageBitmap_Rotation(WEBGL, FRAME_BUFFER_OBJECT
				, bitmap, getX_Random(), getY_Random()
				, 100, 100, getRotation_Random()
			);
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		img.onload = function () { createImageBitmap(img).then(drawImage); };
		img.src = 'index.photo.png'; // 사용할 이미지의 URL
	}

	//----------------------------------------------------------------------------------------------------;

	, Text: function () {
		APIS.drawText(WEBGL, FRAME_BUFFER_OBJECT
			, 'THDTJSDN'
			, getX_Random(), getY_Random()
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, 'Arial', getFontSize_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextRotation: function () {
		APIS.drawText_Rotation(WEBGL, FRAME_BUFFER_OBJECT
			, 'THDTJSDN'
			, getX_Random(), getY_Random(), getRotation_Random()
			, getColor_Random(), getColor_Random(), getColor_Random(), getAlpha_Random()
			, 'Arial', getFontSize_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
};
```

---

# API 목록(필요할 법한 목록만)

- drawArc(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawCircle(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRect(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRect_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawTriangle(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawTriangle_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawImageBitmap(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawImageBitmap_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawLine(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineDashed(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThick(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThickDashed(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThickGradient(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawPolygon(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolygonBezierCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolygonCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawPolyline(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineBezierCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineBezierCurveThick(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineCurveThick(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawRegularPolygon(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRegularPolygon_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...);

- drawText(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawText_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

---