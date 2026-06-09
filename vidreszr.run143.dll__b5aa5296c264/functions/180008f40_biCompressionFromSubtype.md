# biCompressionFromSubtype

- ea: `0x180008f40`
- end: `0x18000915f`
- name: `biCompressionFromSubtype`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004fe0`
- `0x180008680`
- `0x1800089b0`

## callees

- `0x180008f40`

## pseudocode

```c
__int64 __fastcall biCompressionFromSubtype(_QWORD *a1)
{
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_IYUV.Data4
    || *(_OWORD *)a1 == MEDIASUBTYPE_I420
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YV12.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YV12.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_NV12.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_NV12.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_NV11.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_NV11.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YUY2.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_UYVY.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YVYU.Data4
    || *(_OWORD *)a1 == MEDIASUBTYPE_V216
    || *a1 == MEDIASUBTYPE_V410 && a1[1] == 0x719B3800AA000080LL
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_AYUV.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YVU9.Data4
    || *a1 == MEDIASUBTYPE_v210 && a1[1] == 0x719B3800AA000080LL )
  {
    return *(unsigned int *)a1;
  }
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB32.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB24.Data4 )
  {
    return 0;
  }
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 )
    return 3;
  if ( (*a1 != *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_RGB555.Data4)
    && (*a1 != *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_RGB8.Data4)
    && (*a1 != *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_ARGB32.Data4) )
  {
    return *(unsigned int *)a1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008f40  mov     rax, [rcx]
0x180008f43  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data1
0x180008f4a  jnz     short loc_180008F5D
0x180008f4c  mov     rax, [rcx+8]
0x180008f50  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data4
0x180008f57  jz      loc_18000915C
0x180008f5d  mov     rax, [rcx]
0x180008f60  cmp     rax, qword ptr cs:MEDIASUBTYPE_I420
0x180008f67  jnz     short loc_180008F7A
0x180008f69  mov     rax, [rcx+8]
0x180008f6d  cmp     rax, qword ptr cs:MEDIASUBTYPE_I420+8
0x180008f74  jz      loc_18000915C
0x180008f7a  mov     rax, [rcx]
0x180008f7d  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data1
0x180008f84  jnz     short loc_180008F97
0x180008f86  mov     rax, [rcx+8]
0x180008f8a  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data4
0x180008f91  jz      loc_18000915C
0x180008f97  mov     rax, [rcx]
0x180008f9a  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data1
0x180008fa1  jnz     short loc_180008FB4
0x180008fa3  mov     rax, [rcx+8]
0x180008fa7  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data4
0x180008fae  jz      loc_18000915C
0x180008fb4  mov     rax, [rcx]
0x180008fb7  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data1
0x180008fbe  jnz     short loc_180008FD1
0x180008fc0  mov     rax, [rcx+8]
0x180008fc4  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data4
0x180008fcb  jz      loc_18000915C
0x180008fd1  mov     rax, [rcx]
0x180008fd4  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x180008fdb  jnz     short loc_180008FEE
0x180008fdd  mov     rax, [rcx+8]
0x180008fe1  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x180008fe8  jz      loc_18000915C
0x180008fee  mov     rax, [rcx]
0x180008ff1  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x180008ff8  jnz     short loc_18000900B
0x180008ffa  mov     rax, [rcx+8]
0x180008ffe  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x180009005  jz      loc_18000915C
0x18000900b  mov     rax, [rcx]
0x18000900e  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data1
0x180009015  jnz     short loc_180009028
0x180009017  mov     rax, [rcx+8]
0x18000901b  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data4
0x180009022  jz      loc_18000915C
0x180009028  mov     rax, [rcx]
0x18000902b  cmp     rax, qword ptr cs:MEDIASUBTYPE_V216
0x180009032  jnz     short loc_180009045
0x180009034  mov     rax, [rcx+8]
0x180009038  cmp     rax, qword ptr cs:MEDIASUBTYPE_V216+8
0x18000903f  jz      loc_18000915C
0x180009045  mov     rax, [rcx]
0x180009048  cmp     rax, cs:MEDIASUBTYPE_V410
0x18000904f  jnz     short loc_180009062
0x180009051  mov     rax, [rcx+8]
0x180009055  cmp     rax, cs:qword_180017FB8
0x18000905c  jz      loc_18000915C
0x180009062  mov     rax, [rcx]
0x180009065  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x18000906c  jnz     short loc_18000907F
0x18000906e  mov     rax, [rcx+8]
0x180009072  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data4
0x180009079  jz      loc_18000915C
0x18000907f  mov     rax, [rcx]
0x180009082  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data1
0x180009089  jnz     short loc_18000909C
0x18000908b  mov     rax, [rcx+8]
0x18000908f  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data4
0x180009096  jz      loc_18000915C
0x18000909c  mov     rax, [rcx]
0x18000909f  cmp     rax, cs:MEDIASUBTYPE_v210
0x1800090a6  jnz     short loc_1800090B9
0x1800090a8  mov     rax, [rcx+8]
0x1800090ac  cmp     rax, cs:qword_180017FC8
0x1800090b3  jz      loc_18000915C
0x1800090b9  mov     rax, [rcx]
0x1800090bc  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data1
0x1800090c3  jnz     short loc_1800090D6
0x1800090c5  mov     rax, [rcx+8]
0x1800090c9  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data4
0x1800090d0  jz      loc_180009159
0x1800090d6  mov     rax, [rcx]
0x1800090d9  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data1
0x1800090e0  jnz     short loc_1800090EF
0x1800090e2  mov     rax, [rcx+8]
0x1800090e6  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data4
0x1800090ed  jz      short loc_180009159
0x1800090ef  mov     rax, [rcx]
0x1800090f2  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x1800090f9  jnz     short loc_18000910E
0x1800090fb  mov     rax, [rcx+8]
0x1800090ff  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x180009106  jnz     short loc_18000910E
0x180009108  mov     eax, 3
0x18000910d  retn
0x18000910e  mov     rax, [rcx]
0x180009111  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data1
0x180009118  jnz     short loc_180009127
0x18000911a  mov     rax, [rcx+8]
0x18000911e  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data4
0x180009125  jz      short loc_180009159
0x180009127  mov     rax, [rcx]
0x18000912a  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x180009131  jnz     short loc_180009140
0x180009133  mov     rax, [rcx+8]
0x180009137  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x18000913e  jz      short loc_180009159
0x180009140  mov     rax, [rcx]
0x180009143  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x18000914a  jnz     short loc_18000915C
0x18000914c  mov     rax, [rcx+8]
0x180009150  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data4
0x180009157  jnz     short loc_18000915C
0x180009159  xor     eax, eax
0x18000915b  retn
0x18000915c  mov     eax, [rcx]
0x18000915e  retn
```
