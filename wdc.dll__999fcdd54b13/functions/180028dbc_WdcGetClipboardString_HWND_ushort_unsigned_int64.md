# WdcGetClipboardString(HWND__ *,ushort *,unsigned __int64)

- ea: `0x180028dbc`
- end: `0x180028fe1`
- name: `?WdcGetClipboardString@@YAJPEAUHWND__@@PEAG_K@Z`
- size: `549`
- prototype: `int(HWND, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800688e0`

## callees

- `0x18000b854`
- `0x18001cb20`
- `0x180028dbc`
- `0x180068868`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x180028fc3`
- `KERNEL32!GlobalUnlock` at `0x180028fc3`
- `KERNEL32!GlobalLock` at `0x180028e31`
- `KERNEL32!GlobalLock` at `0x180028f74`
- `KERNEL32!GlobalLock` at `0x180028e31`
- `KERNEL32!GlobalLock` at `0x180028f74`
- `KERNEL32!GetLastError` at `0x180028dd7`
- `KERNEL32!GetLastError` at `0x180028e17`
- `KERNEL32!GetLastError` at `0x180028eaa`
- `KERNEL32!GetLastError` at `0x180028f2c`
- `KERNEL32!GetLastError` at `0x180028f52`
- `KERNEL32!GetLastError` at `0x180028dd7`
- `KERNEL32!GetLastError` at `0x180028e17`
- `KERNEL32!GetLastError` at `0x180028eaa`
- `KERNEL32!GetLastError` at `0x180028f2c`
- `KERNEL32!GetLastError` at `0x180028f52`
- `USER32!CloseClipboard` at `0x180028fd0`
- `USER32!CloseClipboard` at `0x180028fd0`
- `USER32!GetClipboardData` at `0x180028e05`
- `USER32!GetClipboardData` at `0x180028f1e`
- `USER32!GetClipboardData` at `0x180028e05`
- `USER32!GetClipboardData` at `0x180028f1e`
- `USER32!IsClipboardFormatAvailable` at `0x180028df5`
- `USER32!IsClipboardFormatAvailable` at `0x180028f0e`
- `USER32!IsClipboardFormatAvailable` at `0x180028df5`
- `USER32!IsClipboardFormatAvailable` at `0x180028f0e`
- `USER32!OpenClipboard` at `0x180028dc8`
- `USER32!OpenClipboard` at `0x180028dc8`

## pseudocode

```c
__int64 __fastcall WdcGetClipboardString(HWND a1, unsigned __int16 *a2)
{
  signed int LastError; // eax
  signed int v4; // ebx
  HANDLE ClipboardData; // rax
  void *v6; // rdi
  signed int v7; // eax
  const unsigned __int16 *v8; // rax
  int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  const char *v14; // rax

  if ( OpenClipboard(a1) )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_6:
      if ( IsClipboardFormatAvailable(0xDu) )
      {
        ClipboardData = GetClipboardData(0xDu);
        v6 = ClipboardData;
        if ( !ClipboardData )
        {
          v7 = GetLastError();
          v4 = v7;
          if ( v7 )
          {
            if ( v7 > 0 )
              v4 = (unsigned __int16)v7 | 0x80070000;
            if ( v4 >= 0 )
              goto LABEL_12;
LABEL_17:
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
              "WdcGetClipboardString",
              0,
              L"FAILURE: 0x%08x",
              v4);
            goto LABEL_46;
          }
LABEL_16:
          v4 = -2147467259;
          goto LABEL_17;
        }
        if ( ClipboardData != (HANDLE)-1LL )
        {
LABEL_12:
          v8 = (const unsigned __int16 *)GlobalLock(v6);
          if ( !v8 )
          {
LABEL_13:
            v9 = -2147024882;
            v4 = -2147024882;
LABEL_42:
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
              "WdcGetClipboardString",
              0,
              L"FAILURE: 0x%08x",
              v9);
LABEL_43:
            if ( v6 )
              goto LABEL_44;
LABEL_46:
            CloseClipboard();
            return (unsigned int)v4;
          }
          v9 = StringCchCopyW(a2, 0x104u, v8);
LABEL_41:
          v4 = v9;
          if ( v9 >= 0 )
            goto LABEL_43;
          goto LABEL_42;
        }
        v10 = GetLastError();
        v4 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            v4 = (unsigned __int16)v10 | 0x80070000;
          if ( v4 >= 0 )
            goto LABEL_12;
