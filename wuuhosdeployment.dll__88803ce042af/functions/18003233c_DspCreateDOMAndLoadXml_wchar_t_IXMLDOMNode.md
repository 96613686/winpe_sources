# DspCreateDOMAndLoadXml(wchar_t *,IXMLDOMNode * *)

- ea: `0x18003233c`
- end: `0x180032595`
- name: `?DspCreateDOMAndLoadXml@@YAJPEA_WPEAPEAUIXMLDOMNode@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(wchar_t *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019e00`

## callees

- `0x180003950`
- `0x180032288`
- `0x18003233c`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800323a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800323a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DspCreateDOMAndLoadXml(wchar_t *a1, struct IXMLDOMNode **a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int ppv; // [rsp+20h] [rbp-30h]
  __int16 v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v13; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v13 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 250;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    goto LABEL_28;
  }
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v13);
  if ( v4 < 0 )
  {
    v5 = 254;
    goto LABEL_27;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v13 + 544LL))(v13, 0);
  if ( v4 < 0 )
  {
    v5 = 255;
    goto LABEL_27;
  }
  v11 = 0;
  v12 = 0;
  if ( !v13 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)0x80004003LL,
      ppv);
LABEL_26:
    v5 = 256;
    goto LABEL_27;
  }
  v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v13)(
         v13,
         &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
         &v12);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_26;
  }
  SetNewParserProperty(v12);
  v7 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int16 *))(*(_QWORD *)v12 + 520LL))(v12, a1, &v11);
  if ( (v7 || !v11) && ((int)(v7 + 0x80000000) < 0 || v7 == -2147467259) )
  {
    v4 = -2145124338;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)0x8024000ELL,
      ppv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_26;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMNode **))v12)(
         v12,
         &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
         a2);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsmisc.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_26;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v4 = 0;
