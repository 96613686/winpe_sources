# CTimer<CTftpSession>::Initialize(CTftpSession *,void *,ulong,ulong,void *,ulong)

- ea: `0x180008310`
- end: `0x1800083d3`
- name: `?Initialize@?$CTimer@VCTftpSession@@@@QEAAKPEAVCTftpSession@@PEAXKK1K@Z`
- size: `195`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005f7c`

## callees

- `0x180002f8c`
- `0x180002ff4`
- `0x180008310`
- `0x18003c514`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18000836c`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000836c`
- `KERNEL32!GetLastError` at `0x18000837c`
- `KERNEL32!GetLastError` at `0x18000837c`

## pseudocode

```c
__int64 __fastcall CTimer<CTftpSession>::Initialize(__int64 Parameter, __int64 a2)
{
  DWORD LastError; // esi
  int v5; // r9d
  __int64 v7; // [rsp+40h] [rbp-18h] BYREF
  int v8; // [rsp+48h] [rbp-10h]

  v7 = Parameter;
  LastError = 0;
  v8 = 0;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(&v7);
  *(_QWORD *)(Parameter + 16) = 0;
  *(_QWORD *)(Parameter + 48) = 0;
  *(_DWORD *)(Parameter + 40) = 0;
  *(_QWORD *)(Parameter + 32) = a2;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)(Parameter + 24),
          0,
          CTimer<CTftpSession>::_TimerCallback,
          (PVOID)Parameter,
          0xFFFFFFFE,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  if ( v8 )
  {
    CAutoTypeLock<CSpinLock>::Unlock((__int64)&v7);
    if ( v8 )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", v5, 0);
  }
  return LastError;
}

```

## disassembly

```asm
0x180008310  mov     rax, rsp
0x180008313  mov     [rax+8], rbx
0x180008317  mov     [rax+10h], rsi
0x18000831b  push    rdi
0x18000831c  sub     rsp, 50h
0x180008320  mov     rdi, rcx
0x180008323  mov     [rax-18h], rcx
0x180008327  xor     esi, esi
0x180008329  lea     rcx, [rax-18h]
0x18000832d  and     [rax-10h], esi
0x180008330  mov     rbx, rdx
0x180008333  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180008338  and     [rdi+10h], rsi
0x18000833c  lea     rcx, [rdi+18h]; phNewTimer
0x180008340  and     [rdi+30h], rsi
0x180008344  lea     r8, ?_TimerCallback@?$CTimer@VCTftpSession@@@@SAXPEAXE@Z; Callback
0x18000834b  and     [rdi+28h], esi
0x18000834e  mov     eax, 0FFFFFFFEh
0x180008353  mov     [rsp+58h+Flags], 1; Flags
0x18000835b  mov     r9, rdi; Parameter
0x18000835e  mov     [rsp+58h+Period], eax; Period
0x180008362  xor     edx, edx; TimerQueue
0x180008364  mov     [rsp+58h+DueTime], eax; int
0x180008368  mov     [rdi+20h], rbx
0x18000836c  call    cs:__imp_CreateTimerQueueTimer
0x180008373  nop     dword ptr [rax+rax+00h]
0x180008378  test    eax, eax
0x18000837a  jnz     short loc_18000838A
0x18000837c  call    cs:__imp_GetLastError
0x180008383  nop     dword ptr [rax+rax+00h]
0x180008388  mov     esi, eax
0x18000838a  mov     ecx, [rsp+58h+var_10]
0x18000838e  test    ecx, ecx
0x180008390  jz      short loc_1800083C1
0x180008392  lea     rcx, [rsp+58h+var_18]
0x180008397  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000839c  mov     ecx, [rsp+58h+var_10]
0x1800083a0  test    ecx, ecx
0x1800083a2  jz      short loc_1800083C1
0x1800083a4  and     [rsp+58h+DueTime], 0
0x1800083a9  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x1800083b0  mov     edx, 16Ah; unsigned int
0x1800083b5  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x1800083bc  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800083c1  mov     rbx, [rsp+58h+arg_0]
0x1800083c6  mov     eax, esi
0x1800083c8  mov     rsi, [rsp+58h+arg_8]
0x1800083cd  add     rsp, 50h
0x1800083d1  pop     rdi
0x1800083d2  retn
```
