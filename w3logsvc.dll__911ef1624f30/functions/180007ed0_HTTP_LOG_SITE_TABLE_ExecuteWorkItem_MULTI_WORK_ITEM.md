# HTTP_LOG_SITE_TABLE::ExecuteWorkItem(MULTI_WORK_ITEM *)

- ea: `0x180007ed0`
- end: `0x180007fc0`
- name: `?ExecuteWorkItem@HTTP_LOG_SITE_TABLE@@UEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct MULTI_WORK_ITEM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007ed0`
- `0x1800086a4`
- `0x180008858`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fa1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007fa1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f65`
- `iisutil!PuDbgPrintError` at `0x180007f3f`
- `iisutil!PuDbgPrintError` at `0x180007f3f`

## string_xrefs

- `0x180007f38`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsitetable.cpp`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::ExecuteWorkItem(RTL_SRWLOCK *this, struct MULTI_WORK_ITEM *a2)
{
  unsigned int v2; // edi
  RTL_SRWLOCK *v4; // rsi
  volatile signed __int32 *Ptr; // rcx

  v2 = 0;
  switch ( *((_QWORD *)a2 + 2) )
  {
    case 1LL:
      HTTP_LOG_SITE_TABLE::Update((HTTP_LOG_SITE_TABLE *)this);
      break;
    case 2LL:
      v4 = this + 137;
      AcquireSRWLockExclusive(this + 137);
      Ptr = (volatile signed __int32 *)this[135].Ptr;
      if ( Ptr )
      {
        if ( _InterlockedExchangeAdd(Ptr + 168, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(PVOID, __int64))Ptr)((PVOID)Ptr, 1);
        this[135].Ptr = 0;
      }
      ReleaseSRWLockExclusive(v4);
      break;
    case 3LL:
      HTTP_LOG_SITE_TABLE::Iterate(
        (HTTP_LOG_SITE_TABLE *)this,
        (int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *))HTTP_LOG_SITE_TABLE::ReleaseWriter,
        1);
      break;
    default:
      v2 = -2147024809;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsitetable.cpp",
          405,
          "HTTP_LOG_SITE_TABLE::ExecuteWorkItem",
          -2147024809,
          "Executing work item on HTTP_LOG_SITE_TABLE failed\n");
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180007ed0  mov     [rsp+arg_0], rbx
0x180007ed5  mov     [rsp+arg_10], rsi
0x180007eda  push    rdi
0x180007edb  sub     rsp, 30h
0x180007edf  mov     rax, [rdx+10h]
0x180007ee3  xor     edi, edi
0x180007ee5  mov     rbx, rcx
0x180007ee8  sub     rax, 1
0x180007eec  jz      loc_180007FA9
0x180007ef2  sub     rax, 1
0x180007ef6  jz      short loc_180007F5B
0x180007ef8  cmp     rax, 1
0x180007efc  jz      short loc_180007F47
0x180007efe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007f05  mov     edi, 80070057h
0x180007f0a  jz      loc_180007FAE
0x180007f10  mov     rcx, cs:g_pDebug
0x180007f17  lea     rax, aExecutingWorkI_1; "Executing work item on HTTP_LOG_SITE_TA"...
0x180007f1e  mov     [rsp+38h+var_10], rax
0x180007f23  lea     r9, aHttpLogSiteTab_1; "HTTP_LOG_SITE_TABLE::ExecuteWorkItem"
0x180007f2a  mov     r8d, 195h
0x180007f30  mov     [rsp+38h+var_18], 80070057h
0x180007f38  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007f3f  call    cs:__imp_PuDbgPrintError
0x180007f45  jmp     short loc_180007FAE
0x180007f47  mov     r8d, 1; int
0x180007f4d  lea     rdx, ?ReleaseWriter@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z; int (*)(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *)
0x180007f54  call    ?Iterate@HTTP_LOG_SITE_TABLE@@AEAAJP6AJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@ZH@Z; HTTP_LOG_SITE_TABLE::Iterate(long (*)(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *),int)
0x180007f59  jmp     short loc_180007FAE
0x180007f5b  lea     rsi, [rcx+448h]
0x180007f62  mov     rcx, rsi; SRWLock
0x180007f65  call    cs:__imp_AcquireSRWLockExclusive
0x180007f6b  mov     rcx, [rbx+438h]
0x180007f72  test    rcx, rcx
0x180007f75  jz      short loc_180007F9E
0x180007f77  or      eax, 0FFFFFFFFh
0x180007f7a  lock xadd [rcx+2A0h], eax
0x180007f82  cmp     eax, 1
0x180007f85  jnz     short loc_180007F97
0x180007f87  mov     rax, [rcx]
0x180007f8a  mov     edx, 1
0x180007f8f  mov     rax, [rax]
0x180007f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f97  mov     [rbx+438h], rdi
0x180007f9e  mov     rcx, rsi; SRWLock
0x180007fa1  call    cs:__imp_ReleaseSRWLockExclusive
0x180007fa7  jmp     short loc_180007FAE
0x180007fa9  call    ?Update@HTTP_LOG_SITE_TABLE@@AEAAJXZ; HTTP_LOG_SITE_TABLE::Update(void)
0x180007fae  mov     rbx, [rsp+38h+arg_0]
0x180007fb3  mov     eax, edi
0x180007fb5  mov     rsi, [rsp+38h+arg_10]
0x180007fba  add     rsp, 30h
0x180007fbe  pop     rdi
0x180007fbf  retn
```
