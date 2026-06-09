# FailedApplySecurityProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180006b80`
- end: `0x180006ce1`
- name: `?FailedApplySecurityProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `353`
- prototype: `INT_PTR __fastcall(HWND, int, unsigned __int16, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006b80`
- `0x180016428`
- `0x18001645c`

## import_xrefs

- `SHLWAPI!PathSetDlgItemPathW` at `0x180006c2c`
- `SHLWAPI!PathSetDlgItemPathW` at `0x180006c2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006cce`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c86`
- `USER32!EndDialog` at `0x180006bb9`
- `USER32!EndDialog` at `0x180006bb9`
- `USER32!SetDlgItemTextW` at `0x180006c01`
- `USER32!SetDlgItemTextW` at `0x180006cbe`
- `USER32!SetDlgItemTextW` at `0x180006c01`
- `USER32!SetDlgItemTextW` at `0x180006cbe`

## pseudocode

```c
INT_PTR __fastcall FailedApplySecurityProc(HWND a1, int a2, unsigned __int16 a3, __int64 a4)
{
  int v6; // edx
  unsigned int v8; // r8d
  DWORD v9; // r8d
  LPCWSTR lpString[3]; // [rsp+40h] [rbp-18h] BYREF

  v6 = a2 - 272;
  if ( v6 )
  {
    if ( v6 == 1 && (a3 == 1 || a3 == 2) )
    {
      EndDialog(a1, a3);
      return 1;
    }
  }
  else
  {
    v8 = *(_DWORD *)(a4 + 24);
    lpString[0] = 0;
    if ( v8 )
    {
      LoadStringAlloc((unsigned __int16 **)lpString, g_hInstance, v8);
      if ( lpString[0] )
      {
        SetDlgItemTextW(a1, 102, lpString[0]);
        if ( lpString[0] )
          LocalFree((HLOCAL)lpString[0]);
      }
      lpString[0] = 0;
    }
    PathSetDlgItemPathW(a1, 100, *(LPCWSTR *)(a4 + 16));
    v9 = *(_DWORD *)(a4 + 8);
    if ( v9 )
    {
      if ( v9 == -2147024891 )
      {
        FormatStringID((unsigned __int16 **)lpString, g_hInstance, 0x5Du);
      }
      else if ( !FormatMessageW(0x1300u, 0, v9, 0, (LPWSTR)lpString, 0, 0) )
      {
        FormatStringID((unsigned __int16 **)lpString, g_hInstance, 0xAu, *(unsigned int *)(a4 + 8));
      }
      if ( lpString[0] )
      {
        SetDlgItemTextW(a1, 101, lpString[0]);
        if ( lpString[0] )
          LocalFree((HLOCAL)lpString[0]);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006b80  mov     [rsp+arg_0], rbx
0x180006b85  push    rdi
0x180006b86  sub     rsp, 50h
0x180006b8a  mov     rbx, r9
0x180006b8d  mov     rdi, rcx
0x180006b90  sub     edx, 110h
0x180006b96  jz      short loc_180006BC9
0x180006b98  cmp     edx, 1
0x180006b9b  jnz     loc_180006CD4
0x180006ba1  movzx   r8d, r8w
0x180006ba5  mov     edx, r8d
0x180006ba8  sub     edx, 1
0x180006bab  jz      short loc_180006BB6
0x180006bad  cmp     edx, 1
0x180006bb0  jnz     loc_180006CD4
0x180006bb6  mov     rdx, r8; nResult
0x180006bb9  call    cs:__imp_EndDialog
0x180006bbf  mov     eax, 1
0x180006bc4  jmp     loc_180006CD6
0x180006bc9  mov     r8d, [r9+18h]; unsigned int
0x180006bcd  mov     [rsp+58h+lpString], 0
0x180006bd6  test    r8d, r8d
0x180006bd9  jz      short loc_180006C20
0x180006bdb  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180006be2  lea     rcx, [rsp+58h+lpString]; unsigned __int16 **
0x180006be7  call    ?LoadStringAlloc@@YAHPEAPEAGPEAUHINSTANCE__@@I@Z; LoadStringAlloc(ushort * *,HINSTANCE__ *,uint)
0x180006bec  mov     rcx, [rsp+58h+lpString]
0x180006bf1  test    rcx, rcx
0x180006bf4  jz      short loc_180006C17
0x180006bf6  mov     r8, rcx; lpString
0x180006bf9  mov     edx, 66h ; 'f'; nIDDlgItem
0x180006bfe  mov     rcx, rdi; hDlg
0x180006c01  call    cs:__imp_SetDlgItemTextW
0x180006c07  mov     rcx, [rsp+58h+lpString]; hMem
0x180006c0c  test    rcx, rcx
0x180006c0f  jz      short loc_180006C17
0x180006c11  call    cs:__imp_LocalFree
0x180006c17  mov     [rsp+58h+lpString], 0
0x180006c20  mov     r8, [rbx+10h]; pszPath
0x180006c24  mov     edx, 64h ; 'd'; id
0x180006c29  mov     rcx, rdi; hDlg
0x180006c2c  call    cs:__imp_PathSetDlgItemPathW
0x180006c32  mov     r8d, [rbx+8]; dwMessageId
0x180006c36  test    r8d, r8d
0x180006c39  jz      loc_180006CD4
0x180006c3f  cmp     r8d, 80070005h
0x180006c46  jnz     short loc_180006C61
0x180006c48  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180006c4f  lea     rcx, [rsp+58h+lpString]; unsigned __int16 **
0x180006c54  mov     r8d, 5Dh ; ']'; unsigned int
0x180006c5a  call    ?FormatStringID@@YAKPEAPEAGPEAUHINSTANCE__@@IZZ; FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180006c5f  jmp     short loc_180006CA9
0x180006c61  mov     [rsp+58h+Arguments], 0; Arguments
0x180006c6a  lea     rax, [rsp+58h+lpString]
0x180006c6f  mov     [rsp+58h+nSize], 0; nSize
0x180006c77  xor     r9d, r9d; dwLanguageId
0x180006c7a  xor     edx, edx; lpSource
0x180006c7c  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180006c81  mov     ecx, 1300h; dwFlags
0x180006c86  call    cs:__imp_FormatMessageW
0x180006c8c  test    eax, eax
0x180006c8e  jnz     short loc_180006CA9
0x180006c90  mov     r9d, [rbx+8]
0x180006c94  lea     r8d, [rax+0Ah]; unsigned int
0x180006c98  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180006c9f  lea     rcx, [rsp+58h+lpString]; unsigned __int16 **
0x180006ca4  call    ?FormatStringID@@YAKPEAPEAGPEAUHINSTANCE__@@IZZ; FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180006ca9  mov     rcx, [rsp+58h+lpString]
0x180006cae  test    rcx, rcx
0x180006cb1  jz      short loc_180006CD4
0x180006cb3  mov     r8, rcx; lpString
0x180006cb6  mov     edx, 65h ; 'e'; nIDDlgItem
0x180006cbb  mov     rcx, rdi; hDlg
0x180006cbe  call    cs:__imp_SetDlgItemTextW
0x180006cc4  mov     rcx, [rsp+58h+lpString]; hMem
0x180006cc9  test    rcx, rcx
0x180006ccc  jz      short loc_180006CD4
0x180006cce  call    cs:__imp_LocalFree
0x180006cd4  xor     eax, eax
0x180006cd6  mov     rbx, [rsp+58h+arg_0]
0x180006cdb  add     rsp, 50h
0x180006cdf  pop     rdi
0x180006ce0  retn
```
