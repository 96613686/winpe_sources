# __isa_available_init

- ea: `0x1400018c8`
- end: `0x140001b4b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400013d0`

## callees

- `0x1400018c8`

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
0x1400018c8  push    rbx
0x1400018ca  push    rbp
0x1400018cb  push    rsi
0x1400018cc  push    rdi
0x1400018cd  sub     rsp, 18h
0x1400018d1  xor     eax, eax
0x1400018d3  xor     ecx, ecx
0x1400018d5  cpuid
0x1400018d7  xor     ecx, 6C65746Eh
0x1400018dd  xor     edx, 49656E69h
0x1400018e3  or      edx, ecx
0x1400018e5  mov     ebp, eax
0x1400018e7  mov     eax, 1
0x1400018ec  xor     ebx, 756E6547h
0x1400018f2  or      edx, ebx
0x1400018f4  lea     ecx, [rax-1]
0x1400018f7  cpuid
0x1400018f9  mov     edi, ecx
0x1400018fb  jnz     short loc_14000195B
0x1400018fd  and     eax, 0FFF3FF0h
0x140001902  mov     cs:__memset_fast_string_threshold, 8000h
0x14000190d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140001918  cmp     eax, 106C0h
0x14000191d  jz      short loc_140001947
0x14000191f  cmp     eax, 20660h
0x140001924  jz      short loc_140001947
0x140001926  cmp     eax, 20670h
0x14000192b  jz      short loc_140001947
0x14000192d  add     eax, 0FFFCF9B0h
0x140001932  cmp     eax, 20h ; ' '
0x140001935  ja      short loc_14000195B
0x140001937  mov     rcx, 100010001h
0x140001941  bt      rcx, rax
0x140001945  jnb     short loc_14000195B
0x140001947  mov     r8d, cs:__favor
0x14000194e  or      r8d, 1
0x140001952  mov     cs:__favor, r8d
0x140001959  jmp     short loc_140001962
0x14000195b  mov     r8d, cs:__favor
0x140001962  xor     r10d, r10d
0x140001965  xor     r11d, r11d
0x140001968  cmp     ebp, 7
0x14000196b  jl      short loc_1400019AF
0x14000196d  xor     ecx, ecx
0x14000196f  lea     eax, [r10+7]
0x140001973  cpuid
0x140001975  mov     esi, edx
0x140001977  mov     r9d, ebx
0x14000197a  bt      ebx, 9
0x14000197e  jnb     short loc_14000198B
0x140001980  or      r8d, 2
0x140001984  mov     cs:__favor, r8d
0x14000198b  cmp     eax, 1
0x14000198e  jl      short loc_14000199D
0x140001990  mov     eax, 7
0x140001995  lea     ecx, [rax-6]
0x140001998  cpuid
0x14000199a  mov     r10d, edx
0x14000199d  mov     eax, 24h ; '$'
0x1400019a2  cmp     ebp, eax
0x1400019a4  jl      short loc_1400019B4
0x1400019a6  xor     ecx, ecx
0x1400019a8  cpuid
0x1400019aa  mov     r11d, ebx
0x1400019ad  jmp     short loc_1400019B4
0x1400019af  xor     r9d, r9d
0x1400019b2  xor     esi, esi
0x1400019b4  mov     rax, cs:__isa_inverted
0x1400019bb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400019bf  mov     cs:__isa_available, 1
0x1400019c9  mov     cs:__isa_enabled, 2
0x1400019d3  mov     cs:__isa_inverted, rax
0x1400019da  bt      edi, 14h
0x1400019de  jnb     short loc_1400019FF
0x1400019e0  and     rax, 0FFFFFFFFFFFFFFEFh
0x1400019e4  mov     cs:__isa_available, 2
0x1400019ee  mov     cs:__isa_inverted, rax
0x1400019f5  mov     cs:__isa_enabled, 6
0x1400019ff  bt      edi, 1Bh
0x140001a03  jnb     loc_140001B40
0x140001a09  xor     ecx, ecx
0x140001a0b  xgetbv
0x140001a0e  shl     rdx, 20h
0x140001a12  or      rdx, rax
0x140001a15  mov     [rsp+38h+arg_0], rdx
0x140001a1a  bt      edi, 1Ch
0x140001a1e  jnb     loc_140001B24
0x140001a24  mov     rax, [rsp+38h+arg_0]
0x140001a29  and     al, 6
0x140001a2b  cmp     al, 6
0x140001a2d  jnz     loc_140001B24
0x140001a33  mov     eax, cs:__isa_enabled
0x140001a39  mov     dl, 0E0h
0x140001a3b  or      eax, 8
0x140001a3e  mov     cs:__isa_available, 3
0x140001a48  mov     cs:__isa_enabled, eax
0x140001a4e  test    r9b, 20h
0x140001a52  jz      short loc_140001AB6
0x140001a54  or      eax, 20h
0x140001a57  mov     cs:__isa_available, 5
0x140001a61  mov     cs:__isa_enabled, eax
0x140001a67  mov     ecx, 0D0030000h
0x140001a6c  mov     rax, cs:__isa_inverted
0x140001a73  and     r9d, ecx
0x140001a76  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001a7a  mov     cs:__isa_inverted, rax
0x140001a81  cmp     r9d, ecx
0x140001a84  jnz     short loc_140001ABD
0x140001a86  mov     rax, [rsp+38h+arg_0]
0x140001a8b  and     al, dl
0x140001a8d  cmp     al, dl
0x140001a8f  jnz     short loc_140001AB6
0x140001a91  mov     rax, cs:__isa_inverted
0x140001a98  or      cs:__isa_enabled, 40h
0x140001a9f  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001aa3  mov     cs:__isa_available, 6
0x140001aad  mov     cs:__isa_inverted, rax
0x140001ab4  jmp     short loc_140001ABD
0x140001ab6  mov     rax, cs:__isa_inverted
0x140001abd  bt      esi, 17h
0x140001ac1  jnb     short loc_140001ACF
0x140001ac3  btr     rax, 18h
0x140001ac8  mov     cs:__isa_inverted, rax
0x140001acf  bt      r10d, 13h
0x140001ad4  jnb     short loc_140001B24
0x140001ad6  mov     rax, [rsp+38h+arg_0]
0x140001adb  and     al, dl
0x140001add  cmp     al, dl
0x140001adf  jnz     short loc_140001B24
0x140001ae1  mov     rdx, cs:__isa_inverted
0x140001ae8  mov     eax, r11d
0x140001aeb  shr     rax, 10h
0x140001aef  mov     ecx, r11d
0x140001af2  and     eax, 6
0x140001af5  and     ecx, 400FFh
0x140001afb  or      rax, 1000029h
0x140001b01  mov     cs:__avx10_version, ecx
0x140001b07  not     rax
0x140001b0a  and     rdx, rax
0x140001b0d  mov     cs:__isa_inverted, rdx
0x140001b14  cmp     cl, 1
0x140001b17  jbe     short loc_140001B24
0x140001b19  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001b1d  mov     cs:__isa_inverted, rdx
0x140001b24  bt      r10d, 15h
0x140001b29  jnb     short loc_140001B40
0x140001b2b  mov     rax, [rsp+38h+arg_0]
0x140001b30  bt      rax, 13h
0x140001b35  jnb     short loc_140001B40
0x140001b37  btr     cs:__isa_inverted, 7
0x140001b40  xor     eax, eax
0x140001b42  add     rsp, 18h
0x140001b46  pop     rdi
0x140001b47  pop     rsi
0x140001b48  pop     rbp
0x140001b49  pop     rbx
0x140001b4a  retn
```
