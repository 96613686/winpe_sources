# GdiProcessCallout

- ea: `0x140030b90`
- end: `0x140030f8d`
- name: `GdiProcessCallout`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140022024`
- `0x140030b90`
- `0x1400321b8`
- `0x140032c4c`
- `0x140039a90`
- `0x1400411c0`
- `0x1401c0610`
- `0x140238bf0`
- `0x1402bd2bc`
- `0x1402bd3b4`
- `0x1402bd3fc`

## import_xrefs

- `ntoskrnl!PsGetProcessPeb` at `0x140030c01`
- `ntoskrnl!PsGetProcessPeb` at `0x140030c01`
- `ntoskrnl!ZwClose` at `0x140030d59`
- `ntoskrnl!ZwClose` at `0x140030d59`
- `ntoskrnl!PsGetProcessId` at `0x140030d9f`
- `ntoskrnl!PsGetProcessId` at `0x140030e61`
- `ntoskrnl!PsGetProcessId` at `0x140030d9f`
- `ntoskrnl!PsGetProcessId` at `0x140030e61`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140030cd4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140030cd4`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140030bd6`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140030bd6`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140030f06`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140030f06`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140030ef5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140030ef5`
- `ntoskrnl!MmSecureVirtualMemory` at `0x140030e25`
- `ntoskrnl!MmSecureVirtualMemory` at `0x140030e25`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140030f65`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x140030f65`
- `ntoskrnl!ZwMapViewOfSection` at `0x140030d36`
- `ntoskrnl!ZwMapViewOfSection` at `0x140030d36`
- `WIN32K!DxDdProcessCallout` at `0x140030c5c`
- `WIN32K!DxDdProcessCallout` at `0x140030dfb`
- `WIN32K!DxDdProcessCallout` at `0x140030ed4`
- `WIN32K!DxDdProcessCallout` at `0x140030c5c`
- `WIN32K!DxDdProcessCallout` at `0x140030dfb`
- `WIN32K!DxDdProcessCallout` at `0x140030ed4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140030dcd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140030e70`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140030dcd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140030e70`
- `WIN32K!W32GetSessionState` at `0x140030c94`
- `WIN32K!W32GetSessionState` at `0x140030dae`
- `WIN32K!W32GetSessionState` at `0x140030c94`
- `WIN32K!W32GetSessionState` at `0x140030dae`

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
  __int64 v16; // rcx
  __int64 (*v17)(void); // rax
  int v18; // eax
  BOOLEAN i; // dl
  HANDLE v20; // rax
  HANDLE v21; // rbx
  __int64 v22; // rcx
  void (__fastcall *v23)(HANDLE); // rax
  PVOID v24; // rax
  _QWORD *v25; // rbx
  void *v26; // rcx
  _QWORD *v27; // rbx
  void *v28; // rcx
  void *v29; // rcx
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
        if ( v9 >= 0 && (v20 = MmSecureVirtualMemory(BaseAddress, 0x1000u, 2u), (*(_QWORD *)(a1 + 240) = v20) != 0) )
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
    v17 = *(__int64 (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v16) + 24) + 2432LL);
    if ( v17 )
      v18 = v17();
    else
      v18 = -1073741637;
    if ( v18 >= 0 )
    {
      v21 = PsGetProcessId(*(PEPROCESS *)a1);
      v23 = *(void (__fastcall **)(HANDLE))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v22) + 24) + 2440LL);
      if ( v23 )
        v23(v21);
    }
    DxDdProcessCallout(a1 + 248, 0);
    for ( i = 1; ; i = 0 )
    {
      v24 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), i);
      if ( !v24 )
        break;
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 88), v24);
    }
    v25 = *(_QWORD **)(a1 + 192);
    if ( v25 )
    {
      while ( v25 != (_QWORD *)(a1 + 192) )
      {
        v26 = v25;
        v25 = (_QWORD *)*v25;
        GreDeleteFastMutex(v26);
      }
    }
    v27 = *(_QWORD **)(a1 + 208);
    if ( v27 )
    {
      while ( v27 != (_QWORD *)(a1 + 208) )
      {
        v28 = v27;
        v27 = (_QWORD *)*v27;
        GreDeleteFastMutex(v28);
      }
    }
    v29 = *(void **)(a1 + 240);
    if ( v29 )
    {
      MmUnsecureVirtualMemory(v29);
      *(_QWORD *)(a1 + 240) = 0;
    }
    return v12 == 0 ? 0xC0000121 : 0;
  }
}

