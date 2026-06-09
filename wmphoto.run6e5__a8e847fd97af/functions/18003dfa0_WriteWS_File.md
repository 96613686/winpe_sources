# WriteWS_File

- ea: `0x18003dfa0`
- end: `0x18003dfd9`
- name: `WriteWS_File`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003dfa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003dfc2`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003dfc2`

## pseudocode

```c
__int64 __fastcall WriteWS_File(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = 0;
  if ( a3 )
    return _o_fwrite(a2, a3, 1, *a1) != 1 ? 0xFFFFFF9A : 0;
  return result;
}

```

## disassembly

```asm
0x18003dfa0  push    rbx
0x18003dfa2  sub     rsp, 20h
0x18003dfa6  xor     eax, eax
0x18003dfa8  mov     r10, r8
0x18003dfab  mov     r11, rdx
0x18003dfae  test    r8, r8
0x18003dfb1  jz      short loc_18003DFD3
0x18003dfb3  mov     r9, [rcx]
0x18003dfb6  lea     ebx, [rax+1]
0x18003dfb9  mov     r8d, ebx
0x18003dfbc  mov     rdx, r10
0x18003dfbf  mov     rcx, r11
0x18003dfc2  call    cs:__imp__o_fwrite
0x18003dfc8  sub     rbx, rax
0x18003dfcb  neg     rbx
0x18003dfce  sbb     eax, eax
0x18003dfd0  and     eax, 0FFFFFF9Ah
0x18003dfd3  add     rsp, 20h
0x18003dfd7  pop     rbx
0x18003dfd8  retn
```
