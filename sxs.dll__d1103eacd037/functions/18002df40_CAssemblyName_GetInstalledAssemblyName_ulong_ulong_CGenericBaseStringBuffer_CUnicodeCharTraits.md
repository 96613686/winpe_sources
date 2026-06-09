# CAssemblyName::GetInstalledAssemblyName(ulong,ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x18002df40`
- end: `0x18002e11d`
- name: `?GetInstalledAssemblyName@CAssemblyName@@QEAAJKKAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180052c98`

## callees

- `0x1800075a0`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001d6f0`
- `0x180023ee0`
- `0x180029380`
- `0x18002d3dc`
- `0x18002df40`
- `0x18002ff90`
- `0x18005cc58`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dfc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e02a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dfc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e02a`

## string_xrefs

- `0x18002e08a`: `SXS: %s - Generated %Iu character installation path:\n   "%ls"\n`
- `0x18002e07f`: `CAssemblyName::GetInstalledAssemblyName`

## pseudocode

```c
__int64 __fastcall CAssemblyName::GetInstalledAssemblyName(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  char **v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h]
  __int64 *v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  unsigned int *v16; // [rsp+70h] [rbp-90h]
  _QWORD v17[2]; // [rsp+80h] [rbp-80h] BYREF
  int v18[2]; // [rsp+90h] [rbp-70h]
  __int64 v19; // [rsp+98h] [rbp-68h]
  int v20[2]; // [rsp+A0h] [rbp-60h]
  char v21; // [rsp+A8h] [rbp-58h] BYREF

  v10 = 0;
  v13 = &qword_18006E0E8;
  v11 = 1;
  v16 = (unsigned int *)&v10;
  v12 = 0;
  v14 = 544438355;
  v15 = 465;
  CFrame::BaseEnter((CFrame *)&v11);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v17);
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyRootDirectory(v17) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v11);
    v7 = off_180076440;
LABEL_3:
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v7);
    goto LABEL_9;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(v17) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v11);
    v7 = off_180076420;
    goto LABEL_3;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetInstalledPath(
                        8,
                        a3,
                        *(__int64 *)v18,
                        *(__int64 *)v20,
                        *(struct _ASSEMBLY_IDENTITY **)(a1 + 16),
                        0,
                        a4) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v11);
    v7 = off_180076400;
    goto LABEL_3;
  }
  FusionpDbgPrintEx(
    0x80000800,
    "SXS: %s - Generated %Iu character installation path:\n   \"%ls\"\n",
    "CAssemblyName::GetInstalledAssemblyName",
    *(_QWORD *)(a4 + 32),
    *(const wchar_t **)(a4 + 16));
  *v16 = 0;
LABEL_9:
  v8 = *v16;
  v17[0] = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  if ( *(char **)v18 != &v21 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v17);
  *(_QWORD *)v18 = 0;
  v17[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v19 = 0;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v11);
  return v8;
}

```

## disassembly