```

## disassembly

```asm
0x140030b90  mov     [rsp+arg_8], rbx
0x140030b95  push    rsi
0x140030b96  push    r14
0x140030b98  push    r15
0x140030b9a  sub     rsp, 60h
0x140030b9e  mov     bl, dl
0x140030ba0  mov     rsi, rcx
0x140030ba3  test    rcx, rcx
0x140030ba6  jz      loc_140030E9D
0x140030bac  test    dl, dl
0x140030bae  jz      loc_140030D82
0x140030bb4  add     rcx, 58h ; 'X'; Table
0x140030bb8  mov     [rsp+78h+TableContext], 0; TableContext
0x140030bc1  lea     r9, rimUserMemAllocNodeFree; FreeRoutine
0x140030bc8  lea     r8, ?GDIEngUserMemAllocNodeAlloc@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x140030bcf  lea     rdx, ?GDIEngUserMemAllocNodeCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x140030bd6  call    cs:__imp_RtlInitializeGenericTableAvl
0x140030bdd  nop     dword ptr [rax+rax+00h]
0x140030be2  lea     rax, [rsi+0C0h]
0x140030be9  mov     [rax+8], rax
0x140030bed  mov     [rax], rax
0x140030bf0  lea     rax, [rsi+0D0h]
0x140030bf7  mov     [rax+8], rax
0x140030bfb  mov     [rax], rax
0x140030bfe  mov     rcx, [rsi]
0x140030c01  call    cs:__imp_PsGetProcessPeb
0x140030c08  nop     dword ptr [rax+rax+00h]
0x140030c0d  mov     r15, rax
0x140030c10  test    rax, rax
0x140030c13  jz      loc_140030E4D
0x140030c19  lea     rcx, [rax+108h]
0x140030c20  mov     edx, [rsi+118h]
0x140030c26  call    RtlWriteULongToUser
0x140030c2b  lea     rcx, [r15+140h]; void *
0x140030c32  xor     edx, edx
0x140030c34  mov     r8d, 0F0h
0x140030c3a  call    RtlSetUserMemory
0x140030c3f  jmp     short loc_140030C4B
0x140030c41  mov     eax, 0C0000142h
0x140030c46  jmp     loc_140030D6F
0x140030c4b  lea     r14, [rsi+0F8h]
0x140030c52  mov     [rsp+78h+var_28], r14
0x140030c57  mov     dl, bl
0x140030c59  mov     rcx, r14
0x140030c5c  call    cs:__imp_DxDdProcessCallout
0x140030c63  nop     dword ptr [rax+rax+00h]
0x140030c68  test    eax, eax
0x140030c6a  js      loc_140030E4D
0x140030c70  mov     [rsp+78h+BaseAddress], 0
0x140030c7c  mov     [rsp+78h+ViewSize], 0
0x140030c88  mov     [rsp+78h+SectionHandle], 0
0x140030c94  call    cs:__imp_W32GetSessionState
0x140030c9b  nop     dword ptr [rax+rax+00h]
0x140030ca0  mov     rcx, [rax+58h]
0x140030ca4  lea     rax, [rsp+78h+SectionHandle]
0x140030cac  mov     [rsp+78h+Handle], rax; Handle
0x140030cb1  mov     [rsp+78h+AccessMode], 0; AccessMode
0x140030cb6  mov     [rsp+78h+TableContext], 0; ObjectType
0x140030cbf  mov     r9d, 0F001Fh; DesiredAccess
0x140030cc5  xor     r8d, r8d; PassedAccessState
0x140030cc8  mov     edx, 200h; HandleAttributes
0x140030ccd  mov     rcx, [rcx+8E0h]; Object
0x140030cd4  call    cs:__imp_ObOpenObjectByPointer
0x140030cdb  nop     dword ptr [rax+rax+00h]
0x140030ce0  test    eax, eax
0x140030ce2  js      loc_140030E43
0x140030ce8  mov     [rsp+78h+Win32Protect], 2; Win32Protect
0x140030cf0  mov     [rsp+78h+AllocationType], 0; AllocationType
0x140030cf8  mov     [rsp+78h+InheritDisposition], 2; InheritDisposition
0x140030d00  lea     rax, [rsp+78h+ViewSize]
0x140030d08  mov     [rsp+78h+Handle], rax; ViewSize
0x140030d0d  mov     qword ptr [rsp+78h+AccessMode], 0; SectionOffset
0x140030d16  mov     [rsp+78h+TableContext], 0; CommitSize
0x140030d1f  xor     r9d, r9d; ZeroBits
0x140030d22  lea     r8, [rsp+78h+BaseAddress]; BaseAddress
0x140030d2a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140030d2e  mov     rcx, [rsp+78h+SectionHandle]; SectionHandle
0x140030d36  call    cs:__imp_ZwMapViewOfSection
0x140030d3d  nop     dword ptr [rax+rax+00h]
0x140030d42  mov     ebx, eax
0x140030d44  test    eax, eax
0x140030d46  jns     loc_140030E12
0x140030d4c  mov     ebx, 0C0000142h
0x140030d51  mov     rcx, [rsp+78h+SectionHandle]; Handle
0x140030d59  call    cs:__imp_ZwClose
0x140030d60  nop     dword ptr [rax+rax+00h]
0x140030d65  test    ebx, ebx
0x140030d67  js      loc_140030ECF
0x140030d6d  mov     eax, ebx
0x140030d6f  mov     rbx, [rsp+78h+arg_8]
0x140030d77  add     rsp, 60h
0x140030d7b  pop     r15
0x140030d7d  pop     r14
0x140030d7f  pop     rsi
0x140030d80  retn
0x140030d82  call    GdiUnmapGDIW32PIDLockedBitmaps
0x140030d87  call    Feature_PreserveObjectReference__private_IsEnabledNoReportingNoInline
0x140030d8c  test    eax, eax
0x140030d8e  jz      loc_140030EE5
0x140030d94  call    ?GrepCloseCurrentProcessPreserveObjectReference@@YAHXZ; GrepCloseCurrentProcessPreserveObjectReference(void)
0x140030d99  mov     r15d, eax
0x140030d9c  mov     rcx, [rsi]; Process
0x140030d9f  call    cs:__imp_PsGetProcessId
0x140030da6  nop     dword ptr [rax+rax+00h]
0x140030dab  mov     rbx, rax
0x140030dae  call    cs:__imp_W32GetSessionState
0x140030db5  nop     dword ptr [rax+rax+00h]
0x140030dba  mov     rcx, [rax+58h]
0x140030dbe  mov     rdx, rbx; void *
0x140030dc1  mov     rcx, [rcx+0E90h]; this
0x140030dc8  call    ?DestroyProtectedOutputsOwnedByProcess@COPM@@QEAAXPEAX@Z; COPM::DestroyProtectedOutputsOwnedByProcess(void *)
0x140030dcd  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140030dd4  nop     dword ptr [rax+rax+00h]
0x140030dd9  mov     rcx, [rax+18h]
0x140030ddd  mov     rax, [rcx+980h]
0x140030de4  test    rax, rax
0x140030de7  jz      short loc_140030E57
0x140030de9  call    _guard_dispatch_icall
0x140030dee  test    eax, eax
0x140030df0  jns     short loc_140030E5E
0x140030df2  lea     rcx, [rsi+0F8h]
0x140030df9  xor     edx, edx
0x140030dfb  call    cs:__imp_DxDdProcessCallout
0x140030e02  nop     dword ptr [rax+rax+00h]
0x140030e07  lea     rbx, [rsi+58h]
0x140030e0b  mov     dl, 1
0x140030e0d  jmp     loc_140030F03
0x140030e12  mov     edx, 1000h; Size
0x140030e17  mov     r8d, 2; ProbeMode
0x140030e1d  mov     rcx, [rsp+78h+BaseAddress]; Address
0x140030e25  call    cs:__imp_MmSecureVirtualMemory
0x140030e2c  nop     dword ptr [rax+rax+00h]
0x140030e31  mov     [rsi+0F0h], rax
0x140030e38  test    rax, rax
0x140030e3b  jz      loc_140030D4C
0x140030e41  jmp     short loc_140030EA7
0x140030e43  mov     ebx, 0C0000142h
0x140030e48  jmp     loc_140030D65
0x140030e4d  mov     eax, 0C0000142h
0x140030e52  jmp     loc_140030D6F
0x140030e57  mov     eax, 0C00000BBh
0x140030e5c  jmp     short loc_140030DEE
0x140030e5e  mov     rcx, [rsi]; Process
0x140030e61  call    cs:__imp_PsGetProcessId
0x140030e68  nop     dword ptr [rax+rax+00h]
0x140030e6d  mov     rbx, rax
0x140030e70  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140030e77  nop     dword ptr [rax+rax+00h]
0x140030e7c  mov     rcx, [rax+18h]
0x140030e80  mov     rax, [rcx+988h]
0x140030e87  test    rax, rax
0x140030e8a  jz      loc_140030DF2
0x140030e90  mov     rcx, rbx
0x140030e93  call    _guard_dispatch_icall
0x140030e98  jmp     loc_140030DF2
0x140030e9d  mov     eax, 0C0000017h
0x140030ea2  jmp     loc_140030D6F
0x140030ea7  lea     rcx, [r15+0F8h]
0x140030eae  mov     rdx, [rsp+78h+BaseAddress]
0x140030eb6  call    RtlWriteULong64ToUser
0x140030ebb  jmp     loc_140030D51
0x140030ec0  mov     ebx, 0C0000142h
0x140030ec5  mov     r14, [rsp+78h+var_28]
0x140030eca  jmp     loc_140030D51
0x140030ecf  xor     edx, edx
0x140030ed1  mov     rcx, r14
0x140030ed4  call    cs:__imp_DxDdProcessCallout
0x140030edb  nop     dword ptr [rax+rax+00h]
0x140030ee0  jmp     loc_140030D6D
0x140030ee5  call    ?GrepCloseCurrentProcess@@YAHXZ; GrepCloseCurrentProcess(void)
0x140030eea  jmp     loc_140030D99
0x140030eef  mov     rdx, rax; Buffer
0x140030ef2  mov     rcx, rbx; Table
0x140030ef5  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140030efc  nop     dword ptr [rax+rax+00h]
0x140030f01  xor     edx, edx; Restart
0x140030f03  mov     rcx, rbx; Table
0x140030f06  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140030f0d  nop     dword ptr [rax+rax+00h]
0x140030f12  test    rax, rax
0x140030f15  jnz     short loc_140030EEF
0x140030f17  lea     r14, [rsi+0C0h]
0x140030f1e  mov     rbx, [r14]
0x140030f21  test    rbx, rbx
0x140030f24  jnz     short loc_140030F33
0x140030f26  jmp     short loc_140030F38
0x140030f28  mov     rcx, rbx; Buffer
0x140030f2b  mov     rbx, [rbx]
0x140030f2e  call    GreDeleteFastMutex
0x140030f33  cmp     rbx, r14
0x140030f36  jnz     short loc_140030F28
0x140030f38  lea     r14, [rsi+0D0h]
0x140030f3f  mov     rbx, [r14]
0x140030f42  test    rbx, rbx
0x140030f45  jnz     short loc_140030F54
0x140030f47  jmp     short loc_140030F59
0x140030f49  mov     rcx, rbx; Buffer
0x140030f4c  mov     rbx, [rbx]
0x140030f4f  call    GreDeleteFastMutex
0x140030f54  cmp     rbx, r14
0x140030f57  jnz     short loc_140030F49
0x140030f59  mov     rcx, [rsi+0F0h]; SecureHandle
0x140030f60  test    rcx, rcx
0x140030f63  jz      short loc_140030F7C
0x140030f65  call    cs:__imp_MmUnsecureVirtualMemory
0x140030f6c  nop     dword ptr [rax+rax+00h]
0x140030f71  mov     qword ptr [rsi+0F0h], 0
0x140030f7c  neg     r15d
0x140030f7f  sbb     eax, eax
0x140030f81  not     eax
0x140030f83  and     eax, 0C0000121h
0x140030f88  jmp     loc_140030D6F
```
