# __isa_available_init

- ea: `0x180001948`
- end: `0x180001bcb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001598`
- `0x1800016d4`

## callees

- `0x180001948`

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
0x180001948  push    rbx
0x18000194a  push    rbp
0x18000194b  push    rsi
0x18000194c  push    rdi
0x18000194d  sub     rsp, 18h
0x180001951  xor     eax, eax
0x180001953  xor     ecx, ecx
0x180001955  cpuid
0x180001957  xor     ecx, 6C65746Eh
0x18000195d  xor     edx, 49656E69h
0x180001963  or      edx, ecx
0x180001965  mov     ebp, eax
0x180001967  mov     eax, 1
0x18000196c  xor     ebx, 756E6547h
0x180001972  or      edx, ebx
0x180001974  lea     ecx, [rax-1]
0x180001977  cpuid
0x180001979  mov     edi, ecx
0x18000197b  jnz     short loc_1800019DB
0x18000197d  and     eax, 0FFF3FF0h
0x180001982  mov     cs:__memset_fast_string_threshold, 8000h
0x18000198d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001998  cmp     eax, 106C0h
0x18000199d  jz      short loc_1800019C7
0x18000199f  cmp     eax, 20660h
0x1800019a4  jz      short loc_1800019C7
0x1800019a6  cmp     eax, 20670h
0x1800019ab  jz      short loc_1800019C7
0x1800019ad  add     eax, 0FFFCF9B0h
0x1800019b2  cmp     eax, 20h ; ' '
0x1800019b5  ja      short loc_1800019DB
0x1800019b7  mov     rcx, 100010001h
0x1800019c1  bt      rcx, rax
0x1800019c5  jnb     short loc_1800019DB
0x1800019c7  mov     r8d, cs:__favor
0x1800019ce  or      r8d, 1
0x1800019d2  mov     cs:__favor, r8d
0x1800019d9  jmp     short loc_1800019E2
0x1800019db  mov     r8d, cs:__favor
0x1800019e2  xor     r10d, r10d
0x1800019e5  xor     r11d, r11d
0x1800019e8  cmp     ebp, 7
0x1800019eb  jl      short loc_180001A2F
0x1800019ed  xor     ecx, ecx
0x1800019ef  lea     eax, [r10+7]
0x1800019f3  cpuid
0x1800019f5  mov     esi, edx
0x1800019f7  mov     r9d, ebx
0x1800019fa  bt      ebx, 9
0x1800019fe  jnb     short loc_180001A0B
0x180001a00  or      r8d, 2
0x180001a04  mov     cs:__favor, r8d
0x180001a0b  cmp     eax, 1
0x180001a0e  jl      short loc_180001A1D
0x180001a10  mov     eax, 7
0x180001a15  lea     ecx, [rax-6]
0x180001a18  cpuid
0x180001a1a  mov     r10d, edx
0x180001a1d  mov     eax, 24h ; '$'
0x180001a22  cmp     ebp, eax
0x180001a24  jl      short loc_180001A34
0x180001a26  xor     ecx, ecx
0x180001a28  cpuid
0x180001a2a  mov     r11d, ebx
0x180001a2d  jmp     short loc_180001A34
0x180001a2f  xor     r9d, r9d
0x180001a32  xor     esi, esi
0x180001a34  mov     rax, cs:__isa_inverted
0x180001a3b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a3f  mov     cs:__isa_available, 1
0x180001a49  mov     cs:__isa_enabled, 2
0x180001a53  mov     cs:__isa_inverted, rax
0x180001a5a  bt      edi, 14h
0x180001a5e  jnb     short loc_180001A7F
0x180001a60  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a64  mov     cs:__isa_available, 2
0x180001a6e  mov     cs:__isa_inverted, rax
0x180001a75  mov     cs:__isa_enabled, 6
0x180001a7f  bt      edi, 1Bh
0x180001a83  jnb     loc_180001BC0
0x180001a89  xor     ecx, ecx
0x180001a8b  xgetbv
0x180001a8e  shl     rdx, 20h
0x180001a92  or      rdx, rax
0x180001a95  mov     [rsp+38h+arg_0], rdx
0x180001a9a  bt      edi, 1Ch
0x180001a9e  jnb     loc_180001BA4
0x180001aa4  mov     rax, [rsp+38h+arg_0]
0x180001aa9  and     al, 6
0x180001aab  cmp     al, 6
0x180001aad  jnz     loc_180001BA4
0x180001ab3  mov     eax, cs:__isa_enabled
0x180001ab9  mov     dl, 0E0h
0x180001abb  or      eax, 8
0x180001abe  mov     cs:__isa_available, 3
0x180001ac8  mov     cs:__isa_enabled, eax
0x180001ace  test    r9b, 20h
0x180001ad2  jz      short loc_180001B36
0x180001ad4  or      eax, 20h
0x180001ad7  mov     cs:__isa_available, 5
0x180001ae1  mov     cs:__isa_enabled, eax
0x180001ae7  mov     ecx, 0D0030000h
0x180001aec  mov     rax, cs:__isa_inverted
0x180001af3  and     r9d, ecx
0x180001af6  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001afa  mov     cs:__isa_inverted, rax
0x180001b01  cmp     r9d, ecx
0x180001b04  jnz     short loc_180001B3D
0x180001b06  mov     rax, [rsp+38h+arg_0]
0x180001b0b  and     al, dl
0x180001b0d  cmp     al, dl
0x180001b0f  jnz     short loc_180001B36
0x180001b11  mov     rax, cs:__isa_inverted
0x180001b18  or      cs:__isa_enabled, 40h
0x180001b1f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b23  mov     cs:__isa_available, 6
0x180001b2d  mov     cs:__isa_inverted, rax
0x180001b34  jmp     short loc_180001B3D
0x180001b36  mov     rax, cs:__isa_inverted
0x180001b3d  bt      esi, 17h
0x180001b41  jnb     short loc_180001B4F
0x180001b43  btr     rax, 18h
0x180001b48  mov     cs:__isa_inverted, rax
0x180001b4f  bt      r10d, 13h
0x180001b54  jnb     short loc_180001BA4
0x180001b56  mov     rax, [rsp+38h+arg_0]
0x180001b5b  and     al, dl
0x180001b5d  cmp     al, dl
0x180001b5f  jnz     short loc_180001BA4
0x180001b61  mov     rdx, cs:__isa_inverted
0x180001b68  mov     eax, r11d
0x180001b6b  shr     rax, 10h
0x180001b6f  mov     ecx, r11d
0x180001b72  and     eax, 6
0x180001b75  and     ecx, 400FFh
0x180001b7b  or      rax, 1000029h
0x180001b81  mov     cs:__avx10_version, ecx
0x180001b87  not     rax
0x180001b8a  and     rdx, rax
0x180001b8d  mov     cs:__isa_inverted, rdx
0x180001b94  cmp     cl, 1
0x180001b97  jbe     short loc_180001BA4
0x180001b99  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001b9d  mov     cs:__isa_inverted, rdx
0x180001ba4  bt      r10d, 15h
0x180001ba9  jnb     short loc_180001BC0
0x180001bab  mov     rax, [rsp+38h+arg_0]
0x180001bb0  bt      rax, 13h
0x180001bb5  jnb     short loc_180001BC0
0x180001bb7  btr     cs:__isa_inverted, 7
0x180001bc0  xor     eax, eax
0x180001bc2  add     rsp, 18h
0x180001bc6  pop     rdi
0x180001bc7  pop     rsi
0x180001bc8  pop     rbp
0x180001bc9  pop     rbx
0x180001bca  retn
```
