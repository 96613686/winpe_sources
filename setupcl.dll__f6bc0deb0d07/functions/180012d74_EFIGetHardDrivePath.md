# EFIGetHardDrivePath

- ea: `0x180012d74`
- end: `0x180012df6`
- name: `EFIGetHardDrivePath`
- size: `130`
- prototype: `char __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012dfc`

## callees

- `0x180012d74`
- `0x1800179ad`

## pseudocode

```c
char __fastcall EFIGetHardDrivePath(_DWORD *a1, _DWORD *a2)
{
  char v2; // r9
  _BYTE *i; // rdx
  char v5; // al
  unsigned int v6; // r9d

  v2 = 0;
  if ( a1 && a2 )
  {
    for ( i = a1 + 3; ; i += *((unsigned __int16 *)i + 1) )
    {
      v5 = *i & 0x7F;
      if ( v5 == 127 )
        break;
      if ( v5 == 4 && i[1] == 1 )
      {
        *a2 = *a1;
        v6 = (_DWORD)a1 + a1[1] - (_DWORD)i;
        a2[1] = v6 + 12;
        a2[2] = a1[2];
        if ( v6 >= 0xFFFFFFF4 )
          return 0;
        memcpy_0(a2 + 3, i, v6);
        return 1;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180012d74  sub     rsp, 28h
0x180012d78  xor     r9b, r9b
0x180012d7b  mov     r10, rdx
0x180012d7e  mov     r8, rcx
0x180012d81  test    rcx, rcx
0x180012d84  jz      short loc_180012DEE
0x180012d86  test    rdx, rdx
0x180012d89  jz      short loc_180012DEE
0x180012d8b  lea     rdx, [rcx+0Ch]; Src
0x180012d8f  mov     al, [rdx]
0x180012d91  and     al, 7Fh
0x180012d93  cmp     al, 7Fh
0x180012d95  jz      short loc_180012DEE
0x180012d97  cmp     al, 4
0x180012d99  jnz     short loc_180012DA1
0x180012d9b  cmp     byte ptr [rdx+1], 1
0x180012d9f  jz      short loc_180012DB5
0x180012da1  movzx   ecx, byte ptr [rdx+3]
0x180012da5  movzx   eax, byte ptr [rdx+2]
0x180012da9  shl     rcx, 8
0x180012dad  or      rcx, rax
0x180012db0  add     rdx, rcx
0x180012db3  jmp     short loc_180012D8F
0x180012db5  mov     eax, [r8]
0x180012db8  mov     [r10], eax
0x180012dbb  mov     r9d, [r8+4]
0x180012dbf  sub     r9d, edx
0x180012dc2  add     r9d, r8d
0x180012dc5  lea     ecx, [r9+0Ch]
0x180012dc9  mov     [r10+4], ecx
0x180012dcd  mov     eax, [r8+8]
0x180012dd1  mov     [r10+8], eax
0x180012dd5  cmp     ecx, 0Ch
0x180012dd8  jb      short loc_180012DEB
0x180012dda  mov     r8d, r9d; Size
0x180012ddd  lea     rcx, [r10+0Ch]; void *
0x180012de1  call    memcpy_0
0x180012de6  mov     r9b, 1
0x180012de9  jmp     short loc_180012DEE
0x180012deb  xor     r9b, r9b
0x180012dee  mov     al, r9b
0x180012df1  add     rsp, 28h
0x180012df5  retn
```
