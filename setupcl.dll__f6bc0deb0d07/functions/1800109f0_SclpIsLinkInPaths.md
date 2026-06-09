# SclpIsLinkInPaths

- ea: `0x1800109f0`
- end: `0x180010b00`
- name: `SclpIsLinkInPaths`
- size: `272`
- prototype: `__int64 __fastcall(wchar_t *String1, _WORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010b08`

## callees

- `0x18000a7f0`
- `0x1800109f0`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x180010ac0`
- `ntdll!_wcsnicmp` at `0x180010ac0`
- `ntdll!_wcsicmp` at `0x180010aa5`
- `ntdll!_wcsicmp` at `0x180010aa5`

## pseudocode

```c
__int64 __fastcall SclpIsLinkInPaths(wchar_t *String1, _WORD *a2, _DWORD *a3)
{
  unsigned __int64 v6; // rbp
  __int64 v7; // rdx
  _WORD *v8; // rcx
  __int64 v9; // rax
  wchar_t *v10; // rdi
  int NextString; // eax
  unsigned int v12; // ebx
  size_t v13; // r15
  wchar_t *String2; // [rsp+78h] [rbp+10h] BYREF
  size_t MaxCount; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v7 = 0;
      v8 = a2;
      do
      {
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        if ( v9 )
          v7 += v9 + 1;
        v8 += v9 + 1;
      }
      while ( *v8 );
      v6 = 2 * v7 + 2;
    }
    else
    {
      v6 = 2;
    }
    v10 = 0;
    String2 = 0;
    MaxCount = 0;
    while ( 1 )
    {
      NextString = SclMultiSzFindNextString((unsigned __int64)a2, v6, (unsigned __int64)v10, &String2, &MaxCount);
      v12 = NextString;
      if ( NextString == -2147483622 )
        break;
      if ( NextString < 0 )
        return v12;
      v10 = String2;
      if ( _wcsicmp(String1, String2) )
      {
        v13 = MaxCount;
        if ( _wcsnicmp(String1, v10, MaxCount) || String1[v13] != 92 )
          continue;
      }
      *a3 = 1;
      return v12;
    }
    return 0;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
}

```

## disassembly

```asm
0x1800109f0  mov     [rsp+arg_0], rbx
0x1800109f5  push    rbp
0x1800109f6  push    rsi
0x1800109f7  push    rdi
0x1800109f8  push    r12
0x1800109fa  push    r13
0x1800109fc  push    r14
0x1800109fe  push    r15
0x180010a00  sub     rsp, 30h
0x180010a04  xor     r13d, r13d
0x180010a07  mov     r14, r8
0x180010a0a  mov     [r8], r13d
0x180010a0d  mov     rsi, rdx
0x180010a10  mov     r12, rcx
0x180010a13  test    rdx, rdx
0x180010a16  jz      loc_180010AE4
0x180010a1c  cmp     r13w, [rdx]
0x180010a20  jnz     short loc_180010A28
0x180010a22  lea     ebp, [r13+2]
0x180010a26  jmp     short loc_180010A5D
0x180010a28  mov     rdx, r13
0x180010a2b  mov     rcx, rsi
0x180010a2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010a32  inc     rax
0x180010a35  cmp     [rcx+rax*2], r13w
0x180010a3a  jnz     short loc_180010A32
0x180010a3c  test    rax, rax
0x180010a3f  jz      short loc_180010A47
0x180010a41  inc     rdx
0x180010a44  add     rdx, rax
0x180010a47  lea     rcx, [rcx+rax*2]
0x180010a4b  add     rcx, 2
0x180010a4f  cmp     r13w, [rcx]
0x180010a53  jnz     short loc_180010A2E
0x180010a55  lea     rbp, ds:2[rdx*2]
0x180010a5d  mov     rdi, r13
0x180010a60  mov     [rsp+68h+String2], r13
0x180010a65  mov     [rsp+68h+MaxCount], r13
0x180010a6d  lea     rax, [rsp+68h+MaxCount]
0x180010a75  mov     r8, rdi
0x180010a78  lea     r9, [rsp+68h+String2]
0x180010a7d  mov     [rsp+68h+var_48], rax
0x180010a82  mov     rdx, rbp
0x180010a85  mov     rcx, rsi
0x180010a88  call    SclMultiSzFindNextString
0x180010a8d  mov     ebx, eax
0x180010a8f  cmp     eax, 8000001Ah
0x180010a94  jz      short loc_180010ADF
0x180010a96  test    eax, eax
0x180010a98  js      short loc_180010AE9
0x180010a9a  mov     rdi, [rsp+68h+String2]
0x180010a9f  mov     rcx, r12; String1
0x180010aa2  mov     rdx, rdi; String2
0x180010aa5  call    cs:__imp__wcsicmp
0x180010aab  test    eax, eax
0x180010aad  jz      short loc_180010AD6
0x180010aaf  mov     r15, [rsp+68h+MaxCount]
0x180010ab7  mov     rdx, rdi; String2
0x180010aba  mov     r8, r15; MaxCount
0x180010abd  mov     rcx, r12; String1
0x180010ac0  call    cs:__imp__wcsnicmp
0x180010ac6  test    eax, eax
0x180010ac8  jnz     short loc_180010A6D
0x180010aca  mov     eax, 5Ch ; '\'
0x180010acf  cmp     ax, [r12+r15*2]
0x180010ad4  jnz     short loc_180010A6D
0x180010ad6  mov     dword ptr [r14], 1
0x180010add  jmp     short loc_180010AE9
0x180010adf  mov     ebx, r13d
0x180010ae2  jmp     short loc_180010AE9
0x180010ae4  mov     ebx, 0C000000Dh
0x180010ae9  mov     eax, ebx
0x180010aeb  mov     rbx, [rsp+68h+arg_0]
0x180010af0  add     rsp, 30h
0x180010af4  pop     r15
0x180010af6  pop     r14
0x180010af8  pop     r13
0x180010afa  pop     r12
0x180010afc  pop     rdi
0x180010afd  pop     rsi
0x180010afe  pop     rbp
0x180010aff  retn
```
