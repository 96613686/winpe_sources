# SxsCreateAssemblyIdentity

- ea: `0x180042868`
- end: `0x180042a8b`
- name: `SxsCreateAssemblyIdentity`
- size: `547`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020f74`
- `0x18002cc78`
- `0x180041f10`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180042868`
- `0x180042ce0`
- `0x18005d2e4`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!qsort` at `0x18004294e`
- `ntdll!qsort` at `0x18004294e`
- `ntdll!RtlPopFrame` at `0x1800429bf`
- `ntdll!RtlPopFrame` at `0x1800429bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800429f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042a10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800429f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042a10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042911`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042a44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042a44`

## pseudocode

```c
__int64 __fastcall SxsCreateAssemblyIdentity(__int64 a1, int a2, _QWORD *a3)
{
  char *v5; // rax
  const char *v6; // rcx
  _DWORD *v7; // rdi
  char *v8; // rbx
  unsigned int v9; // ecx
  unsigned int v10; // ebx
  DWORD v12; // ecx
  DWORD LastError; // eax
  int v14; // [rsp+20h] [rbp-50h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h]
  int v17; // [rsp+48h] [rbp-28h]
  int *v18; // [rsp+50h] [rbp-20h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071030;
  v16 = 544438355;
  v18 = &v14;
  v14 = 0;
  Frame.Previous = 0;
  v17 = 1164;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( a3 )
    *a3 = 0;
  if ( (unsigned int)(a2 - 1) > 2 )
  {
    v12 = 87;
    goto LABEL_11;
  }
  if ( !is_mul_ok(8u, 8u) )
  {
    v12 = 534;
LABEL_11:
    SetLastError(v12);
    goto LABEL_8;
  }
  v5 = (char *)HeapAlloc(g_hHeap, (8 * (unsigned __int128)8uLL) >> 64, 0x78u);
  v7 = v5;
  if ( v5 )
  {
    v8 = v5 + 56;
    *(_OWORD *)(v5 + 56) = 0;
    *(_OWORD *)(v5 + 72) = 0;
    *(_OWORD *)(v5 + 88) = 0;
    *(_OWORD *)(v5 + 104) = 0;
    qsort(v5 + 56, 0, 8u, SxspCompareInternalAttributesForQsort);
    v7[5] = 8;
    v7[4] = 0;
    *((_QWORD *)v7 + 5) = v8;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *v7 = 0;
    v7[1] = 4;
    v7[2] = a2;
    v7[8] = 1;
    SetLastError(0);
    if ( SxspEnsureAssemblyIdentityHashIsUpToDate(v9, (const struct _ASSEMBLY_IDENTITY *)v7) )
    {
      *a3 = v7;
      v14 = 1;
    }
    else
    {
      *v18 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007CEA0);
      HeapFree(g_hHeap, 0, v7);
    }
  }
  else
  {
    FusionpTraceAllocFailure(v6);
    SetLastError(0xEu);
    *v18 = 0;
  }
LABEL_8:
  v10 = v14;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v18 )
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
  return v10;
}

```

## disassembly

