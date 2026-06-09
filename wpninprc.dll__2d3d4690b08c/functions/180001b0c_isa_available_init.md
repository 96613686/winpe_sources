# __isa_available_init

- ea: `0x180001b0c`
- end: `0x180001d8f`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015ac`
- `0x1800016e8`

## callees

- `0x180001b0c`

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
0x180001b0c  push    rbx
0x180001b0e  push    rbp
0x180001b0f  push    rsi
0x180001b10  push    rdi
0x180001b11  sub     rsp, 18h
0x180001b15  xor     eax, eax
0x180001b17  xor     ecx, ecx
0x180001b19  cpuid
0x180001b1b  xor     ecx, 6C65746Eh
0x180001b21  xor     edx, 49656E69h
0x180001b27  or      edx, ecx
0x180001b29  mov     ebp, eax
0x180001b2b  mov     eax, 1
0x180001b30  xor     ebx, 756E6547h
0x180001b36  or      edx, ebx
0x180001b38  lea     ecx, [rax-1]
0x180001b3b  cpuid
0x180001b3d  mov     edi, ecx
0x180001b3f  jnz     short loc_180001B9F
0x180001b41  and     eax, 0FFF3FF0h
0x180001b46  mov     cs:__memset_fast_string_threshold, 8000h
0x180001b51  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001b5c  cmp     eax, 106C0h
0x180001b61  jz      short loc_180001B8B
0x180001b63  cmp     eax, 20660h
0x180001b68  jz      short loc_180001B8B
0x180001b6a  cmp     eax, 20670h
0x180001b6f  jz      short loc_180001B8B
0x180001b71  add     eax, 0FFFCF9B0h
0x180001b76  cmp     eax, 20h ; ' '
0x180001b79  ja      short loc_180001B9F
0x180001b7b  mov     rcx, 100010001h
0x180001b85  bt      rcx, rax
0x180001b89  jnb     short loc_180001B9F
0x180001b8b  mov     r8d, cs:__favor
0x180001b92  or      r8d, 1
0x180001b96  mov     cs:__favor, r8d
0x180001b9d  jmp     short loc_180001BA6
0x180001b9f  mov     r8d, cs:__favor
0x180001ba6  xor     r10d, r10d
0x180001ba9  xor     r11d, r11d
0x180001bac  cmp     ebp, 7
0x180001baf  jl      short loc_180001BF3
0x180001bb1  xor     ecx, ecx
0x180001bb3  lea     eax, [r10+7]
0x180001bb7  cpuid
0x180001bb9  mov     esi, edx
0x180001bbb  mov     r9d, ebx
0x180001bbe  bt      ebx, 9
0x180001bc2  jnb     short loc_180001BCF
0x180001bc4  or      r8d, 2
0x180001bc8  mov     cs:__favor, r8d
0x180001bcf  cmp     eax, 1
0x180001bd2  jl      short loc_180001BE1
0x180001bd4  mov     eax, 7
0x180001bd9  lea     ecx, [rax-6]
0x180001bdc  cpuid
0x180001bde  mov     r10d, edx
0x180001be1  mov     eax, 24h ; '$'
0x180001be6  cmp     ebp, eax
0x180001be8  jl      short loc_180001BF8
0x180001bea  xor     ecx, ecx
0x180001bec  cpuid
0x180001bee  mov     r11d, ebx
0x180001bf1  jmp     short loc_180001BF8
0x180001bf3  xor     r9d, r9d
0x180001bf6  xor     esi, esi
0x180001bf8  mov     rax, cs:__isa_inverted
0x180001bff  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c03  mov     cs:__isa_available, 1
0x180001c0d  mov     cs:__isa_enabled, 2
0x180001c17  mov     cs:__isa_inverted, rax
0x180001c1e  bt      edi, 14h
0x180001c22  jnb     short loc_180001C43
0x180001c24  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001c28  mov     cs:__isa_available, 2
0x180001c32  mov     cs:__isa_inverted, rax
0x180001c39  mov     cs:__isa_enabled, 6
0x180001c43  bt      edi, 1Bh
0x180001c47  jnb     loc_180001D84
0x180001c4d  xor     ecx, ecx
0x180001c4f  xgetbv
0x180001c52  shl     rdx, 20h
0x180001c56  or      rdx, rax
0x180001c59  mov     [rsp+38h+arg_0], rdx
0x180001c5e  bt      edi, 1Ch
0x180001c62  jnb     loc_180001D68
0x180001c68  mov     rax, [rsp+38h+arg_0]
0x180001c6d  and     al, 6
0x180001c6f  cmp     al, 6
0x180001c71  jnz     loc_180001D68
0x180001c77  mov     eax, cs:__isa_enabled
0x180001c7d  mov     dl, 0E0h
0x180001c7f  or      eax, 8
0x180001c82  mov     cs:__isa_available, 3
0x180001c8c  mov     cs:__isa_enabled, eax
0x180001c92  test    r9b, 20h
0x180001c96  jz      short loc_180001CFA
0x180001c98  or      eax, 20h
0x180001c9b  mov     cs:__isa_available, 5
0x180001ca5  mov     cs:__isa_enabled, eax
0x180001cab  mov     ecx, 0D0030000h
0x180001cb0  mov     rax, cs:__isa_inverted
0x180001cb7  and     r9d, ecx
0x180001cba  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001cbe  mov     cs:__isa_inverted, rax
0x180001cc5  cmp     r9d, ecx
0x180001cc8  jnz     short loc_180001D01
0x180001cca  mov     rax, [rsp+38h+arg_0]
0x180001ccf  and     al, dl
0x180001cd1  cmp     al, dl
0x180001cd3  jnz     short loc_180001CFA
0x180001cd5  mov     rax, cs:__isa_inverted
0x180001cdc  or      cs:__isa_enabled, 40h
0x180001ce3  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001ce7  mov     cs:__isa_available, 6
0x180001cf1  mov     cs:__isa_inverted, rax
0x180001cf8  jmp     short loc_180001D01
0x180001cfa  mov     rax, cs:__isa_inverted
0x180001d01  bt      esi, 17h
0x180001d05  jnb     short loc_180001D13
0x180001d07  btr     rax, 18h
0x180001d0c  mov     cs:__isa_inverted, rax
0x180001d13  bt      r10d, 13h
0x180001d18  jnb     short loc_180001D68
0x180001d1a  mov     rax, [rsp+38h+arg_0]
0x180001d1f  and     al, dl
0x180001d21  cmp     al, dl
0x180001d23  jnz     short loc_180001D68
0x180001d25  mov     rdx, cs:__isa_inverted
0x180001d2c  mov     eax, r11d
0x180001d2f  shr     rax, 10h
0x180001d33  mov     ecx, r11d
0x180001d36  and     eax, 6
0x180001d39  and     ecx, 400FFh
0x180001d3f  or      rax, 1000029h
0x180001d45  mov     cs:__avx10_version, ecx
0x180001d4b  not     rax
0x180001d4e  and     rdx, rax
0x180001d51  mov     cs:__isa_inverted, rdx
0x180001d58  cmp     cl, 1
0x180001d5b  jbe     short loc_180001D68
0x180001d5d  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001d61  mov     cs:__isa_inverted, rdx
0x180001d68  bt      r10d, 15h
0x180001d6d  jnb     short loc_180001D84
0x180001d6f  mov     rax, [rsp+38h+arg_0]
0x180001d74  bt      rax, 13h
0x180001d79  jnb     short loc_180001D84
0x180001d7b  btr     cs:__isa_inverted, 7
0x180001d84  xor     eax, eax
0x180001d86  add     rsp, 18h
0x180001d8a  pop     rdi
0x180001d8b  pop     rsi
0x180001d8c  pop     rbp
0x180001d8d  pop     rbx
0x180001d8e  retn
```
