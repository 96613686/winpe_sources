# I_MatchClmdOpt(uchar const *,ushort const *)

- ea: `0x180016890`
- end: `0x180016a2b`
- name: `?I_MatchClmdOpt@@YAKPEBEPEBG@Z`
- size: `411`
- prototype: `unsigned int __fastcall(const unsigned __int8 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002e84`
- `0x18001f340`

## callees

- `0x1800161f4`
- `0x180016890`
- `0x1800195c8`
- `0x18001be10`
- `0x18001e75c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800169ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001694a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001694a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001698f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001698f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016912`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016912`

## pseudocode

```c
__int64 __fastcall I_MatchClmdOpt(const unsigned __int8 *a1, const unsigned __int16 *a2)
{
  int v2; // edi
  BYTE *v4; // rbx
  DWORD v5; // esi
  LSTATUS v6; // r14d
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[256]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  hKey = 0;
  cbData = 255;
  Type = 0;
  cchValueName = 255;
  if ( a1 && a2 )
  {
    v4 = 0;
    v5 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
    {
      while ( !RegEnumValueW(hKey, v5, ValueName, &cchValueName, 0, &Type, 0, 0) )
      {
        if ( Type == 3 )
        {
          v4 = (BYTE *)AllocH(cbData);
          if ( !v4 )
            goto LABEL_13;
          v6 = RegQueryValueExW(hKey, ValueName, 0, 0, v4, &cbData);
          if ( !v6 && AtrCompare(a1, v4, 0, cbData) )
          {
            v2 = 1;
            goto LABEL_13;
          }
          I_CidUtilFreeH(v4);
          v4 = 0;
          cbData = 255;
          cchValueName = 255;
          if ( v6 )
            goto LABEL_13;
        }
        ++v5;
      }
      v4 = 0;
    }
LABEL_13:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v4 )
      I_CidUtilFreeH(v4);
  }
  return 2 * (v2 ^ 1u);
}

```

## disassembly

```asm
0x180016890  mov     [rsp-8+arg_10], rbx
0x180016895  push    rbp
0x180016896  push    rsi
0x180016897  push    rdi
0x180016898  push    r14
0x18001689a  push    r15
0x18001689c  lea     rbp, [rsp-170h]
0x1800168a4  sub     rsp, 270h
0x1800168ab  mov     rax, cs:__security_cookie
0x1800168b2  xor     rax, rsp
0x1800168b5  mov     [rbp+190h+var_30], rax
0x1800168bc  xor     edi, edi
0x1800168be  mov     [rsp+290h+hKey], 0
0x1800168c7  mov     [rsp+290h+cbData], 0FFh
0x1800168cf  mov     r15, rcx
0x1800168d2  mov     [rsp+290h+Type], 0
0x1800168da  mov     [rsp+290h+cchValueName], 0FFh
0x1800168e2  test    rcx, rcx
0x1800168e5  jz      loc_1800169FF
0x1800168eb  test    rdx, rdx
0x1800168ee  jz      loc_1800169FF
0x1800168f4  lea     rax, [rsp+290h+hKey]
0x1800168f9  mov     r9d, 20019h; samDesired
0x1800168ff  xor     r8d, r8d; ulOptions
0x180016902  mov     [rsp+290h+phkResult], rax; phkResult
0x180016907  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001690e  xor     ebx, ebx
0x180016910  xor     esi, esi
0x180016912  call    cs:__imp_RegOpenKeyExW
0x180016918  test    eax, eax
0x18001691a  jnz     loc_1800169E2
0x180016920  mov     rcx, [rsp+290h+hKey]; hKey
0x180016925  lea     rax, [rsp+290h+Type]
0x18001692a  mov     [rsp+290h+lpcbData], rdi; lpcbData
0x18001692f  lea     r9, [rsp+290h+cchValueName]; lpcchValueName
0x180016934  mov     [rsp+290h+lpData], rdi; lpData
0x180016939  lea     r8, [rsp+290h+ValueName]; lpValueName
0x18001693e  mov     [rsp+290h+lpType], rax; lpType
0x180016943  mov     edx, esi; dwIndex
0x180016945  mov     [rsp+290h+phkResult], rdi; lpReserved
0x18001694a  call    cs:__imp_RegEnumValueW
0x180016950  test    eax, eax
0x180016952  jnz     loc_1800169E0
0x180016958  cmp     [rsp+290h+Type], 3
0x18001695d  jnz     short loc_1800169D2
0x18001695f  mov     ecx, [rsp+290h+cbData]; unsigned __int64
0x180016963  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x180016968  mov     rbx, rax
0x18001696b  test    rax, rax
0x18001696e  jz      short loc_1800169E2
0x180016970  mov     rcx, [rsp+290h+hKey]; hKey
0x180016975  lea     rax, [rsp+290h+cbData]
0x18001697a  mov     [rsp+290h+lpType], rax; lpcbData
0x18001697f  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x180016984  xor     r9d, r9d; lpType
0x180016987  mov     [rsp+290h+phkResult], rbx; lpData
0x18001698c  xor     r8d, r8d; lpReserved
0x18001698f  call    cs:__imp_RegQueryValueExW
0x180016995  mov     r14d, eax
0x180016998  test    eax, eax
0x18001699a  jnz     short loc_1800169B3
0x18001699c  mov     r9d, [rsp+290h+cbData]; unsigned int
0x1800169a1  xor     r8d, r8d; unsigned __int8 *
0x1800169a4  mov     rdx, rbx; unsigned __int8 *
0x1800169a7  mov     rcx, r15; unsigned __int8 *
0x1800169aa  call    ?AtrCompare@@YAHPEBE00K@Z; AtrCompare(uchar const *,uchar const *,uchar const *,ulong)
0x1800169af  test    eax, eax
0x1800169b1  jnz     short loc_1800169D9
0x1800169b3  mov     rcx, rbx
0x1800169b6  call    I_CidUtilFreeH
0x1800169bb  xor     ebx, ebx
0x1800169bd  mov     [rsp+290h+cbData], 0FFh
0x1800169c5  mov     [rsp+290h+cchValueName], 0FFh
0x1800169cd  test    r14d, r14d
0x1800169d0  jnz     short loc_1800169E2
0x1800169d2  inc     esi
0x1800169d4  jmp     loc_180016920
0x1800169d9  mov     edi, 1
0x1800169de  jmp     short loc_1800169E2
0x1800169e0  xor     ebx, ebx
0x1800169e2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800169e7  test    rcx, rcx
0x1800169ea  jz      short loc_1800169F2
0x1800169ec  call    cs:__imp_RegCloseKey
0x1800169f2  test    rbx, rbx
0x1800169f5  jz      short loc_1800169FF
0x1800169f7  mov     rcx, rbx
0x1800169fa  call    I_CidUtilFreeH
0x1800169ff  xor     edi, 1
0x180016a02  lea     eax, [rdi+rdi]
0x180016a05  mov     rcx, [rbp+190h+var_30]
0x180016a0c  xor     rcx, rsp; StackCookie
0x180016a0f  call    __security_check_cookie
0x180016a14  mov     rbx, [rsp+290h+arg_10]
0x180016a1c  add     rsp, 270h
0x180016a23  pop     r15
0x180016a25  pop     r14
0x180016a27  pop     rdi
0x180016a28  pop     rsi
0x180016a29  pop     rbp
0x180016a2a  retn
```
