# Digital-System-2-Template :zap:
This reposistory will contain the documentation of *Digital System 2 Lab* at **University of Texas at El Paso** (`UTEP`). Previously, the labs where given in pdf format, however everyone is using version control for development such as Git. Therefore, the main purpose of this labs is to elaborate the previous labs.

# Checklist

- [x] Create a reposistory to contain the labs
- [x] Add co-author
- [ ] Start working on Lab 1
- [ ] Update Readme for Lab 2
- [ ] Change pdf to markdown files
- [ ] Elaborate documentation
- [ ] Verify functionality and proofread verilog

# Development
| **Software** | **Environment** |
| :---:    | :---:       |
| ![Vivado](https://img.shields.io/static/v1?label=&message=Xilinx+Vivado&color=black&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABACAMAAACdt4HsAAABQVBMVEVeYABkZgB1dwB3eQCFhwCLjQmcniHS1CnV1zjX2Ufa3Fbl55Lo6qHq7Kzr7Vrr7bDt77%2Fu8Gn196v8%2FrT%2B%2F8P%2F%2F33%2F%2F9f%2F%2F%2F%2BLjQna3Fbl55Ll55La3Fbl55La3FaLjQna3Fbl55La3FaIigbl55Ll55KLjQmFhwCfoSba3FbZ21Ll55Ll55La3Fbl55LU1jTa3Fbl55L%2F%2F3ra3Fbl55La3Fba3Fbl55KLjQna3Fbl55La3Fbl55La3Fba3Fba3Fbl55KLjQn4%2Bq%2BLjQna3Fbl55Ll55Ll55KLjQna3Fbl55KLjQn196vb3Vzl55Ll55Ll55La3FZxcwB0dgDa3Fba3FaLjQna3Fba3FaLjQna3Fbl55KKjAeLjQnr7Wbl55La3Fba3FZ8fgCFhwCIigSLjQnX2Ufa3Fbl55Ln6Z3o6qFUKg%2FmAAAAYnRSTlMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAFCREVGBkgJSgoKS00NUFFRUVJSU1QUWFlZWVtcHl9fYGBgYWFiZObm5%2Bjr6%2BvtLe7u7u%2Fv8bLz9PX29vb3t%2Ff4%2Bfn5%2Bvr6%2B%2Fz99V9LS0AAAI%2BSURBVHjapdJlm9swDMDxZJ12TZxjZmZmvhszM7PnbN%2F%2FA8yt00dtJbdx%2FX9d%2FZ7IajDoWTAY1%2FYmdooCSi37Ae%2BU%2BuEFXCjdgQewq8rNtAxMKNMLRwBTlU49Ad1wS8A7hT1wA%2FAM2JYTgGfAvrsBeAbs0hGIFWnGF1BuwGtf4DYFJpyAcwrsOgFjFLhwAmIKvLfNRxroNrVyhqjYqYFCubAfnRc5gagzERoAU5XDnGGKA4qJqALQCXcosM5%2Bv2AA3ezPrwTYZ8YTwQML8lX%2FVj3wkR%2FngEdSvg27yf%2B5Zt6M88B9qYFCfxwP24FIL28DZKm3EJbOeWw5Q1RMrIDMAP0JpX4wZ8D1KTAkKwCERpghZ8BxCixIBMwSuks8Q%2BX2NuCGrAb0ElnfjYBfTwB8fgTMEqatDIhwnAGkrAVwCd2D8hnw8RlAUqDQEWXF0fAftYLrU2BIMkDQl5g627raujaftAsrsCAZ4MqAqJSIZPXf3%2FS6DTiSHBD04q9WU9PTeQ64JTkgwA84S6s6o8AXDsAFTtK67ozXAW8ZQC%2BA47TVpkAwwI5jDxsDZgFuHPu00QAoLfAwbdqJDXg5IO6luXo%2BxwG%2FP99M83aXA34tPc45fsavsHitR2yzA%2BSYLABXNSDE6LMc4xwAGaA7bDzOA4CAbuOT4z%2FxESBgYg66JoQNOAIKiNoH%2FTYihBVYAA7AB8VxHhgCAmCHZJwAAByA7U0LjAGAB2g8cB%2F8gEfgByyAD%2FBBToIXIAH8AM%2F%2BAwk%2BiPzFN%2BOgAAAAAElFTkSuQmCC%0A)| ![Verilog](https://img.shields.io/static/v1?label=&message=Verilog&color=blue&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAMAAABEpIrGAAAABGdBTUEAALGPC%2FxhBQAAAAFzUkdCAK7OHOkAAAAgY0hSTQAAeiYAAICEAAD6AAAAgOgAAHUwAADqYAAAOpgAABdwnLpRPAAAAVZQTFRFAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA%2F%2F%2F%2FyxSZEQAAAHB0Uk5TACDmwgk%2F%2B5dpllk088FTmnVzaPnPE7MFkpCcQuEewAe4Tt%2FFG2zlqAiD5%2BReJ3eMiGAMNX6NhFAEPn96K2H%2BgQJNvb6nZL8OR7DDxkXZ2AooItfa1tW7b9zd4N5qGkaHexyJbR1cSmu3ErKPm1JyWFVY6tcAAAABYktHRHGvB1ziAAAACXBIWXMAAA7EAAAOxAGVKw4bAAABf0lEQVQ4y92TWVOCUBiGKbG00lJLshCLFrVNrFxTs0NpUma2mEtGubQv5%2F9f9R2QxqkB7%2FsuzjMcHjjD8L4UBTM0bKIB5pFRcmXBFgIrHqO0GZ%2BwEcGOJ8nVFHaogvNHMLumZwBO7GYAs9hDNufUFykz72K9yrs5WnnUCqtvoU9Y5JeWASur%2FgAguBaENeBf39Dub26FhPA2tbMbicbiVCIZSSaoeCwa2kv1hHQGYzhjH2fIGVaAlaI5gHZGGvcErApYFbAmZA8QEg%2B9zFEOcZ68z8EhzuHLezgk2rPk%2FnGBkyTJJCIFCNkANoRMknQiFU7hc9xYZzLFM%2Bz2USVRTyiely9sJQPhcpCQubrGOSOBjPhfBLpiJFQgYjc8X61Wa3W2QcAqaLBsDcA3buFvMs07WRbuUw92QW61y51uS251O%2BV2SxYem4wSiDAkqm4QmMGRGxhaLfZPerGH4tT%2FFue5rzhQvReleq9q9d7I5nuf0Cvvh1bez9%2Fl1an%2FF8E34yTzLFjpmLMAAAAldEVYdGRhdGU6Y3JlYXRlADIwMjAtMDItMDdUMTc6MjQ6NDUrMDA6MDDiWEe%2BAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDIwLTAyLTA3VDE3OjI0OjQ1KzAwOjAwkwX%2FAgAAAEZ0RVh0c29mdHdhcmUASW1hZ2VNYWdpY2sgNi43LjgtOSAyMDE5LTAyLTAxIFExNiBodHRwOi8vd3d3LmltYWdlbWFnaWNrLm9yZ0F74sgAAAAYdEVYdFRodW1iOjpEb2N1bWVudDo6UGFnZXMAMaf%2Fuy8AAAAYdEVYdFRodW1iOjpJbWFnZTo6aGVpZ2h0ADUxMsDQUFEAAAAXdEVYdFRodW1iOjpJbWFnZTo6V2lkdGgANTEyHHwD3AAAABl0RVh0VGh1bWI6Ok1pbWV0eXBlAGltYWdlL3BuZz%2ByVk4AAAAXdEVYdFRodW1iOjpNVGltZQAxNTgxMDk2Mjg13VzE4wAAABN0RVh0VGh1bWI6OlNpemUANy41M0tCQs3klRUAAABDdEVYdFRodW1iOjpVUkkAZmlsZTovLy4vdXBsb2Fkcy81Ni9zWnp0MUtzLzIxNDgvdmVyaWxvZ19pY29uXzEzMTg5NC5wbmc%2BkF9GAAAAAElFTkSuQmCC)


## Authors:
* [**Jesus Minjares**](https://github.com/jminjares4)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/jesus-minjares-157a21195/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/jminjares4)
* [**Ismael Holguin**](https://github.com/iholguin6)
    * Master of Science in Computer Engineering <br>
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&style=flat)](https://www.linkedin.com/in/ismael-holguin-5ab421224/) [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&style=flat)](https://github.com/iholguin6)
    
