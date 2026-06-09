# WMSDKRESIZER::getType(void)

- ea: `0x180012970`
- end: `0x1800129c2`
- name: `?getType@WMSDKRESIZER@@AEAAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(WMSDKRESIZER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800125b0`
- `0x1800129d0`

## callees

- `0x180012970`

## pseudocode

```c
__int64 __fastcall WMSDKRESIZER::getType(WMSDKRESIZER *this)
{
  __int64 v1; // rcx
  int v3; // ecx

  v1 = *((_QWORD *)this + 1);
  if ( !v1 )
    return 0;
  v3 = *(_DWORD *)(v1 + 16);
  if ( v3 == 1448433993 || v3 == 808596553 || v3 == 842094169 || v3 == 961893977 )
    return 1;
  if ( v3 == 842094158 )
    return 3;
  return (unsigned int)(v3 == 825316942) + 2;
}

```

## disassembly

```asm
0x180012970  mov     rcx, [rcx+8]
0x180012974  test    rcx, rcx
0x180012977  jnz     short loc_18001297C
0x180012979  xor     eax, eax
0x18001297b  retn
0x18001297c  mov     ecx, [rcx+10h]
0x18001297f  cmp     ecx, 56555949h
0x180012985  jz      short loc_1800129BC
0x180012987  cmp     ecx, 30323449h
0x18001298d  jz      short loc_1800129BC
0x18001298f  cmp     ecx, 32315659h
0x180012995  jz      short loc_1800129BC
0x180012997  cmp     ecx, 39555659h
0x18001299d  jz      short loc_1800129BC
0x18001299f  cmp     ecx, 3231564Eh
0x1800129a5  jz      short loc_1800129B6
0x1800129a7  xor     eax, eax
0x1800129a9  cmp     ecx, 3131564Eh
0x1800129af  setz    al
0x1800129b2  add     eax, 2
0x1800129b5  retn
0x1800129b6  mov     eax, 3
0x1800129bb  retn
0x1800129bc  mov     eax, 1
0x1800129c1  retn
```
