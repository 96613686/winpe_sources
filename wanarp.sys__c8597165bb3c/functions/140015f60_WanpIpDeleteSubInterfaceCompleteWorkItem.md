# WanpIpDeleteSubInterfaceCompleteWorkItem

- ea: `0x140015f60`
- end: `0x1400160e4`
- name: `WanpIpDeleteSubInterfaceCompleteWorkItem`
- size: `388`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000d380`
- `0x140015db0`

## callees

- `0x1400032dc`
- `0x14000e280`
- `0x14000e310`
- `0x14000e6f8`
- `0x14000f094`
- `0x140015f60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015f7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016043`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015f7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016043`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015fd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015faf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001606d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001608a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015faf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001606d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001608a`

## pseudocode

```c
void __fastcall WanpIpDeleteSubInterfaceCompleteWorkItem(_QWORD *Entry)
{
  __int64 v1; // rbp
  __int64 v3; // rsi
  bool v4; // r14
  KIRQL v5; // al
  int v6; // eax
  char v7; // r14
  KIRQL v8; // al
  __int64 v9; // rdx
  KSPIN_LOCK *v10; // rcx

  v1 = Entry[2];
  v3 = Entry[1];
  v4 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 56));
  if ( *((_DWORD *)Entry + 25) )
  {
    *(_QWORD *)(v1 + 40) = 0;
    v4 = *((_DWORD *)Entry + 25) == 3;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), v5);
  if ( *((_DWORD *)Entry + 25) == 2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 64), 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag((PVOID)v1, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter((PVOID)v3);
  }
  *((_BYTE *)Entry + 200) = 0;
  if ( *(_DWORD *)(v1 + 108) == 2 )
  {
    WanpDeleteInterfaceFromIp((char *)v1);
  }
  else
  {
    v6 = *((_DWORD *)Entry + 25);
    if ( v6 && v6 != 3 )
    {
      v7 = *((_BYTE *)Entry + 4);
      WanpUnmapInterface((PVOID)v1);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) == 1 )
        WanpDeleteAdapter((PVOID)v3);
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 120));
      v9 = 168;
      if ( v7 )
        v9 = 176;
      v10 = (KSPIN_LOCK *)(v3 + 120);
      if ( *(_QWORD *)(v9 + v3) )
      {
        KeReleaseSpinLock(v10, v8);
        goto LABEL_24;
      }
      KeReleaseSpinLock(v10, v8);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) != 1 )
        goto LABEL_24;
      goto LABEL_22;
    }
    if ( v4 )
      WanpIpDeleteSpecialSubInterfaceComplete(Entry);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 128), 0xFFFFFFFF) == 1 )
LABEL_22:
      WanpDeleteAdapter((PVOID)v3);
  }
LABEL_24:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
    FreeConnection(Entry);
}

