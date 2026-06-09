# UncompressData

- ea: `0x180036d3c`
- end: `0x180036dc4`
- name: `UncompressData`
- size: `136`
- prototype: `__int64 __fastcall(int, __int64, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031154`
- `0x18003179c`

## callees

- `0x1800022d0`
- `0x180036d3c`

## pseudocode

```c
__int64 __fastcall UncompressData(int a1, __int64 a2, unsigned int *a3, __int64 a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  unsigned int v11; // edx

  if ( a2 )
  {
    v9 = *(unsigned __int16 *)(a2 + 2);
    v8 = 0;
    if ( a4 )
    {
      v10 = *a3;
      *a3 = v9;
      if ( v10 >= v9 )
      {
        if ( (unsigned int)uncompress(a4, a3, a2 + 4, (unsigned int)(a1 - 4)) )
        {
          return 1359;
        }
        else
        {
          v11 = 0;
          if ( *(unsigned __int16 *)(a2 + 2) != *a3 )
            return 1359;
          return v11;
        }
      }
      else
      {
        return 234;
      }
    }
    else
    {
      *a3 = v9;
    }
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x180036d3c  mov     [rsp+arg_0], rbx
0x180036d41  mov     [rsp+arg_8], rsi
0x180036d46  push    rdi
0x180036d47  sub     rsp, 20h
0x180036d4b  mov     r10, r9
0x180036d4e  mov     r9d, ecx
0x180036d51  mov     rdi, r8
0x180036d54  mov     rsi, rdx
0x180036d57  test    rdx, rdx
0x180036d5a  jnz     short loc_180036D61
0x180036d5c  lea     ebx, [rdx+57h]
0x180036d5f  jmp     short loc_180036DB2
0x180036d61  movzx   ecx, word ptr [rdx+2]
0x180036d65  xor     ebx, ebx
0x180036d67  test    r10, r10
0x180036d6a  jnz     short loc_180036D71
0x180036d6c  mov     [r8], ecx
0x180036d6f  jmp     short loc_180036DB2
0x180036d71  mov     eax, [r8]
0x180036d74  mov     [r8], ecx
0x180036d77  cmp     eax, ecx
0x180036d79  jnb     short loc_180036D82
0x180036d7b  mov     ebx, 0EAh
0x180036d80  jmp     short loc_180036DB2
0x180036d82  lea     r8, [rdx+4]
0x180036d86  add     r9d, 0FFFFFFFCh
0x180036d8a  mov     rdx, rdi
0x180036d8d  mov     rcx, r10
0x180036d90  call    uncompress
0x180036d95  test    eax, eax
0x180036d97  jz      short loc_180036DA0
0x180036d99  mov     ebx, 54Fh
0x180036d9e  jmp     short loc_180036DB2
0x180036da0  movzx   ecx, word ptr [rsi+2]
0x180036da4  mov     edx, ebx
0x180036da6  cmp     ecx, [rdi]
0x180036da8  mov     ebx, 54Fh
0x180036dad  cmovnz  edx, ebx
0x180036db0  mov     ebx, edx
0x180036db2  mov     rsi, [rsp+28h+arg_8]
0x180036db7  mov     eax, ebx
0x180036db9  mov     rbx, [rsp+28h+arg_0]
0x180036dbe  add     rsp, 20h
0x180036dc2  pop     rdi
0x180036dc3  retn
```
