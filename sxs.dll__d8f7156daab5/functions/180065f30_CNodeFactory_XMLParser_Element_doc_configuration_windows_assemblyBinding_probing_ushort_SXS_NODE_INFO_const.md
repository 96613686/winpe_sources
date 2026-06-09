# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_probing(ushort,_SXS_NODE_INFO const *)

- ea: `0x180065f30`
- end: `0x180066130`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_probing@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180014260`
- `0x18001c270`
- `0x180027160`
- `0x180029380`
- `0x1800515ec`
- `0x180059f28`
- `0x18005d38c`
- `0x180065f30`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066033`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006607a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065fb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066033`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006607a`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_probing(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rax
  unsigned int v7; // ebx
  struct _UNICODE_STRING *v9; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v10; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v11; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v12; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v13; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v14; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v15; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v16; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v17; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v18; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v19; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v20; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v21; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v22; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v23; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v24; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v25; // [rsp+B0h] [rbp-90h]
  _BYTE v26[8]; // [rsp+C0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v27; // [rsp+C8h] [rbp-78h] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  int v29; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-58h]
  __int64 *v31; // [rsp+F0h] [rbp-50h]
  __int64 v32; // [rsp+F8h] [rbp-48h]
  int v33; // [rsp+100h] [rbp-40h]
  unsigned int *v34; // [rsp+108h] [rbp-38h]
  struct _UNICODE_STRING v35; // [rsp+110h] [rbp-30h] BYREF
  struct _UNICODE_STRING v36; // [rsp+120h] [rbp-20h] BYREF
  WCHAR *v37; // [rsp+130h] [rbp-10h]

  v3 = a2;
  v31 = &qword_180079088;
  v29 = 1;
  v34 = (unsigned int *)&v28;
  v28 = 0;
  v30 = 0;
  v32 = 544438355;
  v33 = 2863;
  CFrame::BaseEnter((CFrame *)&v29);
  v26[0] = 0;
  *(_QWORD *)&v35.Length = 0;
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(&v36);
  SetLastError(0);
  if ( (unsigned int)SxspGetAttributeValue(
                       0,
                       (WCHAR **)qword_180079B30,
                       (__int64)a3,
                       v3,
                       (__int64)this + 400,
                       v26,
                       560,
                       (__int64)&v36,
                       &v35,
                       0) )
  {
    if ( v26[0] )
    {
      if ( (unsigned int)SxspAddPrivateProbingPathParts(
                           (__int64)&v36,
                           *((_QWORD *)this + 2) + 640LL,
                           *((_QWORD *)this + 2) + 2392LL)
        && *(_QWORD *)(*((_QWORD *)this + 2) + 2416LL) <= 0xAu )
      {
        SetLastError(0);
        *v34 = 1;
      }
      else
      {
        v6 = -1;
        v27.Buffer = v37;
        do
          ++v6;
        while ( v37[v6] );
        v27.Length = 2 * v6;
        v27.MaximumLength = 2 * v6;
        CNodeFactory::LogParseError(
          this,
          0xC1010050,
          0x99u,
          &v27,
          0,
          0,
          v9,
          v10,
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
          v25);
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v29, 0x36B5u);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180079048);
      }
    }
    else
    {
      SetLastError(0x54Fu);
      *v34 = 0;
    }
  }
  else
  {
    *v34 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079068);
  }
  v7 = *v34;
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(&v36);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v29);
  return v7;
}

