# SqospFreeUnicodeString

- ea: `0x140003ec0`
- end: `0x140003ef6`
- name: `SqospFreeUnicodeString`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e88`
- `0x140006424`
- `0x140011008`
- `0x1400110c4`
- `0x1400111bc`
- `0x140011b00`
- `0x1400158a0`

## callees

- `0x140003ec0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003ed7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ed7`

## pseudocode

```c
__int64 __fastcall SqospFreeUnicodeString(__int64 a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *(void **)(a1 + 8);
  if ( v2 )
    ExFreePoolWithTag(v2, 0x46535153u);
  result = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140003ec0  push    rbx
0x140003ec2  sub     rsp, 20h
0x140003ec6  mov     rbx, rcx
0x140003ec9  mov     rcx, [rcx+8]; P
0x140003ecd  test    rcx, rcx
0x140003ed0  jz      short loc_140003EE3
0x140003ed2  mov     edx, 46535153h; Tag
0x140003ed7  call    cs:__imp_ExFreePoolWithTag
0x140003ede  nop     dword ptr [rax+rax+00h]
0x140003ee3  xor     eax, eax
0x140003ee5  mov     qword ptr [rbx+8], 0
0x140003eed  mov     [rbx], eax
0x140003eef  add     rsp, 20h
0x140003ef3  pop     rbx
0x140003ef4  retn
```
