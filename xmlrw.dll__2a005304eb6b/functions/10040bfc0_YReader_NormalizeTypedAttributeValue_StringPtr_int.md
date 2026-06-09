# YReader::NormalizeTypedAttributeValue(StringPtr *,int)

- ea: `0x10040bfc0`
- end: `0x10040c08f`
- name: `?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z`
- size: `207`
- prototype: `void __fastcall(YReader *__hidden this, struct StringPtr *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1004038d0`
- `0x1004055d0`
- `0x10040b230`
- `0x10040b4c0`

## callees

- `0x100401780`
- `0x10040bfc0`

## pseudocode

```c
void __fastcall YReader::NormalizeTypedAttributeValue(YReader *this, __int16 **a2, int a3)
{
  __int16 *v3; // rax
  __int16 *v4; // r10
  __int16 *v5; // r9
  __int16 v6; // cx
  __int16 *v7; // rcx
  __int64 v8; // r10
  int v9; // r8d
  int v10; // r8d
  __int16 *i; // rdx

  v3 = *a2;
  v4 = *a2;
  v5 = &(*a2)[*((unsigned int *)a2 + 2) - 1];
  if ( *a2 <= v5 )
  {
    while ( *v5 == 32 )
    {
      if ( v3 > --v5 )
        goto LABEL_15;
    }
    if ( v3 <= v5 )
    {
      while ( 1 )
      {
        v6 = *v3++;
        if ( v6 != 32 )
          break;
        if ( v3 > v5 )
          goto LABEL_15;
      }
      for ( *v4 = v6; v3 <= v5; ++v3 )
      {
        if ( *v3 != 32 || *v4 != 32 )
          *++v4 = *v3;
      }
      ++v4;
    }
  }
LABEL_15:
  v7 = *a2;
  v8 = v4 - *a2;
  *((_DWORD *)a2 + 2) = v8;
  v9 = a3 - 6;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 2 )
      {
        for ( i = &v7[(unsigned int)v8]; v7 < i; ++v7 )
        {
          if ( *v7 == 58 )
          {
            MXRRaiseException(-1072894365);
            JUMPOUT(0x10040C08ELL);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x10040bfc0  sub     rsp, 28h
0x10040bfc4  mov     rax, [rdx]
0x10040bfc7  mov     r9d, [rdx+8]
0x10040bfcb  mov     r10, rax
0x10040bfce  dec     r9
0x10040bfd1  lea     r9, [rax+r9*2]
0x10040bfd5  cmp     rax, r9
0x10040bfd8  ja      short loc_10040C044
0x10040bfda  nop     word ptr [rax+rax+00h]
0x10040bfe0  cmp     word ptr [r9], 20h ; ' '
0x10040bfe5  jnz     short loc_10040BFF2
0x10040bfe7  sub     r9, 2
0x10040bfeb  cmp     rax, r9
0x10040bfee  jbe     short loc_10040BFE0
0x10040bff0  jmp     short loc_10040C044
0x10040bff2  cmp     rax, r9
0x10040bff5  ja      short loc_10040C044
0x10040bff7  nop     word ptr [rax+rax+00000000h]
0x10040c000  movzx   ecx, word ptr [rax]
0x10040c003  add     rax, 2
0x10040c007  cmp     cx, 20h ; ' '
0x10040c00b  jnz     short loc_10040C014
0x10040c00d  cmp     rax, r9
0x10040c010  jbe     short loc_10040C000
0x10040c012  jmp     short loc_10040C044
0x10040c014  mov     [r10], cx
0x10040c018  cmp     rax, r9
0x10040c01b  ja      short loc_10040C040
0x10040c01d  nop     dword ptr [rax]
0x10040c020  movzx   ecx, word ptr [rax]
0x10040c023  cmp     cx, 20h ; ' '
0x10040c027  jnz     short loc_10040C02F
0x10040c029  cmp     [r10], cx
0x10040c02d  jz      short loc_10040C037
0x10040c02f  add     r10, 2
0x10040c033  mov     [r10], cx
0x10040c037  add     rax, 2
0x10040c03b  cmp     rax, r9
0x10040c03e  jbe     short loc_10040C020
0x10040c040  add     r10, 2
0x10040c044  mov     rcx, [rdx]
0x10040c047  sub     r10, rcx
0x10040c04a  sar     r10, 1
0x10040c04d  mov     [rdx+8], r10d
0x10040c051  sub     r8d, 6
0x10040c055  jz      short loc_10040C07F
0x10040c057  sub     r8d, 1
0x10040c05b  jz      short loc_10040C07F
0x10040c05d  cmp     r8d, 2
0x10040c061  jz      short loc_10040C07F
0x10040c063  mov     eax, r10d
0x10040c066  lea     rdx, [rcx+rax*2]
0x10040c06a  cmp     rcx, rdx
0x10040c06d  jnb     short loc_10040C07F
0x10040c06f  nop
0x10040c070  cmp     word ptr [rcx], 3Ah ; ':'
0x10040c074  jz      short loc_10040C084
0x10040c076  add     rcx, 2
0x10040c07a  cmp     rcx, rdx
0x10040c07d  jb      short loc_10040C070
0x10040c07f  add     rsp, 28h
0x10040c083  retn
0x10040c084  mov     ecx, 0C00CEE63h; int
0x10040c089  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
