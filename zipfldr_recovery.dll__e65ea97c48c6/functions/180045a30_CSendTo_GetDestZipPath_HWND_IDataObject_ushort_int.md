# CSendTo::_GetDestZipPath(HWND__ *,IDataObject *,ushort *,int)

- ea: `0x180045a30`
- end: `0x180045b26`
- name: `?_GetDestZipPath@CSendTo@@AEAAJPEAUHWND__@@PEAUIDataObject@@PEAGH@Z`
- size: `246`
- prototype: `__int64 __fastcall(CSendTo *__hidden this, HWND, struct IDataObject *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800450f0`

## callees

- `0x180010c30`
- `0x180036f50`
- `0x1800457b8`
- `0x18004580c`
- `0x180045a30`
- `0x180045b2c`
- `0x180045bf8`
- `0x180045c98`

## import_xrefs

- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180045ae7`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180045ae7`
- `SHLWAPI!PathAppendW` at `0x180045abe`
- `SHLWAPI!PathAppendW` at `0x180045abe`
- `SHLWAPI!PathFileExistsW` at `0x180045acd`
- `SHLWAPI!PathFileExistsW` at `0x180045acd`

## pseudocode

```c
int __fastcall CSendTo::_GetDestZipPath(CSendTo *this, HWND a2, struct IDataObject *a3, unsigned __int16 *a4)
{
  int result; // eax
  CSendTo *v9; // rcx
  int v10; // r9d
  CSendTo *v11; // rcx
  int v12; // r9d
  WCHAR pszPath[264]; // [rsp+20h] [rbp-458h] BYREF
  WCHAR pszMore[264]; // [rsp+230h] [rbp-248h] BYREF

  result = CSendTo::_GetZipNameFromDataObject(this, a3, pszMore, (int)a4);
  if ( result >= 0 )
  {
    if ( CSendTo::_GetPathFromDataObject(v9, a3, pszPath, v10) >= 0
      && (unsigned int)CSendTo::_DoesDestSupportZip(this, a3)
      && CSendTo::_CanWriteToFolder(v11, pszPath)
      || (result = CSendTo::_TryDesktopFolder(v11, a2, pszPath, v12), result >= 0) )
    {
      if ( PathAppendW(pszPath, pszMore)
        && (!PathFileExistsW(pszPath) || PathYetAnotherMakeUniqueName(pszPath, pszPath, 0, 0)) )
      {
        return StringCchCopyW(a4, 0x104u, pszPath);
      }
      else
      {
        return -2147467259;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180045a30  push    rbx
0x180045a32  push    rbp
0x180045a33  push    rsi
0x180045a34  push    rdi
0x180045a35  sub     rsp, 458h
0x180045a3c  mov     rax, cs:__security_cookie
0x180045a43  xor     rax, rsp
0x180045a46  mov     [rsp+478h+var_38], rax
0x180045a4e  mov     rbx, r8
0x180045a51  mov     rsi, rdx
0x180045a54  mov     rdx, rbx; struct IDataObject *
0x180045a57  lea     r8, [rsp+478h+pszMore]; unsigned __int16 *
0x180045a5f  mov     rbp, r9
0x180045a62  mov     rdi, rcx
0x180045a65  call    ?_GetZipNameFromDataObject@CSendTo@@AEAAJPEAUIDataObject@@PEAGH@Z; CSendTo::_GetZipNameFromDataObject(IDataObject *,ushort *,int)
0x180045a6a  test    eax, eax
0x180045a6c  js      loc_180045B0A
0x180045a72  lea     r8, [rsp+478h+pszPath]; unsigned __int16 *
0x180045a77  mov     rdx, rbx; struct IDataObject *
0x180045a7a  call    ?_GetPathFromDataObject@CSendTo@@AEAAJPEAUIDataObject@@PEAGH@Z; CSendTo::_GetPathFromDataObject(IDataObject *,ushort *,int)
0x180045a7f  test    eax, eax
0x180045a81  js      short loc_180045AA0
0x180045a83  mov     rdx, rbx; struct IDataObject *
0x180045a86  mov     rcx, rdi; this
0x180045a89  call    ?_DoesDestSupportZip@CSendTo@@AEAAHPEAUIDataObject@@@Z; CSendTo::_DoesDestSupportZip(IDataObject *)
0x180045a8e  test    eax, eax
0x180045a90  jz      short loc_180045AA0
0x180045a92  lea     rdx, [rsp+478h+pszPath]; unsigned __int16 *
0x180045a97  call    ?_CanWriteToFolder@CSendTo@@AEAAHPEBG@Z; CSendTo::_CanWriteToFolder(ushort const *)
0x180045a9c  test    eax, eax
0x180045a9e  jnz     short loc_180045AB1
0x180045aa0  lea     r8, [rsp+478h+pszPath]; unsigned __int16 *
0x180045aa5  mov     rdx, rsi; HWND
0x180045aa8  call    ?_TryDesktopFolder@CSendTo@@AEAAJPEAUHWND__@@PEAGH@Z; CSendTo::_TryDesktopFolder(HWND__ *,ushort *,int)
0x180045aad  test    eax, eax
0x180045aaf  js      short loc_180045B0A
0x180045ab1  lea     rdx, [rsp+478h+pszMore]; pszMore
0x180045ab9  lea     rcx, [rsp+478h+pszPath]; pszPath
0x180045abe  call    cs:__imp_PathAppendW
0x180045ac4  test    eax, eax
0x180045ac6  jz      short loc_180045AF1
0x180045ac8  lea     rcx, [rsp+478h+pszPath]; pszPath
0x180045acd  call    cs:__imp_PathFileExistsW
0x180045ad3  test    eax, eax
0x180045ad5  jz      short loc_180045AF8
0x180045ad7  xor     r9d, r9d; pszFileSpec
0x180045ada  lea     rdx, [rsp+478h+pszPath]; pszPath
0x180045adf  xor     r8d, r8d; pszShort
0x180045ae2  lea     rcx, [rsp+478h+pszPath]; pszUniqueName
0x180045ae7  call    cs:__imp_PathYetAnotherMakeUniqueName
0x180045aed  test    eax, eax
0x180045aef  jnz     short loc_180045AF8
0x180045af1  mov     eax, 80004005h
0x180045af6  jmp     short loc_180045B0A
0x180045af8  lea     r8, [rsp+478h+pszPath]; unsigned __int16 *
0x180045afd  mov     edx, 104h; unsigned __int64
0x180045b02  mov     rcx, rbp; unsigned __int16 *
0x180045b05  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180045b0a  mov     rcx, [rsp+478h+var_38]
0x180045b12  xor     rcx, rsp; StackCookie
0x180045b15  call    __security_check_cookie
0x180045b1a  add     rsp, 458h
0x180045b21  pop     rdi
0x180045b22  pop     rsi
0x180045b23  pop     rbp
0x180045b24  pop     rbx
0x180045b25  retn
```