```asm
0x180042868  mov     [rsp-28h+arg_0], rbx
0x18004286d  mov     [rsp-28h+arg_8], rsi
0x180042872  push    rbp
0x180042873  push    rdi
0x180042874  push    r12
0x180042876  push    r14
0x180042878  push    r15
0x18004287a  mov     rbp, rsp
0x18004287d  sub     rsp, 70h
0x180042881  mov     rax, cs:__security_cookie
0x180042888  xor     rax, rsp
0x18004288b  mov     [rbp+var_10], rax
0x18004288f  lea     rax, qword_180071030
0x180042896  mov     [rbp+Frame.Flags], 1
0x18004289d  mov     [rbp+Frame.Context], rax
0x1800428a1  lea     rcx, [rbp+Frame]; this
0x1800428a5  lea     rax, [rbp+var_50]
0x1800428a9  mov     [rbp+var_30], 20737853h
0x1800428b1  xor     r15d, r15d
0x1800428b4  mov     [rbp+var_20], rax
0x1800428b8  mov     rsi, r8
0x1800428bb  mov     [rbp+var_50], r15d
0x1800428bf  mov     r14d, edx
0x1800428c2  mov     [rbp+Frame.Previous], r15
0x1800428c6  mov     [rbp+var_28], 48Ch
0x1800428cd  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800428d2  test    rsi, rsi
0x1800428d5  jz      short loc_1800428DA
0x1800428d7  mov     [rsi], r15
0x1800428da  lea     eax, [r14-1]
0x1800428de  cmp     eax, 2
0x1800428e1  ja      loc_180042A55
0x1800428e7  mov     r12d, 8
0x1800428ed  mov     eax, r12d
0x1800428f0  mul     r12
0x1800428f3  test    rdx, rdx
0x1800428f6  jnz     loc_1800429F3
0x1800428fc  lea     r8, [rax+38h]; dwBytes
0x180042900  cmp     r8, 38h ; '8'
0x180042904  jb      loc_1800429F3
0x18004290a  mov     rcx, cs:g_hHeap; hHeap
0x180042911  call    cs:__imp_HeapAlloc
0x180042918  nop     dword ptr [rax+rax+00h]
0x18004291d  mov     rdi, rax
0x180042920  test    rax, rax
0x180042923  jz      loc_180042A06
0x180042929  lea     rbx, [rax+38h]
0x18004292d  xorps   xmm0, xmm0
0x180042930  movups  xmmword ptr [rbx], xmm0
0x180042933  lea     r9, ?SxspCompareInternalAttributesForQsort@@YAHPEBX0@Z; CompareFunction
0x18004293a  mov     r8d, r12d; SizeOfElements
0x18004293d  movups  xmmword ptr [rbx+10h], xmm0
0x180042941  xor     edx, edx; NumOfElements
0x180042943  mov     rcx, rbx; Base
0x180042946  movups  xmmword ptr [rbx+20h], xmm0
0x18004294a  movups  xmmword ptr [rbx+30h], xmm0
0x18004294e  call    cs:__imp_qsort
0x180042955  nop     dword ptr [rax+rax+00h]
0x18004295a  xor     ecx, ecx; dwErrCode
0x18004295c  mov     [rdi+14h], r12d
0x180042960  mov     [rdi+10h], r15d
0x180042964  mov     [rdi+28h], rbx
0x180042968  mov     [rdi+18h], r15
0x18004296c  mov     [rdi+30h], r15
0x180042970  mov     [rdi], r15d
0x180042973  mov     dword ptr [rdi+4], 4
0x18004297a  mov     [rdi+8], r14d
0x18004297e  mov     dword ptr [rdi+20h], 1
0x180042985  call    cs:__imp_SetLastError
0x18004298c  nop     dword ptr [rax+rax+00h]
0x180042991  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x180042994  call    ?SxspEnsureAssemblyIdentityHashIsUpToDate@@YAHKPEBU_ASSEMBLY_IDENTITY@@@Z; SxspEnsureAssemblyIdentityHashIsUpToDate(ulong,_ASSEMBLY_IDENTITY const *)
0x180042999  test    eax, eax
0x18004299b  jz      loc_180042A25
0x1800429a1  mov     [rsi], rdi
0x1800429a4  mov     [rbp+var_50], 1
0x1800429ab  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x1800429b2  mov     ebx, [rbp+var_50]
0x1800429b5  jnz     loc_180042A5C
0x1800429bb  lea     rcx, [rbp+Frame]; Frame
0x1800429bf  call    cs:__imp_RtlPopFrame
0x1800429c6  nop     dword ptr [rax+rax+00h]
0x1800429cb  mov     eax, ebx
0x1800429cd  mov     rcx, [rbp+var_10]
0x1800429d1  xor     rcx, rsp; StackCookie
0x1800429d4  call    __security_check_cookie
0x1800429d9  lea     r11, [rsp+70h+var_s0]
0x1800429de  mov     rbx, [r11+30h]
0x1800429e2  mov     rsi, [r11+38h]
0x1800429e6  mov     rsp, r11
0x1800429e9  pop     r15
0x1800429eb  pop     r14
0x1800429ed  pop     r12
0x1800429ef  pop     rdi
0x1800429f0  pop     rbp
0x1800429f1  retn
0x1800429f3  mov     ecx, 216h; dwErrCode
0x1800429f8  call    cs:__imp_SetLastError
0x1800429ff  nop     dword ptr [rax+rax+00h]
0x180042a04  jmp     short loc_1800429AB
0x180042a06  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x180042a0b  mov     ecx, 0Eh; dwErrCode
0x180042a10  call    cs:__imp_SetLastError
0x180042a17  nop     dword ptr [rax+rax+00h]
0x180042a1c  mov     rax, [rbp+var_20]
0x180042a20  mov     [rax], r15d
0x180042a23  jmp     short loc_1800429AB
0x180042a25  mov     rax, [rbp+var_20]
0x180042a29  lea     rcx, off_18007CEA0; struct _CALL_SITE_INFO *
0x180042a30  mov     [rax], r15d
0x180042a33  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180042a38  mov     rcx, cs:g_hHeap; hHeap
0x180042a3f  mov     r8, rdi; lpMem
0x180042a42  xor     edx, edx; dwFlags
0x180042a44  call    cs:__imp_HeapFree
0x180042a4b  nop     dword ptr [rax+rax+00h]
0x180042a50  jmp     loc_1800429AB
0x180042a55  mov     ecx, 57h ; 'W'
0x180042a5a  jmp     short loc_1800429F8
0x180042a5c  mov     rax, [rbp+var_20]
0x180042a60  cmp     [rax], r15d
0x180042a63  jz      short loc_180042A71
0x180042a65  xor     ecx, ecx; char *
0x180042a67  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180042a6c  jmp     loc_1800429BB
0x180042a71  call    cs:__imp_GetLastError
0x180042a78  nop     dword ptr [rax+rax+00h]
0x180042a7d  mov     ecx, eax; unsigned int
0x180042a7f  xor     edx, edx; Format
0x180042a81  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180042a86  jmp     loc_1800429BB
```
