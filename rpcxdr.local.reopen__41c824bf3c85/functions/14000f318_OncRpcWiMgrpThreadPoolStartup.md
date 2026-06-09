# OncRpcWiMgrpThreadPoolStartup

- ea: `0x14000f318`
- end: `0x14000f481`
- name: `OncRpcWiMgrpThreadPoolStartup`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024514`

## callees

- `0x1400020c0`
- `0x14000f318`
- `0x1400203a4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000f37d`
- `ntoskrnl!KeInitializeEvent` at `0x14000f37d`
- `ntoskrnl!KeInitializeQueue` at `0x14000f35e`
- `ntoskrnl!KeInitializeQueue` at `0x14000f35e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f345`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f345`
- `ntoskrnl!ExAllocatePool2` at `0x14000f405`
- `ntoskrnl!ExAllocatePool2` at `0x14000f405`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrpThreadPoolStartup(__int64 a1, int a2)
{
  int v2; // esi
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 Pool2; // rax

  *(_DWORD *)a1 = 1346917458;
  v2 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  *(_WORD *)(a1 + 8) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 24));
  KeInitializeQueue((PRKQUEUE)(a1 + 32), dword_14001A498 & 1);
  *(_DWORD *)(a1 + 216) |= 2u;
  KeInitializeEvent((PRKEVENT)(a1 + 184), NotificationEvent, 0);
  *(_DWORD *)(a1 + 112) = a2;
  if ( (dword_14001A498 & 1) != 0 )
    v5 = dword_14001A448;
  else
    v5 = dword_14001A448 * dword_14001A42C;
  *(_DWORD *)(a1 + 100) = v5;
  v6 = dword_14001A44C;
  if ( (dword_14001A498 & 1) == 0 )
    v6 = dword_14001A42C * dword_14001A44C;
  *(_DWORD *)(a1 + 216) &= ~1u;
  *(_DWORD *)(a1 + 96) = v6;
  v7 = 0;
  *(_DWORD *)(a1 + 108) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 120) = -3000000000LL;
  while ( v7 < *(_DWORD *)(a1 + 100) )
  {
    Pool2 = ExAllocatePool2(64, 16, 1380996178);
    if ( !Pool2 )
    {
      v2 = -1073741670;
      break;
    }
    *(_QWORD *)Pool2 = a1;
    *(_DWORD *)(Pool2 + 8) = *(_DWORD *)(Pool2 + 8) & 0xFFFFFFFC | 1;
    v2 = OncRpcWiMgrpWorkerThreadCreate((__int64 *)Pool2);
    if ( v2 < 0 )
      break;
    ++v7;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000f318  mov     [rsp+arg_0], rbx
0x14000f31d  mov     [rsp+arg_8], rsi
0x14000f322  push    rdi
0x14000f323  sub     rsp, 20h
0x14000f327  mov     dword ptr [rcx], 50485452h
0x14000f32d  xor     esi, esi
0x14000f32f  mov     [rcx+10h], rsi
0x14000f333  xor     eax, eax
0x14000f335  mov     [rcx+4], esi
0x14000f338  mov     rdi, rcx
0x14000f33b  mov     [rcx+8], ax
0x14000f33f  mov     ebx, edx
0x14000f341  add     rcx, 18h; SpinLock
0x14000f345  call    cs:__imp_KeInitializeSpinLock
0x14000f34c  nop     dword ptr [rax+rax+00h]
0x14000f351  mov     edx, cs:dword_14001A498
0x14000f357  lea     rcx, [rdi+20h]; Queue
0x14000f35b  and     edx, 1; Count
0x14000f35e  call    cs:__imp_KeInitializeQueue
0x14000f365  nop     dword ptr [rax+rax+00h]
0x14000f36a  or      dword ptr [rdi+0D8h], 2
0x14000f371  lea     rcx, [rdi+0B8h]; Event
0x14000f378  xor     r8d, r8d; State
0x14000f37b  xor     edx, edx; Type
0x14000f37d  call    cs:__imp_KeInitializeEvent
0x14000f384  nop     dword ptr [rax+rax+00h]
0x14000f389  mov     [rdi+70h], ebx
0x14000f38c  mov     eax, cs:dword_14001A498
0x14000f392  test    al, 1
0x14000f394  jz      short loc_14000F39E
0x14000f396  mov     eax, cs:dword_14001A448
0x14000f39c  jmp     short loc_14000F3AB
0x14000f39e  mov     eax, cs:dword_14001A42C
0x14000f3a4  imul    eax, cs:dword_14001A448
0x14000f3ab  mov     [rdi+64h], eax
0x14000f3ae  mov     eax, cs:dword_14001A498
0x14000f3b4  test    al, 1
0x14000f3b6  mov     eax, cs:dword_14001A44C
0x14000f3bc  jnz     short loc_14000F3C5
0x14000f3be  imul    eax, cs:dword_14001A42C
0x14000f3c5  and     dword ptr [rdi+0D8h], 0FFFFFFFEh
0x14000f3cc  mov     [rdi+60h], eax
0x14000f3cf  xor     ebx, ebx
0x14000f3d1  mov     [rdi+6Ch], esi
0x14000f3d4  mov     rax, 0FFFFFFFF4D2FA200h
0x14000f3de  mov     [rdi+68h], esi
0x14000f3e1  mov     [rdi+0D0h], rsi
0x14000f3e8  mov     [rdi+80h], esi
0x14000f3ee  mov     [rdi+78h], rax
0x14000f3f2  cmp     ebx, [rdi+64h]
0x14000f3f5  jnb     short loc_14000F43C
0x14000f3f7  mov     edx, 10h
0x14000f3fc  mov     r8d, 52505452h
0x14000f402  lea     ecx, [rdx+30h]
0x14000f405  call    cs:__imp_ExAllocatePool2
0x14000f40c  nop     dword ptr [rax+rax+00h]
0x14000f411  mov     rcx, rax; P
0x14000f414  test    rax, rax
0x14000f417  jz      short loc_14000F437
0x14000f419  mov     [rax], rdi
0x14000f41c  mov     eax, [rax+8]
0x14000f41f  and     eax, 0FFFFFFFDh
0x14000f422  or      eax, 1
0x14000f425  mov     [rcx+8], eax
0x14000f428  call    OncRpcWiMgrpWorkerThreadCreate
0x14000f42d  mov     esi, eax
0x14000f42f  test    eax, eax
0x14000f431  js      short loc_14000F43C
0x14000f433  inc     ebx
0x14000f435  jmp     short loc_14000F3F2
0x14000f437  mov     esi, 0C000009Ah
0x14000f43c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f443  lea     rax, WPP_GLOBAL_Control
0x14000f44a  cmp     rcx, rax
0x14000f44d  jz      short loc_14000F46E
0x14000f44f  mov     eax, [rcx+2Ch]
0x14000f452  test    al, 1
0x14000f454  jz      short loc_14000F46E
0x14000f456  mov     rcx, [rcx+18h]
0x14000f45a  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x14000f461  mov     edx, 0Ch
0x14000f466  mov     r9d, esi
0x14000f469  call    WPP_SF_d
0x14000f46e  mov     rbx, [rsp+28h+arg_0]
0x14000f473  mov     eax, esi
0x14000f475  mov     rsi, [rsp+28h+arg_8]
0x14000f47a  add     rsp, 20h
0x14000f47e  pop     rdi
0x14000f47f  retn
```
