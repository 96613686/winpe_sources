# RtlReadULong64FromUser

- ea: `0x1400fc664`
- end: `0x1400fc698`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `51`
- callee_count: `2`
- tags: ``

## callers

- `0x1400134f4`
- `0x140040250`
- `0x1400406a4`
- `0x140041574`
- `0x140041da8`
- `0x140041f2c`
- `0x140042200`
- `0x140042eec`
- `0x14004491c`
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
- `0x140086dd4`
- `0x1400972bc`
- `0x14009760c`
- `0x140097804`
- `0x140097b94`
- `0x14009c7dc`
- `0x1400a0988`
- `0x1400ad0a4`
- `0x1400ad5c4`
- `0x1400ae76c`
- `0x1400aed8c`
- `0x1400aeeec`
- `0x1400af72c`
- `0x1400af7f8`
- `0x1400afc7c`
- `0x1400afd58`
- `0x1400afebc`
- `0x1400b00bc`
- `0x1400b173c`
- `0x1400b1f70`
- `0x1400b2690`
- `0x1400b4be8`
- `0x1400bb42c`
- `0x1400bc1b4`
- `0x1400bdb3c`
- `0x1400be064`
- `0x1400be910`
- `0x1400c2b18`
- `0x1400dc610`
- `0x1400fee4c`

## callees

- `0x1400442ac`
- `0x1400fc664`

## pseudocode

```c
__int64 __fastcall RtlReadULong64FromUser(volatile void *a1)
{
  ProbeForRead(a1, 8u, 1u);
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1400fc664  push    rbx
0x1400fc666  sub     rsp, 20h
0x1400fc66a  mov     rax, cs:qword_14010C438
0x1400fc671  mov     rbx, rcx
0x1400fc674  test    rax, rax
0x1400fc677  jz      short loc_1400FC680
0x1400fc679  call    rax ; qword_14010C438
0x1400fc67b  nop     dword ptr [rax]
0x1400fc67e  jmp     short loc_1400FC691
0x1400fc680  mov     edx, 8; Length
0x1400fc685  lea     r8d, [rdx-7]; Alignment
0x1400fc689  call    ProbeForRead
0x1400fc68e  mov     rax, [rbx]
0x1400fc691  add     rsp, 20h
0x1400fc695  pop     rbx
0x1400fc696  retn
```
