# SrvNetEndpointReopenTdiConnections

- ea: `0x1400161a4`
- end: `0x14001637d`
- name: `SrvNetEndpointReopenTdiConnections`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f180`

## callees

- `0x14000b360`
- `0x140013c50`
- `0x1400161a4`
- `0x1400511f0`
- `0x140051710`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140016221`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016316`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016221`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016316`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400162d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400162d4`

## pseudocode

```c
__int64 **__fastcall SrvNetEndpointReopenTdiConnections(__int64 a1)
{
  KSPIN_LOCK *v2; // r14
  int v3; // r15d
  int v4; // esi
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 ***v7; // rbx
  __int64 v8; // rax
  __int64 ****v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  KIRQL v13; // r9
  __int64 *v14; // rbx
  __int64 **result; // rax
  __int64 *v16; // rax
  __int64 *v17; // [rsp+20h] [rbp-38h] BYREF
  __int64 **v18; // [rsp+28h] [rbp-30h]
  _QWORD *v19; // [rsp+30h] [rbp-28h] BYREF
  __int64 ***v20; // [rsp+38h] [rbp-20h]
  _QWORD v21[3]; // [rsp+40h] [rbp-18h] BYREF

  v21[1] = v21;
  v2 = (KSPIN_LOCK *)(a1 + 24);
  v21[0] = v21;
  v3 = 0;
  v4 = 0;
  v20 = (__int64 ***)&v19;
  v19 = &v19;
  v18 = &v17;
  v17 = (__int64 *)&v17;
  LOBYTE(v6) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  if ( !*(_BYTE *)(a1 + 145) )
    RfsAppendList(v21, a1 + 192, v5, v6);
  KeReleaseSpinLock(v2, v6);
  while ( 1 )
  {
    v7 = (__int64 ***)v21[0];
    if ( (_QWORD *)v21[0] == v21 )
      break;
    if ( *(_QWORD **)(v21[0] + 8LL) != v21 || (v8 = *(_QWORD *)v21[0], *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0]) )
LABEL_21:
      __fastfail(3u);
    v21[0] = *(_QWORD *)v21[0];
    *(_QWORD *)(v8 + 8) = v21;
    if ( (int)SrvNetTdiOpenConnection((__int64)(v7 - 64)) < 0 )
    {
      v10 = v18;
      if ( *v18 != (__int64 *)&v17 )
        goto LABEL_21;
      v7[1] = v18;
      *v7 = &v17;
      ++v4;
      *v10 = v7;
      v18 = (__int64 **)v7;
    }
    else
    {
      v9 = (__int64 ****)v20;
      if ( *v20 != &v19 )
        goto LABEL_21;
      v7[1] = (__int64 **)v20;
      *v7 = &v19;
      ++v3;
      *v9 = v7;
      v20 = v7;
    }
  }
  if ( v19 != &v19 )
  {
    LOBYTE(v12) = KeAcquireSpinLockRaiseToDpc(v2);
    if ( *(_BYTE *)(a1 + 145) )
    {
      RfsAppendList(&v17, &v19, v11, v12);
      v4 += v3;
    }
    else
    {
      RfsAppendList(a1 + 208, &v19, v11, v12);
    }
    *(_DWORD *)(a1 + 168) -= v4;
    KeReleaseSpinLock(v2, v13);
  }
  while ( 1 )
  {
    v14 = v17;
    result = &v17;
    if ( v17 == (__int64 *)&v17 )
      return result;
    if ( (__int64 **)v17[1] != &v17 )
      goto LABEL_21;
    v16 = (__int64 *)*v17;
    if ( *(__int64 **)(*v17 + 8) != v17 )
      goto LABEL_21;
    v17 = (__int64 *)*v17;
    v16[1] = (__int64)&v17;
    SrvNetTdiCloseConnection(v14 - 64);
    SrvNetFreeConnection(v14 - 64);
  }
}

```

## disassembly

