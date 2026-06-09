# CXMLPropStoreSaxParser::_CreateSchemaCollection(IStream *,IXMLDOMSchemaCollection * *)

- ea: `0x180030a4c`
- end: `0x180030bd5`
- name: `?_CreateSchemaCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `393`
- prototype: `int(CXMLPropStoreSaxParser *__hidden this, struct IStream *, struct IXMLDOMSchemaCollection **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002eacc`

## callees

- `0x180003400`
- `0x180012550`
- `0x180023940`
- `0x18003010c`
- `0x1800301f0`
- `0x180030a4c`
- `0x1800321ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030ac5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030ac5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180030aae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180030aae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030b0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030b0e`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_CreateSchemaCollection(
        const unsigned __int16 **this,
        struct IStream *a2,
        struct IXMLDOMSchemaCollection2 **a3)
{
  HRESULT Instance; // ebx
  int v7; // esi
  HMODULE Library; // rdi
  struct IXMLDOMSchemaCollection2 *v9; // r15
  const unsigned __int16 *v10; // r12
  CXMLPropStoreSaxParser *v11; // rcx
  const unsigned __int16 *v12; // r9
  CXMLPropStoreSaxParser *v13; // rcx
  CXMLPropStoreSaxParser *v14; // rcx
  struct IXMLDOMSchemaCollection2 *ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMDocument2 *v17; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszIconFile[264]; // [rsp+40h] [rbp-C0h] BYREF

  *a3 = 0;
  Instance = StringCchCopyW(pszIconFile, 0x104u, this[5]);
  if ( Instance >= 0 )
  {
    v7 = PathParseIconLocationW(pszIconFile);
    if ( v7 > 0 && (Library = LoadLibraryExW(pszIconFile, 0, 2u)) != 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
      Instance = CoCreateInstance(
                   &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
                   0,
                   1u,
                   &GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v9 = ppv;
        v10 = this[8];
        v17 = 0;
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v17);
        Instance = CXMLPropStoreSaxParser::_LoadDOMFromResource(v11, Library, v7, v12, &v17);
        if ( Instance >= 0 )
          Instance = CXMLPropStoreSaxParser::_AddSchemaToCollection(v13, v17, v10, v9);
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v17);
        if ( Instance >= 0 )
        {
          Instance = CXMLPropStoreSaxParser::_AddUniversalSchemaToCollection(v14, a2, ppv);
          if ( Instance >= 0 )
          {
            *a3 = ppv;
            ppv = 0;
          }
        }
      }
      FreeLibrary(Library);
      Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&ppv);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180030a4c  mov     [rsp-8+arg_18], rbx
0x180030a51  push    rbp
0x180030a52  push    rsi
0x180030a53  push    rdi
0x180030a54  push    r12
0x180030a56  push    r13
0x180030a58  push    r14
0x180030a5a  push    r15
0x180030a5c  lea     rbp, [rsp-160h]
0x180030a64  sub     rsp, 260h
0x180030a6b  mov     rax, cs:__security_cookie
0x180030a72  xor     rax, rsp
0x180030a75  mov     [rbp+190h+var_40], rax
0x180030a7c  mov     r14, r8
0x180030a7f  mov     qword ptr [r8], 0
0x180030a86  mov     r8, [rcx+28h]; unsigned __int16 *
0x180030a8a  mov     r13, rdx
0x180030a8d  mov     r12, rcx
0x180030a90  mov     edx, 104h; unsigned __int64
0x180030a95  lea     rcx, [rsp+290h+pszIconFile]; unsigned __int16 *
0x180030a9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030a9f  mov     ebx, eax
0x180030aa1  test    eax, eax
0x180030aa3  js      loc_180030BA9
0x180030aa9  lea     rcx, [rsp+290h+pszIconFile]; pszIconFile
0x180030aae  call    cs:__imp_PathParseIconLocationW
0x180030ab4  mov     esi, eax
0x180030ab6  test    eax, eax
0x180030ab8  jle     short loc_180030AD3
0x180030aba  xor     edx, edx; hFile
0x180030abc  lea     rcx, [rsp+290h+pszIconFile]; lpLibFileName
0x180030ac1  lea     r8d, [rdx+2]; dwFlags
0x180030ac5  call    cs:__imp_LoadLibraryExW
0x180030acb  mov     rdi, rax
0x180030ace  test    rax, rax
0x180030ad1  jnz     short loc_180030ADD
0x180030ad3  mov     ebx, 80070057h
0x180030ad8  jmp     loc_180030BA9
0x180030add  lea     rcx, [rsp+290h+var_260]
0x180030ae2  mov     [rsp+290h+var_260], 0
0x180030aeb  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030af0  xor     edx, edx; pUnkOuter
0x180030af2  lea     rax, [rsp+290h+var_260]
0x180030af7  lea     r9, _GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a; riid
0x180030afe  mov     [rsp+290h+ppv], rax; ppv
0x180030b03  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180030b0a  lea     r8d, [rdx+1]; dwClsContext
0x180030b0e  call    cs:__imp_CoCreateInstance
0x180030b14  mov     ebx, eax
0x180030b16  test    eax, eax
0x180030b18  js      short loc_180030B96
0x180030b1a  mov     r15, [rsp+290h+var_260]
0x180030b1f  lea     rcx, [rsp+290h+var_258]
0x180030b24  mov     r12, [r12+40h]
0x180030b29  mov     [rsp+290h+var_258], 0
0x180030b32  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030b37  lea     rax, [rsp+290h+var_258]
0x180030b3c  mov     r8d, esi; int
0x180030b3f  mov     rdx, rdi; HINSTANCE
0x180030b42  mov     [rsp+290h+ppv], rax; struct IXMLDOMDocument2 **
0x180030b47  call    ?_LoadDOMFromResource@CXMLPropStoreSaxParser@@AEAAJPEAUHINSTANCE__@@HPEBGPEAPEAUIXMLDOMDocument2@@@Z; CXMLPropStoreSaxParser::_LoadDOMFromResource(HINSTANCE__ *,int,ushort const *,IXMLDOMDocument2 * *)
0x180030b4c  mov     ebx, eax
0x180030b4e  test    eax, eax
0x180030b50  js      short loc_180030B64
0x180030b52  mov     rdx, [rsp+290h+var_258]; struct IXMLDOMDocument2 *
0x180030b57  mov     r9, r15; struct IXMLDOMSchemaCollection2 *
0x180030b5a  mov     r8, r12; unsigned __int16 *
0x180030b5d  call    ?_AddSchemaToCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIXMLDOMDocument2@@PEBGPEAUIXMLDOMSchemaCollection2@@@Z; CXMLPropStoreSaxParser::_AddSchemaToCollection(IXMLDOMDocument2 *,ushort const *,IXMLDOMSchemaCollection2 *)
0x180030b62  mov     ebx, eax
0x180030b64  lea     rcx, [rsp+290h+var_258]
0x180030b69  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030b6e  test    ebx, ebx
0x180030b70  js      short loc_180030B96
0x180030b72  mov     r8, [rsp+290h+var_260]; struct IXMLDOMSchemaCollection2 *
0x180030b77  mov     rdx, r13; struct IStream *
0x180030b7a  call    ?_AddUniversalSchemaToCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAUIXMLDOMSchemaCollection2@@@Z; CXMLPropStoreSaxParser::_AddUniversalSchemaToCollection(IStream *,IXMLDOMSchemaCollection2 *)
0x180030b7f  mov     ebx, eax
0x180030b81  test    eax, eax
0x180030b83  js      short loc_180030B96
0x180030b85  mov     rax, [rsp+290h+var_260]
0x180030b8a  mov     [r14], rax
0x180030b8d  mov     [rsp+290h+var_260], 0
0x180030b96  mov     rcx, rdi; hLibModule
0x180030b99  call    cs:__imp_FreeLibrary
0x180030b9f  lea     rcx, [rsp+290h+var_260]
0x180030ba4  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030ba9  mov     eax, ebx
0x180030bab  mov     rcx, [rbp+190h+var_40]
0x180030bb2  xor     rcx, rsp; StackCookie
0x180030bb5  call    __security_check_cookie
0x180030bba  mov     rbx, [rsp+290h+arg_18]
0x180030bc2  add     rsp, 260h
0x180030bc9  pop     r15
0x180030bcb  pop     r14
0x180030bcd  pop     r13
0x180030bcf  pop     r12
0x180030bd1  pop     rdi
0x180030bd2  pop     rsi
0x180030bd3  pop     rbp
0x180030bd4  retn
```
