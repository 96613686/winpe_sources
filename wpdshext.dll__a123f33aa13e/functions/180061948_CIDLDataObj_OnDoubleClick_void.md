# CIDLDataObj::_OnDoubleClick(void)

- ea: `0x180061948`
- end: `0x180061c14`
- name: `?_OnDoubleClick@CIDLDataObj@@AEAAJXZ`
- size: `716`
- prototype: `__int64 __fastcall(CIDLDataObj *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x1800223b0`

## callees

- `0x180004110`
- `0x180024aa4`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180061948`
- `0x180061fe4`
- `0x180062e70`
- `0x180075530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180061a63`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180061ab6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180061a63`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180061ab6`
- `KERNEL32!SetFileAttributesW` at `0x180061af9`
- `KERNEL32!SetFileAttributesW` at `0x180061af9`
- `ole32!PropVariantClear` at `0x180061bc2`
- `ole32!PropVariantClear` at `0x180061bc2`
- `SHELL32!ShellExecuteExW` at `0x180061b4b`
- `SHELL32!ShellExecuteExW` at `0x180061b7e`
- `SHELL32!ShellExecuteExW` at `0x180061b4b`
- `SHELL32!ShellExecuteExW` at `0x180061b7e`

## string_xrefs

- `0x180061b5c`: `openas`

## pseudocode

```c
__int64 __fastcall CIDLDataObj::_OnDoubleClick(CIDLDataObj *this)
{
  int v2; // ebx
  int Blob; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  wchar_t *v6; // rax
  wchar_t *v7; // rax
  wchar_t *Context; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  PROPVARIANT pvar; // [rsp+50h] [rbp-B0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v14[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v15; // [rsp+F0h] [rbp-10h]
  WCHAR FileName[2080]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v17[2080]; // [rsp+1140h] [rbp+1040h] BYREF
  wchar_t String[2080]; // [rsp+2180h] [rbp+2080h] BYREF

  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v11 = 0;
  Context = 0;
  v15 = 0;
  v10 = 0;
  *(_OWORD *)v14 = 0;
  memset_0(String, 0, sizeof(String));
  memset_0(v17, 0, sizeof(v17));
  memset_0(FileName, 0, sizeof(FileName));
  memset(&pvar, 0, sizeof(pvar));
  if ( DataObj_GetHIDA(this, &v10) )
  {
    Blob = DataObj_GetBlob(this, g_cfDOUBLECLICK_FILES, String, 4160);
    v2 = Blob;
    if ( Blob >= 0 )
    {
      v6 = wcstok_s(String, L"*", &Context);
      if ( !v6 || (Blob = StringCchCopyW(v17, 0x820u, v6), v2 = Blob, Blob >= 0) )
      {
        while ( 1 )
        {
          v7 = wcstok_s(0, L"*", &Context);
          if ( !v7 )
            goto LABEL_20;
          Blob = StringCchPrintfW(FileName, 0x820u, L"%s%s", v17, v7);
          v2 = Blob;
          if ( Blob < 0 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v5 = 30;
              goto LABEL_19;
            }
            goto LABEL_20;
          }
          SetFileAttributesW(FileName, 1u);
          pExecInfo.cbSize = 112;
          pExecInfo.lpVerb = v14;
          pExecInfo.fMask = 1280;
          pExecInfo.lpFile = FileName;
          pExecInfo.nShow = 1;
          pExecInfo.lpDirectory = v17;
          StringCchCopyW(v14, 0xAu, L"open");
          ShellExecuteExW(&pExecInfo);
          if ( pExecInfo.hInstApp == (HINSTANCE)31 )
          {
            pExecInfo.fMask = 256;
            StringCchCopyW(v14, 0xAu, L"openas");
            ShellExecuteExW(&pExecInfo);
          }
        }
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_20:
        ReleaseStgMediumHGLOBAL(v4, &v10);
        goto LABEL_21;
      }
      v5 = 29;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_20;
      v5 = 28;
    }
LABEL_19:
    WPP_SF_d(v4[2], v5, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, (unsigned int)Blob);
    goto LABEL_20;
  }
  v2 = -2147024809;
