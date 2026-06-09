# TdhpGetAllTraceEventInfo(IWbemServices *,ushort,_GUID *,_EVENT_DESCRIPTOR const *,ulong *,ulong *,_TRACE_EVENT_INFO * *,ulong *)

- ea: `0x180026f34`
- end: `0x1800270c6`
- name: `?TdhpGetAllTraceEventInfo@@YAKPEAUIWbemServices@@GPEAU_GUID@@PEBU_EVENT_DESCRIPTOR@@PEAK3PEAPEAU_TRACE_EVENT_INFO@@3@Z`
- size: `402`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16, struct _GUID *, const struct _EVENT_DESCRIPTOR *, unsigned int *, unsigned int *, struct _TRACE_EVENT_INFO **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800240c0`

## callees

- `0x1800064d0`
- `0x1800076e0`
- `0x180018198`
- `0x180026d00`
- `0x180026f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026f85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002704f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026f85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002704f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002709c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026fa4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002709c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026fad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026fad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027046`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027046`

## pseudocode

```c
__int64 __fastcall TdhpGetAllTraceEventInfo(
        struct IWbemServices *a1,
        unsigned __int16 a2,
        struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _TRACE_EVENT_INFO **a7,
        unsigned int *a8)
{
  __int64 Version; // rbp
  unsigned int MatchClassFromCache; // edi
  unsigned int v10; // r12d
  RTL_SRWLOCK *v14; // rax
  RTL_SRWLOCK *v15; // rbx
  unsigned int TraceEventInfoArray; // eax
  struct _TRACE_EVENT_INFO **v18; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v19; // [rsp+A8h] [rbp+10h] BYREF
  int v20; // [rsp+B8h] [rbp+20h] BYREF

  Version = a4->Version;
  MatchClassFromCache = 0;
  v10 = a2;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  v14 = (RTL_SRWLOCK *)TdhpCacheLockEntry(0, a3);
  v15 = v14;
  if ( !v14 )
    return 8;
  AcquireSRWLockShared(v14);
  if ( v15[3 * Version + 3].Ptr )
    goto LABEL_10;
  ReleaseSRWLockShared(v15);
  AcquireSRWLockExclusive(v15);
  if ( !v15[3 * Version + 3].Ptr )
  {
    TraceEventInfoArray = TdhpAllocAndGetTraceEventInfoArray(a1, 0, a3, Version, (v10 >> 8) & 1, &v19, &v18, &v20, 0, 0);
    MatchClassFromCache = TraceEventInfoArray;
    if ( TraceEventInfoArray )
    {
      if ( TraceEventInfoArray + 1073217792 <= 1 )
        MatchClassFromCache = 1168;
    }
    else
    {
      v15[3 * Version + 3].Ptr = v18;
      LODWORD(v15[3 * Version + 4].Ptr) = v19;
      HIDWORD(v15[3 * Version + 4].Ptr) = v20;
    }
  }
  ReleaseSRWLockExclusive(v15);
  AcquireSRWLockShared(v15);
  if ( !MatchClassFromCache )
LABEL_10:
    MatchClassFromCache = TdhpFindMatchClassFromCache(v10, (struct TDH_MOF_INFO *)v15, a4, a5, a6, a7, a8);
  ReleaseSRWLockShared(v15);
  TdhpCacheFreeEntry(0, v15);
  return MatchClassFromCache;
}

```

## disassembly

