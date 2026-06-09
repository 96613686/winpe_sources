# WinHvpReferencePartition

- ea: `0x140002bf0`
- end: `0x140002ce1`
- name: `WinHvpReferencePartition`
- size: `241`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001ef0`
- `0x140002358`
- `0x140002454`
- `0x1400025e0`
- `0x1400026d0`
- `0x140002830`
- `0x140004870`
- `0x140007310`
- `0x140007760`
- `0x1400077b0`
- `0x14000794c`
- `0x140007a40`
- `0x140007bec`
- `0x140007cc4`
- `0x140007d0c`
- `0x140008df4`
- `0x140009750`
- `0x14000bf34`
- `0x14001f990`
- `0x14001fb40`
- `0x140024020`

## callees

- `0x140002bf0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140002c01`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002c01`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002c14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002c14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002caa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002caa`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140002c29`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140002c29`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140002c9e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140002c9e`

## pseudocode

```c
volatile signed __int64 *__fastcall WinHvpReferencePartition(unsigned __int64 a1)
{
  KIRQL CurrentIrql; // si
  __int64 v3; // r8
  __int64 v4; // r9
  volatile signed __int64 *v5; // rbx
  int v6; // edx
  int v7; // eax
  unsigned int v9; // ecx

  CurrentIrql = KeGetCurrentIrql();
  if ( CurrentIrql < 2u )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(&WinHvpPartitionArrayLock, 0);
  }
  v5 = 0;
  if ( WinHvpPartitionArray )
  {
    v6 = 0;
    v7 = *(_DWORD *)WinHvpPartitionArray - 1;
    while ( v6 <= v7 )
    {
      v3 = 2LL * ((unsigned int)(v7 + v6) >> 1);
      v4 = (unsigned int)(v7 + v6) >> 1;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16 * v4 + 8) == a1 )
      {
        v5 = *(volatile signed __int64 **)(WinHvpPartitionArray + 16LL * ((unsigned int)(v7 + v6) >> 1) + 16);
        if ( v5 && _InterlockedIncrement64(v5) <= 1 )
          __fastfail(0xEu);
        break;
      }
      v9 = ((unsigned int)(v7 + v6) >> 1) + 1;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16LL * ((unsigned int)(v7 + v6) >> 1) + 8) >= a1 )
        v9 = v6;
      v6 = v9;
      if ( *(_QWORD *)(WinHvpPartitionArray + 16 * v4 + 8) >= a1 )
        v7 = v4 - 1;
    }
  }
  if ( CurrentIrql < 2u )
  {
    ExReleasePushLockSharedEx(&WinHvpPartitionArrayLock, 0, v3, v4);
    KeLeaveCriticalRegion();
  }
  return v5;
}

```

## disassembly

```asm
0x140002bf0  sub     rsp, 28h
0x140002bf4  mov     [rsp+28h+arg_8], rsi
0x140002bf9  mov     [rsp+28h+var_8], rdi
0x140002bfe  mov     rdi, rcx
0x140002c01  call    cs:__imp_KeGetCurrentIrql
0x140002c08  nop     dword ptr [rax+rax+00h]
0x140002c0d  movzx   esi, al
0x140002c10  cmp     al, 2
0x140002c12  jnb     short loc_140002C35
0x140002c14  call    cs:__imp_KeEnterCriticalRegion
0x140002c1b  nop     dword ptr [rax+rax+00h]
0x140002c20  xor     edx, edx
0x140002c22  lea     rcx, WinHvpPartitionArrayLock
0x140002c29  call    cs:__imp_ExAcquirePushLockSharedEx
0x140002c30  nop     dword ptr [rax+rax+00h]
0x140002c35  mov     r11, cs:WinHvpPartitionArray
0x140002c3c  mov     [rsp+28h+arg_0], rbx
0x140002c41  xor     ebx, ebx
0x140002c43  test    r11, r11
0x140002c46  jz      short loc_140002C85
0x140002c48  mov     eax, [r11]
0x140002c4b  mov     edx, ebx
0x140002c4d  dec     eax
0x140002c4f  cmp     edx, eax
0x140002c51  jg      short loc_140002C85
0x140002c53  lea     ecx, [rax+rdx]
0x140002c56  shr     ecx, 1
0x140002c58  mov     r8d, ecx
0x140002c5b  add     r8, r8
0x140002c5e  mov     r9d, ecx
0x140002c61  cmp     [r11+r8*8+8], rdi
0x140002c66  jnz     short loc_140002CC4
0x140002c68  mov     rbx, [r11+r8*8+10h]
0x140002c6d  test    rbx, rbx
0x140002c70  jz      short loc_140002C85
0x140002c72  mov     eax, 1
0x140002c77  lock xadd [rbx], rax
0x140002c7c  inc     rax
0x140002c7f  cmp     rax, 1
0x140002c83  jle     short loc_140002CD8
0x140002c85  mov     rdi, [rsp+28h+var_8]
0x140002c8a  cmp     sil, 2
0x140002c8e  mov     rsi, [rsp+28h+arg_8]
0x140002c93  jnb     short loc_140002CB6
0x140002c95  xor     edx, edx
0x140002c97  lea     rcx, WinHvpPartitionArrayLock
0x140002c9e  call    cs:__imp_ExReleasePushLockSharedEx
0x140002ca5  nop     dword ptr [rax+rax+00h]
0x140002caa  call    cs:__imp_KeLeaveCriticalRegion
0x140002cb1  nop     dword ptr [rax+rax+00h]
0x140002cb6  mov     rax, rbx
0x140002cb9  mov     rbx, [rsp+28h+arg_0]
0x140002cbe  add     rsp, 28h
0x140002cc2  retn
0x140002cc4  lea     ecx, [rcx+1]
0x140002cc7  cmovnb  ecx, edx
0x140002cca  mov     edx, ecx
0x140002ccc  lea     ecx, [r9-1]
0x140002cd0  cmovnb  eax, ecx
0x140002cd3  jmp     loc_140002C4F
0x140002cd8  mov     ecx, 0Eh
0x140002cdd  int     29h; Win8: RtlFailFast(ecx)
0x140002cdf  jmp     short loc_140002C85
```
