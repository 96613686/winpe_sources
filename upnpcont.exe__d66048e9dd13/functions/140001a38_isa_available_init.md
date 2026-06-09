# __isa_available_init

- ea: `0x140001a38`
- end: `0x140001cbb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001520`

## callees

- `0x140001a38`

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
0x140001a38  push    rbx
0x140001a3a  push    rbp
0x140001a3b  push    rsi
0x140001a3c  push    rdi
0x140001a3d  sub     rsp, 18h
0x140001a41  xor     eax, eax
0x140001a43  xor     ecx, ecx
0x140001a45  cpuid
0x140001a47  xor     ecx, 6C65746Eh
0x140001a4d  xor     edx, 49656E69h
0x140001a53  or      edx, ecx
0x140001a55  mov     ebp, eax
0x140001a57  mov     eax, 1
0x140001a5c  xor     ebx, 756E6547h
0x140001a62  or      edx, ebx
0x140001a64  lea     ecx, [rax-1]
0x140001a67  cpuid
0x140001a69  mov     edi, ecx
0x140001a6b  jnz     short loc_140001ACB
0x140001a6d  and     eax, 0FFF3FF0h
0x140001a72  mov     cs:__memset_fast_string_threshold, 8000h
0x140001a7d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140001a88  cmp     eax, 106C0h
0x140001a8d  jz      short loc_140001AB7
0x140001a8f  cmp     eax, 20660h
0x140001a94  jz      short loc_140001AB7
0x140001a96  cmp     eax, 20670h
0x140001a9b  jz      short loc_140001AB7
0x140001a9d  add     eax, 0FFFCF9B0h
0x140001aa2  cmp     eax, 20h ; ' '
0x140001aa5  ja      short loc_140001ACB
0x140001aa7  mov     rcx, 100010001h
0x140001ab1  bt      rcx, rax
0x140001ab5  jnb     short loc_140001ACB
0x140001ab7  mov     r8d, cs:__favor
0x140001abe  or      r8d, 1
0x140001ac2  mov     cs:__favor, r8d
0x140001ac9  jmp     short loc_140001AD2
0x140001acb  mov     r8d, cs:__favor
0x140001ad2  xor     r10d, r10d
0x140001ad5  xor     r11d, r11d
0x140001ad8  cmp     ebp, 7
0x140001adb  jl      short loc_140001B1F
0x140001add  xor     ecx, ecx
0x140001adf  lea     eax, [r10+7]
0x140001ae3  cpuid
0x140001ae5  mov     esi, edx
0x140001ae7  mov     r9d, ebx
0x140001aea  bt      ebx, 9
0x140001aee  jnb     short loc_140001AFB
0x140001af0  or      r8d, 2
0x140001af4  mov     cs:__favor, r8d
0x140001afb  cmp     eax, 1
0x140001afe  jl      short loc_140001B0D
0x140001b00  mov     eax, 7
0x140001b05  lea     ecx, [rax-6]
0x140001b08  cpuid
0x140001b0a  mov     r10d, edx
0x140001b0d  mov     eax, 24h ; '$'
0x140001b12  cmp     ebp, eax
0x140001b14  jl      short loc_140001B24
0x140001b16  xor     ecx, ecx
0x140001b18  cpuid
0x140001b1a  mov     r11d, ebx
0x140001b1d  jmp     short loc_140001B24
0x140001b1f  xor     r9d, r9d
0x140001b22  xor     esi, esi
0x140001b24  mov     rax, cs:__isa_inverted
0x140001b2b  and     rax, 0FFFFFFFFFFFFFFFEh
0x140001b2f  mov     cs:__isa_available, 1
0x140001b39  mov     cs:__isa_enabled, 2
0x140001b43  mov     cs:__isa_inverted, rax
0x140001b4a  bt      edi, 14h
0x140001b4e  jnb     short loc_140001B6F
0x140001b50  and     rax, 0FFFFFFFFFFFFFFEFh
0x140001b54  mov     cs:__isa_available, 2
0x140001b5e  mov     cs:__isa_inverted, rax
0x140001b65  mov     cs:__isa_enabled, 6
0x140001b6f  bt      edi, 1Bh
0x140001b73  jnb     loc_140001CB0
0x140001b79  xor     ecx, ecx
0x140001b7b  xgetbv
0x140001b7e  shl     rdx, 20h
0x140001b82  or      rdx, rax
0x140001b85  mov     [rsp+38h+arg_0], rdx
0x140001b8a  bt      edi, 1Ch
0x140001b8e  jnb     loc_140001C94
0x140001b94  mov     rax, [rsp+38h+arg_0]
0x140001b99  and     al, 6
0x140001b9b  cmp     al, 6
0x140001b9d  jnz     loc_140001C94
0x140001ba3  mov     eax, cs:__isa_enabled
0x140001ba9  mov     dl, 0E0h
0x140001bab  or      eax, 8
0x140001bae  mov     cs:__isa_available, 3
0x140001bb8  mov     cs:__isa_enabled, eax
0x140001bbe  test    r9b, 20h
0x140001bc2  jz      short loc_140001C26
0x140001bc4  or      eax, 20h
0x140001bc7  mov     cs:__isa_available, 5
0x140001bd1  mov     cs:__isa_enabled, eax
0x140001bd7  mov     ecx, 0D0030000h
0x140001bdc  mov     rax, cs:__isa_inverted
0x140001be3  and     r9d, ecx
0x140001be6  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001bea  mov     cs:__isa_inverted, rax
0x140001bf1  cmp     r9d, ecx
0x140001bf4  jnz     short loc_140001C2D
0x140001bf6  mov     rax, [rsp+38h+arg_0]
0x140001bfb  and     al, dl
0x140001bfd  cmp     al, dl
0x140001bff  jnz     short loc_140001C26
0x140001c01  mov     rax, cs:__isa_inverted
0x140001c08  or      cs:__isa_enabled, 40h
0x140001c0f  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001c13  mov     cs:__isa_available, 6
0x140001c1d  mov     cs:__isa_inverted, rax
0x140001c24  jmp     short loc_140001C2D
0x140001c26  mov     rax, cs:__isa_inverted
0x140001c2d  bt      esi, 17h
0x140001c31  jnb     short loc_140001C3F
0x140001c33  btr     rax, 18h
0x140001c38  mov     cs:__isa_inverted, rax
0x140001c3f  bt      r10d, 13h
0x140001c44  jnb     short loc_140001C94
0x140001c46  mov     rax, [rsp+38h+arg_0]
0x140001c4b  and     al, dl
0x140001c4d  cmp     al, dl
0x140001c4f  jnz     short loc_140001C94
0x140001c51  mov     rdx, cs:__isa_inverted
0x140001c58  mov     eax, r11d
0x140001c5b  shr     rax, 10h
0x140001c5f  mov     ecx, r11d
0x140001c62  and     eax, 6
0x140001c65  and     ecx, 400FFh
0x140001c6b  or      rax, 1000029h
0x140001c71  mov     cs:__avx10_version, ecx
0x140001c77  not     rax
0x140001c7a  and     rdx, rax
0x140001c7d  mov     cs:__isa_inverted, rdx
0x140001c84  cmp     cl, 1
0x140001c87  jbe     short loc_140001C94
0x140001c89  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001c8d  mov     cs:__isa_inverted, rdx
0x140001c94  bt      r10d, 15h
0x140001c99  jnb     short loc_140001CB0
0x140001c9b  mov     rax, [rsp+38h+arg_0]
0x140001ca0  bt      rax, 13h
0x140001ca5  jnb     short loc_140001CB0
0x140001ca7  btr     cs:__isa_inverted, 7
0x140001cb0  xor     eax, eax
0x140001cb2  add     rsp, 18h
0x140001cb6  pop     rdi
0x140001cb7  pop     rsi
0x140001cb8  pop     rbp
0x140001cb9  pop     rbx
0x140001cba  retn
```
