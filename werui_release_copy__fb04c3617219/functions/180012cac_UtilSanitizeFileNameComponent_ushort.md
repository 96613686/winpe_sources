# UtilSanitizeFileNameComponent(ushort *)

- ea: `0x180012cac`
- end: `0x180012d5f`
- name: `?UtilSanitizeFileNameComponent@@YAXPEAG@Z`
- size: `179`
- prototype: `void __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f834`

## callees

- `0x180012cac`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180012cef`
- `msvcrt!_wcsnicmp` at `0x180012cef`

## pseudocode

```c
void __fastcall UtilSanitizeFileNameComponent(wchar_t *String1)
{
  unsigned int i; // edi
  const wchar_t *v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rsi
  wchar_t v6; // cx
  __int64 j; // rax

  for ( i = 0; i < 0x17; ++i )
  {
    v3 = `UtilSanitizeFileNameComponent'::`2'::arpwszIllegal[i];
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
    v5 = (unsigned int)v4;
    if ( !_wcsnicmp(String1, v3, (unsigned int)v4) && (!String1[v5] || String1[v5] == 46) )
    {
      *String1 = 88;
      break;
    }
  }
  while ( *String1 )
  {
    v6 = *String1;
    for ( j = 0; j != 12; ++j )
    {
      if ( v6 == `UtilSanitizeFileNameComponent'::`2'::arwchIllegal[j] )
      {
        *String1 = 95;
        v6 = 95;
      }
    }
    if ( (unsigned __int16)(*String1 - 1) <= 0x1Eu )
      *String1 = 95;
    ++String1;
  }
}

```

## disassembly

```asm
0x180012cac  push    rbx
0x180012cae  push    rbp
0x180012caf  push    rsi
0x180012cb0  push    rdi
0x180012cb1  push    r14
0x180012cb3  push    r15
0x180012cb5  sub     rsp, 28h
0x180012cb9  xor     ebp, ebp
0x180012cbb  lea     r15, __ImageBase
0x180012cc2  mov     rbx, rcx
0x180012cc5  mov     edi, ebp
0x180012cc7  lea     r14d, [rbp+1]
0x180012ccb  cmp     edi, 17h
0x180012cce  jnb     short loc_180012D10
0x180012cd0  mov     eax, edi
0x180012cd2  mov     rdx, ds:rva ?arpwszIllegal@?1??UtilSanitizeFileNameComponent@@YAXPEAG@Z@4QBQEBGB[r15+rax*8]; String2
0x180012cda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012cde  inc     rax
0x180012ce1  cmp     [rdx+rax*2], bp
0x180012ce5  jnz     short loc_180012CDE
0x180012ce7  mov     r8d, eax; MaxCount
0x180012cea  mov     rcx, rbx; String1
0x180012ced  mov     esi, eax
0x180012cef  call    cs:__imp__wcsnicmp
0x180012cf5  test    eax, eax
0x180012cf7  jnz     short loc_180012D06
0x180012cf9  cmp     [rbx+rsi*2], bp
0x180012cfd  jz      short loc_180012D0B
0x180012cff  cmp     word ptr [rbx+rsi*2], 2Eh ; '.'
0x180012d04  jz      short loc_180012D0B
0x180012d06  add     edi, r14d
0x180012d09  jmp     short loc_180012CCB
0x180012d0b  mov     word ptr [rbx], 58h ; 'X'
0x180012d10  cmp     [rbx], bp
0x180012d13  jz      short loc_180012D52
0x180012d15  mov     edx, 5Fh ; '_'
0x180012d1a  movzx   ecx, word ptr [rbx]
0x180012d1d  mov     rax, rbp
0x180012d20  cmp     cx, ds:rva ?arwchIllegal@?1??UtilSanitizeFileNameComponent@@YAXPEAG@Z@4QBGB[r15+rax*2]; ushort const near * const `UtilSanitizeFileNameComponent(ushort *)'::`2'::arwchIllegal ...
0x180012d29  jnz     short loc_180012D30
0x180012d2b  mov     [rbx], dx
0x180012d2e  mov     ecx, edx
0x180012d30  add     rax, r14
0x180012d33  cmp     rax, 0Ch
0x180012d37  jnz     short loc_180012D20
0x180012d39  movzx   eax, word ptr [rbx]
0x180012d3c  sub     ax, r14w
0x180012d40  cmp     ax, 1Eh
0x180012d44  ja      short loc_180012D49
0x180012d46  mov     [rbx], dx
0x180012d49  add     rbx, 2
0x180012d4d  cmp     [rbx], bp
0x180012d50  jnz     short loc_180012D1A
0x180012d52  add     rsp, 28h
0x180012d56  pop     r15
0x180012d58  pop     r14
0x180012d5a  pop     rdi
0x180012d5b  pop     rsi
0x180012d5c  pop     rbp
0x180012d5d  pop     rbx
0x180012d5e  retn
```
