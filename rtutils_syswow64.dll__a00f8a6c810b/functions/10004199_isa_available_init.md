# ___isa_available_init

- ea: `0x10004199`
- end: `0x100044b5`
- name: `___isa_available_init`
- size: `796`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10003df8`
- `0x10003ee8`

## callees

- `0x10004199`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x100041b4`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x100041b4`

## pseudocode

```c
int __cdecl __isa_available_init()
{
  bool v5; // zf
  int v11; // eax
  int v12; // edx
  int v28; // eax
  unsigned int v29; // ecx
  int v31; // [esp+0h] [ebp-28h]
  int v32; // [esp+1Ch] [ebp-Ch]
  int v33; // [esp+24h] [ebp-4h]

  __isa_enabled |= 1u;
  __isa_available = 0;
  if ( IsProcessorFeaturePresent(0xAu) )
  {
    _EAX = 0;
    __asm { cpuid }
    v33 = _EAX;
    v5 = (_EBX ^ 0x756E6547 | _ECX ^ 0x6C65746E | _EDX ^ 0x49656E69) == 0;
    _EAX = 1;
    __asm { cpuid }
    v31 = _EAX;
    if ( v5 )
    {
      v11 = _EAX & 0xFFF3FF0;
      if ( (v31 & 0xFFF3FF0) == 0x106C0
        || v11 == 132704
        || v11 == 132720
        || v11 == 198224
        || v11 == 198240
        || v11 == 198256 )
      {
        __favor |= 1u;
      }
    }
    v12 = _ECX;
    v32 = _ECX;
    if ( v33 >= 7 )
    {
      _EAX = 7;
      __asm { cpuid }
      if ( (_EBX & 0x200) != 0 )
        __favor |= 2u;
      if ( _EAX >= 1 )
      {
        _EAX = 7;
        __asm { cpuid }
      }
      _EAX = 36;
      if ( v33 >= 36 )
        __asm { cpuid }
      v12 = v32;
    }
    v28 = __isa_enabled | 2;
    v29 = __isa_inverted & 0xFFFFFFFE;
    __isa_available = 1;
    __isa_enabled |= 2u;
    __isa_inverted &= ~1u;
    if ( (v12 & 0x100000) != 0 )
    {
      __isa_available = 2;
      __isa_enabled = v28 | 4;
      __isa_inverted = v29 & 0xFFFFFFEF;
      if ( (v12 & 0x18000000) == 0x18000000 )
        __asm { xgetbv }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10004199  mov     edi, edi
0x1000419b  push    ebp
0x1000419c  mov     ebp, esp
0x1000419e  or      ___isa_enabled, 1
0x100041a5  sub     esp, 28h
0x100041a8  mov     ___isa_available, 0
0x100041b2  push    0Ah; ProcessorFeature
0x100041b4  call    ds:__imp__IsProcessorFeaturePresent@4; IsProcessorFeaturePresent(x)
0x100041ba  test    eax, eax
0x100041bc  jz      loc_100044B1
0x100041c2  push    ebx
0x100041c3  push    esi
0x100041c4  push    edi
0x100041c5  xor     eax, eax
0x100041c7  lea     edi, [ebp+var_28]
0x100041ca  xor     ecx, ecx
0x100041cc  push    ebx
0x100041cd  cpuid
0x100041cf  mov     esi, ebx
0x100041d1  pop     ebx
0x100041d2  nop
0x100041d3  mov     [edi], eax
0x100041d5  mov     [edi+4], esi
0x100041d8  mov     [edi+8], ecx
0x100041db  mov     [edi+0Ch], edx
0x100041de  mov     eax, [ebp+var_28]
0x100041e1  mov     ecx, [ebp+var_1C]
0x100041e4  mov     [ebp+var_4], eax
0x100041e7  xor     ecx, 49656E69h
0x100041ed  mov     eax, [ebp+var_20]
0x100041f0  xor     eax, 6C65746Eh
0x100041f5  or      ecx, eax
0x100041f7  mov     eax, [ebp+var_24]
0x100041fa  push    1
0x100041fc  xor     eax, 756E6547h
0x10004201  or      ecx, eax
0x10004203  pop     eax
0x10004204  push    0
0x10004206  pop     ecx
0x10004207  push    ebx
0x10004208  cpuid
0x1000420a  mov     esi, ebx
0x1000420c  pop     ebx
0x1000420d  nop
0x1000420e  mov     [edi], eax
0x10004210  mov     [edi+4], esi
0x10004213  mov     [edi+8], ecx
0x10004216  mov     [edi+0Ch], edx
0x10004219  jnz     short loc_10004254
0x1000421b  mov     eax, [ebp+var_28]
0x1000421e  and     eax, 0FFF3FF0h
0x10004223  cmp     eax, 106C0h
0x10004228  jz      short loc_1000424D
0x1000422a  cmp     eax, 20660h
0x1000422f  jz      short loc_1000424D
0x10004231  cmp     eax, 20670h
0x10004236  jz      short loc_1000424D
0x10004238  cmp     eax, 30650h
0x1000423d  jz      short loc_1000424D
0x1000423f  cmp     eax, 30660h
0x10004244  jz      short loc_1000424D
0x10004246  cmp     eax, 30670h
0x1000424b  jnz     short loc_10004254
0x1000424d  or      ___favor, 1
0x10004254  mov     edx, [ebp+var_20]
0x10004257  xor     ebx, ebx
0x10004259  xor     edi, edi
0x1000425b  mov     [ebp+var_C], edx
0x1000425e  cmp     [ebp+var_4], 7
0x10004262  mov     [ebp+var_14], ebx
0x10004265  mov     [ebp+var_18], ebx
0x10004268  jl      loc_100042F5
0x1000426e  push    7
0x10004270  pop     eax
0x10004271  xor     ecx, ecx
0x10004273  push    ebx
0x10004274  cpuid
0x10004276  mov     esi, ebx
0x10004278  pop     ebx
0x10004279  nop
0x1000427a  lea     ebx, [ebp+var_28]
0x1000427d  mov     [ebx], eax
0x1000427f  mov     [ebx+4], esi
0x10004282  mov     [ebx+8], ecx
0x10004285  mov     [ebx+0Ch], edx
0x10004288  mov     ebx, [ebp+var_24]
0x1000428b  mov     eax, [ebp+var_1C]
0x1000428e  mov     [ebp+var_8], ebx
0x10004291  mov     [ebp+var_14], eax
0x10004294  test    ebx, 200h
0x1000429a  jz      short loc_100042A3
0x1000429c  or      ___favor, 2
0x100042a3  cmp     [ebp+var_28], 1
0x100042a7  jl      short loc_100042CD
0x100042a9  push    7
0x100042ab  pop     eax
0x100042ac  xor     ecx, ecx
0x100042ae  inc     ecx
0x100042af  push    ebx
0x100042b0  cpuid
0x100042b2  mov     esi, ebx
0x100042b4  pop     ebx
0x100042b5  nop
0x100042b6  lea     ebx, [ebp+var_28]
0x100042b9  mov     [ebx], eax
0x100042bb  mov     [ebx+4], esi
0x100042be  mov     [ebx+8], ecx
0x100042c1  mov     [ebx+0Ch], edx
0x100042c4  mov     eax, [ebp+var_1C]
0x100042c7  mov     ebx, [ebp+var_8]
0x100042ca  mov     [ebp+var_18], eax
0x100042cd  push    24h ; '$'
0x100042cf  pop     eax
0x100042d0  cmp     [ebp+var_4], eax
0x100042d3  jl      short loc_100042F2
0x100042d5  xor     ecx, ecx
0x100042d7  lea     edi, [ebp+var_28]
0x100042da  push    ebx
0x100042db  cpuid
0x100042dd  mov     esi, ebx
0x100042df  pop     ebx
0x100042e0  nop
0x100042e1  mov     ebx, [ebp+var_8]
0x100042e4  mov     [edi], eax
0x100042e6  mov     [edi+4], esi
0x100042e9  mov     [edi+8], ecx
0x100042ec  mov     [edi+0Ch], edx
0x100042ef  mov     edi, [ebp+var_24]
0x100042f2  mov     edx, [ebp+var_C]
0x100042f5  mov     eax, ___isa_enabled
0x100042fa  mov     ecx, ___isa_inverted
0x10004300  or      eax, 2
0x10004303  mov     esi, dword_1000B08C
0x10004309  and     ecx, 0FFFFFFFEh
0x1000430c  mov     ___isa_available, 1
0x10004316  mov     ___isa_enabled, eax
0x1000431b  mov     ___isa_inverted, ecx
0x10004321  mov     dword_1000B08C, esi
0x10004327  test    edx, 100000h
0x1000432d  jz      loc_100044AE
0x10004333  or      eax, 4
0x10004336  mov     ___isa_available, 2
0x10004340  mov     ___isa_enabled, eax
0x10004345  and     ecx, 0FFFFFFEFh
0x10004348  mov     eax, 18000000h
0x1000434d  mov     ___isa_inverted, ecx
0x10004353  and     edx, eax
0x10004355  mov     dword_1000B08C, esi
0x1000435b  cmp     edx, eax
0x1000435d  jnz     loc_100044AE
0x10004363  xor     ecx, ecx
0x10004365  xgetbv
0x10004368  mov     [ebp+var_10], eax
0x1000436b  xor     esi, esi
0x1000436d  mov     [ebp+var_C], edx
0x10004370  mov     eax, [ebp+var_10]
0x10004373  mov     ecx, [ebp+var_C]
0x10004376  and     eax, 6
0x10004379  and     ecx, esi
0x1000437b  cmp     eax, 6
0x1000437e  jnz     loc_100044AE
0x10004384  cmp     ecx, esi
0x10004386  jnz     loc_100044AE
0x1000438c  mov     eax, ___isa_enabled
0x10004391  or      eax, 8
0x10004394  mov     ___isa_available, 3
0x1000439e  mov     ___isa_enabled, eax
0x100043a3  test    bl, 20h
0x100043a6  jz      short loc_10004421
0x100043a8  mov     ecx, dword_1000B08C
0x100043ae  or      eax, 20h
0x100043b1  mov     ___isa_enabled, eax
0x100043b6  mov     edx, 0D0030000h
0x100043bb  mov     eax, ___isa_inverted
0x100043c0  and     ebx, edx
0x100043c2  and     eax, 0FFFFFFFDh
0x100043c5  mov     ___isa_available, 5
0x100043cf  mov     ___isa_inverted, eax
0x100043d4  mov     dword_1000B08C, ecx
0x100043da  cmp     ebx, edx
0x100043dc  jnz     short loc_1000442C
0x100043de  mov     eax, [ebp+var_10]
0x100043e1  mov     edx, 0E0h
0x100043e6  mov     ecx, [ebp+var_C]
0x100043e9  and     eax, edx
0x100043eb  and     ecx, esi
0x100043ed  cmp     eax, edx
0x100043ef  jnz     short loc_10004421
0x100043f1  cmp     ecx, esi
0x100043f3  jnz     short loc_10004421
0x100043f5  mov     eax, ___isa_inverted
0x100043fa  or      ___isa_enabled, 40h
0x10004401  and     eax, 0FFFFFFDBh
0x10004404  mov     ecx, dword_1000B08C
0x1000440a  mov     ___isa_available, 6
0x10004414  mov     ___isa_inverted, eax
0x10004419  mov     dword_1000B08C, ecx
0x1000441f  jmp     short loc_1000442C
0x10004421  mov     ecx, dword_1000B08C
0x10004427  mov     eax, ___isa_inverted
0x1000442c  test    [ebp+var_14], 800000h
0x10004433  jz      short loc_10004445
0x10004435  and     eax, 0FEFFFFFFh
0x1000443a  mov     dword_1000B08C, ecx
0x10004440  mov     ___isa_inverted, eax
0x10004445  test    [ebp+var_18], 80000h
0x1000444c  jz      short loc_100044AE
0x1000444e  mov     eax, [ebp+var_10]
0x10004451  mov     edx, 0E0h
0x10004456  mov     ecx, [ebp+var_C]
0x10004459  and     eax, edx
0x1000445b  and     ecx, esi
0x1000445d  cmp     eax, edx
0x1000445f  jnz     short loc_100044AE
0x10004461  cmp     ecx, esi
0x10004463  jnz     short loc_100044AE
0x10004465  mov     eax, edi
0x10004467  xor     ecx, ecx
0x10004469  shr     edi, 10h
0x1000446c  and     eax, 400FFh
0x10004471  and     edi, 6
0x10004474  mov     ___avx10_version, eax
0x10004479  or      edi, 1000029h
0x1000447f  not     ecx
0x10004481  and     ecx, dword_1000B08C
0x10004487  not     edi
0x10004489  and     edi, ___isa_inverted
0x1000448f  mov     ___isa_inverted, edi
0x10004495  mov     dword_1000B08C, ecx
0x1000449b  cmp     al, 1
0x1000449d  jbe     short loc_100044AE
0x1000449f  and     edi, 0FFFFFFBFh
0x100044a2  mov     dword_1000B08C, ecx
0x100044a8  mov     ___isa_inverted, edi
0x100044ae  pop     edi
0x100044af  pop     esi
0x100044b0  pop     ebx
0x100044b1  xor     eax, eax
0x100044b3  leave
0x100044b4  retn
```
