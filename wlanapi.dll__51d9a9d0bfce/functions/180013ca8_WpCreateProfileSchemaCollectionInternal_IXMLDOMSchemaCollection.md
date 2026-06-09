# WpCreateProfileSchemaCollectionInternal(IXMLDOMSchemaCollection * *)

- ea: `0x180013ca8`
- end: `0x180013e3a`
- name: `?WpCreateProfileSchemaCollectionInternal@@YAKPEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `402`
- prototype: `unsigned int __fastcall(struct IXMLDOMSchemaCollection **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f390`
- `0x18000f450`

## callees

- `0x180009354`
- `0x180013ca8`
- `0x180019a20`
- `0x18001a5bc`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d09`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180013cff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180013cff`
- `OLEAUT32!__imp_VariantInit` at `0x180013cd7`
- `OLEAUT32!__imp_VariantInit` at `0x180013cd7`
- `OLEAUT32!__imp_VariantClear` at `0x180013e00`
- `OLEAUT32!__imp_VariantClear` at `0x180013e00`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WpCreateProfileSchemaCollectionInternal(struct IXMLDOMSchemaCollection **a1)
{
  struct IXMLDOMSchemaCollection *v2; // rbx
  UINT SystemWindowsDirectoryW; // eax
  unsigned int LastError; // edi
  __int64 v5; // r8
  WCHAR *v6; // rax
  __int64 v7; // rdx
  const struct _XC_SCHEMA_LOCATION *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rdi
  WCHAR *v13; // r8
  wchar_t v14; // dx
  struct IXMLDOMSchemaCollection *v16; // [rsp+20h] [rbp-268h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-260h] BYREF
  OLECHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  v2 = 0;
  v16 = 0;
  VariantInit(&pvarg);
  memset_0(Buffer, 0, 0x208u);
  *a1 = 0;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW <= 0x104 )
    {
      v5 = 260;
      v6 = Buffer;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v5;
      }
      while ( v5 );
      v7 = v5 == 0 ? 0x80070057 : 0;
      v8 = (const struct _XC_SCHEMA_LOCATION *)(260 - v5);
      v9 = (260 - v5) & -(__int64)(v5 != 0);
      if ( v5 )
      {
        v10 = 2147483646;
        v11 = L"\\L2Schemas\\";
        v12 = 260 - v9;
        v13 = &Buffer[v9];
        if ( 260 != v9 )
        {
          do
          {
            if ( !v10 )
              break;
            v14 = *v11;
            if ( !*v11 )
              break;
            ++v11;
            *v13++ = v14;
            --v10;
            --v12;
          }
          while ( v12 );
        }
        v7 = v12 == 0 ? 0x8007007A : 0;
        v8 = (const struct _XC_SCHEMA_LOCATION *)(v13 - 1);
        if ( v12 )
          v8 = (const struct _XC_SCHEMA_LOCATION *)v13;
        *(_WORD *)v8 = 0;
        if ( v12 )
          goto LABEL_19;
      }
      LastError = (unsigned __int16)v7;
      if ( (v7 & 0x1FFF0000) != 0x70000 )
        LastError = v7;
      if ( !LastError )
      {
LABEL_19:
        LastError = XcCreateSchemaCollection(v8, v7, Buffer, &v16);
        if ( LastError )
        {
          v2 = v16;
        }
        else
        {
          v2 = 0;
          *a1 = v16;
        }
      }
    }
    else
    {
      LastError = 122;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  VariantClear(&pvarg);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))v2->lpVtbl->Release)(v2);
  return LastError;
}

```

## disassembly

```asm
0x180013ca8  push    rbx
0x180013caa  push    rbp
0x180013cab  push    rsi
0x180013cac  push    rdi
0x180013cad  sub     rsp, 268h
0x180013cb4  mov     rax, cs:__security_cookie
0x180013cbb  xor     rax, rsp
0x180013cbe  mov     [rsp+288h+var_38], rax
0x180013cc6  mov     rsi, rcx
0x180013cc9  xor     ebp, ebp
0x180013ccb  mov     ebx, ebp
0x180013ccd  mov     [rsp+288h+var_268], rbx
0x180013cd2  lea     rcx, [rsp+288h+pvarg]; pvarg
0x180013cd7  call    cs:__imp_VariantInit
0x180013cdd  nop
0x180013cde  xor     edx, edx; Val
0x180013ce0  mov     r8d, 208h; Size
0x180013ce6  lea     rcx, [rsp+288h+Buffer]; void *
0x180013ceb  call    memset_0
0x180013cf0  mov     [rsi], rbp
0x180013cf3  mov     edi, 104h
0x180013cf8  mov     edx, edi; uSize
0x180013cfa  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x180013cff  call    cs:__imp_GetSystemWindowsDirectoryW
0x180013d05  test    eax, eax
0x180013d07  jnz     short loc_180013D16
0x180013d09  call    cs:__imp_GetLastError
0x180013d0f  mov     edi, eax
0x180013d11  jmp     loc_180013DFB
0x180013d16  cmp     eax, edi
0x180013d18  jbe     short loc_180013D24
0x180013d1a  mov     edi, 7Ah ; 'z'
0x180013d1f  jmp     loc_180013DFB
0x180013d24  mov     r8, rdi
0x180013d27  lea     rax, [rsp+288h+Buffer]
0x180013d2c  cmp     [rax], bp
0x180013d2f  jz      short loc_180013D3B
0x180013d31  add     rax, 2
0x180013d35  sub     r8, 1
0x180013d39  jnz     short loc_180013D2C
0x180013d3b  mov     rax, r8
0x180013d3e  neg     rax
0x180013d41  sbb     edx, edx
0x180013d43  not     edx
0x180013d45  and     edx, 80070057h
0x180013d4b  mov     rax, r8
0x180013d4e  mov     rcx, rdi
0x180013d51  sub     rcx, r8
0x180013d54  neg     rax
0x180013d57  sbb     r9, r9
0x180013d5a  and     r9, rcx
0x180013d5d  test    r8, r8
0x180013d60  jz      short loc_180013DBE
0x180013d62  mov     eax, 7FFFFFFEh
0x180013d67  lea     rcx, aL2schemas; "\\L2Schemas\\"
0x180013d6e  sub     rdi, r9
0x180013d71  lea     r8, [rsp+288h+Buffer]
0x180013d76  lea     r8, [r8+r9*2]
0x180013d7a  jz      short loc_180013D9E
0x180013d7c  test    rax, rax
0x180013d7f  jz      short loc_180013D9E
0x180013d81  movzx   edx, word ptr [rcx]
0x180013d84  test    dx, dx
0x180013d87  jz      short loc_180013D9E
0x180013d89  add     rcx, 2
0x180013d8d  mov     [r8], dx
0x180013d91  add     r8, 2
0x180013d95  dec     rax
0x180013d98  sub     rdi, 1
0x180013d9c  jnz     short loc_180013D7C
0x180013d9e  mov     rax, rdi
0x180013da1  neg     rax
0x180013da4  sbb     edx, edx
0x180013da6  not     edx
0x180013da8  and     edx, 8007007Ah; unsigned int
0x180013dae  lea     rcx, [r8-2]
0x180013db2  test    rdi, rdi
0x180013db5  cmovnz  rcx, r8; struct _XC_SCHEMA_LOCATION *
0x180013db9  mov     [rcx], bp
0x180013dbc  jnz     short loc_180013DD4
0x180013dbe  mov     eax, edx
0x180013dc0  and     eax, 1FFF0000h
0x180013dc5  movzx   edi, dx
0x180013dc8  cmp     eax, 70000h
0x180013dcd  cmovnz  edi, edx
0x180013dd0  test    edi, edi
0x180013dd2  jnz     short loc_180013DFB
0x180013dd4  lea     r9, [rsp+288h+var_268]; struct IXMLDOMSchemaCollection **
0x180013dd9  lea     r8, [rsp+288h+Buffer]; unsigned __int16 *
0x180013dde  call    ?XcCreateSchemaCollection@@YAKPEBU_XC_SCHEMA_LOCATION@@KPEBGPEAPEAUIXMLDOMSchemaCollection@@@Z; XcCreateSchemaCollection(_XC_SCHEMA_LOCATION const *,ulong,ushort const *,IXMLDOMSchemaCollection * *)
0x180013de3  mov     edi, eax
0x180013de5  test    eax, eax
0x180013de7  jnz     short loc_180013DF6
0x180013de9  mov     rax, [rsp+288h+var_268]
0x180013dee  mov     rbx, rbp
0x180013df1  mov     [rsi], rax
0x180013df4  jmp     short loc_180013DFB
0x180013df6  mov     rbx, [rsp+288h+var_268]
0x180013dfb  lea     rcx, [rsp+288h+pvarg]; pvarg
0x180013e00  call    cs:__imp_VariantClear
0x180013e06  nop
0x180013e07  test    rbx, rbx
0x180013e0a  jz      short loc_180013E1C
0x180013e0c  mov     rax, [rbx]
0x180013e0f  mov     rcx, rbx
0x180013e12  mov     rax, [rax+10h]
0x180013e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e1b  nop
0x180013e1c  mov     eax, edi
0x180013e1e  mov     rcx, [rsp+288h+var_38]
0x180013e26  xor     rcx, rsp; StackCookie
0x180013e29  call    __security_check_cookie
0x180013e2e  add     rsp, 268h
0x180013e35  pop     rdi
0x180013e36  pop     rsi
0x180013e37  pop     rbp
0x180013e38  pop     rbx
0x180013e39  retn
```