LABEL_21:
  PropVariantClear(&pvar);
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180061948  push    rbp
0x18006194a  push    rbx
0x18006194b  push    rsi
0x18006194c  push    r15
0x18006194e  lea     rbp, [rsp-30D8h]
0x180061956  mov     eax, 31D8h
0x18006195b  call    _alloca_probe
0x180061960  sub     rsp, rax
0x180061963  mov     rax, cs:__security_cookie
0x18006196a  xor     rax, rsp
0x18006196d  mov     [rbp+30F0h+var_30], rax
0x180061974  xor     edx, edx; Val
0x180061976  mov     rbx, rcx
0x180061979  lea     rcx, [rsp+31F0h+pExecInfo]; void *
0x18006197e  lea     r8d, [rdx+70h]; Size
0x180061982  call    memset_0
0x180061987  xor     eax, eax
0x180061989  lea     rcx, [rbp+30F0h+String]; void *
0x180061990  xorps   xmm0, xmm0
0x180061993  mov     [rsp+31F0h+var_31A8], rax
0x180061998  mov     r15d, 1040h
0x18006199e  mov     [rsp+31F0h+Context], rax
0x1800619a3  mov     r8d, r15d; Size
0x1800619a6  mov     [rbp+30F0h+var_3100], eax
0x1800619a9  xor     edx, edx; Val
0x1800619ab  movups  [rsp+31F0h+var_31B8], xmm0
0x1800619b0  movups  xmmword ptr [rbp+30F0h+var_3110], xmm0
0x1800619b4  call    memset_0
0x1800619b9  mov     r8d, r15d; Size
0x1800619bc  lea     rcx, [rbp+30F0h+var_20B0]; void *
0x1800619c3  xor     edx, edx; Val
0x1800619c5  call    memset_0
0x1800619ca  mov     r8d, r15d; Size
0x1800619cd  lea     rcx, [rbp+30F0h+FileName]; void *
0x1800619d1  xor     edx, edx; Val
0x1800619d3  call    memset_0
0x1800619d8  xorps   xmm0, xmm0
0x1800619db  lea     rdx, [rsp+31F0h+var_31B8]
0x1800619e0  xor     eax, eax
0x1800619e2  mov     rcx, rbx
0x1800619e5  movups  xmmword ptr [rsp+31F0h+pvar], xmm0
0x1800619ea  mov     qword ptr [rsp+31F0h+pvar+10h], rax
0x1800619ef  call    DataObj_GetHIDA
0x1800619f4  lea     rsi, WPP_GLOBAL_Control
0x1800619fb  test    rax, rax
0x1800619fe  jnz     short loc_180061A0A
0x180061a00  mov     ebx, 80070057h
0x180061a05  jmp     loc_180061BBD
0x180061a0a  movzx   edx, cs:?g_cfDOUBLECLICK_FILES@@3GA; ushort g_cfDOUBLECLICK_FILES
0x180061a11  lea     r8, [rbp+30F0h+String]
0x180061a18  mov     r9d, r15d
0x180061a1b  mov     rcx, rbx
0x180061a1e  call    DataObj_GetBlob
0x180061a23  mov     ebx, eax
0x180061a25  test    eax, eax
0x180061a27  jns     short loc_180061A4D
0x180061a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a30  cmp     rcx, rsi
0x180061a33  jz      loc_180061BB3
0x180061a39  test    byte ptr [rcx+1Ch], 2
0x180061a3d  jz      loc_180061BB3
0x180061a43  mov     edx, 1Ch
0x180061a48  jmp     loc_180061BA0
0x180061a4d  lea     r15, Delimiter; "*"
0x180061a54  mov     rdx, r15; Delimiter
0x180061a57  lea     r8, [rsp+31F0h+Context]; Context
0x180061a5c  lea     rcx, [rbp+30F0h+String]; String
0x180061a63  call    cs:__imp_wcstok_s
0x180061a69  test    rax, rax
0x180061a6c  jz      short loc_180061AAC
0x180061a6e  mov     r8, rax; unsigned __int16 *
0x180061a71  lea     rcx, [rbp+30F0h+var_20B0]; unsigned __int16 *
0x180061a78  mov     edx, 820h; unsigned __int64
0x180061a7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061a82  mov     ebx, eax
0x180061a84  test    eax, eax
0x180061a86  jns     short loc_180061AAC
0x180061a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a8f  cmp     rcx, rsi
0x180061a92  jz      loc_180061BB3
0x180061a98  test    byte ptr [rcx+1Ch], 2
0x180061a9c  jz      loc_180061BB3
0x180061aa2  mov     edx, 1Dh
0x180061aa7  jmp     loc_180061BA0
0x180061aac  lea     r8, [rsp+31F0h+Context]; Context
0x180061ab1  mov     rdx, r15; Delimiter
0x180061ab4  xor     ecx, ecx; String
0x180061ab6  call    cs:__imp_wcstok_s
0x180061abc  test    rax, rax
0x180061abf  jz      loc_180061BB3
0x180061ac5  lea     r9, [rbp+30F0h+var_20B0]
0x180061acc  mov     [rsp+31F0h+var_31D0], rax
0x180061ad1  lea     r8, aSS_0; "%s%s"
0x180061ad8  mov     edx, 820h; unsigned __int64
0x180061add  lea     rcx, [rbp+30F0h+FileName]; unsigned __int16 *
0x180061ae1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061ae6  mov     ebx, eax
0x180061ae8  test    eax, eax
0x180061aea  js      loc_180061B89
0x180061af0  mov     edx, 1; dwFileAttributes
0x180061af5  lea     rcx, [rbp+30F0h+FileName]; lpFileName
0x180061af9  call    cs:__imp_SetFileAttributesW
0x180061aff  lea     rax, [rbp+30F0h+var_3110]
0x180061b03  mov     [rsp+31F0h+pExecInfo.cbSize], 70h ; 'p'
0x180061b0b  mov     [rbp+30F0h+pExecInfo.lpVerb], rax
0x180061b0f  lea     r8, aOpen; "open"
0x180061b16  lea     rax, [rbp+30F0h+FileName]
0x180061b1a  mov     [rsp+31F0h+pExecInfo.fMask], 500h
0x180061b22  mov     [rbp+30F0h+pExecInfo.lpFile], rax
0x180061b26  lea     rcx, [rbp+30F0h+var_3110]; unsigned __int16 *
0x180061b2a  lea     rax, [rbp+30F0h+var_20B0]
0x180061b31  mov     [rbp+30F0h+pExecInfo.nShow], 1
0x180061b38  mov     edx, 0Ah; unsigned __int64
0x180061b3d  mov     [rbp+30F0h+pExecInfo.lpDirectory], rax
0x180061b41  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061b46  lea     rcx, [rsp+31F0h+pExecInfo]; pExecInfo
0x180061b4b  call    cs:__imp_ShellExecuteExW
0x180061b51  cmp     [rbp+30F0h+pExecInfo.hInstApp], 1Fh
0x180061b56  jnz     loc_180061AAC
0x180061b5c  lea     r8, aOpenas; "openas"
0x180061b63  mov     [rsp+31F0h+pExecInfo.fMask], 100h
0x180061b6b  mov     edx, 0Ah; unsigned __int64
0x180061b70  lea     rcx, [rbp+30F0h+var_3110]; unsigned __int16 *
0x180061b74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061b79  lea     rcx, [rsp+31F0h+pExecInfo]; pExecInfo
0x180061b7e  call    cs:__imp_ShellExecuteExW
0x180061b84  jmp     loc_180061AAC
0x180061b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b90  cmp     rcx, rsi
0x180061b93  jz      short loc_180061BB3
0x180061b95  test    byte ptr [rcx+1Ch], 2
0x180061b99  jz      short loc_180061BB3
0x180061b9b  mov     edx, 1Eh
0x180061ba0  mov     rcx, [rcx+10h]
0x180061ba4  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180061bab  mov     r9d, eax
0x180061bae  call    WPP_SF_d
0x180061bb3  lea     rdx, [rsp+31F0h+var_31B8]
0x180061bb8  call    ReleaseStgMediumHGLOBAL
0x180061bbd  lea     rcx, [rsp+31F0h+pvar]; pvar
0x180061bc2  call    cs:__imp_PropVariantClear
0x180061bc8  test    ebx, ebx
0x180061bca  jns     short loc_180061BF6
0x180061bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bd3  cmp     rcx, rsi
0x180061bd6  jz      short loc_180061BF6
0x180061bd8  test    byte ptr [rcx+1Ch], 2
0x180061bdc  jz      short loc_180061BF6
0x180061bde  mov     rcx, [rcx+10h]
0x180061be2  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180061be9  mov     edx, 1Fh
0x180061bee  mov     r9d, ebx
0x180061bf1  call    WPP_SF_d
0x180061bf6  mov     eax, ebx
0x180061bf8  mov     rcx, [rbp+30F0h+var_30]
0x180061bff  xor     rcx, rsp; StackCookie
0x180061c02  call    __security_check_cookie
0x180061c07  add     rsp, 31D8h
0x180061c0e  pop     r15
0x180061c10  pop     rsi
0x180061c11  pop     rbx
0x180061c12  pop     rbp
0x180061c13  retn
```
