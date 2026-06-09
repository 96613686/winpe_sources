# CRegCRC::ComputeTreeCRC(HKEY__ *,ulong,ulong &)

- ea: `0x180013bb4`
- end: `0x180013d48`
- name: `?ComputeTreeCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013bb4`
- `0x180013ec0`

## callees

- `0x180009ef0`
- `0x1800138b4`
- `0x180013a68`
- `0x180013bb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013ca6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013ca6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013cf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013c27`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013c27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013cb3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013cfd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013cb3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013cfd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013c71`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013c71`

## pseudocode

```c
__int64 __fastcall CRegCRC::ComputeTreeCRC(HKEY a1, unsigned int a2, unsigned int *a3)
{
  __int64 result; // rax
  LSTATUS v6; // eax
  DWORD i; // edi
  DWORD v8; // ebx
  WCHAR *v9; // rax
  WCHAR *v10; // rsi
  __int64 v11; // rdx
  LSTATUS v12; // ebx
  DWORD cchName; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF
  DWORD cSubKeys; // [rsp+B8h] [rbp+48h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C0h] [rbp+50h] BYREF
  DWORD v17; // [rsp+C8h] [rbp+58h] BYREF

  *a3 = a2;
  result = CRegCRC::ComputeKeyValuesCRC(a1, a2, a3);
  if ( (int)result >= 0 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v6 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v6 || v6 == 122 )
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        v17 = cbMaxSubKeyLen;
        SafeInt<unsigned long>::operator+=<int>(&v17);
        v8 = v17;
        v9 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v17, 2u));
        v10 = v9;
        if ( !v9 )
          return 2147749894LL;
        cchName = v8;
        if ( RegEnumKeyExW(a1, i, v9, &cchName, 0, 0, 0, 0) )
        {
          CWin32DefaultArena::WbemMemFree(v10);
        }
        else
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          *a3 = UpdateCRC32((unsigned __int8 *)v10, v11, *a3);
          hKey = 0;
          v12 = RegOpenKeyExW(a1, v10, 0, 0x20019u, &hKey);
          CWin32DefaultArena::WbemMemFree(v10);
          if ( !v12 )
          {
            CRegCRC::ComputeTreeCRC(hKey, *a3, a3);
            RegCloseKey(hKey);
          }
        }
      }
      return 0;
    }
    else
    {
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013bb4  mov     [rsp-38h+arg_0], rbx
0x180013bb9  push    rbp
0x180013bba  push    rsi
0x180013bbb  push    rdi
0x180013bbc  push    r12
0x180013bbe  push    r13
0x180013bc0  push    r14
0x180013bc2  push    r15
0x180013bc4  mov     rbp, rsp
0x180013bc7  sub     rsp, 70h
0x180013bcb  mov     r14, r8
0x180013bce  mov     [r8], edx
0x180013bd1  mov     r15, rcx
0x180013bd4  call    ?ComputeKeyValuesCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z; CRegCRC::ComputeKeyValuesCRC(HKEY__ *,ulong,ulong &)
0x180013bd9  xor     r12d, r12d
0x180013bdc  test    eax, eax
0x180013bde  js      loc_180013D30
0x180013be4  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180013be9  lea     rax, [rbp+cbMaxSubKeyLen]
0x180013bed  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180013bf2  xor     r9d, r9d; lpReserved
0x180013bf5  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180013bfa  xor     r8d, r8d; lpcchClass
0x180013bfd  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180013c02  xor     edx, edx; lpClass
0x180013c04  mov     [rsp+70h+lpcValues], r12; lpcValues
0x180013c09  mov     rcx, r15; hKey
0x180013c0c  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180013c11  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013c16  lea     rax, [rbp+cSubKeys]
0x180013c1a  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x180013c1f  mov     [rbp+cSubKeys], r12d
0x180013c23  mov     [rbp+cbMaxSubKeyLen], r12d
0x180013c27  call    cs:__imp_RegQueryInfoKeyW
0x180013c2d  test    eax, eax
0x180013c2f  jz      short loc_180013C40
0x180013c31  cmp     eax, 7Ah ; 'z'
0x180013c34  jz      short loc_180013C40
0x180013c36  mov     eax, 80004005h
0x180013c3b  jmp     loc_180013D30
0x180013c40  mov     edi, r12d
0x180013c43  or      r13, 0FFFFFFFFFFFFFFFFh
0x180013c47  cmp     edi, [rbp+cSubKeys]
0x180013c4a  jnb     loc_180013D2E
0x180013c50  mov     eax, [rbp+cbMaxSubKeyLen]
0x180013c53  lea     rcx, [rbp+arg_18]
0x180013c57  mov     [rbp+arg_18], eax
0x180013c5a  call    ??$?YH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator+=<int>(int)
0x180013c5f  mov     ebx, [rbp+arg_18]
0x180013c62  mov     eax, 2
0x180013c67  mul     rbx
0x180013c6a  cmovb   rax, r13
0x180013c6e  mov     rcx, rax
0x180013c71  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013c77  mov     rsi, rax
0x180013c7a  test    rax, rax
0x180013c7d  jz      loc_180013D27
0x180013c83  mov     [rsp+70h+lpcValues], r12; lpftLastWriteTime
0x180013c88  lea     r9, [rbp+cchName]; lpcchName
0x180013c8c  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcchClass
0x180013c91  mov     r8, rax; lpName
0x180013c94  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpClass
0x180013c99  mov     edx, edi; dwIndex
0x180013c9b  mov     rcx, r15; hKey
0x180013c9e  mov     [rsp+70h+lpcSubKeys], r12; lpReserved
0x180013ca3  mov     [rbp+cchName], ebx
0x180013ca6  call    cs:__imp_RegEnumKeyExW
0x180013cac  test    eax, eax
0x180013cae  jz      short loc_180013CBB
0x180013cb0  mov     rcx, rsi
0x180013cb3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013cb9  jmp     short loc_180013D20
0x180013cbb  mov     rdx, r13
0x180013cbe  inc     rdx; int
0x180013cc1  cmp     [rsi+rdx*2], r12w
0x180013cc6  jnz     short loc_180013CBE
0x180013cc8  mov     r8d, [r14]; unsigned int
0x180013ccb  mov     rcx, rsi; unsigned __int8 *
0x180013cce  call    ?UpdateCRC32@@YAKPEAEHK@Z; UpdateCRC32(uchar *,int,ulong)
0x180013cd3  mov     [r14], eax
0x180013cd6  mov     r9d, 20019h; samDesired
0x180013cdc  lea     rax, [rbp+hKey]
0x180013ce0  mov     [rbp+hKey], r12
0x180013ce4  xor     r8d, r8d; ulOptions
0x180013ce7  mov     [rsp+70h+lpcSubKeys], rax; phkResult
0x180013cec  mov     rdx, rsi; lpSubKey
0x180013cef  mov     rcx, r15; hKey
0x180013cf2  call    cs:__imp_RegOpenKeyExW
0x180013cf8  mov     rcx, rsi
0x180013cfb  mov     ebx, eax
0x180013cfd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013d03  test    ebx, ebx
0x180013d05  jnz     short loc_180013D20
0x180013d07  mov     edx, [r14]; unsigned int
0x180013d0a  mov     r8, r14; unsigned int *
0x180013d0d  mov     rcx, [rbp+hKey]; HKEY
0x180013d11  call    ?ComputeTreeCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z; CRegCRC::ComputeTreeCRC(HKEY__ *,ulong,ulong &)
0x180013d16  mov     rcx, [rbp+hKey]; hKey
0x180013d1a  call    cs:__imp_RegCloseKey
0x180013d20  inc     edi
0x180013d22  jmp     loc_180013C47
0x180013d27  mov     eax, 80041006h
0x180013d2c  jmp     short loc_180013D30
0x180013d2e  xor     eax, eax
0x180013d30  mov     rbx, [rsp+70h+arg_0]
0x180013d38  add     rsp, 70h
0x180013d3c  pop     r15
0x180013d3e  pop     r14
0x180013d40  pop     r13
0x180013d42  pop     r12
0x180013d44  pop     rdi
0x180013d45  pop     rsi
0x180013d46  pop     rbp
0x180013d47  retn
```
