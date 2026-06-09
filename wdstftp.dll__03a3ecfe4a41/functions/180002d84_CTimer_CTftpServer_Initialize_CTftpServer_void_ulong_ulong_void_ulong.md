# CTimer<CTftpServer>::Initialize(CTftpServer *,void *,ulong,ulong,void *,ulong)

- ea: `0x180002d84`
- end: `0x180002e4a`
- name: `?Initialize@?$CTimer@VCTftpServer@@@@QEAAKPEAVCTftpServer@@PEAXKK1K@Z`
- size: `198`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012e0`

## callees

- `0x180002d84`
- `0x180002f8c`
- `0x180002ff4`
- `0x18003c514`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180002de3`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002de3`
- `KERNEL32!GetLastError` at `0x180002df3`
- `KERNEL32!GetLastError` at `0x180002df3`

## pseudocode

```c
__int64 __fastcall CTimer<CTftpServer>::Initialize(__int64 Parameter, __int64 a2)
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
          CTimer<CTftpServer>::_TimerCallback,
          (PVOID)Parameter,
          0x7D0u,
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
0x180002d84  mov     rax, rsp
0x180002d87  mov     [rax+8], rbx
0x180002d8b  mov     [rax+10h], rsi
0x180002d8f  push    rdi
0x180002d90  sub     rsp, 50h
0x180002d94  mov     rdi, rcx
0x180002d97  mov     [rax-18h], rcx
0x180002d9b  xor     esi, esi
0x180002d9d  lea     rcx, [rax-18h]
0x180002da1  and     [rax-10h], esi
0x180002da4  mov     rbx, rdx
0x180002da7  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180002dac  and     [rdi+10h], rsi
0x180002db0  lea     rcx, [rdi+18h]; phNewTimer
0x180002db4  and     [rdi+30h], rsi
0x180002db8  lea     r8, ?_TimerCallback@?$CTimer@VCTftpServer@@@@SAXPEAXE@Z; Callback
0x180002dbf  and     [rdi+28h], esi
0x180002dc2  mov     r9, rdi; Parameter
0x180002dc5  mov     [rsp+58h+Flags], 1; Flags
0x180002dcd  xor     edx, edx; TimerQueue
0x180002dcf  mov     [rsp+58h+Period], 0FFFFFFFEh; Period
0x180002dd7  mov     [rsp+58h+DueTime], 7D0h; int
0x180002ddf  mov     [rdi+20h], rbx
0x180002de3  call    cs:__imp_CreateTimerQueueTimer
0x180002dea  nop     dword ptr [rax+rax+00h]
0x180002def  test    eax, eax
0x180002df1  jnz     short loc_180002E01
0x180002df3  call    cs:__imp_GetLastError
0x180002dfa  nop     dword ptr [rax+rax+00h]
0x180002dff  mov     esi, eax
0x180002e01  mov     ecx, [rsp+58h+var_10]
0x180002e05  test    ecx, ecx
0x180002e07  jz      short loc_180002E38
0x180002e09  lea     rcx, [rsp+58h+var_18]
0x180002e0e  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x180002e13  mov     ecx, [rsp+58h+var_10]
0x180002e17  test    ecx, ecx
0x180002e19  jz      short loc_180002E38
0x180002e1b  and     [rsp+58h+DueTime], 0
0x180002e20  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180002e27  mov     edx, 16Ah; unsigned int
0x180002e2c  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x180002e33  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180002e38  mov     rbx, [rsp+58h+arg_0]
0x180002e3d  mov     eax, esi
0x180002e3f  mov     rsi, [rsp+58h+arg_8]
0x180002e44  add     rsp, 50h
0x180002e48  pop     rdi
0x180002e49  retn
```
