# __isa_available_init

- ea: `0x180002b50`
- end: `0x180002dd3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002574`
- `0x1800026b0`

## callees

- `0x180002b50`

## pseudocode

```c
int __cdecl _isa_available_init()
{
  int v5; // ebp
  bool v7; // zf
  int v12; // edi
  int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // r10d
  unsigned int v18; // r11d
  int v24; // esi
  int v25; // r9d
  unsigned __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  int v41; // [rsp+40h] [rbp+8h]

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  v7 = ((unsigned int)_RBX ^ 0x756E6547 | (unsigned int)_RCX ^ 0x6C65746E | (unsigned int)_RDX ^ 0x49656E69) == 0;
  __asm { cpuid }
  v12 = _RCX;
  if ( v7
    && ((v13 = _RAX & 0xFFF3FF0, _memset_fast_string_threshold = 0x8000, _memset_nt_threshold = -1, v13 == 67264)
     || v13 == 132704
     || v13 == 132720
     || (v14 = (unsigned int)(v13 - 198224), (unsigned int)v14 <= 0x20) && (v15 = 0x100010001LL, _bittest64(&v15, v14))) )
  {
    v16 = _favor | 1;
    _favor |= 1u;
  }
  else
  {
    v16 = _favor;
  }
  v17 = 0;
  v18 = 0;
  if ( v5 < 7 )
  {
    v25 = 0;
    v24 = 0;
  }
  else
  {
    _RAX = 7;
    __asm { cpuid }
    v24 = _RDX;
    v25 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v16 | 2;
    if ( (int)_RAX >= 1 )
    {
      _RAX = 7;
      __asm { cpuid }
      v17 = _RDX;
    }
    _RAX = 36;
    if ( v5 >= 36 )
    {
      __asm { cpuid }
      v18 = _RBX;
    }
  }
  v36 = _isa_inverted & 0xFFFFFFFFFFFFFFFEuLL;
  _isa_available = 1;
  _isa_enabled = 2;
  _isa_inverted &= ~1uLL;
  if ( (v12 & 0x100000) != 0 )
  {
    v36 &= ~0x10uLL;
    _isa_available = 2;
    _isa_inverted = v36;
    _isa_enabled = 6;
  }
  if ( (v12 & 0x8000000) != 0 )
  {
    __asm { xgetbv }
    v41 = v36;
    if ( (v12 & 0x10000000) == 0 || (v36 & 6) != 6 )
    {
LABEL_33:
      if ( (v17 & 0x200000) != 0 && (*(_QWORD *)&v41 & 0x80000LL) != 0 )
        _isa_inverted &= ~0x80uLL;
      return 0;
    }
    v37 = _isa_enabled | 8;
    _isa_available = 3;
    _isa_enabled |= 8u;
    if ( (v25 & 0x20) != 0 )
    {
      _isa_available = 5;
      _isa_enabled = v37 | 0x20;
      v38 = _isa_inverted & 0xFFFFFFFFFFFFFFFDuLL;
      _isa_inverted &= ~2uLL;
      if ( (v25 & 0xD0030000) != 0xD0030000 )
      {
LABEL_27:
        if ( (v24 & 0x800000) != 0 )
          _isa_inverted = v38 & 0xFFFFFFFFFEFFFFFFuLL;
        if ( (v17 & 0x80000) != 0 && (v41 & 0xE0) == 0xE0 )
        {
          _avx10_version = v18 & 0x400FF;
          v39 = ~(HIWORD(v18) & 6 | 0x1000029LL) & _isa_inverted;
          _isa_inverted = v39;
          if ( (unsigned __int8)v18 > 1u )
            _isa_inverted = v39 & 0xFFFFFFFFFFFFFFBFuLL;
        }
        goto LABEL_33;
      }
      if ( (v41 & 0xE0) == 0xE0 )
      {
        _isa_enabled |= 0x40u;
        v38 = _isa_inverted & 0xFFFFFFFFFFFFFFDBuLL;
        _isa_available = 6;
        _isa_inverted &= 0xFFFFFFFFFFFFFFDBuLL;
        goto LABEL_27;
      }
    }
    v38 = _isa_inverted;
    goto LABEL_27;
  }
  return 0;
}

```

