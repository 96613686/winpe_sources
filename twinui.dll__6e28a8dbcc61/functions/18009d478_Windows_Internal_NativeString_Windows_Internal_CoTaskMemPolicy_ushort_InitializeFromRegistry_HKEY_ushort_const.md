# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18009d478`
- end: `0x18009d62d`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073390`

## callees

- `0x180027ee4`
- `0x18009d478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d4c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d539`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d4c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d539`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009d56d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009d59c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009d56d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009d59c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d57e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d57e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS Value; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T cb; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  Value = RegQueryValueExW(a2, a3, 0, Type, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( Value > 0 )
    v8 = (unsigned __int16)Value | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, (LPDWORD)&cb);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = ((unsigned int)cb >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)CoTaskMemAlloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            CoTaskMemFree(v14);
            goto LABEL_25;
          }
          v8 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18009d478  mov     r11, rsp
0x18009d47b  mov     [r11+8], rbx
0x18009d47f  mov     [r11+10h], rbp
0x18009d483  mov     [r11+20h], r9b
0x18009d487  push    rsi
0x18009d488  push    rdi
0x18009d489  push    r12
0x18009d48b  push    r14
0x18009d48d  push    r15
0x18009d48f  sub     rsp, 40h
0x18009d493  xor     r12d, r12d
0x18009d496  lea     rax, [r11+20h]
0x18009d49a  mov     rsi, r8
0x18009d49d  mov     [r11-40h], rax
0x18009d4a1  mov     rbp, rdx
0x18009d4a4  mov     [r11-48h], r12
0x18009d4a8  mov     r15, rcx
0x18009d4ab  mov     [r11-38h], r12d
0x18009d4af  mov     rdx, rsi; lpValueName
0x18009d4b2  mov     [r11+20h], r12d
0x18009d4b6  mov     rcx, rbp; hKey
0x18009d4b9  lea     r9, [r11-38h]; lpType
0x18009d4bd  xor     r8d, r8d; lpReserved
0x18009d4c0  mov     edi, r12d
0x18009d4c3  call    cs:__imp_RegQueryValueExW
0x18009d4c9  mov     ebx, eax
0x18009d4cb  mov     r14d, 80070000h
0x18009d4d1  test    eax, eax
0x18009d4d3  jle     short loc_18009D4DB
0x18009d4d5  movzx   ebx, ax
0x18009d4d8  or      ebx, r14d
0x18009d4db  test    ebx, ebx
0x18009d4dd  js      loc_18009D60B
0x18009d4e3  mov     eax, [rsp+68h+Type]
0x18009d4e7  dec     eax
0x18009d4e9  cmp     eax, 1
0x18009d4ec  ja      loc_18009D606
0x18009d4f2  mov     eax, dword ptr [rsp+68h+cb]
0x18009d4f9  test    eax, eax
0x18009d4fb  jz      loc_18009D606
0x18009d501  test    al, 1
0x18009d503  jnz     loc_18009D606
0x18009d509  mov     ecx, eax; cb
0x18009d50b  call    cs:__imp_CoTaskMemAlloc
0x18009d511  mov     rdi, rax
0x18009d514  test    rax, rax
0x18009d517  jz      short loc_18009D58C
0x18009d519  lea     rax, [rsp+68h+cb]
0x18009d521  xor     r8d, r8d; lpReserved
0x18009d524  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18009d529  lea     r9, [rsp+68h+Type]; lpType
0x18009d52e  mov     rdx, rsi; lpValueName
0x18009d531  mov     [rsp+68h+lpData], rdi; lpData
0x18009d536  mov     rcx, rbp; hKey
0x18009d539  call    cs:__imp_RegQueryValueExW
0x18009d53f  mov     ebx, eax
0x18009d541  test    eax, eax
0x18009d543  jle     short loc_18009D54B
0x18009d545  movzx   ebx, ax
0x18009d548  or      ebx, r14d
0x18009d54b  test    ebx, ebx
0x18009d54d  js      loc_18009D60B
0x18009d553  mov     esi, dword ptr [rsp+68h+cb]
0x18009d55a  shr     esi, 1
0x18009d55c  dec     esi
0x18009d55e  cmp     [rsp+68h+Type], 2
0x18009d563  jnz     short loc_18009D5C0
0x18009d565  xor     r8d, r8d; nSize
0x18009d568  xor     edx, edx; lpDst
0x18009d56a  mov     rcx, rdi; lpSrc
0x18009d56d  call    cs:__imp_ExpandEnvironmentStringsW
0x18009d573  mov     ebp, eax
0x18009d575  test    eax, eax
0x18009d577  jz      short loc_18009D5C0
0x18009d579  mov     ecx, ebp
0x18009d57b  add     rcx, rcx; cb
0x18009d57e  call    cs:__imp_CoTaskMemAlloc
0x18009d584  mov     rsi, rax
0x18009d587  test    rax, rax
0x18009d58a  jnz     short loc_18009D593
0x18009d58c  mov     ebx, 8007000Eh
0x18009d591  jmp     short loc_18009D60B
0x18009d593  mov     r8d, ebp; nSize
0x18009d596  mov     rdx, rsi; lpDst
0x18009d599  mov     rcx, rdi; lpSrc
0x18009d59c  call    cs:__imp_ExpandEnvironmentStringsW
0x18009d5a2  mov     r14d, eax
0x18009d5a5  test    eax, eax
0x18009d5a7  jz      short loc_18009D5F6
0x18009d5a9  cmp     eax, ebp
0x18009d5ab  ja      short loc_18009D5F6
0x18009d5ad  mov     rcx, rdi; pv
0x18009d5b0  mov     ebx, r12d
0x18009d5b3  call    cs:__imp_CoTaskMemFree
0x18009d5b9  mov     rdi, rsi
0x18009d5bc  lea     esi, [r14-1]
0x18009d5c0  cmp     [rdi+rsi*2], r12w
0x18009d5c5  jnz     short loc_18009D606
0x18009d5c7  mov     rcx, r15
0x18009d5ca  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009d5cf  test    rdi, rdi
0x18009d5d2  jz      short loc_18009D5F1
0x18009d5d4  lea     eax, [rsi+1]
0x18009d5d7  mov     ecx, eax
0x18009d5d9  test    eax, eax
0x18009d5db  jz      short loc_18009D5F1
0x18009d5dd  dec     rax
0x18009d5e0  mov     [r15], rdi
0x18009d5e3  mov     [r15+8], rax
0x18009d5e7  mov     [r15+10h], rcx
0x18009d5eb  mov     [rdi+rcx*2-2], r12w
0x18009d5f1  mov     rdi, r12
0x18009d5f4  jmp     short loc_18009D60B
0x18009d5f6  mov     rcx, rsi; pv
0x18009d5f9  mov     ebx, 8007007Ah
0x18009d5fe  call    cs:__imp_CoTaskMemFree
0x18009d604  jmp     short loc_18009D60B
0x18009d606  mov     ebx, 8007000Dh
0x18009d60b  mov     rcx, rdi; pv
0x18009d60e  call    cs:__imp_CoTaskMemFree
0x18009d614  mov     rbp, [rsp+68h+arg_8]
0x18009d619  mov     eax, ebx
0x18009d61b  mov     rbx, [rsp+68h+arg_0]
0x18009d620  add     rsp, 40h
0x18009d624  pop     r15
0x18009d626  pop     r14
0x18009d628  pop     r12
0x18009d62a  pop     rdi
0x18009d62b  pop     rsi
0x18009d62c  retn
```
