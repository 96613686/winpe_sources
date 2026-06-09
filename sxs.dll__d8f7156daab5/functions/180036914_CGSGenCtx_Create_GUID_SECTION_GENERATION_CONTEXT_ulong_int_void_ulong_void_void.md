# CGSGenCtx::Create(_GUID_SECTION_GENERATION_CONTEXT * *,ulong,int (*)(void *,ulong,void *),void *)

- ea: `0x180036914`
- end: `0x180036aac`
- name: `?Create@CGSGenCtx@@SAHPEAPEAU_GUID_SECTION_GENERATION_CONTEXT@@KP6AHPEAXK1@Z1@Z`
- size: `408`
- prototype: `__int64 __fastcall(struct _GUID_SECTION_GENERATION_CONTEXT **, unsigned int, int (*)(void *, unsigned int, void *), void *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180002a70`
- `0x1800345b0`
- `0x1800358d0`
- `0x180036dc0`

## callees

- `0x18000df40`
- `0x180029754`
- `0x180036914`
- `0x18005d2b0`
- `0x18005d2e4`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180036a1d`
- `ntdll!RtlPopFrame` at `0x180036a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036a5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036a5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003699d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003699d`

## pseudocode

```c
__int64 __fastcall CGSGenCtx::Create(
        struct _GUID_SECTION_GENERATION_CONTEXT **a1,
        __int64 a2,
        int (*a3)(void *, unsigned int, void *),
        void *a4)
{
  unsigned int v5; // ebx
  const char *v8; // rcx
  _DWORD *v9; // rax
  const char *v10; // rcx
  _DWORD *v11; // rdi
  __int64 v12; // r14
  char *v13; // rsi
  DWORD v15; // ecx
  DWORD LastError; // eax
  int v17; // [rsp+20h] [rbp-48h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-28h]
  int v20; // [rsp+48h] [rbp-20h]
  int *v21; // [rsp+50h] [rbp-18h]

  v19 = 544438355;
  v17 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006F970;
  Frame.Previous = 0;
  v5 = 1;
  v20 = 29;
  Frame.Flags = 1;
  v21 = &v17;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( !a1 )
  {
    v20 = 36;
LABEL_10:
    FusionpTraceParameterCheck(v8);
    v15 = 87;
LABEL_11:
    SetLastError(v15);
    v5 = 0;
    *v21 = 0;
    goto LABEL_7;
  }
  *a1 = 0;
  if ( !a3 )
  {
    v20 = 37;
    goto LABEL_10;
  }
  v9 = HeapAlloc(g_hHeap, 0, 0x158u);
  v11 = v9;
  if ( !v9 )
  {
    FusionpTraceAllocFailure(v10);
    v15 = 14;
    goto LABEL_11;
  }
  v12 = 7;
  v13 = (char *)(v9 + 8);
  v9[4] = 7;
  *((_QWORD *)v9 + 3) = v9 + 8;
  do
  {
    CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::CBucketChain(v13);
    v13 += 40;
    --v12;
  }
  while ( v12 );
  *((_QWORD *)v11 + 39) = 0;
  *((_QWORD *)v11 + 40) = 0;
  v11[84] = 0;
  *(_QWORD *)v11 = a3;
  *((_QWORD *)v11 + 1) = a4;
  v11[85] = 1;
  *a1 = (struct _GUID_SECTION_GENERATION_CONTEXT *)v11;
  SetLastError(0);
  *v21 = 1;
LABEL_7:
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v5 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v5;
}

