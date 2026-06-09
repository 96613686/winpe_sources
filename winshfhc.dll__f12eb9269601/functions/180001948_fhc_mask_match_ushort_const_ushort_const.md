# fhc_mask_match(ushort const *,ushort const *)

- ea: `0x180001948`
- end: `0x1800019ce`
- name: `?fhc_mask_match@@YAHPEBG0@Z`
- size: `134`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019e0`

## callees

- `0x180001948`

## import_xrefs

- `msvcrt!towupper` at `0x18000197a`
- `msvcrt!towupper` at `0x18000198e`
- `msvcrt!towupper` at `0x18000197a`
- `msvcrt!towupper` at `0x18000198e`

## pseudocode

```c
_BOOL8 __fastcall fhc_mask_match(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  wint_t v5; // cx
  wint_t v6; // bx

  LODWORD(v4) = 0;
  if ( !*a1 )
    return a2[(unsigned int)v4] == 0;
  while ( a2[(unsigned int)v4] )
  {
    v5 = a1[(unsigned int)v4];
    if ( v5 == 42 )
      return 1;
    v6 = towupper(v5);
    if ( v6 != towupper(a2[(unsigned int)v4]) )
      break;
    v4 = (unsigned int)(v4 + 1);
    if ( !a1[v4] )
      return a2[(unsigned int)v4] == 0;
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
0x18000194d  push    r14
0x18000194f  push    r15
0x180001951  sub     rsp, 28h
0x180001955  xor     r15d, r15d
0x180001958  mov     r14, rdx
0x18000195b  mov     rsi, rcx
0x18000195e  mov     edi, r15d
0x180001961  cmp     [rcx], r15w
0x180001965  jz      short loc_1800019A8
0x180001967  mov     ebp, edi
0x180001969  cmp     [r14+rbp*2], r15w
0x18000196e  jz      short loc_1800019CA
0x180001970  movzx   ecx, word ptr [rsi+rbp*2]; C
0x180001974  cmp     cx, 2Ah ; '*'
0x180001978  jz      short loc_1800019C3
0x18000197a  call    cs:__imp_towupper
0x180001981  nop     dword ptr [rax+rax+00h]
0x180001986  movzx   ecx, word ptr [r14+rbp*2]; C
0x18000198b  movzx   ebx, ax
0x18000198e  call    cs:__imp_towupper
0x180001995  nop     dword ptr [rax+rax+00h]
0x18000199a  cmp     bx, ax
0x18000199d  jnz     short loc_1800019CA
0x18000199f  inc     edi
0x1800019a1  cmp     [rsi+rdi*2], r15w
0x1800019a6  jnz     short loc_180001967
0x1800019a8  mov     ecx, edi
0x1800019aa  mov     eax, r15d
0x1800019ad  cmp     [r14+rcx*2], r15w
0x1800019b2  setz    al
0x1800019b5  add     rsp, 28h
0x1800019b9  pop     r15
0x1800019bb  pop     r14
0x1800019bd  pop     rdi
0x1800019be  pop     rsi
0x1800019bf  pop     rbp
0x1800019c0  pop     rbx
0x1800019c1  retn
0x1800019c3  mov     eax, 1
0x1800019c8  jmp     short loc_1800019B5
0x1800019ca  xor     eax, eax
0x1800019cc  jmp     short loc_1800019B5
```
