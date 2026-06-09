# CLogonUser::s_GetUnreadMail(CLogonUser *,tagVARIANT *)

- ea: `0x18002f1f0`
- end: `0x18002f351`
- name: `?s_GetUnreadMail@CLogonUser@@CAJPEAV1@PEAUtagVARIANT@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct CLogonUser *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002d1dc`
- `0x18002f1f0`
- `0x180034620`
- `0x180034784`
- `0x1800772c0`

## import_xrefs

- `SHELL32!SHGetUnreadMailCountW` at `0x18002f300`
- `SHELL32!SHGetUnreadMailCountW` at `0x18002f300`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f2a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f2a3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002f2b1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002f2b1`
- `KERNEL32!lstrcmpiW` at `0x18002f257`
- `KERNEL32!lstrcmpiW` at `0x18002f257`
- `KERNEL32!GetComputerNameW` at `0x18002f23b`
- `KERNEL32!GetComputerNameW` at `0x18002f23b`

## pseudocode

```c
__int64 __fastcall CLogonUser::s_GetUnreadMail(const WCHAR *a1, struct tagVARIANT *a2)
{
  HRESULT v4; // edi
  CLogonUser *v5; // rcx
  unsigned int ExpiryDays; // esi
  unsigned __int64 v7; // rdx
  struct _FILETIME FileTime; // [rsp+30h] [rbp-19h] BYREF
  DWORD pdwCount; // [rsp+38h] [rbp-11h] BYREF
  DWORD nSize; // [rsp+3Ch] [rbp-Dh] BYREF
  HKEY hKeyUser[3]; // [rsp+40h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp+Fh] BYREF
  WCHAR Buffer[16]; // [rsp+68h] [rbp+1Fh] BYREF

  if ( a2 )
  {
    nSize = 16;
    v4 = -2147467259;
    if ( GetComputerNameW(Buffer, &nSize) && !lstrcmpiW(Buffer, a1 + 263) )
    {
      CUserProfile::CUserProfile(hKeyUser, a1 + 6, a1 + 263);
      if ( hKeyUser[0] )
      {
        pdwCount = 0;
        SystemTime = 0;
        FileTime = 0;
        ExpiryDays = CLogonUser::_GetExpiryDays(v5, hKeyUser[0]);
        GetLocalTime(&SystemTime);
        SystemTimeToFileTime(&SystemTime, &FileTime);
        v7 = FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32) - 864000000000LL * ExpiryDays;
        FileTime.dwLowDateTime -= 711573504 * ExpiryDays;
        FileTime.dwHighDateTime = HIDWORD(v7);
        v4 = SHGetUnreadMailCountW(hKeyUser[0], 0, &pdwCount, &FileTime, 0, 0);
        if ( v4 >= 0 )
        {
          if ( ExpiryDays )
          {
            a2->lVal = pdwCount;
            a2->vt = 19;
          }
        }
      }
      CUserProfile::~CUserProfile((LPCWSTR *)hKeyUser);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002f1f0  mov     [rsp-8+arg_10], rbx
0x18002f1f5  mov     [rsp-8+arg_18], rsi
0x18002f1fa  push    rbp
0x18002f1fb  push    rdi
0x18002f1fc  push    r14
0x18002f1fe  lea     rbp, [rsp-47h]
0x18002f203  sub     rsp, 90h
0x18002f20a  mov     rax, cs:__security_cookie
0x18002f211  xor     rax, rsp
0x18002f214  mov     [rbp+57h+var_18], rax
0x18002f218  mov     rbx, rdx
0x18002f21b  mov     rsi, rcx
0x18002f21e  test    rdx, rdx
0x18002f221  jz      loc_18002F326
0x18002f227  lea     rdx, [rbp+57h+nSize]; nSize
0x18002f22b  mov     [rbp+57h+nSize], 10h
0x18002f232  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18002f236  mov     edi, 80004005h
0x18002f23b  call    cs:__imp_GetComputerNameW
0x18002f241  test    eax, eax
0x18002f243  jz      loc_18002F32B
0x18002f249  lea     r14, [rsi+20Eh]
0x18002f250  mov     rdx, r14; lpString2
0x18002f253  lea     rcx, [rbp+57h+Buffer]; lpString1
0x18002f257  call    cs:__imp_lstrcmpiW
0x18002f25d  test    eax, eax
0x18002f25f  jnz     loc_18002F32B
0x18002f265  lea     rdx, [rsi+0Ch]; lpAccountName
0x18002f269  mov     r8, r14; DomainName
0x18002f26c  lea     rcx, [rbp+57h+hKeyUser]; phkResult
0x18002f270  call    ??0CUserProfile@@QEAA@PEBG0@Z; CUserProfile::CUserProfile(ushort const *,ushort const *)
0x18002f275  mov     rdx, [rbp+57h+hKeyUser]; HKEY
0x18002f279  test    rdx, rdx
0x18002f27c  jz      loc_18002F31B
0x18002f282  xorps   xmm0, xmm0
0x18002f285  mov     [rbp+57h+pdwCount], 0
0x18002f28c  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002f290  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18002f298  call    ?_GetExpiryDays@CLogonUser@@AEAAKPEAUHKEY__@@@Z; CLogonUser::_GetExpiryDays(HKEY__ *)
0x18002f29d  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002f2a1  mov     esi, eax
0x18002f2a3  call    cs:__imp_GetLocalTime
0x18002f2a9  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18002f2ad  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002f2b1  call    cs:__imp_SystemTimeToFileTime
0x18002f2b7  mov     edx, [rbp+57h+FileTime.dwHighDateTime]
0x18002f2ba  lea     r9, [rbp+57h+FileTime]; pFileTime
0x18002f2be  shl     rdx, 20h
0x18002f2c2  lea     r8, [rbp+57h+pdwCount]; pdwCount
0x18002f2c6  mov     rax, 0C92A69C000h
0x18002f2d0  mov     [rsp+0A0h+cchShellExecuteCommand], 0; cchShellExecuteCommand
0x18002f2d8  mov     ecx, esi
0x18002f2da  mov     [rsp+0A0h+pszShellExecuteCommand], 0; pszShellExecuteCommand
0x18002f2e3  imul    rcx, rax
0x18002f2e7  sub     rdx, rcx
0x18002f2ea  mov     ecx, [rbp+57h+FileTime.dwLowDateTime]
0x18002f2ed  add     rdx, rcx
0x18002f2f0  mov     rcx, [rbp+57h+hKeyUser]; hKeyUser
0x18002f2f4  mov     [rbp+57h+FileTime.dwLowDateTime], edx
0x18002f2f7  shr     rdx, 20h
0x18002f2fb  mov     [rbp+57h+FileTime.dwHighDateTime], edx
0x18002f2fe  xor     edx, edx; pszMailAddress
0x18002f300  call    cs:__imp_SHGetUnreadMailCountW
0x18002f306  mov     edi, eax
0x18002f308  test    eax, eax
0x18002f30a  js      short loc_18002F31B
0x18002f30c  test    esi, esi
0x18002f30e  jz      short loc_18002F31B
0x18002f310  mov     ecx, [rbp+57h+pdwCount]
0x18002f313  mov     [rbx+8], ecx
0x18002f316  mov     word ptr [rbx], 13h
0x18002f31b  lea     rcx, [rbp+57h+hKeyUser]; this
0x18002f31f  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18002f324  jmp     short loc_18002F32B
0x18002f326  mov     edi, 80070057h
0x18002f32b  mov     eax, edi
0x18002f32d  mov     rcx, [rbp+57h+var_18]
0x18002f331  xor     rcx, rsp; StackCookie
0x18002f334  call    __security_check_cookie
0x18002f339  lea     r11, [rsp+0A0h+var_10]
0x18002f341  mov     rbx, [r11+30h]
0x18002f345  mov     rsi, [r11+38h]
0x18002f349  mov     rsp, r11
0x18002f34c  pop     r14
0x18002f34e  pop     rdi
0x18002f34f  pop     rbp
0x18002f350  retn
```
