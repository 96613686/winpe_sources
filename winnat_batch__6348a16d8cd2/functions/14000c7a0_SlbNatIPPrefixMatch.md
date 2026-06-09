# SlbNatIPPrefixMatch

- ea: `0x14000c7a0`
- end: `0x14000c7ff`
- name: `SlbNatIPPrefixMatch`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002e0c0`
- `0x14002e560`
- `0x1400300c4`
- `0x1400308ac`
- `0x140032e78`
- `0x140033cc8`

## callees

- `0x14000c7a0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000c7bc`
- `ntoskrnl!RtlCompareMemory` at `0x14000c7bc`

## pseudocode

```c
bool __fastcall SlbNatIPPrefixMatch(const void *a1, const void *a2, unsigned __int16 a3)
{
  char v3; // bl
  SIZE_T v6; // rdi
  int v8; // ebx

  v3 = a3;
  v6 = (unsigned __int64)a3 >> 3;
  if ( RtlCompareMemory(a1, a2, v6) < v6 )
    return 0;
  v8 = v3 & 7;
  return !v8 || *((_BYTE *)a1 + v6) >> (8 - v8) == *((_BYTE *)a2 + v6) >> (8 - v8);
}

```

## disassembly

```asm
0x14000c7a0  push    rbx
0x14000c7a2  push    rbp
0x14000c7a3  push    rsi
0x14000c7a4  push    rdi
0x14000c7a5  sub     rsp, 28h
0x14000c7a9  movzx   ebx, r8w
0x14000c7ad  mov     rsi, rdx
0x14000c7b0  mov     edi, ebx
0x14000c7b2  mov     rbp, rcx
0x14000c7b5  shr     rdi, 3
0x14000c7b9  mov     r8, rdi; Length
0x14000c7bc  call    cs:__imp_RtlCompareMemory
0x14000c7c3  nop     dword ptr [rax+rax+00h]
0x14000c7c8  cmp     rax, rdi
0x14000c7cb  jnb     short loc_14000C7D1
0x14000c7cd  xor     al, al
0x14000c7cf  jmp     short loc_14000C7F5
0x14000c7d1  and     ebx, 7
0x14000c7d4  jz      short loc_14000C7F3
0x14000c7d6  mov     dl, [rdi+rbp]
0x14000c7d9  mov     r8d, 8
0x14000c7df  mov     al, [rdi+rsi]
0x14000c7e2  sub     r8b, bl
0x14000c7e5  mov     cl, r8b
0x14000c7e8  shr     al, cl
0x14000c7ea  shr     dl, cl
0x14000c7ec  cmp     dl, al
0x14000c7ee  setz    al
0x14000c7f1  jmp     short loc_14000C7F5
0x14000c7f3  mov     al, 1
0x14000c7f5  add     rsp, 28h
0x14000c7f9  pop     rdi
0x14000c7fa  pop     rsi
0x14000c7fb  pop     rbp
0x14000c7fc  pop     rbx
0x14000c7fd  retn
```
