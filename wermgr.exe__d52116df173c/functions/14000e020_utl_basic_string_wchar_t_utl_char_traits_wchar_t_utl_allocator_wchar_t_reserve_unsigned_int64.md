# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)

- ea: `0x14000e020`
- end: `0x14000e08f`
- name: `?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z`
- size: `111`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400045bc`
- `0x14001817c`
- `0x140018ff0`
- `0x14001c23c`

## callees

- `0x14000d87c`
- `0x14000e020`

## pseudocode

```c
bool __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(
        _QWORD *a1,
        unsigned __int64 a2)
{
  _QWORD *v2; // r9
  __int64 v4; // rax
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rdx

  v2 = a1 + 2;
  v4 = 7;
  if ( (_QWORD *)*a1 == a1 + 2 )
    v5 = 7;
  else
    v5 = (__int64)(*v2 - *a1) >> 1;
  if ( a2 <= v5 )
    return 1;
  if ( (_QWORD *)*a1 != v2 )
    v4 = (__int64)(*v2 - *a1) >> 1;
  v6 = 2 * v4 + 1;
  if ( v6 < a2 )
    v6 = a2;
  if ( v6 > 0x3FFFFFFFFFFFFFF7LL )
    v6 = 0x3FFFFFFFFFFFFFF7LL;
  return a2 <= v6
      && utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo((__int64)a1, v6);
}

```

## disassembly

```asm
0x14000e020  sub     rsp, 28h
0x14000e024  lea     r9, [rcx+10h]
0x14000e028  mov     r10, rdx
0x14000e02b  mov     eax, 7
0x14000e030  cmp     [rcx], r9
0x14000e033  jnz     short loc_14000E03A
0x14000e035  mov     r8d, eax
0x14000e038  jmp     short loc_14000E043
0x14000e03a  mov     r8, [r9]
0x14000e03d  sub     r8, [rcx]
0x14000e040  sar     r8, 1
0x14000e043  cmp     r10, r8
0x14000e046  jbe     short loc_14000E088
0x14000e048  cmp     [rcx], r9
0x14000e04b  jz      short loc_14000E056
0x14000e04d  mov     rax, [r9]
0x14000e050  sub     rax, [rcx]
0x14000e053  sar     rax, 1
0x14000e056  lea     rdx, ds:1[rax*2]
0x14000e05e  mov     rax, 3FFFFFFFFFFFFFF7h
0x14000e068  cmp     rdx, r10
0x14000e06b  cmovb   rdx, r10
0x14000e06f  cmp     rdx, rax
0x14000e072  cmova   rdx, rax
0x14000e076  cmp     r10, rdx
0x14000e079  ja      short loc_14000E084
0x14000e07b  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x14000e080  test    al, al
0x14000e082  jnz     short loc_14000E088
0x14000e084  xor     al, al
0x14000e086  jmp     short loc_14000E08A
0x14000e088  mov     al, 1
0x14000e08a  add     rsp, 28h
0x14000e08e  retn
```
