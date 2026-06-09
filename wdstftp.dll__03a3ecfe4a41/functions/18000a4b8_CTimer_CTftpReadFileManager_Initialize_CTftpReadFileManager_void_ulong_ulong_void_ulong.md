# CTimer<CTftpReadFileManager>::Initialize(CTftpReadFileManager *,void *,ulong,ulong,void *,ulong)

- ea: `0x18000a4b8`
- end: `0x18000a589`
- name: `?Initialize@?$CTimer@VCTftpReadFileManager@@@@QEAAKPEAVCTftpReadFileManager@@PEAXKK1K@Z`
- size: `209`
- prototype: `__int64 __usercall@<rax>(PVOID Parameter@<rcx>, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800093e0`

## callees

- `0x180002f8c`
- `0x180002ff4`
- `0x18000a4b8`
- `0x18003c514`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18000a51d`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000a51d`
- `KERNEL32!GetLastError` at `0x18000a52d`
- `KERNEL32!GetLastError` at `0x18000a52d`

## pseudocode

```c
__int64 __fastcall CTimer<CTftpReadFileManager>::Initialize(
        __int64 Parameter,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        DWORD Period)
{
  DWORD LastError; // ebp
  int v9; // r9d
  __int64 v11; // [rsp+40h] [rbp-18h] BYREF
  int v12; // [rsp+48h] [rbp-10h]

  v11 = Parameter;
  LastError = 0;
  v12 = 0;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(&v11);
  *(_QWORD *)(Parameter + 16) = 0;
  *(_QWORD *)(Parameter + 48) = 0;
  *(_DWORD *)(Parameter + 40) = 0;
  *(_QWORD *)(Parameter + 32) = a2;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)(Parameter + 24),
          0,
          CTimer<CTftpReadFileManager>::_TimerCallback,
          (PVOID)Parameter,
          a4,
          Period,
          1u) )
    LastError = GetLastError();
  if ( v12 )
  {
    CAutoTypeLock<CSpinLock>::Unlock((__int64)&v11);
    if ( v12 )
      WdsAssert("internal\\onecorebase\\private\\inc\\eco\\wds\\locks.h", 0x16Au, "m_uLockCount == 0", v9, 0);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a4b8  mov     rax, rsp
0x18000a4bb  mov     [rax+8], rbx
0x18000a4bf  mov     [rax+10h], rbp
0x18000a4c3  mov     [rax+18h], rsi
0x18000a4c7  push    rdi
0x18000a4c8  sub     rsp, 50h
0x18000a4cc  mov     rdi, rcx
0x18000a4cf  mov     [rax-18h], rcx
0x18000a4d3  xor     ebp, ebp
0x18000a4d5  lea     rcx, [rax-18h]
0x18000a4d9  and     [rax-10h], ebp
0x18000a4dc  mov     esi, r9d
0x18000a4df  mov     rbx, rdx
0x18000a4e2  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x18000a4e7  mov     eax, [rsp+58h+arg_20]
0x18000a4ee  lea     rcx, [rdi+18h]; phNewTimer
0x18000a4f2  and     [rdi+10h], rbp
0x18000a4f6  lea     r8, ?_TimerCallback@?$CTimer@VCTftpReadFileManager@@@@SAXPEAXE@Z; Callback
0x18000a4fd  and     [rdi+30h], rbp
0x18000a501  mov     r9, rdi; Parameter
0x18000a504  and     [rdi+28h], ebp
0x18000a507  xor     edx, edx; TimerQueue
0x18000a509  mov     [rsp+58h+Flags], 1; Flags
0x18000a511  mov     [rsp+58h+Period], eax; Period
0x18000a515  mov     [rsp+58h+DueTime], esi; int
0x18000a519  mov     [rdi+20h], rbx
0x18000a51d  call    cs:__imp_CreateTimerQueueTimer
0x18000a524  nop     dword ptr [rax+rax+00h]
0x18000a529  test    eax, eax
0x18000a52b  jnz     short loc_18000A53B
0x18000a52d  call    cs:__imp_GetLastError
0x18000a534  nop     dword ptr [rax+rax+00h]
0x18000a539  mov     ebp, eax
0x18000a53b  mov     ecx, [rsp+58h+var_10]
0x18000a53f  test    ecx, ecx
0x18000a541  jz      short loc_18000A572
0x18000a543  lea     rcx, [rsp+58h+var_18]
0x18000a548  call    ?Unlock@?$CAutoTypeLock@VCSpinLock@@@@QEAAXXZ; CAutoTypeLock<CSpinLock>::Unlock(void)
0x18000a54d  mov     ecx, [rsp+58h+var_10]
0x18000a551  test    ecx, ecx
0x18000a553  jz      short loc_18000A572
0x18000a555  and     [rsp+58h+DueTime], 0
0x18000a55a  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000a561  mov     edx, 16Ah; unsigned int
0x18000a566  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x18000a56d  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000a572  mov     rbx, [rsp+58h+arg_0]
0x18000a577  mov     eax, ebp
0x18000a579  mov     rbp, [rsp+58h+arg_8]
0x18000a57e  mov     rsi, [rsp+58h+arg_10]
0x18000a583  add     rsp, 50h
0x18000a587  pop     rdi
0x18000a588  retn
```
