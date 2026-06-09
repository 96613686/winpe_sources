# CIasMigErrorHelper::ReadStringFromResource(ushort const *,uint,_bstr_t &)

- ea: `0x180053c30`
- end: `0x180053e26`
- name: `?ReadStringFromResource@CIasMigErrorHelper@@SAJPEBGIAEAV_bstr_t@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName, UINT uID, struct _bstr_t *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053188`
- `0x180053e2c`
- `0x180054220`
- `0x180054320`
- `0x1800544b0`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x180042a80`
- `0x18004724c`
- `0x180053c30`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180053c56`
- `KERNEL32!LocalFree` at `0x180053d7a`
- `KERNEL32!LocalFree` at `0x180053e09`
- `KERNEL32!LocalFree` at `0x180053c56`
- `KERNEL32!LocalFree` at `0x180053d7a`
- `KERNEL32!LocalFree` at `0x180053e09`
- `KERNEL32!LoadLibraryExW` at `0x180053ce2`
- `KERNEL32!LoadLibraryExW` at `0x180053ce2`
- `KERNEL32!GetLastError` at `0x180053ced`
- `KERNEL32!GetLastError` at `0x180053d80`
- `KERNEL32!GetLastError` at `0x180053ced`
- `KERNEL32!GetLastError` at `0x180053d80`
- `KERNEL32!LocalAlloc` at `0x180053c71`
- `KERNEL32!LocalAlloc` at `0x180053c71`
- `USER32!LoadStringW` at `0x180053d6b`
- `USER32!LoadStringW` at `0x180053d6b`

## string_xrefs

- `0x180053ca0`: `ReadStringFromResource: LocalAlloc() failed.\n`
- `0x180053d23`: `ReadStringFromResource: LoadLibraryExW() Error: %!hresult!`
- `0x180053db6`: `ReadStringFromResource: LoadStringW() Error: %!hresult!`

## pseudocode

