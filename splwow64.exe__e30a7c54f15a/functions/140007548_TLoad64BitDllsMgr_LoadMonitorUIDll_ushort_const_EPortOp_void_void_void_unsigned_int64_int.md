# TLoad64BitDllsMgr::LoadMonitorUIDll(ushort const *,EPortOp,void * *,void * *,void * *,unsigned __int64 *,int *)

- ea: `0x140007548`
- end: `0x140007788`
- name: `?LoadMonitorUIDll@TLoad64BitDllsMgr@@IEBAKPEBGW4EPortOp@@PEAPEAX22PEA_KPEAH@Z`
- size: `576`
- prototype: `unsigned int __high(const unsigned __int16 *, enum EPortOp, void **, void **, void **, unsigned __int64 *, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1400066c0`
- `0x1400067b0`
- `0x1400068d0`

## callees

- `0x140001b90`
- `0x140001b9c`
- `0x1400028b8`
- `0x14000719c`
- `0x140007548`
- `0x140007d54`
- `0x140014a90`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000761c`
- `KERNEL32!GetLastError` at `0x1400076bf`
- `KERNEL32!GetLastError` at `0x1400076c9`
- `KERNEL32!GetLastError` at `0x14000761c`
- `KERNEL32!GetLastError` at `0x1400076bf`
- `KERNEL32!GetLastError` at `0x1400076c9`
- `KERNEL32!GetProcAddress` at `0x140007665`
- `KERNEL32!GetProcAddress` at `0x140007665`
- `KERNEL32!CreateActCtxW` at `0x1400075f4`
- `KERNEL32!CreateActCtxW` at `0x1400075f4`
- `KERNEL32!ActivateActCtx` at `0x140007612`
- `KERNEL32!ActivateActCtx` at `0x140007612`
- `KERNEL32!LoadLibraryW` at `0x140007649`
- `KERNEL32!LoadLibraryW` at `0x140007649`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::LoadMonitorUIDll(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        _QWORD *a4,
        HMODULE *a5,
        __int64 *a6,
        ULONG_PTR *lpCookie,
        int *a8)
{
  __int64 v8; // rdi
  __int64 v9; // r14
  unsigned __int16 *v12; // rax
  TLoad64BitDllsMgr *v13; // rcx
  unsigned __int16 *v14; // r15
  TLoad64BitDllsMgr *v15; // rcx
  DWORD MonitorUIFullPath; // ebx
  __int64 v17; // rax
  HMODULE LibraryW; // rax
  __int64 (*ProcAddress)(void); // rax
  _QWORD *v20; // rax
  const wchar_t *v22; // [rsp+30h] [rbp-81h] BYREF
  __int64 v23; // [rsp+38h] [rbp-79h]
  int v24; // [rsp+40h] [rbp-71h]
  int v25; // [rsp+48h] [rbp-69h] BYREF
  __int64 v26; // [rsp+50h] [rbp-61h]
  int v27; // [rsp+58h] [rbp-59h]
  DWORD v28; // [rsp+60h] [rbp-51h] BYREF
  __int64 v29; // [rsp+68h] [rbp-49h]
  int v30; // [rsp+70h] [rbp-41h]
  ACTCTXW pActCtx; // [rsp+78h] [rbp-39h] BYREF

  v8 = -1;
  v9 = a3;
  *a8 = 0;
  *a6 = -1;
  *lpCookie = 0;
  *a5 = 0;
  v12 = (unsigned __int16 *)operator new[](0x208u);
  v14 = v12;
  if ( !v12 )
  {
    MonitorUIFullPath = 14;
    goto LABEL_26;
  }
  memset_0(v12, 0, 0x208u);
  MonitorUIFullPath = TLoad64BitDllsMgr::GetMonitorUIFullPath(v15, a2, v14);
  if ( !MonitorUIFullPath )
  {
    pActCtx.cbSize = 56;
    pActCtx.dwFlags = 8;
    pActCtx.lpSource = v14;
    *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
    pActCtx.lpResourceName = (LPCWSTR)123;
    *(_OWORD *)&pActCtx.lpApplicationName = 0;
    v17 = (__int64)CreateActCtxW(&pActCtx);
    *a6 = v17;
    if ( v17 == -1 )
    {
      v17 = -3;
      *a6 = -3;
    }
    if ( ActivateActCtx((HANDLE)v17, lpCookie) )
      *a8 = 1;
    else
      MonitorUIFullPath = GetLastError();
  }
  operator delete(v14);
  if ( MonitorUIFullPath )
    goto LABEL_26;
  LibraryW = LoadLibraryW(a2);
  *a5 = LibraryW;
  if ( !LibraryW )
  {
    v25 = 117;
    v26 = 4;
    MonitorUIFullPath = GetLastError();
    v29 = 4;
    v27 = 0;
    v28 = MonitorUIFullPath;
    v30 = 0;
    if ( a2 )
    {
      v22 = a2;
      do
        ++v8;
      while ( a2[v8] );
      v23 = 2 * v8 + 2;
    }
    else
    {
      v23 = 4;
      v22 = L"-";
    }
    v24 = 1;
    SplLogEvent2(&LOAD_PLUGIN_FAILED_EVENT, (struct SplLogType *)&v22, &v28, &v25, 0);
LABEL_23:
    if ( !MonitorUIFullPath )
      return MonitorUIFullPath;
LABEL_26:
    TLoad64BitDllsMgr::ReleaseMonitorActivationContext(v13, a5, a6, *lpCookie, *a8);
    return MonitorUIFullPath;
  }
  ProcAddress = GetProcAddress(LibraryW, "InitializePrintMonitorUI");
  if ( !ProcAddress || (v20 = (_QWORD *)ProcAddress()) == 0 )
  {
    MonitorUIFullPath = GetLastError();
    goto LABEL_23;
  }
  if ( (unsigned int)v9 < 2 )
  {
    v22 = (const wchar_t *)v20[2];
    v23 = v20[3];
    *a4 = (&v22)[v9];
  }
  else if ( (_DWORD)v9 == 2 )
  {
    *a4 = v20[1];
  }
  return MonitorUIFullPath;
}

```