## disassembly

```asm
0x180002b50  push    rbx
0x180002b52  push    rbp
0x180002b53  push    rsi
0x180002b54  push    rdi
0x180002b55  sub     rsp, 18h
0x180002b59  xor     eax, eax
0x180002b5b  xor     ecx, ecx
0x180002b5d  cpuid
0x180002b5f  xor     ecx, 6C65746Eh
0x180002b65  xor     edx, 49656E69h
0x180002b6b  or      edx, ecx
0x180002b6d  mov     ebp, eax
0x180002b6f  mov     eax, 1
0x180002b74  xor     ebx, 756E6547h
0x180002b7a  or      edx, ebx
0x180002b7c  lea     ecx, [rax-1]
0x180002b7f  cpuid
0x180002b81  mov     edi, ecx
0x180002b83  jnz     short loc_180002BE3
0x180002b85  and     eax, 0FFF3FF0h
0x180002b8a  mov     cs:__memset_fast_string_threshold, 8000h
0x180002b95  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002ba0  cmp     eax, 106C0h
0x180002ba5  jz      short loc_180002BCF
0x180002ba7  cmp     eax, 20660h
0x180002bac  jz      short loc_180002BCF
0x180002bae  cmp     eax, 20670h
0x180002bb3  jz      short loc_180002BCF
0x180002bb5  add     eax, 0FFFCF9B0h
0x180002bba  cmp     eax, 20h ; ' '
0x180002bbd  ja      short loc_180002BE3
0x180002bbf  mov     rcx, 100010001h
0x180002bc9  bt      rcx, rax
0x180002bcd  jnb     short loc_180002BE3
0x180002bcf  mov     r8d, cs:__favor
0x180002bd6  or      r8d, 1
0x180002bda  mov     cs:__favor, r8d
0x180002be1  jmp     short loc_180002BEA
0x180002be3  mov     r8d, cs:__favor
0x180002bea  xor     r10d, r10d
0x180002bed  xor     r11d, r11d
0x180002bf0  cmp     ebp, 7
0x180002bf3  jl      short loc_180002C37
0x180002bf5  xor     ecx, ecx
0x180002bf7  lea     eax, [r10+7]
0x180002bfb  cpuid
0x180002bfd  mov     esi, edx
0x180002bff  mov     r9d, ebx
0x180002c02  bt      ebx, 9
0x180002c06  jnb     short loc_180002C13
0x180002c08  or      r8d, 2
0x180002c0c  mov     cs:__favor, r8d
0x180002c13  cmp     eax, 1
0x180002c16  jl      short loc_180002C25
0x180002c18  mov     eax, 7
0x180002c1d  lea     ecx, [rax-6]
0x180002c20  cpuid
0x180002c22  mov     r10d, edx
0x180002c25  mov     eax, 24h ; '$'
0x180002c2a  cmp     ebp, eax
0x180002c2c  jl      short loc_180002C3C
0x180002c2e  xor     ecx, ecx
0x180002c30  cpuid
0x180002c32  mov     r11d, ebx
0x180002c35  jmp     short loc_180002C3C
0x180002c37  xor     r9d, r9d
0x180002c3a  xor     esi, esi
0x180002c3c  mov     rax, cs:__isa_inverted
0x180002c43  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002c47  mov     cs:__isa_available, 1
0x180002c51  mov     cs:__isa_enabled, 2
0x180002c5b  mov     cs:__isa_inverted, rax
0x180002c62  bt      edi, 14h
0x180002c66  jnb     short loc_180002C87
0x180002c68  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002c6c  mov     cs:__isa_available, 2
0x180002c76  mov     cs:__isa_inverted, rax
0x180002c7d  mov     cs:__isa_enabled, 6
0x180002c87  bt      edi, 1Bh
0x180002c8b  jnb     loc_180002DC8
0x180002c91  xor     ecx, ecx
0x180002c93  xgetbv
0x180002c96  shl     rdx, 20h
0x180002c9a  or      rdx, rax
0x180002c9d  mov     [rsp+38h+arg_0], rdx
0x180002ca2  bt      edi, 1Ch
0x180002ca6  jnb     loc_180002DAC
0x180002cac  mov     rax, [rsp+38h+arg_0]
0x180002cb1  and     al, 6
0x180002cb3  cmp     al, 6
0x180002cb5  jnz     loc_180002DAC
0x180002cbb  mov     eax, cs:__isa_enabled
0x180002cc1  mov     dl, 0E0h
0x180002cc3  or      eax, 8
0x180002cc6  mov     cs:__isa_available, 3
0x180002cd0  mov     cs:__isa_enabled, eax
0x180002cd6  test    r9b, 20h
0x180002cda  jz      short loc_180002D3E
0x180002cdc  or      eax, 20h
0x180002cdf  mov     cs:__isa_available, 5
0x180002ce9  mov     cs:__isa_enabled, eax
0x180002cef  mov     ecx, 0D0030000h
0x180002cf4  mov     rax, cs:__isa_inverted
0x180002cfb  and     r9d, ecx
0x180002cfe  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002d02  mov     cs:__isa_inverted, rax
0x180002d09  cmp     r9d, ecx
0x180002d0c  jnz     short loc_180002D45
0x180002d0e  mov     rax, [rsp+38h+arg_0]
0x180002d13  and     al, dl
0x180002d15  cmp     al, dl
0x180002d17  jnz     short loc_180002D3E
0x180002d19  mov     rax, cs:__isa_inverted
0x180002d20  or      cs:__isa_enabled, 40h
0x180002d27  and     rax, 0FFFFFFFFFFFFFFDBh
0x180002d2b  mov     cs:__isa_available, 6
0x180002d35  mov     cs:__isa_inverted, rax
0x180002d3c  jmp     short loc_180002D45
0x180002d3e  mov     rax, cs:__isa_inverted
0x180002d45  bt      esi, 17h
0x180002d49  jnb     short loc_180002D57
0x180002d4b  btr     rax, 18h
0x180002d50  mov     cs:__isa_inverted, rax
0x180002d57  bt      r10d, 13h
0x180002d5c  jnb     short loc_180002DAC
0x180002d5e  mov     rax, [rsp+38h+arg_0]
0x180002d63  and     al, dl
0x180002d65  cmp     al, dl
0x180002d67  jnz     short loc_180002DAC
0x180002d69  mov     rdx, cs:__isa_inverted
0x180002d70  mov     eax, r11d
0x180002d73  shr     rax, 10h
0x180002d77  mov     ecx, r11d
0x180002d7a  and     eax, 6
0x180002d7d  and     ecx, 400FFh
0x180002d83  or      rax, 1000029h
0x180002d89  mov     cs:__avx10_version, ecx
0x180002d8f  not     rax
0x180002d92  and     rdx, rax
0x180002d95  mov     cs:__isa_inverted, rdx
0x180002d9c  cmp     cl, 1
0x180002d9f  jbe     short loc_180002DAC
0x180002da1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002da5  mov     cs:__isa_inverted, rdx
0x180002dac  bt      r10d, 15h
0x180002db1  jnb     short loc_180002DC8
0x180002db3  mov     rax, [rsp+38h+arg_0]
0x180002db8  bt      rax, 13h
0x180002dbd  jnb     short loc_180002DC8
0x180002dbf  btr     cs:__isa_inverted, 7
0x180002dc8  xor     eax, eax
0x180002dca  add     rsp, 18h
0x180002dce  pop     rdi
0x180002dcf  pop     rsi
0x180002dd0  pop     rbp
0x180002dd1  pop     rbx
0x180002dd2  retn
```
