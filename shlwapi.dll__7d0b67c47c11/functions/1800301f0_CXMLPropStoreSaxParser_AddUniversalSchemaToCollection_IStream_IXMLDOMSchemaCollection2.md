# CXMLPropStoreSaxParser::_AddUniversalSchemaToCollection(IStream *,IXMLDOMSchemaCollection2 *)

- ea: `0x1800301f0`
- end: `0x1800303a4`
- name: `?_AddUniversalSchemaToCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAUIXMLDOMSchemaCollection2@@@Z`
- size: `436`
- prototype: `int(CXMLPropStoreSaxParser *__hidden this, struct IStream *, struct IXMLDOMSchemaCollection2 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030a4c`

## callees

- `0x180012550`
- `0x180023940`
- `0x18002e7d0`
- `0x18003010c`
- `0x1800301f0`
- `0x180031454`
- `0x180032498`
- `0x1800327a0`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180030300`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180030300`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_AddUniversalSchemaToCollection(
        CXMLPropStoreSaxParser *this,
        struct IStream *a2,
        struct IXMLDOMSchemaCollection2 *a3)
{
  __int64 v5; // rsi
  CXMLPropStoreSaxParser *v6; // rcx
  int v7; // ebx
  unsigned __int16 *v8; // rdi
  const WCHAR *v9; // rax
  const WCHAR *v10; // r8
  struct IStream *v11; // rbx
  CXMLPropStoreSaxParser *v12; // rcx
  CXMLPropStoreSaxParser *v13; // rcx
  unsigned __int16 *v15; // [rsp+20h] [rbp-49h] BYREF
  __int64 v16; // [rsp+28h] [rbp-41h]
  __int64 v17; // [rsp+30h] [rbp-39h]
  unsigned __int16 *v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h]
  IStream *v21; // [rsp+50h] [rbp-19h] BYREF
  BYTE *pInit[3]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v23[3]; // [rsp+70h] [rbp+7h] BYREF
  struct IXMLDOMDocument2 *v24; // [rsp+88h] [rbp+1Fh] BYREF

  v18 = 0;
  v19 = 0;
  v20 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
  v5 = -1;
  v16 = -1;
  v17 = -1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
  v19 = -1;
  v20 = -1;
  v7 = CXMLPropStoreSaxParser::_RetrieveRootNodeAndNamespace(v6, a2, &v18, &v15);
  if ( v7 >= 0 )
  {
    v8 = v15;
    v9 = 0;
    memset(v23, 0, sizeof(v23));
    if ( v15 && *v15 )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             v23,
             L"targetNamespace=\"%s\"",
             v15);
      v9 = (const WCHAR *)v23[0];
    }
    else
    {
      v7 = 0;
    }
    if ( v7 >= 0 )
    {
      v10 = &psz;
      pInit[0] = 0;
      pInit[1] = 0;
      if ( v9 )
        v10 = v9;
      pInit[2] = 0;
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             pInit,
             qword_180048020,
             v10,
             v18);
      if ( v7 >= 0 )
      {
        do
          ++v5;
        while ( *(_WORD *)&pInit[0][2 * v5] );
        v21 = SHCreateMemStream(pInit[0], 2 * (int)v5);
        v11 = v21;
        if ( v21 )
        {
          v24 = 0;
          Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v24);
          v7 = CXMLPropStoreSaxParser::_LoadDOMFromStream(v12, v11, &v24);
          if ( v7 >= 0 )
            v7 = CXMLPropStoreSaxParser::_AddSchemaToCollection(v13, v24, v8, a3);
          Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v24);
        }
        else
        {
          v7 = -2147024882;
        }
        Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(&v21);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)pInit);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v23);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800301f0  mov     [rsp-8+arg_0], rbx