```

## disassembly

```asm
0x180036914  push    rbp
0x180036916  push    rbx
0x180036917  push    rsi
0x180036918  push    rdi
0x180036919  push    r12
0x18003691b  push    r13
0x18003691d  push    r14
0x18003691f  push    r15
0x180036921  mov     rbp, rsp
0x180036924  sub     rsp, 68h
0x180036928  mov     rax, cs:__security_cookie
0x18003692f  xor     rax, rsp
0x180036932  mov     [rbp+var_10], rax
0x180036936  xor     esi, esi
0x180036938  mov     [rbp+var_28], 20737853h
0x180036940  lea     rax, qword_18006F970
0x180036947  mov     [rbp+var_48], esi
0x18003694a  mov     [rbp+Frame.Context], rax
0x18003694e  mov     r15, rcx
0x180036951  lea     rax, [rbp+var_48]
0x180036955  mov     [rbp+Frame.Previous], rsi
0x180036959  lea     ebx, [rsi+1]
0x18003695c  mov     [rbp+var_20], 1Dh
0x180036963  lea     rcx, [rbp+Frame]; this
0x180036967  mov     [rbp+Frame.Flags], ebx
0x18003696a  mov     r13, r9
0x18003696d  mov     [rbp+var_18], rax
0x180036971  mov     r12, r8
0x180036974  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180036979  test    r15, r15
0x18003697c  jz      loc_180036A49
0x180036982  mov     [r15], rsi
0x180036985  test    r12, r12
0x180036988  jz      loc_180036A7C
0x18003698e  mov     rcx, cs:g_hHeap; hHeap
0x180036995  xor     edx, edx; dwFlags
0x180036997  mov     r8d, 158h; dwBytes
0x18003699d  call    cs:__imp_HeapAlloc
0x1800369a4  nop     dword ptr [rax+rax+00h]
0x1800369a9  mov     rdi, rax
0x1800369ac  test    rax, rax
0x1800369af  jz      loc_180036A70
0x1800369b5  lea     r14d, [rsi+7]
0x1800369b9  lea     rsi, [rax+20h]
0x1800369bd  mov     [rax+10h], r14d
0x1800369c1  mov     [rax+18h], rsi
0x1800369c5  mov     rcx, rsi
0x1800369c8  call    ??0CBucketChain@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAA@XZ; CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucketChain::CBucketChain(void)
0x1800369cd  add     rsi, 28h ; '('
0x1800369d1  sub     r14, rbx
0x1800369d4  jnz     short loc_1800369C5
0x1800369d6  xor     esi, esi
0x1800369d8  xor     ecx, ecx; dwErrCode
0x1800369da  mov     [rdi+138h], rsi
0x1800369e1  mov     [rdi+140h], rsi
0x1800369e8  mov     [rdi+150h], esi
0x1800369ee  mov     [rdi], r12
0x1800369f1  mov     [rdi+8], r13
0x1800369f5  mov     [rdi+154h], ebx
0x1800369fb  mov     [r15], rdi
0x1800369fe  call    cs:__imp_SetLastError
0x180036a05  nop     dword ptr [rax+rax+00h]
0x180036a0a  mov     rax, [rbp+var_18]
0x180036a0e  mov     [rax], ebx
0x180036a10  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x180036a17  jnz     short loc_180036A85
0x180036a19  lea     rcx, [rbp+Frame]; Frame
0x180036a1d  call    cs:__imp_RtlPopFrame
0x180036a24  nop     dword ptr [rax+rax+00h]
0x180036a29  mov     eax, ebx
0x180036a2b  mov     rcx, [rbp+var_10]
0x180036a2f  xor     rcx, rsp; StackCookie
0x180036a32  call    __security_check_cookie
0x180036a37  add     rsp, 68h
0x180036a3b  pop     r15
0x180036a3d  pop     r14
0x180036a3f  pop     r13
0x180036a41  pop     r12
0x180036a43  pop     rdi
0x180036a44  pop     rsi
0x180036a45  pop     rbx
0x180036a46  pop     rbp
0x180036a47  retn
0x180036a49  mov     [rbp+var_20], 24h ; '$'
0x180036a50  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180036a55  mov     ecx, 57h ; 'W'; dwErrCode
0x180036a5a  call    cs:__imp_SetLastError
0x180036a61  nop     dword ptr [rax+rax+00h]
0x180036a66  mov     rax, [rbp+var_18]
0x180036a6a  mov     ebx, esi
0x180036a6c  mov     [rax], esi
0x180036a6e  jmp     short loc_180036A10
0x180036a70  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x180036a75  mov     ecx, 0Eh
0x180036a7a  jmp     short loc_180036A5A
0x180036a7c  mov     [rbp+var_20], 25h ; '%'
0x180036a83  jmp     short loc_180036A50
0x180036a85  test    ebx, ebx
0x180036a87  jz      short loc_180036A92
0x180036a89  xor     ecx, ecx; char *
0x180036a8b  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180036a90  jmp     short loc_180036A19
0x180036a92  call    cs:__imp_GetLastError
0x180036a99  nop     dword ptr [rax+rax+00h]
0x180036a9e  mov     ecx, eax; unsigned int
0x180036aa0  xor     edx, edx; Format
0x180036aa2  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180036aa7  jmp     loc_180036A19
```
