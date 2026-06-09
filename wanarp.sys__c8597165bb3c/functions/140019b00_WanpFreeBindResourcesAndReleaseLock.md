# WanpFreeBindResourcesAndReleaseLock

- ea: `0x140019b00`
- end: `0x140019bac`
- name: `WanpFreeBindResourcesAndReleaseLock`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017010`
- `0x140019970`

## callees

- `0x1400028b0`
- `0x14000d010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019b58`

## pseudocode

```c
LONG __fastcall WanpFreeBindResourcesAndReleaseLock(char a1)
{
  wchar_t *Buffer; // rcx
  wchar_t **p_Buffer; // rax
  PVOID v4; // rcx
  __int64 *v5; // rax
  char *v6; // rax

  Buffer = (wchar_t *)qword_1400099F8;
  if ( !a1 )
    Buffer = DestinationString.Buffer;
  ExFreePoolWithTag(Buffer, 0);
  p_Buffer = (wchar_t **)&qword_1400099F8;
  if ( !a1 )
    p_Buffer = &DestinationString.Buffer;
  *p_Buffer = 0;
  v4 = (PVOID)qword_140009A08;
  if ( !a1 )
    v4 = qword_140009B28;
  ExFreePoolWithTag(v4, 0);
  v5 = &qword_140009A08;
  if ( !a1 )
    v5 = (__int64 *)&qword_140009B28;
  *v5 = 0;
  v6 = &byte_140009A2C;
  if ( !a1 )
    v6 = &byte_140009B4C;
  *v6 = 1;
  WanpRemoveAllConnections(a1);
  return WanpRemoveAllAdapters(a1);
}

```

## disassembly

```asm
0x140019b00  mov     [rsp+arg_0], rbx
0x140019b05  push    rdi
0x140019b06  sub     rsp, 20h
0x140019b0a  movzx   ebx, cl
0x140019b0d  mov     rcx, cs:qword_1400099F8
0x140019b14  test    bl, bl
0x140019b16  cmovz   rcx, cs:DestinationString.Buffer; P
0x140019b1e  xor     edx, edx; Tag
0x140019b20  call    cs:__imp_ExFreePoolWithTag
0x140019b27  nop     dword ptr [rax+rax+00h]
0x140019b2c  test    bl, bl
0x140019b2e  lea     rcx, DestinationString.Buffer
0x140019b35  lea     rax, qword_1400099F8
0x140019b3c  cmovz   rax, rcx
0x140019b40  xor     edi, edi
0x140019b42  test    bl, bl
0x140019b44  mov     [rax], rdi
0x140019b47  mov     rcx, cs:qword_140009A08
0x140019b4e  cmovz   rcx, cs:qword_140009B28; P
0x140019b56  xor     edx, edx; Tag
0x140019b58  call    cs:__imp_ExFreePoolWithTag
0x140019b5f  nop     dword ptr [rax+rax+00h]
0x140019b64  test    bl, bl
0x140019b66  lea     rcx, qword_140009B28
0x140019b6d  lea     rax, qword_140009A08
0x140019b74  cmovz   rax, rcx
0x140019b78  lea     rcx, byte_140009B4C
0x140019b7f  mov     [rax], rdi
0x140019b82  lea     rax, byte_140009A2C
0x140019b89  cmovz   rax, rcx
0x140019b8d  movzx   ecx, bl
0x140019b90  mov     byte ptr [rax], 1
0x140019b93  call    WanpRemoveAllConnections
0x140019b98  movzx   ecx, bl
0x140019b9b  call    WanpRemoveAllAdapters
0x140019ba0  mov     rbx, [rsp+28h+arg_0]
0x140019ba5  add     rsp, 20h
0x140019ba9  pop     rdi
0x140019baa  retn
```
