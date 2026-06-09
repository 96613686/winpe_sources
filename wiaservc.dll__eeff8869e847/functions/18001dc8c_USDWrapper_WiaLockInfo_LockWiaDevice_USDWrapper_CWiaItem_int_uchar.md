# USDWrapper::WiaLockInfo::LockWiaDevice(USDWrapper *,CWiaItem *,int *,uchar *)

- ea: `0x18001dc8c`
- end: `0x18001ddfc`
- name: `?LockWiaDevice@WiaLockInfo@USDWrapper@@QEAAJPEAV2@PEAVCWiaItem@@PEAHPEAE@Z`
- size: `368`
- prototype: `__int64 __fastcall(USDWrapper::WiaLockInfo *__hidden this, struct USDWrapper *, struct CWiaItem *, int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001db34`

## callees

- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18001dc8c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001dde7`
- `KERNEL32!LeaveCriticalSection` at `0x18001dde7`
- `KERNEL32!GetCurrentThreadId` at `0x18001dcc0`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd2a`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd5f`
- `KERNEL32!GetCurrentThreadId` at `0x18001ddd6`
- `KERNEL32!GetCurrentThreadId` at `0x18001dcc0`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd2a`
- `KERNEL32!GetCurrentThreadId` at `0x18001dd5f`
- `KERNEL32!GetCurrentThreadId` at `0x18001ddd6`

## string_xrefs

- `0x18001dccb`: `Device is already locked by this thread`
- `0x18001dcf5`: `Device is already locked by this thread`
- `0x18001dd34`: `Device is already locked by another (%d) thread, failing this (%d) thread!`
- `0x18001dd69`: `Device is already locked by another (%d) thread, failing this (%d) thread!`

## pseudocode

