# CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)

- ea: `0x180008bc0`
- end: `0x180008e31`
- name: `?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, LPBYTE lpData, int, char, unsigned int *, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008990`
- `0x180008e40`
- `0x180008ea0`
- `0x180009170`
- `0x180009380`
- `0x1800097e0`
- `0x180009960`

## callees

- `0x180003970`
- `0x180007f84`
- `0x180008bc0`
- `0x18000a5e0`
- `0x18000a6c0`
- `0x18000a7b8`
- `0x18000a858`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180008cec`
- `ADVAPI32!RegQueryValueExW` at `0x180008cec`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c5c`
- `ADVAPI32!RegOpenKeyExW` at `0x180008c5c`
- `ADVAPI32!RegCloseKey` at `0x180008dc6`
- `ADVAPI32!RegCloseKey` at `0x180008dc6`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryEntry(
        HKEY hKey,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        LPBYTE lpData,
        DWORD a5,
        int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v8; // r12d
  unsigned __int16 *v13; // rdx
  LSTATUS v14; // eax
  char v15; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // r8d
  LSTATUS v18; // eax
  char v19; // si
  char v20; // si
  LSTATUS v21; // edi
  unsigned int v22; // eax
  __int64 v23; // r8
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v28[272]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  hKeya = 0;
  Type = 0;
  cbData = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a8 )
    CClientUtils::MakeSubKey(v28, (unsigned int)a2, a2);
  v13 = v28;
  if ( a8 )
    v13 = a2;
  v14 = RegOpenKeyExW(hKey, v13, 0, 0x20019u, &hKeya);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v17, CurrentThreadActivityIdPrefix, (__int64)v28, v15);
    }
  }
  else
  {
    cbData = a5;
    v18 = RegQueryValueExW(hKeya, a3, 0, &Type, lpData, &cbData);
    v19 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSl(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v19);
      }
    }
    else
    {
      v20 = Type;
      if ( Type == a6 || Type == 3 && a6 == 4 && cbData == 4 )
      {
        if ( a7 )
          *a7 = cbData;
        v8 = 1;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSll(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v20, a6);
      }
    }
    v21 = RegCloseKey(hKeya);
    if ( v21
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v23, v22, v21);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180008bc0  push    rbp
0x180008bc2  push    rbx
0x180008bc3  push    rsi
0x180008bc4  push    rdi
0x180008bc5  push    r12
0x180008bc7  push    r13
0x180008bc9  push    r14
0x180008bcb  push    r15
0x180008bcd  lea     rbp, [rsp-188h]
0x180008bd5  sub     rsp, 288h
0x180008bdc  mov     rax, cs:__security_cookie
0x180008be3  xor     rax, rsp
0x180008be6  mov     [rbp+1C0h+var_50], rax
0x180008bed  mov     rdi, [rbp+1C0h+arg_30]
0x180008bf4  xor     r12d, r12d
0x180008bf7  mov     [rsp+2C0h+hKey], 0
0x180008c00  mov     r14, r9
0x180008c03  mov     [rsp+2C0h+Type], 0
0x180008c0b  mov     r13, r8
0x180008c0e  mov     [rsp+2C0h+cbData], 0
0x180008c16  mov     r15, rdx
0x180008c19  mov     rsi, rcx
0x180008c1c  test    rdi, rdi
0x180008c1f  jz      short loc_180008C24
0x180008c21  mov     [rdi], r12d
0x180008c24  mov     ebx, [rbp+1C0h+arg_38]
0x180008c2a  test    ebx, ebx
0x180008c2c  jnz     short loc_180008C3B
0x180008c2e  mov     r8, r15; unsigned __int16 *
0x180008c31  lea     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x180008c36  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180008c3b  lea     rax, [rsp+2C0h+hKey]
0x180008c40  test    ebx, ebx
0x180008c42  lea     rdx, [rsp+2C0h+var_270]
0x180008c47  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180008c4c  cmovnz  rdx, r15; lpSubKey
0x180008c50  mov     r9d, 20019h; samDesired
0x180008c56  xor     r8d, r8d; ulOptions
0x180008c59  mov     rcx, rsi; hKey
0x180008c5c  call    cs:__imp_RegOpenKeyExW
0x180008c62  mov     esi, eax
0x180008c64  test    eax, eax
0x180008c66  jz      short loc_180008CC3
0x180008c68  mov     rax, cs:WPP_GLOBAL_Control
0x180008c6f  lea     rbx, WPP_GLOBAL_Control
0x180008c76  cmp     rax, rbx
0x180008c79  jz      loc_180008E0B
0x180008c7f  test    byte ptr [rax+1Ch], 1
0x180008c83  jz      loc_180008E0B
0x180008c89  cmp     byte ptr [rax+19h], 4
0x180008c8d  jb      loc_180008E0B
0x180008c93  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008c98  lea     rcx, [rsp+2C0h+var_270]
0x180008c9d  mov     dword ptr [rsp+2C0h+lpcbData], esi
0x180008ca1  mov     [rsp+2C0h+phkResult], rcx
0x180008ca6  mov     edx, 0Ch
0x180008cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cb2  mov     r9d, eax
0x180008cb5  mov     rcx, [rcx+10h]
0x180008cb9  call    WPP_SF_DSd
0x180008cbe  jmp     loc_180008E0B
0x180008cc3  mov     eax, [rbp+1C0h+arg_20]
0x180008cc9  lea     r9, [rsp+2C0h+Type]; lpType
0x180008cce  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180008cd3  xor     r8d, r8d; lpReserved
0x180008cd6  mov     [rsp+2C0h+cbData], eax
0x180008cda  mov     rdx, r13; lpValueName
0x180008cdd  lea     rax, [rsp+2C0h+cbData]
0x180008ce2  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180008ce7  mov     [rsp+2C0h+phkResult], r14; lpData
0x180008cec  call    cs:__imp_RegQueryValueExW
0x180008cf2  lea     rbx, WPP_GLOBAL_Control
0x180008cf9  mov     esi, eax
0x180008cfb  test    eax, eax
0x180008cfd  jz      short loc_180008D4B
0x180008cff  mov     rax, cs:WPP_GLOBAL_Control
0x180008d06  cmp     rax, rbx
0x180008d09  jz      loc_180008DC1
0x180008d0f  test    byte ptr [rax+1Ch], 1
0x180008d13  jz      loc_180008DC1
0x180008d19  cmp     byte ptr [rax+19h], 4
0x180008d1d  jb      loc_180008DC1
0x180008d23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d2f  mov     r9d, eax
0x180008d32  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x180008d36  mov     [rsp+2C0h+lpcbData], r13; __int64
0x180008d3b  mov     [rsp+2C0h+phkResult], r15; __int64
0x180008d40  mov     rcx, [rcx+10h]; LoggerHandle
0x180008d44  call    WPP_SF_DSSl
0x180008d49  jmp     short loc_180008DC1
0x180008d4b  mov     esi, [rsp+2C0h+Type]
0x180008d4f  mov     r14d, dword ptr [rbp+1C0h+arg_28]
0x180008d56  mov     eax, [rsp+2C0h+cbData]
0x180008d5a  cmp     esi, r14d
0x180008d5d  jz      short loc_180008DB4
0x180008d5f  cmp     esi, 3
0x180008d62  jnz     short loc_180008D6F
0x180008d64  cmp     r14d, 4
0x180008d68  jnz     short loc_180008D6F
0x180008d6a  cmp     eax, r14d
0x180008d6d  jz      short loc_180008DB4
0x180008d6f  mov     rax, cs:WPP_GLOBAL_Control
0x180008d76  cmp     rax, rbx
0x180008d79  jz      short loc_180008DC1
0x180008d7b  test    byte ptr [rax+1Ch], 1
0x180008d7f  jz      short loc_180008DC1
0x180008d81  cmp     byte ptr [rax+19h], 3
0x180008d85  jb      short loc_180008DC1
0x180008d87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d93  mov     r9d, eax
0x180008d96  mov     dword ptr [rsp+2C0h+var_288], r14d; char
0x180008d9b  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x180008d9f  mov     [rsp+2C0h+lpcbData], r13; __int64
0x180008da4  mov     rcx, [rcx+10h]; LoggerHandle
0x180008da8  mov     [rsp+2C0h+phkResult], r15; __int64
0x180008dad  call    WPP_SF_DSSll
0x180008db2  jmp     short loc_180008DC1
0x180008db4  test    rdi, rdi
0x180008db7  jz      short loc_180008DBB
0x180008db9  mov     [rdi], eax
0x180008dbb  mov     r12d, 1
0x180008dc1  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180008dc6  call    cs:__imp_RegCloseKey
0x180008dcc  mov     edi, eax
0x180008dce  test    eax, eax
0x180008dd0  jz      short loc_180008E0B
0x180008dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dd9  cmp     rcx, rbx
0x180008ddc  jz      short loc_180008E0B
0x180008dde  test    byte ptr [rcx+1Ch], 1
0x180008de2  jz      short loc_180008E0B
0x180008de4  cmp     byte ptr [rcx+19h], 2
0x180008de8  jb      short loc_180008E0B
0x180008dea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008def  mov     rcx, cs:WPP_GLOBAL_Control
0x180008df6  mov     edx, 0Fh
0x180008dfb  mov     r9d, eax
0x180008dfe  mov     dword ptr [rsp+2C0h+phkResult], edi
0x180008e02  mov     rcx, [rcx+10h]
0x180008e06  call    WPP_SF_Dl
0x180008e0b  mov     eax, r12d
0x180008e0e  mov     rcx, [rbp+1C0h+var_50]
0x180008e15  xor     rcx, rsp; StackCookie
0x180008e18  call    __security_check_cookie
0x180008e1d  add     rsp, 288h
0x180008e24  pop     r15
0x180008e26  pop     r14
0x180008e28  pop     r13
0x180008e2a  pop     r12
0x180008e2c  pop     rdi
0x180008e2d  pop     rsi
0x180008e2e  pop     rbx
0x180008e2f  pop     rbp
0x180008e30  retn
```
