# SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18002bee4`
- end: `0x18002c084`
- name: `?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c08c`

## callees

- `0x180020710`
- `0x180020908`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002bee4`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18002c011`
- `KERNEL32!SetFileAttributesW` at `0x18002c011`
- `KERNEL32!CreateDirectoryW` at `0x18002bf4d`
- `KERNEL32!CreateDirectoryW` at `0x18002bf4d`
- `KERNEL32!GetLastError` at `0x18002bf5b`
- `KERNEL32!GetLastError` at `0x18002bf5b`

## string_xrefs

- `0x18002bf30`: `SxCreateDirectory`
- `0x18002c04a`: `::SetFileAttributesW( wszDirectoryName, FILE_ATTRIBUTE_NOT_CONTENT_INDEXED | FILE_ATTRIBUTE_HIDDEN | FILE_ATTRIBUTE_SYSTEM )`

## pseudocode

```c
__int64 __fastcall SxCreateDirectory(LPCWSTR lpFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  signed int LastFailureAsHRESULT; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  const char *v10; // r9
  __int64 v11; // rcx
  signed int v13; // [rsp+30h] [rbp-48h] BYREF
  __int16 v14; // [rsp+34h] [rbp-44h]
  __int16 v15; // [rsp+36h] [rbp-42h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxCreateDirectory", 1621, 1);
  if ( CreateDirectoryW(lpFileName, lpSecurityAttributes) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, lpFileName);
  }
  else
  {
    LastError = GetLastError();
    LastFailureAsHRESULT = 0;
    if ( LastError != 183 )
      LastFailureAsHRESULT = LastError;
    if ( LastFailureAsHRESULT > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
    v13 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v15 = 1637;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        v9 = 47;
        v10 = "dwErr";
LABEL_13:
        WPP_SF_sSd(
          v8[2],
          v9,
          (unsigned int)&WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
          (_DWORD)v10,
          (__int64)lpFileName,
          LastFailureAsHRESULT);
        LastFailureAsHRESULT = v13;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v14 = 1637;
  }
  if ( SetFileAttributesW(lpFileName, 0x2006u) )
  {
    LastFailureAsHRESULT = 0;
    v13 = 0;
    v14 = 1651;
    goto LABEL_23;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
  v13 = LastFailureAsHRESULT;
  v15 = 1651;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v9 = 49;
    v10 = "::SetFileAttributesW( wszDirectoryName, FILE_ATTRIBUTE_NOT_CONTENT_INDEXED | FILE_ATTRIBUTE_HIDDEN | FILE_ATTRIBUTE_SYSTEM )";
    goto LABEL_13;
  }
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v5, v6);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002bee4  mov     [rsp+arg_0], rbx
0x18002bee9  mov     [rsp+arg_8], rsi
0x18002beee  push    rdi
0x18002beef  sub     rsp, 70h
0x18002bef3  mov     rbx, rdx
0x18002bef6  mov     rdi, rcx
0x18002bef9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf00  lea     rsi, WPP_GLOBAL_Control
0x18002bf07  cmp     rcx, rsi
0x18002bf0a  jz      short loc_18002BF2A
0x18002bf0c  test    dword ptr [rcx+1Ch], 20000000h
0x18002bf13  jz      short loc_18002BF2A
0x18002bf15  mov     rcx, [rcx+10h]
0x18002bf19  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002bf20  mov     edx, 2Eh ; '.'
0x18002bf25  call    WPP_SF_
0x18002bf2a  mov     r9d, 1; unsigned __int16
0x18002bf30  lea     rdx, aSxcreatedirect_0; "SxCreateDirectory"
0x18002bf37  mov     r8d, 655h; unsigned __int16
0x18002bf3d  lea     rcx, [rsp+78h+var_48]; this
0x18002bf42  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002bf47  mov     rdx, rbx; lpSecurityAttributes
0x18002bf4a  mov     rcx, rdi; lpPathName
0x18002bf4d  call    cs:__imp_CreateDirectoryW
0x18002bf53  test    eax, eax
0x18002bf55  jnz     loc_18002BFDC
0x18002bf5b  call    cs:__imp_GetLastError
0x18002bf61  xor     ebx, ebx
0x18002bf63  cmp     eax, 0B7h
0x18002bf68  cmovnz  ebx, eax
0x18002bf6b  test    ebx, ebx
0x18002bf6d  jle     short loc_18002BF78
0x18002bf6f  movzx   ebx, bx
0x18002bf72  or      ebx, 80070000h
0x18002bf78  mov     [rsp+78h+var_48], ebx
0x18002bf7c  mov     eax, 665h
0x18002bf81  test    ebx, ebx
0x18002bf83  jns     short loc_18002BFD5
0x18002bf85  mov     [rsp+78h+var_42], ax
0x18002bf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf91  cmp     rcx, rsi
0x18002bf94  jz      loc_18002C066
0x18002bf9a  test    dword ptr [rcx+1Ch], 2000000h
0x18002bfa1  jz      loc_18002C066
0x18002bfa7  mov     edx, 2Fh ; '/'
0x18002bfac  lea     r9, aDwerr; "dwErr"
0x18002bfb3  mov     rcx, [rcx+10h]
0x18002bfb7  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002bfbe  mov     [rsp+78h+var_50], ebx
0x18002bfc2  mov     [rsp+78h+var_58], rdi
0x18002bfc7  call    WPP_SF_sSd
0x18002bfcc  mov     ebx, [rsp+78h+var_48]
0x18002bfd0  jmp     loc_18002C066
0x18002bfd5  mov     [rsp+78h+var_44], ax
0x18002bfda  jmp     short loc_18002C009
0x18002bfdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfe3  cmp     rcx, rsi
0x18002bfe6  jz      short loc_18002C009
0x18002bfe8  test    dword ptr [rcx+1Ch], 8000000h
0x18002bfef  jz      short loc_18002C009
0x18002bff1  mov     rcx, [rcx+10h]
0x18002bff5  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002bffc  mov     edx, 30h ; '0'
0x18002c001  mov     r9, rdi
0x18002c004  call    WPP_SF_S
0x18002c009  mov     edx, 2006h; dwFileAttributes
0x18002c00e  mov     rcx, rdi; lpFileName
0x18002c011  call    cs:__imp_SetFileAttributesW
0x18002c017  test    eax, eax
0x18002c019  jnz     short loc_18002C056
0x18002c01b  call    GetLastFailureAsHRESULT
0x18002c020  mov     ebx, eax
0x18002c022  mov     [rsp+78h+var_48], eax
0x18002c026  mov     eax, 673h
0x18002c02b  mov     [rsp+78h+var_42], ax
0x18002c030  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c037  cmp     rcx, rsi
0x18002c03a  jz      short loc_18002C066
0x18002c03c  test    dword ptr [rcx+1Ch], 2000000h
0x18002c043  jz      short loc_18002C066
0x18002c045  mov     edx, 31h ; '1'
0x18002c04a  lea     r9, aSetfileattribu; "::SetFileAttributesW( wszDirectoryName,"...
0x18002c051  jmp     loc_18002BFB3
0x18002c056  xor     ebx, ebx
0x18002c058  mov     eax, 673h
0x18002c05d  mov     [rsp+78h+var_48], ebx
0x18002c061  mov     [rsp+78h+var_44], ax
0x18002c066  lea     rcx, [rsp+78h+var_48]; this
0x18002c06b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002c070  lea     r11, [rsp+78h+var_8]
0x18002c075  mov     eax, ebx
0x18002c077  mov     rbx, [r11+10h]
0x18002c07b  mov     rsi, [r11+18h]
0x18002c07f  mov     rsp, r11
0x18002c082  pop     rdi
0x18002c083  retn
```
