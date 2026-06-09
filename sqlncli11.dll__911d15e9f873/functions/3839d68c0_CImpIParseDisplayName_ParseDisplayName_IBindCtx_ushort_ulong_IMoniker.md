# CImpIParseDisplayName::ParseDisplayName(IBindCtx *,ushort *,ulong *,IMoniker * *)

- ea: `0x3839d68c0`
- end: `0x3839d6c0c`
- name: `?ParseDisplayName@CImpIParseDisplayName@@UEAAJPEAUIBindCtx@@PEAGPEAKPEAPEAUIMoniker@@@Z`
- size: `844`
- prototype: `int(CImpIParseDisplayName *__hidden this, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct IMoniker **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x3838434c0`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839bd770`
- `0x3839d68c0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x3839d69de`
- `ole32!CoCreateInstance` at `0x3839d69de`
- `ole32!CreatePointerMoniker` at `0x3839d6acc`
- `ole32!CreatePointerMoniker` at `0x3839d6acc`
- `OLEAUT32!__imp_SysAllocString` at `0x3839d6a6d`
- `OLEAUT32!__imp_SysAllocString` at `0x3839d6a6d`
- `OLEAUT32!__imp_VariantInit` at `0x3839d69ba`
- `OLEAUT32!__imp_VariantInit` at `0x3839d69ba`
- `OLEAUT32!__imp_VariantClear` at `0x3839d6b12`
- `OLEAUT32!__imp_VariantClear` at `0x3839d6b12`
- `OLEAUT32!__imp_SetErrorInfo` at `0x3839d69b0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x3839d69b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIParseDisplayName::ParseDisplayName(
        CImpIParseDisplayName *this,
        struct IBindCtx *a2,
        const struct _GUID *a3,
        unsigned int *a4,
        struct IMoniker **ppmk)
{
  __int64 v7; // rcx
  HRESULT v8; // eax
  HRESULT PointerMoniker; // ebx
  int v10; // eax
  LPVOID ppv; // [rsp+40h] [rbp-81h] BYREF
  __int64 v13; // [rsp+48h] [rbp-79h] BYREF
  LPUNKNOWN punk[2]; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v15; // [rsp+60h] [rbp-61h] BYREF
  int v16; // [rsp+68h] [rbp-59h]
  GUID v17; // [rsp+6Ch] [rbp-55h]
  __int64 v18; // [rsp+80h] [rbp-41h] BYREF
  DBID v19; // [rsp+90h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-11h] BYREF

  punk[1] = (LPUNKNOWN)-2LL;
  v13 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4A950[0] )
    bidScopeEnterW(&v13, off_383B4A950[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  if ( ppmk )
    *ppmk = 0;
  if ( !a3 || !a4 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B432A0[0], 521257, off_383B49128[0], 2147746277LL);
    v7 = 2147746277LL;
    goto LABEL_32;
  }
  if ( !ppmk )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B432A0[0], 527401, off_383B49128[0], 2147549183LL);
    v7 = 2147549183LL;
LABEL_32:
    PointerMoniker = CError::PostHResult((CError *)v7, (int)&IID_IParseDisplayName, a3);
    goto LABEL_33;
  }
  ppv = 0;
  punk[0] = 0;
  SetErrorInfo(0, 0);
  VariantInit(&pvarg);
  v8 = CoCreateInstance(&CLSID_SQLNCLI11, 0, 1u, &IID_IDBProperties, &ppv);
  PointerMoniker = v8;
  if ( v8 >= 0 )
  {
    v15 = &v18;
    v16 = 1;
    v17 = DBPROPSET_DBINIT;
    v18 = 59;
    v19 = DB_NULLID;
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString((const OLECHAR *)a3);
    v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 **))(*(_QWORD *)ppv + 40LL))(ppv, 1, &v15);
    PointerMoniker = v10;
    if ( v10 >= 0 )
    {
      (**(void (__fastcall ***)(LPVOID, GUID *, LPUNKNOWN *))ppv)(ppv, &IID_IUnknown, punk);
      PointerMoniker = CreatePointerMoniker(punk[0], ppmk);
      if ( PointerMoniker < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B432A0[0], 583689, off_383B49120[0], 570);
        *ppmk = 0;
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      bidTraceHR(off_383B432A0[0], 573449, (unsigned int)v10);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceHR(off_383B432A0[0], 555017, (unsigned int)v8);
  }
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( punk[0] )
    ((void (__fastcall *)(LPUNKNOWN))punk[0]->lpVtbl->Release)(punk[0]);