## disassembly

```asm
0x140007548  push    rbp
0x14000754a  push    rbx
0x14000754b  push    rsi
0x14000754c  push    rdi
0x14000754d  push    r12
0x14000754f  push    r13
0x140007551  push    r14
0x140007553  push    r15
0x140007555  lea     rbp, [rsp-7]
0x14000755a  sub     rsp, 0B8h
0x140007561  mov     rax, [rbp+3Fh+arg_38]
0x140007568  xor     ebx, ebx
0x14000756a  mov     r13, [rbp+3Fh+arg_28]
0x14000756e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007572  mov     ecx, 208h; unsigned __int64
0x140007577  movsxd  r14, r8d
0x14000757a  mov     r12, r9
0x14000757d  mov     rsi, rdx
0x140007580  mov     [rax], ebx
0x140007582  mov     rax, [rbp+3Fh+lpCookie]
0x140007586  mov     [r13+0], rdi
0x14000758a  mov     [rax], rbx
0x14000758d  mov     rax, [rbp+3Fh+arg_20]
0x140007591  mov     [rax], rbx
0x140007594  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140007599  mov     r15, rax
0x14000759c  test    rax, rax
0x14000759f  jz      loc_14000774D
0x1400075a5  xor     edx, edx; Val
0x1400075a7  mov     r8d, 208h; Size
0x1400075ad  mov     rcx, rax; void *
0x1400075b0  call    memset_0
0x1400075b5  mov     r8, r15; unsigned __int16 *
0x1400075b8  mov     rdx, rsi; unsigned __int16 *
0x1400075bb  call    ?GetMonitorUIFullPath@TLoad64BitDllsMgr@@IEBAKPEBGPEAG@Z; TLoad64BitDllsMgr::GetMonitorUIFullPath(ushort const *,ushort *)
0x1400075c0  mov     ebx, eax
0x1400075c2  test    eax, eax
0x1400075c4  jnz     short loc_140007633
0x1400075c6  xorps   xmm0, xmm0
0x1400075c9  mov     [rbp+3Fh+pActCtx.cbSize], 38h ; '8'
0x1400075d0  xorps   xmm1, xmm1
0x1400075d3  mov     [rbp+3Fh+pActCtx.dwFlags], 8
0x1400075da  lea     rcx, [rbp+3Fh+pActCtx]; pActCtx
0x1400075de  mov     [rbp+3Fh+pActCtx.lpSource], r15
0x1400075e2  movdqu  xmmword ptr [rbp+3Fh+pActCtx.wProcessorArchitecture], xmm0
0x1400075e7  mov     [rbp+3Fh+pActCtx.lpResourceName], 7Bh ; '{'
0x1400075ef  movdqu  xmmword ptr [rbp+3Fh+pActCtx.lpApplicationName], xmm1
0x1400075f4  call    cs:__imp_CreateActCtxW
0x1400075fa  mov     [r13+0], rax
0x1400075fe  cmp     rax, rdi
0x140007601  jnz     short loc_14000760B
0x140007603  lea     rax, [rdi-2]
0x140007607  mov     [r13+0], rax
0x14000760b  mov     rdx, [rbp+3Fh+lpCookie]; lpCookie
0x14000760f  mov     rcx, rax; hActCtx
0x140007612  call    cs:__imp_ActivateActCtx
0x140007618  test    eax, eax
0x14000761a  jnz     short loc_140007626
0x14000761c  call    cs:__imp_GetLastError
0x140007622  mov     ebx, eax
0x140007624  jmp     short loc_140007633
0x140007626  mov     rax, [rbp+3Fh+arg_38]
0x14000762d  mov     dword ptr [rax], 1
0x140007633  mov     rcx, r15; Block
0x140007636  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000763b  xor     r15d, r15d
0x14000763e  test    ebx, ebx
0x140007640  jnz     loc_140007752
0x140007646  mov     rcx, rsi; lpLibFileName
0x140007649  call    cs:__imp_LoadLibraryW
0x14000764f  mov     rcx, [rbp+3Fh+arg_20]
0x140007653  mov     [rcx], rax
0x140007656  test    rax, rax
0x140007659  jz      short loc_1400076C9
0x14000765b  lea     rdx, aInitializeprin; "InitializePrintMonitorUI"
0x140007662  mov     rcx, rax; hModule
0x140007665  call    cs:__imp_GetProcAddress
0x14000766b  test    rax, rax
0x14000766e  jz      short loc_1400076BF
0x140007670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007675  mov     r8, rax
0x140007678  test    rax, rax
0x14000767b  jz      short loc_1400076BF
0x14000767d  mov     edx, r14d
0x140007680  test    r14d, r14d
0x140007683  jz      short loc_1400076A0
0x140007685  sub     edx, 1
0x140007688  jz      short loc_1400076A0
0x14000768a  cmp     edx, 1
0x14000768d  jnz     loc_140007772
0x140007693  mov     rax, [rax+8]
0x140007697  mov     [r12], rax
0x14000769b  jmp     loc_140007772
0x1400076a0  mov     rax, [rax+10h]
0x1400076a4  mov     [rsp+0F0h+var_C0], rax
0x1400076a9  mov     rax, [r8+18h]
0x1400076ad  mov     [rbp+3Fh+var_B8], rax
0x1400076b1  mov     rcx, [rsp+r14*8+0F0h+var_C0]
0x1400076b6  mov     [r12], rcx
0x1400076ba  jmp     loc_140007772
0x1400076bf  call    cs:__imp_GetLastError
0x1400076c5  mov     ebx, eax
0x1400076c7  jmp     short loc_140007747
0x1400076c9  call    cs:__imp_GetLastError
0x1400076cf  mov     [rbp+3Fh+var_A8], 75h ; 'u'
0x1400076d6  mov     ecx, 4
0x1400076db  mov     [rbp+3Fh+var_A0], rcx
0x1400076df  mov     ebx, eax
0x1400076e1  mov     [rbp+3Fh+var_88], rcx
0x1400076e5  mov     [rbp+3Fh+var_98], r15d
0x1400076e9  mov     [rbp+3Fh+var_90], eax
0x1400076ec  mov     [rbp+3Fh+var_80], r15d
0x1400076f0  test    rsi, rsi
0x1400076f3  jz      short loc_140007712
0x1400076f5  mov     [rsp+0F0h+var_C0], rsi
0x1400076fa  inc     rdi
0x1400076fd  cmp     [rsi+rdi*2], r15w
0x140007702  jnz     short loc_1400076FA
0x140007704  lea     rax, ds:2[rdi*2]
0x14000770c  mov     [rbp+3Fh+var_B8], rax
0x140007710  jmp     short loc_140007722
0x140007712  lea     rax, asc_14001A8D8; "-"
0x140007719  mov     [rbp+3Fh+var_B8], rcx
0x14000771d  mov     [rsp+0F0h+var_C0], rax
0x140007722  lea     r9, [rbp+3Fh+var_A8]
0x140007726  mov     [rbp+3Fh+var_B0], 1
0x14000772d  lea     r8, [rbp+3Fh+var_90]
0x140007731  mov     qword ptr [rsp+0F0h+var_D0], r15
0x140007736  lea     rdx, [rsp+0F0h+var_C0]; struct SplLogType *
0x14000773b  lea     rcx, LOAD_PLUGIN_FAILED_EVENT; struct _EVENT_DESCRIPTOR *
0x140007742  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x140007747  test    ebx, ebx
0x140007749  jz      short loc_140007772
0x14000774b  jmp     short loc_140007752
0x14000774d  mov     ebx, 0Eh
0x140007752  mov     rax, [rbp+3Fh+arg_38]
0x140007759  mov     r8, r13; void *
0x14000775c  mov     rdx, [rbp+3Fh+arg_20]; void *
0x140007760  mov     eax, [rax]
0x140007762  mov     [rsp+0F0h+var_D0], eax; int
0x140007766  mov     rax, [rbp+3Fh+lpCookie]
0x14000776a  mov     r9, [rax]; unsigned __int64
0x14000776d  call    ?ReleaseMonitorActivationContext@TLoad64BitDllsMgr@@IEBAXPEAX0_KH@Z; TLoad64BitDllsMgr::ReleaseMonitorActivationContext(void *,void *,unsigned __int64,int)
0x140007772  mov     eax, ebx
0x140007774  add     rsp, 0B8h
0x14000777b  pop     r15
0x14000777d  pop     r14
0x14000777f  pop     r13
0x140007781  pop     r12
0x140007783  pop     rdi
0x140007784  pop     rsi
0x140007785  pop     rbx
0x140007786  pop     rbp
0x140007787  retn
```