```

## disassembly

```asm
0x140015f60  push    rbx
0x140015f62  push    rbp
0x140015f63  push    rsi
0x140015f64  push    rdi
0x140015f65  push    r14
0x140015f67  sub     rsp, 20h
0x140015f6b  mov     rbp, [rcx+10h]
0x140015f6f  mov     rbx, rcx
0x140015f72  mov     rsi, [rcx+8]
0x140015f76  xor     r14b, r14b
0x140015f79  lea     rcx, [rbp+38h]; SpinLock
0x140015f7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015f84  nop     dword ptr [rax+rax+00h]
0x140015f89  cmp     dword ptr [rbx+64h], 0
0x140015f8d  jz      short loc_140015FA8
0x140015f8f  mov     qword ptr [rbp+28h], 0
0x140015f97  mov     ecx, 1
0x140015f9c  cmp     dword ptr [rbx+64h], 3
0x140015fa0  movzx   r14d, r14b
0x140015fa4  cmovz   r14d, ecx
0x140015fa8  movzx   edx, al; NewIrql
0x140015fab  lea     rcx, [rbp+38h]; SpinLock
0x140015faf  call    cs:__imp_KeReleaseSpinLock
0x140015fb6  nop     dword ptr [rax+rax+00h]
0x140015fbb  cmp     dword ptr [rbx+64h], 2
0x140015fbf  mov     edi, 0FFFFFFFFh
0x140015fc4  jnz     short loc_140015FFA
0x140015fc6  mov     eax, edi
0x140015fc8  lock xadd [rbp+40h], eax
0x140015fcd  cmp     eax, 1
0x140015fd0  jnz     short loc_140015FE3
0x140015fd2  xor     edx, edx; Tag
0x140015fd4  mov     rcx, rbp; P
0x140015fd7  call    cs:__imp_ExFreePoolWithTag
0x140015fde  nop     dword ptr [rax+rax+00h]
0x140015fe3  mov     eax, edi
0x140015fe5  lock xadd [rsi+80h], eax
0x140015fed  cmp     eax, 1
0x140015ff0  jnz     short loc_140015FFA
0x140015ff2  mov     rcx, rsi; P
0x140015ff5  call    WanpDeleteAdapter
0x140015ffa  mov     byte ptr [rbx+0C8h], 0
0x140016001  cmp     dword ptr [rbp+6Ch], 2
0x140016005  jz      loc_1400160BE
0x14001600b  mov     eax, [rbx+64h]
0x14001600e  test    eax, eax
0x140016010  jz      loc_140016098
0x140016016  cmp     eax, 3
0x140016019  jz      short loc_140016098
0x14001601b  movzx   r14d, byte ptr [rbx+4]
0x140016020  mov     rcx, rbp; P
0x140016023  call    WanpUnmapInterface
0x140016028  mov     eax, edi
0x14001602a  lock xadd [rsi+80h], eax
0x140016032  cmp     eax, 1
0x140016035  jnz     short loc_14001603F
0x140016037  mov     rcx, rsi; P
0x14001603a  call    WanpDeleteAdapter
0x14001603f  lea     rcx, [rsi+78h]; SpinLock
0x140016043  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001604a  nop     dword ptr [rax+rax+00h]
0x14001604f  test    r14b, r14b
0x140016052  mov     ecx, 0B0h
0x140016057  mov     edx, 0A8h
0x14001605c  cmovnz  edx, ecx
0x14001605f  lea     rcx, [rsi+78h]; SpinLock
0x140016063  cmp     qword ptr [rdx+rsi], 0
0x140016068  movzx   edx, al; NewIrql
0x14001606b  jnz     short loc_14001608A
0x14001606d  call    cs:__imp_KeReleaseSpinLock
0x140016074  nop     dword ptr [rax+rax+00h]
0x140016079  mov     eax, edi
0x14001607b  lock xadd [rsi+80h], eax
0x140016083  cmp     eax, 1
0x140016086  jnz     short loc_1400160C6
0x140016088  jmp     short loc_1400160B4
0x14001608a  call    cs:__imp_KeReleaseSpinLock
0x140016091  nop     dword ptr [rax+rax+00h]
0x140016096  jmp     short loc_1400160C6
0x140016098  test    r14b, r14b
0x14001609b  jz      short loc_1400160A5
0x14001609d  mov     rcx, rbx
0x1400160a0  call    WanpIpDeleteSpecialSubInterfaceComplete
0x1400160a5  mov     eax, edi
0x1400160a7  lock xadd [rsi+80h], eax
0x1400160af  cmp     eax, 1
0x1400160b2  jnz     short loc_1400160C6
0x1400160b4  mov     rcx, rsi; P
0x1400160b7  call    WanpDeleteAdapter
0x1400160bc  jmp     short loc_1400160C6
0x1400160be  mov     rcx, rbp; P
0x1400160c1  call    WanpDeleteInterfaceFromIp
0x1400160c6  lock xadd [rbx+60h], edi
0x1400160cb  cmp     edi, 1
0x1400160ce  jnz     short loc_1400160D8
0x1400160d0  mov     rcx, rbx; Entry
0x1400160d3  call    FreeConnection
0x1400160d8  add     rsp, 20h
0x1400160dc  pop     r14
0x1400160de  pop     rdi
0x1400160df  pop     rsi
0x1400160e0  pop     rbp
0x1400160e1  pop     rbx
0x1400160e2  retn
```
