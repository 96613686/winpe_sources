# FoundDebugger(ushort *,int)

- ea: `0x140094f68`
- end: `0x1400952cc`
- name: `?FoundDebugger@@YAHPEAGH@Z`
- size: `868`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400952f0`

## callees

- `0x1400057f4`
- `0x14000fb30`
- `0x14001a520`
- `0x140053720`
- `0x14005f3c4`
- `0x140094f68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14009504e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14009515a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14009504e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14009515a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400950fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140095072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400950fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140094fc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140094fc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140095002`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140095002`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400952a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009eb53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400952a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009eb53`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140095034`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400951e0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14009521a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140095277`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140095034`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1400951e0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14009521a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140095277`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009505c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009517a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400951f0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009522a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140095255`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140095287`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009505c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009517a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400951f0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14009522a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140095255`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140095287`

## string_xrefs

- `0x140095270`: `%SystemRoot%\System32\ntsd.exe`

## pseudocode

```c
_BOOL8 __fastcall FoundDebugger(unsigned __int16 *a1)
{
  BOOL v2; // ebx
  DWORD v3; // eax
  char v4; // al
  CUser *v5; // rax
  __int64 v6; // rdx
  BYTE *v7; // r9
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  DWORD v10; // eax
  DWORD Type; // [rsp+34h] [rbp-244h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  DWORD cbData[4]; // [rsp+40h] [rbp-238h] BYREF
  wchar_t Data[264]; // [rsp+50h] [rbp-228h] BYREF

  v2 = 0;
  hKey = 0;
  Type = 0;
  if ( !a1 )
    goto LABEL_38;
  *a1 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AeDebug",
          0,
          0x20019u,
          &hKey) )
  {
    cbData[0] = 520;
    if ( !RegQueryValueExW(hKey, L"BpidDebugger", 0, &Type, (LPBYTE)Data, cbData) )
    {
      if ( Type == 1 )
      {
        if ( wcsstr(Data, L"ntsd") )
        {
          StringCchCopyW(a1, 0x104u, Data);
          FileAttributesW = GetFileAttributesW(a1);
          v2 = FileAttributesW != -1;
          if ( FileAttributesW != -1 )
            goto LABEL_38;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v6 = 10;
        v7 = (BYTE *)Data;
      }
      else
      {
        if ( Type != 2 )
          goto LABEL_28;
        if ( !ExpandEnvironmentStringsW(Data, a1, 0x104u) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids,
              LastError);
          }
          goto LABEL_29;
        }
        if ( wcsstr(Data, L"ntsd") )
        {
          v3 = GetFileAttributesW(a1);
          LOBYTE(v2) = v3 != -1;
          if ( v3 != -1 )
            goto LABEL_38;
          v4 = GetLastError();
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              (unsigned int)WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids,
              (_DWORD)a1,
              v4);
          }
          goto LABEL_28;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_28:
          *a1 = 0;
          goto LABEL_29;
        }
        v6 = 12;
        v7 = (BYTE *)a1;
      }
      WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids, v7);
      goto LABEL_28;
    }
  }
