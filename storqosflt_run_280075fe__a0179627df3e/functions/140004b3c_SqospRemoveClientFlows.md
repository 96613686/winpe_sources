# SqospRemoveClientFlows

- ea: `0x140004b3c`
- end: `0x140004bdd`
- name: `SqospRemoveClientFlows`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015810`

## callees

- `0x140004b3c`
- `0x140004be4`
- `0x1400110c4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004bb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004bb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004b8c`

## pseudocode

```c
void __fastcall SqospRemoveClientFlows(__int64 a1)
{
  _QWORD **v2; // r14
  _QWORD *v3; // rsi
  _QWORD *v4; // rax
  __int64 v5; // rdi

  v2 = (_QWORD **)(a1 + 104);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    v3[1] = 0;
    *v3 = 0;
    --*(_DWORD *)(a1 + 120);
    v5 = *(v3 - 5);
    *(_BYTE *)(v5 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 832));
    BalanceFinalizeFlow(v3 - 5);
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 832), *(_BYTE *)(v5 + 840));
    SqospCleanupFlow(v3 - 5, v5);
  }
}

```

## disassembly

```asm
0x140004b3c  push    rbx
0x140004b3e  push    rbp
0x140004b3f  push    rsi
0x140004b40  push    rdi
0x140004b41  push    r14
0x140004b43  sub     rsp, 20h
0x140004b47  mov     rbp, rcx
0x140004b4a  lea     r14, [rcx+68h]
0x140004b4e  mov     rsi, [r14]
0x140004b51  cmp     rsi, r14
0x140004b54  jz      short loc_140004BD1
0x140004b56  cmp     [rsi+8], r14
0x140004b5a  jnz     short loc_140004BCA
0x140004b5c  mov     rax, [rsi]
0x140004b5f  cmp     [rax+8], rsi
0x140004b63  jnz     short loc_140004BCA
0x140004b65  mov     [r14], rax
0x140004b68  mov     [rax+8], r14
0x140004b6c  mov     qword ptr [rsi+8], 0
0x140004b74  mov     qword ptr [rsi], 0
0x140004b7b  dec     dword ptr [rbp+78h]
0x140004b7e  mov     rdi, [rsi-28h]
0x140004b82  lea     rbx, [rdi+340h]
0x140004b89  mov     rcx, rbx; SpinLock
0x140004b8c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004b93  nop     dword ptr [rax+rax+00h]
0x140004b98  lea     rcx, [rsi-28h]
0x140004b9c  mov     [rdi+348h], al
0x140004ba2  call    BalanceFinalizeFlow
0x140004ba7  mov     dl, [rdi+348h]; NewIrql
0x140004bad  mov     rcx, rbx; SpinLock
0x140004bb0  call    cs:__imp_KeReleaseSpinLock
0x140004bb7  nop     dword ptr [rax+rax+00h]
0x140004bbc  mov     rdx, rdi
0x140004bbf  lea     rcx, [rsi-28h]; Entry
0x140004bc3  call    SqospCleanupFlow
0x140004bc8  jmp     short loc_140004B4E
0x140004bca  mov     ecx, 3
0x140004bcf  int     29h; Win8: RtlFailFast(ecx)
0x140004bd1  add     rsp, 20h
0x140004bd5  pop     r14
0x140004bd7  pop     rdi
0x140004bd8  pop     rsi
0x140004bd9  pop     rbp
0x140004bda  pop     rbx
0x140004bdb  retn
```
