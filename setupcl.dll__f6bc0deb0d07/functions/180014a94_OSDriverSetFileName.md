# OSDriverSetFileName

- ea: `0x180014a94`
- end: `0x180014b15`
- name: `OSDriverSetFileName`
- size: `129`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180014784`
- `0x18001490c`

## callees

- `0x180014a94`
- `0x180014bc4`

## import_xrefs

- `ntdll!wcsrchr` at `0x180014ac2`
- `ntdll!wcsrchr` at `0x180014ac2`

## pseudocode

```c
__int64 __fastcall OSDriverSetFileName(__int64 a1, const wchar_t *a2)
{
  __int64 v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rcx

  v3 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( *a2 )
      {
        v4 = wcsrchr(a2, 0x5Cu);
        if ( v4 )
        {
          v3 = a1 + 4;
          StringCchCopyNW((STRSAFE_LPWSTR)(a1 + 4), 0x104u, v4 + 1, 0x103u);
          *(_WORD *)(a1 + 522) = 0;
          v5 = *(_QWORD *)(a1 + 2088);
          *(_DWORD *)(a1 + 2084) |= 0x10000000u;
          *(_DWORD *)(v5 + 4) |= 0x10000000u;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180014a94  mov     [rsp+arg_0], rbx
0x180014a99  mov     [rsp+arg_8], rsi
0x180014a9e  push    rdi
0x180014a9f  sub     rsp, 20h
0x180014aa3  xor     esi, esi
0x180014aa5  mov     rax, rdx
0x180014aa8  mov     rbx, rcx
0x180014aab  mov     edi, esi
0x180014aad  test    rcx, rcx
0x180014ab0  jz      short loc_180014B02
0x180014ab2  test    rax, rax
0x180014ab5  jz      short loc_180014B02
0x180014ab7  cmp     [rdx], si
0x180014aba  jz      short loc_180014B02
0x180014abc  lea     edx, [rsi+5Ch]; Ch
0x180014abf  mov     rcx, rax; Str
0x180014ac2  call    cs:__imp_wcsrchr
0x180014ac8  test    rax, rax
0x180014acb  jz      short loc_180014B02
0x180014acd  mov     edx, 104h; cchDest
0x180014ad2  lea     rdi, [rbx+4]
0x180014ad6  lea     r8, [rax+2]; pszSrc
0x180014ada  mov     rcx, rdi; pszDest
0x180014add  lea     r9d, [rdx-1]; cchToCopy
0x180014ae1  call    StringCchCopyNW
0x180014ae6  mov     [rbx+20Ah], si
0x180014aed  mov     eax, 10000000h
0x180014af2  mov     rcx, [rbx+828h]
0x180014af9  or      [rbx+824h], eax
0x180014aff  or      [rcx+4], eax
0x180014b02  mov     rbx, [rsp+28h+arg_0]
0x180014b07  mov     rax, rdi
0x180014b0a  mov     rsi, [rsp+28h+arg_8]
0x180014b0f  add     rsp, 20h
0x180014b13  pop     rdi
0x180014b14  retn
```
