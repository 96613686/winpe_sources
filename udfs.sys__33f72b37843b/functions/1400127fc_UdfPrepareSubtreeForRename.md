# UdfPrepareSubtreeForRename

- ea: `0x1400127fc`
- end: `0x1400128ee`
- name: `UdfPrepareSubtreeForRename`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140034450`

## callees

- `0x1400091b8`
- `0x14000c574`
- `0x1400127fc`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001285c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001285c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400128bc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400128bc`

## pseudocode

```c
__int64 __fastcall UdfPrepareSubtreeForRename(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 i; // rdx
  __int64 v5; // rdi
  struct _KTHREAD *CurrentThread; // rbp
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // rbx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = 0;
  v3 = a2;
  for ( i = 0; ; i = v10 )
  {
    result = UdfGetNextScbBottomUp(a1, i, v3, &v11);
    v10 = result;
    if ( result == a2 )
      break;
    if ( *(_WORD *)result == 2355 )
      v5 = *(_QWORD *)(result + 160) - 32LL;
    else
      v5 = v11;
    CurrentThread = KeGetCurrentThread();
    v7 = *(_QWORD *)(result + 136);
    if ( CurrentThread != *(struct _KTHREAD **)(v7 + 64) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v7 + 80) + 216LL));
      *(_QWORD *)(*(_QWORD *)(v10 + 136) + 64LL) = CurrentThread;
    }
    ++*(_DWORD *)(*(_QWORD *)(v10 + 136) + 72LL);
    *(_DWORD *)(v5 + 68) |= 0x200u;
    UdfFreeStringBuffer(v5 + 80);
    --*(_DWORD *)(*(_QWORD *)(v10 + 136) + 72LL);
    v8 = *(_QWORD *)(v10 + 136);
    if ( !*(_DWORD *)(v8 + 72) )
    {
      *(_QWORD *)(v8 + 64) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v10 + 136) + 80LL) + 216LL));
    }
    v3 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1400127fc  mov     [rsp+arg_0], rcx
0x140012801  push    rbx
0x140012802  push    rbp
0x140012803  push    rsi
0x140012804  push    rdi
0x140012805  sub     rsp, 28h
0x140012809  mov     rsi, rdx
0x14001280c  mov     [rsp+48h+arg_0], 0
0x140012815  mov     r8, rdx
0x140012818  xor     edx, edx
0x14001281a  jmp     loc_1400128CE
0x14001281f  mov     eax, 933h
0x140012824  cmp     [rbx], ax
0x140012827  jz      short loc_140012830
0x140012829  mov     rdi, [rsp+48h+arg_0]
0x14001282e  jmp     short loc_14001283B
0x140012830  mov     rdi, [rbx+0A0h]
0x140012837  sub     rdi, 20h ; ' '
0x14001283b  mov     rbp, gs:188h
0x140012844  mov     rcx, [rbx+88h]
0x14001284b  cmp     rbp, [rcx+40h]
0x14001284f  jz      short loc_140012873
0x140012851  mov     rcx, [rcx+50h]
0x140012855  add     rcx, 0D8h; FastMutex
0x14001285c  call    cs:__imp_ExAcquireFastMutex
0x140012863  nop     dword ptr [rax+rax+00h]
0x140012868  mov     rax, [rbx+88h]
0x14001286f  mov     [rax+40h], rbp
0x140012873  mov     rax, [rbx+88h]
0x14001287a  lea     rcx, [rdi+50h]
0x14001287e  inc     dword ptr [rax+48h]
0x140012881  bts     dword ptr [rdi+44h], 9
0x140012886  call    UdfFreeStringBuffer
0x14001288b  mov     rax, [rbx+88h]
0x140012892  dec     dword ptr [rax+48h]
0x140012895  mov     rax, [rbx+88h]
0x14001289c  cmp     dword ptr [rax+48h], 0
0x1400128a0  jnz     short loc_1400128C8
0x1400128a2  mov     qword ptr [rax+40h], 0
0x1400128aa  mov     rax, [rbx+88h]
0x1400128b1  mov     rcx, [rax+50h]
0x1400128b5  add     rcx, 0D8h; FastMutex
0x1400128bc  call    cs:__imp_ExReleaseFastMutex
0x1400128c3  nop     dword ptr [rax+rax+00h]
0x1400128c8  mov     r8, rsi
0x1400128cb  mov     rdx, rbx
0x1400128ce  lea     r9, [rsp+48h+arg_0]
0x1400128d3  call    UdfGetNextScbBottomUp
0x1400128d8  mov     rbx, rax
0x1400128db  cmp     rax, rsi
0x1400128de  jnz     loc_14001281F
0x1400128e4  add     rsp, 28h
0x1400128e8  pop     rdi
0x1400128e9  pop     rsi
0x1400128ea  pop     rbp
0x1400128eb  pop     rbx
0x1400128ec  retn
```
