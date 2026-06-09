# __isa_available_init

- ea: `0x140002098`
- end: `0x14000232d`
- name: `__isa_available_init`
- size: `661`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400019b4`

## callees

- `0x140002098`

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
  int v17; // r9d
  int v18; // esi
  int v19; // r10d
  unsigned int v20; // r11d
  unsigned __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // rax
  __int64 v39; // rcx
  int v41; // [rsp+20h] [rbp+8h]

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
  v19 = 0;
  v20 = 0;
  if ( v5 >= 7 )
  {
    _RAX = 7;
    __asm { cpuid }
    v18 = _RDX;
    v17 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v16 | 2;
    if ( (int)_RAX >= 1 )
    {
      _RAX = 7;
      __asm { cpuid }
      v19 = _RDX;
    }
    _RAX = 36;
    if ( v5 >= 36 )
    {
      __asm { cpuid }
      v20 = _RBX;
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
LABEL_32:
      if ( (v19 & 0x200000) != 0 && (*(_QWORD *)&v41 & 0x80000LL) != 0 )
        _isa_inverted &= ~0x80uLL;
      return 0;
    }
    v37 = _isa_enabled | 8;
    _isa_available = 3;
    _isa_enabled |= 8u;
    if ( (v17 & 0x20) != 0 )
    {
      _isa_available = 5;
      _isa_enabled = v37 | 0x20;
      v38 = _isa_inverted & 0xFFFFFFFFFFFFFFFDuLL;
      _isa_inverted &= ~2uLL;
      if ( (v17 & 0xD0030000) != 0xD0030000 )
      {
LABEL_26:
        if ( (v18 & 0x800000) != 0 )
          _isa_inverted = v38 & 0xFFFFFFFFFEFFFFFFuLL;
        if ( (v19 & 0x80000) != 0 && (v41 & 0xE0) == 0xE0 )
        {
          _avx10_version = v20 & 0x400FF;
          v39 = _isa_inverted & ~(HIWORD(v20) & 6 | 0x1000029LL);
          _isa_inverted = v39;
          if ( (unsigned __int8)v20 > 1u )
            _isa_inverted = v39 & 0xFFFFFFFFFFFFFFBFuLL;
        }
        goto LABEL_32;
      }
      if ( (v41 & 0xE0) == 0xE0 )
      {
        _isa_enabled |= 0x40u;
        v38 = _isa_inverted & 0xFFFFFFFFFFFFFFDBuLL;
        _isa_available = 6;
        _isa_inverted &= 0xFFFFFFFFFFFFFFDBuLL;
        goto LABEL_26;
      }
    }
    v38 = _isa_inverted;
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x140002098  mov     [rsp+arg_8], rbx
0x14000209d  mov     [rsp+arg_10], rbp
0x1400020a2  mov     [rsp+arg_18], rsi
0x1400020a7  push    rdi
0x1400020a8  sub     rsp, 10h
0x1400020ac  xor     eax, eax
0x1400020ae  xor     ecx, ecx
0x1400020b0  cpuid
0x1400020b2  xor     ecx, 6C65746Eh
0x1400020b8  xor     edx, 49656E69h
0x1400020be  or      edx, ecx
0x1400020c0  mov     ebp, eax
0x1400020c2  mov     eax, 1
0x1400020c7  xor     ebx, 756E6547h
0x1400020cd  or      edx, ebx
0x1400020cf  lea     ecx, [rax-1]
0x1400020d2  cpuid
0x1400020d4  mov     edi, ecx
0x1400020d6  jnz     short loc_140002136
0x1400020d8  and     eax, 0FFF3FF0h
0x1400020dd  mov     cs:__memset_fast_string_threshold, 8000h
0x1400020e8  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1400020f3  cmp     eax, 106C0h
0x1400020f8  jz      short loc_140002122
0x1400020fa  cmp     eax, 20660h
0x1400020ff  jz      short loc_140002122
0x140002101  cmp     eax, 20670h
0x140002106  jz      short loc_140002122
0x140002108  add     eax, 0FFFCF9B0h
0x14000210d  cmp     eax, 20h ; ' '
0x140002110  ja      short loc_140002136
0x140002112  mov     rcx, 100010001h
0x14000211c  bt      rcx, rax
0x140002120  jnb     short loc_140002136
0x140002122  mov     r8d, cs:__favor
0x140002129  or      r8d, 1
0x14000212d  mov     cs:__favor, r8d
0x140002134  jmp     short loc_14000213D
0x140002136  mov     r8d, cs:__favor
0x14000213d  xor     r9d, r9d
0x140002140  mov     esi, r9d
0x140002143  mov     r10d, r9d
0x140002146  mov     r11d, r9d
0x140002149  cmp     ebp, 7
0x14000214c  jl      short loc_14000218E
0x14000214e  lea     eax, [r9+7]
0x140002152  xor     ecx, ecx
0x140002154  cpuid
0x140002156  mov     esi, edx
0x140002158  mov     r9d, ebx
0x14000215b  bt      ebx, 9
0x14000215f  jnb     short loc_14000216C
0x140002161  or      r8d, 2
0x140002165  mov     cs:__favor, r8d
0x14000216c  cmp     eax, 1
0x14000216f  jl      short loc_14000217E
0x140002171  mov     eax, 7
0x140002176  lea     ecx, [rax-6]
0x140002179  cpuid
0x14000217b  mov     r10d, edx
0x14000217e  mov     eax, 24h ; '$'
0x140002183  cmp     ebp, eax
0x140002185  jl      short loc_14000218E
0x140002187  xor     ecx, ecx
0x140002189  cpuid
0x14000218b  mov     r11d, ebx
0x14000218e  mov     rax, cs:__isa_inverted
0x140002195  and     rax, 0FFFFFFFFFFFFFFFEh
0x140002199  mov     cs:__isa_available, 1
0x1400021a3  mov     cs:__isa_enabled, 2
0x1400021ad  mov     cs:__isa_inverted, rax
0x1400021b4  bt      edi, 14h
0x1400021b8  jnb     short loc_1400021D9
0x1400021ba  and     rax, 0FFFFFFFFFFFFFFEFh
0x1400021be  mov     cs:__isa_available, 2
0x1400021c8  mov     cs:__isa_inverted, rax
0x1400021cf  mov     cs:__isa_enabled, 6
0x1400021d9  bt      edi, 1Bh
0x1400021dd  jnb     loc_140002316
0x1400021e3  xor     ecx, ecx
0x1400021e5  xgetbv
0x1400021e8  shl     rdx, 20h
0x1400021ec  or      rdx, rax
0x1400021ef  mov     [rsp+18h+arg_0], rdx
0x1400021f4  bt      edi, 1Ch
0x1400021f8  jnb     loc_1400022FA
0x1400021fe  mov     rax, [rsp+18h+arg_0]
0x140002203  and     al, 6
0x140002205  cmp     al, 6
0x140002207  jnz     loc_1400022FA
0x14000220d  mov     eax, cs:__isa_enabled
0x140002213  mov     dl, 0E0h
0x140002215  or      eax, 8
0x140002218  mov     cs:__isa_available, 3
0x140002222  mov     cs:__isa_enabled, eax
0x140002228  test    r9b, 20h
0x14000222c  jz      short loc_140002290
0x14000222e  or      eax, 20h
0x140002231  mov     cs:__isa_available, 5
0x14000223b  mov     cs:__isa_enabled, eax
0x140002241  mov     ecx, 0D0030000h
0x140002246  mov     rax, cs:__isa_inverted
0x14000224d  and     r9d, ecx
0x140002250  and     rax, 0FFFFFFFFFFFFFFFDh
0x140002254  mov     cs:__isa_inverted, rax
0x14000225b  cmp     r9d, ecx
0x14000225e  jnz     short loc_140002297
0x140002260  mov     rax, [rsp+18h+arg_0]
0x140002265  and     al, dl
0x140002267  cmp     al, dl
0x140002269  jnz     short loc_140002290
0x14000226b  mov     rax, cs:__isa_inverted
0x140002272  or      cs:__isa_enabled, 40h
0x140002279  and     rax, 0FFFFFFFFFFFFFFDBh
0x14000227d  mov     cs:__isa_available, 6
0x140002287  mov     cs:__isa_inverted, rax
0x14000228e  jmp     short loc_140002297
0x140002290  mov     rax, cs:__isa_inverted
0x140002297  bt      esi, 17h
0x14000229b  jnb     short loc_1400022A9
0x14000229d  btr     rax, 18h
0x1400022a2  mov     cs:__isa_inverted, rax
0x1400022a9  bt      r10d, 13h
0x1400022ae  jnb     short loc_1400022FA
0x1400022b0  mov     rax, [rsp+18h+arg_0]
0x1400022b5  and     al, dl
0x1400022b7  cmp     al, dl
0x1400022b9  jnz     short loc_1400022FA
0x1400022bb  mov     ecx, r11d
0x1400022be  mov     eax, r11d
0x1400022c1  shr     rcx, 10h
0x1400022c5  and     eax, 400FFh
0x1400022ca  and     ecx, 6
0x1400022cd  mov     cs:__avx10_version, eax
0x1400022d3  or      rcx, 1000029h
0x1400022da  not     rcx
0x1400022dd  and     rcx, cs:__isa_inverted
0x1400022e4  mov     cs:__isa_inverted, rcx
0x1400022eb  cmp     al, 1
0x1400022ed  jbe     short loc_1400022FA
0x1400022ef  and     rcx, 0FFFFFFFFFFFFFFBFh
0x1400022f3  mov     cs:__isa_inverted, rcx
0x1400022fa  bt      r10d, 15h
0x1400022ff  jnb     short loc_140002316
0x140002301  mov     rax, [rsp+18h+arg_0]
0x140002306  bt      rax, 13h
0x14000230b  jnb     short loc_140002316
0x14000230d  btr     cs:__isa_inverted, 7
0x140002316  mov     rbx, [rsp+18h+arg_8]
0x14000231b  xor     eax, eax
0x14000231d  mov     rbp, [rsp+18h+arg_10]
0x140002322  mov     rsi, [rsp+18h+arg_18]
0x140002327  add     rsp, 10h
0x14000232b  pop     rdi
0x14000232c  retn
```
