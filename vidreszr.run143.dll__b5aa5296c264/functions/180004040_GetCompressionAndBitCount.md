# GetCompressionAndBitCount

- ea: `0x180004040`
- end: `0x1800042ae`
- name: `GetCompressionAndBitCount`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003950`

## callees

- `0x180004040`

## pseudocode

```c
__int64 __fastcall GetCompressionAndBitCount(unsigned int a1, unsigned int *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5)
{
  __int64 result; // rax

  *a5 = 0;
  if ( a1 > 0x32595559 )
  {
    if ( a1 > 0x56555949 )
    {
      if ( a1 > 0xE436EB7C )
      {
        if ( a1 == -466162819 )
          goto LABEL_52;
        if ( a1 == -466162818 )
        {
LABEL_51:
          result = 0;
          *a3 = 32;
          *a5 = 1;
          *a4 = 1;
          *a2 = 0;
          return result;
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0xE436EB7C:
            goto LABEL_47;
          case 0x59565955u:
            goto LABEL_46;
          case 0xE436EB7A:
LABEL_45:
            result = 0;
            *a3 = 8;
            *a5 = 1;
            *a4 = 1;
            *a2 = 0;
            return result;
          case 0xE436EB7B:
LABEL_44:
            result = 3;
            *a3 = 16;
            *a5 = 1;
            *a4 = 1;
            *a2 = 3;
            return result;
        }
      }
    }
    else
    {
      if ( a1 == 1448433993 )
        goto LABEL_20;
      result = 961893977;
      if ( a1 <= 0x39555659 )
      {
        if ( a1 == 961893977 )
        {
          *a3 = 9;
          *a4 = 1;
          *a2 = 961893977;
          return result;
        }
        if ( a1 == 860048713 )
          goto LABEL_46;
        if ( a1 != 876825929 )
        {
          if ( a1 != 909193814 )
          {
            *a3 = 0;
            result = a1;
            *a4 = 1;
            *a2 = a1;
            return result;
          }
          goto LABEL_38;
        }
        goto LABEL_20;
      }
      switch ( a1 )
      {
        case 0x50313459u:
          goto LABEL_20;
        case 0x55595659u:
          goto LABEL_46;
        case 0x56555941u:
LABEL_38:
          *a3 = 32;
          result = a1;
          *a4 = 1;
          *a2 = a1;
          return result;
      }
    }
LABEL_50:
    *a3 = 0;
    result = a1;
    *a4 = 1;
    *a2 = a1;
    return result;
  }
  if ( a1 == 844715353 )
    goto LABEL_46;
  if ( a1 > 0x30323449 )
  {
    if ( a1 > 0x31434D49 )
    {
      if ( a1 != 842094158 && a1 != 842094169 && a1 != 843271497 )
      {
        *a3 = 0;
        result = a1;
        *a4 = 1;
        *a2 = a1;
        return result;
      }
      goto LABEL_20;
    }
    if ( a1 == 826494281 )
      goto LABEL_46;
    result = 825307737;
    switch ( a1 )
    {
      case 0x31313259u:
        *a3 = 8;
        *a4 = 1;
        *a2 = 825307737;
        return result;
      case 0x31313459u:
        goto LABEL_46;
      case 0x3131564Eu:
LABEL_20:
        *a3 = 12;
        result = a1;
        *a4 = 1;
        *a2 = a1;
        return result;
    }
    goto LABEL_50;
  }
  if ( a1 == 808596553 )
    goto LABEL_20;
  if ( a1 > 0x18 )
  {
    if ( a1 != 41 )
    {
      if ( a1 != 808530550 )
      {
        if ( a1 != 808531030 )
        {
          *a3 = 0;
          result = a1;
          *a4 = 1;
          *a2 = a1;
          return result;
        }
        goto LABEL_38;
      }
LABEL_46:
      *a3 = 16;
      result = a1;
      *a4 = 1;
      *a2 = a1;
      return result;
    }
    goto LABEL_45;
  }
  if ( a1 == 24 )
  {
LABEL_47:
    result = 0;
    *a3 = 16;
    *a5 = 1;
    *a4 = 1;
    *a2 = 0;
    return result;
  }
  if ( a1 != 20 )
  {
    if ( a1 != 22 )
    {
      if ( a1 != 23 )
      {
        *a3 = 0;
        result = a1;
        *a4 = 1;
        *a2 = a1;
        return result;
      }
      goto LABEL_44;
    }
    goto LABEL_51;
  }
LABEL_52:
  result = 0;
  *a3 = 24;
  *a5 = 1;
  *a4 = 1;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180004040  mov     r10, [rsp+arg_20]
0x180004045  xor     r11d, r11d
0x180004048  mov     [r10], r11d
0x18000404b  cmp     ecx, 32595559h
0x180004051  ja      loc_180004149
0x180004057  jz      loc_18000422B
0x18000405d  cmp     ecx, 30323449h
0x180004063  ja      short loc_1800040D2
0x180004065  jz      loc_180004101
0x18000406b  cmp     ecx, 18h
0x18000406e  ja      short loc_1800040A2
0x180004070  jz      loc_18000423E
0x180004076  mov     eax, ecx
0x180004078  sub     eax, 14h
0x18000407b  jz      loc_180004293
0x180004081  sub     eax, 2
0x180004084  jz      loc_180004278
0x18000408a  cmp     eax, 1
0x18000408d  jz      loc_1800041F3
0x180004093  mov     [r8], r11d
0x180004096  mov     eax, ecx
0x180004098  mov     dword ptr [r9], 1
0x18000409f  mov     [rdx], ecx
0x1800040a1  retn
0x1800040a2  cmp     ecx, 29h ; ')'
0x1800040a5  jz      loc_180004210
0x1800040ab  cmp     ecx, 30313276h
0x1800040b1  jz      loc_18000422B
0x1800040b7  cmp     ecx, 30313456h
0x1800040bd  jz      loc_1800041BA
0x1800040c3  mov     [r8], r11d
0x1800040c6  mov     eax, ecx
0x1800040c8  mov     dword ptr [r9], 1
0x1800040cf  mov     [rdx], ecx
0x1800040d1  retn
0x1800040d2  cmp     ecx, 31434D49h
0x1800040d8  ja      short loc_180004125
0x1800040da  jz      loc_18000422B
0x1800040e0  mov     eax, 31313259h
0x1800040e5  cmp     ecx, eax
0x1800040e7  jz      short loc_180004114
0x1800040e9  cmp     ecx, 31313459h
0x1800040ef  jz      loc_18000422B
0x1800040f5  cmp     ecx, 3131564Eh
0x1800040fb  jnz     loc_180004269
0x180004101  mov     dword ptr [r8], 0Ch
0x180004108  mov     eax, ecx
0x18000410a  mov     dword ptr [r9], 1
0x180004111  mov     [rdx], ecx
0x180004113  retn
0x180004114  mov     dword ptr [r8], 8
0x18000411b  mov     dword ptr [r9], 1
0x180004122  mov     [rdx], eax
0x180004124  retn
0x180004125  mov     eax, ecx
0x180004127  sub     eax, 3231564Eh
0x18000412c  jz      short loc_180004101
0x18000412e  sub     eax, 0Bh
0x180004131  jz      short loc_180004101
0x180004133  cmp     eax, 11F6F0h
0x180004138  jz      short loc_180004101
0x18000413a  mov     [r8], r11d
0x18000413d  mov     eax, ecx
0x18000413f  mov     dword ptr [r9], 1
0x180004146  mov     [rdx], ecx
0x180004148  retn
0x180004149  cmp     ecx, 56555949h
0x18000414f  ja      short loc_1800041CD
0x180004151  jz      short loc_180004101
0x180004153  mov     eax, 39555659h
0x180004158  cmp     ecx, eax
0x18000415a  ja      short loc_18000419A
0x18000415c  jz      short loc_180004189
0x18000415e  cmp     ecx, 33434D49h
0x180004164  jz      loc_18000422B
0x18000416a  cmp     ecx, 34434D49h
0x180004170  jz      short loc_180004101
0x180004172  cmp     ecx, 36313256h
0x180004178  jz      short loc_1800041BA
0x18000417a  mov     [r8], r11d
0x18000417d  mov     eax, ecx
0x18000417f  mov     dword ptr [r9], 1
0x180004186  mov     [rdx], ecx
0x180004188  retn
0x180004189  mov     dword ptr [r8], 9
0x180004190  mov     dword ptr [r9], 1
0x180004197  mov     [rdx], eax
0x180004199  retn
0x18000419a  cmp     ecx, 50313459h
0x1800041a0  jz      loc_180004101
0x1800041a6  cmp     ecx, 55595659h
0x1800041ac  jz      short loc_18000422B
0x1800041ae  cmp     ecx, 56555941h
0x1800041b4  jnz     loc_180004269
0x1800041ba  mov     dword ptr [r8], 20h ; ' '
0x1800041c1  mov     eax, ecx
0x1800041c3  mov     dword ptr [r9], 1
0x1800041ca  mov     [rdx], ecx
0x1800041cc  retn
0x1800041cd  cmp     ecx, 0E436EB7Ch
0x1800041d3  ja      loc_180004259
0x1800041d9  jz      short loc_18000423E
0x1800041db  cmp     ecx, 59565955h
0x1800041e1  jz      short loc_18000422B
0x1800041e3  cmp     ecx, 0E436EB7Ah
0x1800041e9  jz      short loc_180004210
0x1800041eb  cmp     ecx, 0E436EB7Bh
0x1800041f1  jnz     short loc_180004269
0x1800041f3  mov     eax, 3
0x1800041f8  mov     dword ptr [r8], 10h
0x1800041ff  mov     dword ptr [r10], 1
0x180004206  mov     dword ptr [r9], 1
0x18000420d  mov     [rdx], eax
0x18000420f  retn
0x180004210  mov     eax, r11d
0x180004213  mov     dword ptr [r8], 8
0x18000421a  mov     dword ptr [r10], 1
0x180004221  mov     dword ptr [r9], 1
0x180004228  mov     [rdx], eax
0x18000422a  retn
0x18000422b  mov     dword ptr [r8], 10h
0x180004232  mov     eax, ecx
0x180004234  mov     dword ptr [r9], 1
0x18000423b  mov     [rdx], ecx
0x18000423d  retn
0x18000423e  mov     eax, r11d
0x180004241  mov     dword ptr [r8], 10h
0x180004248  mov     dword ptr [r10], 1
0x18000424f  mov     dword ptr [r9], 1
0x180004256  mov     [rdx], eax
0x180004258  retn
0x180004259  cmp     ecx, 0E436EB7Dh
0x18000425f  jz      short loc_180004293
0x180004261  cmp     ecx, 0E436EB7Eh
0x180004267  jz      short loc_180004278
0x180004269  mov     [r8], r11d
0x18000426c  mov     eax, ecx
0x18000426e  mov     dword ptr [r9], 1
0x180004275  mov     [rdx], ecx
0x180004277  retn
0x180004278  mov     eax, r11d
0x18000427b  mov     dword ptr [r8], 20h ; ' '
0x180004282  mov     dword ptr [r10], 1
0x180004289  mov     dword ptr [r9], 1
0x180004290  mov     [rdx], eax
0x180004292  retn
0x180004293  mov     eax, r11d
0x180004296  mov     dword ptr [r8], 18h
0x18000429d  mov     dword ptr [r10], 1
0x1800042a4  mov     dword ptr [r9], 1
0x1800042ab  mov     [rdx], eax
0x1800042ad  retn
```