0x1800301f5  push    rbp
0x1800301f6  push    rsi
0x1800301f7  push    rdi
0x1800301f8  push    r14
0x1800301fa  push    r15
0x1800301fc  lea     rbp, [rsp-37h]
0x180030201  sub     rsp, 0A0h
0x180030208  mov     rax, cs:__security_cookie
0x18003020f  xor     rax, rsp
0x180030212  mov     [rbp+57h+var_30], rax
0x180030216  xor     r15d, r15d
0x180030219  lea     rcx, [rbp+57h+var_A0]
0x18003021d  mov     [rbp+57h+var_88], r15
0x180030221  mov     r14, r8
0x180030224  mov     [rbp+57h+var_80], r15
0x180030228  mov     rbx, rdx
0x18003022b  mov     [rbp+57h+var_78], r15
0x18003022f  mov     [rbp+57h+var_A0], r15
0x180030233  mov     [rbp+57h+var_98], r15
0x180030237  mov     [rbp+57h+var_90], r15
0x18003023b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030240  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030244  lea     rcx, [rbp+57h+var_88]
0x180030248  mov     [rbp+57h+var_98], rsi
0x18003024c  mov     [rbp+57h+var_90], rsi
0x180030250  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030255  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x180030259  mov     [rbp+57h+var_80], rsi
0x18003025d  lea     r8, [rbp+57h+var_88]; unsigned __int16 **
0x180030261  mov     [rbp+57h+var_78], rsi
0x180030265  mov     rdx, rbx; struct IStream *
0x180030268  call    ?_RetrieveRootNodeAndNamespace@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAG1@Z; CXMLPropStoreSaxParser::_RetrieveRootNodeAndNamespace(IStream *,ushort * *,ushort * *)
0x18003026d  mov     ebx, eax
0x18003026f  test    eax, eax
0x180030271  js      loc_18003036D
0x180030277  mov     rdi, [rbp+57h+var_A0]
0x18003027b  mov     eax, r15d
0x18003027e  mov     [rbp+57h+var_50], rax
0x180030282  mov     [rbp+57h+var_48], r15
0x180030286  mov     [rbp+57h+var_40], r15
0x18003028a  test    rdi, rdi
0x18003028d  jz      short loc_1800302B0
0x18003028f  cmp     [rdi], r15w
0x180030293  jz      short loc_1800302B0
0x180030295  mov     r8, rdi
0x180030298  lea     rdx, aTargetnamespac; "targetNamespace=\"%s\""
0x18003029f  lea     rcx, [rbp+57h+var_50]
0x1800302a3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800302a8  mov     ebx, eax
0x1800302aa  mov     rax, [rbp+57h+var_50]
0x1800302ae  jmp     short loc_1800302B3
0x1800302b0  mov     ebx, r15d
0x1800302b3  test    ebx, ebx
0x1800302b5  js      loc_180030364
0x1800302bb  mov     r9, [rbp+57h+var_88]
0x1800302bf  lea     r8, psz
0x1800302c6  test    rax, rax
0x1800302c9  mov     [rbp+57h+pInit], r15
0x1800302cd  lea     rdx, qword_180048020
0x1800302d4  mov     [rbp+57h+var_60], r15
0x1800302d8  cmovnz  r8, rax
0x1800302dc  mov     [rbp+57h+var_58], r15
0x1800302e0  lea     rcx, [rbp+57h+pInit]
0x1800302e4  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800302e9  mov     ebx, eax
0x1800302eb  test    eax, eax
0x1800302ed  js      short loc_18003035B
0x1800302ef  mov     rcx, [rbp+57h+pInit]; pInit
0x1800302f3  inc     rsi
0x1800302f6  cmp     [rcx+rsi*2], r15w
0x1800302fb  jnz     short loc_1800302F3
0x1800302fd  lea     edx, [rsi+rsi]; cbInit
0x180030300  call    cs:__imp_SHCreateMemStream
0x180030306  mov     [rbp+57h+var_70], rax
0x18003030a  mov     rbx, rax
0x18003030d  test    rax, rax
0x180030310  jnz     short loc_180030319
0x180030312  mov     ebx, 8007000Eh
0x180030317  jmp     short loc_180030352
0x180030319  lea     rcx, [rbp+57h+var_38]
0x18003031d  mov     [rbp+57h+var_38], r15
0x180030321  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030326  lea     r8, [rbp+57h+var_38]; struct IXMLDOMDocument2 **
0x18003032a  mov     rdx, rbx; struct IStream *
0x18003032d  call    ?_LoadDOMFromStream@CXMLPropStoreSaxParser@@AEAAJPEAUIStream@@PEAPEAUIXMLDOMDocument2@@@Z; CXMLPropStoreSaxParser::_LoadDOMFromStream(IStream *,IXMLDOMDocument2 * *)
0x180030332  mov     ebx, eax
0x180030334  test    eax, eax
0x180030336  js      short loc_180030349
0x180030338  mov     rdx, [rbp+57h+var_38]; struct IXMLDOMDocument2 *
0x18003033c  mov     r9, r14; struct IXMLDOMSchemaCollection2 *
0x18003033f  mov     r8, rdi; unsigned __int16 *
0x180030342  call    ?_AddSchemaToCollection@CXMLPropStoreSaxParser@@AEAAJPEAUIXMLDOMDocument2@@PEBGPEAUIXMLDOMSchemaCollection2@@@Z; CXMLPropStoreSaxParser::_AddSchemaToCollection(IXMLDOMDocument2 *,ushort const *,IXMLDOMSchemaCollection2 *)
0x180030347  mov     ebx, eax
0x180030349  lea     rcx, [rbp+57h+var_38]
0x18003034d  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x180030352  lea     rcx, [rbp+57h+var_70]
0x180030356  call    ?InternalRelease@?$ComPtr@UIPropertyDescription@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPropertyDescription>::InternalRelease(void)
0x18003035b  lea     rcx, [rbp+57h+pInit]
0x18003035f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030364  lea     rcx, [rbp+57h+var_50]
0x180030368  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003036d  lea     rcx, [rbp+57h+var_A0]
0x180030371  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030376  lea     rcx, [rbp+57h+var_88]
0x18003037a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003037f  mov     eax, ebx
0x180030381  mov     rcx, [rbp+57h+var_30]
0x180030385  xor     rcx, rsp; StackCookie
0x180030388  call    __security_check_cookie
0x18003038d  mov     rbx, [rsp+0C0h+arg_0]
0x180030395  add     rsp, 0A0h
0x18003039c  pop     r15
0x18003039e  pop     r14
0x1800303a0  pop     rdi
0x1800303a1  pop     rsi
0x1800303a2  pop     rbp
0x1800303a3  retn
```
