# GdiProcessCallout

- ea: `0x140013160`
- end: `0x14001355d`
- name: `GdiProcessCallout`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140011f04`
- `0x140013160`
- `0x1400147f8`
- `0x14001520c`
- `0x14003b020`
- `0x14007b930`
- `0x1401c11e0`
- `0x1402389c0`
- `0x1402bb218`
- `0x1402bb310`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1400131d1`
- `ntoskrnl!PsGetProcessPeb` at `0x1400131d1`
- `ntoskrnl!ZwClose` at `0x140013329`
- `ntoskrnl!ZwClose` at `0x140013329`
- `ntoskrnl!PsGetProcessId` at `0x14001336f`
- `ntoskrnl!PsGetProcessId` at `0x140013431`
- `ntoskrnl!PsGetProcessId` at `0x14001336f`
- `ntoskrnl!PsGetProcessId` at `0x140013431`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400132a4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400132a4`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400131a6`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400131a6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400134d6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400134d6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400134c5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400134c5`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400133f5`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400133f5`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140013535`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140013535`
- `ntoskrnl!ZwMapViewOfSection` at `0x140013306`
- `ntoskrnl!ZwMapViewOfSection` at `0x140013306`
- `WIN32K!DxDdProcessCallout` at `0x14001322c`
- `WIN32K!DxDdProcessCallout` at `0x1400133cb`
- `WIN32K!DxDdProcessCallout` at `0x1400134a4`
- `WIN32K!DxDdProcessCallout` at `0x14001322c`
- `WIN32K!DxDdProcessCallout` at `0x1400133cb`
- `WIN32K!DxDdProcessCallout` at `0x1400134a4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001339d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140013440`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14001339d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140013440`
- `WIN32K!W32GetSessionState` at `0x140013264`
- `WIN32K!W32GetSessionState` at `0x14001337e`
- `WIN32K!W32GetSessionState` at `0x140013264`
- `WIN32K!W32GetSessionState` at `0x14001337e`

## pseudocode

```c
__int64 __fastcall GdiProcessCallout(__int64 a1, char a2)
{
  __int64 ProcessPeb; // rax
  __int64 v5; // r15
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 SessionState; // rax
  NTSTATUS v9; // ebx
  int v11; // eax
  int v12; // r15d
  HANDLE ProcessId; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 (*v18)(void); // rax
  int v19; // eax
  BOOLEAN i; // dl
  HANDLE v21; // rax
  HANDLE v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  void (__fastcall *v25)(HANDLE); // rax
  PVOID v26; // rax
  _QWORD *v27; // rbx
  void *v28; // rcx
  _QWORD *v29; // rbx
  void *v30; // rcx
  void *v31; // rcx
  PVOID BaseAddress; // [rsp+80h] [rbp+8h] BYREF
  HANDLE SectionHandle; // [rsp+90h] [rbp+18h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp+20h] BYREF

  if ( !a1 )
    return 3221225495LL;
  if ( a2 )
  {
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(a1 + 88),
      GDIEngUserMemAllocNodeCompare,
      GDIEngUserMemAllocNodeAlloc,
      rimUserMemAllocNodeFree,
      0);
    *(_QWORD *)(a1 + 200) = a1 + 192;
    *(_QWORD *)(a1 + 192) = a1 + 192;
    *(_QWORD *)(a1 + 216) = a1 + 208;
    *(_QWORD *)(a1 + 208) = a1 + 208;
    ProcessPeb = PsGetProcessPeb(*(_QWORD *)a1);
    v5 = ProcessPeb;
    if ( ProcessPeb
      && (RtlWriteULongToUser(ProcessPeb + 264, *(unsigned int *)(a1 + 280)),
          RtlSetUserMemory((void *)(v5 + 320)),
          LOBYTE(v6) = a2,
          (int)DxDdProcessCallout(a1 + 248, v6) >= 0) )
    {
      BaseAddress = 0;
      ViewSize = 0;
      SectionHandle = 0;
      SessionState = W32GetSessionState(v7);
      if ( ObOpenObjectByPointer(
             *(PVOID *)(*(_QWORD *)(SessionState + 88) + 2272LL),
             0x200u,
             0,
             0xF001Fu,
             0,
             0,
             &SectionHandle) < 0 )
      {
        v9 = -1073741502;
      }
      else
      {
        v9 = ZwMapViewOfSection(
               SectionHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               &BaseAddress,
               0,
               0,
               0,
               &ViewSize,
               ViewUnmap,
               0,
               2u);
        if ( v9 >= 0 && (v21 = MmSecureVirtualMemory(BaseAddress, 0x1000u, 2u), (*(_QWORD *)(a1 + 240) = v21) != 0) )
          RtlWriteULong64ToUser(v5 + 248, BaseAddress);
        else
          v9 = -1073741502;
        ZwClose(SectionHandle);
      }
      if ( v9 < 0 )
        DxDdProcessCallout(a1 + 248, 0);
      return (unsigned int)v9;
    }
    else
    {
      return 3221225794LL;
    }
  }
  else
  {
    GdiUnmapGDIW32PIDLockedBitmaps();
    if ( (unsigned int)Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline() )
      v11 = GrepCloseCurrentProcessPreserveObjectReference();
    else
      v11 = GrepCloseCurrentProcess();
    v12 = v11;
    ProcessId = PsGetProcessId(*(PEPROCESS *)a1);
    v15 = W32GetSessionState(v14);
    COPM::DestroyProtectedOutputsOwnedByProcess(*(COPM **)(*(_QWORD *)(v15 + 88) + 3728LL), ProcessId);
    v18 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v17, v16) + 24) + 2432LL);
    if ( v18 )
      v19 = v18();
    else
      v19 = -1073741637;
    if ( v19 >= 0 )
    {
      v22 = PsGetProcessId(*(PEPROCESS *)a1);
      v25 = *(void (__fastcall **)(HANDLE))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v24, v23) + 24) + 2440LL);
      if ( v25 )
        v25(v22);
    }
    DxDdProcessCallout(a1 + 248, 0);
    for ( i = 1; ; i = 0 )
    {
      v26 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), i);
      if ( !v26 )
        break;
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), v26);
    }
    v27 = *(_QWORD **)(a1 + 192);
    if ( v27 )
    {
      while ( v27 != (_QWORD *)(a1 + 192) )
      {
        v28 = v27;
        v27 = (_QWORD *)*v27;
        GreDeleteFastMutex(v28);
      }
    }
    v29 = *(_QWORD **)(a1 + 208);
    if ( v29 )
    {
      while ( v29 != (_QWORD *)(a1 + 208) )
      {
        v30 = v29;
        v29 = (_QWORD *)*v29;
        GreDeleteFastMutex(v30);
      }
    }
    v31 = *(void **)(a1 + 240);
    if ( v31 )
    {
      MmUnsecureVirtualMemory(v31);
      *(_QWORD *)(a1 + 240) = 0;
    }
    return v12 == 0 ? 0xC0000121 : 0;
  }
}

```

