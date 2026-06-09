# CreateAssemblyCache

- ea: `0x1800597f0`
- end: `0x180059978`
- name: `CreateAssemblyCache`
- size: `392`
- prototype: `HRESULT __stdcall(IAssemblyCache **ppAsmCache, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18002e98c`
- `0x18002ff90`
- `0x1800597f0`
- `0x18005bf78`
- `0x18005bfc0`
- `0x18005c5e4`
- `0x18005cc58`
- `0x18005d2b0`
- `0x18005d6e4`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800598bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800598bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059890`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059890`

## pseudocode

```c
HRESULT __stdcall CreateAssemblyCache(IAssemblyCache **ppAsmCache, DWORD dwReserved)
{
  const char *v3; // rcx
  CAssemblyCache *v4; // rax
  int v5; // eax
  int v6; // ebx
  HRESULT v7; // ebx
  CAssemblyCache *v9; // [rsp+20h] [rbp-50h] BYREF
  char v10; // [rsp+28h] [rbp-48h]
  HRESULT v11; // [rsp+30h] [rbp-40h] BYREF
  int v12; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h]
  __int64 *v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+58h] [rbp-18h]
  HRESULT *v17; // [rsp+60h] [rbp-10h]

  v11 = 0;
  v14 = &qword_180072D80;
  v12 = 1;
  v17 = &v11;
  v13 = 0;
  v15 = 544438355;
  v16 = 63;
  CFrame::BaseEnter((CFrame *)&v12);
  v9 = 0;
  v10 = 0;
  if ( ppAsmCache )
  {
    *ppAsmCache = 0;
    SxspDeletePatchedComponentsData();
    SetLastError(0);
    v4 = (CAssemblyCache *)HeapAlloc(g_hHeap, 0, 0x10u);
    if ( v4 && (v9 = CAssemblyCache::CAssemblyCache(v4)) != 0 )
    {
      v10 = 1;
      SetLastError(0);
      v5 = (**(__int64 (__fastcall ***)(CAssemblyCache *, GUID *, IAssemblyCache **))v9)(
             v9,
             &IID_IAssemblyCache,
             ppAsmCache);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v9 = 0;
        v10 = 0;
        v11 = 0;
      }
      else
      {
        FusionpTraceCOMFailure(v5, byte_18008517D);
        CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&v12, v6);
      }
    }
    else
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v12);
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180072D60);
    }
  }
  else
  {
    v16 = 69;
    FusionpTraceParameterCheck(v3);
    *v17 = -2147024809;
  }
  v7 = v11;
  CSmartPtr<CAssemblyCache,CSmartPtrBaseTypeHelper<CAssemblyCache>>::~CSmartPtr<CAssemblyCache,CSmartPtrBaseTypeHelper<CAssemblyCache>>(&v9);
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v12);
  return v7;
}

```

## disassembly

