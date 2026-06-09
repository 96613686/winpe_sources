# ChangeIdleState

- ea: `0x14000773c`
- end: `0x14000783c`
- name: `ChangeIdleState`
- size: `256`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140004f50`
- `0x140005eb0`
- `0x140006d40`
- `0x140007170`
- `0x1400145e0`

## callees

- `0x140007020`
- `0x14000773c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007762`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007762`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077a2`
- `ntoskrnl!KeSetEvent` at `0x1400077e6`
- `ntoskrnl!KeSetEvent` at `0x1400077e6`
- `ntoskrnl!KeResetEvent` at `0x1400077c6`
- `ntoskrnl!KeResetEvent` at `0x1400077c6`

## pseudocode

```c
void __fastcall ChangeIdleState(__int64 a1, int a2, char a3)
{
  KSPIN_LOCK *v3; // rbp
  KIRQL v7; // si

  v3 = (KSPIN_LOCK *)(a1 + 696);
  if ( a3 )
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 696));
  else
    v7 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qLL(
      *(_QWORD *)(a1 + 1368),
      4u,
      7u,
      0x37u,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      *(_QWORD *)(a1 + 32),
      *(_DWORD *)(a1 + 688),
      a2);
  if ( *(_DWORD *)(a1 + 688) == 4 )
  {
    if ( a2 == 5 )
      KeResetEvent((PRKEVENT)(a1 + 872));
  }
  else if ( *(_DWORD *)(a1 + 688) == 5 )
  {
    *(_DWORD *)(a1 + 688) = a2;
    KeSetEvent((PRKEVENT)(a1 + 872), 0, 0);
  }
  *(_DWORD *)(a1 + 688) = a2;
  if ( a3 )
    KeReleaseSpinLock(v3, v7);
}

```

## disassembly

```asm
0x14000773c  push    rbx
0x14000773e  push    rbp
0x14000773f  push    rsi
0x140007740  push    rdi
0x140007741  push    r14
0x140007743  sub     rsp, 40h
0x140007747  lea     rbp, [rcx+2B8h]
0x14000774e  mov     r14b, r8b
0x140007751  mov     edi, edx
0x140007753  mov     rbx, rcx
0x140007756  test    r8b, r8b
0x140007759  jz      loc_140007834
0x14000775f  mov     rcx, rbp; SpinLock
0x140007762  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007769  nop     dword ptr [rax+rax+00h]
0x14000776e  mov     sil, al
0x140007771  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007778  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000777f  jnz     short loc_1400077F4
0x140007781  mov     ecx, [rbx+2B0h]
0x140007787  sub     ecx, 4
0x14000778a  jz      short loc_1400077BA
0x14000778c  cmp     ecx, 1
0x14000778f  jz      short loc_1400077D4
0x140007791  mov     [rbx+2B0h], edi
0x140007797  test    r14b, r14b
0x14000779a  jz      short loc_1400077AE
0x14000779c  mov     dl, sil; NewIrql
0x14000779f  mov     rcx, rbp; SpinLock
0x1400077a2  call    cs:__imp_KeReleaseSpinLock
0x1400077a9  nop     dword ptr [rax+rax+00h]
0x1400077ae  add     rsp, 40h
0x1400077b2  pop     r14
0x1400077b4  pop     rdi
0x1400077b5  pop     rsi
0x1400077b6  pop     rbp
0x1400077b7  pop     rbx
0x1400077b8  retn
0x1400077ba  cmp     edi, 5
0x1400077bd  jnz     short loc_140007791
0x1400077bf  lea     rcx, [rbx+368h]; Event
0x1400077c6  call    cs:__imp_KeResetEvent
0x1400077cd  nop     dword ptr [rax+rax+00h]
0x1400077d2  jmp     short loc_140007791
0x1400077d4  lea     rcx, [rbx+368h]; Event
0x1400077db  mov     [rbx+2B0h], edi
0x1400077e1  xor     r8d, r8d; Wait
0x1400077e4  xor     edx, edx; Increment
0x1400077e6  call    cs:__imp_KeSetEvent
0x1400077ed  nop     dword ptr [rax+rax+00h]
0x1400077f2  jmp     short loc_140007791
0x1400077f4  mov     eax, [rbx+2B0h]
0x1400077fa  mov     r9d, 37h ; '7'
0x140007800  mov     rcx, [rbx+558h]
0x140007807  mov     dl, 4
0x140007809  mov     [rsp+68h+var_30], edi
0x14000780d  mov     [rsp+68h+var_38], eax
0x140007811  mov     rax, [rbx+20h]
0x140007815  lea     r8d, [r9-30h]
0x140007819  mov     [rsp+68h+var_40], rax
0x14000781e  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140007825  mov     [rsp+68h+var_48], rax
0x14000782a  call    WPP_RECORDER_SF_qLL
0x14000782f  jmp     loc_140007781
0x140007834  xor     sil, sil
0x140007837  jmp     loc_140007771
```
