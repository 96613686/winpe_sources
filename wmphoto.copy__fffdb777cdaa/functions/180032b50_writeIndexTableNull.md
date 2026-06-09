# writeIndexTableNull

- ea: `0x180032b50`
- end: `0x180032bfd`
- name: `writeIndexTableNull`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007340`
- `0x1800309d0`

## callees

- `0x18000290c`
- `0x180003760`
- `0x180032b50`

## pseudocode

```c
__int64 __fastcall writeIndexTableNull(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // r8

  if ( !*(_QWORD *)(a1 + 34480) )
  {
    v2 = *(_QWORD *)(a1 + 34368);
    if ( *(_DWORD *)(a1 + 160) )
    {
      PutVLWordEsc(v2, 0, 4);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33020), 8);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33021), v3);
      putBit16z(v2, 0, 15);
      putBit16z(v2, 1, 1);
    }
    else
    {
      PutVLWordEsc(v2, 255, 0);
    }
    putBit16z(v2, 0, -*(_DWORD *)(v2 + 8) & 7);
  }
  return 0;
}

```

## disassembly

```asm
0x180032b50  mov     [rsp+arg_0], rbx
0x180032b55  push    rdi
0x180032b56  sub     rsp, 20h
0x180032b5a  cmp     qword ptr [rcx+86B0h], 0
0x180032b62  mov     rdi, rcx
0x180032b65  jnz     loc_180032BF0
0x180032b6b  mov     rbx, [rcx+8640h]
0x180032b72  cmp     dword ptr [rcx+0A0h], 0
0x180032b79  mov     rcx, rbx
0x180032b7c  jz      short loc_180032BCE
0x180032b7e  xor     edx, edx
0x180032b80  lea     r8d, [rdx+4]
0x180032b84  call    PutVLWordEsc
0x180032b89  movzx   edx, byte ptr [rdi+80FCh]
0x180032b90  mov     r8d, 8
0x180032b96  mov     rcx, rbx
0x180032b99  call    putBit16z
0x180032b9e  movzx   edx, byte ptr [rdi+80FDh]
0x180032ba5  mov     rcx, rbx
0x180032ba8  call    putBit16z
0x180032bad  xor     edx, edx
0x180032baf  mov     rcx, rbx
0x180032bb2  lea     r8d, [rdx+0Fh]
0x180032bb6  call    putBit16z
0x180032bbb  mov     r8d, 1
0x180032bc1  mov     rcx, rbx
0x180032bc4  mov     edx, r8d
0x180032bc7  call    putBit16z
0x180032bcc  jmp     short loc_180032BDB
0x180032bce  xor     r8d, r8d
0x180032bd1  mov     edx, 0FFh
0x180032bd6  call    PutVLWordEsc
0x180032bdb  mov     r8d, [rbx+8]
0x180032bdf  xor     edx, edx
0x180032be1  neg     r8d
0x180032be4  mov     rcx, rbx
0x180032be7  and     r8d, 7
0x180032beb  call    putBit16z
0x180032bf0  mov     rbx, [rsp+28h+arg_0]
0x180032bf5  xor     eax, eax
0x180032bf7  add     rsp, 20h
0x180032bfb  pop     rdi
0x180032bfc  retn
```
