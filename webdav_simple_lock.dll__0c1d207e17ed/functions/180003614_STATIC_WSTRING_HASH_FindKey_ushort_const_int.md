# STATIC_WSTRING_HASH::FindKey(ushort const *,int)

- ea: `0x180003614`
- end: `0x1800036d0`
- name: `?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z`
- size: `188`
- prototype: `struct STATIC_WSTRING_HASH_RECORD *__fastcall(STATIC_WSTRING_HASH *this, wchar_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dc0`
- `0x1800031b0`
- `0x180003530`
- `0x1800036e0`
- `0x1800039e0`
- `0x180003a10`

## callees

- `0x180003614`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800036b1`
- `msvcrt!_wcsicmp` at `0x1800036b1`

## pseudocode

```c
struct STATIC_WSTRING_HASH_RECORD *__fastcall STATIC_WSTRING_HASH::FindKey(STATIC_WSTRING_HASH *this, wchar_t *a2)
{
  wchar_t v2; // ax
  const wchar_t *v3; // rdi
  unsigned int v5; // r8d
  wchar_t v6; // cx
  __int64 i; // rbx
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rax
  signed __int64 v10; // rdx
  int v11; // r8d
  int v12; // ecx
  bool v13; // zf

  v2 = *a2;
  v3 = a2;
  v5 = 0;
  if ( *((_DWORD *)this + 262) )
  {
    while ( v2 )
    {
      ++a2;
      v5 = v2 + 101 * v5;
      v2 = *a2;
    }
  }
  else
  {
    while ( v2 )
    {
      v6 = v2;
      v2 = *++a2;
      v5 = (v6 & 0xFFDF) + 101 * v5;
    }
  }
  for ( i = *((_QWORD *)this + v5 % 0x83); i; i = *(_QWORD *)(i + 8) )
  {
    v8 = *(const wchar_t **)i;
    if ( *((_DWORD *)this + 262) )
    {
      v9 = v3;
      v10 = (char *)v8 - (char *)v3;
      do
      {
        v11 = *(const wchar_t *)((char *)v9 + v10);
        v12 = *v9 - v11;
        if ( v12 )
          break;
        ++v9;
      }
      while ( v11 );
      v13 = v12 == 0;
    }
    else
    {
      v13 = _wcsicmp(v3, v8) == 0;
    }
    if ( v13 )
      break;
  }
  return (struct STATIC_WSTRING_HASH_RECORD *)i;
}

```

## disassembly

```asm
0x180003614  push    rbx
0x180003616  push    rbp
0x180003617  push    rsi
0x180003618  push    rdi
0x180003619  sub     rsp, 28h
0x18000361d  movzx   eax, word ptr [rdx]
0x180003620  xor     ebp, ebp
0x180003622  mov     rdi, rdx
0x180003625  mov     rsi, rcx
0x180003628  mov     r8d, ebp
0x18000362b  cmp     [rcx+418h], ebp
0x180003631  jz      short loc_180003664
0x180003633  jmp     short loc_180003646
0x180003635  movzx   eax, ax
0x180003638  lea     rdx, [rdx+2]
0x18000363c  imul    r8d, 65h ; 'e'
0x180003640  add     r8d, eax
0x180003643  movzx   eax, word ptr [rdx]
0x180003646  test    ax, ax
0x180003649  jnz     short loc_180003635
0x18000364b  jmp     short loc_180003669
0x18000364d  movzx   ecx, ax
0x180003650  lea     rdx, [rdx+2]
0x180003654  movzx   eax, word ptr [rdx]
0x180003657  and     ecx, 0FFDFh
0x18000365d  imul    r8d, 65h ; 'e'
0x180003661  add     r8d, ecx
0x180003664  test    ax, ax
0x180003667  jnz     short loc_18000364D
0x180003669  mov     eax, 0FA232CF3h
0x18000366e  mul     r8d
0x180003671  shr     edx, 7
0x180003674  imul    eax, edx, 83h
0x18000367a  sub     r8d, eax
0x18000367d  mov     rbx, [rsi+r8*8]
0x180003681  jmp     short loc_1800036BF
0x180003683  mov     rdx, [rbx]; String2
0x180003686  cmp     [rsi+418h], ebp
0x18000368c  jz      short loc_1800036AE
0x18000368e  mov     rax, rdi
0x180003691  sub     rdx, rdi
0x180003694  movzx   ecx, word ptr [rax]
0x180003697  movzx   r8d, word ptr [rax+rdx]
0x18000369c  sub     ecx, r8d
0x18000369f  jnz     short loc_1800036AA
0x1800036a1  add     rax, 2
0x1800036a5  test    r8d, r8d
0x1800036a8  jnz     short loc_180003694
0x1800036aa  test    ecx, ecx
0x1800036ac  jmp     short loc_1800036B9
0x1800036ae  mov     rcx, rdi; String1
0x1800036b1  call    cs:__imp__wcsicmp
0x1800036b7  test    eax, eax
0x1800036b9  jz      short loc_1800036C4
0x1800036bb  mov     rbx, [rbx+8]
0x1800036bf  test    rbx, rbx
0x1800036c2  jnz     short loc_180003683
0x1800036c4  mov     rax, rbx
0x1800036c7  add     rsp, 28h
0x1800036cb  pop     rdi
0x1800036cc  pop     rsi
0x1800036cd  pop     rbp
0x1800036ce  pop     rbx
0x1800036cf  retn
```
