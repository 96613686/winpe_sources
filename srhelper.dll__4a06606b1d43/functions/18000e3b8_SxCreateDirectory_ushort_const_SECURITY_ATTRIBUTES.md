# SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000e3b8`
- end: `0x18000e54e`
- name: `?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bdd0`
- `0x18000bf70`
- `0x18000e554`

## callees

- `0x180003ce0`
- `0x180003e5c`
- `0x18000ceb4`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e3b8`
- `0x18000f154`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e425`
- `KERNEL32!GetLastError` at `0x18000e425`
- `KERNEL32!CreateDirectoryW` at `0x18000e417`
- `KERNEL32!CreateDirectoryW` at `0x18000e417`
- `KERNEL32!SetFileAttributesW` at `0x18000e4db`
- `KERNEL32!SetFileAttributesW` at `0x18000e4db`

## string_xrefs

- `0x18000e401`: `SxCreateDirectory`
- `0x18000e514`: `::SetFileAttributesW( wszDirectoryName, FILE_ATTRIBUTE_NOT_CONTENT_INDEXED | FILE_ATTRIBUTE_HIDDEN | FILE_ATTRIBUTE_SYSTEM )`

## pseudocode

```c
__int64 __fastcall SxCreateDirectory(LPCWSTR lpFileName, struct _SECURITY_ATTRIBUTES *a2)
{
  DWORD LastError; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  signed int LastFailureAsHRESULT; // ebx
  _QWORD *v7; // rcx
  int v8; // edx
  const char *v9; // r9
  signed int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "SxCreateDirectory", 1621);
  if ( CreateDirectoryW(lpFileName, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, lpFileName);
  }
  else
  {
    LastError = GetLastError();
    LastFailureAsHRESULT = 0;
    if ( LastError != 183 )
      LastFailureAsHRESULT = LastError;
    if ( LastFailureAsHRESULT > 0 )
      LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
    v11 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v13 = 1637;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        v8 = 47;
        v9 = "dwErr";
LABEL_13:
        WPP_SF_sSd(
          v7[2],
          v8,
          (unsigned int)WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
          (_DWORD)v9,
          (__int64)lpFileName,
          LastFailureAsHRESULT);
        LastFailureAsHRESULT = v11;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    v12 = 1637;
  }
  if ( SetFileAttributesW(lpFileName, 0x2006u) )
  {
    LastFailureAsHRESULT = 0;
    v11 = 0;
    v12 = 1651;
    goto LABEL_23;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  v11 = LastFailureAsHRESULT;
  v13 = 1651;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v8 = 49;
    v9 = "::SetFileAttributesW( wszDirectoryName, FILE_ATTRIBUTE_NOT_CONTENT_INDEXED | FILE_ATTRIBUTE_HIDDEN | FILE_ATTRIBUTE_SYSTEM )";
    goto LABEL_13;
  }
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11, v4, v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000e3b8  mov     [rsp+arg_0], rbx
0x18000e3bd  mov     [rsp+arg_8], rsi
0x18000e3c2  push    rdi
0x18000e3c3  sub     rsp, 70h
0x18000e3c7  mov     rdi, rcx
0x18000e3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3d1  lea     rsi, WPP_GLOBAL_Control
0x18000e3d8  cmp     rcx, rsi
0x18000e3db  jz      short loc_18000E3FB
0x18000e3dd  test    dword ptr [rcx+1Ch], 20000000h
0x18000e3e4  jz      short loc_18000E3FB
0x18000e3e6  mov     rcx, [rcx+10h]
0x18000e3ea  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000e3f1  mov     edx, 2Eh ; '.'
0x18000e3f6  call    WPP_SF_
0x18000e3fb  mov     r8d, 655h; unsigned __int16
0x18000e401  lea     rdx, aSxcreatedirect_0; "SxCreateDirectory"
0x18000e408  lea     rcx, [rsp+78h+var_48]; this
0x18000e40d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e412  xor     edx, edx; lpSecurityAttributes
0x18000e414  mov     rcx, rdi; lpPathName
0x18000e417  call    cs:__imp_CreateDirectoryW
0x18000e41d  test    eax, eax
0x18000e41f  jnz     loc_18000E4A6
0x18000e425  call    cs:__imp_GetLastError
0x18000e42b  xor     ebx, ebx
0x18000e42d  cmp     eax, 0B7h
0x18000e432  cmovnz  ebx, eax
0x18000e435  test    ebx, ebx
0x18000e437  jle     short loc_18000E442
0x18000e439  movzx   ebx, bx
0x18000e43c  or      ebx, 80070000h
0x18000e442  mov     [rsp+78h+var_48], ebx
0x18000e446  mov     eax, 665h
0x18000e44b  test    ebx, ebx
0x18000e44d  jns     short loc_18000E49F
0x18000e44f  mov     [rsp+78h+var_42], ax
0x18000e454  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e45b  cmp     rcx, rsi
0x18000e45e  jz      loc_18000E530
0x18000e464  test    dword ptr [rcx+1Ch], 2000000h
0x18000e46b  jz      loc_18000E530
0x18000e471  mov     edx, 2Fh ; '/'
0x18000e476  lea     r9, aDwerr; "dwErr"
0x18000e47d  mov     rcx, [rcx+10h]
0x18000e481  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000e488  mov     [rsp+78h+var_50], ebx
0x18000e48c  mov     [rsp+78h+var_58], rdi
0x18000e491  call    WPP_SF_sSd
0x18000e496  mov     ebx, [rsp+78h+var_48]
0x18000e49a  jmp     loc_18000E530
0x18000e49f  mov     [rsp+78h+var_44], ax
0x18000e4a4  jmp     short loc_18000E4D3
0x18000e4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4ad  cmp     rcx, rsi
0x18000e4b0  jz      short loc_18000E4D3
0x18000e4b2  test    dword ptr [rcx+1Ch], 8000000h
0x18000e4b9  jz      short loc_18000E4D3
0x18000e4bb  mov     rcx, [rcx+10h]
0x18000e4bf  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000e4c6  mov     edx, 30h ; '0'
0x18000e4cb  mov     r9, rdi
0x18000e4ce  call    WPP_SF_S
0x18000e4d3  mov     edx, 2006h; dwFileAttributes
0x18000e4d8  mov     rcx, rdi; lpFileName
0x18000e4db  call    cs:__imp_SetFileAttributesW
0x18000e4e1  test    eax, eax
0x18000e4e3  jnz     short loc_18000E520
0x18000e4e5  call    GetLastFailureAsHRESULT
0x18000e4ea  mov     ebx, eax
0x18000e4ec  mov     [rsp+78h+var_48], eax
0x18000e4f0  mov     eax, 673h
0x18000e4f5  mov     [rsp+78h+var_42], ax
0x18000e4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e501  cmp     rcx, rsi
0x18000e504  jz      short loc_18000E530
0x18000e506  test    dword ptr [rcx+1Ch], 2000000h
0x18000e50d  jz      short loc_18000E530
0x18000e50f  mov     edx, 31h ; '1'
0x18000e514  lea     r9, aSetfileattribu; "::SetFileAttributesW( wszDirectoryName,"...
0x18000e51b  jmp     loc_18000E47D
0x18000e520  xor     ebx, ebx
0x18000e522  mov     eax, 673h
0x18000e527  mov     [rsp+78h+var_48], ebx
0x18000e52b  mov     [rsp+78h+var_44], ax
0x18000e530  lea     rcx, [rsp+78h+var_48]; this
0x18000e535  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e53a  lea     r11, [rsp+78h+var_8]
0x18000e53f  mov     eax, ebx
0x18000e541  mov     rbx, [r11+10h]
0x18000e545  mov     rsi, [r11+18h]
0x18000e549  mov     rsp, r11
0x18000e54c  pop     rdi
0x18000e54d  retn
```