LABEL_28:
  if ( v13 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003233c  mov     [rsp-28h+arg_10], rbx
0x180032341  push    rbp
0x180032342  push    rsi
0x180032343  push    rdi
0x180032344  push    r14
0x180032346  push    r15
0x180032348  mov     rbp, rsp
0x18003234b  sub     rsp, 50h
0x18003234f  mov     rax, cs:__security_cookie
0x180032356  xor     rax, rsp
0x180032359  mov     [rbp+var_8], rax
0x18003235d  mov     rdi, rdx
0x180032360  mov     rsi, rcx
0x180032363  xor     r14d, r14d
0x180032366  mov     [rbp+var_10], r14
0x18003236a  lea     r15, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180032371  test    rdx, rdx
0x180032374  jnz     short loc_180032385
0x180032376  mov     ebx, 80004003h
0x18003237b  mov     edx, 0FAh
0x180032380  jmp     loc_18003254D
0x180032385  lea     rax, [rbp+var_10]
0x180032389  mov     qword ptr [rsp+50h+ppv], rax; int
0x18003238e  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180032395  xor     edx, edx; pUnkOuter
0x180032397  lea     r8d, [rdx+1]; dwClsContext
0x18003239b  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800323a2  call    cs:__imp_CoCreateInstance
0x1800323a8  mov     ebx, eax
0x1800323aa  test    eax, eax
0x1800323ac  jns     short loc_1800323B8
0x1800323ae  mov     edx, 0FEh
0x1800323b3  jmp     loc_18003254D
0x1800323b8  xor     edx, edx
0x1800323ba  mov     rcx, [rbp+var_10]
0x1800323be  mov     rax, [rcx]
0x1800323c1  mov     rax, [rax+220h]
0x1800323c8  call    _guard_dispatch_icall
0x1800323cd  mov     ebx, eax
0x1800323cf  test    eax, eax
0x1800323d1  jns     short loc_1800323DD
0x1800323d3  mov     edx, 0FFh
0x1800323d8  jmp     loc_18003254D
0x1800323dd  mov     rcx, [rbp+var_10]
0x1800323e1  mov     [rbp+var_20], r14w
0x1800323e6  mov     [rbp+var_18], r14
0x1800323ea  test    rcx, rcx
0x1800323ed  jnz     short loc_180032424
0x1800323ef  mov     rcx, [rbp+28h]; this
0x1800323f3  mov     ebx, 80004003h
0x1800323f8  mov     r9d, ebx; char *
0x1800323fb  mov     r8, r15; unsigned int
0x1800323fe  mov     edx, 0DDh; void *
0x180032403  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032408  nop
0x180032409  mov     rcx, [rbp+var_18]
0x18003240d  test    rcx, rcx
0x180032410  jz      short loc_18003241F
0x180032412  mov     rax, [rcx]
0x180032415  mov     rax, [rax+10h]
0x180032419  call    _guard_dispatch_icall
0x18003241e  nop
0x18003241f  jmp     loc_180032548
0x180032424  mov     rax, [rcx]
0x180032427  lea     r8, [rbp+var_18]
0x18003242b  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x180032432  mov     rax, [rax]
0x180032435  call    _guard_dispatch_icall
0x18003243a  mov     ebx, eax
0x18003243c  test    eax, eax
0x18003243e  jns     short loc_180032470
0x180032440  mov     rcx, [rbp+28h]; this
0x180032444  mov     r9d, eax; char *
0x180032447  mov     r8, r15; unsigned int
0x18003244a  mov     edx, 0DFh; void *
0x18003244f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032454  nop
0x180032455  mov     rcx, [rbp+var_18]
0x180032459  test    rcx, rcx
0x18003245c  jz      short loc_18003246B
0x18003245e  mov     rax, [rcx]
0x180032461  mov     rax, [rax+10h]
0x180032465  call    _guard_dispatch_icall
0x18003246a  nop
0x18003246b  jmp     loc_180032548
0x180032470  mov     rcx, [rbp+var_18]
0x180032474  call    SetNewParserProperty
0x180032479  mov     rcx, [rbp+var_18]
0x18003247d  mov     rax, [rcx]
0x180032480  lea     r8, [rbp+var_20]
0x180032484  mov     rdx, rsi
0x180032487  mov     rax, [rax+208h]
0x18003248e  call    _guard_dispatch_icall
0x180032493  test    eax, eax
0x180032495  jnz     short loc_18003249E
0x180032497  cmp     [rbp+var_20], r14w
0x18003249c  jnz     short loc_1800324B1
0x18003249e  mov     edx, 80000000h
0x1800324a3  lea     ecx, [rax+rdx]
0x1800324a6  test    edx, ecx
0x1800324a8  jnz     short loc_180032518
0x1800324aa  cmp     eax, 80004005h
0x1800324af  jz      short loc_180032518
0x1800324b1  mov     rcx, [rbp+var_18]
0x1800324b5  mov     rax, [rcx]
0x1800324b8  mov     r8, rdi
0x1800324bb  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1800324c2  mov     rax, [rax]
0x1800324c5  call    _guard_dispatch_icall
0x1800324ca  mov     ebx, eax
0x1800324cc  test    eax, eax
0x1800324ce  jns     short loc_1800324FD
0x1800324d0  mov     rcx, [rbp+28h]; this
0x1800324d4  mov     r9d, eax; char *
0x1800324d7  mov     r8, r15; unsigned int
0x1800324da  mov     edx, 0EFh; void *
0x1800324df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324e4  nop
0x1800324e5  mov     rcx, [rbp+var_18]
0x1800324e9  test    rcx, rcx
0x1800324ec  jz      short loc_1800324FB
0x1800324ee  mov     rax, [rcx]
0x1800324f1  mov     rax, [rax+10h]
0x1800324f5  call    _guard_dispatch_icall
0x1800324fa  nop
0x1800324fb  jmp     short loc_180032548
0x1800324fd  mov     rcx, [rbp+var_18]
0x180032501  test    rcx, rcx
0x180032504  jz      short loc_180032513
0x180032506  mov     rax, [rcx]
0x180032509  mov     rax, [rax+10h]
0x18003250d  call    _guard_dispatch_icall
0x180032512  nop
0x180032513  mov     ebx, r14d
0x180032516  jmp     short loc_18003255D
0x180032518  mov     rcx, [rbp+28h]; this
0x18003251c  mov     ebx, 8024000Eh
0x180032521  mov     r9d, ebx; char *
0x180032524  mov     r8, r15; unsigned int
0x180032527  mov     edx, 0ECh; void *
0x18003252c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032531  nop
0x180032532  mov     rcx, [rbp+var_18]
0x180032536  test    rcx, rcx
0x180032539  jz      short loc_180032548
0x18003253b  mov     rax, [rcx]
0x18003253e  mov     rax, [rax+10h]
0x180032542  call    _guard_dispatch_icall
0x180032547  nop
0x180032548  mov     edx, 100h; void *
0x18003254d  mov     rcx, [rbp+28h]; this
0x180032551  mov     r9d, ebx; char *
0x180032554  mov     r8, r15; unsigned int
0x180032557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003255c  nop
0x18003255d  mov     rcx, [rbp+var_10]
0x180032561  test    rcx, rcx
0x180032564  jz      short loc_180032573
0x180032566  mov     rdx, [rcx]
0x180032569  mov     rax, [rdx+10h]
0x18003256d  call    _guard_dispatch_icall
0x180032572  nop
0x180032573  mov     eax, ebx
0x180032575  mov     rcx, [rbp+var_8]
0x180032579  xor     rcx, rsp; StackCookie
0x18003257c  call    __security_check_cookie
0x180032581  mov     rbx, [rsp+50h+arg_10]
0x180032589  add     rsp, 50h
0x18003258d  pop     r15
0x18003258f  pop     r14
0x180032591  pop     rdi
0x180032592  pop     rsi
0x180032593  pop     rbp
0x180032594  retn
```