```c
__int64 __fastcall CIasMigErrorHelper::ReadStringFromResource(LPCWSTR lpLibFileName, UINT uID, struct _bstr_t *a3)
{
  unsigned int v6; // ebx
  WCHAR *v7; // rax
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  int StringW; // eax
  signed int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // eax
  LPWSTR hMem; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v17[20]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v18; // [rsp+A8h] [rbp+20h]

  hMem = 0;
  v6 = 128;
  while ( 1 )
  {
    try
    {
      LocalFree(&hMem);
      hMem = 0;
      v6 *= 2;
      v7 = (WCHAR *)LocalAlloc(0x40u, 2LL * v6);
    }
    catch ( _com_error v17 )
    {
      v18 = v17[2];
      _com_error::~_com_error((_com_error *)v17);
      return v18;
    }
    hMem = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WppDbgPrint("ReadStringFromResource: LocalAlloc() failed.\n");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids, "NPSSETUP");
      }
      return 2147942414LL;
    }
    Library = LoadLibraryExW(lpLibFileName, 0, 0x22u);
    if ( !Library )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WppDbgPrint("ReadStringFromResource: LoadLibraryExW() Error: %!hresult!");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids,
          (unsigned int)"NPSSETUP",
          v11);
      }
      return v11;
    }
    StringW = LoadStringW(Library, uID, hMem, v6);
    if ( !StringW )
      break;
    v15 = StringW + 1;
    if ( v15 < v6 )
    {
      _bstr_t::operator=(a3, hMem);
      LocalFree(&hMem);
      return 0;
    }
  }
  LocalFree(&hMem);
  v13 = GetLastError();
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WppDbgPrint("ReadStringFromResource: LoadStringW() Error: %!hresult!");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids,
      (unsigned int)"NPSSETUP",
      v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180053c30  push    rbx
0x180053c32  push    rsi
0x180053c33  push    rdi
0x180053c34  push    r14
0x180053c36  sub     rsp, 68h
0x180053c3a  mov     rdi, r8
0x180053c3d  mov     r14d, edx
0x180053c40  mov     rsi, rcx
0x180053c43  mov     [rsp+88h+hMem], 0
0x180053c4c  mov     ebx, 80h
0x180053c51  lea     rcx, [rsp+88h+hMem]; hMem
0x180053c56  call    cs:__imp_LocalFree
0x180053c5c  mov     [rsp+88h+hMem], 0
0x180053c65  add     ebx, ebx
0x180053c67  mov     edx, ebx
0x180053c69  add     rdx, rdx; uBytes
0x180053c6c  mov     ecx, 40h ; '@'; uFlags
0x180053c71  call    cs:__imp_LocalAlloc
0x180053c77  mov     [rsp+88h+hMem], rax
0x180053c7c  test    rax, rax
0x180053c7f  jnz     short loc_180053CD9
0x180053c81  lea     rax, WPP_GLOBAL_Control
0x180053c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c8f  cmp     rcx, rax
0x180053c92  jz      short loc_180053CCF
0x180053c94  cmp     byte ptr [rcx+19h], 2
0x180053c98  jb      short loc_180053CCF
0x180053c9a  test    byte ptr [rcx+1Ch], 40h
0x180053c9e  jz      short loc_180053CCF
0x180053ca0  lea     rcx, aReadstringfrom; "ReadStringFromResource: LocalAlloc() fa"...
0x180053ca7  call    WppDbgPrint
0x180053cac  mov     edx, 0Dh
0x180053cb1  lea     r9, aNpssetup; "NPSSETUP"
0x180053cb8  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x180053cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180053cc6  mov     rcx, [rcx+10h]
0x180053cca  call    WPP_SF_s
0x180053ccf  mov     eax, 8007000Eh
0x180053cd4  jmp     loc_180053E1B
0x180053cd9  xor     edx, edx; hFile
0x180053cdb  lea     r8d, [rdx+22h]; dwFlags
0x180053cdf  mov     rcx, rsi; lpLibFileName
0x180053ce2  call    cs:__imp_LoadLibraryExW
0x180053ce8  test    rax, rax
0x180053ceb  jnz     short loc_180053D5D
0x180053ced  call    cs:__imp_GetLastError
0x180053cf3  mov     ebx, eax
0x180053cf5  test    eax, eax
0x180053cf7  jle     short loc_180053D02
0x180053cf9  movzx   ebx, ax
0x180053cfc  or      ebx, 80070000h
0x180053d02  lea     rax, WPP_GLOBAL_Control
0x180053d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d10  cmp     rcx, rax
0x180053d13  jz      short loc_180053D56
0x180053d15  cmp     byte ptr [rcx+19h], 2
0x180053d19  jb      short loc_180053D56
0x180053d1b  test    byte ptr [rcx+1Ch], 40h
0x180053d1f  jz      short loc_180053D56
0x180053d21  mov     edx, ebx
0x180053d23  lea     rcx, aReadstringfrom_2; "ReadStringFromResource: LoadLibraryExW("...
0x180053d2a  call    WppDbgPrint
0x180053d2f  mov     edx, 0Eh
0x180053d34  mov     [rsp+88h+var_68], ebx
0x180053d38  lea     r9, aNpssetup; "NPSSETUP"
0x180053d3f  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x180053d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d4d  mov     rcx, [rcx+10h]
0x180053d51  call    WPP_SF_sd
0x180053d56  mov     eax, ebx
0x180053d58  jmp     loc_180053E1B
0x180053d5d  mov     r9d, ebx; cchBufferMax
0x180053d60  mov     r8, [rsp+88h+hMem]; lpBuffer
0x180053d65  mov     edx, r14d; uID
0x180053d68  mov     rcx, rax; hInstance
0x180053d6b  call    cs:__imp_LoadStringW
0x180053d71  test    eax, eax
0x180053d73  jnz     short loc_180053DED
0x180053d75  lea     rcx, [rsp+88h+hMem]; hMem
0x180053d7a  call    cs:__imp_LocalFree
0x180053d80  call    cs:__imp_GetLastError
0x180053d86  mov     ebx, eax
0x180053d88  test    eax, eax
0x180053d8a  jle     short loc_180053D95
0x180053d8c  movzx   ebx, ax
0x180053d8f  or      ebx, 80070000h
0x180053d95  lea     rax, WPP_GLOBAL_Control
0x180053d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053da3  cmp     rcx, rax
0x180053da6  jz      short loc_180053DE9
0x180053da8  cmp     byte ptr [rcx+19h], 2
0x180053dac  jb      short loc_180053DE9
0x180053dae  test    byte ptr [rcx+1Ch], 40h
0x180053db2  jz      short loc_180053DE9
0x180053db4  mov     edx, ebx
0x180053db6  lea     rcx, aReadstringfrom_1; "ReadStringFromResource: LoadStringW() E"...
0x180053dbd  call    WppDbgPrint
0x180053dc2  mov     edx, 0Fh
0x180053dc7  mov     [rsp+88h+var_68], ebx
0x180053dcb  lea     r9, aNpssetup; "NPSSETUP"
0x180053dd2  lea     r8, WPP_a172f93e3a9532ef0a391bb7dc34d5ba_Traceguids
0x180053dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180053de0  mov     rcx, [rcx+10h]
0x180053de4  call    WPP_SF_sd
0x180053de9  mov     eax, ebx
0x180053deb  jmp     short loc_180053E1B
0x180053ded  inc     eax
0x180053def  cmp     eax, ebx
0x180053df1  jnb     loc_180053C51
0x180053df7  mov     rdx, [rsp+88h+hMem]
0x180053dfc  mov     rcx, rdi
0x180053dff  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180053e04  lea     rcx, [rsp+88h+hMem]; hMem
0x180053e09  call    cs:__imp_LocalFree
0x180053e0f  nop
0x180053e10  xor     eax, eax
0x180053e12  jmp     short loc_180053E1B
0x180053e14  mov     eax, [rsp+88h+arg_18]
0x180053e1b  add     rsp, 68h
0x180053e1f  pop     r14
0x180053e21  pop     rdi
0x180053e22  pop     rsi
0x180053e23  pop     rbx
0x180053e24  retn
```
