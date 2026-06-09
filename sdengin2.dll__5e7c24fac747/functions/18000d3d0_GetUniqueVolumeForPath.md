# GetUniqueVolumeForPath

- ea: `0x18000d3d0`
- end: `0x18000d5ef`
- name: `GetUniqueVolumeForPath`
- size: `543`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPWSTR lpszVolumeName, DWORD cchBufferLength)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18000b8c8`
- `0x18000d9fc`
- `0x18000ed08`

## callees

- `0x18000d3d0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a3ac`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18000d506`
- `KERNEL32!GetVolumePathNameW` at `0x18000d506`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d546`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d584`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d546`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d584`

## string_xrefs

- `0x18000d40b`: `GetUniqueVolumeForPath`

## pseudocode

```c
__int64 __fastcall GetUniqueVolumeForPath(unsigned __int16 *a1, LPWSTR lpszVolumeName, DWORD cchBufferLength)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v13; // [rsp+24h] [rbp-DCh]
  __int16 v14; // [rsp+26h] [rbp-DAh]
  LPCWSTR lpszFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  WCHAR szVolumePathName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szVolumeName[264]; // [rsp+280h] [rbp+180h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "GetUniqueVolumeForPath", 58, 1);
  lpszFileName = (LPCWSTR)qword_1800E8530;
  v16 = 0;
  memset_0(szVolumePathName, 0, 0x20Au);
  memset_0(szVolumeName, 0, 0x20Au);
  v6 = 64;
  if ( !a1 )
    goto LABEL_2;
  v13 = 64;
  if ( !lpszVolumeName )
  {
    v6 = 65;
LABEL_2:
    LastFailureAsHRESULT = -2147024809;
    v12 = -2147024809;
    goto LABEL_3;
  }
  v12 = 0;
  v13 = 66;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)&lpszFileName, a1);
  v12 = LastFailureAsHRESULT;
  v6 = 69;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v13 = 69;
  v6 = 70;
  if ( !(_DWORD)v16 )
    goto LABEL_2;
  v12 = 0;
  v13 = 70;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)&lpszFileName, 0x5Cu);
  v12 = LastFailureAsHRESULT;
  v6 = 72;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v13 = 72;
    if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x105u) )
    {
      v12 = 0;
      v13 = 77;
      if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u) )
      {
        v12 = 0;
        v13 = 84;
        if ( GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, cchBufferLength) )
        {
          v12 = 0;
          v13 = 89;
          LastFailureAsHRESULT = 0;
          goto LABEL_16;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
        v12 = LastFailureAsHRESULT;
        v6 = 89;
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v12 = LastFailureAsHRESULT;
        v6 = 84;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v12 = LastFailureAsHRESULT;
      v6 = 77;
    }
  }
LABEL_3:
  v14 = v6;
LABEL_16:
  CBsString::_Release((CBsString *)&lpszFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000d3d0  mov     [rsp-8+arg_18], rbx
0x18000d3d5  push    rbp
0x18000d3d6  push    rsi
0x18000d3d7  push    rdi
0x18000d3d8  lea     rbp, [rsp-3A0h]
0x18000d3e0  sub     rsp, 4A0h
0x18000d3e7  mov     rax, cs:__security_cookie
0x18000d3ee  xor     rax, rsp
0x18000d3f1  mov     [rbp+3B0h+var_20], rax
0x18000d3f8  mov     esi, r8d
0x18000d3fb  mov     rdi, rdx
0x18000d3fe  mov     rbx, rcx
0x18000d401  mov     r9d, 1; unsigned __int16
0x18000d407  lea     r8d, [r9+39h]; unsigned __int16
0x18000d40b  lea     rdx, aGetuniquevolum; "GetUniqueVolumeForPath"
0x18000d412  lea     rcx, [rsp+4B0h+var_490]; this
0x18000d417  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d41c  lea     rax, qword_1800E8530
0x18000d423  mov     [rsp+4B0h+lpszFileName], rax
0x18000d428  mov     [rsp+4B0h+var_450], 0
0x18000d431  xor     edx, edx; Val
0x18000d433  mov     r8d, 20Ah; Size
0x18000d439  lea     rcx, [rsp+4B0h+szVolumePathName]; void *
0x18000d43e  call    memset_0
0x18000d443  xor     edx, edx; Val
0x18000d445  mov     r8d, 20Ah; Size
0x18000d44b  lea     rcx, [rbp+3B0h+szVolumeName]; void *
0x18000d452  call    memset_0
0x18000d457  mov     eax, 40h ; '@'
0x18000d45c  test    rbx, rbx
0x18000d45f  jnz     short loc_18000D474
0x18000d461  mov     ebx, 80070057h
0x18000d466  mov     [rsp+4B0h+var_490], ebx
0x18000d46a  mov     [rsp+4B0h+var_48A], ax
0x18000d46f  jmp     loc_18000D5B7
0x18000d474  mov     [rsp+4B0h+var_48C], ax
0x18000d479  test    rdi, rdi
0x18000d47c  jnz     short loc_18000D483
0x18000d47e  lea     eax, [rdi+41h]
0x18000d481  jmp     short loc_18000D461
0x18000d483  mov     [rsp+4B0h+var_490], 0
0x18000d48b  mov     eax, 42h ; 'B'
0x18000d490  mov     [rsp+4B0h+var_48C], ax
0x18000d495  mov     rdx, rbx; unsigned __int16 *
0x18000d498  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000d49d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000d4a2  mov     ebx, eax
0x18000d4a4  mov     [rsp+4B0h+var_490], eax
0x18000d4a8  test    eax, eax
0x18000d4aa  mov     eax, 45h ; 'E'
0x18000d4af  js      short loc_18000D46A
0x18000d4b1  mov     [rsp+4B0h+var_48C], ax
0x18000d4b6  mov     eax, 46h ; 'F'
0x18000d4bb  cmp     dword ptr [rsp+4B0h+var_450], 0
0x18000d4c0  jz      short loc_18000D461
0x18000d4c2  mov     [rsp+4B0h+var_490], 0
0x18000d4ca  mov     [rsp+4B0h+var_48C], ax
0x18000d4cf  lea     edx, [rax+16h]; unsigned __int16
0x18000d4d2  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000d4d7  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000d4dc  mov     ebx, eax
0x18000d4de  mov     [rsp+4B0h+var_490], eax
0x18000d4e2  test    eax, eax
0x18000d4e4  mov     eax, 48h ; 'H'
0x18000d4e9  js      loc_18000D46A
0x18000d4ef  mov     [rsp+4B0h+var_48C], ax
0x18000d4f4  mov     ebx, 105h
0x18000d4f9  mov     r8d, ebx; cchBufferLength
0x18000d4fc  lea     rdx, [rsp+4B0h+szVolumePathName]; lpszVolumePathName
0x18000d501  mov     rcx, [rsp+4B0h+lpszFileName]; lpszFileName
0x18000d506  call    cs:__imp_GetVolumePathNameW
0x18000d50c  test    eax, eax
0x18000d50e  jnz     short loc_18000D525
0x18000d510  call    GetLastFailureAsHRESULT
0x18000d515  mov     ebx, eax
0x18000d517  mov     [rsp+4B0h+var_490], eax
0x18000d51b  mov     eax, 4Dh ; 'M'
0x18000d520  jmp     loc_18000D46A
0x18000d525  mov     [rsp+4B0h+var_490], 0
0x18000d52d  mov     eax, 4Dh ; 'M'
0x18000d532  mov     [rsp+4B0h+var_48C], ax
0x18000d537  mov     r8d, ebx; cchBufferLength
0x18000d53a  lea     rdx, [rbp+3B0h+szVolumeName]; lpszVolumeName
0x18000d541  lea     rcx, [rsp+4B0h+szVolumePathName]; lpszVolumeMountPoint
0x18000d546  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000d54c  test    eax, eax
0x18000d54e  jnz     short loc_18000D565
0x18000d550  call    GetLastFailureAsHRESULT
0x18000d555  mov     ebx, eax
0x18000d557  mov     [rsp+4B0h+var_490], eax
0x18000d55b  mov     eax, 54h ; 'T'
0x18000d560  jmp     loc_18000D46A
0x18000d565  mov     [rsp+4B0h+var_490], 0
0x18000d56d  mov     eax, 54h ; 'T'
0x18000d572  mov     [rsp+4B0h+var_48C], ax
0x18000d577  mov     r8d, esi; cchBufferLength
0x18000d57a  mov     rdx, rdi; lpszVolumeName
0x18000d57d  lea     rcx, [rbp+3B0h+szVolumeName]; lpszVolumeMountPoint
0x18000d584  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000d58a  test    eax, eax
0x18000d58c  jnz     short loc_18000D5A3
0x18000d58e  call    GetLastFailureAsHRESULT
0x18000d593  mov     ebx, eax
0x18000d595  mov     [rsp+4B0h+var_490], eax
0x18000d599  mov     eax, 59h ; 'Y'
0x18000d59e  jmp     loc_18000D46A
0x18000d5a3  mov     [rsp+4B0h+var_490], 0
0x18000d5ab  mov     eax, 59h ; 'Y'
0x18000d5b0  mov     [rsp+4B0h+var_48C], ax
0x18000d5b5  xor     ebx, ebx
0x18000d5b7  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000d5bc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000d5c1  lea     rcx, [rsp+4B0h+var_490]; this
0x18000d5c6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d5cb  mov     eax, ebx
0x18000d5cd  mov     rcx, [rbp+3B0h+var_20]
0x18000d5d4  xor     rcx, rsp; StackCookie
0x18000d5d7  call    __security_check_cookie
0x18000d5dc  mov     rbx, [rsp+4B0h+arg_18]
0x18000d5e4  add     rsp, 4A0h
0x18000d5eb  pop     rdi
0x18000d5ec  pop     rsi
0x18000d5ed  pop     rbp
0x18000d5ee  retn
```