```asm
0x1800597f0  mov     [rsp-8+arg_8], rbx
0x1800597f5  mov     [rsp-8+arg_10], rdi
0x1800597fa  push    rbp
0x1800597fb  mov     rbp, rsp
0x1800597fe  sub     rsp, 70h
0x180059802  mov     rax, cs:__security_cookie
0x180059809  xor     rax, rsp
0x18005980c  mov     [rbp+var_8], rax
0x180059810  lea     rax, qword_180072D80
0x180059817  mov     [rbp+var_40], 0
0x18005981e  mov     [rbp+var_28], rax
0x180059822  mov     rdi, rcx
0x180059825  lea     rax, [rbp+var_40]
0x180059829  mov     [rbp+var_38], 1
0x180059830  lea     rcx, [rbp+var_38]; this
0x180059834  mov     [rbp+var_10], rax
0x180059838  mov     [rbp+var_30], 0
0x180059840  mov     [rbp+var_20], 20737853h
0x180059848  mov     [rbp+var_18], 3Fh ; '?'
0x18005984f  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180059854  mov     [rbp+var_50], 0
0x18005985c  mov     [rbp+var_48], 0
0x180059860  test    rdi, rdi
0x180059863  jz      loc_18005992C
0x180059869  mov     qword ptr [rdi], 0
0x180059870  call    ?SxspDeletePatchedComponentsData@@YAXXZ; SxspDeletePatchedComponentsData(void)
0x180059875  xor     ecx, ecx; dwErrCode
0x180059877  call    cs:__imp_SetLastError
0x18005987e  nop     dword ptr [rax+rax+00h]
0x180059883  mov     rcx, cs:g_hHeap; hHeap
0x18005988a  xor     edx, edx; dwFlags
0x18005988c  lea     r8d, [rdx+10h]; dwBytes
0x180059890  call    cs:__imp_HeapAlloc
0x180059897  nop     dword ptr [rax+rax+00h]
0x18005989c  test    rax, rax
0x18005989f  jz      short loc_180059915
0x1800598a1  mov     rcx, rax; this
0x1800598a4  call    ??0CAssemblyCache@@QEAA@XZ; CAssemblyCache::CAssemblyCache(void)
0x1800598a9  mov     [rbp+var_50], rax
0x1800598ad  mov     rbx, rax
0x1800598b0  test    rax, rax
0x1800598b3  jz      short loc_180059915
0x1800598b5  mov     [rbp+var_48], 1
0x1800598b9  xor     ecx, ecx; dwErrCode
0x1800598bb  call    cs:__imp_SetLastError
0x1800598c2  nop     dword ptr [rax+rax+00h]
0x1800598c7  mov     rcx, [rbx]
0x1800598ca  lea     rdx, IID_IAssemblyCache
0x1800598d1  mov     r8, rdi
0x1800598d4  mov     rax, [rcx]
0x1800598d7  mov     rcx, rbx
0x1800598da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598df  mov     ebx, eax
0x1800598e1  test    eax, eax
0x1800598e3  jns     short loc_180059900
0x1800598e5  lea     rdx, byte_18008517D; char *
0x1800598ec  mov     ecx, eax; int
0x1800598ee  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x1800598f3  mov     edx, ebx; int
0x1800598f5  lea     rcx, [rbp+var_38]; this
0x1800598f9  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x1800598fe  jmp     short loc_180059942
0x180059900  mov     [rbp+var_50], 0
0x180059908  mov     [rbp+var_48], 0
0x18005990c  mov     [rbp+var_40], 0
0x180059913  jmp     short loc_180059942
0x180059915  lea     rcx, [rbp+var_38]; this
0x180059919  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18005991e  lea     rcx, off_180072D60; struct _CALL_SITE_INFO *
0x180059925  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005992a  jmp     short loc_180059942
0x18005992c  mov     [rbp+var_18], 45h ; 'E'
0x180059933  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180059938  mov     rax, [rbp+var_10]
0x18005993c  mov     dword ptr [rax], 80070057h
0x180059942  mov     ebx, [rbp+var_40]
0x180059945  lea     rcx, [rbp+var_50]
0x180059949  call    ??1?$CSmartPtr@VCAssemblyCache@@V?$CSmartPtrBaseTypeHelper@VCAssemblyCache@@@@@@QEAA@XZ; CSmartPtr<CAssemblyCache,CSmartPtrBaseTypeHelper<CAssemblyCache>>::~CSmartPtr<CAssemblyCache,CSmartPtrBaseTypeHelper<CAssemblyCache>>(void)
0x18005994e  lea     rcx, [rbp+var_38]; this
0x180059952  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180059957  mov     eax, ebx
0x180059959  mov     rcx, [rbp+var_8]
0x18005995d  xor     rcx, rsp; StackCookie
0x180059960  call    __security_check_cookie
0x180059965  lea     r11, [rsp+70h+var_s0]
0x18005996a  mov     rbx, [r11+18h]
0x18005996e  mov     rdi, [r11+20h]
0x180059972  mov     rsp, r11
0x180059975  pop     rbp
0x180059976  retn
```
