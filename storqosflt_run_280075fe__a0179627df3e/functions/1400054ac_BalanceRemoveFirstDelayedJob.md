# BalanceRemoveFirstDelayedJob

- ea: `0x1400054ac`
- end: `0x140005539`
- name: `BalanceRemoveFirstDelayedJob`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005384`
- `0x140005414`

## callees

- `0x1400054ac`

## import_xrefs

- `FLTMGR!FltCbdqRemoveIo` at `0x140005510`
- `FLTMGR!FltCbdqRemoveIo` at `0x140005510`

## pseudocode

```c
_QWORD *__fastcall BalanceRemoveFirstDelayedJob(_QWORD *a1)
{
  _QWORD *v1; // rdx
  _QWORD *v2; // rax
  __int64 v3; // r8
  _QWORD *v4; // rbx
  __int64 v5; // rcx

  v1 = a1 + 18;
  v2 = (_QWORD *)a1[18];
  if ( (_QWORD *)v2[1] != a1 + 18 || (v3 = *v2, *(_QWORD **)(*v2 + 8LL) != v2) )
    __fastfail(3u);
  *v1 = v3;
  v4 = v2 - 10;
  *(_QWORD *)(v3 + 8) = v1;
  v2[1] = 0;
  *v2 = 0;
  *(_QWORD *)(*a1 + 952LL) -= v2[9];
  v5 = *(v2 - 6);
  *((_BYTE *)v2 + 50) = 0;
  if ( !FltCbdqRemoveIo(
          (PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(v5 + 8) + 480LL),
          (PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT)v2 - 3) )
    *((_BYTE *)v4 + 132) = 1;
  return v4;
}

```

## disassembly

```asm
0x1400054ac  push    rbx
0x1400054ae  sub     rsp, 20h
0x1400054b2  lea     rdx, [rcx+90h]
0x1400054b9  mov     rax, [rdx]
0x1400054bc  cmp     [rax+8], rdx
0x1400054c0  jnz     short loc_140005532
0x1400054c2  mov     r8, [rax]
0x1400054c5  cmp     [r8+8], rax
0x1400054c9  jnz     short loc_140005532
0x1400054cb  mov     [rdx], r8
0x1400054ce  lea     rbx, [rax-50h]
0x1400054d2  mov     [r8+8], rdx
0x1400054d6  lea     rdx, [rbx+8]; Context
0x1400054da  mov     qword ptr [rax+8], 0
0x1400054e2  mov     qword ptr [rax], 0
0x1400054e9  mov     rcx, [rcx]
0x1400054ec  mov     rax, [rbx+98h]
0x1400054f3  sub     [rcx+3B8h], rax
0x1400054fa  mov     rcx, [rbx+20h]
0x1400054fe  mov     byte ptr [rbx+82h], 0
0x140005505  mov     rcx, [rcx+8]
0x140005509  add     rcx, 1E0h; Cbdq
0x140005510  call    cs:__imp_FltCbdqRemoveIo
0x140005517  nop     dword ptr [rax+rax+00h]
0x14000551c  test    rax, rax
0x14000551f  jnz     short loc_140005528
0x140005521  mov     byte ptr [rbx+84h], 1
0x140005528  mov     rax, rbx
0x14000552b  add     rsp, 20h
0x14000552f  pop     rbx
0x140005530  retn
0x140005532  mov     ecx, 3
0x140005537  int     29h; Win8: RtlFailFast(ecx)
```
