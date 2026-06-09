# GetClsIDInfo(_GUID *,ulong,ulong *)

- ea: `0x1800f0924`
- end: `0x1800f0b25`
- name: `?GetClsIDInfo@@YAJPEAU_GUID@@KPEAK@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009d048`
- `0x18009d790`
- `0x1800ad0c4`

## callees

- `0x18002fee0`
- `0x18004d7f0`
- `0x18005e1c0`
- `0x180079578`
- `0x1800f0924`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f09dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f0a15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f09dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800f0a15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f0a6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f0ab9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f0a6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800f0ab9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f0a2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f0ad7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f0a2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f0ad7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f0957`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800f0957`

## string_xrefs

- `0x1800f099c`: `CLSID\`

## pseudocode

```c
__int64 __fastcall GetClsIDInfo(struct _GUID *a1, __int64 a2, unsigned int *a3)
{
  char *v4; // rdx
  __int64 v5; // r8
  char *v6; // rsi
  unsigned int v7; // edi
  unsigned int v8; // r10d
  int v9; // r15d
  LSTATUS ValueA; // eax
  int v11; // ebx
  int v12; // r15d
  DWORD pcbData; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-51h] BYREF
  CHAR SubKey[48]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pvData[64]; // [rsp+90h] [rbp-19h] BYREF

  lpsz = 0;
  StringFromCLSID(a1, &lpsz);
  if ( lpsz && (v6 = SzW2ADynamic(lpsz, v4, v5, 1), operator delete(lpsz), v6) )
  {
    hKey = 0;
    pcbData = 0;
    v7 = -2147467259;
    StringCchCopyA(SubKey, 0x2Fu, "CLSID\\");
    StringCchCatA(SubKey, v8, v6);
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey) )
    {
      phkResult = 0;
      v9 = 0;
      if ( !RegOpenKeyExA(hKey, "InprocServer32", 0, 0x2000000u, &phkResult) )
      {
        v9 = 3;
        RegCloseKey(phkResult);
      }
      pcbData = 64;
      ValueA = RegGetValueA(hKey, "LocalServer32", 0, 0x10000006u, 0, pvData, &pcbData);
      pcbData = 64;
      v11 = v9 | 4;
      if ( ValueA )
        v11 = v9;
      v12 = v11 | 0x100;
      if ( RegGetValueA(hKey, "DocObject", 0, 0x10000006u, 0, pvData, &pcbData) )
        v12 = v11;
      RegCloseKey(hKey);
      if ( v12 )
      {
        v7 = 0;
        *a3 = v12;
      }
    }
    operator delete(v6);
  }
  else
  {
    v7 = -2147024882;
    *a3 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800f0924  mov     [rsp-8+arg_8], rbx
0x1800f0929  push    rbp
0x1800f092a  push    rsi
0x1800f092b  push    rdi
0x1800f092c  push    r14
0x1800f092e  push    r15
0x1800f0930  lea     rbp, [rsp-37h]
0x1800f0935  sub     rsp, 0E0h
0x1800f093c  mov     rax, cs:__security_cookie
0x1800f0943  xor     rax, rsp
0x1800f0946  mov     [rbp+57h+var_30], rax
0x1800f094a  xor     ebx, ebx
0x1800f094c  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800f0950  mov     [rbp+57h+lpsz], rbx
0x1800f0954  mov     r14, r8
0x1800f0957  call    cs:__imp_StringFromCLSID
0x1800f095e  nop     dword ptr [rax+rax+00h]
0x1800f0963  mov     rcx, [rbp+57h+lpsz]; lpWideCharStr
0x1800f0967  test    rcx, rcx
0x1800f096a  jz      loc_1800F0AF7
0x1800f0970  lea     r9d, [rbx+1]; int
0x1800f0974  call    ?SzW2ADynamic@@YAPEADPEBGPEADHH@Z; SzW2ADynamic(ushort const *,char *,int,int)
0x1800f0979  mov     rcx, [rbp+57h+lpsz]; void *
0x1800f097d  mov     rsi, rax
0x1800f0980  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0985  test    rsi, rsi
0x1800f0988  jz      loc_1800F0AF7
0x1800f098e  lea     r10d, [rbx+2Fh]
0x1800f0992  mov     [rbp+57h+hKey], rbx
0x1800f0996  mov     edx, r10d; unsigned __int64
0x1800f0999  mov     [rbp+57h+var_C0], ebx
0x1800f099c  lea     r8, aClsid_4; "CLSID\\"
0x1800f09a3  mov     edi, 80004005h
0x1800f09a8  lea     rcx, [rbp+57h+SubKey]; char *
0x1800f09ac  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800f09b1  mov     r8, rsi; char *
0x1800f09b4  lea     rcx, [rbp+57h+SubKey]; char *
0x1800f09b8  mov     edx, r10d; unsigned __int64
0x1800f09bb  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800f09c0  lea     rax, [rbp+57h+hKey]
0x1800f09c4  mov     r9d, 2000000h; samDesired
0x1800f09ca  xor     r8d, r8d; ulOptions
0x1800f09cd  mov     [rsp+100h+phkResult], rax; phkResult
0x1800f09d2  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800f09d6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800f09dd  call    cs:__imp_RegOpenKeyExA
0x1800f09e4  nop     dword ptr [rax+rax+00h]
0x1800f09e9  test    eax, eax
0x1800f09eb  jnz     loc_1800F0AED
0x1800f09f1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800f09f5  lea     rax, [rbp+57h+var_A8]
0x1800f09f9  mov     r9d, 2000000h; samDesired
0x1800f09ff  mov     [rsp+100h+phkResult], rax; phkResult
0x1800f0a04  xor     r8d, r8d; ulOptions
0x1800f0a07  mov     [rbp+57h+var_A8], rbx
0x1800f0a0b  lea     rdx, aInprocserver32_1; "InprocServer32"
0x1800f0a12  mov     r15d, ebx
0x1800f0a15  call    cs:__imp_RegOpenKeyExA
0x1800f0a1c  nop     dword ptr [rax+rax+00h]
0x1800f0a21  test    eax, eax
0x1800f0a23  jnz     short loc_1800F0A39
0x1800f0a25  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800f0a29  lea     r15d, [rbx+3]
0x1800f0a2d  call    cs:__imp_RegCloseKey
0x1800f0a34  nop     dword ptr [rax+rax+00h]
0x1800f0a39  mov     rcx, [rbp+57h+hKey]; hkey
0x1800f0a3d  lea     rax, [rbp+57h+var_C0]
0x1800f0a41  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f0a46  lea     rdx, aLocalserver32_0; "LocalServer32"
0x1800f0a4d  lea     rax, [rbp+57h+var_70]
0x1800f0a51  mov     [rbp+57h+var_C0], 40h ; '@'
0x1800f0a58  mov     [rsp+100h+pvData], rax; pvData
0x1800f0a5d  mov     r9d, 10000006h; dwFlags
0x1800f0a63  xor     r8d, r8d; lpValue
0x1800f0a66  mov     [rsp+100h+phkResult], rbx; pdwType
0x1800f0a6b  call    cs:__imp_RegGetValueA
0x1800f0a72  nop     dword ptr [rax+rax+00h]
0x1800f0a77  mov     rcx, [rbp+57h+hKey]; hkey
0x1800f0a7b  lea     rdx, aDocobject; "DocObject"
0x1800f0a82  mov     ebx, r15d
0x1800f0a85  mov     [rbp+57h+var_C0], 40h ; '@'
0x1800f0a8c  or      ebx, 4
0x1800f0a8f  mov     r9d, 10000006h; dwFlags
0x1800f0a95  test    eax, eax
0x1800f0a97  lea     rax, [rbp+57h+var_C0]
0x1800f0a9b  mov     [rsp+100h+pcbData], rax; pcbData
0x1800f0aa0  lea     rax, [rbp+57h+var_70]
0x1800f0aa4  cmovnz  ebx, r15d
0x1800f0aa8  mov     [rsp+100h+pvData], rax; pvData
0x1800f0aad  xor     r8d, r8d; lpValue
0x1800f0ab0  mov     [rsp+100h+phkResult], 0; pdwType
0x1800f0ab9  call    cs:__imp_RegGetValueA
0x1800f0ac0  nop     dword ptr [rax+rax+00h]
0x1800f0ac5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800f0ac9  mov     r15d, ebx
0x1800f0acc  bts     r15d, 8
0x1800f0ad1  test    eax, eax
0x1800f0ad3  cmovnz  r15d, ebx
0x1800f0ad7  call    cs:__imp_RegCloseKey
0x1800f0ade  nop     dword ptr [rax+rax+00h]
0x1800f0ae3  test    r15d, r15d
0x1800f0ae6  jz      short loc_1800F0AED
0x1800f0ae8  xor     edi, edi
0x1800f0aea  mov     [r14], r15d
0x1800f0aed  mov     rcx, rsi; void *
0x1800f0af0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f0af5  jmp     short loc_1800F0AFF
0x1800f0af7  mov     edi, 8007000Eh
0x1800f0afc  mov     [r14], ebx
0x1800f0aff  mov     eax, edi
0x1800f0b01  mov     rcx, [rbp+57h+var_30]
0x1800f0b05  xor     rcx, rsp; StackCookie
0x1800f0b08  call    __security_check_cookie
0x1800f0b0d  mov     rbx, [rsp+100h+arg_8]
0x1800f0b15  add     rsp, 0E0h
0x1800f0b1c  pop     r15
0x1800f0b1e  pop     r14
0x1800f0b20  pop     rdi
0x1800f0b21  pop     rsi
0x1800f0b22  pop     rbp
0x1800f0b23  retn
```