```asm
0x1400161a4  push    rbp
0x1400161a6  push    rbx
0x1400161a7  push    rsi
0x1400161a8  push    rdi
0x1400161a9  push    r14
0x1400161ab  push    r15
0x1400161ad  mov     rbp, rsp
0x1400161b0  sub     rsp, 58h
0x1400161b4  lea     rax, [rbp+var_18]
0x1400161b8  mov     rdi, rcx
0x1400161bb  mov     [rbp+var_10], rax
0x1400161bf  lea     r14, [rcx+18h]
0x1400161c3  lea     rax, [rbp+var_18]
0x1400161c7  mov     rcx, r14; SpinLock
0x1400161ca  mov     [rbp+var_18], rax
0x1400161ce  xor     r15d, r15d
0x1400161d1  lea     rax, [rbp+var_28]
0x1400161d5  xor     esi, esi
0x1400161d7  mov     [rbp+var_20], rax
0x1400161db  lea     rax, [rbp+var_28]
0x1400161df  mov     [rbp+var_28], rax
0x1400161e3  lea     rax, [rbp+var_38]
0x1400161e7  mov     [rbp+var_30], rax
0x1400161eb  lea     rax, [rbp+var_38]
0x1400161ef  mov     [rbp+var_38], rax
0x1400161f3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400161fa  nop     dword ptr [rax+rax+00h]
0x1400161ff  mov     r9b, al
0x140016202  cmp     [rdi+91h], sil
0x140016209  jnz     short loc_14001621B
0x14001620b  lea     rdx, [rdi+0C0h]
0x140016212  lea     rcx, [rbp+var_18]
0x140016216  call    RfsAppendList
0x14001621b  mov     dl, r9b; NewIrql
0x14001621e  mov     rcx, r14; SpinLock
0x140016221  call    cs:__imp_KeReleaseSpinLock
0x140016228  nop     dword ptr [rax+rax+00h]
0x14001622d  mov     rbx, [rbp+var_18]
0x140016231  lea     rax, [rbp+var_18]
0x140016235  cmp     rbx, rax
0x140016238  jz      loc_1400162C7
0x14001623e  lea     rax, [rbp+var_18]
0x140016242  cmp     [rbx+8], rax
0x140016246  jnz     loc_140016368
0x14001624c  mov     rax, [rbx]
0x14001624f  cmp     [rax+8], rbx
0x140016253  jnz     loc_140016368
0x140016259  lea     rcx, [rbp+var_18]
0x14001625d  mov     [rbp+var_18], rax
0x140016261  mov     [rax+8], rcx
0x140016265  lea     rcx, [rbx-200h]
0x14001626c  call    SrvNetTdiOpenConnection
0x140016271  test    eax, eax
0x140016273  js      short loc_14001629D
0x140016275  mov     rax, [rbp+var_20]
0x140016279  lea     rcx, [rbp+var_28]
0x14001627d  cmp     [rax], rcx
0x140016280  jnz     loc_140016368
0x140016286  mov     [rbx+8], rax
0x14001628a  lea     rcx, [rbp+var_28]
0x14001628e  mov     [rbx], rcx
0x140016291  inc     r15d
0x140016294  mov     [rax], rbx
0x140016297  mov     [rbp+var_20], rbx
0x14001629b  jmp     short loc_14001622D
0x14001629d  mov     rax, [rbp+var_30]
0x1400162a1  lea     rcx, [rbp+var_38]
0x1400162a5  cmp     [rax], rcx
0x1400162a8  jnz     loc_140016368
0x1400162ae  mov     [rbx+8], rax
0x1400162b2  lea     rcx, [rbp+var_38]
0x1400162b6  mov     [rbx], rcx
0x1400162b9  inc     esi
0x1400162bb  mov     [rax], rbx
0x1400162be  mov     [rbp+var_30], rbx
0x1400162c2  jmp     loc_14001622D
0x1400162c7  lea     rax, [rbp+var_28]
0x1400162cb  cmp     [rbp+var_28], rax
0x1400162cf  jz      short loc_140016322
0x1400162d1  mov     rcx, r14; SpinLock
0x1400162d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400162db  nop     dword ptr [rax+rax+00h]
0x1400162e0  cmp     byte ptr [rdi+91h], 0
0x1400162e7  lea     rdx, [rbp+var_28]
0x1400162eb  mov     r9b, al
0x1400162ee  jz      short loc_1400162FE
0x1400162f0  lea     rcx, [rbp+var_38]
0x1400162f4  call    RfsAppendList
0x1400162f9  add     esi, r15d
0x1400162fc  jmp     short loc_14001630A
0x1400162fe  lea     rcx, [rdi+0D0h]
0x140016305  call    RfsAppendList
0x14001630a  sub     [rdi+0A8h], esi
0x140016310  mov     dl, r9b; NewIrql
0x140016313  mov     rcx, r14; SpinLock
0x140016316  call    cs:__imp_KeReleaseSpinLock
0x14001631d  nop     dword ptr [rax+rax+00h]
0x140016322  mov     rbx, [rbp+var_38]
0x140016326  lea     rax, [rbp+var_38]
0x14001632a  cmp     rbx, rax
0x14001632d  jz      short loc_14001636F
0x14001632f  lea     rax, [rbp+var_38]
0x140016333  cmp     [rbx+8], rax
0x140016337  jnz     short loc_140016368
0x140016339  mov     rax, [rbx]
0x14001633c  cmp     [rax+8], rbx
0x140016340  jnz     short loc_140016368
0x140016342  lea     rcx, [rbp+var_38]
0x140016346  mov     [rbp+var_38], rax
0x14001634a  mov     [rax+8], rcx
0x14001634e  lea     rcx, [rbx-200h]
0x140016355  call    SrvNetTdiCloseConnection
0x14001635a  lea     rcx, [rbx-200h]; P
0x140016361  call    SrvNetFreeConnection
0x140016366  jmp     short loc_140016322
0x140016368  mov     ecx, 3
0x14001636d  int     29h; Win8: RtlFailFast(ecx)
0x14001636f  add     rsp, 58h
0x140016373  pop     r15
0x140016375  pop     r14
0x140016377  pop     rdi
0x140016378  pop     rsi
0x140016379  pop     rbx
0x14001637a  pop     rbp
0x14001637b  retn
```