LABEL_29:
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\Debuggers\\ntsd.exe", a1, 0x104u) <= 0x104 )
    v2 = GetFileAttributesW(a1) != -1;
  if ( !v2 )
  {
    if ( ExpandEnvironmentStringsW(L"%SystemDrive%\\Debuggers\\ntsd.exe", a1, 0x104u) <= 0x104 )
      LOBYTE(v2) = GetFileAttributesW(a1) != -1;
    if ( !v2 )
    {
      StringCchCopyW(a1, 0x104u, L"C:\\Debuggers\\ntsd.exe");
      v10 = GetFileAttributesW(a1);
      v2 = v10 != -1;
      if ( v10 == -1 && ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\ntsd.exe", a1, 0x104u) <= 0x104 )
        v2 = GetFileAttributesW(a1) != -1;
    }
  }
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140094f68  mov     [rsp+arg_8], rbx
0x140094f6d  push    rdi
0x140094f6e  sub     rsp, 270h
0x140094f75  mov     rax, cs:__security_cookie
0x140094f7c  xor     rax, rsp
0x140094f7f  mov     [rsp+278h+var_18], rax
0x140094f87  mov     rdi, rcx
0x140094f8a  xor     ebx, ebx
0x140094f8c  mov     [rsp+278h+hKey], rbx
0x140094f91  mov     [rsp+278h+Type], ebx
0x140094f95  test    rcx, rcx
0x140094f98  jz      loc_140095299
0x140094f9e  xor     eax, eax
0x140094fa0  mov     [rcx], ax
0x140094fa3  lea     rax, [rsp+278h+hKey]
0x140094fa8  mov     [rsp+278h+phkResult], rax; phkResult
0x140094fad  mov     r9d, 20019h; samDesired
0x140094fb3  xor     r8d, r8d; ulOptions
0x140094fb6  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\Windows NT\\Curren"...
0x140094fbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140094fc4  call    cs:__imp_RegOpenKeyExW
0x140094fca  test    eax, eax
0x140094fcc  jnz     loc_1400951D0
0x140094fd2  mov     [rsp+278h+cbData], 208h
0x140094fda  lea     rax, [rsp+278h+cbData]
0x140094fdf  mov     [rsp+278h+lpcbData], rax; lpcbData
0x140094fe4  lea     rax, [rsp+278h+Data]
0x140094fe9  mov     [rsp+278h+phkResult], rax; lpData
0x140094fee  lea     r9, [rsp+278h+Type]; lpType
0x140094ff3  xor     r8d, r8d; lpReserved
0x140094ff6  lea     rdx, aBpiddebugger; "BpidDebugger"
0x140094ffd  mov     rcx, [rsp+278h+hKey]; hKey
0x140095002  call    cs:__imp_RegQueryValueExW
0x140095008  test    eax, eax
0x14009500a  jnz     loc_1400951D0
0x140095010  mov     eax, [rsp+278h+Type]
0x140095014  sub     eax, 1
0x140095017  jz      loc_14009514E
0x14009501d  cmp     eax, 1
0x140095020  jnz     loc_1400951CB
0x140095026  mov     r8d, 104h; nSize
0x14009502c  mov     rdx, rdi; lpDst
0x14009502f  lea     rcx, [rsp+278h+Data]; lpSrc
0x140095034  call    cs:__imp_ExpandEnvironmentStringsW
0x14009503a  test    eax, eax
0x14009503c  jz      loc_1400950FE
0x140095042  lea     rdx, aNtsd; "ntsd"
0x140095049  lea     rcx, [rsp+278h+Data]; Str
0x14009504e  call    cs:__imp_wcsstr
0x140095054  test    rax, rax
0x140095057  jz      short loc_1400950C6
0x140095059  mov     rcx, rdi; lpFileName
0x14009505c  call    cs:__imp_GetFileAttributesW
0x140095062  cmp     eax, 0FFFFFFFFh
0x140095065  setnz   bl
0x140095068  mov     [rsp+278h+var_248], ebx
0x14009506c  jnz     loc_140095299
0x140095072  call    cs:__imp_GetLastError
0x140095078  lea     rcx, WPP_GLOBAL_Control
0x14009507f  mov     r10, cs:WPP_GLOBAL_Control
0x140095086  cmp     r10, rcx
0x140095089  jz      loc_1400951CB
0x14009508f  test    byte ptr [r10+1Ch], 8
0x140095094  jz      loc_1400951CB
0x14009509a  cmp     byte ptr [r10+19h], 2
0x14009509f  jb      loc_1400951CB
0x1400950a5  mov     edx, 0Bh
0x1400950aa  mov     dword ptr [rsp+278h+phkResult], eax
0x1400950ae  mov     r9, rdi
0x1400950b1  lea     r8, WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids
0x1400950b8  mov     rcx, [r10+10h]
0x1400950bc  call    WPP_SF_SD
0x1400950c1  jmp     loc_1400951CB
0x1400950c6  lea     rcx, WPP_GLOBAL_Control
0x1400950cd  mov     rax, cs:WPP_GLOBAL_Control
0x1400950d4  cmp     rax, rcx
0x1400950d7  jz      loc_1400951CB
0x1400950dd  test    byte ptr [rax+1Ch], 8
0x1400950e1  jz      loc_1400951CB
0x1400950e7  cmp     byte ptr [rax+19h], 2
0x1400950eb  jb      loc_1400951CB
0x1400950f1  mov     edx, 0Ch
0x1400950f6  mov     r9, rdi
0x1400950f9  jmp     loc_1400951BB
0x1400950fe  call    cs:__imp_GetLastError
0x140095104  lea     rcx, WPP_GLOBAL_Control
0x14009510b  mov     r10, cs:WPP_GLOBAL_Control
0x140095112  cmp     r10, rcx
0x140095115  jz      loc_1400951D0
0x14009511b  test    byte ptr [r10+1Ch], 8
0x140095120  jz      loc_1400951D0
0x140095126  cmp     byte ptr [r10+19h], 2
0x14009512b  jb      loc_1400951D0
0x140095131  mov     edx, 0Dh
0x140095136  mov     r9d, eax
0x140095139  lea     r8, WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids
0x140095140  mov     rcx, [r10+10h]
0x140095144  call    WPP_SF_d
0x140095149  jmp     loc_1400951D0
0x14009514e  lea     rdx, aNtsd; "ntsd"
0x140095155  lea     rcx, [rsp+278h+Data]; Str
0x14009515a  call    cs:__imp_wcsstr
0x140095160  test    rax, rax
0x140095163  jz      short loc_140095192
0x140095165  lea     r8, [rsp+278h+Data]; unsigned __int16 *
0x14009516a  mov     edx, 104h; unsigned __int64
0x14009516f  mov     rcx, rdi; unsigned __int16 *
0x140095172  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140095177  mov     rcx, rdi; lpFileName
0x14009517a  call    cs:__imp_GetFileAttributesW
0x140095180  xor     ebx, ebx
0x140095182  cmp     eax, 0FFFFFFFFh
0x140095185  setnz   bl
0x140095188  mov     [rsp+278h+var_248], ebx
0x14009518c  jnz     loc_140095299
0x140095192  lea     rcx, WPP_GLOBAL_Control
0x140095199  mov     rax, cs:WPP_GLOBAL_Control
0x1400951a0  cmp     rax, rcx
0x1400951a3  jz      short loc_1400951CB
0x1400951a5  test    byte ptr [rax+1Ch], 8
0x1400951a9  jz      short loc_1400951CB
0x1400951ab  cmp     byte ptr [rax+19h], 2
0x1400951af  jb      short loc_1400951CB
0x1400951b1  mov     edx, 0Ah
0x1400951b6  lea     r9, [rsp+278h+Data]
0x1400951bb  lea     r8, WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids
0x1400951c2  mov     rcx, [rax+10h]
0x1400951c6  call    WPP_SF_S
0x1400951cb  xor     eax, eax
0x1400951cd  mov     [rdi], ax
0x1400951d0  mov     r8d, 104h; nSize
0x1400951d6  mov     rdx, rdi; lpDst
0x1400951d9  lea     rcx, aSystemrootDebu; "%SystemRoot%\\Debuggers\\ntsd.exe"
0x1400951e0  call    cs:__imp_ExpandEnvironmentStringsW
0x1400951e6  cmp     eax, 104h
0x1400951eb  ja      short loc_140095202
0x1400951ed  mov     rcx, rdi; lpFileName
0x1400951f0  call    cs:__imp_GetFileAttributesW
0x1400951f6  xor     ebx, ebx
0x1400951f8  cmp     eax, 0FFFFFFFFh
0x1400951fb  setnz   bl
0x1400951fe  mov     [rsp+278h+var_248], ebx
0x140095202  test    ebx, ebx
0x140095204  jnz     loc_140095299
0x14009520a  mov     r8d, 104h; nSize
0x140095210  mov     rdx, rdi; lpDst
0x140095213  lea     rcx, aSystemdriveDeb; "%SystemDrive%\\Debuggers\\ntsd.exe"
0x14009521a  call    cs:__imp_ExpandEnvironmentStringsW
0x140095220  cmp     eax, 104h
0x140095225  ja      short loc_14009523A
0x140095227  mov     rcx, rdi; lpFileName
0x14009522a  call    cs:__imp_GetFileAttributesW
0x140095230  cmp     eax, 0FFFFFFFFh
0x140095233  setnz   bl
0x140095236  mov     [rsp+278h+var_248], ebx
0x14009523a  test    ebx, ebx
0x14009523c  jnz     short loc_140095299
0x14009523e  lea     r8, aCDebuggersNtsd; "C:\\Debuggers\\ntsd.exe"
0x140095245  mov     edx, 104h; unsigned __int64
0x14009524a  mov     rcx, rdi; unsigned __int16 *
0x14009524d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140095252  mov     rcx, rdi; lpFileName
0x140095255  call    cs:__imp_GetFileAttributesW
0x14009525b  cmp     eax, 0FFFFFFFFh
0x14009525e  setnz   bl
0x140095261  mov     [rsp+278h+var_248], ebx
0x140095265  jnz     short loc_140095299
0x140095267  mov     r8d, 104h; nSize
0x14009526d  mov     rdx, rdi; lpDst
0x140095270  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\ntsd.exe"
0x140095277  call    cs:__imp_ExpandEnvironmentStringsW
0x14009527d  cmp     eax, 104h
0x140095282  ja      short loc_140095299
0x140095284  mov     rcx, rdi; lpFileName
0x140095287  call    cs:__imp_GetFileAttributesW
0x14009528d  xor     ebx, ebx
0x14009528f  cmp     eax, 0FFFFFFFFh
0x140095292  setnz   bl
0x140095295  mov     [rsp+278h+var_248], ebx
0x140095299  mov     rcx, [rsp+278h+hKey]; hKey
0x14009529e  test    rcx, rcx
0x1400952a1  jz      short loc_1400952A9
0x1400952a3  call    cs:__imp_RegCloseKey
0x1400952a9  mov     eax, ebx
0x1400952ab  mov     rcx, [rsp+278h+var_18]
0x1400952b3  xor     rcx, rsp; StackCookie
0x1400952b6  call    __security_check_cookie
0x1400952bb  mov     rbx, [rsp+278h+arg_8]
0x1400952c3  add     rsp, 270h
0x1400952ca  pop     rdi
0x1400952cb  retn
0x14009eb41  push    rbp
0x14009eb43  sub     rsp, 30h
0x14009eb47  mov     rbp, rdx
0x14009eb4a  mov     rcx, [rbp+38h]; hKey
0x14009eb4e  test    rcx, rcx
0x14009eb51  jz      short loc_14009EB5A
0x14009eb53  call    cs:__imp_RegCloseKey
0x14009eb59  nop
0x14009eb5a  add     rsp, 30h
0x14009eb5e  pop     rbp
0x14009eb5f  retn
```
