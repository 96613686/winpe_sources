# RemoveTrailingSpaces(ushort *)

- ea: `0x1800231a0`
- end: `0x1800231cc`
- name: `?RemoveTrailingSpaces@@YAXPEAG@Z`
- size: `44`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800222b4`

## callees

- `0x18000134e`
- `0x1800231a0`

## pseudocode

```c
void __fastcall RemoveTrailingSpaces(unsigned __int16 *a1)
{
  wchar_t *i; // rax

  for ( i = wcschr_0(a1, 0); *--i == 32 && i > a1; *i = 0 )
    ;
}

```

## disassembly

```asm
0x1800231a0  push    rbx
0x1800231a2  sub     rsp, 20h
0x1800231a6  xor     edx, edx; Ch
0x1800231a8  mov     rbx, rcx
0x1800231ab  call    wcschr_0
0x1800231b0  jmp     short loc_1800231BC
0x1800231b2  cmp     rax, rbx
0x1800231b5  jbe     short loc_1800231C6
0x1800231b7  xor     ecx, ecx
0x1800231b9  mov     [rax], cx
0x1800231bc  sub     rax, 2
0x1800231c0  cmp     word ptr [rax], 20h ; ' '
0x1800231c4  jz      short loc_1800231B2
0x1800231c6  add     rsp, 20h
0x1800231ca  pop     rbx
0x1800231cb  retn
```