## disassembly

```asm
0x140013160  mov     [rsp+arg_8], rbx
0x140013165  push    rsi
0x140013166  push    r14
0x140013168  push    r15
0x14001316a  sub     rsp, 60h
0x14001316e  mov     bl, dl
0x140013170  mov     rsi, rcx
0x140013173  test    rcx, rcx
0x140013176  jz      loc_14001346D
0x14001317c  test    dl, dl
0x14001317e  jz      loc_140013352
0x140013184  add     rcx, 58h ; 'X'; Table
0x140013188  mov     [rsp+78h+TableContext], 0; TableContext
0x140013191  lea     r9, rimUserMemAllocNodeFree; FreeRoutine
0x140013198  lea     r8, ?GDIEngUserMemAllocNodeAlloc@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x14001319f  lea     rdx, ?GDIEngUserMemAllocNodeCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1400131a6  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400131ad  nop     dword ptr [rax+rax+00h]
0x1400131b2  lea     rax, [rsi+0C0h]
0x1400131b9  mov     [rax+8], rax
0x1400131bd  mov     [rax], rax
0x1400131c0  lea     rax, [rsi+0D0h]
0x1400131c7  mov     [rax+8], rax
0x1400131cb  mov     [rax], rax
0x1400131ce  mov     rcx, [rsi]
0x1400131d1  call    cs:__imp_PsGetProcessPeb
0x1400131d8  nop     dword ptr [rax+rax+00h]
0x1400131dd  mov     r15, rax
0x1400131e0  test    rax, rax
0x1400131e3  jz      loc_14001341D
0x1400131e9  lea     rcx, [rax+108h]
0x1400131f0  mov     edx, [rsi+118h]
0x1400131f6  call    RtlWriteULongToUser
0x1400131fb  lea     rcx, [r15+140h]; void *
0x140013202  xor     edx, edx
0x140013204  mov     r8d, 0F0h
0x14001320a  call    RtlSetUserMemory
0x14001320f  jmp     short loc_14001321B
0x140013211  mov     eax, 0C0000142h
0x140013216  jmp     loc_14001333F
0x14001321b  lea     r14, [rsi+0F8h]
0x140013222  mov     [rsp+78h+var_28], r14
0x140013227  mov     dl, bl
0x140013229  mov     rcx, r14
0x14001322c  call    cs:__imp_DxDdProcessCallout
0x140013233  nop     dword ptr [rax+rax+00h]
0x140013238  test    eax, eax
0x14001323a  js      loc_14001341D
0x140013240  mov     [rsp+78h+BaseAddress], 0
0x14001324c  mov     [rsp+78h+ViewSize], 0
0x140013258  mov     [rsp+78h+SectionHandle], 0
0x140013264  call    cs:__imp_W32GetSessionState
0x14001326b  nop     dword ptr [rax+rax+00h]
0x140013270  mov     rcx, [rax+58h]
0x140013274  lea     rax, [rsp+78h+SectionHandle]
0x14001327c  mov     [rsp+78h+Handle], rax; Handle
0x140013281  mov     [rsp+78h+AccessMode], 0; AccessMode
0x140013286  mov     [rsp+78h+TableContext], 0; ObjectType
0x14001328f  mov     r9d, 0F001Fh; DesiredAccess
0x140013295  xor     r8d, r8d; PassedAccessState
0x140013298  mov     edx, 200h; HandleAttributes
0x14001329d  mov     rcx, [rcx+8E0h]; Object
0x1400132a4  call    cs:__imp_ObOpenObjectByPointer
0x1400132ab  nop     dword ptr [rax+rax+00h]
0x1400132b0  test    eax, eax
0x1400132b2  js      loc_140013413
0x1400132b8  mov     [rsp+78h+Win32Protect], 2; Win32Protect
0x1400132c0  mov     [rsp+78h+AllocationType], 0; AllocationType
0x1400132c8  mov     [rsp+78h+InheritDisposition], 2; InheritDisposition
0x1400132d0  lea     rax, [rsp+78h+ViewSize]
0x1400132d8  mov     [rsp+78h+Handle], rax; ViewSize
0x1400132dd  mov     qword ptr [rsp+78h+AccessMode], 0; SectionOffset
0x1400132e6  mov     [rsp+78h+TableContext], 0; CommitSize
0x1400132ef  xor     r9d, r9d; ZeroBits
0x1400132f2  lea     r8, [rsp+78h+BaseAddress]; BaseAddress
0x1400132fa  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400132fe  mov     rcx, [rsp+78h+SectionHandle]; SectionHandle
0x140013306  call    cs:__imp_ZwMapViewOfSection
0x14001330d  nop     dword ptr [rax+rax+00h]
0x140013312  mov     ebx, eax
0x140013314  test    eax, eax
0x140013316  jns     loc_1400133E2
0x14001331c  mov     ebx, 0C0000142h
0x140013321  mov     rcx, [rsp+78h+SectionHandle]; Handle
0x140013329  call    cs:__imp_ZwClose
0x140013330  nop     dword ptr [rax+rax+00h]
0x140013335  test    ebx, ebx
0x140013337  js      loc_14001349F
0x14001333d  mov     eax, ebx
0x14001333f  mov     rbx, [rsp+78h+arg_8]
0x140013347  add     rsp, 60h
0x14001334b  pop     r15
0x14001334d  pop     r14
0x14001334f  pop     rsi
0x140013350  retn
0x140013352  call    GdiUnmapGDIW32PIDLockedBitmaps
0x140013357  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x14001335c  test    eax, eax
0x14001335e  jz      loc_1400134B5
0x140013364  call    ?GrepCloseCurrentProcessPreserveObjectReference@@YAHXZ; GrepCloseCurrentProcessPreserveObjectReference(void)
0x140013369  mov     r15d, eax
0x14001336c  mov     rcx, [rsi]; Process
0x14001336f  call    cs:__imp_PsGetProcessId
0x140013376  nop     dword ptr [rax+rax+00h]
0x14001337b  mov     rbx, rax
0x14001337e  call    cs:__imp_W32GetSessionState
0x140013385  nop     dword ptr [rax+rax+00h]
0x14001338a  mov     rcx, [rax+58h]
0x14001338e  mov     rdx, rbx; void *
0x140013391  mov     rcx, [rcx+0E90h]; this
0x140013398  call    ?DestroyProtectedOutputsOwnedByProcess@COPM@@QEAAXPEAX@Z; COPM::DestroyProtectedOutputsOwnedByProcess(void *)
0x14001339d  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400133a4  nop     dword ptr [rax+rax+00h]
0x1400133a9  mov     rcx, [rax+18h]
0x1400133ad  mov     rax, [rcx+980h]
0x1400133b4  test    rax, rax
0x1400133b7  jz      short loc_140013427
0x1400133b9  call    _guard_dispatch_icall
0x1400133be  test    eax, eax
0x1400133c0  jns     short loc_14001342E
0x1400133c2  lea     rcx, [rsi+0F8h]
0x1400133c9  xor     edx, edx
0x1400133cb  call    cs:__imp_DxDdProcessCallout
0x1400133d2  nop     dword ptr [rax+rax+00h]
0x1400133d7  lea     rbx, [rsi+58h]
0x1400133db  mov     dl, 1
0x1400133dd  jmp     loc_1400134D3
0x1400133e2  mov     edx, 1000h; Size
0x1400133e7  mov     r8d, 2; ProbeMode
0x1400133ed  mov     rcx, [rsp+78h+BaseAddress]; Address
0x1400133f5  call    cs:__imp_MmSecureVirtualMemory
0x1400133fc  nop     dword ptr [rax+rax+00h]
0x140013401  mov     [rsi+0F0h], rax
0x140013408  test    rax, rax
0x14001340b  jz      loc_14001331C
0x140013411  jmp     short loc_140013477
0x140013413  mov     ebx, 0C0000142h
0x140013418  jmp     loc_140013335
0x14001341d  mov     eax, 0C0000142h
0x140013422  jmp     loc_14001333F
0x140013427  mov     eax, 0C00000BBh
0x14001342c  jmp     short loc_1400133BE
0x14001342e  mov     rcx, [rsi]; Process
0x140013431  call    cs:__imp_PsGetProcessId
0x140013438  nop     dword ptr [rax+rax+00h]
0x14001343d  mov     rbx, rax
0x140013440  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140013447  nop     dword ptr [rax+rax+00h]
0x14001344c  mov     rcx, [rax+18h]
0x140013450  mov     rax, [rcx+988h]
0x140013457  test    rax, rax
0x14001345a  jz      loc_1400133C2
0x140013460  mov     rcx, rbx
0x140013463  call    _guard_dispatch_icall
0x140013468  jmp     loc_1400133C2
0x14001346d  mov     eax, 0C0000017h
0x140013472  jmp     loc_14001333F
0x140013477  lea     rcx, [r15+0F8h]
0x14001347e  mov     rdx, [rsp+78h+BaseAddress]
0x140013486  call    RtlWriteULong64ToUser
0x14001348b  jmp     loc_140013321
0x140013490  mov     ebx, 0C0000142h
0x140013495  mov     r14, [rsp+78h+var_28]
0x14001349a  jmp     loc_140013321
0x14001349f  xor     edx, edx
0x1400134a1  mov     rcx, r14
0x1400134a4  call    cs:__imp_DxDdProcessCallout
0x1400134ab  nop     dword ptr [rax+rax+00h]
0x1400134b0  jmp     loc_14001333D
0x1400134b5  call    ?GrepCloseCurrentProcess@@YAHXZ; GrepCloseCurrentProcess(void)
0x1400134ba  jmp     loc_140013369
0x1400134bf  mov     rdx, rax; Buffer
0x1400134c2  mov     rcx, rbx; Table
0x1400134c5  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400134cc  nop     dword ptr [rax+rax+00h]
0x1400134d1  xor     edx, edx; Restart
0x1400134d3  mov     rcx, rbx; Table
0x1400134d6  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400134dd  nop     dword ptr [rax+rax+00h]
0x1400134e2  test    rax, rax
0x1400134e5  jnz     short loc_1400134BF
0x1400134e7  lea     r14, [rsi+0C0h]
0x1400134ee  mov     rbx, [r14]
0x1400134f1  test    rbx, rbx
0x1400134f4  jnz     short loc_140013503
0x1400134f6  jmp     short loc_140013508
0x1400134f8  mov     rcx, rbx; Buffer
0x1400134fb  mov     rbx, [rbx]
0x1400134fe  call    GreDeleteFastMutex
0x140013503  cmp     rbx, r14
0x140013506  jnz     short loc_1400134F8
0x140013508  lea     r14, [rsi+0D0h]
0x14001350f  mov     rbx, [r14]
0x140013512  test    rbx, rbx
0x140013515  jnz     short loc_140013524
0x140013517  jmp     short loc_140013529
0x140013519  mov     rcx, rbx; Buffer
0x14001351c  mov     rbx, [rbx]
0x14001351f  call    GreDeleteFastMutex
0x140013524  cmp     rbx, r14
0x140013527  jnz     short loc_140013519
0x140013529  mov     rcx, [rsi+0F0h]; SecureHandle
0x140013530  test    rcx, rcx
0x140013533  jz      short loc_14001354C
0x140013535  call    cs:__imp_MmUnsecureVirtualMemory
0x14001353c  nop     dword ptr [rax+rax+00h]
0x140013541  mov     qword ptr [rsi+0F0h], 0
0x14001354c  neg     r15d
0x14001354f  sbb     eax, eax
0x140013551  not     eax
0x140013553  and     eax, 0C0000121h
0x140013558  jmp     loc_14001333F
```
