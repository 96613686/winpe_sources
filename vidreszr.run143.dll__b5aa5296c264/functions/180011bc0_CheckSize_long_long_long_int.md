# CheckSize(long,long,long,int)

- ea: `0x180011bc0`
- end: `0x180011cd2`
- name: `?CheckSize@@YAJJJJH@Z`
- size: `274`
- prototype: `_BOOL8 __fastcall(int, int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012e30`
- `0x180013420`
- `0x180013a00`

## callees

- `0x180011bc0`

## pseudocode

```c
_BOOL8 __fastcall CheckSize(int a1, int a2, int a3, int a4)
{
  bool v4; // zf

  if ( a4 )
  {
    if ( !a1 || a1 == 3 || a1 == 1448433985 )
    {
      return a3 & 1;
    }
    else
    {
      if ( a1 != 844715353 && a1 != 1498831189 && a1 != 909193814 )
      {
        if ( a1 == 1448433993 || a1 == 808596553 || a1 == 842094169 )
        {
          if ( (a2 & 1) != 0 )
            return 1;
          v4 = (a3 & 3) == 0;
        }
        else
        {
          if ( a1 != 961893977 )
            return 0;
          if ( (a2 & 3) != 0 )
            return 1;
          v4 = (a3 & 7) == 0;
        }
        return !v4;
      }
      return (((unsigned __int8)a3 | (unsigned __int8)a2) & 1) != 0;
    }
  }
  else
  {
    if ( !a1 || a1 == 3 || a1 == 1448433985 )
      return 0;
    if ( a1 != 844715353 && a1 != 1498831189 && a1 != 842150992 && a1 != 909193814 )
    {
      if ( a1 != 1448433993 && a1 != 842094169 && a1 != 808596553 )
      {
        if ( a1 != 961893977 )
          return 0;
        if ( a2 % 4 )
          return 1;
        v4 = a3 % 4 == 0;
        return !v4;
      }
      return (((unsigned __int8)a3 | (unsigned __int8)a2) & 1) != 0;
    }
    return a2 & 1;
  }
}

```

## disassembly

```asm
0x180011bc0  test    r9d, r9d
0x180011bc3  jnz     loc_180011C5C
0x180011bc9  test    ecx, ecx
0x180011bcb  jz      short loc_180011C45
0x180011bcd  cmp     ecx, 3
0x180011bd0  jz      short loc_180011C45
0x180011bd2  cmp     ecx, 56555941h
0x180011bd8  jz      short loc_180011C45
0x180011bda  cmp     ecx, 32595559h
0x180011be0  jz      short loc_180011C56
0x180011be2  cmp     ecx, 59565955h
0x180011be8  jz      short loc_180011C56
0x180011bea  cmp     ecx, 32323450h
0x180011bf0  jz      short loc_180011C56
0x180011bf2  cmp     ecx, 36313256h
0x180011bf8  jz      short loc_180011C56
0x180011bfa  cmp     ecx, 56555949h
0x180011c00  jz      short loc_180011C48
0x180011c02  cmp     ecx, 32315659h
0x180011c08  jz      short loc_180011C48
0x180011c0a  cmp     ecx, 30323449h
0x180011c10  jz      short loc_180011C48
0x180011c12  cmp     ecx, 39555659h
0x180011c18  jnz     short loc_180011C45
0x180011c1a  and     edx, 80000003h
0x180011c20  jge     short loc_180011C29
0x180011c22  dec     edx
0x180011c24  or      edx, 0FFFFFFFCh
0x180011c27  inc     edx
0x180011c29  test    edx, edx
0x180011c2b  jnz     short loc_180011C50
0x180011c2d  and     r8d, 80000003h
0x180011c34  jge     short loc_180011C40
0x180011c36  dec     r8d
0x180011c39  or      r8d, 0FFFFFFFCh
0x180011c3d  inc     r8d
0x180011c40  test    r8d, r8d
0x180011c43  jnz     short loc_180011C50
0x180011c45  xor     eax, eax
0x180011c47  retn
0x180011c48  or      edx, r8d
0x180011c4b  test    dl, 1
0x180011c4e  jz      short loc_180011C45
0x180011c50  mov     eax, 1
0x180011c55  retn
0x180011c56  and     edx, 1
0x180011c59  mov     eax, edx
0x180011c5b  retn
0x180011c5c  test    ecx, ecx
0x180011c5e  jz      short loc_180011CCA
0x180011c60  cmp     ecx, 3
0x180011c63  jz      short loc_180011CCA
0x180011c65  cmp     ecx, 56555941h
0x180011c6b  jz      short loc_180011CCA
0x180011c6d  cmp     ecx, 32595559h
0x180011c73  jz      short loc_180011CBB
0x180011c75  cmp     ecx, 59565955h
0x180011c7b  jz      short loc_180011CBB
0x180011c7d  cmp     ecx, 36313256h
0x180011c83  jz      short loc_180011CBB
0x180011c85  cmp     ecx, 56555949h
0x180011c8b  jz      short loc_180011CB0
0x180011c8d  cmp     ecx, 30323449h
0x180011c93  jz      short loc_180011CB0
0x180011c95  cmp     ecx, 32315659h
0x180011c9b  jz      short loc_180011CB0
0x180011c9d  cmp     ecx, 39555659h
0x180011ca3  jnz     short loc_180011C45
0x180011ca5  test    dl, 3
0x180011ca8  jnz     short loc_180011C50
0x180011caa  test    r8b, 7
0x180011cae  jmp     short loc_180011C43
0x180011cb0  test    dl, 1
0x180011cb3  jnz     short loc_180011C50
0x180011cb5  test    r8b, 3
0x180011cb9  jmp     short loc_180011C43
0x180011cbb  or      edx, r8d
0x180011cbe  mov     eax, 0
0x180011cc3  test    dl, 1
0x180011cc6  setnz   al
0x180011cc9  retn
0x180011cca  and     r8d, 1
0x180011cce  mov     eax, r8d
0x180011cd1  retn
```
