# WMSDKRESIZER::BMPSize(long,long)

- ea: `0x180011b40`
- end: `0x180011bb4`
- name: `?BMPSize@WMSDKRESIZER@@QEAAJJJ@Z`
- size: `116`
- prototype: `__int64 __fastcall(WMSDKRESIZER *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012e30`
- `0x180013560`

## callees

- `0x180011b40`

## pseudocode

```c
__int64 __fastcall WMSDKRESIZER::BMPSize(WMSDKRESIZER *this, int a2, int a3)
{
  __int64 v3; // rax
  int v4; // ecx
  int v5; // eax
  int v6; // kr08_4
  __int64 result; // rax
  unsigned int v8; // ecx

  v3 = *((_QWORD *)this + 1);
  v4 = *(_DWORD *)(v3 + 16);
  v5 = *(unsigned __int16 *)(v3 + 14);
  if ( v4 == 1448433993 || v4 == 808596553 || v4 == 842094169 || v4 == 842094158 || v4 == 825316942 )
  {
    v8 = a3 * a2 * v5 / 8;
    result = (unsigned int)(a3 * a2 * v5 / -8);
    if ( (int)result < 0 )
      return v8;
  }
  else
  {
    v6 = a2 * v5 / 8 + 3;
    result = (unsigned int)(-4 * a3 * (v6 / 4));
    if ( (int)result < 0 )
      return (unsigned int)(4 * a3 * (v6 / 4));
  }
  return result;
}

```

## disassembly

```asm
0x180011b40  mov     rax, [rcx+8]
0x180011b44  mov     ecx, [rax+10h]
0x180011b47  movzx   eax, word ptr [rax+0Eh]
0x180011b4b  cmp     ecx, 56555949h
0x180011b51  jz      short loc_180011B9B
0x180011b53  cmp     ecx, 30323449h
0x180011b59  jz      short loc_180011B9B
0x180011b5b  cmp     ecx, 32315659h
0x180011b61  jz      short loc_180011B9B
0x180011b63  cmp     ecx, 3231564Eh
0x180011b69  jz      short loc_180011B9B
0x180011b6b  cmp     ecx, 3131564Eh
0x180011b71  jz      short loc_180011B9B
0x180011b73  imul    eax, edx
0x180011b76  cdq
0x180011b77  and     edx, 7
0x180011b7a  add     eax, edx
0x180011b7c  sar     eax, 3
0x180011b7f  add     eax, 3
0x180011b82  cdq
0x180011b83  and     edx, 3
0x180011b86  lea     ecx, [rdx+rax]
0x180011b89  sar     ecx, 2
0x180011b8c  imul    ecx, r8d
0x180011b90  shl     ecx, 2
0x180011b93  mov     eax, ecx
0x180011b95  neg     eax
0x180011b97  cmovs   eax, ecx
0x180011b9a  retn
0x180011b9b  imul    eax, edx
0x180011b9e  imul    eax, r8d
0x180011ba2  cdq
0x180011ba3  and     edx, 7
0x180011ba6  lea     ecx, [rdx+rax]
0x180011ba9  sar     ecx, 3
0x180011bac  mov     eax, ecx
0x180011bae  neg     eax
0x180011bb0  cmovs   eax, ecx
0x180011bb3  retn
```
