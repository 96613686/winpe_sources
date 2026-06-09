# __isa_available_init

- ea: `0x1800040f8`
- end: `0x18000437b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d48`
- `0x180003e84`

## callees

- `0x1800040f8`

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
0x1800040f8  push    rbx
0x1800040fa  push    rbp
0x1800040fb  push    rsi
0x1800040fc  push    rdi
0x1800040fd  sub     rsp, 18h
0x180004101  xor     eax, eax
0x180004103  xor     ecx, ecx
0x180004105  cpuid
0x180004107  xor     ecx, 6C65746Eh
0x18000410d  xor     edx, 49656E69h
0x180004113  or      edx, ecx
0x180004115  mov     ebp, eax
0x180004117  mov     eax, 1
0x18000411c  xor     ebx, 756E6547h
0x180004122  or      edx, ebx
0x180004124  lea     ecx, [rax-1]
0x180004127  cpuid
0x180004129  mov     edi, ecx
0x18000412b  jnz     short loc_18000418B
0x18000412d  and     eax, 0FFF3FF0h
0x180004132  mov     cs:__memset_fast_string_threshold, 8000h
0x18000413d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180004148  cmp     eax, 106C0h
0x18000414d  jz      short loc_180004177
0x18000414f  cmp     eax, 20660h
0x180004154  jz      short loc_180004177
0x180004156  cmp     eax, 20670h
0x18000415b  jz      short loc_180004177
0x18000415d  add     eax, 0FFFCF9B0h
0x180004162  cmp     eax, 20h ; ' '
0x180004165  ja      short loc_18000418B
0x180004167  mov     rcx, 100010001h
0x180004171  bt      rcx, rax
0x180004175  jnb     short loc_18000418B
0x180004177  mov     r8d, cs:__favor
0x18000417e  or      r8d, 1
0x180004182  mov     cs:__favor, r8d
0x180004189  jmp     short loc_180004192
0x18000418b  mov     r8d, cs:__favor
0x180004192  xor     r10d, r10d
0x180004195  xor     r11d, r11d
0x180004198  cmp     ebp, 7
0x18000419b  jl      short loc_1800041DF
0x18000419d  xor     ecx, ecx
0x18000419f  lea     eax, [r10+7]
0x1800041a3  cpuid
0x1800041a5  mov     esi, edx
0x1800041a7  mov     r9d, ebx
0x1800041aa  bt      ebx, 9
0x1800041ae  jnb     short loc_1800041BB
0x1800041b0  or      r8d, 2
0x1800041b4  mov     cs:__favor, r8d
0x1800041bb  cmp     eax, 1
0x1800041be  jl      short loc_1800041CD
0x1800041c0  mov     eax, 7
0x1800041c5  lea     ecx, [rax-6]
0x1800041c8  cpuid
0x1800041ca  mov     r10d, edx
0x1800041cd  mov     eax, 24h ; '$'
0x1800041d2  cmp     ebp, eax
0x1800041d4  jl      short loc_1800041E4
0x1800041d6  xor     ecx, ecx
0x1800041d8  cpuid
0x1800041da  mov     r11d, ebx
0x1800041dd  jmp     short loc_1800041E4
0x1800041df  xor     r9d, r9d
0x1800041e2  xor     esi, esi
0x1800041e4  mov     rax, cs:__isa_inverted
0x1800041eb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800041ef  mov     cs:__isa_available, 1
0x1800041f9  mov     cs:__isa_enabled, 2
0x180004203  mov     cs:__isa_inverted, rax
0x18000420a  bt      edi, 14h
0x18000420e  jnb     short loc_18000422F
0x180004210  and     rax, 0FFFFFFFFFFFFFFEFh
0x180004214  mov     cs:__isa_available, 2
0x18000421e  mov     cs:__isa_inverted, rax
0x180004225  mov     cs:__isa_enabled, 6
0x18000422f  bt      edi, 1Bh
0x180004233  jnb     loc_180004370
0x180004239  xor     ecx, ecx
0x18000423b  xgetbv
0x18000423e  shl     rdx, 20h
0x180004242  or      rdx, rax
0x180004245  mov     [rsp+38h+arg_0], rdx
0x18000424a  bt      edi, 1Ch
0x18000424e  jnb     loc_180004354
0x180004254  mov     rax, [rsp+38h+arg_0]
0x180004259  and     al, 6
0x18000425b  cmp     al, 6
0x18000425d  jnz     loc_180004354
0x180004263  mov     eax, cs:__isa_enabled
0x180004269  mov     dl, 0E0h
0x18000426b  or      eax, 8
0x18000426e  mov     cs:__isa_available, 3
0x180004278  mov     cs:__isa_enabled, eax
0x18000427e  test    r9b, 20h
0x180004282  jz      short loc_1800042E6
0x180004284  or      eax, 20h
0x180004287  mov     cs:__isa_available, 5
0x180004291  mov     cs:__isa_enabled, eax
0x180004297  mov     ecx, 0D0030000h
0x18000429c  mov     rax, cs:__isa_inverted
0x1800042a3  and     r9d, ecx
0x1800042a6  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800042aa  mov     cs:__isa_inverted, rax
0x1800042b1  cmp     r9d, ecx
0x1800042b4  jnz     short loc_1800042ED
0x1800042b6  mov     rax, [rsp+38h+arg_0]
0x1800042bb  and     al, dl
0x1800042bd  cmp     al, dl
0x1800042bf  jnz     short loc_1800042E6
0x1800042c1  mov     rax, cs:__isa_inverted
0x1800042c8  or      cs:__isa_enabled, 40h
0x1800042cf  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800042d3  mov     cs:__isa_available, 6
0x1800042dd  mov     cs:__isa_inverted, rax
0x1800042e4  jmp     short loc_1800042ED
0x1800042e6  mov     rax, cs:__isa_inverted
0x1800042ed  bt      esi, 17h
0x1800042f1  jnb     short loc_1800042FF
0x1800042f3  btr     rax, 18h
0x1800042f8  mov     cs:__isa_inverted, rax
0x1800042ff  bt      r10d, 13h
0x180004304  jnb     short loc_180004354
0x180004306  mov     rax, [rsp+38h+arg_0]
0x18000430b  and     al, dl
0x18000430d  cmp     al, dl
0x18000430f  jnz     short loc_180004354
0x180004311  mov     rdx, cs:__isa_inverted
0x180004318  mov     eax, r11d
0x18000431b  shr     rax, 10h
0x18000431f  mov     ecx, r11d
0x180004322  and     eax, 6
0x180004325  and     ecx, 400FFh
0x18000432b  or      rax, 1000029h
0x180004331  mov     cs:__avx10_version, ecx
0x180004337  not     rax
0x18000433a  and     rdx, rax
0x18000433d  mov     cs:__isa_inverted, rdx
0x180004344  cmp     cl, 1
0x180004347  jbe     short loc_180004354
0x180004349  and     rdx, 0FFFFFFFFFFFFFFBFh
0x18000434d  mov     cs:__isa_inverted, rdx
0x180004354  bt      r10d, 15h
0x180004359  jnb     short loc_180004370
0x18000435b  mov     rax, [rsp+38h+arg_0]
0x180004360  bt      rax, 13h
0x180004365  jnb     short loc_180004370
0x180004367  btr     cs:__isa_inverted, 7
0x180004370  xor     eax, eax
0x180004372  add     rsp, 18h
0x180004376  pop     rdi
0x180004377  pop     rsi
0x180004378  pop     rbp
0x180004379  pop     rbx
0x18000437a  retn
```