LABEL_25:
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
            "WdcGetClipboardString",
            0,
            L"FAILURE: 0x%08x",
            v4);
LABEL_44:
          GlobalUnlock(v6);
          goto LABEL_46;
        }
LABEL_24:
        v4 = -2147467259;
        goto LABEL_25;
      }
      if ( !IsClipboardFormatAvailable(1u) )
      {
        v4 = -2147467259;
        goto LABEL_46;
      }
      v11 = GetClipboardData(1u);
      v6 = v11;
      if ( v11 )
      {
        if ( v11 == (HANDLE)-1LL )
        {
          v13 = GetLastError();
          v4 = v13;
          if ( !v13 )
            goto LABEL_24;
          if ( v13 > 0 )
            v4 = (unsigned __int16)v13 | 0x80070000;
          if ( v4 < 0 )
            goto LABEL_25;
        }
      }
      else
      {
        v12 = GetLastError();
        v4 = v12;
        if ( !v12 )
          goto LABEL_16;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_17;
      }
      v14 = (const char *)GlobalLock(v6);
      if ( !v14 )
        goto LABEL_13;
      v9 = WdcMbToUnicode(v14, a2, 0x104u);
      goto LABEL_41;
    }
  }
  else
  {
    v4 = -2147467259;
  }
  WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp", "WdcGetClipboardString", 0, L"FAILURE: 0x%08x", v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028dbc  push    rbx
