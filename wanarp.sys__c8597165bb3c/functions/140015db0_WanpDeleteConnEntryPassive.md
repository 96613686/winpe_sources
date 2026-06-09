# WanpDeleteConnEntryPassive

- ea: `0x140015db0`
- end: `0x140015f59`
- name: `WanpDeleteConnEntryPassive`
- size: `425`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f728`

## callees

- `0x1400032dc`
- `0x1400050f0`
- `0x140015db0`
- `0x140015f60`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e26`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e26`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e80`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015de7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e80`

## pseudocode

```c
void __fastcall WanpDeleteConnEntryPassive(_QWORD *Entry)
{
  char v1; // r14
  KIRQL v3; // al
  bool v4; // zf
  KSPIN_LOCK *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdi
  KIRQL v8; // al
  __int64 v9; // rdi
  char v10; // bp
  __int64 v11; // rcx
  int v12; // esi
  _QWORD v13[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *((_BYTE *)Entry + 4);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry[10]);
  v4 = *((_DWORD *)Entry + 31) == 0;
  v5 = (KSPIN_LOCK *)Entry[10];
  *((_BYTE *)Entry + 200) = 0;
  if ( v4 )
  {
    v6 = Entry[16];
    v7 = *((unsigned int *)Entry + 26);
    *((_DWORD *)Entry + 31) = 4;
    KeReleaseSpinLock(v5, v3);
    v8 = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
    if ( *((_QWORD **)g_puipConnTable + v7) == Entry )
    {
      *((_QWORD *)g_puipConnTable + v7) = 0;
      --g_rgulConns[*((int *)Entry + 25)];
      if ( *((_QWORD *)g_puipConnTable + (unsigned int)g_ulNextConnIndex) )
        g_ulNextConnIndex = v7;
    }
    KeReleaseSpinLock(&g_rlConnTableLock, v8);
    v9 = *((unsigned int *)Entry + 25);
    v13[0] = WanIpDeleteSubInterfaceComplete;
    v13[1] = v6;
    _InterlockedIncrement((volatile signed __int32 *)Entry + 24);
    if ( (_DWORD)v9 == 1 || (v10 = 0, (_DWORD)v9 == 2) )
    {
      v10 = 1;
      v13[0] = WanIpDeleteDialOutSubInterfaceComplete;
      _InterlockedIncrement((volatile signed __int32 *)Entry + 24);
    }
    if ( v6 )
    {
      v11 = qword_1400090D8;
      if ( !v1 )
        v11 = qword_140009328;
      v12 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v11 + 8) + 40LL))(v13);
      _InterlockedIncrement(&dword_140009784[4 * v9]);
      if ( v12 != 259 && v10 && _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
        FreeConnection(Entry);
      if ( (unsigned int)(v9 - 1) <= 1 || v12 != 259 )
        WanpIpDeleteSubInterfaceCompleteWorkItem(Entry);
    }
  }
  else
  {
    KeReleaseSpinLock(v5, v3);
  }
}

