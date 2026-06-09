# DeallocEmbedHeaderData

- ea: `0x180019014`
- end: `0x18001909d`
- name: `DeallocEmbedHeaderData`
- size: `137`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18001862c`
- `0x1800190a4`
- `0x1800205bc`
- `0x180020784`
- `0x18002089c`
- `0x180020c40`
- `0x18002173c`

## callees

- `0x180019014`
- `0x180019dc0`

## pseudocode

```c
void __fastcall DeallocEmbedHeaderData(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)a1[11];
  if ( v2 )
  {
    T2free(v2);
    a1[11] = 0;
  }
  v3 = (void *)a1[13];
  if ( v3 )
  {
    T2free(v3);
    a1[13] = 0;
  }
  v4 = (void *)a1[15];
  if ( v4 )
  {
    T2free(v4);
    a1[15] = 0;
  }
  v5 = (void *)a1[17];
  if ( v5 )
  {
    T2free(v5);
    a1[17] = 0;
  }
  v6 = (void *)a1[19];
  if ( v6 )
  {
    T2free(v6);
    a1[19] = 0;
  }
}

```

## disassembly

```asm
0x180019014  push    rbx
0x180019016  sub     rsp, 20h
0x18001901a  mov     rbx, rcx
0x18001901d  mov     rcx, [rcx+58h]; lpMem
0x180019021  test    rcx, rcx
0x180019024  jz      short loc_180019033
0x180019026  call    T2free
0x18001902b  mov     qword ptr [rbx+58h], 0
0x180019033  mov     rcx, [rbx+68h]; lpMem
0x180019037  test    rcx, rcx
0x18001903a  jz      short loc_180019049
0x18001903c  call    T2free
0x180019041  mov     qword ptr [rbx+68h], 0
0x180019049  mov     rcx, [rbx+78h]; lpMem
0x18001904d  test    rcx, rcx
0x180019050  jz      short loc_18001905F
0x180019052  call    T2free
0x180019057  mov     qword ptr [rbx+78h], 0
0x18001905f  mov     rcx, [rbx+88h]; lpMem
0x180019066  test    rcx, rcx
0x180019069  jz      short loc_18001907B
0x18001906b  call    T2free
0x180019070  mov     qword ptr [rbx+88h], 0
0x18001907b  mov     rcx, [rbx+98h]; lpMem
0x180019082  test    rcx, rcx
0x180019085  jz      short loc_180019097
0x180019087  call    T2free
0x18001908c  mov     qword ptr [rbx+98h], 0
0x180019097  add     rsp, 20h
0x18001909b  pop     rbx
0x18001909c  retn
```
