# GetUniqueVolumeForPath

- ea: `0x18000d814`
- end: `0x18000da46`
- name: `GetUniqueVolumeForPath`
- size: `562`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPWSTR lpszVolumeName, DWORD cchBufferLength)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18000bc28`
- `0x18000de8c`
- `0x18000f2cc`

## callees

- `0x18000d814`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ea6c`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x18000d94a`
- `KERNEL32!GetVolumePathNameW` at `0x18000d94a`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d990`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d9d4`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d990`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18000d9d4`

## string_xrefs

- `0x18000d84f`: `GetUniqueVolumeForPath`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "GetUniqueVolumeForPath", 0x3Au, 1u);
  lpszFileName = (LPCWSTR)qword_1800EE510;
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
0x18000d814  mov     [rsp-8+arg_18], rbx
0x18000d819  push    rbp
0x18000d81a  push    rsi
0x18000d81b  push    rdi
0x18000d81c  lea     rbp, [rsp-3A0h]
0x18000d824  sub     rsp, 4A0h
0x18000d82b  mov     rax, cs:__security_cookie
0x18000d832  xor     rax, rsp
0x18000d835  mov     [rbp+3B0h+var_20], rax
0x18000d83c  mov     esi, r8d
0x18000d83f  mov     rdi, rdx
0x18000d842  mov     rbx, rcx
0x18000d845  mov     r9d, 1; unsigned __int16
0x18000d84b  lea     r8d, [r9+39h]; unsigned __int16
0x18000d84f  lea     rdx, aGetuniquevolum; "GetUniqueVolumeForPath"
0x18000d856  lea     rcx, [rsp+4B0h+var_490]; this
0x18000d85b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d860  lea     rax, qword_1800EE510
0x18000d867  mov     [rsp+4B0h+lpszFileName], rax
0x18000d86c  mov     [rsp+4B0h+var_450], 0
0x18000d875  xor     edx, edx; Val
0x18000d877  mov     r8d, 20Ah; Size
0x18000d87d  lea     rcx, [rsp+4B0h+szVolumePathName]; void *
0x18000d882  call    memset_0
0x18000d887  xor     edx, edx; Val
0x18000d889  mov     r8d, 20Ah; Size
0x18000d88f  lea     rcx, [rbp+3B0h+szVolumeName]; void *
0x18000d896  call    memset_0
0x18000d89b  mov     eax, 40h ; '@'
0x18000d8a0  test    rbx, rbx
0x18000d8a3  jnz     short loc_18000D8B8
0x18000d8a5  mov     ebx, 80070057h
0x18000d8aa  mov     [rsp+4B0h+var_490], ebx
0x18000d8ae  mov     [rsp+4B0h+var_48A], ax
0x18000d8b3  jmp     loc_18000DA0D
0x18000d8b8  mov     [rsp+4B0h+var_48C], ax
0x18000d8bd  test    rdi, rdi
0x18000d8c0  jnz     short loc_18000D8C7
0x18000d8c2  lea     eax, [rdi+41h]
0x18000d8c5  jmp     short loc_18000D8A5
0x18000d8c7  mov     [rsp+4B0h+var_490], 0
0x18000d8cf  mov     eax, 42h ; 'B'
0x18000d8d4  mov     [rsp+4B0h+var_48C], ax
0x18000d8d9  mov     rdx, rbx; unsigned __int16 *
0x18000d8dc  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000d8e1  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000d8e6  mov     ebx, eax
0x18000d8e8  mov     [rsp+4B0h+var_490], eax
0x18000d8ec  test    eax, eax
0x18000d8ee  mov     eax, 45h ; 'E'
0x18000d8f3  js      short loc_18000D8AE
0x18000d8f5  mov     [rsp+4B0h+var_48C], ax
0x18000d8fa  mov     eax, 46h ; 'F'
0x18000d8ff  cmp     dword ptr [rsp+4B0h+var_450], 0
0x18000d904  jz      short loc_18000D8A5
0x18000d906  mov     [rsp+4B0h+var_490], 0
0x18000d90e  mov     [rsp+4B0h+var_48C], ax
0x18000d913  lea     edx, [rax+16h]; unsigned __int16
0x18000d916  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000d91b  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000d920  mov     ebx, eax
0x18000d922  mov     [rsp+4B0h+var_490], eax
0x18000d926  test    eax, eax
0x18000d928  mov     eax, 48h ; 'H'
0x18000d92d  js      loc_18000D8AE
0x18000d933  mov     [rsp+4B0h+var_48C], ax
0x18000d938  mov     ebx, 105h
0x18000d93d  mov     r8d, ebx; cchBufferLength
0x18000d940  lea     rdx, [rsp+4B0h+szVolumePathName]; lpszVolumePathName
0x18000d945  mov     rcx, [rsp+4B0h+lpszFileName]; lpszFileName
0x18000d94a  call    cs:__imp_GetVolumePathNameW
0x18000d951  nop     dword ptr [rax+rax+00h]
0x18000d956  test    eax, eax
0x18000d958  jnz     short loc_18000D96F
0x18000d95a  call    GetLastFailureAsHRESULT
0x18000d95f  mov     ebx, eax
0x18000d961  mov     [rsp+4B0h+var_490], eax
0x18000d965  mov     eax, 4Dh ; 'M'
0x18000d96a  jmp     loc_18000D8AE
0x18000d96f  mov     [rsp+4B0h+var_490], 0
0x18000d977  mov     eax, 4Dh ; 'M'
0x18000d97c  mov     [rsp+4B0h+var_48C], ax
0x18000d981  mov     r8d, ebx; cchBufferLength
0x18000d984  lea     rdx, [rbp+3B0h+szVolumeName]; lpszVolumeName
0x18000d98b  lea     rcx, [rsp+4B0h+szVolumePathName]; lpszVolumeMountPoint
0x18000d990  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000d997  nop     dword ptr [rax+rax+00h]
0x18000d99c  test    eax, eax
0x18000d99e  jnz     short loc_18000D9B5
0x18000d9a0  call    GetLastFailureAsHRESULT
0x18000d9a5  mov     ebx, eax
0x18000d9a7  mov     [rsp+4B0h+var_490], eax
0x18000d9ab  mov     eax, 54h ; 'T'
0x18000d9b0  jmp     loc_18000D8AE
0x18000d9b5  mov     [rsp+4B0h+var_490], 0
0x18000d9bd  mov     eax, 54h ; 'T'
0x18000d9c2  mov     [rsp+4B0h+var_48C], ax
0x18000d9c7  mov     r8d, esi; cchBufferLength
0x18000d9ca  mov     rdx, rdi; lpszVolumeName
0x18000d9cd  lea     rcx, [rbp+3B0h+szVolumeName]; lpszVolumeMountPoint
0x18000d9d4  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000d9db  nop     dword ptr [rax+rax+00h]
0x18000d9e0  test    eax, eax
0x18000d9e2  jnz     short loc_18000D9F9
0x18000d9e4  call    GetLastFailureAsHRESULT
0x18000d9e9  mov     ebx, eax
0x18000d9eb  mov     [rsp+4B0h+var_490], eax
0x18000d9ef  mov     eax, 59h ; 'Y'
0x18000d9f4  jmp     loc_18000D8AE
0x18000d9f9  mov     [rsp+4B0h+var_490], 0
0x18000da01  mov     eax, 59h ; 'Y'
0x18000da06  mov     [rsp+4B0h+var_48C], ax
0x18000da0b  xor     ebx, ebx
0x18000da0d  lea     rcx, [rsp+4B0h+lpszFileName]; this
0x18000da12  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000da17  lea     rcx, [rsp+4B0h+var_490]; this
0x18000da1c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000da21  mov     eax, ebx
0x18000da23  mov     rcx, [rbp+3B0h+var_20]
0x18000da2a  xor     rcx, rsp; StackCookie
0x18000da2d  call    __security_check_cookie
0x18000da32  mov     rbx, [rsp+4B0h+arg_18]
0x18000da3a  add     rsp, 4A0h
0x18000da41  pop     rdi
0x18000da42  pop     rsi
0x18000da43  pop     rbp
0x18000da44  retn
```
