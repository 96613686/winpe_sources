# CLogonUser::getMailAccountInfo(uint,tagVARIANT *,uint *)

- ea: `0x18002e180`
- end: `0x18002e366`
- name: `?getMailAccountInfo@CLogonUser@@UEAAJIPEAUtagVARIANT@@PEAI@Z`
- size: `486`
- prototype: `int(CLogonUser *__hidden this, unsigned int, struct tagVARIANT *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002d1dc`
- `0x18002e180`
- `0x180034620`
- `0x180034784`
- `0x1800772c0`

## import_xrefs

- `SHELL32!SHEnumerateUnreadMailAccountsW` at `0x18002e227`
- `SHELL32!SHEnumerateUnreadMailAccountsW` at `0x18002e227`
- `SHELL32!SHGetUnreadMailCountW` at `0x18002e2ad`
- `SHELL32!SHGetUnreadMailCountW` at `0x18002e2ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e245`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e245`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002e308`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002e308`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002e2e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002e2e8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002e2f8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002e2f8`
- `KERNEL32!lstrcmpiW` at `0x18002e1e5`
- `KERNEL32!lstrcmpiW` at `0x18002e1e5`
- `KERNEL32!GetComputerNameW` at `0x18002e1c8`
- `KERNEL32!GetComputerNameW` at `0x18002e1c8`

## pseudocode

