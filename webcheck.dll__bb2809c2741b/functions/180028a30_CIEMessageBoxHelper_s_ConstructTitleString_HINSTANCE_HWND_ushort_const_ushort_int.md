# CIEMessageBoxHelper::s_ConstructTitleString(HINSTANCE__ *,HWND__ *,ushort const *,ushort *,int)

- ea: `0x180028a30`
- end: `0x180028ae1`
- name: `?s_ConstructTitleString@CIEMessageBoxHelper@@SAPEBGPEAUHINSTANCE__@@PEAUHWND__@@PEBGPEAGH@Z`
- size: `177`
- prototype: `static const unsigned __int16 *(HINSTANCE, HWND, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800286e8`

## callees

- `0x180028a30`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180028aa3`
- `KERNEL32!GetCurrentThreadId` at `0x180028aa3`
- `USER32!GetWindowTextW` at `0x180028a76`
- `USER32!GetWindowTextW` at `0x180028a76`
- `USER32!GetPropW` at `0x180028ab7`
- `USER32!GetPropW` at `0x180028ab7`
- `USER32!LoadStringW` at `0x180028a5e`
- `USER32!LoadStringW` at `0x180028a5e`
- `USER32!GetWindowThreadProcessId` at `0x180028a9b`
- `USER32!GetWindowThreadProcessId` at `0x180028a9b`
- `SHLWAPI!StrCmpW` at `0x180028a8a`
- `SHLWAPI!StrCmpW` at `0x180028a8a`

## pseudocode

```c
unsigned __int16 *__fastcall CIEMessageBoxHelper::s_ConstructTitleString(
        HINSTANCE a1,
        HWND a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // rdi
  DWORD WindowThreadProcessId; // ebx
  HANDLE PropW; // rax

  v5 = a3;
  if ( (unsigned __int64)a3 < 0x10000 )
  {
    if ( LoadStringW(a1, (unsigned __int16)a3, a4, 80) )
      return a4;
    if ( !a2 || !GetWindowTextW(a2, a4, 80) )
      return (unsigned __int16 *)&Default;
    if ( StrCmpW(a4, L"Program Manager") )
    {
      return a4;
    }
    else
    {
      v5 = 0;
      WindowThreadProcessId = GetWindowThreadProcessId(a2, 0);
      if ( WindowThreadProcessId == GetCurrentThreadId() )
      {
        PropW = GetPropW(a2, L"pszDesktopTitleW");
        v5 = a4;
        if ( PropW )
          return (unsigned __int16 *)PropW;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180028a30  push    rbx
0x180028a32  push    rbp
0x180028a33  push    rsi
0x180028a34  push    rdi
0x180028a35  sub     rsp, 28h
0x180028a39  mov     rsi, r9
0x180028a3c  mov     rdi, r8
0x180028a3f  mov     rbp, rdx
0x180028a42  cmp     r8, 10000h
0x180028a49  jnb     loc_180028AD5
0x180028a4f  movzx   edx, r8w; uID
0x180028a53  mov     ebx, 50h ; 'P'
0x180028a58  mov     r9d, ebx; cchBufferMax
0x180028a5b  mov     r8, rsi; lpBuffer
0x180028a5e  call    cs:__imp_LoadStringW
0x180028a64  test    eax, eax
0x180028a66  jnz     short loc_180028AC9
0x180028a68  test    rbp, rbp
0x180028a6b  jz      short loc_180028ACE
0x180028a6d  mov     r8d, ebx; nMaxCount
0x180028a70  mov     rdx, rsi; lpString
0x180028a73  mov     rcx, rbp; hWnd
0x180028a76  call    cs:__imp_GetWindowTextW
0x180028a7c  test    eax, eax
0x180028a7e  jz      short loc_180028ACE
0x180028a80  lea     rdx, aProgramManager; "Program Manager"
0x180028a87  mov     rcx, rsi; psz1
0x180028a8a  call    cs:__imp_StrCmpW
0x180028a90  test    eax, eax
0x180028a92  jnz     short loc_180028AC9
0x180028a94  xor     edx, edx; lpdwProcessId
0x180028a96  mov     rcx, rbp; hWnd
0x180028a99  xor     edi, edi
0x180028a9b  call    cs:__imp_GetWindowThreadProcessId
0x180028aa1  mov     ebx, eax
0x180028aa3  call    cs:__imp_GetCurrentThreadId
0x180028aa9  cmp     ebx, eax
0x180028aab  jnz     short loc_180028AD5
0x180028aad  lea     rdx, aPszdesktoptitl; "pszDesktopTitleW"
0x180028ab4  mov     rcx, rbp; hWnd
0x180028ab7  call    cs:__imp_GetPropW
0x180028abd  test    rax, rax
0x180028ac0  mov     rdi, rsi
0x180028ac3  cmovnz  rdi, rax
0x180028ac7  jmp     short loc_180028AD5
0x180028ac9  mov     rdi, rsi
0x180028acc  jmp     short loc_180028AD5
0x180028ace  lea     rdi, Default
0x180028ad5  mov     rax, rdi
0x180028ad8  add     rsp, 28h
0x180028adc  pop     rdi
0x180028add  pop     rsi
0x180028ade  pop     rbp
0x180028adf  pop     rbx
0x180028ae0  retn
```