LABEL_33:
  if ( (bidGblFlags & 2) != 0 && off_383B496E0[0] )
    bidTraceW(off_383B432A0[0], 600064, off_383B496E0[0], (unsigned int)PointerMoniker);
  if ( v13 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return (unsigned int)PointerMoniker;
}

```

## disassembly

```asm
0x3839d68c0  push    rbp
0x3839d68c2  push    rbx
0x3839d68c3  push    rsi
0x3839d68c4  push    rdi
0x3839d68c5  push    r14
0x3839d68c7  push    r15
0x3839d68c9  lea     rbp, [rsp-27h]
0x3839d68ce  sub     rsp, 0E8h
0x3839d68d5  mov     [rbp+4Fh+var_B8], 0FFFFFFFFFFFFFFFEh
0x3839d68dd  mov     rax, cs:__security_cookie
0x3839d68e4  xor     rax, rsp
0x3839d68e7  mov     [rbp+4Fh+var_40], rax
0x3839d68eb  mov     r14, r9
0x3839d68ee  mov     rsi, r8
0x3839d68f1  mov     rdi, [rbp+4Fh+ppmk]
0x3839d68f5  mov     [rbp+4Fh+var_C8], 0FFFFFFFFFFFFFFFFh
0x3839d68fd  test    byte ptr cs:_bidGblFlags, 4
0x3839d6904  jz      short loc_3839D693C
0x3839d6906  mov     rax, cs:off_383B4A950; "<IParseDisplayName::ParseDisplayName|OL"...
0x3839d690d  test    rax, rax
0x3839d6910  jz      short loc_3839D693C
0x3839d6912  mov     rax, [rcx+8]
0x3839d6916  mov     [rsp+110h+var_E0], rdi
0x3839d691b  mov     [rsp+110h+var_E8], r9
0x3839d6920  mov     [rsp+110h+ppv], r8
0x3839d6925  mov     r9, rdx
0x3839d6928  mov     r8d, [rax+34h]
0x3839d692c  mov     rdx, cs:off_383B4A950; "<IParseDisplayName::ParseDisplayName|OL"...
0x3839d6933  lea     rcx, [rbp+4Fh+var_C8]
0x3839d6937  call    _bidScopeEnterW
0x3839d693c  xor     r15d, r15d
0x3839d693f  test    rdi, rdi
0x3839d6942  jz      short loc_3839D6947
0x3839d6944  mov     [rdi], r15
0x3839d6947  test    rsi, rsi
0x3839d694a  jz      loc_3839D6B39
0x3839d6950  test    r14, r14
0x3839d6953  jz      loc_3839D6B39
0x3839d6959  test    rdi, rdi
0x3839d695c  jnz     short loc_3839D69A3
0x3839d695e  test    byte ptr cs:_bidGblFlags, 2
0x3839d6965  jz      short loc_3839D6999
0x3839d6967  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d696e  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839d6975  test    rax, rax
0x3839d6978  jz      short loc_3839D6999
0x3839d697a  mov     dword ptr [rsp+110h+ppv], 203h
0x3839d6982  mov     r9d, 8000FFFFh
0x3839d6988  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839d698f  mov     edx, 80C29h
0x3839d6994  call    _bidTraceW
0x3839d6999  mov     ecx, 8000FFFFh
0x3839d699e  jmp     loc_3839D6B79
0x3839d69a3  mov     [rsp+110h+var_D0], r15
0x3839d69a8  mov     [rbp+4Fh+punk], r15
0x3839d69ac  xor     edx, edx; perrinfo
0x3839d69ae  xor     ecx, ecx; dwReserved
0x3839d69b0  call    cs:__imp_SetErrorInfo
0x3839d69b6  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x3839d69ba  call    cs:__imp_VariantInit
0x3839d69c0  lea     r11, [rsp+110h+var_D0]
0x3839d69c5  mov     [rsp+110h+ppv], r11; ppv
0x3839d69ca  lea     r9, IID_IDBProperties; riid
0x3839d69d1  xor     edx, edx; pUnkOuter
0x3839d69d3  lea     r8d, [rdx+1]; dwClsContext
0x3839d69d7  lea     rcx, CLSID_SQLNCLI11; rclsid
0x3839d69de  call    cs:__imp_CoCreateInstance
0x3839d69e4  mov     ebx, eax
0x3839d69e6  test    eax, eax
0x3839d69e8  jns     short loc_3839D6A10
0x3839d69ea  test    byte ptr cs:_bidGblFlags, 2
0x3839d69f1  jz      loc_3839D6B0E
0x3839d69f7  mov     r8d, eax
0x3839d69fa  mov     edx, 87809h
0x3839d69ff  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d6a06  call    _bidTraceHR
0x3839d6a0b  jmp     loc_3839D6B0E
0x3839d6a10  lea     rax, [rbp+4Fh+var_90]
0x3839d6a14  mov     [rbp+4Fh+var_B0], rax
0x3839d6a18  mov     [rbp+4Fh+var_A8], 1
0x3839d6a1f  mov     eax, cs:DBPROPSET_DBINIT.Data1
0x3839d6a25  mov     [rbp+4Fh+var_A4], eax
0x3839d6a28  mov     eax, dword ptr cs:DBPROPSET_DBINIT.Data2
0x3839d6a2e  mov     [rbp+4Fh+var_A0], eax
0x3839d6a31  mov     eax, dword ptr cs:DBPROPSET_DBINIT.Data4
0x3839d6a37  mov     [rbp+4Fh+var_9C], eax
0x3839d6a3a  mov     eax, dword ptr cs:DBPROPSET_DBINIT.Data4+4
0x3839d6a40  mov     [rbp+4Fh+var_98], eax
0x3839d6a43  mov     [rbp+4Fh+var_90], 3Bh ; ';'
0x3839d6a4b  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x3839d6a52  movaps  [rbp+4Fh+var_80], xmm0
0x3839d6a56  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x3839d6a5d  movaps  [rbp+4Fh+var_70], xmm1
0x3839d6a61  mov     eax, 8
0x3839d6a66  mov     word ptr [rbp+4Fh+pvarg], ax
0x3839d6a6a  mov     rcx, rsi; psz
0x3839d6a6d  call    cs:__imp_SysAllocString
0x3839d6a73  mov     qword ptr [rbp+4Fh+pvarg+8], rax
0x3839d6a77  mov     rcx, [rsp+110h+var_D0]
0x3839d6a7c  mov     rax, [rcx]
0x3839d6a7f  lea     r8, [rbp+4Fh+var_B0]
0x3839d6a83  mov     edx, 1
0x3839d6a88  call    qword ptr [rax+28h]
0x3839d6a8b  mov     ebx, eax
0x3839d6a8d  test    eax, eax
0x3839d6a8f  jns     short loc_3839D6AB0
0x3839d6a91  test    byte ptr cs:_bidGblFlags, 2
0x3839d6a98  jz      short loc_3839D6B0E
0x3839d6a9a  mov     r8d, eax
0x3839d6a9d  mov     edx, 8C009h
0x3839d6aa2  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d6aa9  call    _bidTraceHR
0x3839d6aae  jmp     short loc_3839D6B0E
0x3839d6ab0  mov     rcx, [rsp+110h+var_D0]
0x3839d6ab5  mov     rax, [rcx]
0x3839d6ab8  lea     r8, [rbp+4Fh+punk]
0x3839d6abc  lea     rdx, IID_IUnknown
0x3839d6ac3  call    qword ptr [rax]
0x3839d6ac5  mov     rdx, rdi; ppmk
0x3839d6ac8  mov     rcx, [rbp+4Fh+punk]; punk
0x3839d6acc  call    cs:__imp_CreatePointerMoniker
0x3839d6ad2  mov     ebx, eax
0x3839d6ad4  test    eax, eax
0x3839d6ad6  jns     short loc_3839D6B0E
0x3839d6ad8  test    byte ptr cs:_bidGblFlags, 2
0x3839d6adf  jz      short loc_3839D6B0B
0x3839d6ae1  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d6ae8  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839d6aef  test    rax, rax
0x3839d6af2  jz      short loc_3839D6B0B
0x3839d6af4  mov     r9d, 23Ah
0x3839d6afa  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839d6b01  mov     edx, 8E809h
0x3839d6b06  call    _bidTraceW
0x3839d6b0b  mov     [rdi], r15
0x3839d6b0e  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x3839d6b12  call    cs:__imp_VariantClear
0x3839d6b18  mov     rcx, [rsp+110h+var_D0]
0x3839d6b1d  test    rcx, rcx
0x3839d6b20  jz      short loc_3839D6B28
0x3839d6b22  mov     rax, [rcx]
0x3839d6b25  call    qword ptr [rax+10h]
0x3839d6b28  mov     rcx, [rbp+4Fh+punk]
0x3839d6b2c  test    rcx, rcx
0x3839d6b2f  jz      short loc_3839D6B87
0x3839d6b31  mov     rax, [rcx]
0x3839d6b34  call    qword ptr [rax+10h]
0x3839d6b37  jmp     short loc_3839D6B87
0x3839d6b39  test    byte ptr cs:_bidGblFlags, 2
0x3839d6b40  jz      short loc_3839D6B74
0x3839d6b42  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d6b49  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839d6b50  test    rax, rax
0x3839d6b53  jz      short loc_3839D6B74
0x3839d6b55  mov     dword ptr [rsp+110h+ppv], 1FDh
0x3839d6b5d  mov     r9d, 800401E5h
0x3839d6b63  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839d6b6a  mov     edx, 7F429h
0x3839d6b6f  call    _bidTraceW
0x3839d6b74  mov     ecx, 800401E5h; this
0x3839d6b79  lea     rdx, IID_IParseDisplayName; int
0x3839d6b80  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x3839d6b85  mov     ebx, eax
0x3839d6b87  test    byte ptr cs:_bidGblFlags, 2
0x3839d6b8e  jz      short loc_3839D6BC2
0x3839d6b90  mov     rax, cs:off_383B496E0; "<IParseDisplayName::ParseDisplayName|OL"...
0x3839d6b97  test    rax, rax
0x3839d6b9a  jz      short loc_3839D6BC2
0x3839d6b9c  mov     [rsp+110h+var_E8], rdi
0x3839d6ba1  mov     [rsp+110h+ppv], r14
0x3839d6ba6  mov     r9d, ebx
0x3839d6ba9  mov     r8, cs:off_383B496E0; "<IParseDisplayName::ParseDisplayName|OL"...
0x3839d6bb0  mov     edx, 92800h
0x3839d6bb5  mov     rcx, cs:off_383B432A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839d6bbc  call    _bidTraceW
0x3839d6bc1  nop
0x3839d6bc2  cmp     [rbp+4Fh+var_C8], 0FFFFFFFFFFFFFFFFh
0x3839d6bc7  jz      short loc_3839D6BEE
0x3839d6bc9  test    byte ptr cs:_bidGblFlags, 4
0x3839d6bd0  jz      short loc_3839D6BEE
0x3839d6bd2  mov     rcx, cs:_bidID
0x3839d6bd9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3839d6bdd  jz      short loc_3839D6BEE
0x3839d6bdf  lea     r9, [rbp+4Fh+var_C8]
0x3839d6be3  xor     r8d, r8d
0x3839d6be6  xor     edx, edx
0x3839d6be8  call    cs:off_383B15058
0x3839d6bee  mov     eax, ebx
0x3839d6bf0  mov     rcx, [rbp+4Fh+var_40]
0x3839d6bf4  xor     rcx, rsp; StackCookie
0x3839d6bf7  call    __security_check_cookie
0x3839d6bfc  add     rsp, 0E8h
0x3839d6c03  pop     r15
0x3839d6c05  pop     r14
0x3839d6c07  pop     rdi
0x3839d6c08  pop     rsi
0x3839d6c09  pop     rbx
0x3839d6c0a  pop     rbp
0x3839d6c0b  retn
```