```c
__int64 __fastcall CLogonUser::getMailAccountInfo(const WCHAR *this, DWORD a2, struct tagVARIANT *a3, unsigned int *a4)
{
  HRESULT v8; // ebx
  CLogonUser *v9; // rcx
  BSTR v10; // rax
  unsigned int ExpiryDays; // esi
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  BOOL v14; // eax
  FILETIME pFileTime; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwCount; // [rsp+38h] [rbp-C8h] BYREF
  DWORD nSize; // [rsp+3Ch] [rbp-C4h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeyUser[3]; // [rsp+48h] [rbp-B8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszMailAddress[104]; // [rsp+90h] [rbp-70h] BYREF

  nSize = 16;
  v8 = -2147467259;
  if ( GetComputerNameW(Buffer, &nSize) && !lstrcmpiW(Buffer, this + 263) )
  {
    CUserProfile::CUserProfile(hKeyUser, this + 6, this + 263);
    if ( hKeyUser[0] )
    {
      pdwCount = 0;
      v8 = SHEnumerateUnreadMailAccountsW(hKeyUser[0], a2, pszMailAddress, 100);
      if ( v8 >= 0 )
      {
        if ( !a3 )
          goto LABEL_8;
        a3->vt = 8;
        v10 = SysAllocString(pszMailAddress);
        a3->llVal = (LONGLONG)v10;
        if ( v10 )
        {
          v8 = 0;
LABEL_8:
          if ( a4 )
          {
            SystemTime = 0;
            pFileTime = 0;
            FileTime = 0;
            ExpiryDays = CLogonUser::_GetExpiryDays(v9, hKeyUser[0]);
            v8 = SHGetUnreadMailCountW(hKeyUser[0], pszMailAddress, &pdwCount, &pFileTime, 0, 0);
            v12 = 864000000000LL * ExpiryDays;
            v13 = pFileTime.dwLowDateTime + v12 + ((unsigned __int64)pFileTime.dwHighDateTime << 32);
            pFileTime.dwLowDateTime += v12;
            pFileTime.dwHighDateTime = HIDWORD(v13);
            GetLocalTime(&SystemTime);
            SystemTimeToFileTime(&SystemTime, &FileTime);
            v14 = CompareFileTime(&pFileTime, &FileTime) < 0 || !ExpiryDays;
            if ( v8 < 0 || v14 )
              *a4 = 0;
            else
              *a4 = pdwCount;
          }
          goto LABEL_18;
        }
        v8 = -2147024882;
      }
    }
LABEL_18:
    CUserProfile::~CUserProfile((LPCWSTR *)hKeyUser);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002e180  push    rbp
0x18002e182  push    rbx
0x18002e183  push    rsi
0x18002e184  push    rdi
0x18002e185  push    r12
0x18002e187  push    r14
0x18002e189  push    r15
0x18002e18b  lea     rbp, [rsp-70h]
0x18002e190  sub     rsp, 170h
0x18002e197  mov     rax, cs:__security_cookie
0x18002e19e  xor     rax, rsp
0x18002e1a1  mov     [rbp+0A0h+var_40], rax
0x18002e1a5  mov     r12d, edx
0x18002e1a8  mov     [rsp+1A0h+nSize], 10h
0x18002e1b0  mov     r15, rcx
0x18002e1b3  lea     rdx, [rsp+1A0h+nSize]; nSize
0x18002e1b8  lea     rcx, [rsp+1A0h+Buffer]; lpBuffer
0x18002e1bd  mov     rdi, r9
0x18002e1c0  mov     rsi, r8
0x18002e1c3  mov     ebx, 80004005h
0x18002e1c8  call    cs:__imp_GetComputerNameW
0x18002e1ce  test    eax, eax
0x18002e1d0  jz      loc_18002E346
0x18002e1d6  lea     r14, [r15+20Eh]
0x18002e1dd  mov     rdx, r14; lpString2
0x18002e1e0  lea     rcx, [rsp+1A0h+Buffer]; lpString1
0x18002e1e5  call    cs:__imp_lstrcmpiW
0x18002e1eb  test    eax, eax
0x18002e1ed  jnz     loc_18002E346
0x18002e1f3  lea     rdx, [r15+0Ch]; lpAccountName
0x18002e1f7  mov     r8, r14; DomainName
0x18002e1fa  lea     rcx, [rsp+1A0h+hKeyUser]; phkResult
0x18002e1ff  call    ??0CUserProfile@@QEAA@PEBG0@Z; CUserProfile::CUserProfile(ushort const *,ushort const *)
0x18002e204  mov     rcx, [rsp+1A0h+hKeyUser]; hKeyUser
0x18002e209  test    rcx, rcx
0x18002e20c  jz      loc_18002E33C
0x18002e212  mov     r9d, 64h ; 'd'; cchMailAddress
0x18002e218  mov     [rsp+1A0h+pdwCount], 0
0x18002e220  lea     r8, [rbp+0A0h+pszMailAddress]; pszMailAddress
0x18002e224  mov     edx, r12d; dwIndex
0x18002e227  call    cs:__imp_SHEnumerateUnreadMailAccountsW
0x18002e22d  mov     ebx, eax
0x18002e22f  test    eax, eax
0x18002e231  js      loc_18002E33C
0x18002e237  test    rsi, rsi
0x18002e23a  jz      short loc_18002E25A
0x18002e23c  lea     rcx, [rbp+0A0h+pszMailAddress]; psz
0x18002e240  mov     word ptr [rsi], 8
0x18002e245  call    cs:__imp_SysAllocString
0x18002e24b  mov     [rsi+8], rax
0x18002e24f  test    rax, rax
0x18002e252  jz      loc_18002E31A
0x18002e258  xor     ebx, ebx
0x18002e25a  test    rdi, rdi
0x18002e25d  jz      loc_18002E33C
0x18002e263  mov     rdx, [rsp+1A0h+hKeyUser]; HKEY
0x18002e268  xorps   xmm0, xmm0
0x18002e26b  movups  xmmword ptr [rsp+1A0h+SystemTime.wYear], xmm0
0x18002e270  mov     qword ptr [rsp+1A0h+pFileTime.dwLowDateTime], 0
0x18002e279  mov     qword ptr [rsp+1A0h+FileTime.dwLowDateTime], 0
0x18002e282  call    ?_GetExpiryDays@CLogonUser@@AEAAKPEAUHKEY__@@@Z; CLogonUser::_GetExpiryDays(HKEY__ *)
0x18002e287  mov     rcx, [rsp+1A0h+hKeyUser]; hKeyUser
0x18002e28c  lea     r9, [rsp+1A0h+pFileTime]; pFileTime
0x18002e291  lea     r8, [rsp+1A0h+pdwCount]; pdwCount
0x18002e296  mov     [rsp+1A0h+cchShellExecuteCommand], 0; cchShellExecuteCommand
0x18002e29e  lea     rdx, [rbp+0A0h+pszMailAddress]; pszMailAddress
0x18002e2a2  mov     esi, eax
0x18002e2a4  mov     [rsp+1A0h+pszShellExecuteCommand], 0; pszShellExecuteCommand
0x18002e2ad  call    cs:__imp_SHGetUnreadMailCountW
0x18002e2b3  mov     ecx, [rsp+1A0h+pFileTime.dwHighDateTime]
0x18002e2b7  mov     edx, esi
0x18002e2b9  shl     rcx, 20h
0x18002e2bd  mov     ebx, eax
0x18002e2bf  mov     rax, 0C92A69C000h
0x18002e2c9  imul    rdx, rax
0x18002e2cd  mov     eax, [rsp+1A0h+pFileTime.dwLowDateTime]
0x18002e2d1  add     rcx, rdx
0x18002e2d4  add     rcx, rax
0x18002e2d7  mov     [rsp+1A0h+pFileTime.dwLowDateTime], ecx
0x18002e2db  shr     rcx, 20h
0x18002e2df  mov     [rsp+1A0h+pFileTime.dwHighDateTime], ecx
0x18002e2e3  lea     rcx, [rsp+1A0h+SystemTime]; lpSystemTime
0x18002e2e8  call    cs:__imp_GetLocalTime
0x18002e2ee  lea     rdx, [rsp+1A0h+FileTime]; lpFileTime
0x18002e2f3  lea     rcx, [rsp+1A0h+SystemTime]; lpSystemTime
0x18002e2f8  call    cs:__imp_SystemTimeToFileTime
0x18002e2fe  lea     rdx, [rsp+1A0h+FileTime]; lpFileTime2
0x18002e303  lea     rcx, [rsp+1A0h+pFileTime]; lpFileTime1
0x18002e308  call    cs:__imp_CompareFileTime
0x18002e30e  test    eax, eax
0x18002e310  js      short loc_18002E321
0x18002e312  test    esi, esi
0x18002e314  jz      short loc_18002E321
0x18002e316  xor     eax, eax
0x18002e318  jmp     short loc_18002E326
0x18002e31a  mov     ebx, 8007000Eh
0x18002e31f  jmp     short loc_18002E33C
0x18002e321  mov     eax, 1
0x18002e326  test    ebx, ebx
0x18002e328  js      short loc_18002E336
0x18002e32a  test    eax, eax
0x18002e32c  jnz     short loc_18002E336
0x18002e32e  mov     eax, [rsp+1A0h+pdwCount]
0x18002e332  mov     [rdi], eax
0x18002e334  jmp     short loc_18002E33C
0x18002e336  mov     dword ptr [rdi], 0
0x18002e33c  lea     rcx, [rsp+1A0h+hKeyUser]; this
0x18002e341  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18002e346  mov     eax, ebx
0x18002e348  mov     rcx, [rbp+0A0h+var_40]
0x18002e34c  xor     rcx, rsp; StackCookie
0x18002e34f  call    __security_check_cookie
0x18002e354  add     rsp, 170h
0x18002e35b  pop     r15
0x18002e35d  pop     r14
0x18002e35f  pop     r12
0x18002e361  pop     rdi
0x18002e362  pop     rsi
0x18002e363  pop     rbx
0x18002e364  pop     rbp
0x18002e365  retn
```
