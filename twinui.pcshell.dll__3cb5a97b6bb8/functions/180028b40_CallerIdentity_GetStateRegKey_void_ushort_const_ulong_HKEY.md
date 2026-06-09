# CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)

- ea: `0x180028b40`
- end: `0x180028d9a`
- name: `?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z`
- size: `602`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f1f80`
- `0x1803c98b8`

## callees

- `0x180028b40`
- `0x1800290dc`
- `0x18038fec8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028be8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028be8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028bb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028bb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028cbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028cbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028d69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028cfd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028cfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028d2f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180028b76`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180028c87`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180028b76`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180028c87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetStateRegKey(
        CallerIdentity *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        HKEY *a4)
{
  WCHAR *v7; // rbx
  signed int Error; // edi
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rsi
  __int64 v12; // r8
  WCHAR *v13; // rcx
  LSTATUS v14; // eax
  LSTATUS Key; // eax
  HKEY v16; // rcx
  HKEY v17; // rcx
  unsigned __int64 v18; // rsi
  bool v19; // cf
  LSTATUS v20; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-8h] BYREF
  REGSAM samDesired; // [rsp+B0h] [rbp+50h]
  unsigned int v24; // [rsp+B8h] [rbp+58h] BYREF

  samDesired = (unsigned int)a3;
  v7 = 0;
  *a4 = 0;
  v24 = 0;
  if ( (unsigned int)GetSystemAppDataKey(this, 0, 0, &v24) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 && v24 )
    {
      CoTaskMemFree(0);
      v9 = v24;
      v10 = v24 + 1LL;
      if ( v10 >= v24 && (phkResult = 0, is_mul_ok(v10, 2u)) )
      {
        v7 = (WCHAR *)CoTaskMemAlloc(2 * v10);
        Error = v7 == 0 ? 0x8007000E : 0;
        if ( v7 )
        {
          if ( v10 > 0x7FFFFFFF || v9 >= 0x7FFFFFFF )
          {
            *v7 = 0;
          }
          else
          {
            v12 = -1;
            if ( v10 )
              v12 = 0;
            v13 = v7 - 1;
            if ( v10 )
              v13 = v7;
            *v13 = 0;
            if ( v10 )
            {
              v19 = v10 == v12;
              v18 = v10 - v12;
              if ( !v19 && v18 != 1 )
                StringExHandleFillBehindNullW(&v7[v12], 2 * v18, 0x300u);
            }
          }
          hKey = 0;
          if ( (unsigned int)GetSystemAppDataKey(this, &hKey, v7, &v24)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            if ( a2 )
            {
              phkResult = 0;
              v14 = RegOpenKeyExW(hKey, v7, 0, 0x2001Fu, &phkResult);
              Error = v14;
              if ( v14 > 0 )
                Error = (unsigned __int16)v14 | 0x80070000;
              if ( Error >= 0 )
              {
                Key = RegCreateKeyExW(phkResult, a2, 0, 0, 0, samDesired, 0, a4, 0);
                Error = Key;
                if ( Key > 0 )
                  Error = (unsigned __int16)Key | 0x80070000;
              }
              v16 = phkResult;
              phkResult = 0;
              if ( v16 )
                RegCloseKey(v16);
            }
            else
            {
              v20 = RegOpenKeyExW(hKey, v7, 0, samDesired, a4);
              Error = v20;
              if ( v20 > 0 )
                Error = (unsigned __int16)v20 | 0x80070000;
            }
          }
          v17 = hKey;
          hKey = 0;
          if ( v17 )
            RegCloseKey(v17);
        }
      }
      else
      {
        Error = -2147024362;
      }
      CoTaskMemFree(v7);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180028b40  mov     [rsp-38h+arg_0], rbx
0x180028b45  mov     [rsp-38h+arg_10], r8d
0x180028b4a  push    rbp
0x180028b4b  push    rsi
0x180028b4c  push    rdi
0x180028b4d  push    r12
0x180028b4f  push    r13
0x180028b51  push    r14
0x180028b53  push    r15
0x180028b55  mov     rbp, rsp
0x180028b58  sub     rsp, 60h
0x180028b5c  mov     r15, r9
0x180028b5f  mov     r12, rdx
0x180028b62  mov     r13, rcx
0x180028b65  xor     ebx, ebx
0x180028b67  mov     [r9], rbx
0x180028b6a  mov     [rbp+arg_18], ebx
0x180028b6d  lea     r9, [rbp+arg_18]
0x180028b71  xor     r8d, r8d
0x180028b74  xor     edx, edx
0x180028b76  call    cs:__imp_GetSystemAppDataKey
0x180028b7c  test    eax, eax
0x180028b7e  jnz     loc_180028D80
0x180028b84  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180028b89  mov     edi, eax
0x180028b8b  cmp     eax, 8007007Ah
0x180028b90  jnz     short loc_180028BBA
0x180028b92  cmp     [rbp+arg_18], ebx
0x180028b95  jbe     short loc_180028BBA
0x180028b97  xor     ecx, ecx; pv
0x180028b99  call    cs:__imp_CoTaskMemFree
0x180028b9f  mov     r14d, [rbp+arg_18]
0x180028ba3  lea     rsi, [r14+1]
0x180028ba7  cmp     rsi, r14
0x180028baa  jnb     short loc_180028BD4
0x180028bac  mov     edi, 80070216h
0x180028bb1  mov     rcx, rbx; pv
0x180028bb4  call    cs:__imp_CoTaskMemFree
0x180028bba  mov     eax, edi
0x180028bbc  mov     rbx, [rsp+60h+arg_0]
0x180028bc4  add     rsp, 60h
0x180028bc8  pop     r15
0x180028bca  pop     r14
0x180028bcc  pop     r13
0x180028bce  pop     r12
0x180028bd0  pop     rdi
0x180028bd1  pop     rsi
0x180028bd2  pop     rbp
0x180028bd3  retn
0x180028bd4  mov     [rbp+var_8], rbx
0x180028bd8  mov     eax, 2
0x180028bdd  mul     rsi
0x180028be0  test    rdx, rdx
0x180028be3  jnz     short loc_180028BAC
0x180028be5  mov     rcx, rax; cb
0x180028be8  call    cs:__imp_CoTaskMemAlloc
0x180028bee  mov     rbx, rax
0x180028bf1  neg     rax
0x180028bf4  sbb     edi, edi
0x180028bf6  not     edi
0x180028bf8  and     edi, 8007000Eh
0x180028bfe  test    rbx, rbx
0x180028c01  jz      short loc_180028BB1
0x180028c03  mov     eax, 7FFFFFFFh
0x180028c08  cmp     rsi, rax
0x180028c0b  jbe     short loc_180028C16
0x180028c0d  xor     r14d, r14d
0x180028c10  mov     [rbx], r14w
0x180028c14  jmp     short loc_180028C75
0x180028c16  cmp     r14, rax
0x180028c19  jnb     short loc_180028C0D
0x180028c1b  xor     r14d, r14d
0x180028c1e  mov     ecx, r14d
0x180028c21  lea     r8, pvData
0x180028c28  mov     rdx, rsi
0x180028c2b  mov     rax, rbx
0x180028c2e  mov     r9d, r14d
0x180028c31  test    rcx, rcx
0x180028c34  jz      short loc_180028C58
0x180028c36  movzx   r10d, word ptr [r8]
0x180028c3a  test    r10w, r10w
0x180028c3e  jz      short loc_180028C58
0x180028c40  add     r8, 2
0x180028c44  mov     [rax], r10w
0x180028c48  add     rax, 2
0x180028c4c  dec     rcx
0x180028c4f  inc     r9
0x180028c52  sub     rdx, 1
0x180028c56  jnz     short loc_180028C31
0x180028c58  lea     r8, [r9-1]
0x180028c5c  test    rdx, rdx
0x180028c5f  cmovnz  r8, r9
0x180028c63  lea     rcx, [rax-2]
0x180028c67  cmovnz  rcx, rax
0x180028c6b  mov     [rcx], r14w
0x180028c6f  jnz     loc_180028D3B
0x180028c75  mov     [rbp+hKey], r14
0x180028c79  lea     r9, [rbp+arg_18]
0x180028c7d  mov     r8, rbx
0x180028c80  lea     rdx, [rbp+hKey]
0x180028c84  mov     rcx, r13
0x180028c87  call    cs:__imp_GetSystemAppDataKey
0x180028c8d  test    eax, eax
0x180028c8f  jz      loc_180028D8A
0x180028c95  xor     r8d, r8d; ulOptions
0x180028c98  mov     rdx, rbx; lpSubKey
0x180028c9b  mov     rcx, [rbp+hKey]; hKey
0x180028c9f  test    r12, r12
0x180028ca2  jz      loc_180028D60
0x180028ca8  mov     [rbp+var_8], r14
0x180028cac  lea     rax, [rbp+var_8]
0x180028cb0  mov     [rsp+60h+phkResult], rax; phkResult
0x180028cb5  mov     r9d, 2001Fh; samDesired
0x180028cbb  call    cs:__imp_RegOpenKeyExW
0x180028cc1  mov     edi, eax
0x180028cc3  mov     esi, 80070000h
0x180028cc8  test    eax, eax
0x180028cca  jle     short loc_180028CD1
0x180028ccc  movzx   edi, ax
0x180028ccf  or      edi, esi
0x180028cd1  test    edi, edi
0x180028cd3  js      short loc_180028D0E
0x180028cd5  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x180028cda  mov     [rsp+60h+var_28], r15; phkResult
0x180028cdf  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180028ce4  mov     eax, [rbp+arg_10]
0x180028ce7  mov     [rsp+60h+samDesired], eax; samDesired
0x180028ceb  mov     dword ptr [rsp+60h+phkResult], r14d; dwOptions
0x180028cf0  xor     r9d, r9d; lpClass
0x180028cf3  xor     r8d, r8d; Reserved
0x180028cf6  mov     rdx, r12; lpSubKey
0x180028cf9  mov     rcx, [rbp+var_8]; hKey
0x180028cfd  call    cs:__imp_RegCreateKeyExW
0x180028d03  mov     edi, eax
0x180028d05  test    eax, eax
0x180028d07  jle     short loc_180028D0E
0x180028d09  movzx   edi, ax
0x180028d0c  or      edi, esi
0x180028d0e  mov     rcx, [rbp+var_8]; hKey
0x180028d12  mov     [rbp+var_8], r14
0x180028d16  test    rcx, rcx
0x180028d19  jz      short loc_180028D22
0x180028d1b  call    cs:__imp_RegCloseKey
0x180028d21  nop
0x180028d22  mov     rcx, [rbp+hKey]; hKey
0x180028d26  mov     [rbp+hKey], r14
0x180028d2a  test    rcx, rcx
0x180028d2d  jz      short loc_180028D36
0x180028d2f  call    cs:__imp_RegCloseKey
0x180028d35  nop
0x180028d36  jmp     loc_180028BB1
0x180028d3b  sub     rsi, r8
0x180028d3e  cmp     rsi, 1
0x180028d42  jbe     loc_180028C75
0x180028d48  lea     rdx, [rsi+rsi]; cbRemaining
0x180028d4c  lea     rcx, [rbx+r8*2]; pszDestEnd
0x180028d50  mov     r8d, 300h; dwFlags
0x180028d56  call    StringExHandleFillBehindNullW
0x180028d5b  jmp     loc_180028C75
0x180028d60  mov     [rsp+60h+phkResult], r15; phkResult
0x180028d65  mov     r9d, [rbp+arg_10]; samDesired
0x180028d69  call    cs:__imp_RegOpenKeyExW
0x180028d6f  mov     edi, eax
0x180028d71  test    eax, eax
0x180028d73  jle     short loc_180028D22
0x180028d75  movzx   edi, ax
0x180028d78  or      edi, 80070000h
0x180028d7e  jmp     short loc_180028D22
0x180028d80  mov     edi, 8000FFFFh
0x180028d85  jmp     loc_180028BBA
0x180028d8a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180028d8f  mov     edi, eax
0x180028d91  test    eax, eax
0x180028d93  js      short loc_180028D22
0x180028d95  jmp     loc_180028C95
```
