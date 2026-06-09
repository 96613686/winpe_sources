# GdiProcessCallout

- ea: `0x1400d9e80`
- end: `0x1400da27d`
- name: `GdiProcessCallout`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14002b044`
- `0x140041380`
- `0x14004a0d0`
- `0x1400d9e80`
- `0x1400db4a8`
- `0x1400dbf3c`
- `0x1401c00b0`
- `0x140238240`
- `0x1402bb218`
- `0x1402bb310`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x1400d9ef1`
- `ntoskrnl!PsGetProcessPeb` at `0x1400d9ef1`
- `ntoskrnl!ZwClose` at `0x1400da049`
- `ntoskrnl!ZwClose` at `0x1400da049`
- `ntoskrnl!PsGetProcessId` at `0x1400da08f`
- `ntoskrnl!PsGetProcessId` at `0x1400da151`
- `ntoskrnl!PsGetProcessId` at `0x1400da08f`
- `ntoskrnl!PsGetProcessId` at `0x1400da151`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d9fc4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d9fc4`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400d9ec6`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400d9ec6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400da1f6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400da1f6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400da1e5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400da1e5`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400da115`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400da115`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400da255`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400da255`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400da026`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400da026`
- `WIN32K!DxDdProcessCallout` at `0x1400d9f4c`
- `WIN32K!DxDdProcessCallout` at `0x1400da0eb`
- `WIN32K!DxDdProcessCallout` at `0x1400da1c4`
- `WIN32K!DxDdProcessCallout` at `0x1400d9f4c`
- `WIN32K!DxDdProcessCallout` at `0x1400da0eb`
- `WIN32K!DxDdProcessCallout` at `0x1400da1c4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400da0bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400da160`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400da0bd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400da160`
- `WIN32K!W32GetSessionState` at `0x1400d9f84`
- `WIN32K!W32GetSessionState` at `0x1400da09e`
- `WIN32K!W32GetSessionState` at `0x1400d9f84`
- `WIN32K!W32GetSessionState` at `0x1400da09e`

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
  __int64 (*v16)(void); // rax
  int v17; // eax
  BOOLEAN i; // dl
  HANDLE v19; // rax
  HANDLE v20; // rbx
  void (__fastcall *v21)(HANDLE); // rax
  PVOID v22; // rax
  _QWORD *v23; // rbx
  void *v24; // rcx
  _QWORD *v25; // rbx
  void *v26; // rcx
  void *v27; // rcx
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
      (PRTL_AVL_FREE_ROUTINE)rimUserMemAllocNodeFree,
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
        if ( v9 >= 0 && (v19 = MmSecureVirtualMemory(BaseAddress, 0x1000u, 2u), (*(_QWORD *)(a1 + 240) = v19) != 0) )
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
    v16 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2432LL);
    if ( v16 )
      v17 = v16();
    else
      v17 = -1073741637;
    if ( v17 >= 0 )
    {
      v20 = PsGetProcessId(*(PEPROCESS *)a1);
      v21 = *(void (__fastcall **)(HANDLE))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2440LL);
      if ( v21 )
        v21(v20);
    }
    DxDdProcessCallout(a1 + 248, 0);
    for ( i = 1; ; i = 0 )
    {
      v22 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), i);
      if ( !v22 )
        break;
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), v22);
    }
    v23 = *(_QWORD **)(a1 + 192);
    if ( v23 )
    {
      while ( v23 != (_QWORD *)(a1 + 192) )
      {
        v24 = v23;
        v23 = (_QWORD *)*v23;
        GreDeleteFastMutex(v24);
      }
    }
    v25 = *(_QWORD **)(a1 + 208);
    if ( v25 )
    {
      while ( v25 != (_QWORD *)(a1 + 208) )
      {
        v26 = v25;
        v25 = (_QWORD *)*v25;
        GreDeleteFastMutex(v26);
      }
    }
    v27 = *(void **)(a1 + 240);
    if ( v27 )
    {
      MmUnsecureVirtualMemory(v27);
      *(_QWORD *)(a1 + 240) = 0;
    }
    return v12 == 0 ? 0xC0000121 : 0;
  }
}

