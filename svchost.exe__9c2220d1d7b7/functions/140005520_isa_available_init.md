# __isa_available_init

- ea: `0x140005520`
- end: `0x1400057a3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ff4`

## callees

- `0x140005520`

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
0x140005520  push    rbx
0x140005522  push    rbp
0x140005523  push    rsi
0x140005524  push    rdi
0x140005525  sub     rsp, 18h
0x140005529  xor     eax, eax
0x14000552b  xor     ecx, ecx
0x14000552d  cpuid
0x14000552f  xor     ecx, 6C65746Eh
0x140005535  xor     edx, 49656E69h
0x14000553b  or      edx, ecx
0x14000553d  mov     ebp, eax
0x14000553f  mov     eax, 1
0x140005544  xor     ebx, 756E6547h
0x14000554a  or      edx, ebx
0x14000554c  lea     ecx, [rax-1]
0x14000554f  cpuid
0x140005551  mov     edi, ecx
0x140005553  jnz     short loc_1400055B3
0x140005555  and     eax, 0FFF3FF0h
0x14000555a  mov     cs:__memset_fast_string_threshold, 8000h
0x140005565  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140005570  cmp     eax, 106C0h
0x140005575  jz      short loc_14000559F
0x140005577  cmp     eax, 20660h
0x14000557c  jz      short loc_14000559F
0x14000557e  cmp     eax, 20670h
0x140005583  jz      short loc_14000559F
0x140005585  add     eax, 0FFFCF9B0h
0x14000558a  cmp     eax, 20h ; ' '
0x14000558d  ja      short loc_1400055B3
0x14000558f  mov     rcx, 100010001h
0x140005599  bt      rcx, rax
0x14000559d  jnb     short loc_1400055B3
0x14000559f  mov     r8d, cs:__favor
0x1400055a6  or      r8d, 1
0x1400055aa  mov     cs:__favor, r8d
0x1400055b1  jmp     short loc_1400055BA
0x1400055b3  mov     r8d, cs:__favor
0x1400055ba  xor     r10d, r10d
0x1400055bd  xor     r11d, r11d
0x1400055c0  cmp     ebp, 7
0x1400055c3  jl      short loc_140005607
0x1400055c5  xor     ecx, ecx
0x1400055c7  lea     eax, [r10+7]
0x1400055cb  cpuid
0x1400055cd  mov     esi, edx
0x1400055cf  mov     r9d, ebx
0x1400055d2  bt      ebx, 9
0x1400055d6  jnb     short loc_1400055E3
0x1400055d8  or      r8d, 2
0x1400055dc  mov     cs:__favor, r8d
0x1400055e3  cmp     eax, 1
0x1400055e6  jl      short loc_1400055F5
0x1400055e8  mov     eax, 7
0x1400055ed  lea     ecx, [rax-6]
0x1400055f0  cpuid
0x1400055f2  mov     r10d, edx
0x1400055f5  mov     eax, 24h ; '$'
0x1400055fa  cmp     ebp, eax
0x1400055fc  jl      short loc_14000560C
0x1400055fe  xor     ecx, ecx
0x140005600  cpuid
0x140005602  mov     r11d, ebx
0x140005605  jmp     short loc_14000560C
0x140005607  xor     r9d, r9d
0x14000560a  xor     esi, esi
0x14000560c  mov     rax, cs:__isa_inverted
0x140005613  and     rax, 0FFFFFFFFFFFFFFFEh
0x140005617  mov     cs:__isa_available, 1
0x140005621  mov     cs:__isa_enabled, 2
0x14000562b  mov     cs:__isa_inverted, rax
0x140005632  bt      edi, 14h
0x140005636  jnb     short loc_140005657
0x140005638  and     rax, 0FFFFFFFFFFFFFFEFh
0x14000563c  mov     cs:__isa_available, 2
0x140005646  mov     cs:__isa_inverted, rax
0x14000564d  mov     cs:__isa_enabled, 6
0x140005657  bt      edi, 1Bh
0x14000565b  jnb     loc_140005798
0x140005661  xor     ecx, ecx
0x140005663  xgetbv
0x140005666  shl     rdx, 20h
0x14000566a  or      rdx, rax
0x14000566d  mov     [rsp+38h+arg_0], rdx
0x140005672  bt      edi, 1Ch
0x140005676  jnb     loc_14000577C
0x14000567c  mov     rax, [rsp+38h+arg_0]
0x140005681  and     al, 6
0x140005683  cmp     al, 6
0x140005685  jnz     loc_14000577C
0x14000568b  mov     eax, cs:__isa_enabled
0x140005691  mov     dl, 0E0h
0x140005693  or      eax, 8
0x140005696  mov     cs:__isa_available, 3
0x1400056a0  mov     cs:__isa_enabled, eax
0x1400056a6  test    r9b, 20h
0x1400056aa  jz      short loc_14000570E
0x1400056ac  or      eax, 20h
0x1400056af  mov     cs:__isa_available, 5
0x1400056b9  mov     cs:__isa_enabled, eax
0x1400056bf  mov     ecx, 0D0030000h
0x1400056c4  mov     rax, cs:__isa_inverted
0x1400056cb  and     r9d, ecx
0x1400056ce  and     rax, 0FFFFFFFFFFFFFFFDh
0x1400056d2  mov     cs:__isa_inverted, rax
0x1400056d9  cmp     r9d, ecx
0x1400056dc  jnz     short loc_140005715
0x1400056de  mov     rax, [rsp+38h+arg_0]
0x1400056e3  and     al, dl
0x1400056e5  cmp     al, dl
0x1400056e7  jnz     short loc_14000570E
0x1400056e9  mov     rax, cs:__isa_inverted
0x1400056f0  or      cs:__isa_enabled, 40h
0x1400056f7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1400056fb  mov     cs:__isa_available, 6
0x140005705  mov     cs:__isa_inverted, rax
0x14000570c  jmp     short loc_140005715
0x14000570e  mov     rax, cs:__isa_inverted
0x140005715  bt      esi, 17h
0x140005719  jnb     short loc_140005727
0x14000571b  btr     rax, 18h
0x140005720  mov     cs:__isa_inverted, rax
0x140005727  bt      r10d, 13h
0x14000572c  jnb     short loc_14000577C
0x14000572e  mov     rax, [rsp+38h+arg_0]
0x140005733  and     al, dl
0x140005735  cmp     al, dl
0x140005737  jnz     short loc_14000577C
0x140005739  mov     rdx, cs:__isa_inverted
0x140005740  mov     eax, r11d
0x140005743  shr     rax, 10h
0x140005747  mov     ecx, r11d
0x14000574a  and     eax, 6
0x14000574d  and     ecx, 400FFh
0x140005753  or      rax, 1000029h
0x140005759  mov     cs:__avx10_version, ecx
0x14000575f  not     rax
0x140005762  and     rdx, rax
0x140005765  mov     cs:__isa_inverted, rdx
0x14000576c  cmp     cl, 1
0x14000576f  jbe     short loc_14000577C
0x140005771  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140005775  mov     cs:__isa_inverted, rdx
0x14000577c  bt      r10d, 15h
0x140005781  jnb     short loc_140005798
0x140005783  mov     rax, [rsp+38h+arg_0]
0x140005788  bt      rax, 13h
0x14000578d  jnb     short loc_140005798
0x14000578f  btr     cs:__isa_inverted, 7
0x140005798  xor     eax, eax
0x14000579a  add     rsp, 18h
0x14000579e  pop     rdi
0x14000579f  pop     rsi
0x1400057a0  pop     rbp
0x1400057a1  pop     rbx
0x1400057a2  retn
```