```c
__int64 __fastcall USDWrapper::WiaLockInfo::LockWiaDevice(
        USDWrapper::WiaLockInfo *this,
        struct USDWrapper *a2,
        struct CWiaItem *a3,
        int *a4,
        unsigned __int8 *a5)
{
  int v9; // ebp
  char *v10; // rbx
  void *v11; // rdx
  void **lpMem; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  int v15; // ebx
  DWORD CurrentThreadId; // eax
  char *v17; // rbx
  void *v18; // rdx
  DWORD v19; // eax
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v25; // [rsp+70h] [rbp+8h] BYREF

  *a4 = 0;
  v9 = CRIT_SECT::Lock((USDWrapper::WiaLockInfo *)((char *)this + 8));
  if ( *(_DWORD *)this )
  {
    if ( GetCurrentThreadId() == *((_DWORD *)this + 1) )
    {
      v10 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Device is already locked by this thread");
      WriteDbgTraceInfoWI("USDWrapper::WiaLockInfo::LockWiaDevice", v10);
      WiaTrcLib::Free((WiaTrcLib *)v10, v11);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Device is already locked by this thread");
      WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"USDWrapper::WiaLockInfo::LockWiaDevice", 4, lpMem);
      v15 = 0;
      *a4 = 1;
    }
    else
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = (char *)WiaTrace_TraceLogWithSubComp(
                      0,
                      "Device is already locked by another (%d) thread, failing this (%d) thread!",
                      *((_DWORD *)this + 1),
                      CurrentThreadId);
      WriteDbgTraceWarningWI("USDWrapper::WiaLockInfo::LockWiaDevice", v17);
      WiaTrcLib::Free((WiaTrcLib *)v17, v18);
      v19 = GetCurrentThreadId();
      v20 = (void **)WiaTrace_TraceWithSubComp(
                       0,
                       "Device is already locked by another (%d) thread, failing this (%d) thread!",
                       *((_DWORD *)this + 1),
                       v19);
      WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"USDWrapper::WiaLockInfo::LockWiaDevice", 2, v20);
      v15 = -2145320954;
    }
  }
  else
  {
    v23 = *(_QWORD *)a2;
    v25 = 0;
    v15 = (*(__int64 (__fastcall **)(struct USDWrapper *, struct CWiaItem *, unsigned __int8 *, _QWORD, int *))(v23 + 408))(
            a2,
            a3,
            a5,
            0,
            &v25);
    if ( v15 >= 0 )
    {
      *(_DWORD *)this = 1;
      *((_DWORD *)this + 1) = GetCurrentThreadId();
    }
  }
  if ( v9 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001dc8c  push    rbx
0x18001dc8e  push    rbp
0x18001dc8f  push    rsi
0x18001dc90  push    rdi
0x18001dc91  push    r14
0x18001dc93  push    r15
0x18001dc95  sub     rsp, 38h
0x18001dc99  mov     rdi, rcx
0x18001dc9c  mov     dword ptr [r9], 0
0x18001dca3  add     rcx, 8; this
0x18001dca7  mov     r14, r9
0x18001dcaa  mov     r15, r8
0x18001dcad  mov     rbx, rdx
0x18001dcb0  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18001dcb5  cmp     dword ptr [rdi], 0
0x18001dcb8  mov     ebp, eax
0x18001dcba  jz      loc_18001DD98
0x18001dcc0  call    cs:__imp_GetCurrentThreadId
0x18001dcc6  cmp     eax, [rdi+4]
0x18001dcc9  jnz     short loc_18001DD2A
0x18001dccb  lea     r8, aDeviceIsAlread_0; "Device is already locked by this thread"
0x18001dcd2  xor     edx, edx
0x18001dcd4  xor     ecx, ecx
0x18001dcd6  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001dcdb  mov     rdx, rax; char *
0x18001dcde  lea     rcx, aUsdwrapperWial; "USDWrapper::WiaLockInfo::LockWiaDevice"
0x18001dce5  mov     rbx, rax
0x18001dce8  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001dced  mov     rcx, rbx; this
0x18001dcf0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001dcf5  lea     r8, aDeviceIsAlread_0; "Device is already locked by this thread"
0x18001dcfc  xor     edx, edx
0x18001dcfe  xor     ecx, ecx
0x18001dd00  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001dd05  mov     r9d, 4; int
0x18001dd0b  mov     [rsp+68h+lpMem], rax; lpMem
0x18001dd10  lea     r8, aUsdwrapperWial; "USDWrapper::WiaLockInfo::LockWiaDevice"
0x18001dd17  call    WiaTrace_ProcessTrace_Ex
0x18001dd1c  xor     ebx, ebx
0x18001dd1e  mov     dword ptr [r14], 1
0x18001dd25  jmp     loc_18001DDDF
0x18001dd2a  call    cs:__imp_GetCurrentThreadId
0x18001dd30  mov     r8d, [rdi+4]
0x18001dd34  lea     rdx, aDeviceIsAlread; "Device is already locked by another (%d"...
0x18001dd3b  mov     r9d, eax
0x18001dd3e  xor     ecx, ecx
0x18001dd40  call    WiaTrace_TraceLogWithSubComp
0x18001dd45  mov     rdx, rax; char *
0x18001dd48  lea     rcx, aUsdwrapperWial; "USDWrapper::WiaLockInfo::LockWiaDevice"
0x18001dd4f  mov     rbx, rax
0x18001dd52  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001dd57  mov     rcx, rbx; this
0x18001dd5a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001dd5f  call    cs:__imp_GetCurrentThreadId
0x18001dd65  mov     r8d, [rdi+4]
0x18001dd69  lea     rdx, aDeviceIsAlread; "Device is already locked by another (%d"...
0x18001dd70  mov     r9d, eax
0x18001dd73  xor     ecx, ecx
0x18001dd75  call    WiaTrace_TraceWithSubComp
0x18001dd7a  mov     r9d, 2; int
0x18001dd80  mov     [rsp+68h+lpMem], rax; lpMem
0x18001dd85  lea     r8, aUsdwrapperWial; "USDWrapper::WiaLockInfo::LockWiaDevice"
0x18001dd8c  call    WiaTrace_ProcessTrace_Ex
0x18001dd91  mov     ebx, 80210006h
0x18001dd96  jmp     short loc_18001DDDF
0x18001dd98  mov     rax, [rbx]
0x18001dd9b  lea     rcx, [rsp+68h+arg_0]
0x18001dda0  mov     r8, [rsp+68h+arg_20]
0x18001dda8  xor     r9d, r9d
0x18001ddab  mov     [rsp+68h+lpMem], rcx
0x18001ddb0  mov     rdx, r15
0x18001ddb3  mov     rcx, rbx
0x18001ddb6  mov     [rsp+68h+arg_0], 0
0x18001ddbe  mov     rax, [rax+198h]
0x18001ddc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddca  mov     ebx, eax
0x18001ddcc  test    eax, eax
0x18001ddce  js      short loc_18001DDDF
0x18001ddd0  mov     dword ptr [rdi], 1
0x18001ddd6  call    cs:__imp_GetCurrentThreadId
0x18001dddc  mov     [rdi+4], eax
0x18001dddf  test    ebp, ebp
0x18001dde1  jz      short loc_18001DDED
0x18001dde3  lea     rcx, [rdi+8]; lpCriticalSection
0x18001dde7  call    cs:__imp_LeaveCriticalSection
0x18001dded  mov     eax, ebx
0x18001ddef  add     rsp, 38h
0x18001ddf3  pop     r15
0x18001ddf5  pop     r14
0x18001ddf7  pop     rdi
0x18001ddf8  pop     rsi
0x18001ddf9  pop     rbp
0x18001ddfa  pop     rbx
0x18001ddfb  retn
```
