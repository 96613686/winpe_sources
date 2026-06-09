# SdpCopyDirectory(ushort const *,ushort const *)

- ea: `0x180026958`
- end: `0x180026bee`
- name: `?SdpCopyDirectory@@YAJPEBG0@Z`
- size: `662`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000a86c`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180002978`
- `0x180026958`
- `0x180026fa0`
- `0x18002758c`
- `0x180029734`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026b3b`
- `KERNEL32!GetLastError` at `0x180026b3b`
- `KERNEL32!FindFirstFileW` at `0x180026a52`
- `KERNEL32!FindFirstFileW` at `0x180026a52`
- `KERNEL32!FindClose` at `0x180026bbb`
- `KERNEL32!FindClose` at `0x180026bbb`
- `KERNEL32!FindNextFileW` at `0x180026b5c`
- `KERNEL32!FindNextFileW` at `0x180026b5c`
- `KERNEL32!CopyFileW` at `0x180026b2d`
- `KERNEL32!CopyFileW` at `0x180026b2d`

## string_xrefs

- `0x1800269b3`: `SdpCopyDirectory`
- `0x180026b88`: `SdpCopyDirectory`

## pseudocode

```c
__int64 __fastcall SdpCopyDirectory(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rdi
  char *FirstFileW; // r14
  unsigned __int16 *v9; // rsi
  int v10; // r9d
  int v11; // r8d
  int v12; // eax
  int IsSubDirectory; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  signed int LastError; // eax
  int v18[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    v4 = 2050;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    v6 = v5;
    SdpDebugTrace(1u, L"SdpCopyDirectory", v4, v5);
    return v6;
  }
  if ( !a2 )
  {
    v4 = 2051;
    goto LABEL_3;
  }
  v7 = (unsigned __int16 *)operator new[](0x208u);
  if ( !v7 )
  {
    v5 = -2147024882;
    v4 = 2054;
    goto LABEL_4;
  }
  FirstFileW = 0;
  v9 = (unsigned __int16 *)operator new[](0x208u);
  if ( !v9 )
  {
    v10 = -2147024882;
    v11 = 2057;
    v6 = -2147024882;
    goto LABEL_33;
  }
  v12 = StringCchPrintfW(v7, 0x104u, L"%s\\*", a1);
  v6 = v12;
  if ( v12 < 0 )
  {
    v11 = 2060;
    goto LABEL_32;
  }
  FirstFileW = (char *)FindFirstFileW(v7, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v12 = StringCchPrintfW(v7, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
        v6 = v12;
        if ( v12 < 0 )
        {
          v11 = 2081;
LABEL_32:
          v10 = v12;
LABEL_33:
          SdpDebugTrace(1u, L"SdpCopyDirectory", v11, v10);
          break;
        }
        v12 = StringCchPrintfW(v9, 0x104u, L"%s\\%s", a2);
        v6 = v12;
        if ( v12 < 0 )
        {
          v11 = 2088;
          goto LABEL_32;
        }
        v18[0] = 0;
        IsSubDirectory = SdpIsSubDirectory(a1, v7, v18);
        if ( IsSubDirectory < 0 )
          goto LABEL_18;
        if ( !v18[0] )
          continue;
        v18[0] = 0;
        IsSubDirectory = SdpIsSubDirectory(a2, v9, v18);
        if ( IsSubDirectory < 0 )
        {
LABEL_18:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            v14,
            v15,
            (const char *)(unsigned int)IsSubDirectory,
            (int)FindFileData.cFileName);
        }
        else if ( v18[0] )
        {
          if ( CopyFileW(v7, v9, 1) )
          {
            v6 = 0;
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            if ( (v6 & 0x80000000) != 0 )
            {
              v10 = v6;
              v11 = 2097;
              goto LABEL_33;
            }
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  operator delete(v7);
  if ( v9 )
    operator delete(v9);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  return v6;
}

```

## disassembly

```asm
0x180026958  mov     [rsp-8+arg_10], rbx
0x18002695d  mov     [rsp-8+arg_18], rsi
0x180026962  push    rbp
0x180026963  push    rdi
0x180026964  push    r12
0x180026966  push    r14
0x180026968  push    r15
0x18002696a  lea     rbp, [rsp-1A0h]
0x180026972  sub     rsp, 2A0h
0x180026979  mov     rax, cs:__security_cookie
0x180026980  xor     rax, rsp
0x180026983  mov     [rbp+1C0h+var_30], rax
0x18002698a  mov     r12, rdx
0x18002698d  mov     r15, rcx
0x180026990  xor     edx, edx; Val
0x180026992  lea     rcx, [rsp+2C0h+FindFileData]; void *
0x180026997  mov     r8d, 250h; Size
0x18002699d  call    memset_0
0x1800269a2  test    r15, r15
0x1800269a5  jnz     short loc_1800269CC
0x1800269a7  mov     r8d, 802h; int
0x1800269ad  mov     r9d, 80070057h; int
0x1800269b3  lea     rdx, aSdpcopydirecto; "SdpCopyDirectory"
0x1800269ba  mov     ecx, 1; Level
0x1800269bf  mov     ebx, r9d
0x1800269c2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800269c7  jmp     loc_180026BC1
0x1800269cc  test    r12, r12
0x1800269cf  jnz     short loc_1800269D9
0x1800269d1  mov     r8d, 803h
0x1800269d7  jmp     short loc_1800269AD
0x1800269d9  mov     ebx, 208h
0x1800269de  mov     ecx, ebx; unsigned __int64
0x1800269e0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800269e5  mov     rdi, rax
0x1800269e8  test    rax, rax
0x1800269eb  jnz     short loc_1800269FB
0x1800269ed  mov     r9d, 8007000Eh
0x1800269f3  mov     r8d, 806h
0x1800269f9  jmp     short loc_1800269B3
0x1800269fb  mov     rcx, rbx; unsigned __int64
0x1800269fe  xor     r14d, r14d
0x180026a01  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026a06  mov     rsi, rax
0x180026a09  test    rax, rax
0x180026a0c  jnz     short loc_180026A22
0x180026a0e  mov     r9d, 8007000Eh
0x180026a14  mov     r8d, 809h
0x180026a1a  mov     ebx, r9d
0x180026a1d  jmp     loc_180026B88
0x180026a22  mov     r9, r15
0x180026a25  lea     r8, aS; "%s\\*"
0x180026a2c  mov     edx, 104h; unsigned __int64
0x180026a31  mov     rcx, rdi; unsigned __int16 *
0x180026a34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026a39  mov     ebx, eax
0x180026a3b  test    eax, eax
0x180026a3d  jns     short loc_180026A4A
0x180026a3f  mov     r8d, 80Ch
0x180026a45  jmp     loc_180026B85
0x180026a4a  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x180026a4f  mov     rcx, rdi; lpFileName
0x180026a52  call    cs:__imp_FindFirstFileW
0x180026a58  mov     r14, rax
0x180026a5b  lea     rcx, [rax-1]
0x180026a5f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180026a63  ja      loc_180026B99
0x180026a69  test    byte ptr [rsp+2C0h+FindFileData.dwFileAttributes], 10h
0x180026a6e  jnz     loc_180026B54
0x180026a74  lea     rax, [rsp+2C0h+FindFileData.cFileName]
0x180026a79  mov     r9, r15
0x180026a7c  lea     r8, aSS; "%s\\%s"
0x180026a83  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180026a88  mov     edx, 104h; unsigned __int64
0x180026a8d  mov     rcx, rdi; unsigned __int16 *
0x180026a90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026a95  mov     ebx, eax
0x180026a97  test    eax, eax
0x180026a99  js      loc_180026B7F
0x180026a9f  lea     rax, [rsp+2C0h+FindFileData.cFileName]
0x180026aa4  mov     r9, r12
0x180026aa7  lea     r8, aSS; "%s\\%s"
0x180026aae  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x180026ab3  mov     edx, 104h; unsigned __int64
0x180026ab8  mov     rcx, rsi; unsigned __int16 *
0x180026abb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ac0  mov     ebx, eax
0x180026ac2  test    eax, eax
0x180026ac4  js      loc_180026B77
0x180026aca  lea     r8, [rsp+2C0h+var_290]; int *
0x180026acf  mov     [rsp+2C0h+var_290], 0
0x180026ad7  mov     rdx, rdi; unsigned __int16 *
0x180026ada  mov     rcx, r15; unsigned __int16 *
0x180026add  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x180026ae2  test    eax, eax
0x180026ae4  jns     short loc_180026AF7
0x180026ae6  mov     rcx, [rbp+1C8h]; this
0x180026aed  mov     r9d, eax; char *
0x180026af0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026af5  jmp     short loc_180026B54
0x180026af7  cmp     [rsp+2C0h+var_290], 0
0x180026afc  jz      short loc_180026B54
0x180026afe  lea     r8, [rsp+2C0h+var_290]; int *
0x180026b03  mov     [rsp+2C0h+var_290], 0
0x180026b0b  mov     rdx, rsi; unsigned __int16 *
0x180026b0e  mov     rcx, r12; unsigned __int16 *
0x180026b11  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x180026b16  test    eax, eax
0x180026b18  js      short loc_180026AE6
0x180026b1a  cmp     [rsp+2C0h+var_290], 0
0x180026b1f  jz      short loc_180026B54
0x180026b21  mov     r8d, 1; bFailIfExists
0x180026b27  mov     rdx, rsi; lpNewFileName
0x180026b2a  mov     rcx, rdi; lpExistingFileName
0x180026b2d  call    cs:__imp_CopyFileW
0x180026b33  test    eax, eax
0x180026b35  jz      short loc_180026B3B
0x180026b37  xor     ebx, ebx
0x180026b39  jmp     short loc_180026B54
0x180026b3b  call    cs:__imp_GetLastError
0x180026b41  mov     ebx, eax
0x180026b43  test    eax, eax
0x180026b45  jle     short loc_180026B50
0x180026b47  movzx   ebx, ax
0x180026b4a  or      ebx, 80070000h
0x180026b50  test    ebx, ebx
0x180026b52  js      short loc_180026B6C
0x180026b54  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x180026b59  mov     rcx, r14; hFindFile
0x180026b5c  call    cs:__imp_FindNextFileW
0x180026b62  test    eax, eax
0x180026b64  jnz     loc_180026A69
0x180026b6a  jmp     short loc_180026B99
0x180026b6c  mov     r9d, ebx
0x180026b6f  mov     r8d, 831h
0x180026b75  jmp     short loc_180026B88
0x180026b77  mov     r8d, 828h
0x180026b7d  jmp     short loc_180026B85
0x180026b7f  mov     r8d, 821h; int
0x180026b85  mov     r9d, eax; int
0x180026b88  lea     rdx, aSdpcopydirecto; "SdpCopyDirectory"
0x180026b8f  mov     ecx, 1; Level
0x180026b94  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026b99  mov     rcx, rdi; Block
0x180026b9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ba1  test    rsi, rsi
0x180026ba4  jz      short loc_180026BAE
0x180026ba6  mov     rcx, rsi; Block
0x180026ba9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026bae  lea     rax, [r14-1]
0x180026bb2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026bb6  ja      short loc_180026BC1
0x180026bb8  mov     rcx, r14; hFindFile
0x180026bbb  call    cs:__imp_FindClose
0x180026bc1  mov     eax, ebx
0x180026bc3  mov     rcx, [rbp+1C0h+var_30]
0x180026bca  xor     rcx, rsp; StackCookie
0x180026bcd  call    __security_check_cookie
0x180026bd2  lea     r11, [rsp+2C0h+var_20]
0x180026bda  mov     rbx, [r11+40h]
0x180026bde  mov     rsi, [r11+48h]
0x180026be2  mov     rsp, r11
0x180026be5  pop     r15
0x180026be7  pop     r14
0x180026be9  pop     r12
0x180026beb  pop     rdi
0x180026bec  pop     rbp
0x180026bed  retn
```