```

## disassembly

```asm
0x140015db0  mov     [rsp+arg_18], rbx
0x140015db5  push    r14
0x140015db7  sub     rsp, 30h
0x140015dbb  movzx   r14d, byte ptr [rcx+4]
0x140015dc0  mov     rbx, rcx
0x140015dc3  mov     rcx, [rcx+50h]; SpinLock
0x140015dc7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015dce  nop     dword ptr [rax+rax+00h]
0x140015dd3  cmp     dword ptr [rbx+7Ch], 0
0x140015dd7  movzx   edx, al; NewIrql
0x140015dda  mov     rcx, [rbx+50h]; SpinLock
0x140015dde  mov     byte ptr [rbx+0C8h], 0
0x140015de5  jz      short loc_140015DF8
0x140015de7  call    cs:__imp_KeReleaseSpinLock
0x140015dee  nop     dword ptr [rax+rax+00h]
0x140015df3  jmp     loc_140015F4C
0x140015df8  mov     [rsp+38h+arg_8], rsi
0x140015dfd  mov     rsi, [rbx+80h]
0x140015e04  mov     [rsp+38h+arg_10], rdi
0x140015e09  mov     edi, [rbx+68h]
0x140015e0c  mov     dword ptr [rbx+7Ch], 4
0x140015e13  call    cs:__imp_KeReleaseSpinLock
0x140015e1a  nop     dword ptr [rax+rax+00h]
0x140015e1f  lea     rcx, g_rlConnTableLock; SpinLock
0x140015e26  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015e2d  nop     dword ptr [rax+rax+00h]
0x140015e32  mov     rcx, cs:g_puipConnTable
0x140015e39  cmp     [rcx+rdi*8], rbx
0x140015e3d  jnz     short loc_140015E71
0x140015e3f  mov     qword ptr [rcx+rdi*8], 0
0x140015e47  lea     r8, g_rgulConns
0x140015e4e  movsxd  rdx, dword ptr [rbx+64h]
0x140015e52  dec     dword ptr [r8+rdx*4]
0x140015e56  mov     r8d, cs:g_ulNextConnIndex
0x140015e5d  mov     rdx, cs:g_puipConnTable
0x140015e64  cmp     qword ptr [rdx+r8*8], 0
0x140015e69  jz      short loc_140015E71
0x140015e6b  mov     cs:g_ulNextConnIndex, edi
0x140015e71  movzx   edx, al; NewIrql
0x140015e74  mov     [rsp+38h+arg_0], rbp
0x140015e79  lea     rcx, g_rlConnTableLock; SpinLock
0x140015e80  call    cs:__imp_KeReleaseSpinLock
0x140015e87  nop     dword ptr [rax+rax+00h]
0x140015e8c  mov     edi, [rbx+64h]
0x140015e8f  lea     rax, WanIpDeleteSubInterfaceComplete
0x140015e96  mov     [rsp+38h+var_18], rax
0x140015e9b  mov     [rsp+38h+var_10], rsi
0x140015ea0  lock inc dword ptr [rbx+60h]
0x140015ea4  cmp     edi, 1
0x140015ea7  jz      short loc_140015EB1
0x140015ea9  xor     bpl, bpl
0x140015eac  cmp     edi, 2
0x140015eaf  jnz     short loc_140015EC4
0x140015eb1  lea     rax, WanIpDeleteDialOutSubInterfaceComplete
0x140015eb8  mov     bpl, 1
0x140015ebb  mov     [rsp+38h+var_18], rax
0x140015ec0  lock inc dword ptr [rbx+60h]
0x140015ec4  test    rsi, rsi
0x140015ec7  jz      short loc_140015F3D
0x140015ec9  mov     rcx, cs:qword_1400090D8
0x140015ed0  test    r14b, r14b
0x140015ed3  cmovz   rcx, cs:qword_140009328
0x140015edb  mov     rax, [rcx+8]
0x140015edf  lea     rcx, [rsp+38h+var_18]
0x140015ee4  mov     rax, [rax+28h]
0x140015ee8  call    _guard_dispatch_icall
0x140015eed  mov     rcx, rdi
0x140015ef0  mov     esi, eax
0x140015ef2  shl     rcx, 4
0x140015ef6  lea     rax, dword_140009784
0x140015efd  lock inc dword ptr [rcx+rax]
0x140015f01  cmp     esi, 103h
0x140015f07  jz      short loc_140015F25
0x140015f09  test    bpl, bpl
0x140015f0c  jz      short loc_140015F25
0x140015f0e  mov     eax, 0FFFFFFFFh
0x140015f13  lock xadd [rbx+60h], eax
0x140015f18  cmp     eax, 1
0x140015f1b  jnz     short loc_140015F25
0x140015f1d  mov     rcx, rbx; Entry
0x140015f20  call    FreeConnection
0x140015f25  lea     eax, [rdi-1]
0x140015f28  cmp     eax, 1
0x140015f2b  jbe     short loc_140015F35
0x140015f2d  cmp     esi, 103h
0x140015f33  jz      short loc_140015F3D
0x140015f35  mov     rcx, rbx; Entry
0x140015f38  call    WanpIpDeleteSubInterfaceCompleteWorkItem
0x140015f3d  mov     rbp, [rsp+38h+arg_0]
0x140015f42  mov     rsi, [rsp+38h+arg_8]
0x140015f47  mov     rdi, [rsp+38h+arg_10]
0x140015f4c  mov     rbx, [rsp+38h+arg_18]
0x140015f51  add     rsp, 30h
0x140015f55  pop     r14
0x140015f57  retn
```
