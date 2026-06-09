# SqospModifyStreamHandleContext

- ea: `0x140006188`
- end: `0x14000631d`
- name: `SqospModifyStreamHandleContext`
- size: `405`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000603c`
- `0x140014d10`

## callees

- `0x140003870`
- `0x140003940`
- `0x140005a74`
- `0x140006188`
- `0x1400147e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000629a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000629a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061ed`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400062b8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400062b8`
- `FLTMGR!FltReleasePushLockEx` at `0x1400062da`
- `FLTMGR!FltReleasePushLockEx` at `0x1400062da`

## pseudocode

```c
__int64 __fastcall SqospModifyStreamHandleContext(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        char a5)
{
  __int64 v5; // r13
  __int64 *v6; // rsi
  __int64 v9; // r12
  struct _FLT_CALLBACK_DATA *v10; // rbp
  int v11; // r14d
  __int64 v12; // rbx
  __int64 v13; // rcx
  _BYTE *v14; // rbx
  char v15; // dl
  _BYTE *v16; // rbp
  void *v17; // rbx

  v5 = 0;
  v6 = a3 + 1;
  v9 = a2;
  v10 = a1;
  if ( a3[2] != a4 )
  {
    v5 = SqospLookupFlow((PKSPIN_LOCK)a4);
    if ( !v5 )
      return (unsigned int)-1073741670;
  }
  v12 = *v6;
  *(_BYTE *)(v12 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*v6 + 832));
  v13 = *v6;
  if ( *(_BYTE *)(*v6 + 928) )
  {
    v11 = -1071906805;
    goto LABEL_18;
  }
  v14 = a3 + 4;
  v11 = 0;
  v15 = *(_BYTE *)(a3[2] + 124LL);
  if ( !v15 )
  {
    v16 = a3 + 4;
    if ( !*v14 )
      goto LABEL_12;
  }
  if ( *(_BYTE *)(a4 + 124) || a5 )
  {
    v16 = a3 + 4;
    if ( v15 )
      goto LABEL_17;
LABEL_12:
    if ( !*v16 && (*(_BYTE *)(a4 + 124) || a5) )
    {
      --*(_DWORD *)(v13 + 916);
      BalanceUpdateDeviceMode(*v6);
    }
    v14 = v16;
    goto LABEL_17;
  }
  ++*(_DWORD *)(v13 + 916);
  BalanceUpdateDeviceMode(*v6);
LABEL_17:
  v10 = a1;
  *v14 = a5;
  v9 = a2;
LABEL_18:
  KeReleaseSpinLock((PKSPIN_LOCK)(a3[1] + 832LL), *(_BYTE *)(a3[1] + 840LL));
  if ( v11 >= 0 )
  {
    v17 = 0;
    if ( a3[2] != a4 )
    {
      FltAcquirePushLockExclusiveEx(a3, 0);
      v17 = (void *)a3[2];
      _InterlockedIncrement((volatile signed __int32 *)(a4 + 12));
      a3[2] = a4;
      a3[3] = v5;
      FltReleasePushLockEx(a3, 0);
    }
    SqosTraceStreamHandleContext(v10, v9, (__int64)a3, 0);
    if ( v17 )
      SqospReleaseClient(v17);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140006188  mov     [rsp+arg_10], rbx
0x14000618d  mov     [rsp+arg_8], rdx
0x140006192  mov     [rsp+arg_0], rcx
0x140006197  push    rbp
0x140006198  push    rsi
0x140006199  push    rdi
0x14000619a  push    r12
0x14000619c  push    r13
0x14000619e  push    r14
0x1400061a0  push    r15
0x1400061a2  sub     rsp, 20h
0x1400061a6  xor     r13d, r13d
0x1400061a9  lea     rsi, [r8+8]
0x1400061ad  mov     r15, r9
0x1400061b0  mov     rdi, r8
0x1400061b3  mov     r12, rdx
0x1400061b6  mov     rbp, rcx
0x1400061b9  cmp     [r8+10h], r9
0x1400061bd  jz      short loc_1400061E3
0x1400061bf  mov     rdx, [rsi]
0x1400061c2  mov     r9, rcx
0x1400061c5  mov     rcx, r15; SpinLock
0x1400061c8  xor     r8d, r8d
0x1400061cb  call    SqospLookupFlow
0x1400061d0  mov     r13, rax
0x1400061d3  test    rax, rax
0x1400061d6  jnz     short loc_1400061E3
0x1400061d8  mov     r14d, 0C000009Ah
0x1400061de  jmp     loc_140006304
0x1400061e3  mov     rbx, [rsi]
0x1400061e6  lea     rcx, [rbx+340h]; SpinLock
0x1400061ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400061f4  nop     dword ptr [rax+rax+00h]
0x1400061f9  mov     [rbx+348h], al
0x1400061ff  xor     r8d, r8d
0x140006202  mov     rcx, [rsi]
0x140006205  cmp     [rcx+3A0h], r8b
0x14000620c  jz      short loc_140006216
0x14000620e  mov     r14d, 0C01C000Bh
0x140006214  jmp     short loc_140006289
0x140006216  mov     rax, [rdi+10h]
0x14000621a  lea     rbx, [rdi+20h]
0x14000621e  mov     r12b, [rsp+58h+arg_20]
0x140006226  mov     r14d, r8d
0x140006229  mov     dl, [rax+7Ch]
0x14000622c  test    dl, dl
0x14000622e  jnz     short loc_140006238
0x140006230  mov     rbp, rbx
0x140006233  cmp     [rbx], r8b
0x140006236  jz      short loc_14000625A
0x140006238  cmp     [r15+7Ch], r8b
0x14000623c  jnz     short loc_140006253
0x14000623e  test    r12b, r12b
0x140006241  jnz     short loc_140006253
0x140006243  inc     dword ptr [rcx+394h]
0x140006249  mov     rcx, [rsi]
0x14000624c  call    BalanceUpdateDeviceMode
0x140006251  jmp     short loc_14000627C
0x140006253  mov     rbp, rbx
0x140006256  test    dl, dl
0x140006258  jnz     short loc_14000627C
0x14000625a  cmp     [rbp+0], r8b
0x14000625e  jnz     short loc_140006279
0x140006260  cmp     [r15+7Ch], r8b
0x140006264  jnz     short loc_14000626B
0x140006266  test    r12b, r12b
0x140006269  jz      short loc_140006279
0x14000626b  dec     dword ptr [rcx+394h]
0x140006271  mov     rcx, [rsi]
0x140006274  call    BalanceUpdateDeviceMode
0x140006279  mov     rbx, rbp
0x14000627c  mov     rbp, [rsp+58h+arg_0]
0x140006281  mov     [rbx], r12b
0x140006284  mov     r12, [rsp+58h+arg_8]
0x140006289  mov     rdx, [rdi+8]
0x14000628d  lea     rcx, [rdx+340h]; SpinLock
0x140006294  mov     dl, [rdx+348h]; NewIrql
0x14000629a  call    cs:__imp_KeReleaseSpinLock
0x1400062a1  nop     dword ptr [rax+rax+00h]
0x1400062a6  test    r14d, r14d
0x1400062a9  js      short loc_140006304
0x1400062ab  xor     ebx, ebx
0x1400062ad  cmp     [rdi+10h], r15
0x1400062b1  jz      short loc_1400062E6
0x1400062b3  xor     edx, edx
0x1400062b5  mov     rcx, rdi
0x1400062b8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400062bf  nop     dword ptr [rax+rax+00h]
0x1400062c4  mov     rbx, [rdi+10h]
0x1400062c8  lock inc dword ptr [r15+0Ch]
0x1400062cd  xor     edx, edx
0x1400062cf  mov     [rdi+10h], r15
0x1400062d3  mov     rcx, rdi
0x1400062d6  mov     [rdi+18h], r13
0x1400062da  call    cs:__imp_FltReleasePushLockEx
0x1400062e1  nop     dword ptr [rax+rax+00h]
0x1400062e6  xor     r9d, r9d
0x1400062e9  mov     r8, rdi
0x1400062ec  mov     rdx, r12
0x1400062ef  mov     rcx, rbp
0x1400062f2  call    SqosTraceStreamHandleContext
0x1400062f7  test    rbx, rbx
0x1400062fa  jz      short loc_140006304
0x1400062fc  mov     rcx, rbx; Entry
0x1400062ff  call    SqospReleaseClient
0x140006304  mov     rbx, [rsp+58h+arg_10]
0x140006309  mov     eax, r14d
0x14000630c  add     rsp, 20h
0x140006310  pop     r15
0x140006312  pop     r14
0x140006314  pop     r13
0x140006316  pop     r12
0x140006318  pop     rdi
0x140006319  pop     rsi
0x14000631a  pop     rbp
0x14000631b  retn
```
