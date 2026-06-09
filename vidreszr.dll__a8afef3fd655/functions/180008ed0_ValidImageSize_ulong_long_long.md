# ValidImageSize(ulong,long,long)

- ea: `0x180008ed0`
- end: `0x180008f38`
- name: `?ValidImageSize@@YAHKJJ@Z`
- size: `104`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008680`
- `0x1800089b0`

## callees

- `0x180008ed0`

## pseudocode

```c
__int64 __fastcall ValidImageSize(int a1, int a2, int a3)
{
  bool v3; // zf

  if ( a2 && a3 )
  {
    if ( !a1 || a1 == 3 || a1 == 1448433985 )
      return 1;
    if ( (a2 & 1) == 0 && (a1 != 1448433993 && a1 != 808596553 && a1 != 842094169 || (a3 & 1) == 0) )
    {
      if ( ((a1 - 1345401945) & 0xFBFFFFFF) != 0 )
      {
        if ( a1 != 961893977 )
          return 1;
        v3 = (((unsigned __int8)a3 | (unsigned __int8)a2) & 3) == 0;
      }
      else
      {
        v3 = (a2 & 7) == 0;
      }
      if ( v3 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008ed0  test    edx, edx
0x180008ed2  jz      short loc_180008F35
0x180008ed4  test    r8d, r8d
0x180008ed7  jz      short loc_180008F35
0x180008ed9  test    ecx, ecx
0x180008edb  jz      short loc_180008F2F
0x180008edd  cmp     ecx, 3
0x180008ee0  jz      short loc_180008F2F
0x180008ee2  cmp     ecx, 56555941h
0x180008ee8  jz      short loc_180008F2F
0x180008eea  test    dl, 1
0x180008eed  jnz     short loc_180008F35
0x180008eef  cmp     ecx, 56555949h
0x180008ef5  jz      short loc_180008F07
0x180008ef7  cmp     ecx, 30323449h
0x180008efd  jz      short loc_180008F07
0x180008eff  cmp     ecx, 32315659h
0x180008f05  jnz     short loc_180008F0D
0x180008f07  test    r8b, 1
0x180008f0b  jnz     short loc_180008F35
0x180008f0d  lea     eax, [rcx-50313459h]
0x180008f13  test    eax, 0FBFFFFFFh
0x180008f18  jz      short loc_180008F2A
0x180008f1a  cmp     ecx, 39555659h
0x180008f20  jnz     short loc_180008F2F
0x180008f22  or      edx, r8d
0x180008f25  test    dl, 3
0x180008f28  jmp     short loc_180008F2D
0x180008f2a  test    dl, 7
0x180008f2d  jnz     short loc_180008F35
0x180008f2f  mov     eax, 1
0x180008f34  retn
0x180008f35  xor     eax, eax
0x180008f37  retn
```
