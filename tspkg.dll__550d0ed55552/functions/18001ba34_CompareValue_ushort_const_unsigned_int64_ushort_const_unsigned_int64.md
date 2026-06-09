# CompareValue(ushort const *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18001ba34`
- end: `0x18001bad9`
- name: `?CompareValue@@YAHPEBG_K01@Z`
- size: `165`
- prototype: `__int64 __fastcall(wchar_t *String2, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002e50`
- `0x180007c40`

## callees

- `0x18000c144`
- `0x18000c150`
- `0x18001ba34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001ba68`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001ba68`

## pseudocode

```c
_BOOL8 __fastcall CompareValue(wchar_t *String2, unsigned __int64 a2, const unsigned __int16 *a3, __int64 a4)
{
  wchar_t *v8; // rax
  __int64 v9; // rax
  unsigned int v10; // r15d
  int v11; // eax

  if ( !String2 || !a2 || !a3 || !a4 )
    return 0;
  v8 = wcschr(a3, 0x2Au);
  if ( v8 )
  {
    v9 = v8 - a3;
    v10 = a4 - v9 - 1;
    if ( (unsigned int)(a4 - 1) > a2 || wcsnicmp(a3, String2, (unsigned int)v9) )
      return 0;
    v11 = wcsnicmp(&a3[a4 - v10], &String2[a2 - v10], v10);
  }
  else
  {
    v11 = wcsicmp(a3, String2);
  }
  return !v11;
}

```

## disassembly

```asm
0x18001ba34  push    rbx
0x18001ba36  push    rsi
0x18001ba37  push    rdi
0x18001ba38  push    r14
0x18001ba3a  push    r15
0x18001ba3c  sub     rsp, 20h
0x18001ba40  mov     rdi, r9
0x18001ba43  mov     rbx, r8
0x18001ba46  mov     rsi, rdx
0x18001ba49  mov     r14, rcx
0x18001ba4c  test    rcx, rcx
0x18001ba4f  jz      short loc_18001BAB7
0x18001ba51  test    rdx, rdx
0x18001ba54  jz      short loc_18001BAB7
0x18001ba56  test    rbx, rbx
0x18001ba59  jz      short loc_18001BAB7
0x18001ba5b  test    r9, r9
0x18001ba5e  jz      short loc_18001BAB7
0x18001ba60  mov     edx, 2Ah ; '*'; Ch
0x18001ba65  mov     rcx, rbx; Str
0x18001ba68  call    cs:__imp_wcschr
0x18001ba6e  test    rax, rax
0x18001ba71  jz      short loc_18001BAC5
0x18001ba73  sub     rax, rbx
0x18001ba76  mov     r15d, edi
0x18001ba79  sar     rax, 1
0x18001ba7c  sub     r15d, eax
0x18001ba7f  dec     r15d
0x18001ba82  lea     edx, [r15+rax]
0x18001ba86  cmp     rdx, rsi
0x18001ba89  ja      short loc_18001BAB7
0x18001ba8b  mov     r8d, eax; MaxCount
0x18001ba8e  mov     rdx, r14; String2
0x18001ba91  mov     rcx, rbx; String1
0x18001ba94  call    _wcsnicmp
0x18001ba99  test    eax, eax
0x18001ba9b  jnz     short loc_18001BAB7
0x18001ba9d  mov     r8d, r15d; MaxCount
0x18001baa0  sub     rsi, r8
0x18001baa3  sub     rdi, r8
0x18001baa6  lea     rdx, [r14+rsi*2]; String2
0x18001baaa  lea     rcx, [rbx+rdi*2]; String1
0x18001baae  call    _wcsnicmp
0x18001bab3  test    eax, eax
0x18001bab5  jz      short loc_18001BAD2
0x18001bab7  xor     eax, eax
0x18001bab9  add     rsp, 20h
0x18001babd  pop     r15
0x18001babf  pop     r14
0x18001bac1  pop     rdi
0x18001bac2  pop     rsi
0x18001bac3  pop     rbx
0x18001bac4  retn
0x18001bac5  mov     rdx, r14; String2
0x18001bac8  mov     rcx, rbx; String1
0x18001bacb  call    _wcsicmp
0x18001bad0  jmp     short loc_18001BAB3
0x18001bad2  mov     eax, 1
0x18001bad7  jmp     short loc_18001BAB9
```
