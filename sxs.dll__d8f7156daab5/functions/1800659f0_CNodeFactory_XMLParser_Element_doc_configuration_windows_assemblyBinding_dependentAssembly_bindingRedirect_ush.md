# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_bindingRedirect(ushort,_SXS_NODE_INFO const *)

- ea: `0x1800659f0`
- end: `0x180065d26`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_bindingRedirect@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18001e5d0`
- `0x180020820`
- `0x180027160`
- `0x1800515ec`
- `0x180056890`
- `0x180058904`
- `0x18005d38c`
- `0x18005d428`
- `0x1800659f0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065cc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065b37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065cc9`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_bindingRedirect(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // r14
  char **v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  WCHAR *v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  const struct _UNICODE_STRING *v14; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v15; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v16; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v17; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v18; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v19; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v20; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v21; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v22; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v23; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v24; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v25; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v26; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v27; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v28; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v29; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v30; // [rsp+B0h] [rbp-90h]
  struct _UNICODE_STRING v31; // [rsp+C0h] [rbp-80h] BYREF
  unsigned __int16 *v32; // [rsp+D0h] [rbp-70h]
  struct _UNICODE_STRING v33; // [rsp+D8h] [rbp-68h] BYREF
  struct _UNICODE_STRING v34; // [rsp+E8h] [rbp-58h] BYREF
  int v35; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+100h] [rbp-40h] BYREF
  int v37; // [rsp+108h] [rbp-38h] BYREF
  __int64 v38; // [rsp+110h] [rbp-30h]
  __int64 *v39; // [rsp+118h] [rbp-28h]
  __int64 v40; // [rsp+120h] [rbp-20h]
  int v41; // [rsp+128h] [rbp-18h]
  int *v42; // [rsp+130h] [rbp-10h]
  _BYTE v43[16]; // [rsp+140h] [rbp+0h] BYREF
  unsigned __int16 *v44; // [rsp+150h] [rbp+10h]
  _BYTE v45[16]; // [rsp+1F0h] [rbp+B0h] BYREF
  unsigned __int16 *v46; // [rsp+200h] [rbp+C0h]

  v3 = a2;
  v39 = &qword_180078E68;
  v37 = 1;
  v42 = &v35;
  v35 = 0;
  v38 = 0;
  v40 = 544438355;
  v41 = 3137;
  CFrame::BaseEnter((CFrame *)&v37);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v45);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v43);
  v31.Length = 0;
  v36 = 0;
  if ( !*((_QWORD *)this + 157) )
  {
    CNodeFactory::LogParseError(
      this,
      0xC1010036,
      0x89u,
      0,
      0,
      0,
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
      v27,
      v28,
      v29,
      v30);
    goto LABEL_22;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_180072D30,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        &v31,
                        168,
                        (__int64)v45,
                        &v36,
                        0) )
  {
    v6 = off_180078E48;
LABEL_5:
    *v42 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v6);
    goto LABEL_22;
  }
  if ( !LOBYTE(v31.Length) )
    goto LABEL_21;
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_18007A070,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        &v31,
                        168,
                        (__int64)v43,
                        &v36,
                        0) )
  {
    v6 = off_180078E28;
    goto LABEL_5;
  }
  if ( !LOBYTE(v31.Length) )
  {
LABEL_21:
    SetLastError(0x54Fu);
    *v42 = 0;
    goto LABEL_22;
  }
  SetLastError(0);
  if ( !(unsigned int)CPolicyStatement::AddRedirect(*((_QWORD *)this + 157), v45, v43, (char *)&v31.Length + 1) )
  {
    v6 = off_180078E08;
    goto LABEL_5;
  }
  if ( HIBYTE(v31.Length) )
  {
    v35 = 1;
  }
  else
  {
    v7 = -1;
    v32 = v44;
    v8 = -1;
    do
      ++v8;
    while ( v44[v8] );
    LOWORD(v31.Buffer) = 2 * v8;
    WORD1(v31.Buffer) = 2 * v8;
    v9 = -1;
    v33.Buffer = v46;
    do
      ++v9;
    while ( v46[v9] );
    v33.Length = 2 * v9;
    v33.MaximumLength = 2 * v9;
    v10 = *(WCHAR **)(*((_QWORD *)this + 49) + 40LL);
    v34.Buffer = v10;
    do
      ++v7;
    while ( v10[v7] );
    v11 = *((_QWORD *)this + 2);
    v34.Length = 2 * v7;
    v34.MaximumLength = 2 * v7;
    FusionpLogActCtxGenError(
      0xC1010047,
      *(const unsigned __int16 **)(v11 + 1312),
      &v34,
      &v33,
      (const struct _UNICODE_STRING *)&v31.Buffer);
    TraceActCtxGenManifestParseError(
      *(_DWORD *)(*((_QWORD *)this + 2) + 1304LL),
      *((unsigned int *)this + 118),
      v46,
      v44,
      0,
      0x95u);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v37, 0x36B5u);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078DE8);
  }
LABEL_22:
  v12 = v35;
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v43);
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v45);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v37);
  return v12;
}

```

