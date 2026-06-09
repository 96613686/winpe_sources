# wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000d038`
- end: `0x18000d0d2`
- name: `?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000acf4`
- `0x18000c3d0`
- `0x18000c830`
- `0x18000cbb0`
- `0x18000d1cc`

## callees

- `0x18000d038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d068`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d068`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d0b9`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-18h] BYREF
  PSRWLOCK v9; // [rsp+28h] [rbp-10h] BYREF

  LODWORD(SRWLock) = 0;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    p_SRWLock = &v9;
    v6 = 1;
  }
  else
  {
    p_SRWLock = &SRWLock;
    v6 = 2;
    v4 = 0;
  }
  *a2 = v4;
  *p_SRWLock = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  if ( (v6 & 1) != 0 && v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x18000d038  mov     [rsp+arg_10], rbx
0x18000d03d  mov     [rsp+arg_18], rsi
0x18000d042  push    rdi
0x18000d043  sub     rsp, 30h
0x18000d047  mov     dword ptr [rsp+38h+SRWLock], 0
0x18000d04f  mov     rsi, rdx
0x18000d052  mov     rbx, [rcx+118h]
0x18000d059  test    rbx, rbx
0x18000d05c  jz      short loc_18000D07A
0x18000d05e  add     rbx, 108h
0x18000d065  mov     rcx, rbx; SRWLock
0x18000d068  call    cs:__imp_AcquireSRWLockExclusive
0x18000d06e  lea     rax, [rsp+38h+var_10]
0x18000d073  mov     edi, 1
0x18000d078  jmp     short loc_18000D086
0x18000d07a  lea     rax, [rsp+38h+SRWLock]
0x18000d07f  mov     edi, 2
0x18000d084  xor     ebx, ebx
0x18000d086  mov     [rsi], rbx
0x18000d089  mov     qword ptr [rax], 0
0x18000d090  test    dil, 2
0x18000d094  jz      short loc_18000D0A9
0x18000d096  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18000d09b  and     edi, 0FFFFFFFDh
0x18000d09e  test    rcx, rcx
0x18000d0a1  jz      short loc_18000D0A9
0x18000d0a3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d0a9  test    dil, 1
0x18000d0ad  jz      short loc_18000D0BF
0x18000d0af  mov     rcx, [rsp+38h+var_10]; SRWLock
0x18000d0b4  test    rcx, rcx
0x18000d0b7  jz      short loc_18000D0BF
0x18000d0b9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d0bf  mov     rbx, [rsp+38h+arg_10]
0x18000d0c4  mov     rax, rsi
0x18000d0c7  mov     rsi, [rsp+38h+arg_18]
0x18000d0cc  add     rsp, 30h
0x18000d0d0  pop     rdi
0x18000d0d1  retn
```
