# __isa_available_init

- ea: `0x180001b28`
- end: `0x180001dab`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015a0`
- `0x1800016dc`

## callees

- `0x180001b28`

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
0x180001b28  push    rbx
0x180001b2a  push    rbp
0x180001b2b  push    rsi
0x180001b2c  push    rdi
0x180001b2d  sub     rsp, 18h
0x180001b31  xor     eax, eax
0x180001b33  xor     ecx, ecx
0x180001b35  cpuid
0x180001b37  xor     ecx, 6C65746Eh
0x180001b3d  xor     edx, 49656E69h
0x180001b43  or      edx, ecx
0x180001b45  mov     ebp, eax
0x180001b47  mov     eax, 1
0x180001b4c  xor     ebx, 756E6547h
0x180001b52  or      edx, ebx
0x180001b54  lea     ecx, [rax-1]
0x180001b57  cpuid
0x180001b59  mov     edi, ecx
0x180001b5b  jnz     short loc_180001BBB
0x180001b5d  and     eax, 0FFF3FF0h
0x180001b62  mov     cs:__memset_fast_string_threshold, 8000h
0x180001b6d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001b78  cmp     eax, 106C0h
0x180001b7d  jz      short loc_180001BA7
0x180001b7f  cmp     eax, 20660h
0x180001b84  jz      short loc_180001BA7
0x180001b86  cmp     eax, 20670h
0x180001b8b  jz      short loc_180001BA7
0x180001b8d  add     eax, 0FFFCF9B0h
0x180001b92  cmp     eax, 20h ; ' '
0x180001b95  ja      short loc_180001BBB
0x180001b97  mov     rcx, 100010001h
0x180001ba1  bt      rcx, rax
0x180001ba5  jnb     short loc_180001BBB
0x180001ba7  mov     r8d, cs:__favor
0x180001bae  or      r8d, 1
0x180001bb2  mov     cs:__favor, r8d
0x180001bb9  jmp     short loc_180001BC2
0x180001bbb  mov     r8d, cs:__favor
0x180001bc2  xor     r10d, r10d
0x180001bc5  xor     r11d, r11d
0x180001bc8  cmp     ebp, 7
0x180001bcb  jl      short loc_180001C0F
0x180001bcd  xor     ecx, ecx
0x180001bcf  lea     eax, [r10+7]
0x180001bd3  cpuid
0x180001bd5  mov     esi, edx
0x180001bd7  mov     r9d, ebx
0x180001bda  bt      ebx, 9
0x180001bde  jnb     short loc_180001BEB
0x180001be0  or      r8d, 2
0x180001be4  mov     cs:__favor, r8d
0x180001beb  cmp     eax, 1
0x180001bee  jl      short loc_180001BFD
0x180001bf0  mov     eax, 7
0x180001bf5  lea     ecx, [rax-6]
0x180001bf8  cpuid
0x180001bfa  mov     r10d, edx
0x180001bfd  mov     eax, 24h ; '$'
0x180001c02  cmp     ebp, eax
0x180001c04  jl      short loc_180001C14
0x180001c06  xor     ecx, ecx
0x180001c08  cpuid
0x180001c0a  mov     r11d, ebx
0x180001c0d  jmp     short loc_180001C14
0x180001c0f  xor     r9d, r9d
0x180001c12  xor     esi, esi
0x180001c14  mov     rax, cs:__isa_inverted
0x180001c1b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c1f  mov     cs:__isa_available, 1
0x180001c29  mov     cs:__isa_enabled, 2
0x180001c33  mov     cs:__isa_inverted, rax
0x180001c3a  bt      edi, 14h
0x180001c3e  jnb     short loc_180001C5F
0x180001c40  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001c44  mov     cs:__isa_available, 2
0x180001c4e  mov     cs:__isa_inverted, rax
0x180001c55  mov     cs:__isa_enabled, 6
0x180001c5f  bt      edi, 1Bh
0x180001c63  jnb     loc_180001DA0
0x180001c69  xor     ecx, ecx
0x180001c6b  xgetbv
0x180001c6e  shl     rdx, 20h
0x180001c72  or      rdx, rax
0x180001c75  mov     [rsp+38h+arg_0], rdx
0x180001c7a  bt      edi, 1Ch
0x180001c7e  jnb     loc_180001D84
0x180001c84  mov     rax, [rsp+38h+arg_0]
0x180001c89  and     al, 6
0x180001c8b  cmp     al, 6
0x180001c8d  jnz     loc_180001D84
0x180001c93  mov     eax, cs:__isa_enabled
0x180001c99  mov     dl, 0E0h
0x180001c9b  or      eax, 8
0x180001c9e  mov     cs:__isa_available, 3
0x180001ca8  mov     cs:__isa_enabled, eax
0x180001cae  test    r9b, 20h
0x180001cb2  jz      short loc_180001D16
0x180001cb4  or      eax, 20h
0x180001cb7  mov     cs:__isa_available, 5
0x180001cc1  mov     cs:__isa_enabled, eax
0x180001cc7  mov     ecx, 0D0030000h
0x180001ccc  mov     rax, cs:__isa_inverted
0x180001cd3  and     r9d, ecx
0x180001cd6  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001cda  mov     cs:__isa_inverted, rax
0x180001ce1  cmp     r9d, ecx
0x180001ce4  jnz     short loc_180001D1D
0x180001ce6  mov     rax, [rsp+38h+arg_0]
0x180001ceb  and     al, dl
0x180001ced  cmp     al, dl
0x180001cef  jnz     short loc_180001D16
0x180001cf1  mov     rax, cs:__isa_inverted
0x180001cf8  or      cs:__isa_enabled, 40h
0x180001cff  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d03  mov     cs:__isa_available, 6
0x180001d0d  mov     cs:__isa_inverted, rax
0x180001d14  jmp     short loc_180001D1D
0x180001d16  mov     rax, cs:__isa_inverted
0x180001d1d  bt      esi, 17h
0x180001d21  jnb     short loc_180001D2F
0x180001d23  btr     rax, 18h
0x180001d28  mov     cs:__isa_inverted, rax
0x180001d2f  bt      r10d, 13h
0x180001d34  jnb     short loc_180001D84
0x180001d36  mov     rax, [rsp+38h+arg_0]
0x180001d3b  and     al, dl
0x180001d3d  cmp     al, dl
0x180001d3f  jnz     short loc_180001D84
0x180001d41  mov     rdx, cs:__isa_inverted
0x180001d48  mov     eax, r11d
0x180001d4b  shr     rax, 10h
0x180001d4f  mov     ecx, r11d
0x180001d52  and     eax, 6
0x180001d55  and     ecx, 400FFh
0x180001d5b  or      rax, 1000029h
0x180001d61  mov     cs:__avx10_version, ecx
0x180001d67  not     rax
0x180001d6a  and     rdx, rax
0x180001d6d  mov     cs:__isa_inverted, rdx
0x180001d74  cmp     cl, 1
0x180001d77  jbe     short loc_180001D84
0x180001d79  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001d7d  mov     cs:__isa_inverted, rdx
0x180001d84  bt      r10d, 15h
0x180001d89  jnb     short loc_180001DA0
0x180001d8b  mov     rax, [rsp+38h+arg_0]
0x180001d90  bt      rax, 13h
0x180001d95  jnb     short loc_180001DA0
0x180001d97  btr     cs:__isa_inverted, 7
0x180001da0  xor     eax, eax
0x180001da2  add     rsp, 18h
0x180001da6  pop     rdi
0x180001da7  pop     rsi
0x180001da8  pop     rbp
0x180001da9  pop     rbx
0x180001daa  retn
```