## disassembly

```asm
0x1800659f0  mov     [rsp-8+arg_8], rbx
0x1800659f5  push    rbp
0x1800659f6  push    rsi
0x1800659f7  push    rdi
0x1800659f8  push    r14
0x1800659fa  push    r15
0x1800659fc  lea     rbp, [rsp-170h]
0x180065a04  sub     rsp, 2B0h
0x180065a0b  mov     rax, cs:__security_cookie
0x180065a12  xor     rax, rsp
0x180065a15  mov     [rbp+190h+var_30], rax
0x180065a1c  lea     rax, qword_180078E68
0x180065a23  movzx   r14d, dx
0x180065a27  mov     [rbp+190h+var_1B8], rax
0x180065a2b  mov     rbx, rcx
0x180065a2e  lea     rax, [rbp+190h+var_1D8]
0x180065a32  mov     [rbp+190h+var_1C8], 1
0x180065a39  xor     r15d, r15d
0x180065a3c  mov     [rbp+190h+var_1A0], rax
0x180065a40  lea     rcx, [rbp+190h+var_1C8]; this
0x180065a44  mov     [rbp+190h+var_1D8], r15d
0x180065a48  mov     rdi, r8
0x180065a4b  mov     [rbp+190h+var_1C0], r15
0x180065a4f  mov     [rbp+190h+var_1B0], 20737853h
0x180065a57  mov     [rbp+190h+var_1A8], 0C41h
0x180065a5e  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180065a63  lea     rcx, [rbp+190h+var_E0]
0x180065a6a  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180065a6f  lea     rcx, [rbp+190h+var_190]
0x180065a73  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180065a78  mov     byte ptr [rbp+190h+var_210.Length], r15b
0x180065a7c  mov     byte ptr [rbp+190h+var_210.Length+1], r15b
0x180065a80  mov     [rbp+190h+var_1D0], r15
0x180065a84  cmp     [rbx+4E8h], r15
0x180065a8b  jnz     short loc_180065AB2
0x180065a8d  mov     [rsp+2D0h+var_2A8], r15; struct _UNICODE_STRING *
0x180065a92  xor     r9d, r9d; struct _UNICODE_STRING *
0x180065a95  mov     edx, 0C1010036h; unsigned int
0x180065a9a  mov     [rsp+2D0h+var_2B0], r15; struct _UNICODE_STRING *
0x180065a9f  mov     r8d, 89h; unsigned int
0x180065aa5  mov     rcx, rbx; this
0x180065aa8  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180065aad  jmp     loc_180065CDC
0x180065ab2  xor     ecx, ecx; dwErrCode
0x180065ab4  call    cs:__imp_SetLastError
0x180065abb  nop     dword ptr [rax+rax+00h]
0x180065ac0  mov     [rsp+2D0h+var_288], r15
0x180065ac5  lea     rax, [rbp+190h+var_1D0]
0x180065ac9  mov     [rsp+2D0h+var_290], rax
0x180065ace  lea     rsi, [rbx+190h]
0x180065ad5  lea     rax, [rbp+190h+var_E0]
0x180065adc  mov     r9, r14
0x180065adf  mov     [rsp+2D0h+var_298], rax
0x180065ae4  lea     rdx, qword_180072D30
0x180065aeb  lea     rax, [rbp+190h+var_210]
0x180065aef  mov     [rsp+2D0h+var_2A0], 0A8h
0x180065af8  mov     [rsp+2D0h+var_2A8], rax
0x180065afd  mov     r8, rdi
0x180065b00  mov     ecx, 1
0x180065b05  mov     [rsp+2D0h+var_2B0], rsi
0x180065b0a  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180065b0f  test    eax, eax
0x180065b11  jnz     short loc_180065B2B
0x180065b13  lea     rcx, off_180078E48; struct _CALL_SITE_INFO *
0x180065b1a  mov     rax, [rbp+190h+var_1A0]
0x180065b1e  mov     [rax], r15d
0x180065b21  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180065b26  jmp     loc_180065CDC
0x180065b2b  cmp     byte ptr [rbp+190h+var_210.Length], r15b
0x180065b2f  jz      loc_180065CC4
0x180065b35  xor     ecx, ecx; dwErrCode
0x180065b37  call    cs:__imp_SetLastError
0x180065b3e  nop     dword ptr [rax+rax+00h]
0x180065b43  mov     [rsp+2D0h+var_288], r15
0x180065b48  lea     rax, [rbp+190h+var_1D0]
0x180065b4c  mov     [rsp+2D0h+var_290], rax
0x180065b51  lea     rdx, qword_18007A070
0x180065b58  lea     rax, [rbp+190h+var_190]
0x180065b5c  mov     r9, r14
0x180065b5f  mov     [rsp+2D0h+var_298], rax
0x180065b64  mov     r8, rdi
0x180065b67  lea     rax, [rbp+190h+var_210]
0x180065b6b  mov     [rsp+2D0h+var_2A0], 0A8h
0x180065b74  mov     [rsp+2D0h+var_2A8], rax; struct _UNICODE_STRING *
0x180065b79  mov     ecx, 1
0x180065b7e  mov     [rsp+2D0h+var_2B0], rsi
0x180065b83  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180065b88  test    eax, eax
0x180065b8a  jnz     short loc_180065B95
0x180065b8c  lea     rcx, off_180078E28; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180065b93  jmp     short loc_180065B1A
0x180065b95  cmp     byte ptr [rbp+190h+var_210.Length], r15b
0x180065b99  jz      loc_180065CC4
0x180065b9f  xor     ecx, ecx; dwErrCode
0x180065ba1  call    cs:__imp_SetLastError
0x180065ba8  nop     dword ptr [rax+rax+00h]
0x180065bad  mov     rcx, [rbx+4E8h]
0x180065bb4  lea     r9, [rbp+190h+var_210.Length+1]
0x180065bb8  lea     r8, [rbp+190h+var_190]
0x180065bbc  lea     rdx, [rbp+190h+var_E0]
0x180065bc3  call    ?AddRedirect@CPolicyStatement@@QEAAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@0AEA_N@Z; CPolicyStatement::AddRedirect(CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)
0x180065bc8  test    eax, eax
0x180065bca  jnz     short loc_180065BD8
0x180065bcc  lea     rcx, off_180078E08; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180065bd3  jmp     loc_180065B1A
0x180065bd8  cmp     byte ptr [rbp+190h+var_210.Length+1], r15b
0x180065bdc  jnz     loc_180065CBB
0x180065be2  mov     rdx, [rbp+190h+var_180]
0x180065be6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180065bea  mov     [rbp+190h+var_200], rdx
0x180065bee  mov     rax, rcx
0x180065bf1  inc     rax
0x180065bf4  cmp     [rdx+rax*2], r15w
0x180065bf9  jnz     short loc_180065BF1
0x180065bfb  mov     rdx, [rbp+190h+var_D0]
0x180065c02  add     ax, ax
0x180065c05  mov     word ptr [rbp+190h+var_210.Buffer], ax
0x180065c09  mov     word ptr [rbp+190h+var_210.Buffer+2], ax
0x180065c0d  mov     rax, rcx
0x180065c10  mov     [rbp+190h+var_1F8.Buffer], rdx
0x180065c14  inc     rax
0x180065c17  cmp     [rdx+rax*2], r15w
0x180065c1c  jnz     short loc_180065C14
0x180065c1e  add     ax, ax
0x180065c21  mov     [rbp+190h+var_1F8.Length], ax
0x180065c25  mov     [rbp+190h+var_1F8.MaximumLength], ax
0x180065c29  mov     rax, [rbx+188h]
0x180065c30  mov     rdx, [rax+28h]
0x180065c34  mov     [rbp+190h+var_1E8.Buffer], rdx
0x180065c38  inc     rcx
0x180065c3b  cmp     [rdx+rcx*2], r15w
0x180065c40  jnz     short loc_180065C38
0x180065c42  mov     rdx, [rbx+10h]
0x180065c46  lea     rax, [rbp+190h+var_210.Buffer]
0x180065c4a  add     cx, cx
0x180065c4d  mov     [rsp+2D0h+var_2B0], rax; struct _UNICODE_STRING *
0x180065c52  mov     [rbp+190h+var_1E8.Length], cx
0x180065c56  lea     r9, [rbp+190h+var_1F8]; struct _UNICODE_STRING *
0x180065c5a  mov     [rbp+190h+var_1E8.MaximumLength], cx
0x180065c5e  lea     r8, [rbp+190h+var_1E8]; struct _UNICODE_STRING *
0x180065c62  mov     rdx, [rdx+520h]; unsigned __int16 *
0x180065c69  mov     ecx, 0C1010047h; unsigned int
0x180065c6e  call    ?FusionpLogActCtxGenError@@YAJKPEBGPEBU_UNICODE_STRING@@111@Z; FusionpLogActCtxGenError(ulong,ushort const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180065c73  mov     rcx, [rbx+10h]
0x180065c77  mov     r9, [rbp+190h+var_180]; unsigned __int16 *
0x180065c7b  mov     r8, [rbp+190h+var_D0]; unsigned __int16 *
0x180065c82  mov     edx, [rbx+1D8h]; unsigned int
0x180065c88  mov     ecx, [rcx+518h]; int
0x180065c8e  mov     word ptr [rsp+2D0h+var_2A8], 95h; unsigned __int16
0x180065c95  mov     [rsp+2D0h+var_2B0], r15; unsigned __int16 *
0x180065c9a  call    ?TraceActCtxGenManifestParseError@@YAKJKPEBG00G@Z; TraceActCtxGenManifestParseError(long,ulong,ushort const *,ushort const *,ushort const *,ushort)
0x180065c9f  mov     edx, 36B5h; unsigned int
0x180065ca4  lea     rcx, [rbp+190h+var_1C8]; this
0x180065ca8  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180065cad  lea     rcx, off_180078DE8; struct _CALL_SITE_INFO *
0x180065cb4  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180065cb9  jmp     short loc_180065CDC
0x180065cbb  mov     [rbp+190h+var_1D8], 1
0x180065cc2  jmp     short loc_180065CDC
0x180065cc4  mov     ecx, 54Fh; dwErrCode
0x180065cc9  call    cs:__imp_SetLastError
0x180065cd0  nop     dword ptr [rax+rax+00h]
0x180065cd5  mov     rax, [rbp+190h+var_1A0]
0x180065cd9  mov     [rax], r15d
0x180065cdc  mov     ebx, [rbp+190h+var_1D8]
0x180065cdf  lea     rcx, [rbp+190h+var_190]
0x180065ce3  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180065ce8  lea     rcx, [rbp+190h+var_E0]
0x180065cef  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180065cf4  lea     rcx, [rbp+190h+var_1C8]; this
0x180065cf8  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180065cfd  mov     eax, ebx
0x180065cff  mov     rcx, [rbp+190h+var_30]
0x180065d06  xor     rcx, rsp; StackCookie
0x180065d09  call    __security_check_cookie
0x180065d0e  mov     rbx, [rsp+2D0h+arg_8]
0x180065d16  add     rsp, 2B0h
0x180065d1d  pop     r15
0x180065d1f  pop     r14
0x180065d21  pop     rdi
0x180065d22  pop     rsi
0x180065d23  pop     rbp
0x180065d24  retn
```
