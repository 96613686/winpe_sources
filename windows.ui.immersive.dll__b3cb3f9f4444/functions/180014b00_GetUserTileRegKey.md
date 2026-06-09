# GetUserTileRegKey

- ea: `0x180014b00`
- end: `0x180014ceb`
- name: `GetUserTileRegKey`
- size: `491`
- prototype: `__int64 __fastcall(LPCWSTR psz, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003afc0`
- `0x18004bf90`
- `0x1800d1620`
- `0x1800d17f0`
- `0x1800d1ae8`

## callees

- `0x180014b00`
- `0x1800156f0`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014c62`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014ba9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014cd8`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014ba9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c7e`

## pseudocode

```c
__int64 __fastcall GetUserTileRegKey(LPCWSTR psz, REGSAM samDesired, PHKEY phkResult)
{
  WCHAR *v3; // r9
  __int64 v4; // rdi
  __int64 v5; // rbx
  const wchar_t *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  WCHAR *v12; // rdx
  int v13; // esi
  HRESULT CurrentUsersSidString; // eax
  WCHAR *v15; // rax
  LPWSTR v16; // rcx
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  LPWSTR v19; // rcx
  LSTATUS v20; // eax
  WCHAR *v21; // rcx
  LPWSTR ppwsz; // [rsp+30h] [rbp-258h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-250h] BYREF
  WCHAR psza[260]; // [rsp+40h] [rbp-248h] BYREF
  _BYTE v26[8]; // [rsp+248h] [rbp-40h] BYREF

  v3 = psza;
  v4 = 2147483646;
  *phkResult = 0;
  v5 = 260;
  lpSubKey = 0;
  v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
  v10 = 260;
  v11 = 2147483646;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v3++ = *v9++;
    --v11;
    --v10;
  }
  while ( v10 );
  v12 = v3 - 1;
  v13 = -2147024774;
  if ( v10 )
  {
    v12 = v3;
    v13 = 0;
  }
  *v12 = 0;
  if ( v10 )
  {
    ppwsz = 0;
    if ( psz )
      CurrentUsersSidString = SHStrDupW(psz, &ppwsz);
    else
      CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
    v13 = CurrentUsersSidString;
    if ( CurrentUsersSidString >= 0 )
    {
      v15 = psza;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v5;
      }
      while ( v5 );
      v13 = -2147024809;
      if ( v5 )
      {
        v16 = ppwsz;
        v17 = &v26[-2 * v5];
        do
        {
          if ( !v4 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v4;
          --v5;
        }
        while ( v5 );
        v18 = v17 - 1;
        v13 = -2147024774;
        if ( v5 )
        {
          v18 = v17;
          v13 = 0;
        }
        *v18 = 0;
        if ( v5 )
          v13 = SHStrDupW(psza, (LPWSTR *)&lpSubKey);
      }
    }
    v19 = ppwsz;
    ppwsz = 0;
    CoTaskMemFree(v19);
    if ( v13 >= 0 )
    {
      v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, samDesired, phkResult);
      v13 = v20;
      if ( v20 > 0 )
        v13 = (unsigned __int16)v20 | 0x80070000;
    }
  }
  v21 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  CoTaskMemFree(v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180014b00  mov     [rsp+arg_18], rbx
0x180014b05  push    rbp
0x180014b06  push    rsi
0x180014b07  push    rdi
0x180014b08  push    r14
0x180014b0a  push    r15
0x180014b0c  sub     rsp, 260h
0x180014b13  mov     rax, cs:__security_cookie
0x180014b1a  xor     rax, rsp
0x180014b1d  mov     [rsp+288h+var_38], rax
0x180014b25  xor     r15d, r15d
0x180014b28  lea     r9, [rsp+288h+psz]
0x180014b2d  mov     edi, 7FFFFFFEh
0x180014b32  mov     [r8], r15
0x180014b35  mov     ebx, 104h
0x180014b3a  mov     [rsp+288h+lpSubKey], r15
0x180014b3f  mov     r14, r8
0x180014b42  mov     ebp, edx
0x180014b44  mov     r10, rcx
0x180014b47  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014b4e  mov     r8d, ebx
0x180014b51  mov     ecx, edi
0x180014b53  test    rcx, rcx
0x180014b56  jz      short loc_180014B75
0x180014b58  movzx   eax, word ptr [rdx]
0x180014b5b  test    ax, ax
0x180014b5e  jz      short loc_180014B75
0x180014b60  mov     [r9], ax
0x180014b64  add     rdx, 2
0x180014b68  add     r9, 2
0x180014b6c  dec     rcx
0x180014b6f  sub     r8, 1
0x180014b73  jnz     short loc_180014B53
0x180014b75  test    r8, r8
0x180014b78  lea     rdx, [r9-2]
0x180014b7c  mov     esi, 8007007Ah
0x180014b81  cmovnz  rdx, r9
0x180014b85  cmovnz  esi, r15d
0x180014b89  mov     [rdx], r15w
0x180014b8d  jz      loc_180014C74
0x180014b93  mov     [rsp+288h+ppwsz], r15
0x180014b98  test    r10, r10
0x180014b9b  jz      loc_180014CBF
0x180014ba1  lea     rdx, [rsp+288h+ppwsz]; ppwsz
0x180014ba6  mov     rcx, r10; psz
0x180014ba9  call    cs:__imp_SHStrDupW
0x180014bb0  nop     dword ptr [rax+rax+00h]
0x180014bb5  mov     esi, eax
0x180014bb7  test    eax, eax
0x180014bb9  js      short loc_180014C31
0x180014bbb  lea     rax, [rsp+288h+psz]
0x180014bc0  cmp     [rax], r15w
0x180014bc4  jz      short loc_180014BD0
0x180014bc6  add     rax, 2
0x180014bca  sub     rbx, 1
0x180014bce  jnz     short loc_180014BC0
0x180014bd0  test    rbx, rbx
0x180014bd3  mov     esi, 80070057h
0x180014bd8  cmovnz  esi, r15d
0x180014bdc  jz      short loc_180014C31
0x180014bde  mov     rcx, [rsp+288h+ppwsz]
0x180014be3  lea     rax, [rbx+rbx]
0x180014be7  lea     rdx, [rsp+288h+var_40]
0x180014bef  sub     rdx, rax
0x180014bf2  test    rdi, rdi
0x180014bf5  jz      short loc_180014C13
0x180014bf7  movzx   eax, word ptr [rcx]
0x180014bfa  test    ax, ax
0x180014bfd  jz      short loc_180014C13
0x180014bff  mov     [rdx], ax
0x180014c02  add     rcx, 2
0x180014c06  add     rdx, 2
0x180014c0a  dec     rdi
0x180014c0d  sub     rbx, 1
0x180014c11  jnz     short loc_180014BF2
0x180014c13  test    rbx, rbx
0x180014c16  lea     rcx, [rdx-2]
0x180014c1a  mov     esi, 8007007Ah
0x180014c1f  cmovnz  rcx, rdx
0x180014c23  cmovnz  esi, r15d
0x180014c27  mov     [rcx], r15w
0x180014c2b  jnz     loc_180014CCE
0x180014c31  mov     rcx, [rsp+288h+ppwsz]; pv
0x180014c36  mov     [rsp+288h+ppwsz], r15
0x180014c3b  call    cs:__imp_CoTaskMemFree
0x180014c42  nop     dword ptr [rax+rax+00h]
0x180014c47  test    esi, esi
0x180014c49  js      short loc_180014C74
0x180014c4b  mov     rdx, [rsp+288h+lpSubKey]; lpSubKey
0x180014c50  mov     r9d, ebp; samDesired
0x180014c53  xor     r8d, r8d; ulOptions
0x180014c56  mov     [rsp+288h+phkResult], r14; phkResult
0x180014c5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014c62  call    cs:__imp_RegOpenKeyExW
0x180014c69  nop     dword ptr [rax+rax+00h]
0x180014c6e  mov     esi, eax
0x180014c70  test    eax, eax
0x180014c72  jg      short loc_180014CB4
0x180014c74  mov     rcx, [rsp+288h+lpSubKey]; pv
0x180014c79  mov     [rsp+288h+lpSubKey], r15
0x180014c7e  call    cs:__imp_CoTaskMemFree
0x180014c85  nop     dword ptr [rax+rax+00h]
0x180014c8a  mov     eax, esi
0x180014c8c  mov     rcx, [rsp+288h+var_38]
0x180014c94  xor     rcx, rsp; StackCookie
0x180014c97  call    __security_check_cookie
0x180014c9c  mov     rbx, [rsp+288h+arg_18]
0x180014ca4  add     rsp, 260h
0x180014cab  pop     r15
0x180014cad  pop     r14
0x180014caf  pop     rdi
0x180014cb0  pop     rsi
0x180014cb1  pop     rbp
0x180014cb2  retn
0x180014cb4  movzx   esi, ax
0x180014cb7  or      esi, 80070000h
0x180014cbd  jmp     short loc_180014C74
0x180014cbf  lea     rcx, [rsp+288h+ppwsz]; ppwsz
0x180014cc4  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180014cc9  jmp     loc_180014BB5
0x180014cce  lea     rdx, [rsp+288h+lpSubKey]; ppwsz
0x180014cd3  lea     rcx, [rsp+288h+psz]; psz
0x180014cd8  call    cs:__imp_SHStrDupW
0x180014cdf  nop     dword ptr [rax+rax+00h]
0x180014ce4  mov     esi, eax
0x180014ce6  jmp     loc_180014C31
```
