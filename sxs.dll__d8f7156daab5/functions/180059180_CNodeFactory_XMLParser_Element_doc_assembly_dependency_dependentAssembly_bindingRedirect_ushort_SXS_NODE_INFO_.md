# CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly_bindingRedirect(ushort,_SXS_NODE_INFO const *)

- ea: `0x180059180`
- end: `0x180059437`
- name: `?XMLParser_Element_doc_assembly_dependency_dependentAssembly_bindingRedirect@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x1800075a0`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180020820`
- `0x180027160`
- `0x1800515ec`
- `0x180056890`
- `0x180059180`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005924b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800592cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059389`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005924b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800592cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059389`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly_bindingRedirect(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // r14
  unsigned int v6; // edx
  unsigned int v7; // r8d
  char **v8; // rcx
  unsigned int v9; // ebx
  const struct _UNICODE_STRING *v11; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v12; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v13; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v14; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v15; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v16; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v17; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v18; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v19; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v20; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v21; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v22; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v23; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v24; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v25; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v26; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v27; // [rsp+B0h] [rbp-90h]
  char v28; // [rsp+C0h] [rbp-80h] BYREF
  _BYTE v29[3]; // [rsp+C1h] [rbp-7Fh] BYREF
  int v30; // [rsp+C4h] [rbp-7Ch] BYREF
  __int64 v31; // [rsp+C8h] [rbp-78h] BYREF
  int v32; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-68h]
  __int64 *v34; // [rsp+E0h] [rbp-60h]
  __int64 v35; // [rsp+E8h] [rbp-58h]
  int v36; // [rsp+F0h] [rbp-50h]
  int *v37; // [rsp+F8h] [rbp-48h]
  _QWORD v38[2]; // [rsp+100h] [rbp-40h] BYREF
  char *v39; // [rsp+110h] [rbp-30h]
  __int64 v40; // [rsp+118h] [rbp-28h]
  char v41; // [rsp+128h] [rbp-18h] BYREF
  _QWORD v42[2]; // [rsp+1B0h] [rbp+70h] BYREF
  char *v43; // [rsp+1C0h] [rbp+80h]
  __int64 v44; // [rsp+1C8h] [rbp+88h]
  char v45; // [rsp+1D8h] [rbp+98h] BYREF

  v3 = a2;
  v34 = &qword_180072CF0;
  v32 = 1;
  v37 = &v30;
  v30 = 0;
  v33 = 0;
  v35 = 544438355;
  v36 = 2458;
  CFrame::BaseEnter((CFrame *)&v32);
  v28 = 0;
  v29[0] = 0;
  v31 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v42);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v38);
  if ( !*((_QWORD *)this + 157) )
    goto LABEL_17;
  if ( *((_DWORD *)this + 2) != 2 )
  {
    v6 = -1056899022;
    v7 = 143;
LABEL_4:
    CNodeFactory::LogParseError(
      this,
      v6,
      v7,
      0,
      0,
      0,
      v11,
      v12,
      v13,
      v14,
      v15,
      v16,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23,
      v24,
      v25,
      v26,
      v27);
    goto LABEL_18;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_180072D30,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        &v28,
                        168,
                        (__int64)v42,
                        &v31,
                        0) )
  {
    v8 = off_180072D10;
LABEL_7:
    *v37 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
    goto LABEL_18;
  }
  if ( !v28 )
    goto LABEL_17;
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_18007A070,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        &v28,
                        168,
                        (__int64)v38,
                        &v31,
                        0) )
  {
    v8 = off_180079288;
    goto LABEL_7;
  }
  if ( v28 )
  {
    SetLastError(0);
    if ( !(unsigned int)CPolicyStatement::AddRedirect(*((_QWORD *)this + 157), v42, v38, v29) )
    {
      v8 = off_180079268;
      goto LABEL_7;
    }
    if ( !v29[0] )
    {
      v6 = -1056899021;
      v7 = 120;
      goto LABEL_4;
    }
    v30 = 1;
  }
  else
  {
LABEL_17:
    SetLastError(0x54Fu);
    *v37 = 0;
  }
LABEL_18:
  v9 = v30;
  v38[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v39 != &v41 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v38);
  v39 = 0;
  v40 = 0;
  v38[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v42[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v43 != &v45 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v42);
  v43 = 0;
  v44 = 0;
  v42[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v32);
  return v9;
}

```

