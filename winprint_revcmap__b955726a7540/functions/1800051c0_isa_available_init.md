# __isa_available_init

- ea: `0x1800051c0`
- end: `0x180005443`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dec`
- `0x180004f28`

## callees

- `0x1800051c0`

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
0x1800051c0  push    rbx
0x1800051c2  push    rbp
0x1800051c3  push    rsi
0x1800051c4  push    rdi
0x1800051c5  sub     rsp, 18h
0x1800051c9  xor     eax, eax
0x1800051cb  xor     ecx, ecx
0x1800051cd  cpuid
0x1800051cf  xor     ecx, 6C65746Eh
0x1800051d5  xor     edx, 49656E69h
0x1800051db  or      edx, ecx
0x1800051dd  mov     ebp, eax
0x1800051df  mov     eax, 1
0x1800051e4  xor     ebx, 756E6547h
0x1800051ea  or      edx, ebx
0x1800051ec  lea     ecx, [rax-1]
0x1800051ef  cpuid
0x1800051f1  mov     edi, ecx
0x1800051f3  jnz     short loc_180005253
0x1800051f5  and     eax, 0FFF3FF0h
0x1800051fa  mov     cs:__memset_fast_string_threshold, 8000h
0x180005205  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180005210  cmp     eax, 106C0h
0x180005215  jz      short loc_18000523F
0x180005217  cmp     eax, 20660h
0x18000521c  jz      short loc_18000523F
0x18000521e  cmp     eax, 20670h
0x180005223  jz      short loc_18000523F
0x180005225  add     eax, 0FFFCF9B0h
0x18000522a  cmp     eax, 20h ; ' '
0x18000522d  ja      short loc_180005253
0x18000522f  mov     rcx, 100010001h
0x180005239  bt      rcx, rax
0x18000523d  jnb     short loc_180005253
0x18000523f  mov     r8d, cs:__favor
0x180005246  or      r8d, 1
0x18000524a  mov     cs:__favor, r8d
0x180005251  jmp     short loc_18000525A
0x180005253  mov     r8d, cs:__favor
0x18000525a  xor     r10d, r10d
0x18000525d  xor     r11d, r11d
0x180005260  cmp     ebp, 7
0x180005263  jl      short loc_1800052A7
0x180005265  xor     ecx, ecx
0x180005267  lea     eax, [r10+7]
0x18000526b  cpuid
0x18000526d  mov     esi, edx
0x18000526f  mov     r9d, ebx
0x180005272  bt      ebx, 9
0x180005276  jnb     short loc_180005283
0x180005278  or      r8d, 2
0x18000527c  mov     cs:__favor, r8d
0x180005283  cmp     eax, 1
0x180005286  jl      short loc_180005295
0x180005288  mov     eax, 7
0x18000528d  lea     ecx, [rax-6]
0x180005290  cpuid
0x180005292  mov     r10d, edx
0x180005295  mov     eax, 24h ; '$'
0x18000529a  cmp     ebp, eax
0x18000529c  jl      short loc_1800052AC
0x18000529e  xor     ecx, ecx
0x1800052a0  cpuid
0x1800052a2  mov     r11d, ebx
0x1800052a5  jmp     short loc_1800052AC
0x1800052a7  xor     r9d, r9d
0x1800052aa  xor     esi, esi
0x1800052ac  mov     rax, cs:__isa_inverted
0x1800052b3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800052b7  mov     cs:__isa_available, 1
0x1800052c1  mov     cs:__isa_enabled, 2
0x1800052cb  mov     cs:__isa_inverted, rax
0x1800052d2  bt      edi, 14h
0x1800052d6  jnb     short loc_1800052F7
0x1800052d8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800052dc  mov     cs:__isa_available, 2
0x1800052e6  mov     cs:__isa_inverted, rax
0x1800052ed  mov     cs:__isa_enabled, 6
0x1800052f7  bt      edi, 1Bh
0x1800052fb  jnb     loc_180005438
0x180005301  xor     ecx, ecx
0x180005303  xgetbv
0x180005306  shl     rdx, 20h
0x18000530a  or      rdx, rax
0x18000530d  mov     [rsp+38h+arg_0], rdx
0x180005312  bt      edi, 1Ch
0x180005316  jnb     loc_18000541C
0x18000531c  mov     rax, [rsp+38h+arg_0]
0x180005321  and     al, 6
0x180005323  cmp     al, 6
0x180005325  jnz     loc_18000541C
0x18000532b  mov     eax, cs:__isa_enabled
0x180005331  mov     dl, 0E0h
0x180005333  or      eax, 8
0x180005336  mov     cs:__isa_available, 3
0x180005340  mov     cs:__isa_enabled, eax
0x180005346  test    r9b, 20h
0x18000534a  jz      short loc_1800053AE
0x18000534c  or      eax, 20h
0x18000534f  mov     cs:__isa_available, 5
0x180005359  mov     cs:__isa_enabled, eax
0x18000535f  mov     ecx, 0D0030000h
0x180005364  mov     rax, cs:__isa_inverted
0x18000536b  and     r9d, ecx
0x18000536e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180005372  mov     cs:__isa_inverted, rax
0x180005379  cmp     r9d, ecx
0x18000537c  jnz     short loc_1800053B5
0x18000537e  mov     rax, [rsp+38h+arg_0]
0x180005383  and     al, dl
0x180005385  cmp     al, dl
0x180005387  jnz     short loc_1800053AE
0x180005389  mov     rax, cs:__isa_inverted
0x180005390  or      cs:__isa_enabled, 40h
0x180005397  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000539b  mov     cs:__isa_available, 6
0x1800053a5  mov     cs:__isa_inverted, rax
0x1800053ac  jmp     short loc_1800053B5
0x1800053ae  mov     rax, cs:__isa_inverted
0x1800053b5  bt      esi, 17h
0x1800053b9  jnb     short loc_1800053C7
0x1800053bb  btr     rax, 18h
0x1800053c0  mov     cs:__isa_inverted, rax
0x1800053c7  bt      r10d, 13h
0x1800053cc  jnb     short loc_18000541C
0x1800053ce  mov     rax, [rsp+38h+arg_0]
0x1800053d3  and     al, dl
0x1800053d5  cmp     al, dl
0x1800053d7  jnz     short loc_18000541C
0x1800053d9  mov     rdx, cs:__isa_inverted
0x1800053e0  mov     eax, r11d
0x1800053e3  shr     rax, 10h
0x1800053e7  mov     ecx, r11d
0x1800053ea  and     eax, 6
0x1800053ed  and     ecx, 400FFh
0x1800053f3  or      rax, 1000029h
0x1800053f9  mov     cs:__avx10_version, ecx
0x1800053ff  not     rax
0x180005402  and     rdx, rax
0x180005405  mov     cs:__isa_inverted, rdx
0x18000540c  cmp     cl, 1
0x18000540f  jbe     short loc_18000541C
0x180005411  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180005415  mov     cs:__isa_inverted, rdx
0x18000541c  bt      r10d, 15h
0x180005421  jnb     short loc_180005438
0x180005423  mov     rax, [rsp+38h+arg_0]
0x180005428  bt      rax, 13h
0x18000542d  jnb     short loc_180005438
0x18000542f  btr     cs:__isa_inverted, 7
0x180005438  xor     eax, eax
0x18000543a  add     rsp, 18h
0x18000543e  pop     rdi
0x18000543f  pop     rsi
0x180005440  pop     rbp
0x180005441  pop     rbx
0x180005442  retn
```
