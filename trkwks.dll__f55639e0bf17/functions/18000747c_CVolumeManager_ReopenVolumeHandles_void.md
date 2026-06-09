# CVolumeManager::ReopenVolumeHandles(void)

- ea: `0x18000747c`
- end: `0x180007564`
- name: `?ReopenVolumeHandles@CVolumeManager@@QEAAHXZ`
- size: `232`
- prototype: `__int64 __fastcall(CVolumeManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000c300`
- `0x18000c6b0`

## callees

- `0x180006600`
- `0x1800066c0`
- `0x18000747c`
- `0x18000756c`
- `0x18000d2f8`

## pseudocode

```c
__int64 __fastcall CVolumeManager::ReopenVolumeHandles(CVolumeManager *this)
{
  volatile signed __int32 *v1; // rsi
  __int64 v2; // r8
  unsigned int v3; // edi
  _BYTE *v4; // r14
  CVolume *NextVolume; // rax
  PLogFileNotify *v6; // rbx
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-28h]

  v1 = (volatile signed __int32 *)((char *)this + 160);
  if ( !(unsigned int)BeginSingleInstanceTask((int *)this + 40) )
    return 0;
  v3 = 1;
  v8 = 0;
  v9 = 0;
  v4 = (_BYTE *)(v2 + 20);
  if ( (*(_BYTE *)(v2 + 20) & 2) != 0 || (*v4 & 1) != 0 )
  {
    *(_QWORD *)&v8 = v2 + 200;
    *((_QWORD *)&v8 + 1) = v2 + 208;
  }
  while ( 1 )
  {
    NextVolume = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v8);
    v6 = NextVolume;
    if ( !NextVolume )
      break;
    v3 &= -((unsigned int)CVolume::ReopenVolumeHandles(NextVolume) != 0);
    PLogFileNotify::Release(v6);
  }
  *(_DWORD *)v4 |= 2u;
  _InterlockedDecrement(v1);
  return v3;
}

```

## disassembly

```asm
0x18000747c  mov     [rsp+arg_18], rbx
0x180007481  push    rsi
0x180007482  push    rdi
0x180007483  push    r14
0x180007485  sub     rsp, 50h
0x180007489  mov     r8, rcx
0x18000748c  lea     rsi, [rcx+0A0h]
0x180007493  mov     [rsp+68h+arg_8], rsi
0x180007498  mov     rcx, rsi; int *
0x18000749b  call    ?BeginSingleInstanceTask@@YAHPEAJ@Z; BeginSingleInstanceTask(long *)
0x1800074a0  test    eax, eax
0x1800074a2  jz      loc_180007556
0x1800074a8  mov     edi, 1
0x1800074ad  xorps   xmm0, xmm0
0x1800074b0  movdqu  [rsp+68h+var_38], xmm0
0x1800074b6  mov     [rsp+68h+var_28], 0
0x1800074bf  lea     r14, [r8+14h]
0x1800074c3  mov     [rsp+68h+arg_10], r14
0x1800074cb  test    byte ptr [r14], 2
0x1800074cf  jz      loc_18000755A
0x1800074d5  lea     rax, [r8+0C8h]
0x1800074dc  mov     qword ptr [rsp+68h+var_38], rax
0x1800074e1  lea     rax, [r8+0D0h]
0x1800074e8  mov     qword ptr [rsp+68h+var_38+8], rax
0x1800074ed  lea     rcx, [rsp+68h+var_38]; this
0x1800074f2  call    ?GetNextVolume@CVolumeEnumerator@@QEAAPEAVCVolume@@XZ; CVolumeEnumerator::GetNextVolume(void)
0x1800074f7  mov     rbx, rax
0x1800074fa  mov     [rsp+68h+arg_0], rax
0x1800074ff  test    rax, rax
0x180007502  jnz     short loc_18000751E
0x180007504  or      dword ptr [r14], 2
0x180007508  lock dec dword ptr [rsi]
0x18000750b  mov     eax, edi
0x18000750d  mov     rbx, [rsp+68h+arg_18]
0x180007515  add     rsp, 50h
0x180007519  pop     r14
0x18000751b  pop     rdi
0x18000751c  pop     rsi
0x18000751d  retn
0x18000751e  mov     rcx, rbx; this
0x180007521  call    ?ReopenVolumeHandles@CVolume@@QEAAHXZ; CVolume::ReopenVolumeHandles(void)
0x180007526  neg     eax
0x180007528  sbb     ecx, ecx
0x18000752a  and     ecx, edi
0x18000752c  mov     edi, ecx
0x18000752e  mov     [rsp+68h+var_48], ecx
0x180007532  jmp     short loc_18000754C
0x180007534  xor     edi, edi
0x180007536  mov     [rsp+68h+var_48], edi
0x18000753a  mov     rbx, [rsp+68h+arg_0]
0x18000753f  mov     rsi, [rsp+68h+arg_8]
0x180007544  mov     r14, [rsp+68h+arg_10]
0x18000754c  mov     rcx, rbx; this
0x18000754f  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x180007554  jmp     short loc_1800074ED
0x180007556  xor     eax, eax
0x180007558  jmp     short loc_18000750D
0x18000755a  test    [r14], dil
0x18000755d  jz      short loc_1800074ED
0x18000755f  jmp     loc_1800074D5
0x180011481  push    rbp
0x180011483  sub     rsp, 20h
0x180011487  mov     rbp, rdx
0x18001148a  mov     eax, 1
0x18001148f  add     rsp, 20h
0x180011493  pop     rbp
0x180011494  retn
```