```asm
0x18002df40  mov     [rsp-8+arg_8], rbx
0x18002df45  push    rbp
0x18002df46  push    rsi
0x18002df47  push    rdi
0x18002df48  lea     rbp, [rsp-1C0h]
0x18002df50  sub     rsp, 2C0h
0x18002df57  mov     rax, cs:__security_cookie
0x18002df5e  xor     rax, rsp
0x18002df61  mov     [rbp+1D0h+var_20], rax
0x18002df68  lea     rax, qword_18006E0E8
0x18002df6f  mov     [rsp+2D0h+var_290], 0
0x18002df77  mov     [rsp+2D0h+var_278], rax
0x18002df7c  mov     rdi, rcx
0x18002df7f  lea     rax, [rsp+2D0h+var_290]
0x18002df84  mov     [rsp+2D0h+var_288], 1
0x18002df8c  lea     rcx, [rsp+2D0h+var_288]; this
0x18002df91  mov     [rsp+2D0h+var_260], rax
0x18002df96  mov     rbx, r9
0x18002df99  mov     [rsp+2D0h+var_280], 0
0x18002dfa2  mov     esi, r8d
0x18002dfa5  mov     [rsp+2D0h+var_270], 20737853h
0x18002dfae  mov     [rsp+2D0h+var_268], 1D1h
0x18002dfb6  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002dfbb  lea     rcx, [rbp+1D0h+var_250]; void *
0x18002dfbf  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002dfc4  xor     ecx, ecx; dwErrCode
0x18002dfc6  call    cs:__imp_SetLastError
0x18002dfcd  nop     dword ptr [rax+rax+00h]
0x18002dfd2  lea     rcx, [rbp+1D0h+var_250]
0x18002dfd6  call    ?SxspGetAssemblyRootDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetAssemblyRootDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002dfdb  test    eax, eax
0x18002dfdd  jnz     short loc_18002DFFA
0x18002dfdf  lea     rcx, [rsp+2D0h+var_288]; this
0x18002dfe4  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18002dfe9  lea     rcx, off_180076440; struct _CALL_SITE_INFO *
0x18002dff0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002dff5  jmp     loc_18002E0AB
0x18002dffa  xor     ecx, ecx; dwErrCode
0x18002dffc  call    cs:__imp_SetLastError
0x18002e003  nop     dword ptr [rax+rax+00h]
0x18002e008  lea     rcx, [rbp+1D0h+var_250]
0x18002e00c  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x18002e011  test    eax, eax
0x18002e013  jnz     short loc_18002E028
0x18002e015  lea     rcx, [rsp+2D0h+var_288]; this
0x18002e01a  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18002e01f  lea     rcx, off_180076420; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002e026  jmp     short loc_18002DFF0
0x18002e028  xor     ecx, ecx; dwErrCode
0x18002e02a  call    cs:__imp_SetLastError
0x18002e031  nop     dword ptr [rax+rax+00h]
0x18002e036  mov     rax, [rdi+10h]
0x18002e03a  mov     edx, esi; int
0x18002e03c  mov     r9, qword ptr [rbp+1D0h+var_230]; int
0x18002e040  mov     ecx, 8; int
0x18002e045  mov     r8, qword ptr [rbp+1D0h+var_240]; int
0x18002e049  mov     [rsp+2D0h+var_2A0], rbx; __int64
0x18002e04e  mov     [rsp+2D0h+var_2A8], 0; __int64
0x18002e057  mov     [rsp+2D0h+var_2B0], rax; struct _ASSEMBLY_IDENTITY *
0x18002e05c  call    ?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18002e061  test    eax, eax
0x18002e063  jnz     short loc_18002E07B
0x18002e065  lea     rcx, [rsp+2D0h+var_288]; this
0x18002e06a  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18002e06f  lea     rcx, off_180076400; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18002e076  jmp     loc_18002DFF0
0x18002e07b  mov     rax, [rbx+10h]
0x18002e07f  lea     r8, aCassemblynameG_1; "CAssemblyName::GetInstalledAssemblyName"
0x18002e086  mov     r9, [rbx+20h]
0x18002e08a  lea     rdx, aSxsSGeneratedI; "SXS: %s - Generated %Iu character insta"...
0x18002e091  mov     ecx, 80000800h; unsigned int
0x18002e096  mov     [rsp+2D0h+var_2B0], rax
0x18002e09b  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18002e0a0  mov     rax, [rsp+2D0h+var_260]
0x18002e0a5  mov     dword ptr [rax], 0
0x18002e0ab  mov     rax, [rsp+2D0h+var_260]
0x18002e0b0  mov     rdx, qword ptr [rbp+1D0h+var_240]
0x18002e0b4  mov     ebx, [rax]
0x18002e0b6  lea     rax, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x18002e0bd  mov     [rbp+1D0h+var_250], rax
0x18002e0c1  lea     rax, [rbp+1D0h+var_228]
0x18002e0c5  cmp     rdx, rax
0x18002e0c8  jz      short loc_18002E0D3
0x18002e0ca  lea     rcx, [rbp+1D0h+var_250]
0x18002e0ce  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x18002e0d3  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x18002e0da  mov     qword ptr [rbp+1D0h+var_240], 0
0x18002e0e2  lea     rcx, [rsp+2D0h+var_288]; this
0x18002e0e7  mov     [rbp+1D0h+var_250], rax
0x18002e0eb  mov     [rbp+1D0h+var_238], 0
0x18002e0f3  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x18002e0f8  mov     eax, ebx
0x18002e0fa  mov     rcx, [rbp+1D0h+var_20]
0x18002e101  xor     rcx, rsp; StackCookie
0x18002e104  call    __security_check_cookie
0x18002e109  mov     rbx, [rsp+2D0h+arg_8]
0x18002e111  add     rsp, 2C0h
0x18002e118  pop     rdi
0x18002e119  pop     rsi
0x18002e11a  pop     rbp
0x18002e11b  retn
```