0x180028dbe  push    rbp
0x180028dbf  push    rsi
0x180028dc0  push    rdi
0x180028dc1  sub     rsp, 38h
0x180028dc5  mov     rsi, rdx
0x180028dc8  call    cs:__imp_OpenClipboard
0x180028dce  mov     ebp, 80070000h
0x180028dd3  test    eax, eax
0x180028dd5  jnz     short loc_180028DEE
0x180028dd7  call    cs:__imp_GetLastError
0x180028ddd  mov     ebx, eax
0x180028ddf  test    eax, eax
0x180028de1  jz      short loc_180028E4C
0x180028de3  jle     short loc_180028DEA
0x180028de5  movzx   ebx, ax
0x180028de8  or      ebx, ebp
0x180028dea  test    ebx, ebx
0x180028dec  js      short loc_180028E51
0x180028dee  mov     ebx, 0Dh
0x180028df3  mov     ecx, ebx; format
0x180028df5  call    cs:__imp_IsClipboardFormatAvailable
0x180028dfb  test    eax, eax
0x180028dfd  jz      loc_180028F07
0x180028e03  mov     ecx, ebx; uFormat
0x180028e05  call    cs:__imp_GetClipboardData
0x180028e0b  mov     rdi, rax
0x180028e0e  test    rax, rax
0x180028e11  jnz     loc_180028EA4
0x180028e17  call    cs:__imp_GetLastError
0x180028e1d  mov     ebx, eax
0x180028e1f  test    eax, eax
0x180028e21  jz      short loc_180028E79
0x180028e23  jle     short loc_180028E2A
0x180028e25  movzx   ebx, ax
0x180028e28  or      ebx, ebp
0x180028e2a  test    ebx, ebx
0x180028e2c  js      short loc_180028E7E
0x180028e2e  mov     rcx, rdi; hMem
0x180028e31  call    cs:__imp_GlobalLock
0x180028e37  test    rax, rax
0x180028e3a  jnz     loc_180028EF2
0x180028e40  mov     eax, 8007000Eh
0x180028e45  mov     ebx, eax
0x180028e47  jmp     loc_180028F9A
0x180028e4c  mov     ebx, 80004005h
0x180028e51  mov     eax, ebx
0x180028e53  mov     [rsp+58h+var_38], ebx
0x180028e57  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028e5e  xor     r8d, r8d; int
0x180028e61  lea     rdx, aWdcgetclipboar; "WdcGetClipboardString"
0x180028e68  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180028e6f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028e74  jmp     loc_180028FD6
0x180028e79  mov     ebx, 80004005h
0x180028e7e  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028e85  mov     [rsp+58h+var_38], ebx
0x180028e89  xor     r8d, r8d; int
0x180028e8c  lea     rdx, aWdcgetclipboar; "WdcGetClipboardString"
0x180028e93  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180028e9a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028e9f  jmp     loc_180028FD0
0x180028ea4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180028ea8  jnz     short loc_180028E2E
0x180028eaa  call    cs:__imp_GetLastError
0x180028eb0  mov     ebx, eax
0x180028eb2  test    eax, eax
0x180028eb4  jz      short loc_180028EC7
0x180028eb6  jle     short loc_180028EBD
0x180028eb8  movzx   ebx, ax
0x180028ebb  or      ebx, ebp
0x180028ebd  test    ebx, ebx
0x180028ebf  jns     loc_180028E2E
0x180028ec5  jmp     short loc_180028ECC
0x180028ec7  mov     ebx, 80004005h
0x180028ecc  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028ed3  mov     [rsp+58h+var_38], ebx
0x180028ed7  xor     r8d, r8d; int
0x180028eda  lea     rdx, aWdcgetclipboar; "WdcGetClipboardString"
0x180028ee1  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180028ee8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028eed  jmp     loc_180028FC0
0x180028ef2  mov     r8, rax; unsigned __int16 *
0x180028ef5  mov     edx, 104h; unsigned __int64
0x180028efa  mov     rcx, rsi; unsigned __int16 *
0x180028efd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028f02  jmp     loc_180028F94
0x180028f07  mov     ebx, 1
0x180028f0c  mov     ecx, ebx; format
0x180028f0e  call    cs:__imp_IsClipboardFormatAvailable
0x180028f14  test    eax, eax
0x180028f16  jz      loc_180028FCB
0x180028f1c  mov     ecx, ebx; uFormat
0x180028f1e  call    cs:__imp_GetClipboardData
0x180028f24  mov     rdi, rax
0x180028f27  test    rax, rax
0x180028f2a  jnz     short loc_180028F4C
0x180028f2c  call    cs:__imp_GetLastError
0x180028f32  mov     ebx, eax
0x180028f34  test    eax, eax
0x180028f36  jz      loc_180028E79
0x180028f3c  jle     short loc_180028F43
0x180028f3e  movzx   ebx, ax
0x180028f41  or      ebx, ebp
0x180028f43  test    ebx, ebx
0x180028f45  jns     short loc_180028F71
0x180028f47  jmp     loc_180028E7E
0x180028f4c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180028f50  jnz     short loc_180028F71
0x180028f52  call    cs:__imp_GetLastError
0x180028f58  mov     ebx, eax
0x180028f5a  test    eax, eax
0x180028f5c  jz      loc_180028EC7
0x180028f62  jle     short loc_180028F69
0x180028f64  movzx   ebx, ax
0x180028f67  or      ebx, ebp
0x180028f69  test    ebx, ebx
0x180028f6b  js      loc_180028ECC
0x180028f71  mov     rcx, rdi; hMem
0x180028f74  call    cs:__imp_GlobalLock
0x180028f7a  test    rax, rax
0x180028f7d  jz      loc_180028E40
0x180028f83  mov     r8d, 104h; unsigned __int64
0x180028f89  mov     rdx, rsi; unsigned __int16 *
0x180028f8c  mov     rcx, rax; char *
0x180028f8f  call    ?WdcMbToUnicode@@YAJPEBDPEAG_K@Z; WdcMbToUnicode(char const *,ushort *,unsigned __int64)
0x180028f94  mov     ebx, eax
0x180028f96  test    eax, eax
0x180028f98  jns     short loc_180028FBB
0x180028f9a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180028fa1  mov     [rsp+58h+var_38], eax
0x180028fa5  xor     r8d, r8d; int
0x180028fa8  lea     rdx, aWdcgetclipboar; "WdcGetClipboardString"
0x180028faf  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x180028fb6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028fbb  test    rdi, rdi
0x180028fbe  jz      short loc_180028FD0
0x180028fc0  mov     rcx, rdi; hMem
0x180028fc3  call    cs:__imp_GlobalUnlock
0x180028fc9  jmp     short loc_180028FD0
0x180028fcb  mov     ebx, 80004005h
0x180028fd0  call    cs:__imp_CloseClipboard
0x180028fd6  mov     eax, ebx
0x180028fd8  add     rsp, 38h
0x180028fdc  pop     rdi
0x180028fdd  pop     rsi
0x180028fde  pop     rbp
0x180028fdf  pop     rbx
0x180028fe0  retn
```