```asm
0x180026f34  mov     rax, rsp
0x180026f37  mov     [rax+8], rbx
0x180026f3b  push    rbp
0x180026f3c  push    rsi
0x180026f3d  push    rdi
0x180026f3e  push    r12
0x180026f40  push    r13
0x180026f42  push    r14
0x180026f44  push    r15
0x180026f46  sub     rsp, 60h
0x180026f4a  movzx   ebp, byte ptr [r9+2]
0x180026f4f  xor     edi, edi
0x180026f51  movzx   r12d, dx
0x180026f55  mov     r13, rcx
0x180026f58  mov     rdx, r8
0x180026f5b  mov     [rax+10h], edi
0x180026f5e  xor     ecx, ecx
0x180026f60  mov     [rax+20h], edi
0x180026f63  mov     [rax-48h], rdi
0x180026f67  mov     r14, r9
0x180026f6a  mov     r15, r8
0x180026f6d  call    TdhpCacheLockEntry
0x180026f72  mov     rbx, rax
0x180026f75  test    rax, rax
0x180026f78  jnz     short loc_180026F82
0x180026f7a  lea     eax, [rdi+8]
0x180026f7d  jmp     loc_1800270AE
0x180026f82  mov     rcx, rbx; SRWLock
0x180026f85  call    cs:__imp_AcquireSRWLockShared
0x180026f8b  lea     rsi, ds:0[rbp*2]
0x180026f93  add     rsi, rbp
0x180026f96  cmp     [rbx+rsi*8+18h], rdi
0x180026f9b  jnz     loc_180027059
0x180026fa1  mov     rcx, rbx; SRWLock
0x180026fa4  call    cs:__imp_ReleaseSRWLockShared
0x180026faa  mov     rcx, rbx; SRWLock
0x180026fad  call    cs:__imp_AcquireSRWLockExclusive
0x180026fb3  xor     ecx, ecx
0x180026fb5  cmp     [rbx+rsi*8+18h], rcx
0x180026fba  jnz     loc_180027043
0x180026fc0  mov     [rsp+98h+var_50], rcx
0x180026fc5  mov     eax, r12d
0x180026fc8  mov     [rsp+98h+var_58], rcx
0x180026fcd  mov     r9b, bpl
0x180026fd0  lea     rcx, [rsp+98h+arg_18]
0x180026fd8  shr     eax, 8
0x180026fdb  mov     [rsp+98h+var_60], rcx
0x180026fe0  and     eax, 1
0x180026fe3  lea     rcx, [rsp+98h+var_48]
0x180026fe8  mov     r8, r15
0x180026feb  mov     [rsp+98h+var_68], rcx
0x180026ff0  xor     edx, edx
0x180026ff2  lea     rcx, [rsp+98h+arg_8]
0x180026ffa  mov     [rsp+98h+var_70], rcx
0x180026fff  mov     rcx, r13
0x180027002  mov     dword ptr [rsp+98h+var_78], eax
0x180027006  call    TdhpAllocAndGetTraceEventInfoArray
0x18002700b  mov     edi, eax
0x18002700d  test    eax, eax
0x18002700f  jnz     short loc_180027033
0x180027011  mov     rcx, [rsp+98h+var_48]
0x180027016  mov     [rbx+rsi*8+18h], rcx
0x18002701b  mov     ecx, [rsp+98h+arg_8]
0x180027022  mov     [rbx+rsi*8+20h], ecx
0x180027026  mov     ecx, [rsp+98h+arg_18]
0x18002702d  mov     [rbx+rsi*8+24h], ecx
0x180027031  jmp     short loc_180027043
0x180027033  add     eax, 3FF80100h
0x180027038  mov     ecx, 490h
0x18002703d  cmp     eax, 1
0x180027040  cmovbe  edi, ecx
0x180027043  mov     rcx, rbx; SRWLock
0x180027046  call    cs:__imp_ReleaseSRWLockExclusive
0x18002704c  mov     rcx, rbx; SRWLock
0x18002704f  call    cs:__imp_AcquireSRWLockShared
0x180027055  test    edi, edi
0x180027057  jnz     short loc_180027099
0x180027059  mov     rax, [rsp+98h+arg_38]
0x180027061  mov     r8, r14; struct _EVENT_DESCRIPTOR *
0x180027064  mov     r9, [rsp+98h+arg_20]; unsigned int *
0x18002706c  mov     rdx, rbx; struct TDH_MOF_INFO *
0x18002706f  mov     [rsp+98h+var_68], rax; unsigned int *
0x180027074  movzx   ecx, r12w; unsigned __int16
0x180027078  mov     rax, [rsp+98h+arg_30]
0x180027080  mov     [rsp+98h+var_70], rax; struct _TRACE_EVENT_INFO **
0x180027085  mov     rax, [rsp+98h+arg_28]
0x18002708d  mov     [rsp+98h+var_78], rax; unsigned int *
0x180027092  call    ?TdhpFindMatchClassFromCache@@YAKGPEAUTDH_MOF_INFO@@PEBU_EVENT_DESCRIPTOR@@PEAK2PEAPEAU_TRACE_EVENT_INFO@@2@Z; TdhpFindMatchClassFromCache(ushort,TDH_MOF_INFO *,_EVENT_DESCRIPTOR const *,ulong *,ulong *,_TRACE_EVENT_INFO * *,ulong *)
0x180027097  mov     edi, eax
0x180027099  mov     rcx, rbx; SRWLock
0x18002709c  call    cs:__imp_ReleaseSRWLockShared
0x1800270a2  mov     rdx, rbx
0x1800270a5  xor     ecx, ecx
0x1800270a7  call    TdhpCacheFreeEntry
0x1800270ac  mov     eax, edi
0x1800270ae  mov     rbx, [rsp+98h+arg_0]
0x1800270b6  add     rsp, 60h
0x1800270ba  pop     r15
0x1800270bc  pop     r14
0x1800270be  pop     r13
0x1800270c0  pop     r12
0x1800270c2  pop     rdi
0x1800270c3  pop     rsi
0x1800270c4  pop     rbp
0x1800270c5  retn
```
