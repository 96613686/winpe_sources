# __isa_available_init

- ea: `0x180002300`
- end: `0x180002583`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f2c`
- `0x180002068`

## callees

- `0x180002300`

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
0x180002300  push    rbx
0x180002302  push    rbp
0x180002303  push    rsi
0x180002304  push    rdi
0x180002305  sub     rsp, 18h
0x180002309  xor     eax, eax
0x18000230b  xor     ecx, ecx
0x18000230d  cpuid
0x18000230f  xor     ecx, 6C65746Eh
0x180002315  xor     edx, 49656E69h
0x18000231b  or      edx, ecx
0x18000231d  mov     ebp, eax
0x18000231f  mov     eax, 1
0x180002324  xor     ebx, 756E6547h
0x18000232a  or      edx, ebx
0x18000232c  lea     ecx, [rax-1]
0x18000232f  cpuid
0x180002331  mov     edi, ecx
0x180002333  jnz     short loc_180002393
0x180002335  and     eax, 0FFF3FF0h
0x18000233a  mov     cs:__memset_fast_string_threshold, 8000h
0x180002345  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002350  cmp     eax, 106C0h
0x180002355  jz      short loc_18000237F
0x180002357  cmp     eax, 20660h
0x18000235c  jz      short loc_18000237F
0x18000235e  cmp     eax, 20670h
0x180002363  jz      short loc_18000237F
0x180002365  add     eax, 0FFFCF9B0h
0x18000236a  cmp     eax, 20h ; ' '
0x18000236d  ja      short loc_180002393
0x18000236f  mov     rcx, 100010001h
0x180002379  bt      rcx, rax
0x18000237d  jnb     short loc_180002393
0x18000237f  mov     r8d, cs:__favor
0x180002386  or      r8d, 1
0x18000238a  mov     cs:__favor, r8d
0x180002391  jmp     short loc_18000239A
0x180002393  mov     r8d, cs:__favor
0x18000239a  xor     r10d, r10d
0x18000239d  xor     r11d, r11d
0x1800023a0  cmp     ebp, 7
0x1800023a3  jl      short loc_1800023E7
0x1800023a5  xor     ecx, ecx
0x1800023a7  lea     eax, [r10+7]
0x1800023ab  cpuid
0x1800023ad  mov     esi, edx
0x1800023af  mov     r9d, ebx
0x1800023b2  bt      ebx, 9
0x1800023b6  jnb     short loc_1800023C3
0x1800023b8  or      r8d, 2
0x1800023bc  mov     cs:__favor, r8d
0x1800023c3  cmp     eax, 1
0x1800023c6  jl      short loc_1800023D5
0x1800023c8  mov     eax, 7
0x1800023cd  lea     ecx, [rax-6]
0x1800023d0  cpuid
0x1800023d2  mov     r10d, edx
0x1800023d5  mov     eax, 24h ; '$'
0x1800023da  cmp     ebp, eax
0x1800023dc  jl      short loc_1800023EC
0x1800023de  xor     ecx, ecx
0x1800023e0  cpuid
0x1800023e2  mov     r11d, ebx
0x1800023e5  jmp     short loc_1800023EC
0x1800023e7  xor     r9d, r9d
0x1800023ea  xor     esi, esi
0x1800023ec  mov     rax, cs:__isa_inverted
0x1800023f3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800023f7  mov     cs:__isa_available, 1
0x180002401  mov     cs:__isa_enabled, 2
0x18000240b  mov     cs:__isa_inverted, rax
0x180002412  bt      edi, 14h
0x180002416  jnb     short loc_180002437
0x180002418  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000241c  mov     cs:__isa_available, 2
0x180002426  mov     cs:__isa_inverted, rax
0x18000242d  mov     cs:__isa_enabled, 6
0x180002437  bt      edi, 1Bh
0x18000243b  jnb     loc_180002578
0x180002441  xor     ecx, ecx
0x180002443  xgetbv
0x180002446  shl     rdx, 20h
0x18000244a  or      rdx, rax
0x18000244d  mov     [rsp+38h+arg_0], rdx
0x180002452  bt      edi, 1Ch
0x180002456  jnb     loc_18000255C
0x18000245c  mov     rax, [rsp+38h+arg_0]
0x180002461  and     al, 6
0x180002463  cmp     al, 6
0x180002465  jnz     loc_18000255C
0x18000246b  mov     eax, cs:__isa_enabled
0x180002471  mov     dl, 0E0h
0x180002473  or      eax, 8
0x180002476  mov     cs:__isa_available, 3
0x180002480  mov     cs:__isa_enabled, eax
0x180002486  test    r9b, 20h
0x18000248a  jz      short loc_1800024EE
0x18000248c  or      eax, 20h
0x18000248f  mov     cs:__isa_available, 5
0x180002499  mov     cs:__isa_enabled, eax
0x18000249f  mov     ecx, 0D0030000h
0x1800024a4  mov     rax, cs:__isa_inverted
0x1800024ab  and     r9d, ecx
0x1800024ae  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800024b2  mov     cs:__isa_inverted, rax
0x1800024b9  cmp     r9d, ecx
0x1800024bc  jnz     short loc_1800024F5
0x1800024be  mov     rax, [rsp+38h+arg_0]
0x1800024c3  and     al, dl
0x1800024c5  cmp     al, dl
0x1800024c7  jnz     short loc_1800024EE
0x1800024c9  mov     rax, cs:__isa_inverted
0x1800024d0  or      cs:__isa_enabled, 40h
0x1800024d7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800024db  mov     cs:__isa_available, 6
0x1800024e5  mov     cs:__isa_inverted, rax
0x1800024ec  jmp     short loc_1800024F5
0x1800024ee  mov     rax, cs:__isa_inverted
0x1800024f5  bt      esi, 17h
0x1800024f9  jnb     short loc_180002507
0x1800024fb  btr     rax, 18h
0x180002500  mov     cs:__isa_inverted, rax
0x180002507  bt      r10d, 13h
0x18000250c  jnb     short loc_18000255C
0x18000250e  mov     rax, [rsp+38h+arg_0]
0x180002513  and     al, dl
0x180002515  cmp     al, dl
0x180002517  jnz     short loc_18000255C
0x180002519  mov     rdx, cs:__isa_inverted
0x180002520  mov     eax, r11d
0x180002523  shr     rax, 10h
0x180002527  mov     ecx, r11d
0x18000252a  and     eax, 6
0x18000252d  and     ecx, 400FFh
0x180002533  or      rax, 1000029h
0x180002539  mov     cs:__avx10_version, ecx
0x18000253f  not     rax
0x180002542  and     rdx, rax
0x180002545  mov     cs:__isa_inverted, rdx
0x18000254c  cmp     cl, 1
0x18000254f  jbe     short loc_18000255C
0x180002551  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002555  mov     cs:__isa_inverted, rdx
0x18000255c  bt      r10d, 15h
0x180002561  jnb     short loc_180002578
0x180002563  mov     rax, [rsp+38h+arg_0]
0x180002568  bt      rax, 13h
0x18000256d  jnb     short loc_180002578
0x18000256f  btr     cs:__isa_inverted, 7
0x180002578  xor     eax, eax
0x18000257a  add     rsp, 18h
0x18000257e  pop     rdi
0x18000257f  pop     rsi
0x180002580  pop     rbp
0x180002581  pop     rbx
0x180002582  retn
```
