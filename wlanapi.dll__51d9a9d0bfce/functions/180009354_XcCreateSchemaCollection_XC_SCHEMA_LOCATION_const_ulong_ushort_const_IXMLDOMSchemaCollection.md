# XcCreateSchemaCollection(_XC_SCHEMA_LOCATION const *,ulong,ushort const *,IXMLDOMSchemaCollection * *)

- ea: `0x180009354`
- end: `0x18000964b`
- name: `?XcCreateSchemaCollection@@YAKPEBU_XC_SCHEMA_LOCATION@@KPEBGPEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `759`
- prototype: `unsigned int __fastcall(const struct _XC_SCHEMA_LOCATION *, unsigned int, const unsigned __int16 *, struct IXMLDOMSchemaCollection **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013ca8`

## callees

- `0x180006ef0`
- `0x180009354`
- `0x180009654`
- `0x180009860`
- `0x180019a20`
- `0x18002fb10`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009430`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009430`
- `OLEAUT32!__imp_SysAllocString` at `0x1800094ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180009531`
- `OLEAUT32!__imp_SysAllocString` at `0x1800094ef`
- `OLEAUT32!__imp_SysAllocString` at `0x180009531`
- `OLEAUT32!__imp_SysFreeString` at `0x18000946f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800094e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800094ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000946f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800094e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800094ff`
- `OLEAUT32!__imp_VariantInit` at `0x180009394`
- `OLEAUT32!__imp_VariantInit` at `0x180009394`
- `OLEAUT32!__imp_VariantClear` at `0x18000947a`
- `OLEAUT32!__imp_VariantClear` at `0x18000950d`
- `OLEAUT32!__imp_VariantClear` at `0x180009541`
- `OLEAUT32!__imp_VariantClear` at `0x18000947a`
- `OLEAUT32!__imp_VariantClear` at `0x18000950d`
- `OLEAUT32!__imp_VariantClear` at `0x180009541`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XcCreateSchemaCollection(
        const struct _XC_SCHEMA_LOCATION *a1,
        __int64 a2,
        OLECHAR *a3,
        struct IXMLDOMSchemaCollection **a4)
{
  OLECHAR *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  OLECHAR *v9; // r8
  OLECHAR v10; // cx
  unsigned int v11; // edi
  OLECHAR *v12; // rcx
  __int64 v13; // rsi
  HRESULT v14; // eax
  unsigned int i; // r14d
  struct IXMLDOMSchemaCollection *v16; // rcx
  int v18; // eax
  __int64 v19; // r10
  __int64 v20; // r11
  const OLECHAR *v21; // rdi
  BSTR v22; // rdi
  int v23; // eax
  errno_t v24; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG Source; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR psz[264]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  VariantInit(&pvarg);
  v6 = 0;
  v7 = 2147483646;
  v8 = 260;
  v9 = psz;
  do
  {
    if ( !v7 )
      break;
    v10 = *a3;
    if ( !*a3 )
      break;
    ++a3;
    *v9++ = v10;
    --v7;
    --v8;
  }
  while ( v8 );
  v11 = v8 == 0 ? 0x8007007A : 0;
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  if ( v8 || (v11 = (unsigned __int16)v11, !(_WORD)v11) )
  {
    v13 = -1;
    do
      ++v13;
    while ( psz[v13] );
    v14 = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 1u, &IID_IXMLDOMSchemaCollection, &ppv);
    v11 = v14;
    if ( v14 < 0 )
    {
      if ( (v14 & 0x1FFF0000) == 0x70000 )
        v11 = (unsigned __int16)v14;
      if ( v11 )
        goto LABEL_16;
    }
    else
    {
      v11 = 0;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= 0xA )
      {
        v16 = (struct IXMLDOMSchemaCollection *)ppv;
        ppv = 0;
        *a4 = v16;
        goto LABEL_16;
      }
      v18 = StringCchCopyW(&psz[v13], 260 - v13, off_180063090[2 * i + 1]);
      v11 = v18;
      if ( v18 < 0 )
      {
        if ( (v18 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v18;
        if ( v11 )
          goto LABEL_16;
      }
      v21 = *(const OLECHAR **)(v20 + 8 * v19);
      SysFreeString(v6);
      v6 = 0;
      v22 = SysAllocString(v21);
      if ( v22 )
      {
        SysFreeString(0);
        v6 = v22;
      }
      if ( VariantClear(&pvarg) >= 0 )
      {
        memset(&Source, 0, sizeof(Source));
        Source.vt = 8;
        Source.llVal = (LONGLONG)SysAllocString(psz);
        if ( VariantClear(&pvarg) >= 0 )
        {
          v24 = memcpy_s(&pvarg, 0x18u, &Source, 0x18u);
          ATL::AtlCrtErrorCheck(v24);
        }
      }
      if ( !v6 || pvarg.vt != 8 || !pvarg.llVal )
        break;
      Source = pvarg;
      v23 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 56LL))(ppv, v6, &Source);
      v11 = v23;
      if ( v23 < 0 )
      {
        if ( (v23 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v23;
        if ( v11 )
          goto LABEL_16;
      }
      else
      {
        v11 = 0;
      }
    }
    v11 = 8;
  }
LABEL_16:
  SysFreeString(v6);
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppv);
  return v11;
}

```

## disassembly

```asm
0x180009354  push    rbp
0x180009356  push    rbx
0x180009357  push    rsi
0x180009358  push    rdi
0x180009359  push    r12
0x18000935b  push    r13
0x18000935d  push    r14
0x18000935f  push    r15
0x180009361  lea     rbp, [rsp-198h]
0x180009369  sub     rsp, 298h
0x180009370  mov     rax, cs:__security_cookie
0x180009377  xor     rax, rsp
0x18000937a  mov     [rbp+1D0h+var_50], rax
0x180009381  mov     r15, r9
0x180009384  mov     rdi, r8
0x180009387  xor     r12d, r12d
0x18000938a  mov     [rsp+2D0h+var_2A0], r12
0x18000938f  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180009394  call    cs:__imp_VariantInit
0x18000939a  mov     ebx, r12d
0x18000939d  mov     eax, 7FFFFFFEh
0x1800093a2  mov     edx, 104h
0x1800093a7  lea     r8, [rsp+2D0h+psz]
0x1800093ac  test    rax, rax
0x1800093af  jz      short loc_1800093CE
0x1800093b1  movzx   ecx, word ptr [rdi]
0x1800093b4  test    cx, cx
0x1800093b7  jz      short loc_1800093CE
0x1800093b9  add     rdi, 2
0x1800093bd  mov     [r8], cx
0x1800093c1  add     r8, 2
0x1800093c5  dec     rax
0x1800093c8  sub     rdx, 1
0x1800093cc  jnz     short loc_1800093AC
0x1800093ce  mov     rax, rdx
0x1800093d1  neg     rax
0x1800093d4  sbb     edi, edi
0x1800093d6  not     edi
0x1800093d8  and     edi, 8007007Ah
0x1800093de  lea     rcx, [r8-2]
0x1800093e2  test    rdx, rdx
0x1800093e5  cmovnz  rcx, r8
0x1800093e9  mov     [rcx], r12w
0x1800093ed  mov     r14d, 1FFF0000h
0x1800093f3  mov     r13d, 70000h
0x1800093f9  jz      loc_1800095A4
0x1800093ff  lea     rax, [rsp+2D0h+psz]
0x180009404  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009408  inc     rsi
0x18000940b  cmp     [rax+rsi*2], r12w
0x180009410  jnz     short loc_180009408
0x180009412  lea     rax, [rsp+2D0h+var_2A0]
0x180009417  mov     [rsp+2D0h+ppv], rax; ppv
0x18000941c  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x180009423  xor     edx, edx; pUnkOuter
0x180009425  lea     r8d, [rdx+1]; dwClsContext
0x180009429  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x180009430  call    cs:__imp_CoCreateInstance
0x180009436  mov     edi, eax
0x180009438  test    eax, eax
0x18000943a  js      loc_1800095BE
0x180009440  mov     edi, r12d
0x180009443  mov     r14d, r12d
0x180009446  mov     r13d, 8
0x18000944c  lea     r11, off_180063090; "http://www.microsoft.com/networking/WLA"...
0x180009453  cmp     r14d, 0Ah
0x180009457  jb      short loc_1800094B1
0x180009459  mov     rcx, [rsp+2D0h+var_2A0]
0x18000945e  mov     [rsp+2D0h+var_2A0], r12
0x180009463  mov     [r15], rcx
0x180009466  jmp     short loc_18000946C
0x180009468  test    edi, edi
0x18000946a  jz      short loc_180009443
0x18000946c  mov     rcx, rbx; bstrString
0x18000946f  call    cs:__imp_SysFreeString
0x180009475  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18000947a  call    cs:__imp_VariantClear
0x180009480  nop
0x180009481  lea     rcx, [rsp+2D0h+var_2A0]
0x180009486  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000948b  nop
0x18000948c  mov     eax, edi
0x18000948e  mov     rcx, [rbp+1D0h+var_50]
0x180009495  xor     rcx, rsp; StackCookie
0x180009498  call    __security_check_cookie
0x18000949d  add     rsp, 298h
0x1800094a4  pop     r15
0x1800094a6  pop     r14
0x1800094a8  pop     r13
0x1800094aa  pop     r12
0x1800094ac  pop     rdi
0x1800094ad  pop     rsi
0x1800094ae  pop     rbx
0x1800094af  pop     rbp
0x1800094b0  retn
0x1800094b1  mov     r10d, r14d
0x1800094b4  add     r10, r10
0x1800094b7  mov     edx, 104h
0x1800094bc  sub     rdx, rsi; unsigned __int64
0x1800094bf  lea     rcx, [rsp+2D0h+psz]
0x1800094c4  lea     rcx, [rcx+rsi*2]; unsigned __int16 *
0x1800094c8  mov     r8, [r11+r10*8+8]; unsigned __int16 *
0x1800094cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800094d2  mov     edi, eax
0x1800094d4  test    eax, eax
0x1800094d6  js      loc_1800095D2
0x1800094dc  mov     rdi, [r11+r10*8]
0x1800094e0  mov     rcx, rbx; bstrString
0x1800094e3  call    cs:__imp_SysFreeString
0x1800094e9  mov     rbx, r12
0x1800094ec  mov     rcx, rdi; psz
0x1800094ef  call    cs:__imp_SysAllocString
0x1800094f5  mov     rdi, rax
0x1800094f8  test    rax, rax
0x1800094fb  jz      short loc_180009508
0x1800094fd  xor     ecx, ecx; bstrString
0x1800094ff  call    cs:__imp_SysFreeString
0x180009505  mov     rbx, rdi
0x180009508  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x18000950d  call    cs:__imp_VariantClear
0x180009513  test    eax, eax
0x180009515  js      short loc_18000954F
0x180009517  xorps   xmm0, xmm0
0x18000951a  xor     eax, eax
0x18000951c  movups  [rsp+2D0h+Source], xmm0
0x180009521  mov     [rsp+2D0h+var_270], rax
0x180009526  mov     word ptr [rsp+2D0h+Source], r13w
0x18000952c  lea     rcx, [rsp+2D0h+psz]; psz
0x180009531  call    cs:__imp_SysAllocString
0x180009537  mov     qword ptr [rsp+2D0h+Source+8], rax
0x18000953c  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180009541  call    cs:__imp_VariantClear
0x180009547  test    eax, eax
0x180009549  jns     loc_1800095EE
0x18000954f  test    rbx, rbx
0x180009552  jnz     loc_180009613
0x180009558  mov     edi, r13d
0x18000955b  jmp     loc_18000946C
0x180009560  mov     rcx, [rsp+2D0h+var_2A0]
0x180009565  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x18000956a  movaps  [rsp+2D0h+Source], xmm0
0x18000956f  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x180009575  movsd   [rsp+2D0h+var_270], xmm1
0x18000957b  mov     rax, [rcx]
0x18000957e  lea     r8, [rsp+2D0h+Source]
0x180009583  mov     rdx, rbx
0x180009586  mov     rax, [rax+38h]
0x18000958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958f  mov     edi, eax
0x180009591  test    eax, eax
0x180009593  js      loc_18000962F
0x180009599  mov     edi, r12d
0x18000959c  inc     r14d
0x18000959f  jmp     loc_18000944C
0x1800095a4  mov     eax, edi
0x1800095a6  and     eax, r14d
0x1800095a9  cmp     eax, r13d
0x1800095ac  jnz     short loc_1800095B1
0x1800095ae  movzx   edi, di
0x1800095b1  test    edi, edi
0x1800095b3  jnz     loc_18000946C
0x1800095b9  jmp     loc_1800093FF
0x1800095be  and     eax, r14d
0x1800095c1  cmp     eax, r13d
0x1800095c4  jnz     loc_180009468
0x1800095ca  movzx   edi, di
0x1800095cd  jmp     loc_180009468
0x1800095d2  and     eax, 1FFF0000h
0x1800095d7  cmp     eax, 70000h
0x1800095dc  jnz     short loc_1800095E1
0x1800095de  movzx   edi, di
0x1800095e1  test    edi, edi
0x1800095e3  jnz     loc_18000946C
0x1800095e9  jmp     loc_1800094DC
0x1800095ee  mov     eax, 18h
0x1800095f3  mov     r9d, eax; SourceSize
0x1800095f6  lea     r8, [rsp+2D0h+Source]; Source
0x1800095fb  mov     edx, eax; DestinationSize
0x1800095fd  lea     rcx, [rsp+2D0h+pvarg]; Destination
0x180009602  call    memcpy_s
0x180009607  mov     ecx, eax; int
0x180009609  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000960e  jmp     loc_18000954F
0x180009613  cmp     word ptr [rsp+2D0h+pvarg], r13w
0x180009619  jnz     loc_180009558
0x18000961f  cmp     qword ptr [rsp+2D0h+pvarg+8], r12
0x180009624  jz      loc_180009558
0x18000962a  jmp     loc_180009560
0x18000962f  and     eax, 1FFF0000h
0x180009634  cmp     eax, 70000h
0x180009639  jnz     short loc_18000963E
0x18000963b  movzx   edi, di
0x18000963e  test    edi, edi
0x180009640  jnz     loc_18000946C
0x180009646  jmp     loc_18000959C
```
