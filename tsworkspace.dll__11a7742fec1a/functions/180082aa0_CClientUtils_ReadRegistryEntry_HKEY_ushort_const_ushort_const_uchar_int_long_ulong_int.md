# CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)

- ea: `0x180082aa0`
- end: `0x180082d11`
- name: `?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, LPBYTE lpData, int, char, unsigned int *, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180082870`
- `0x180082d20`
- `0x180082d80`
- `0x180083050`
- `0x180083260`
- `0x1800836a0`
- `0x180083820`

## callees

- `0x18000b1d8`
- `0x1800824b4`
- `0x180082aa0`
- `0x1800843bc`
- `0x18008449c`
- `0x180084594`
- `0x180084634`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180082bcc`
- `ADVAPI32!RegQueryValueExW` at `0x180082bcc`
- `ADVAPI32!RegCloseKey` at `0x180082ca6`
- `ADVAPI32!RegCloseKey` at `0x180082ca6`
- `ADVAPI32!RegOpenKeyExW` at `0x180082b3c`
- `ADVAPI32!RegOpenKeyExW` at `0x180082b3c`

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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v17, CurrentThreadActivityIdPrefix, (__int64)v28, v15);
    }
  }
  else
  {
    cbData = a5;
    v18 = RegQueryValueExW(hKeya, a3, 0, &Type, lpData, &cbData);
    v19 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
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
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSll(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v20, a6);
      }
    }
    v21 = RegCloseKey(hKeya);
    if ( v21
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
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
0x180082aa0  push    rbp
0x180082aa2  push    rbx
0x180082aa3  push    rsi
0x180082aa4  push    rdi
0x180082aa5  push    r12
0x180082aa7  push    r13
0x180082aa9  push    r14
0x180082aab  push    r15
0x180082aad  lea     rbp, [rsp-188h]
0x180082ab5  sub     rsp, 288h
0x180082abc  mov     rax, cs:__security_cookie
0x180082ac3  xor     rax, rsp
0x180082ac6  mov     [rbp+1C0h+var_50], rax
0x180082acd  mov     rdi, [rbp+1C0h+arg_30]
0x180082ad4  xor     r12d, r12d
0x180082ad7  mov     [rsp+2C0h+hKey], 0
0x180082ae0  mov     r14, r9
0x180082ae3  mov     [rsp+2C0h+Type], 0
0x180082aeb  mov     r13, r8
0x180082aee  mov     [rsp+2C0h+cbData], 0
0x180082af6  mov     r15, rdx
0x180082af9  mov     rsi, rcx
0x180082afc  test    rdi, rdi
0x180082aff  jz      short loc_180082B04
0x180082b01  mov     [rdi], r12d
0x180082b04  mov     ebx, [rbp+1C0h+arg_38]
0x180082b0a  test    ebx, ebx
0x180082b0c  jnz     short loc_180082B1B
0x180082b0e  mov     r8, r15; unsigned __int16 *
0x180082b11  lea     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x180082b16  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180082b1b  lea     rax, [rsp+2C0h+hKey]
0x180082b20  test    ebx, ebx
0x180082b22  lea     rdx, [rsp+2C0h+var_270]
0x180082b27  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180082b2c  cmovnz  rdx, r15; lpSubKey
0x180082b30  mov     r9d, 20019h; samDesired
0x180082b36  xor     r8d, r8d; ulOptions
0x180082b39  mov     rcx, rsi; hKey
0x180082b3c  call    cs:__imp_RegOpenKeyExW
0x180082b42  mov     esi, eax
0x180082b44  test    eax, eax
0x180082b46  jz      short loc_180082BA3
0x180082b48  mov     rax, cs:WPP_GLOBAL_Control
0x180082b4f  lea     rbx, WPP_GLOBAL_Control
0x180082b56  cmp     rax, rbx
0x180082b59  jz      loc_180082CEB
0x180082b5f  test    byte ptr [rax+1Ch], 1
0x180082b63  jz      loc_180082CEB
0x180082b69  cmp     byte ptr [rax+19h], 4
0x180082b6d  jb      loc_180082CEB
0x180082b73  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082b78  lea     rcx, [rsp+2C0h+var_270]
0x180082b7d  mov     dword ptr [rsp+2C0h+lpcbData], esi
0x180082b81  mov     [rsp+2C0h+phkResult], rcx
0x180082b86  mov     edx, 0Ch
0x180082b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b92  mov     r9d, eax
0x180082b95  mov     rcx, [rcx+10h]
0x180082b99  call    WPP_SF_DSl
0x180082b9e  jmp     loc_180082CEB
0x180082ba3  mov     eax, [rbp+1C0h+arg_20]
0x180082ba9  lea     r9, [rsp+2C0h+Type]; lpType
0x180082bae  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180082bb3  xor     r8d, r8d; lpReserved
0x180082bb6  mov     [rsp+2C0h+cbData], eax
0x180082bba  mov     rdx, r13; lpValueName
0x180082bbd  lea     rax, [rsp+2C0h+cbData]
0x180082bc2  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180082bc7  mov     [rsp+2C0h+phkResult], r14; lpData
0x180082bcc  call    cs:__imp_RegQueryValueExW
0x180082bd2  lea     rbx, WPP_GLOBAL_Control
0x180082bd9  mov     esi, eax
0x180082bdb  test    eax, eax
0x180082bdd  jz      short loc_180082C2B
0x180082bdf  mov     rax, cs:WPP_GLOBAL_Control
0x180082be6  cmp     rax, rbx
0x180082be9  jz      loc_180082CA1
0x180082bef  test    byte ptr [rax+1Ch], 1
0x180082bf3  jz      loc_180082CA1
0x180082bf9  cmp     byte ptr [rax+19h], 4
0x180082bfd  jb      loc_180082CA1
0x180082c03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c0f  mov     r9d, eax
0x180082c12  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x180082c16  mov     [rsp+2C0h+lpcbData], r13; __int64
0x180082c1b  mov     [rsp+2C0h+phkResult], r15; __int64
0x180082c20  mov     rcx, [rcx+10h]; LoggerHandle
0x180082c24  call    WPP_SF_DSSl
0x180082c29  jmp     short loc_180082CA1
0x180082c2b  mov     esi, [rsp+2C0h+Type]
0x180082c2f  mov     r14d, dword ptr [rbp+1C0h+arg_28]
0x180082c36  mov     eax, [rsp+2C0h+cbData]
0x180082c3a  cmp     esi, r14d
0x180082c3d  jz      short loc_180082C94
0x180082c3f  cmp     esi, 3
0x180082c42  jnz     short loc_180082C4F
0x180082c44  cmp     r14d, 4
0x180082c48  jnz     short loc_180082C4F
0x180082c4a  cmp     eax, r14d
0x180082c4d  jz      short loc_180082C94
0x180082c4f  mov     rax, cs:WPP_GLOBAL_Control
0x180082c56  cmp     rax, rbx
0x180082c59  jz      short loc_180082CA1
0x180082c5b  test    byte ptr [rax+1Ch], 1
0x180082c5f  jz      short loc_180082CA1
0x180082c61  cmp     byte ptr [rax+19h], 3
0x180082c65  jb      short loc_180082CA1
0x180082c67  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c73  mov     r9d, eax
0x180082c76  mov     dword ptr [rsp+2C0h+var_288], r14d; char
0x180082c7b  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x180082c7f  mov     [rsp+2C0h+lpcbData], r13; __int64
0x180082c84  mov     rcx, [rcx+10h]; LoggerHandle
0x180082c88  mov     [rsp+2C0h+phkResult], r15; __int64
0x180082c8d  call    WPP_SF_DSSll
0x180082c92  jmp     short loc_180082CA1
0x180082c94  test    rdi, rdi
0x180082c97  jz      short loc_180082C9B
0x180082c99  mov     [rdi], eax
0x180082c9b  mov     r12d, 1
0x180082ca1  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180082ca6  call    cs:__imp_RegCloseKey
0x180082cac  mov     edi, eax
0x180082cae  test    eax, eax
0x180082cb0  jz      short loc_180082CEB
0x180082cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180082cb9  cmp     rcx, rbx
0x180082cbc  jz      short loc_180082CEB
0x180082cbe  test    byte ptr [rcx+1Ch], 1
0x180082cc2  jz      short loc_180082CEB
0x180082cc4  cmp     byte ptr [rcx+19h], 2
0x180082cc8  jb      short loc_180082CEB
0x180082cca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180082cd6  mov     edx, 0Fh
0x180082cdb  mov     r9d, eax
0x180082cde  mov     dword ptr [rsp+2C0h+phkResult], edi
0x180082ce2  mov     rcx, [rcx+10h]
0x180082ce6  call    WPP_SF_Dl
0x180082ceb  mov     eax, r12d
0x180082cee  mov     rcx, [rbp+1C0h+var_50]
0x180082cf5  xor     rcx, rsp; StackCookie
0x180082cf8  call    __security_check_cookie
0x180082cfd  add     rsp, 288h
0x180082d04  pop     r15
0x180082d06  pop     r14
0x180082d08  pop     r13
0x180082d0a  pop     r12
0x180082d0c  pop     rdi
0x180082d0d  pop     rsi
0x180082d0e  pop     rbx
0x180082d0f  pop     rbp
0x180082d10  retn
```
