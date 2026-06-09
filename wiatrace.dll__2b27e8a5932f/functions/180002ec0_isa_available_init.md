# __isa_available_init

- ea: `0x180002ec0`
- end: `0x180003143`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002aec`
- `0x180002c28`

## callees

- `0x180002ec0`

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
0x180002ec0  push    rbx
0x180002ec2  push    rbp
0x180002ec3  push    rsi
0x180002ec4  push    rdi
0x180002ec5  sub     rsp, 18h
0x180002ec9  xor     eax, eax
0x180002ecb  xor     ecx, ecx
0x180002ecd  cpuid
0x180002ecf  xor     ecx, 6C65746Eh
0x180002ed5  xor     edx, 49656E69h
0x180002edb  or      edx, ecx
0x180002edd  mov     ebp, eax
0x180002edf  mov     eax, 1
0x180002ee4  xor     ebx, 756E6547h
0x180002eea  or      edx, ebx
0x180002eec  lea     ecx, [rax-1]
0x180002eef  cpuid
0x180002ef1  mov     edi, ecx
0x180002ef3  jnz     short loc_180002F53
0x180002ef5  and     eax, 0FFF3FF0h
0x180002efa  mov     cs:__memset_fast_string_threshold, 8000h
0x180002f05  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002f10  cmp     eax, 106C0h
0x180002f15  jz      short loc_180002F3F
0x180002f17  cmp     eax, 20660h
0x180002f1c  jz      short loc_180002F3F
0x180002f1e  cmp     eax, 20670h
0x180002f23  jz      short loc_180002F3F
0x180002f25  add     eax, 0FFFCF9B0h
0x180002f2a  cmp     eax, 20h ; ' '
0x180002f2d  ja      short loc_180002F53
0x180002f2f  mov     rcx, 100010001h
0x180002f39  bt      rcx, rax
0x180002f3d  jnb     short loc_180002F53
0x180002f3f  mov     r8d, cs:__favor
0x180002f46  or      r8d, 1
0x180002f4a  mov     cs:__favor, r8d
0x180002f51  jmp     short loc_180002F5A
0x180002f53  mov     r8d, cs:__favor
0x180002f5a  xor     r10d, r10d
0x180002f5d  xor     r11d, r11d
0x180002f60  cmp     ebp, 7
0x180002f63  jl      short loc_180002FA7
0x180002f65  xor     ecx, ecx
0x180002f67  lea     eax, [r10+7]
0x180002f6b  cpuid
0x180002f6d  mov     esi, edx
0x180002f6f  mov     r9d, ebx
0x180002f72  bt      ebx, 9
0x180002f76  jnb     short loc_180002F83
0x180002f78  or      r8d, 2
0x180002f7c  mov     cs:__favor, r8d
0x180002f83  cmp     eax, 1
0x180002f86  jl      short loc_180002F95
0x180002f88  mov     eax, 7
0x180002f8d  lea     ecx, [rax-6]
0x180002f90  cpuid
0x180002f92  mov     r10d, edx
0x180002f95  mov     eax, 24h ; '$'
0x180002f9a  cmp     ebp, eax
0x180002f9c  jl      short loc_180002FAC
0x180002f9e  xor     ecx, ecx
0x180002fa0  cpuid
0x180002fa2  mov     r11d, ebx
0x180002fa5  jmp     short loc_180002FAC
0x180002fa7  xor     r9d, r9d
0x180002faa  xor     esi, esi
0x180002fac  mov     rax, cs:__isa_inverted
0x180002fb3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002fb7  mov     cs:__isa_available, 1
0x180002fc1  mov     cs:__isa_enabled, 2
0x180002fcb  mov     cs:__isa_inverted, rax
0x180002fd2  bt      edi, 14h
0x180002fd6  jnb     short loc_180002FF7
0x180002fd8  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002fdc  mov     cs:__isa_available, 2
0x180002fe6  mov     cs:__isa_inverted, rax
0x180002fed  mov     cs:__isa_enabled, 6
0x180002ff7  bt      edi, 1Bh
0x180002ffb  jnb     loc_180003138
0x180003001  xor     ecx, ecx
0x180003003  xgetbv
0x180003006  shl     rdx, 20h
0x18000300a  or      rdx, rax
0x18000300d  mov     [rsp+38h+arg_0], rdx
0x180003012  bt      edi, 1Ch
0x180003016  jnb     loc_18000311C
0x18000301c  mov     rax, [rsp+38h+arg_0]
0x180003021  and     al, 6
0x180003023  cmp     al, 6
0x180003025  jnz     loc_18000311C
0x18000302b  mov     eax, cs:__isa_enabled
0x180003031  mov     dl, 0E0h
0x180003033  or      eax, 8
0x180003036  mov     cs:__isa_available, 3
0x180003040  mov     cs:__isa_enabled, eax
0x180003046  test    r9b, 20h
0x18000304a  jz      short loc_1800030AE
0x18000304c  or      eax, 20h
0x18000304f  mov     cs:__isa_available, 5
0x180003059  mov     cs:__isa_enabled, eax
0x18000305f  mov     ecx, 0D0030000h
0x180003064  mov     rax, cs:__isa_inverted
0x18000306b  and     r9d, ecx
0x18000306e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180003072  mov     cs:__isa_inverted, rax
0x180003079  cmp     r9d, ecx
0x18000307c  jnz     short loc_1800030B5
0x18000307e  mov     rax, [rsp+38h+arg_0]
0x180003083  and     al, dl
0x180003085  cmp     al, dl
0x180003087  jnz     short loc_1800030AE
0x180003089  mov     rax, cs:__isa_inverted
0x180003090  or      cs:__isa_enabled, 40h
0x180003097  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000309b  mov     cs:__isa_available, 6
0x1800030a5  mov     cs:__isa_inverted, rax
0x1800030ac  jmp     short loc_1800030B5
0x1800030ae  mov     rax, cs:__isa_inverted
0x1800030b5  bt      esi, 17h
0x1800030b9  jnb     short loc_1800030C7
0x1800030bb  btr     rax, 18h
0x1800030c0  mov     cs:__isa_inverted, rax
0x1800030c7  bt      r10d, 13h
0x1800030cc  jnb     short loc_18000311C
0x1800030ce  mov     rax, [rsp+38h+arg_0]
0x1800030d3  and     al, dl
0x1800030d5  cmp     al, dl
0x1800030d7  jnz     short loc_18000311C
0x1800030d9  mov     rdx, cs:__isa_inverted
0x1800030e0  mov     eax, r11d
0x1800030e3  shr     rax, 10h
0x1800030e7  mov     ecx, r11d
0x1800030ea  and     eax, 6
0x1800030ed  and     ecx, 400FFh
0x1800030f3  or      rax, 1000029h
0x1800030f9  mov     cs:__avx10_version, ecx
0x1800030ff  not     rax
0x180003102  and     rdx, rax
0x180003105  mov     cs:__isa_inverted, rdx
0x18000310c  cmp     cl, 1
0x18000310f  jbe     short loc_18000311C
0x180003111  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180003115  mov     cs:__isa_inverted, rdx
0x18000311c  bt      r10d, 15h
0x180003121  jnb     short loc_180003138
0x180003123  mov     rax, [rsp+38h+arg_0]
0x180003128  bt      rax, 13h
0x18000312d  jnb     short loc_180003138
0x18000312f  btr     cs:__isa_inverted, 7
0x180003138  xor     eax, eax
0x18000313a  add     rsp, 18h
0x18000313e  pop     rdi
0x18000313f  pop     rsi
0x180003140  pop     rbp
0x180003141  pop     rbx
0x180003142  retn
```
