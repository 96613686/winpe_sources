# DupOleString

- ea: `0x1800235a8`
- end: `0x180023617`
- name: `DupOleString`
- size: `111`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001ed0`
- `0x180029a20`

## callees

- `0x1800235a8`
- `0x180032c52`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800235e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800235e4`

## pseudocode

```c
__int64 __fastcall DupOleString(_WORD *Src, _QWORD *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  SIZE_T v6; // rbp
  void *v7; // rax
  void *v8; // rdi

  *a2 = 0;
  if ( !Src )
    return 2147942487LL;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  v6 = (unsigned int)(2 * v5 + 2);
  v7 = CoTaskMemAlloc(v6);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, Src, v6);
  result = 0;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x1800235a8  push    rbx
0x1800235aa  push    rbp
0x1800235ab  push    rsi
0x1800235ac  push    rdi
0x1800235ad  push    r14
0x1800235af  sub     rsp, 20h
0x1800235b3  xor     r14d, r14d
0x1800235b6  mov     rsi, rdx
0x1800235b9  mov     [rdx], r14
0x1800235bc  mov     rbx, rcx
0x1800235bf  test    rcx, rcx
0x1800235c2  jnz     short loc_1800235CB
0x1800235c4  mov     eax, 80070057h
0x1800235c9  jmp     short loc_18002360C
0x1800235cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800235cf  inc     rax
0x1800235d2  cmp     [rcx+rax*2], r14w
0x1800235d7  jnz     short loc_1800235CF
0x1800235d9  lea     eax, ds:2[rax*2]
0x1800235e0  mov     ecx, eax; cb
0x1800235e2  mov     ebp, eax
0x1800235e4  call    cs:__imp_CoTaskMemAlloc
0x1800235ea  mov     rdi, rax
0x1800235ed  test    rax, rax
0x1800235f0  jnz     short loc_1800235F9
0x1800235f2  mov     eax, 8007000Eh
0x1800235f7  jmp     short loc_18002360C
0x1800235f9  mov     r8, rbp; Size
0x1800235fc  mov     rdx, rbx; Src
0x1800235ff  mov     rcx, rdi; void *
0x180023602  call    memcpy_0
0x180023607  xor     eax, eax
0x180023609  mov     [rsi], rdi
0x18002360c  add     rsp, 20h
0x180023610  pop     r14
0x180023612  pop     rdi
0x180023613  pop     rsi
0x180023614  pop     rbp
0x180023615  pop     rbx
0x180023616  retn
```
