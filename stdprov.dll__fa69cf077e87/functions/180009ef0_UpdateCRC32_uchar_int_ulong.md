# UpdateCRC32(uchar *,int,ulong)

- ea: `0x180009ef0`
- end: `0x180009f2f`
- name: `?UpdateCRC32@@YAKPEAEHK@Z`
- size: `63`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180009dd0`
- `0x180013904`
- `0x180013a68`
- `0x180013bb4`

## callees

- `0x180009ef0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdateCRC32(unsigned __int8 *a1, int a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 i; // rdx
  unsigned __int64 v7; // rcx

  if ( !a2 )
    return a3;
  result = 0;
  for ( i = 0; (int)i < a2; result = a3 )
  {
    v7 = a1[i];
    i = (unsigned int)(i + 1);
    a3 = *((_DWORD *)qword_18001A550 + ((unsigned __int8)a3 ^ v7)) ^ (a3 >> 8);
  }
  return result;
}

```

## disassembly

```asm
0x180009ef0  mov     r9d, edx
0x180009ef3  mov     r10, rcx
0x180009ef6  test    edx, edx
0x180009ef8  jnz     short loc_180009EFE
0x180009efa  mov     eax, r8d
0x180009efd  retn
0x180009efe  xor     eax, eax
0x180009f00  xor     edx, edx
0x180009f02  test    r9d, r9d
0x180009f05  jle     short locret_180009EFD
0x180009f07  lea     r11, qword_18001A550
0x180009f0e  xchg    ax, ax
0x180009f10  movzx   ecx, byte ptr [rdx+r10]
0x180009f15  inc     edx
0x180009f17  movzx   eax, r8b
0x180009f1b  xor     rcx, rax
0x180009f1e  shr     r8d, 8
0x180009f22  xor     r8d, [r11+rcx*4]
0x180009f26  mov     eax, r8d
0x180009f29  cmp     edx, r9d
0x180009f2c  jl      short loc_180009F10
0x180009f2e  retn
```
