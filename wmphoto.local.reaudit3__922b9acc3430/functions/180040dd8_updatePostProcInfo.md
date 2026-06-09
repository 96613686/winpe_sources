# updatePostProcInfo

- ea: `0x180040dd8`
- end: `0x180040e5c`
- name: `updatePostProcInfo`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180026620`

## callees

- `0x180040dd8`

## pseudocode

```c
unsigned __int64 __fastcall updatePostProcInfo(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r10
  unsigned __int64 result; // rax
  unsigned __int64 i; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r9
  unsigned __int64 v10; // r8

  v5 = 88 * a3 + *(_QWORD *)(a1 + 16 * a4 + 8);
  *(_DWORD *)v5 = *a2;
  result = 16;
  *(_BYTE *)(v5 + 4) = 0;
  while ( result < 0x100 )
  {
    if ( a2[result] )
    {
      *(_BYTE *)(v5 + 4) = 3;
      break;
    }
    result += 16LL;
  }
  for ( i = 0; i < 4; ++i )
  {
    v8 = 0;
    v9 = v5 + 4 * i;
    do
    {
      v10 = 1;
      *(_BYTE *)(v9 + v8 + 72) = 0;
      while ( v10 < 0x10 )
      {
        result = v10 + 16 * (i + 4 * v8);
        if ( a2[result] )
        {
          *(_BYTE *)(v9 + v8 + 72) = 3;
          break;
        }
        ++v10;
      }
      ++v8;
    }
    while ( v8 < 4 );
  }
  return result;
}

```

## disassembly

```asm
0x180040dd8  mov     eax, [rdx]
0x180040dda  add     r9, r9
0x180040ddd  imul    r8, 58h ; 'X'
0x180040de1  mov     r10, [rcx+r9*8+8]
0x180040de6  mov     r11, rdx
0x180040de9  add     r10, r8
0x180040dec  mov     [r10], eax
0x180040def  mov     eax, 10h
0x180040df4  mov     byte ptr [r10+4], 0
0x180040df9  cmp     rax, 100h
0x180040dff  jnb     short loc_180040E12
0x180040e01  cmp     dword ptr [rdx+rax*4], 0
0x180040e05  jnz     short loc_180040E0D
0x180040e07  add     rax, 10h
0x180040e0b  jmp     short loc_180040DF9
0x180040e0d  mov     byte ptr [r10+4], 3
0x180040e12  xor     edx, edx
0x180040e14  xor     ecx, ecx
0x180040e16  lea     r9, [r10+rdx*4]
0x180040e1a  mov     r8d, 1
0x180040e20  mov     byte ptr [r9+rcx+48h], 0
0x180040e26  cmp     r8, 10h
0x180040e2a  jnb     short loc_180040E49
0x180040e2c  lea     rax, [rdx+rcx*4]
0x180040e30  shl     rax, 4
0x180040e34  add     rax, r8
0x180040e37  cmp     dword ptr [r11+rax*4], 0
0x180040e3c  jnz     short loc_180040E43
0x180040e3e  inc     r8
0x180040e41  jmp     short loc_180040E26
0x180040e43  mov     byte ptr [r9+rcx+48h], 3
0x180040e49  inc     rcx
0x180040e4c  cmp     rcx, 4
0x180040e50  jb      short loc_180040E1A
0x180040e52  inc     rdx
0x180040e55  cmp     rdx, 4
0x180040e59  jb      short loc_180040E14
0x180040e5b  retn
```
