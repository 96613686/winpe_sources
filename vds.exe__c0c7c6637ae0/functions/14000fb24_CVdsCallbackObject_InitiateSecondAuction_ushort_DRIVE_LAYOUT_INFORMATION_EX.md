# CVdsCallbackObject::InitiateSecondAuction(ushort *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14000fb24`
- end: `0x14000fd16`
- name: `?InitiateSecondAuction@CVdsCallbackObject@@AEAAKPEAGPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `498`
- prototype: `unsigned int(CVdsCallbackObject *__hidden this, unsigned __int16 *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000fa00`

## callees

- `0x140006e60`
- `0x14000f930`
- `0x14000f9b0`
- `0x14000fb24`
- `0x140011a60`
- `0x140012c70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fbed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fb84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000fbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fc70`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000fc58`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000fc58`
- `vdsutil!VdsTraceExW` at `0x14000fbc8`
- `vdsutil!VdsTraceExW` at `0x14000fccc`
- `vdsutil!VdsTraceExW` at `0x14000fbc8`
- `vdsutil!VdsTraceExW` at `0x14000fccc`
- `vdsutil!VdsHeapAlloc` at `0x14000fb99`
- `vdsutil!VdsHeapAlloc` at `0x14000fbfb`
- `vdsutil!VdsHeapAlloc` at `0x14000fb99`
- `vdsutil!VdsHeapAlloc` at `0x14000fbfb`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000fb67`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000fb67`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000fcd7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000fcd7`
- `vdsutil!VdsTraceW` at `0x14000fc22`
- `vdsutil!VdsTraceW` at `0x14000fc87`
- `vdsutil!VdsTraceW` at `0x14000fc22`
- `vdsutil!VdsTraceW` at `0x14000fc87`

## string_xrefs

- `0x14000fcc0`: `CVdsCallbackObject::InitiateSecondAuction, 1, error=%lX, pwszDevicePath=%s, pLayout=%p`
- `0x14000fbbc`: `CVdsCallbackObject::InitiateSecondAuction, 2, error=%lX, pwszDevicePath=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsCallbackObject::InitiateSecondAuction(
        CVdsCallbackObject *this,
        unsigned __int16 *a2,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a3)
{
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  __int64 v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // r15
  HANDLE v10; // rax
  __int64 v11; // rax
  __int64 v12; // r10
  HANDLE v13; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v15; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-18h] BYREF
  DWORD ThreadId; // [rsp+90h] [rbp+40h] BYREF
  int v18; // [rsp+94h] [rbp+44h]
  unsigned __int16 *v19; // [rsp+98h] [rbp+48h] BYREF
  LPVOID lpParameter; // [rsp+A0h] [rbp+50h] BYREF
  void *v21; // [rsp+A8h] [rbp+58h] BYREF

  v18 = HIDWORD(this);
  lpParameter = 0;
  v19 = 0;
  v21 = 0;
  ThreadId = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsCallbackObject::InitiateSecondAuction()");
  v15 = a3;
  if ( a2 && a3 )
  {
    ProcessHeap = GetProcessHeap();
    LODWORD(LastError) = 8;
    v7 = VdsHeapAlloc(ProcessHeap, 8, 32);
    CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&lpParameter, v7);
    v8 = lpParameter;
    if ( lpParameter )
    {
      *((_QWORD *)lpParameter + 3) = a3;
      v9 = -1;
      do
        ++v9;
      while ( a2[v9] );
      v10 = GetProcessHeap();
      v11 = VdsHeapAlloc(v10, 8, 2 * v9 + 2);
      CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&v19, v11);
      if ( v19 )
      {
        StringCchCopyW(v19, v9 + 1, a2);
        *v8 = v12;
        v13 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)AuctionThread, v8, 0, &ThreadId);
        CVdsHandleImpl<0>::operator=(&v21, v13);
        if ( v21 )
        {
          LODWORD(LastError) = 0;
          lpParameter = 0;
          v19 = 0;
          v15 = 0;
        }
        else
        {
          LastError = GetLastError();
          VdsTraceW(0, L"CVdsCallbackObject::InitiateSecondAuction, 4, %s, error=%ld", a2, LastError);
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsCallbackObject::InitiateSecondAuction, 3, %s", a2);
      }
    }
    else
    {
      VdsTraceExW(95, 0, L"CVdsCallbackObject::InitiateSecondAuction, 2, error=%lX, pwszDevicePath=%s", 8, a2);
    }
  }
  else
  {
    LODWORD(LastError) = 87;
    if ( !a2 )
      a2 = L"UNKNOWN";
    VdsTraceExW(
      95,
      0,
      L"CVdsCallbackObject::InitiateSecondAuction, 1, error=%lX, pwszDevicePath=%s, pLayout=%p",
      87,
      a2,
      a3,
      v15);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v21);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v15);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v19);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000fb24  mov     qword ptr [rsp-38h+ThreadId], rcx
0x14000fb29  push    rbp
0x14000fb2a  push    rbx
0x14000fb2b  push    rsi
0x14000fb2c  push    rdi
0x14000fb2d  push    r12
0x14000fb2f  push    r14
0x14000fb31  push    r15
0x14000fb33  mov     rbp, rsp
0x14000fb36  sub     rsp, 50h
0x14000fb3a  mov     rdi, r8
0x14000fb3d  mov     r14, rdx
0x14000fb40  xor     r12d, r12d
0x14000fb43  mov     [rbp+lpParameter], r12
0x14000fb47  mov     [rbp+arg_8], r12
0x14000fb4b  mov     [rbp+var_20], r12
0x14000fb4f  mov     [rbp+arg_18], r12
0x14000fb53  mov     [rbp+ThreadId], r12d
0x14000fb57  lea     r8, aCvdscallbackob_18; "CVdsCallbackObject::InitiateSecondAucti"...
0x14000fb5e  lea     edx, [r12+5Eh]
0x14000fb63  lea     rcx, [rbp+var_18]
0x14000fb67  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000fb6d  nop
0x14000fb6e  mov     [rbp+var_20], rdi
0x14000fb72  test    r14, r14
0x14000fb75  jz      loc_14000FCA0
0x14000fb7b  test    rdi, rdi
0x14000fb7e  jz      loc_14000FCA0
0x14000fb84  call    cs:__imp_GetProcessHeap
0x14000fb8a  mov     rcx, rax
0x14000fb8d  lea     esi, [r12+8]
0x14000fb92  lea     r8d, [r12+20h]
0x14000fb97  mov     edx, esi
0x14000fb99  call    cs:__imp_VdsHeapAlloc
0x14000fb9f  mov     rdx, rax
0x14000fba2  lea     rcx, [rbp+lpParameter]
0x14000fba6  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x14000fbab  mov     rbx, [rbp+lpParameter]
0x14000fbaf  test    rbx, rbx
0x14000fbb2  jnz     short loc_14000FBD3
0x14000fbb4  mov     qword ptr [rsp+50h+dwCreationFlags], r14
0x14000fbb9  mov     r9d, esi
0x14000fbbc  lea     r8, aCvdscallbackob_28; "CVdsCallbackObject::InitiateSecondAucti"...
0x14000fbc3  xor     edx, edx
0x14000fbc5  lea     ecx, [rsi+57h]
0x14000fbc8  call    cs:__imp_VdsTraceExW
0x14000fbce  jmp     loc_14000FCD3
0x14000fbd3  mov     [rbx+18h], rdi
0x14000fbd7  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000fbdb  inc     r15
0x14000fbde  cmp     [r14+r15*2], r12w
0x14000fbe3  jnz     short loc_14000FBDB
0x14000fbe5  lea     rdi, ds:2[r15*2]
0x14000fbed  call    cs:__imp_GetProcessHeap
0x14000fbf3  mov     rcx, rax
0x14000fbf6  mov     r8, rdi
0x14000fbf9  mov     edx, esi
0x14000fbfb  call    cs:__imp_VdsHeapAlloc
0x14000fc01  mov     rdx, rax
0x14000fc04  lea     rcx, [rbp+arg_8]
0x14000fc08  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x14000fc0d  mov     r10, [rbp+arg_8]
0x14000fc11  mov     r8, r14; unsigned __int16 *
0x14000fc14  test    r10, r10
0x14000fc17  jnz     short loc_14000FC2D
0x14000fc19  lea     rdx, aCvdscallbackob_20; "CVdsCallbackObject::InitiateSecondAucti"...
0x14000fc20  xor     ecx, ecx
0x14000fc22  call    cs:__imp_VdsTraceW
0x14000fc28  jmp     loc_14000FCD3
0x14000fc2d  lea     rdx, [r15+1]; unsigned __int64
0x14000fc31  mov     rcx, r10; unsigned __int16 *
0x14000fc34  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000fc39  mov     [rbx], r10
0x14000fc3c  lea     rax, [rbp+ThreadId]
0x14000fc40  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x14000fc45  mov     [rsp+50h+dwCreationFlags], r12d; dwCreationFlags
0x14000fc4a  mov     r9, rbx; lpParameter
0x14000fc4d  lea     r8, ?AuctionThread@@YAKPEAX@Z; lpStartAddress
0x14000fc54  xor     edx, edx; dwStackSize
0x14000fc56  xor     ecx, ecx; lpThreadAttributes
0x14000fc58  call    cs:__imp_CreateThread
0x14000fc5e  mov     rdx, rax
0x14000fc61  lea     rcx, [rbp+arg_18]
0x14000fc65  call    ??4?$CVdsHandleImpl@$0A@@@QEAAPEAXPEAX@Z; CVdsHandleImpl<0>::operator=(void *)
0x14000fc6a  cmp     [rbp+arg_18], r12
0x14000fc6e  jnz     short loc_14000FC8F
0x14000fc70  call    cs:__imp_GetLastError
0x14000fc76  mov     esi, eax
0x14000fc78  mov     r9d, eax
0x14000fc7b  mov     r8, r14
0x14000fc7e  lea     rdx, aCvdscallbackob_36; "CVdsCallbackObject::InitiateSecondAucti"...
0x14000fc85  xor     ecx, ecx
0x14000fc87  call    cs:__imp_VdsTraceW
0x14000fc8d  jmp     short loc_14000FCD3
0x14000fc8f  mov     esi, r12d
0x14000fc92  mov     [rbp+lpParameter], r12
0x14000fc96  mov     [rbp+arg_8], r12
0x14000fc9a  mov     [rbp+var_20], r12
0x14000fc9e  jmp     short loc_14000FCD3
0x14000fca0  mov     esi, 57h ; 'W'
0x14000fca5  lea     rax, aUnknown_0; "UNKNOWN"
0x14000fcac  test    r14, r14
0x14000fcaf  cmovz   r14, rax
0x14000fcb3  mov     [rsp+50h+lpThreadId], rdi
0x14000fcb8  mov     qword ptr [rsp+50h+dwCreationFlags], r14
0x14000fcbd  mov     r9d, esi
0x14000fcc0  lea     r8, aCvdscallbackob_25; "CVdsCallbackObject::InitiateSecondAucti"...
0x14000fcc7  xor     edx, edx
0x14000fcc9  lea     ecx, [rsi+8]
0x14000fccc  call    cs:__imp_VdsTraceExW
0x14000fcd2  nop
0x14000fcd3  lea     rcx, [rbp+var_18]
0x14000fcd7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000fcdd  nop
0x14000fcde  lea     rcx, [rbp+arg_18]
0x14000fce2  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x14000fce7  nop
0x14000fce8  lea     rcx, [rbp+var_20]
0x14000fcec  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000fcf1  nop
0x14000fcf2  lea     rcx, [rbp+arg_8]
0x14000fcf6  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000fcfb  nop
0x14000fcfc  lea     rcx, [rbp+lpParameter]
0x14000fd00  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000fd05  mov     eax, esi
0x14000fd07  add     rsp, 50h
0x14000fd0b  pop     r15
0x14000fd0d  pop     r14
0x14000fd0f  pop     r12
0x14000fd11  pop     rdi
0x14000fd12  pop     rsi
0x14000fd13  pop     rbx
0x14000fd14  pop     rbp
0x14000fd15  retn
```