## disassembly

```asm
0x180059180  mov     [rsp-8+arg_8], rbx
0x180059185  push    rbp
0x180059186  push    rsi
0x180059187  push    rdi
0x180059188  push    r14
0x18005918a  push    r15
0x18005918c  lea     rbp, [rsp-130h]
0x180059194  sub     rsp, 270h
0x18005919b  mov     rax, cs:__security_cookie
0x1800591a2  xor     rax, rsp
0x1800591a5  mov     [rbp+150h+var_30], rax
0x1800591ac  lea     rax, qword_180072CF0
0x1800591b3  movzx   r14d, dx
0x1800591b7  mov     [rbp+150h+var_1B0], rax
0x1800591bb  mov     rbx, rcx
0x1800591be  lea     rax, [rbp+150h+var_1CC]
0x1800591c2  mov     [rbp+150h+var_1C0], 1
0x1800591c9  xor     r15d, r15d
0x1800591cc  mov     [rbp+150h+var_198], rax
0x1800591d0  lea     rcx, [rbp+150h+var_1C0]; this
0x1800591d4  mov     [rbp+150h+var_1CC], r15d
0x1800591d8  mov     rdi, r8
0x1800591db  mov     [rbp+150h+var_1B8], r15
0x1800591df  mov     [rbp+150h+var_1A8], 20737853h
0x1800591e7  mov     [rbp+150h+var_1A0], 99Ah
0x1800591ee  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800591f3  lea     rcx, [rbp+150h+var_E0]
0x1800591f7  mov     [rbp+150h+var_1D0], r15b
0x1800591fb  mov     [rbp+150h+var_1CF], r15b
0x1800591ff  mov     [rbp+150h+var_1C8], r15
0x180059203  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180059208  lea     rcx, [rbp+150h+var_190]
0x18005920c  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180059211  cmp     [rbx+4E8h], r15
0x180059218  jz      loc_180059384
0x18005921e  cmp     dword ptr [rbx+8], 2
0x180059222  jz      short loc_180059249
0x180059224  mov     edx, 0C1010032h; unsigned int
0x180059229  mov     r8d, 8Fh; unsigned int
0x18005922f  mov     [rsp+290h+var_268], r15; struct _UNICODE_STRING *
0x180059234  xor     r9d, r9d; struct _UNICODE_STRING *
0x180059237  mov     rcx, rbx; this
0x18005923a  mov     [rsp+290h+var_270], r15; struct _UNICODE_STRING *
0x18005923f  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180059244  jmp     loc_18005939C
0x180059249  xor     ecx, ecx; dwErrCode
0x18005924b  call    cs:__imp_SetLastError
0x180059252  nop     dword ptr [rax+rax+00h]
0x180059257  mov     [rsp+290h+var_248], r15
0x18005925c  lea     rax, [rbp+150h+var_1C8]
0x180059260  mov     [rsp+290h+var_250], rax
0x180059265  lea     rsi, [rbx+190h]
0x18005926c  lea     rax, [rbp+150h+var_E0]
0x180059270  mov     r9, r14
0x180059273  mov     [rsp+290h+var_258], rax
0x180059278  lea     rdx, qword_180072D30
0x18005927f  lea     rax, [rbp+150h+var_1D0]
0x180059283  mov     [rsp+290h+var_260], 0A8h
0x18005928c  mov     [rsp+290h+var_268], rax
0x180059291  mov     r8, rdi
0x180059294  mov     ecx, 1
0x180059299  mov     [rsp+290h+var_270], rsi
0x18005929e  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x1800592a3  test    eax, eax
0x1800592a5  jnz     short loc_1800592BF
0x1800592a7  lea     rcx, off_180072D10; struct _CALL_SITE_INFO *
0x1800592ae  mov     rax, [rbp+150h+var_198]
0x1800592b2  mov     [rax], r15d
0x1800592b5  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800592ba  jmp     loc_18005939C
0x1800592bf  cmp     [rbp+150h+var_1D0], r15b
0x1800592c3  jz      loc_180059384
0x1800592c9  xor     ecx, ecx; dwErrCode
0x1800592cb  call    cs:__imp_SetLastError
0x1800592d2  nop     dword ptr [rax+rax+00h]
0x1800592d7  mov     [rsp+290h+var_248], r15
0x1800592dc  lea     rax, [rbp+150h+var_1C8]
0x1800592e0  mov     [rsp+290h+var_250], rax
0x1800592e5  lea     rdx, qword_18007A070
0x1800592ec  lea     rax, [rbp+150h+var_190]
0x1800592f0  mov     r9, r14
0x1800592f3  mov     [rsp+290h+var_258], rax
0x1800592f8  mov     r8, rdi
0x1800592fb  lea     rax, [rbp+150h+var_1D0]
0x1800592ff  mov     [rsp+290h+var_260], 0A8h
0x180059308  mov     [rsp+290h+var_268], rax
0x18005930d  mov     ecx, 1
0x180059312  mov     [rsp+290h+var_270], rsi
0x180059317  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18005931c  test    eax, eax
0x18005931e  jnz     short loc_180059329
0x180059320  lea     rcx, off_180079288; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180059327  jmp     short loc_1800592AE
0x180059329  cmp     [rbp+150h+var_1D0], r15b
0x18005932d  jz      short loc_180059384
0x18005932f  xor     ecx, ecx; dwErrCode
0x180059331  call    cs:__imp_SetLastError
0x180059338  nop     dword ptr [rax+rax+00h]
0x18005933d  mov     rcx, [rbx+4E8h]
0x180059344  lea     r9, [rbp+150h+var_1CF]
0x180059348  lea     r8, [rbp+150h+var_190]
0x18005934c  lea     rdx, [rbp+150h+var_E0]
0x180059350  call    ?AddRedirect@CPolicyStatement@@QEAAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@0AEA_N@Z; CPolicyStatement::AddRedirect(CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)
0x180059355  test    eax, eax
0x180059357  jnz     short loc_180059365
0x180059359  lea     rcx, off_180079268; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180059360  jmp     loc_1800592AE
0x180059365  cmp     [rbp+150h+var_1CF], r15b
0x180059369  jnz     short loc_18005937B
0x18005936b  mov     edx, 0C1010033h
0x180059370  mov     r8d, 78h ; 'x'
0x180059376  jmp     loc_18005922F
0x18005937b  mov     [rbp+150h+var_1CC], 1
0x180059382  jmp     short loc_18005939C
0x180059384  mov     ecx, 54Fh; dwErrCode
0x180059389  call    cs:__imp_SetLastError
0x180059390  nop     dword ptr [rax+rax+00h]
0x180059395  mov     rax, [rbp+150h+var_198]
0x180059399  mov     [rax], r15d
0x18005939c  mov     rdx, [rbp+150h+var_180]
0x1800593a0  lea     rax, [rbp+150h+var_168]
0x1800593a4  mov     ebx, [rbp+150h+var_1CC]
0x1800593a7  lea     rdi, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x1800593ae  mov     [rbp+150h+var_190], rdi
0x1800593b2  cmp     rdx, rax
0x1800593b5  jz      short loc_1800593C0
0x1800593b7  lea     rcx, [rbp+150h+var_190]
0x1800593bb  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x1800593c0  mov     rdx, [rbp+150h+var_D0]
0x1800593c7  lea     rax, [rbp+150h+var_B8]
0x1800593ce  mov     [rbp+150h+var_180], r15
0x1800593d2  lea     rsi, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x1800593d9  mov     [rbp+150h+var_178], r15
0x1800593dd  mov     [rbp+150h+var_190], rsi
0x1800593e1  mov     [rbp+150h+var_E0], rdi
0x1800593e5  cmp     rdx, rax
0x1800593e8  jz      short loc_1800593F3
0x1800593ea  lea     rcx, [rbp+150h+var_E0]
0x1800593ee  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x1800593f3  lea     rcx, [rbp+150h+var_1C0]; this
0x1800593f7  mov     [rbp+150h+var_D0], r15
0x1800593fe  mov     [rbp+150h+var_C8], r15
0x180059405  mov     [rbp+150h+var_E0], rsi
0x180059409  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005940e  mov     eax, ebx
0x180059410  mov     rcx, [rbp+150h+var_30]
0x180059417  xor     rcx, rsp; StackCookie
0x18005941a  call    __security_check_cookie
0x18005941f  mov     rbx, [rsp+290h+arg_8]
0x180059427  add     rsp, 270h
0x18005942e  pop     r15
0x180059430  pop     r14
0x180059432  pop     rdi
0x180059433  pop     rsi
0x180059434  pop     rbp
0x180059435  retn
```
