# UmpoInternalConvertGuidToStringBuffer

- ea: `0x180012864`
- end: `0x1800128db`
- name: `UmpoInternalConvertGuidToStringBuffer`
- size: `119`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001980`
- `0x180003a00`
- `0x18000681c`
- `0x18000cae0`
- `0x180011c1c`
- `0x180011f4c`
- `0x180012254`
- `0x180013808`
- `0x180014300`
- `0x180014440`

## callees

- `0x180012864`

## pseudocode

```c
__int64 __fastcall UmpoInternalConvertGuidToStringBuffer(__int64 a1, _WORD *a2)
{
  __int64 i; // r9
  __int64 v4; // rax
  __int64 result; // rax

  for ( i = 0; i != 20; ++i )
  {
    v4 = *((unsigned __int8 *)qword_18001D1E0 + i);
    if ( (_BYTE)v4 == 45 )
    {
      *a2 = 45;
    }
    else
    {
      *a2 = a0123456789abcd[(unsigned __int64)*(unsigned __int8 *)(v4 + a1) >> 4];
      a2[1] = a0123456789abcd[*(_BYTE *)(v4 + a1) & 0xF];
      ++a2;
    }
    ++a2;
  }
  result = 0;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180012864  mov     [rsp+arg_0], rbx
0x180012869  xor     r9d, r9d
0x18001286c  lea     rbx, __ImageBase
0x180012873  mov     r8, rdx
0x180012876  mov     r10, rcx
0x180012879  lea     r11d, [r9+2Dh]
0x18001287d  movzx   eax, byte ptr [r9+rbx+1D1E0h]
0x180012886  cmp     al, r11b
0x180012889  jnz     short loc_180012891
0x18001288b  mov     [r8], r11w
0x18001288f  jmp     short loc_1800128C2
0x180012891  mov     rcx, rax
0x180012894  movzx   eax, byte ptr [rax+r10]
0x180012899  shr     rax, 4
0x18001289d  movzx   eax, word ptr ds:rva a0123456789abcd[rbx+rax*2]; "0123456789ABCDEF" ...
0x1800128a5  mov     [r8], ax
0x1800128a9  movzx   eax, byte ptr [rcx+r10]
0x1800128ae  and     eax, 0Fh
0x1800128b1  movzx   eax, word ptr ds:rva a0123456789abcd[rbx+rax*2]; "0123456789ABCDEF" ...
0x1800128b9  mov     [r8+2], ax
0x1800128be  add     r8, 2
0x1800128c2  add     r8, 2
0x1800128c6  inc     r9
0x1800128c9  cmp     r9, 14h
0x1800128cd  jnz     short loc_18001287D
0x1800128cf  mov     rbx, [rsp+arg_0]
0x1800128d4  xor     eax, eax
0x1800128d6  mov     [r8], ax
0x1800128da  retn
```
