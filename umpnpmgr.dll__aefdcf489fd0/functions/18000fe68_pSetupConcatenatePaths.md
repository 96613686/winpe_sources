# pSetupConcatenatePaths

- ea: `0x18000fe68`
- end: `0x18000ff55`
- name: `pSetupConcatenatePaths`
- size: `237`
- prototype: `_BOOL8 __fastcall(__int64, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016424`
- `0x1800164e0`
- `0x180016818`

## callees

- `0x18000fe68`
- `0x180010384`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff38`

## pseudocode

```c
_BOOL8 __fastcall pSetupConcatenatePaths(__int64 a1, const wchar_t *a2, unsigned int a3)
{
  __int64 v3; // r10
  unsigned int v4; // r11d
  __int64 v5; // r9
  int v7; // ecx
  __int64 v8; // rax
  DWORD v9; // ebx
  HRESULT v10; // eax

  v3 = -1;
  v4 = a3;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  do
    ++v3;
  while ( a2[v3] );
  if ( (_DWORD)v5
    && (*(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 92 || *(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 47) )
  {
    LODWORD(v5) = v5 - 1;
  }
  if ( *a2 == 92 || *a2 == 47 )
  {
    v7 = 1;
    LODWORD(v3) = v3 - 1;
  }
  else
  {
    v7 = 0;
  }
  if ( (int)v5 + (int)v3 + 2 > a3 )
  {
    v9 = 206;
LABEL_25:
    SetLastError(v9);
    return v9 == 0;
  }
  if ( !v7 )
  {
    if ( (unsigned int)v5 >= a3 )
    {
LABEL_17:
      v9 = 206;
      goto LABEL_20;
    }
    v8 = (unsigned int)v5;
    LODWORD(v5) = v5 + 1;
    *(_WORD *)(a1 + 2 * v8) = 92;
  }
  if ( (unsigned int)v5 >= a3 )
    goto LABEL_17;
  v9 = 0;
  v10 = StringCchCopyW((STRSAFE_LPWSTR)(a1 + 2LL * (unsigned int)v5), a3 - (unsigned int)v5, a2);
  if ( v10 < 0 )
    v9 = (unsigned __int16)v10;
LABEL_20:
  if ( v4 )
    *(_WORD *)(a1 + 2LL * (v4 - 1)) = 0;
  if ( v9 )
    goto LABEL_25;
  return v9 == 0;
}

```

## disassembly

```asm
0x18000fe68  mov     [rsp+arg_0], rbx
0x18000fe6d  mov     [rsp+arg_8], rsi
0x18000fe72  push    rdi
0x18000fe73  sub     rsp, 20h
0x18000fe77  or      r10, 0FFFFFFFFFFFFFFFFh
0x18000fe7b  mov     r11d, r8d
0x18000fe7e  mov     r9, r10
0x18000fe81  xor     esi, esi
0x18000fe83  mov     r8, rdx; pszSrc
0x18000fe86  mov     rdi, rcx
0x18000fe89  inc     r9
0x18000fe8c  cmp     [rcx+r9*2], si
0x18000fe91  jnz     short loc_18000FE89
0x18000fe93  inc     r10
0x18000fe96  cmp     [rdx+r10*2], si
0x18000fe9b  jnz     short loc_18000FE93
0x18000fe9d  or      ebx, 0FFFFFFFFh
0x18000fea0  mov     edx, 5Ch ; '\'
0x18000fea5  test    r9d, r9d
0x18000fea8  jz      short loc_18000FEBF
0x18000feaa  mov     eax, r9d
0x18000fead  cmp     [rcx+rax*2-2], dx
0x18000feb2  jz      short loc_18000FEBC
0x18000feb4  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x18000feba  jnz     short loc_18000FEBF
0x18000febc  add     r9d, ebx
0x18000febf  cmp     [r8], dx
0x18000fec3  jz      short loc_18000FED0
0x18000fec5  cmp     word ptr [r8], 2Fh ; '/'
0x18000feca  jz      short loc_18000FED0
0x18000fecc  mov     ecx, esi
0x18000fece  jmp     short loc_18000FED8
0x18000fed0  mov     ecx, 1
0x18000fed5  add     r10d, ebx
0x18000fed8  lea     eax, [r10+2]
0x18000fedc  add     eax, r9d
0x18000fedf  cmp     eax, r11d
0x18000fee2  ja      short loc_18000FF31
0x18000fee4  test    ecx, ecx
0x18000fee6  jnz     short loc_18000FEF7
0x18000fee8  cmp     r9d, r11d
0x18000feeb  jnb     short loc_18000FEFC
0x18000feed  mov     eax, r9d
0x18000fef0  inc     r9d
0x18000fef3  mov     [rdi+rax*2], dx
0x18000fef7  cmp     r9d, r11d
0x18000fefa  jb      short loc_18000FF03
0x18000fefc  mov     ebx, 0CEh
0x18000ff01  jmp     short loc_18000FF1E
0x18000ff03  mov     eax, r9d
0x18000ff06  mov     edx, r11d
0x18000ff09  sub     edx, r9d; cchDest
0x18000ff0c  mov     ebx, esi
0x18000ff0e  lea     rcx, [rdi+rax*2]; pszDest
0x18000ff12  call    StringCchCopyW
0x18000ff17  test    eax, eax
0x18000ff19  jns     short loc_18000FF1E
0x18000ff1b  movzx   ebx, ax
0x18000ff1e  test    r11d, r11d
0x18000ff21  jz      short loc_18000FF2B
0x18000ff23  lea     eax, [r11-1]
0x18000ff27  mov     [rdi+rax*2], si
0x18000ff2b  test    ebx, ebx
0x18000ff2d  jnz     short loc_18000FF36
0x18000ff2f  jmp     short loc_18000FF3E
0x18000ff31  mov     ebx, 0CEh
0x18000ff36  mov     ecx, ebx; dwErrCode
0x18000ff38  call    cs:__imp_SetLastError
0x18000ff3e  test    ebx, ebx
0x18000ff40  mov     eax, esi
0x18000ff42  mov     rbx, [rsp+28h+arg_0]
0x18000ff47  mov     rsi, [rsp+28h+arg_8]
0x18000ff4c  setz    al
0x18000ff4f  add     rsp, 20h
0x18000ff53  pop     rdi
0x18000ff54  retn
```
