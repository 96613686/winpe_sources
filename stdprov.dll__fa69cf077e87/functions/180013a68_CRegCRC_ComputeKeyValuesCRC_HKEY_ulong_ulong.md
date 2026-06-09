# CRegCRC::ComputeKeyValuesCRC(HKEY__ *,ulong,ulong &)

- ea: `0x180013a68`
- end: `0x180013bad`
- name: `?ComputeKeyValuesCRC@CRegCRC@@SAJPEAUHKEY__@@KAEAK@Z`
- size: `325`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013904`
- `0x180013bb4`

## callees

- `0x180009dd0`
- `0x180009ef0`
- `0x1800138b4`
- `0x180013a68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013abe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013abe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013b4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013b4f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b88`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013b88`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013b1c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013b1c`

## pseudocode

```c
__int64 __fastcall CRegCRC::ComputeKeyValuesCRC(HKEY hKey, unsigned int a2, unsigned int *a3)
{
  LSTATUS v5; // eax
  DWORD i; // edi
  DWORD v8; // ebx
  WCHAR *v9; // rax
  unsigned __int8 *v10; // rsi
  __int64 v11; // rdx
  unsigned int updated; // eax
  DWORD cchValueName[18]; // [rsp+60h] [rbp-48h] BYREF
  DWORD v14; // [rsp+B8h] [rbp+10h] BYREF
  DWORD v15; // [rsp+C0h] [rbp+18h] BYREF
  DWORD v16; // [rsp+C8h] [rbp+20h] BYREF

  *a3 = a2;
  v14 = 0;
  v15 = 0;
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &v14, &v15, 0, 0, 0);
  if ( v5 && v5 != 122 )
    return 2147500037LL;
  for ( i = 0; i < v14; ++i )
  {
    v16 = v15;
    SafeInt<unsigned long>::operator+=<int>(&v16);
    v8 = v16;
    v9 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v16, 2u));
    v10 = (unsigned __int8 *)v9;
    if ( !v9 )
      return 2147749894LL;
    cchValueName[0] = v8;
    if ( !RegEnumValueW(hKey, i, v9, cchValueName, 0, 0, 0, 0) )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v10[2 * v11] );
      updated = UpdateCRC32(v10, v11, *a3);
      *a3 = updated;
      CRegCRC::ComputeValueCRC(hKey, (LPCWSTR)v10, updated, a3);
    }
    CWin32DefaultArena::WbemMemFree(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180013a68  mov     r11, rsp
0x180013a6b  push    rbx
0x180013a6c  push    rbp
0x180013a6d  push    rsi
0x180013a6e  push    rdi
0x180013a6f  push    r12
0x180013a71  push    r14
0x180013a73  push    r15
0x180013a75  sub     rsp, 70h
0x180013a79  xor     r15d, r15d
0x180013a7c  mov     [r8], edx
0x180013a7f  mov     [r11-50h], r15
0x180013a83  lea     rax, [r11+18h]
0x180013a87  mov     [r11-58h], r15
0x180013a8b  mov     r14, r8
0x180013a8e  mov     [r11-60h], r15
0x180013a92  xor     r9d, r9d; lpReserved
0x180013a95  mov     [r11-68h], rax
0x180013a99  xor     r8d, r8d; lpcchClass
0x180013a9c  lea     rax, [r11+10h]
0x180013aa0  mov     [r11+10h], r15d
0x180013aa4  mov     [r11-70h], rax
0x180013aa8  xor     edx, edx; lpClass
0x180013aaa  mov     [r11-78h], r15
0x180013aae  mov     rbp, rcx
0x180013ab1  mov     [r11-80h], r15
0x180013ab5  mov     [rsp+0A8h+lpcSubKeys], r15; lpcSubKeys
0x180013aba  mov     [r11+18h], r15d
0x180013abe  call    cs:__imp_RegQueryInfoKeyW
0x180013ac4  test    eax, eax
0x180013ac6  jz      short loc_180013AD7
0x180013ac8  cmp     eax, 7Ah ; 'z'
0x180013acb  jz      short loc_180013AD7
0x180013acd  mov     eax, 80004005h
0x180013ad2  jmp     loc_180013B9E
0x180013ad7  mov     edi, r15d
0x180013ada  or      r12, 0FFFFFFFFFFFFFFFFh
0x180013ade  cmp     edi, [rsp+0A8h+arg_8]
0x180013ae5  jnb     loc_180013B9C
0x180013aeb  mov     eax, [rsp+0A8h+arg_10]
0x180013af2  lea     rcx, [rsp+0A8h+arg_18]
0x180013afa  mov     [rsp+0A8h+arg_18], eax
0x180013b01  call    ??$?YH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator+=<int>(int)
0x180013b06  mov     ebx, [rsp+0A8h+arg_18]
0x180013b0d  mov     eax, 2
0x180013b12  mul     rbx
0x180013b15  cmovb   rax, r12
0x180013b19  mov     rcx, rax
0x180013b1c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013b22  mov     rsi, rax
0x180013b25  test    rax, rax
0x180013b28  jz      short loc_180013B95
0x180013b2a  mov     [rsp+0A8h+lpcbData], r15; lpcbData
0x180013b2f  lea     r9, [rsp+0A8h+cchValueName]; lpcchValueName
0x180013b34  mov     [rsp+0A8h+lpData], r15; lpData
0x180013b39  mov     r8, rax; lpValueName
0x180013b3c  mov     [rsp+0A8h+lpType], r15; lpType
0x180013b41  mov     edx, edi; dwIndex
0x180013b43  mov     rcx, rbp; hKey
0x180013b46  mov     [rsp+0A8h+lpcSubKeys], r15; lpReserved
0x180013b4b  mov     [rsp+0A8h+cchValueName], ebx
0x180013b4f  call    cs:__imp_RegEnumValueW
0x180013b55  test    eax, eax
0x180013b57  jnz     short loc_180013B85
0x180013b59  mov     rdx, r12
0x180013b5c  inc     rdx; int
0x180013b5f  cmp     [rsi+rdx*2], r15w
0x180013b64  jnz     short loc_180013B5C
0x180013b66  mov     r8d, [r14]; unsigned int
0x180013b69  mov     rcx, rsi; unsigned __int8 *
0x180013b6c  call    ?UpdateCRC32@@YAKPEAEHK@Z; UpdateCRC32(uchar *,int,ulong)
0x180013b71  mov     r9, r14; unsigned int *
0x180013b74  mov     [r14], eax
0x180013b77  mov     r8d, eax; unsigned int
0x180013b7a  mov     rdx, rsi; lpValueName
0x180013b7d  mov     rcx, rbp; hKey
0x180013b80  call    ?ComputeValueCRC@CRegCRC@@SAJPEAUHKEY__@@PEBGKAEAK@Z; CRegCRC::ComputeValueCRC(HKEY__ *,ushort const *,ulong,ulong &)
0x180013b85  mov     rcx, rsi
0x180013b88  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013b8e  inc     edi
0x180013b90  jmp     loc_180013ADE
0x180013b95  mov     eax, 80041006h
0x180013b9a  jmp     short loc_180013B9E
0x180013b9c  xor     eax, eax
0x180013b9e  add     rsp, 70h
0x180013ba2  pop     r15
0x180013ba4  pop     r14
0x180013ba6  pop     r12
0x180013ba8  pop     rdi
0x180013ba9  pop     rsi
0x180013baa  pop     rbp
0x180013bab  pop     rbx
0x180013bac  retn
```
