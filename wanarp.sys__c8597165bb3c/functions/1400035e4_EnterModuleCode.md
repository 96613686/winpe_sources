# EnterModuleCode

- ea: `0x1400035e4`
- end: `0x1400036df`
- name: `EnterModuleCode`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fdc4`
- `0x140010448`
- `0x1400172d0`

## callees

- `0x1400035e4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003665`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003665`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000363a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000363a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036c0`

## pseudocode

```c
char __fastcall EnterModuleCode(char a1)
{
  char v1; // dl
  unsigned int v2; // esi
  char v4; // bl
  char v5; // cl
  KIRQL v6; // al
  int v7; // ecx
  KIRQL v8; // dl
  int v9; // ecx
  int *v10; // rax
  int v11; // ecx
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  v1 = byte_1400099E4;
  v2 = 0;
  if ( !a1 )
    v1 = byte_140009B04;
  v4 = 1;
  if ( v1 )
  {
LABEL_8:
    v6 = KeAcquireSpinLockRaiseToDpc(&g_rlStateLock);
    v7 = dword_140009A80;
    v8 = v6;
    if ( !a1 )
      v7 = Increment;
    if ( v7 == 2 )
    {
      v9 = dword_140009AE8;
      v10 = &dword_140009AE8;
      if ( !a1 )
        v9 = dword_140009C08;
      v11 = v9 + 1;
      if ( !a1 )
        v10 = &dword_140009C08;
      *v10 = v11;
    }
    else
    {
      v4 = 0;
    }
    KeReleaseSpinLock(&g_rlStateLock, v8);
    return v4;
  }
  else
  {
    while ( v2 < 3 )
    {
      ++v2;
      Interval.QuadPart = -50000000 - 50000000 * v2;
      KeDelayExecutionThread(1, 0, &Interval);
      v5 = byte_1400099E4;
      if ( !a1 )
        v5 = byte_140009B04;
      if ( v5 )
        goto LABEL_8;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400035e4  mov     [rsp+arg_0], rbx
0x1400035e9  mov     [rsp+arg_10], rsi
0x1400035ee  push    rdi
0x1400035ef  sub     rsp, 20h
0x1400035f3  movzx   edx, cs:byte_1400099E4
0x1400035fa  xor     esi, esi
0x1400035fc  movzx   eax, cs:byte_140009B04
0x140003603  test    cl, cl
0x140003605  mov     dil, cl
0x140003608  cmovz   edx, eax
0x14000360b  lea     ebx, [rsi+1]
0x14000360e  test    dl, dl
0x140003610  jnz     short loc_14000365E
0x140003612  cmp     esi, 3
0x140003615  jnb     loc_1400036B3
0x14000361b  mov     ecx, 0FD050F80h
0x140003620  lea     r8, [rsp+28h+Interval]; Interval
0x140003625  add     esi, ebx
0x140003627  xor     edx, edx; Alertable
0x140003629  imul    eax, esi, 2FAF080h
0x14000362f  sub     ecx, eax
0x140003631  mov     eax, ecx
0x140003633  mov     cl, bl; WaitMode
0x140003635  mov     qword ptr [rsp+28h+Interval], rax
0x14000363a  call    cs:__imp_KeDelayExecutionThread
0x140003641  nop     dword ptr [rax+rax+00h]
0x140003646  movzx   ecx, cs:byte_1400099E4
0x14000364d  test    dil, dil
0x140003650  movzx   eax, cs:byte_140009B04
0x140003657  cmovz   ecx, eax
0x14000365a  test    cl, cl
0x14000365c  jz      short loc_140003612
0x14000365e  lea     rcx, g_rlStateLock; SpinLock
0x140003665  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000366c  nop     dword ptr [rax+rax+00h]
0x140003671  mov     ecx, cs:dword_140009A80
0x140003677  test    dil, dil
0x14000367a  mov     dl, al; NewIrql
0x14000367c  cmovz   ecx, cs:Increment
0x140003683  cmp     ecx, 2
0x140003686  jnz     short loc_1400036B7
0x140003688  mov     ecx, cs:dword_140009AE8
0x14000368e  lea     r8, dword_140009C08
0x140003695  test    dil, dil
0x140003698  lea     rax, dword_140009AE8
0x14000369f  cmovz   ecx, cs:dword_140009C08
0x1400036a6  add     ecx, ebx
0x1400036a8  test    dil, dil
0x1400036ab  cmovz   rax, r8
0x1400036af  mov     [rax], ecx
0x1400036b1  jmp     short loc_1400036B9
0x1400036b3  xor     al, al
0x1400036b5  jmp     short loc_1400036CE
0x1400036b7  xor     bl, bl
0x1400036b9  lea     rcx, g_rlStateLock; SpinLock
0x1400036c0  call    cs:__imp_KeReleaseSpinLock
0x1400036c7  nop     dword ptr [rax+rax+00h]
0x1400036cc  mov     al, bl
0x1400036ce  mov     rbx, [rsp+28h+arg_0]
0x1400036d3  mov     rsi, [rsp+28h+arg_10]
0x1400036d8  add     rsp, 20h
0x1400036dc  pop     rdi
0x1400036dd  retn
```
