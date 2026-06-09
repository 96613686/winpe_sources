# RtlWriteULongToUser

- ea: `0x1400fc808`
- end: `0x1400fc846`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x14003fcfc`
- `0x140040250`
- `0x1400406a4`
- `0x140042074`
- `0x140042e68`
- `0x140043038`
- `0x140043654`
- `0x1400440b4`
- `0x140065654`
- `0x140067ecc`
- `0x1400883a4`
- `0x140097f38`
- `0x1400adaf8`
- `0x1400aee6c`
- `0x1400af1cc`
- `0x1400af910`
- `0x1400afc7c`
- `0x1400afd58`
- `0x1400afe90`
- `0x1400b0bc0`
- `0x1400b1390`
- `0x1400b17a4`
- `0x1400b6c24`
- `0x1400c3614`
- `0x1400fc1a8`
- `0x1401070b0`

## callees

- `0x1400442ac`
- `0x1400fc808`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x1400fc808  mov     [rsp+arg_0], rbx
0x1400fc80d  push    rdi
0x1400fc80e  sub     rsp, 20h
0x1400fc812  mov     rax, cs:qword_14010C430
0x1400fc819  mov     edi, edx
0x1400fc81b  mov     rbx, rcx
0x1400fc81e  test    rax, rax
0x1400fc821  jz      short loc_1400FC82A
0x1400fc823  call    rax ; qword_14010C430
0x1400fc825  nop     dword ptr [rax]
0x1400fc828  jmp     short loc_1400FC83A
0x1400fc82a  mov     edx, 4; Length
0x1400fc82f  lea     r8d, [rdx-3]; Alignment
0x1400fc833  call    ProbeForRead
0x1400fc838  mov     [rbx], edi
0x1400fc83a  mov     rbx, [rsp+28h+arg_0]
0x1400fc83f  add     rsp, 20h
0x1400fc843  pop     rdi
0x1400fc844  retn
```