```

## disassembly

```asm
0x1400d9e80  mov     [rsp+arg_8], rbx
0x1400d9e85  push    rsi
0x1400d9e86  push    r14
0x1400d9e88  push    r15
0x1400d9e8a  sub     rsp, 60h
0x1400d9e8e  mov     bl, dl
0x1400d9e90  mov     rsi, rcx
0x1400d9e93  test    rcx, rcx
0x1400d9e96  jz      loc_1400DA18D
0x1400d9e9c  test    dl, dl
0x1400d9e9e  jz      loc_1400DA072
0x1400d9ea4  add     rcx, 58h ; 'X'; Table
0x1400d9ea8  mov     [rsp+78h+TableContext], 0; TableContext
0x1400d9eb1  lea     r9, rimUserMemAllocNodeFree; FreeRoutine
0x1400d9eb8  lea     r8, ?GDIEngUserMemAllocNodeAlloc@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1400d9ebf  lea     rdx, ?GDIEngUserMemAllocNodeCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1400d9ec6  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400d9ecd  nop     dword ptr [rax+rax+00h]
0x1400d9ed2  lea     rax, [rsi+0C0h]
0x1400d9ed9  mov     [rax+8], rax
0x1400d9edd  mov     [rax], rax
0x1400d9ee0  lea     rax, [rsi+0D0h]
0x1400d9ee7  mov     [rax+8], rax
0x1400d9eeb  mov     [rax], rax
0x1400d9eee  mov     rcx, [rsi]
0x1400d9ef1  call    cs:__imp_PsGetProcessPeb
0x1400d9ef8  nop     dword ptr [rax+rax+00h]
0x1400d9efd  mov     r15, rax
0x1400d9f00  test    rax, rax
0x1400d9f03  jz      loc_1400DA13D
0x1400d9f09  lea     rcx, [rax+108h]
0x1400d9f10  mov     edx, [rsi+118h]
0x1400d9f16  call    RtlWriteULongToUser
0x1400d9f1b  lea     rcx, [r15+140h]; void *
0x1400d9f22  xor     edx, edx
0x1400d9f24  mov     r8d, 0F0h
0x1400d9f2a  call    RtlSetUserMemory
0x1400d9f2f  jmp     short loc_1400D9F3B
0x1400d9f31  mov     eax, 0C0000142h
0x1400d9f36  jmp     loc_1400DA05F
0x1400d9f3b  lea     r14, [rsi+0F8h]
0x1400d9f42  mov     [rsp+78h+var_28], r14
0x1400d9f47  mov     dl, bl
0x1400d9f49  mov     rcx, r14
0x1400d9f4c  call    cs:__imp_DxDdProcessCallout
0x1400d9f53  nop     dword ptr [rax+rax+00h]
0x1400d9f58  test    eax, eax
0x1400d9f5a  js      loc_1400DA13D
0x1400d9f60  mov     [rsp+78h+BaseAddress], 0
0x1400d9f6c  mov     [rsp+78h+ViewSize], 0
0x1400d9f78  mov     [rsp+78h+SectionHandle], 0
0x1400d9f84  call    cs:__imp_W32GetSessionState
0x1400d9f8b  nop     dword ptr [rax+rax+00h]
0x1400d9f90  mov     rcx, [rax+58h]
0x1400d9f94  lea     rax, [rsp+78h+SectionHandle]
0x1400d9f9c  mov     [rsp+78h+Handle], rax; Handle
0x1400d9fa1  mov     [rsp+78h+AccessMode], 0; AccessMode
0x1400d9fa6  mov     [rsp+78h+TableContext], 0; ObjectType
0x1400d9faf  mov     r9d, 0F001Fh; DesiredAccess
0x1400d9fb5  xor     r8d, r8d; PassedAccessState
0x1400d9fb8  mov     edx, 200h; HandleAttributes
0x1400d9fbd  mov     rcx, [rcx+8E0h]; Object
0x1400d9fc4  call    cs:__imp_ObOpenObjectByPointer
0x1400d9fcb  nop     dword ptr [rax+rax+00h]
0x1400d9fd0  test    eax, eax
0x1400d9fd2  js      loc_1400DA133
0x1400d9fd8  mov     [rsp+78h+Win32Protect], 2; Win32Protect
0x1400d9fe0  mov     [rsp+78h+AllocationType], 0; AllocationType
0x1400d9fe8  mov     [rsp+78h+InheritDisposition], 2; InheritDisposition
0x1400d9ff0  lea     rax, [rsp+78h+ViewSize]
0x1400d9ff8  mov     [rsp+78h+Handle], rax; ViewSize
0x1400d9ffd  mov     qword ptr [rsp+78h+AccessMode], 0; SectionOffset
0x1400da006  mov     [rsp+78h+TableContext], 0; CommitSize
0x1400da00f  xor     r9d, r9d; ZeroBits
0x1400da012  lea     r8, [rsp+78h+BaseAddress]; BaseAddress
0x1400da01a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400da01e  mov     rcx, [rsp+78h+SectionHandle]; SectionHandle
0x1400da026  call    cs:__imp_ZwMapViewOfSection
0x1400da02d  nop     dword ptr [rax+rax+00h]
0x1400da032  mov     ebx, eax
0x1400da034  test    eax, eax
0x1400da036  jns     loc_1400DA102
0x1400da03c  mov     ebx, 0C0000142h
0x1400da041  mov     rcx, [rsp+78h+SectionHandle]; Handle
0x1400da049  call    cs:__imp_ZwClose
0x1400da050  nop     dword ptr [rax+rax+00h]
0x1400da055  test    ebx, ebx
0x1400da057  js      loc_1400DA1BF
0x1400da05d  mov     eax, ebx
0x1400da05f  mov     rbx, [rsp+78h+arg_8]
0x1400da067  add     rsp, 60h
0x1400da06b  pop     r15
0x1400da06d  pop     r14
0x1400da06f  pop     rsi
0x1400da070  retn
0x1400da072  call    GdiUnmapGDIW32PIDLockedBitmaps
0x1400da077  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x1400da07c  test    eax, eax
0x1400da07e  jz      loc_1400DA1D5
0x1400da084  call    ?GrepCloseCurrentProcessPreserveObjectReference@@YAHXZ; GrepCloseCurrentProcessPreserveObjectReference(void)
0x1400da089  mov     r15d, eax
0x1400da08c  mov     rcx, [rsi]; Process
0x1400da08f  call    cs:__imp_PsGetProcessId
0x1400da096  nop     dword ptr [rax+rax+00h]
0x1400da09b  mov     rbx, rax
0x1400da09e  call    cs:__imp_W32GetSessionState
0x1400da0a5  nop     dword ptr [rax+rax+00h]
0x1400da0aa  mov     rcx, [rax+58h]
0x1400da0ae  mov     rdx, rbx; void *
0x1400da0b1  mov     rcx, [rcx+0E90h]; this
0x1400da0b8  call    ?DestroyProtectedOutputsOwnedByProcess@COPM@@QEAAXPEAX@Z; COPM::DestroyProtectedOutputsOwnedByProcess(void *)
0x1400da0bd  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400da0c4  nop     dword ptr [rax+rax+00h]
0x1400da0c9  mov     rcx, [rax+18h]
0x1400da0cd  mov     rax, [rcx+980h]
0x1400da0d4  test    rax, rax
0x1400da0d7  jz      short loc_1400DA147
0x1400da0d9  call    _guard_dispatch_icall
0x1400da0de  test    eax, eax
0x1400da0e0  jns     short loc_1400DA14E
0x1400da0e2  lea     rcx, [rsi+0F8h]
0x1400da0e9  xor     edx, edx
0x1400da0eb  call    cs:__imp_DxDdProcessCallout
0x1400da0f2  nop     dword ptr [rax+rax+00h]
0x1400da0f7  lea     rbx, [rsi+58h]
0x1400da0fb  mov     dl, 1
0x1400da0fd  jmp     loc_1400DA1F3
0x1400da102  mov     edx, 1000h; Size
0x1400da107  mov     r8d, 2; ProbeMode
0x1400da10d  mov     rcx, [rsp+78h+BaseAddress]; Address
0x1400da115  call    cs:__imp_MmSecureVirtualMemory
0x1400da11c  nop     dword ptr [rax+rax+00h]
0x1400da121  mov     [rsi+0F0h], rax
0x1400da128  test    rax, rax
0x1400da12b  jz      loc_1400DA03C
0x1400da131  jmp     short loc_1400DA197
0x1400da133  mov     ebx, 0C0000142h
0x1400da138  jmp     loc_1400DA055
0x1400da13d  mov     eax, 0C0000142h
0x1400da142  jmp     loc_1400DA05F
0x1400da147  mov     eax, 0C00000BBh
0x1400da14c  jmp     short loc_1400DA0DE
0x1400da14e  mov     rcx, [rsi]; Process
0x1400da151  call    cs:__imp_PsGetProcessId
0x1400da158  nop     dword ptr [rax+rax+00h]
0x1400da15d  mov     rbx, rax
0x1400da160  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400da167  nop     dword ptr [rax+rax+00h]
0x1400da16c  mov     rcx, [rax+18h]
0x1400da170  mov     rax, [rcx+988h]
0x1400da177  test    rax, rax
0x1400da17a  jz      loc_1400DA0E2
0x1400da180  mov     rcx, rbx
0x1400da183  call    _guard_dispatch_icall
0x1400da188  jmp     loc_1400DA0E2
0x1400da18d  mov     eax, 0C0000017h
0x1400da192  jmp     loc_1400DA05F
0x1400da197  lea     rcx, [r15+0F8h]
0x1400da19e  mov     rdx, [rsp+78h+BaseAddress]
0x1400da1a6  call    RtlWriteULong64ToUser
0x1400da1ab  jmp     loc_1400DA041
0x1400da1b0  mov     ebx, 0C0000142h
0x1400da1b5  mov     r14, [rsp+78h+var_28]
0x1400da1ba  jmp     loc_1400DA041
0x1400da1bf  xor     edx, edx
0x1400da1c1  mov     rcx, r14
0x1400da1c4  call    cs:__imp_DxDdProcessCallout
0x1400da1cb  nop     dword ptr [rax+rax+00h]
0x1400da1d0  jmp     loc_1400DA05D
0x1400da1d5  call    ?GrepCloseCurrentProcess@@YAHXZ; GrepCloseCurrentProcess(void)
0x1400da1da  jmp     loc_1400DA089
0x1400da1df  mov     rdx, rax; Buffer
0x1400da1e2  mov     rcx, rbx; Table
0x1400da1e5  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400da1ec  nop     dword ptr [rax+rax+00h]
0x1400da1f1  xor     edx, edx; Restart
0x1400da1f3  mov     rcx, rbx; Table
0x1400da1f6  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400da1fd  nop     dword ptr [rax+rax+00h]
0x1400da202  test    rax, rax
0x1400da205  jnz     short loc_1400DA1DF
0x1400da207  lea     r14, [rsi+0C0h]
0x1400da20e  mov     rbx, [r14]
0x1400da211  test    rbx, rbx
0x1400da214  jnz     short loc_1400DA223
0x1400da216  jmp     short loc_1400DA228
0x1400da218  mov     rcx, rbx; Buffer
0x1400da21b  mov     rbx, [rbx]
0x1400da21e  call    GreDeleteFastMutex
0x1400da223  cmp     rbx, r14
0x1400da226  jnz     short loc_1400DA218
0x1400da228  lea     r14, [rsi+0D0h]
0x1400da22f  mov     rbx, [r14]
0x1400da232  test    rbx, rbx
0x1400da235  jnz     short loc_1400DA244
0x1400da237  jmp     short loc_1400DA249
0x1400da239  mov     rcx, rbx; Buffer
0x1400da23c  mov     rbx, [rbx]
0x1400da23f  call    GreDeleteFastMutex
0x1400da244  cmp     rbx, r14
0x1400da247  jnz     short loc_1400DA239
0x1400da249  mov     rcx, [rsi+0F0h]; SecureHandle
0x1400da250  test    rcx, rcx
0x1400da253  jz      short loc_1400DA26C
0x1400da255  call    cs:__imp_MmUnsecureVirtualMemory
0x1400da25c  nop     dword ptr [rax+rax+00h]
0x1400da261  mov     qword ptr [rsi+0F0h], 0
0x1400da26c  neg     r15d
0x1400da26f  sbb     eax, eax
0x1400da271  not     eax
0x1400da273  and     eax, 0C0000121h
0x1400da278  jmp     loc_1400DA05F
```
