# RtlWriteULong64ToUser

- ea: `0x1400fc7c0`
- end: `0x1400fc800`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `54`
- callee_count: `2`
- tags: ``

## callers

- `0x140021428`
- `0x140033b58`
- `0x140040250`
- `0x1400406a4`
- `0x140041574`
- `0x1400416dc`
- `0x140041da8`
- `0x140042074`
- `0x1400423a8`
- `0x1400428d8`
- `0x140042eec`
- `0x140043654`
- `0x14005bd70`
- `0x14005c1e0`
- `0x14005c7e4`
- `0x14005c8fc`
- `0x14005c98c`
- `0x14005cad8`
- `0x140064ea0`
- `0x1400651cc`
- `0x140065654`
- `0x140067ecc`
- `0x1400839bc`
- `0x140086c2c`
- `0x140086dd4`
- `0x14008969c`
- `0x140089b8c`
- `0x1400961bc`
- `0x14009760c`
- `0x140097804`
- `0x1400a0988`
- `0x1400ad0a4`
- `0x1400ad5c4`
- `0x1400adaf8`
- `0x1400adfe8`
- `0x1400aee6c`
- `0x1400af1cc`
- `0x1400af528`
- `0x1400afc7c`
- `0x1400afd58`
- `0x1400afebc`
- `0x1400b00bc`
- `0x1400b068c`
- `0x1400b1390`
- `0x1400b173c`
- `0x1400b17a4`
- `0x1400b4ac0`
- `0x1400b6b80`
- `0x1400b6c24`
- `0x1400bc1b4`

## callees

- `0x1400442ac`
- `0x1400fc7c0`

## pseudocode

```c
void __fastcall RtlWriteULong64ToUser(_QWORD *a1, __int64 a2)
{
  ProbeForRead(a1, 8u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x1400fc7c0  mov     [rsp+arg_0], rbx
0x1400fc7c5  push    rdi
0x1400fc7c6  sub     rsp, 20h
0x1400fc7ca  mov     rax, cs:qword_14010C440
0x1400fc7d1  mov     rdi, rdx
0x1400fc7d4  mov     rbx, rcx
0x1400fc7d7  test    rax, rax
0x1400fc7da  jz      short loc_1400FC7E3
0x1400fc7dc  call    rax ; qword_14010C440
0x1400fc7de  nop     dword ptr [rax]
0x1400fc7e1  jmp     short loc_1400FC7F4
0x1400fc7e3  mov     edx, 8; Length
0x1400fc7e8  lea     r8d, [rdx-7]; Alignment
0x1400fc7ec  call    ProbeForRead
0x1400fc7f1  mov     [rbx], rdi
0x1400fc7f4  mov     rbx, [rsp+28h+arg_0]
0x1400fc7f9  add     rsp, 20h
0x1400fc7fd  pop     rdi
0x1400fc7fe  retn
```