```

## disassembly

```asm
0x180065f30  mov     [rsp-8+arg_8], rbx
0x180065f35  mov     [rsp-8+arg_18], rsi
0x180065f3a  push    rbp
0x180065f3b  push    rdi
0x180065f3c  push    r14
0x180065f3e  lea     rbp, [rsp-220h]
0x180065f46  sub     rsp, 360h
0x180065f4d  mov     rax, cs:__security_cookie
0x180065f54  xor     rax, rsp
0x180065f57  mov     [rbp+230h+var_20], rax
0x180065f5e  lea     rax, qword_180079088
0x180065f65  movzx   ebx, dx
0x180065f68  mov     [rbp+230h+var_280], rax
0x180065f6c  mov     rsi, rcx
0x180065f6f  lea     rax, [rbp+230h+var_298]
0x180065f73  mov     [rbp+230h+var_290], 1
0x180065f7a  xor     r14d, r14d
0x180065f7d  mov     [rbp+230h+var_268], rax
0x180065f81  lea     rcx, [rbp+230h+var_290]; this
0x180065f85  mov     [rbp+230h+var_298], r14d
0x180065f89  mov     rdi, r8
0x180065f8c  mov     [rbp+230h+var_288], r14
0x180065f90  mov     [rbp+230h+var_278], 20737853h
0x180065f98  mov     [rbp+230h+var_270], 0B2Fh
0x180065f9f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180065fa4  lea     rcx, [rbp+230h+var_250]; void *
0x180065fa8  mov     [rbp+230h+var_2B0], r14b
0x180065fac  mov     qword ptr [rbp+230h+var_260.Length], r14
0x180065fb0  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180065fb5  xor     ecx, ecx; dwErrCode
0x180065fb7  call    cs:__imp_SetLastError
0x180065fbe  nop     dword ptr [rax+rax+00h]
0x180065fc3  mov     [rsp+370h+var_328], r14; struct _UNICODE_STRING *
0x180065fc8  lea     rcx, [rbp+230h+var_260]
0x180065fcc  mov     [rsp+370h+var_330], rcx; struct _UNICODE_STRING *
0x180065fd1  lea     rax, [rsi+190h]
0x180065fd8  lea     rcx, [rbp+230h+var_250]
0x180065fdc  mov     r9d, ebx
0x180065fdf  mov     [rsp+370h+var_338], rcx; struct _UNICODE_STRING *
0x180065fe4  lea     rdx, qword_180079B30
0x180065feb  lea     rcx, [rbp+230h+var_2B0]
0x180065fef  mov     [rsp+370h+var_340], 230h; struct _UNICODE_STRING *
0x180065ff8  mov     [rsp+370h+var_348], rcx
0x180065ffd  mov     r8, rdi
0x180066000  xor     ecx, ecx
0x180066002  mov     [rsp+370h+var_350], rax
0x180066007  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18006600c  test    eax, eax
0x18006600e  jnz     short loc_180066028
0x180066010  mov     rax, [rbp+230h+var_268]
0x180066014  lea     rcx, off_180079068; struct _CALL_SITE_INFO *
0x18006601b  mov     [rax], r14d
0x18006601e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180066023  jmp     loc_1800660EE
0x180066028  cmp     [rbp+230h+var_2B0], r14b
0x18006602c  jnz     short loc_18006604B
0x18006602e  mov     ecx, 54Fh; dwErrCode
0x180066033  call    cs:__imp_SetLastError
0x18006603a  nop     dword ptr [rax+rax+00h]
0x18006603f  mov     rax, [rbp+230h+var_268]
0x180066043  mov     [rax], r14d
0x180066046  jmp     loc_1800660EE
0x18006604b  mov     rdx, [rsi+10h]
0x18006604f  lea     rcx, [rbp+230h+var_250]
0x180066053  lea     r8, [rdx+958h]
0x18006605a  add     rdx, 280h
0x180066061  call    ?SxspAddPrivateProbingPathParts@@YAHAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@0PEAV?$CFusionArray@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@V1@$0A@$0CA@@@@Z; SxspAddPrivateProbingPathParts(CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,CFusionArray<CGenericStringBuffer<260,CUnicodeCharTraits>,CGenericStringBuffer<260,CUnicodeCharTraits>,0,32> *)
0x180066066  test    eax, eax
0x180066068  jz      short loc_180066092
0x18006606a  mov     rax, [rsi+10h]
0x18006606e  cmp     qword ptr [rax+970h], 0Ah
0x180066076  ja      short loc_180066092
0x180066078  xor     ecx, ecx; dwErrCode
0x18006607a  call    cs:__imp_SetLastError
0x180066081  nop     dword ptr [rax+rax+00h]
0x180066086  mov     rax, [rbp+230h+var_268]
0x18006608a  mov     dword ptr [rax], 1
0x180066090  jmp     short loc_1800660EE
0x180066092  mov     rcx, [rbp+230h+var_240]
0x180066096  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006609a  mov     [rbp+230h+var_2A8.Buffer], rcx
0x18006609e  inc     rax
0x1800660a1  cmp     [rcx+rax*2], r14w
0x1800660a6  jnz     short loc_18006609E
0x1800660a8  add     ax, ax
0x1800660ab  mov     [rsp+370h+var_348], r14; struct _UNICODE_STRING *
0x1800660b0  lea     r9, [rbp+230h+var_2A8]; struct _UNICODE_STRING *
0x1800660b4  mov     [rbp+230h+var_2A8.Length], ax
0x1800660b8  mov     edx, 0C1010050h; unsigned int
0x1800660bd  mov     [rbp+230h+var_2A8.MaximumLength], ax
0x1800660c1  mov     r8d, 99h; unsigned int
0x1800660c7  mov     [rsp+370h+var_350], r14; struct _UNICODE_STRING *
0x1800660cc  mov     rcx, rsi; this
0x1800660cf  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800660d4  mov     edx, 36B5h; unsigned int
0x1800660d9  lea     rcx, [rbp+230h+var_290]; this
0x1800660dd  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x1800660e2  lea     rcx, off_180079048; struct _CALL_SITE_INFO *
0x1800660e9  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800660ee  mov     rax, [rbp+230h+var_268]
0x1800660f2  lea     rcx, [rbp+230h+var_250]; void *
0x1800660f6  mov     ebx, [rax]
0x1800660f8  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x1800660fd  lea     rcx, [rbp+230h+var_290]; this
0x180066101  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180066106  mov     eax, ebx
0x180066108  mov     rcx, [rbp+230h+var_20]
0x18006610f  xor     rcx, rsp; StackCookie
0x180066112  call    __security_check_cookie
0x180066117  lea     r11, [rsp+370h+var_10]
0x18006611f  mov     rbx, [r11+28h]
0x180066123  mov     rsi, [r11+38h]
0x180066127  mov     rsp, r11
0x18006612a  pop     r14
0x18006612c  pop     rdi
0x18006612d  pop     rbp
0x18006612e  retn
```
