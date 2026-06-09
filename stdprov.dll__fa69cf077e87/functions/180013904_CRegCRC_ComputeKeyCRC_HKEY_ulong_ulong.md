# CRegCRC::ComputeKeyCRC(HKEY__ *,ulong,ulong &)

- ea: `0x180013904`
- end: `0x180013a61`
- name: `?ComputeKeyCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z`
- size: `349`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013ea0`

## callees

- `0x180009ef0`
- `0x1800138b4`
- `0x180013904`
- `0x180013a68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013a0a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013a0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013982`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013982`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013a32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013a32`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800139d7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800139d7`

## pseudocode

```c
__int64 __fastcall CRegCRC::ComputeKeyCRC(HKEY hKey, DWORD a2, unsigned int *a3)
{
  LSTATUS v5; // eax
  DWORD i; // edi
  DWORD v8; // ebx
  WCHAR *v9; // rax
  unsigned __int8 *v10; // rsi
  __int64 v11; // rdx
  DWORD v12; // [rsp+60h] [rbp-38h] BYREF
  DWORD cchName[3]; // [rsp+64h] [rbp-34h] BYREF
  DWORD cSubKeys; // [rsp+A8h] [rbp+10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B8h] [rbp+20h] BYREF

  cSubKeys = a2;
  CRegCRC::ComputeKeyValuesCRC(hKey, 0xFFFFFFFF, a3);
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v5 && v5 != 122 )
    return 2147500037LL;
  for ( i = 0; i < cSubKeys; ++i )
  {
    v12 = cbMaxSubKeyLen;
    SafeInt<unsigned long>::operator+=<int>(&v12);
    v8 = v12;
    v9 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v12, 2u));
    v10 = (unsigned __int8 *)v9;
    if ( !v9 )
      return 2147749894LL;
    cchName[0] = v8;
    if ( !RegEnumKeyExW(hKey, i, v9, cchName, 0, 0, 0, 0) )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v10[2 * v11] );
      *a3 = UpdateCRC32(v10, v11, *a3);
    }
    CWin32DefaultArena::WbemMemFree(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180013904  mov     [rsp+arg_0], rbx
0x180013909  mov     [rsp+arg_10], rbp
0x18001390e  mov     [rsp+cSubKeys], edx
0x180013912  push    rsi
0x180013913  push    rdi
0x180013914  push    r12
0x180013916  push    r14
0x180013918  push    r15
0x18001391a  sub     rsp, 70h
0x18001391e  or      edx, 0FFFFFFFFh; unsigned int
0x180013921  mov     r14, r8
0x180013924  mov     rbp, rcx
0x180013927  call    ?ComputeKeyValuesCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z; CRegCRC::ComputeKeyValuesCRC(HKEY__ *,ulong,ulong &)
0x18001392c  xor     r15d, r15d
0x18001392f  lea     rax, [rsp+98h+cbMaxSubKeyLen]
0x180013937  mov     [rsp+98h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001393c  xor     r9d, r9d; lpReserved
0x18001393f  mov     [rsp+98h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180013944  xor     r8d, r8d; lpcchClass
0x180013947  mov     [rsp+98h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001394c  xor     edx, edx; lpClass
0x18001394e  mov     [rsp+98h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180013953  mov     rcx, rbp; hKey
0x180013956  mov     [rsp+98h+lpcValues], r15; lpcValues
0x18001395b  mov     [rsp+98h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180013960  mov     [rsp+98h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013965  lea     rax, [rsp+98h+cSubKeys]
0x18001396d  mov     [rsp+98h+lpcSubKeys], rax; lpcSubKeys
0x180013972  mov     [rsp+98h+cSubKeys], r15d
0x18001397a  mov     [rsp+98h+cbMaxSubKeyLen], r15d
0x180013982  call    cs:__imp_RegQueryInfoKeyW
0x180013988  test    eax, eax
0x18001398a  jz      short loc_18001399B
0x18001398c  cmp     eax, 7Ah ; 'z'
0x18001398f  jz      short loc_18001399B
0x180013991  mov     eax, 80004005h
0x180013996  jmp     loc_180013A48
0x18001399b  mov     edi, r15d
0x18001399e  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800139a2  cmp     edi, [rsp+98h+cSubKeys]
0x1800139a9  jnb     loc_180013A46
0x1800139af  mov     eax, [rsp+98h+cbMaxSubKeyLen]
0x1800139b6  lea     rcx, [rsp+98h+var_38]
0x1800139bb  mov     [rsp+98h+var_38], eax
0x1800139bf  call    ??$?YH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator+=<int>(int)
0x1800139c4  mov     ebx, [rsp+98h+var_38]
0x1800139c8  mov     eax, 2
0x1800139cd  mul     rbx
0x1800139d0  cmovb   rax, r12
0x1800139d4  mov     rcx, rax
0x1800139d7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800139dd  mov     rsi, rax
0x1800139e0  test    rax, rax
0x1800139e3  jz      short loc_180013A3F
0x1800139e5  mov     [rsp+98h+lpcValues], r15; lpftLastWriteTime
0x1800139ea  lea     r9, [rsp+98h+cchName]; lpcchName
0x1800139ef  mov     [rsp+98h+lpcbMaxClassLen], r15; lpcchClass
0x1800139f4  mov     r8, rax; lpName
0x1800139f7  mov     [rsp+98h+lpcbMaxSubKeyLen], r15; lpClass
0x1800139fc  mov     edx, edi; dwIndex
0x1800139fe  mov     rcx, rbp; hKey
0x180013a01  mov     [rsp+98h+lpcSubKeys], r15; lpReserved
0x180013a06  mov     [rsp+98h+cchName], ebx
0x180013a0a  call    cs:__imp_RegEnumKeyExW
0x180013a10  test    eax, eax
0x180013a12  jnz     short loc_180013A2F
0x180013a14  mov     rdx, r12
0x180013a17  inc     rdx; int
0x180013a1a  cmp     [rsi+rdx*2], r15w
0x180013a1f  jnz     short loc_180013A17
0x180013a21  mov     r8d, [r14]; unsigned int
0x180013a24  mov     rcx, rsi; unsigned __int8 *
0x180013a27  call    ?UpdateCRC32@@YAKPEAEHK@Z; UpdateCRC32(uchar *,int,ulong)
0x180013a2c  mov     [r14], eax
0x180013a2f  mov     rcx, rsi
0x180013a32  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013a38  inc     edi
0x180013a3a  jmp     loc_1800139A2
0x180013a3f  mov     eax, 80041006h
0x180013a44  jmp     short loc_180013A48
0x180013a46  xor     eax, eax
0x180013a48  lea     r11, [rsp+98h+var_28]
0x180013a4d  mov     rbx, [r11+30h]
0x180013a51  mov     rbp, [r11+40h]
0x180013a55  mov     rsp, r11
0x180013a58  pop     r15
0x180013a5a  pop     r14
0x180013a5c  pop     r12
0x180013a5e  pop     rdi
0x180013a5f  pop     rsi
0x180013a60  retn
```
