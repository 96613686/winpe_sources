# __isa_available_init

- ea: `0x140005140`
- end: `0x1400053c3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004c34`

## callees

- `0x140005140`

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
0x140005140  push    rbx
0x140005142  push    rbp
0x140005143  push    rsi
0x140005144  push    rdi
0x140005145  sub     rsp, 18h
0x140005149  xor     eax, eax
0x14000514b  xor     ecx, ecx
0x14000514d  cpuid
0x14000514f  xor     ecx, 6C65746Eh
0x140005155  xor     edx, 49656E69h
0x14000515b  or      edx, ecx
0x14000515d  mov     ebp, eax
0x14000515f  mov     eax, 1
0x140005164  xor     ebx, 756E6547h
0x14000516a  or      edx, ebx
0x14000516c  lea     ecx, [rax-1]
0x14000516f  cpuid
0x140005171  mov     edi, ecx
0x140005173  jnz     short loc_1400051D3
0x140005175  and     eax, 0FFF3FF0h
0x14000517a  mov     cs:__memset_fast_string_threshold, 8000h
0x140005185  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140005190  cmp     eax, 106C0h
0x140005195  jz      short loc_1400051BF
0x140005197  cmp     eax, 20660h
0x14000519c  jz      short loc_1400051BF
0x14000519e  cmp     eax, 20670h
0x1400051a3  jz      short loc_1400051BF
0x1400051a5  add     eax, 0FFFCF9B0h
0x1400051aa  cmp     eax, 20h ; ' '
0x1400051ad  ja      short loc_1400051D3
0x1400051af  mov     rcx, 100010001h
0x1400051b9  bt      rcx, rax
0x1400051bd  jnb     short loc_1400051D3
0x1400051bf  mov     r8d, cs:__favor
0x1400051c6  or      r8d, 1
0x1400051ca  mov     cs:__favor, r8d
0x1400051d1  jmp     short loc_1400051DA
0x1400051d3  mov     r8d, cs:__favor
0x1400051da  xor     r10d, r10d
0x1400051dd  xor     r11d, r11d
0x1400051e0  cmp     ebp, 7
0x1400051e3  jl      short loc_140005227
0x1400051e5  xor     ecx, ecx
0x1400051e7  lea     eax, [r10+7]
0x1400051eb  cpuid
0x1400051ed  mov     esi, edx
0x1400051ef  mov     r9d, ebx
0x1400051f2  bt      ebx, 9
0x1400051f6  jnb     short loc_140005203
0x1400051f8  or      r8d, 2
0x1400051fc  mov     cs:__favor, r8d
0x140005203  cmp     eax, 1
0x140005206  jl      short loc_140005215
0x140005208  mov     eax, 7
0x14000520d  lea     ecx, [rax-6]
0x140005210  cpuid
0x140005212  mov     r10d, edx
0x140005215  mov     eax, 24h ; '$'
0x14000521a  cmp     ebp, eax
0x14000521c  jl      short loc_14000522C
0x14000521e  xor     ecx, ecx
0x140005220  cpuid
0x140005222  mov     r11d, ebx
0x140005225  jmp     short loc_14000522C
0x140005227  xor     r9d, r9d
0x14000522a  xor     esi, esi
0x14000522c  mov     rax, cs:__isa_inverted
0x140005233  and     rax, 0FFFFFFFFFFFFFFFEh
0x140005237  mov     cs:__isa_available, 1
0x140005241  mov     cs:__isa_enabled, 2
0x14000524b  mov     cs:__isa_inverted, rax
0x140005252  bt      edi, 14h
0x140005256  jnb     short loc_140005277
0x140005258  and     rax, 0FFFFFFFFFFFFFFEFh
0x14000525c  mov     cs:__isa_available, 2
0x140005266  mov     cs:__isa_inverted, rax
0x14000526d  mov     cs:__isa_enabled, 6
0x140005277  bt      edi, 1Bh
0x14000527b  jnb     loc_1400053B8
0x140005281  xor     ecx, ecx
0x140005283  xgetbv
0x140005286  shl     rdx, 20h
0x14000528a  or      rdx, rax
0x14000528d  mov     [rsp+38h+arg_0], rdx
0x140005292  bt      edi, 1Ch
0x140005296  jnb     loc_14000539C
0x14000529c  mov     rax, [rsp+38h+arg_0]
0x1400052a1  and     al, 6
0x1400052a3  cmp     al, 6
0x1400052a5  jnz     loc_14000539C
0x1400052ab  mov     eax, cs:__isa_enabled
0x1400052b1  mov     dl, 0E0h
0x1400052b3  or      eax, 8
0x1400052b6  mov     cs:__isa_available, 3
0x1400052c0  mov     cs:__isa_enabled, eax
0x1400052c6  test    r9b, 20h
0x1400052ca  jz      short loc_14000532E
0x1400052cc  or      eax, 20h
0x1400052cf  mov     cs:__isa_available, 5
0x1400052d9  mov     cs:__isa_enabled, eax
0x1400052df  mov     ecx, 0D0030000h
0x1400052e4  mov     rax, cs:__isa_inverted
0x1400052eb  and     r9d, ecx
0x1400052ee  and     rax, 0FFFFFFFFFFFFFFFDh
0x1400052f2  mov     cs:__isa_inverted, rax
0x1400052f9  cmp     r9d, ecx
0x1400052fc  jnz     short loc_140005335
0x1400052fe  mov     rax, [rsp+38h+arg_0]
0x140005303  and     al, dl
0x140005305  cmp     al, dl
0x140005307  jnz     short loc_14000532E
0x140005309  mov     rax, cs:__isa_inverted
0x140005310  or      cs:__isa_enabled, 40h
0x140005317  and     rax, 0FFFFFFFFFFFFFFDBh
0x14000531b  mov     cs:__isa_available, 6
0x140005325  mov     cs:__isa_inverted, rax
0x14000532c  jmp     short loc_140005335
0x14000532e  mov     rax, cs:__isa_inverted
0x140005335  bt      esi, 17h
0x140005339  jnb     short loc_140005347
0x14000533b  btr     rax, 18h
0x140005340  mov     cs:__isa_inverted, rax
0x140005347  bt      r10d, 13h
0x14000534c  jnb     short loc_14000539C
0x14000534e  mov     rax, [rsp+38h+arg_0]
0x140005353  and     al, dl
0x140005355  cmp     al, dl
0x140005357  jnz     short loc_14000539C
0x140005359  mov     rdx, cs:__isa_inverted
0x140005360  mov     eax, r11d
0x140005363  shr     rax, 10h
0x140005367  mov     ecx, r11d
0x14000536a  and     eax, 6
0x14000536d  and     ecx, 400FFh
0x140005373  or      rax, 1000029h
0x140005379  mov     cs:__avx10_version, ecx
0x14000537f  not     rax
0x140005382  and     rdx, rax
0x140005385  mov     cs:__isa_inverted, rdx
0x14000538c  cmp     cl, 1
0x14000538f  jbe     short loc_14000539C
0x140005391  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140005395  mov     cs:__isa_inverted, rdx
0x14000539c  bt      r10d, 15h
0x1400053a1  jnb     short loc_1400053B8
0x1400053a3  mov     rax, [rsp+38h+arg_0]
0x1400053a8  bt      rax, 13h
0x1400053ad  jnb     short loc_1400053B8
0x1400053af  btr     cs:__isa_inverted, 7
0x1400053b8  xor     eax, eax
0x1400053ba  add     rsp, 18h
0x1400053be  pop     rdi
0x1400053bf  pop     rsi
0x1400053c0  pop     rbp
0x1400053c1  pop     rbx
0x1400053c2  retn
```
