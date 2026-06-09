# Login_OnCommand(HWND__ *,ushort,ushort,HWND__ *)

- ea: `0x180012ae0`
- end: `0x180012c56`
- name: `?Login_OnCommand@@YAHPEAUHWND__@@GG0@Z`
- size: `374`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, unsigned __int16, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012ab0`

## callees

- `0x180003950`
- `0x180012ae0`
- `0x18001be60`
- `0x180029280`

## import_xrefs

- `USER32!GetDlgItemTextW` at `0x180012b49`
- `USER32!GetDlgItemTextW` at `0x180012b64`
- `USER32!GetDlgItemTextW` at `0x180012b7d`
- `USER32!GetDlgItemTextW` at `0x180012b49`
- `USER32!GetDlgItemTextW` at `0x180012b64`
- `USER32!GetDlgItemTextW` at `0x180012b7d`
- `USER32!EndDialog` at `0x180012c32`
- `USER32!EndDialog` at `0x180012c32`
- `USER32!GetWindowLongPtrW` at `0x180012b0d`
- `USER32!GetWindowLongPtrW` at `0x180012b0d`
- `SHLWAPI!StrCmpW` at `0x180012bd8`
- `SHLWAPI!StrCmpW` at `0x180012bd8`

## pseudocode

```c
__int64 __fastcall Login_OnCommand(HWND hWnd, __int64 a2, unsigned __int16 a3, HWND a4)
{
  unsigned int v4; // ebp
  int v5; // ebx
  LONG_PTR WindowLongPtrW; // rsi
  INT_PTR v8; // rdx
  unsigned int v9; // edx
  WCHAR psz1[72]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR psz2[72]; // [rsp+B0h] [rbp-1D8h] BYREF
  WCHAR String[136]; // [rsp+140h] [rbp-148h] BYREF

  v4 = 1;
  v5 = a3;
  WindowLongPtrW = GetWindowLongPtrW(hWnd, 16);
  if ( v5 == 1 )
  {
    GetDlgItemTextW(hWnd, 2122, String, 129);
    GetDlgItemTextW(hWnd, 2096, psz1, 65);
    GetDlgItemTextW(hWnd, 2141, psz2, 65);
    if ( String[0] )
    {
      if ( !psz1[0] )
      {
        v9 = *(_DWORD *)(WindowLongPtrW + 44) != 0 ? 8104 : 8107;
        goto LABEL_13;
      }
    }
    else if ( psz1[0] || psz2[0] )
    {
      v9 = *(_DWORD *)(WindowLongPtrW + 44) != 0 ? 8105 : 8109;
      goto LABEL_13;
    }
    if ( !StrCmpW(psz1, psz2) )
    {
      StringCchCopyW((unsigned __int16 *)(WindowLongPtrW + 172), 0x80u, String);
      StringCchCopyW((unsigned __int16 *)(WindowLongPtrW + 428), 0x40u, psz1);
      *(_DWORD *)WindowLongPtrW |= 0x180u;
      v8 = 1;
      goto LABEL_15;
    }
    v9 = 8231;
LABEL_13:
    SGMessageBox(hWnd, v9, 0x30u);
    return v4;
  }
  if ( v5 == 2 )
  {
    v8 = 2;
LABEL_15:
    EndDialog(hWnd, v8);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180012ae0  push    rbx
0x180012ae2  push    rbp
0x180012ae3  push    rsi
0x180012ae4  push    rdi
0x180012ae5  sub     rsp, 268h
0x180012aec  mov     rax, cs:__security_cookie
0x180012af3  xor     rax, rsp
0x180012af6  mov     [rsp+288h+var_38], rax
0x180012afe  mov     ebp, 1
0x180012b03  movzx   ebx, r8w
0x180012b07  mov     rdi, rcx
0x180012b0a  lea     edx, [rbp+0Fh]; nIndex
0x180012b0d  call    cs:__imp_GetWindowLongPtrW
0x180012b13  mov     rsi, rax
0x180012b16  mov     eax, ebx
0x180012b18  sub     eax, ebp
0x180012b1a  jz      short loc_180012B33
0x180012b1c  cmp     eax, ebp
0x180012b1e  jz      short loc_180012B29
0x180012b20  xor     ebx, ebx
0x180012b22  mov     ebp, ebx
0x180012b24  jmp     loc_180012C38
0x180012b29  mov     edx, 2
0x180012b2e  jmp     loc_180012C2F
0x180012b33  mov     r9d, 81h; cchMax
0x180012b39  lea     r8, [rsp+288h+String]; lpString
0x180012b41  mov     edx, 84Ah; nIDDlgItem
0x180012b46  mov     rcx, rdi; hDlg
0x180012b49  call    cs:__imp_GetDlgItemTextW
0x180012b4f  mov     ebx, 41h ; 'A'
0x180012b54  lea     r8, [rsp+288h+psz1]; lpString
0x180012b59  mov     r9d, ebx; cchMax
0x180012b5c  mov     edx, 830h; nIDDlgItem
0x180012b61  mov     rcx, rdi; hDlg
0x180012b64  call    cs:__imp_GetDlgItemTextW
0x180012b6a  mov     r9d, ebx; cchMax
0x180012b6d  lea     r8, [rsp+288h+psz2]; lpString
0x180012b75  mov     edx, 85Dh; nIDDlgItem
0x180012b7a  mov     rcx, rdi; hDlg
0x180012b7d  call    cs:__imp_GetDlgItemTextW
0x180012b83  xor     ebx, ebx
0x180012b85  cmp     [rsp+288h+String], bx
0x180012b8d  jnz     short loc_180012BB2
0x180012b8f  cmp     [rsp+288h+psz1], bx
0x180012b94  jnz     short loc_180012BA0
0x180012b96  cmp     [rsp+288h+psz2], bx
0x180012b9e  jz      short loc_180012BCB
0x180012ba0  mov     eax, [rsi+2Ch]
0x180012ba3  neg     eax
0x180012ba5  sbb     edx, edx
0x180012ba7  and     edx, 0FFFFFFFCh
0x180012baa  add     edx, 1FADh
0x180012bb0  jmp     short loc_180012BE7
0x180012bb2  cmp     [rsp+288h+psz1], bx
0x180012bb7  jnz     short loc_180012BCB
0x180012bb9  mov     eax, [rsi+2Ch]
0x180012bbc  neg     eax
0x180012bbe  sbb     edx, edx
0x180012bc0  and     edx, 0FFFFFFFDh
0x180012bc3  add     edx, 1FABh
0x180012bc9  jmp     short loc_180012BE7
0x180012bcb  lea     rdx, [rsp+288h+psz2]; psz2
0x180012bd3  lea     rcx, [rsp+288h+psz1]; psz1
0x180012bd8  call    cs:__imp_StrCmpW
0x180012bde  test    eax, eax
0x180012be0  jz      short loc_180012BF7
0x180012be2  mov     edx, 2027h; unsigned int
0x180012be7  mov     r8d, 30h ; '0'; unsigned int
0x180012bed  mov     rcx, rdi; hWnd
0x180012bf0  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x180012bf5  jmp     short loc_180012C38
0x180012bf7  lea     rcx, [rsi+0ACh]; unsigned __int16 *
0x180012bfe  mov     edx, 80h; unsigned __int64
0x180012c03  lea     r8, [rsp+288h+String]; unsigned __int16 *
0x180012c0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012c10  lea     rcx, [rsi+1ACh]; unsigned __int16 *
0x180012c17  mov     edx, 40h ; '@'; unsigned __int64
0x180012c1c  lea     r8, [rsp+288h+psz1]; unsigned __int16 *
0x180012c21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012c26  or      dword ptr [rsi], 180h
0x180012c2c  mov     rdx, rbp; nResult
0x180012c2f  mov     rcx, rdi; hDlg
0x180012c32  call    cs:__imp_EndDialog
0x180012c38  mov     eax, ebp
0x180012c3a  mov     rcx, [rsp+288h+var_38]
0x180012c42  xor     rcx, rsp; StackCookie
0x180012c45  call    __security_check_cookie
0x180012c4a  add     rsp, 268h
0x180012c51  pop     rdi
0x180012c52  pop     rsi
0x180012c53  pop     rbp
0x180012c54  pop     rbx
0x180012c55  retn
```
