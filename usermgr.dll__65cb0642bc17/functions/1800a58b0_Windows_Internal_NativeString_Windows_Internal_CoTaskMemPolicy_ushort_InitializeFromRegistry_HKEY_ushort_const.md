# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800a58b0`
- end: `0x1800a5a65`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800943b4`

## callees

- `0x180060524`
- `0x1800a58b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a59eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a59eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a5943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a59b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a5943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a59b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a58fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5971`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a58fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5971`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a59a5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a59d4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a59a5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a59d4`

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
0x1800a58b0  mov     r11, rsp
0x1800a58b3  mov     [r11+8], rbx
0x1800a58b7  mov     [r11+10h], rbp
0x1800a58bb  mov     [r11+20h], r9b
0x1800a58bf  push    rsi
0x1800a58c0  push    rdi
0x1800a58c1  push    r12
0x1800a58c3  push    r14
0x1800a58c5  push    r15
0x1800a58c7  sub     rsp, 40h
0x1800a58cb  xor     r12d, r12d
0x1800a58ce  lea     rax, [r11+20h]
0x1800a58d2  mov     rsi, r8
0x1800a58d5  mov     [r11-40h], rax
0x1800a58d9  mov     rbp, rdx
0x1800a58dc  mov     [r11-48h], r12
0x1800a58e0  mov     r15, rcx
0x1800a58e3  mov     [r11-38h], r12d
0x1800a58e7  mov     rdx, rsi; lpValueName
0x1800a58ea  mov     [r11+20h], r12d
0x1800a58ee  mov     rcx, rbp; hKey
0x1800a58f1  lea     r9, [r11-38h]; lpType
0x1800a58f5  xor     r8d, r8d; lpReserved
0x1800a58f8  mov     edi, r12d
0x1800a58fb  call    cs:__imp_RegQueryValueExW
0x1800a5901  mov     ebx, eax
0x1800a5903  mov     r14d, 80070000h
0x1800a5909  test    eax, eax
0x1800a590b  jle     short loc_1800A5913
0x1800a590d  movzx   ebx, ax
0x1800a5910  or      ebx, r14d
0x1800a5913  test    ebx, ebx
0x1800a5915  js      loc_1800A5A43
0x1800a591b  mov     eax, [rsp+68h+Type]
0x1800a591f  dec     eax
0x1800a5921  cmp     eax, 1
0x1800a5924  ja      loc_1800A5A3E
0x1800a592a  mov     eax, dword ptr [rsp+68h+cb]
0x1800a5931  test    eax, eax
0x1800a5933  jz      loc_1800A5A3E
0x1800a5939  test    al, 1
0x1800a593b  jnz     loc_1800A5A3E
0x1800a5941  mov     ecx, eax; cb
0x1800a5943  call    cs:__imp_CoTaskMemAlloc
0x1800a5949  mov     rdi, rax
0x1800a594c  test    rax, rax
0x1800a594f  jz      short loc_1800A59C4
0x1800a5951  lea     rax, [rsp+68h+cb]
0x1800a5959  xor     r8d, r8d; lpReserved
0x1800a595c  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800a5961  lea     r9, [rsp+68h+Type]; lpType
0x1800a5966  mov     rdx, rsi; lpValueName
0x1800a5969  mov     [rsp+68h+lpData], rdi; lpData
0x1800a596e  mov     rcx, rbp; hKey
0x1800a5971  call    cs:__imp_RegQueryValueExW
0x1800a5977  mov     ebx, eax
0x1800a5979  test    eax, eax
0x1800a597b  jle     short loc_1800A5983
0x1800a597d  movzx   ebx, ax
0x1800a5980  or      ebx, r14d
0x1800a5983  test    ebx, ebx
0x1800a5985  js      loc_1800A5A43
0x1800a598b  mov     esi, dword ptr [rsp+68h+cb]
0x1800a5992  shr     esi, 1
0x1800a5994  dec     esi
0x1800a5996  cmp     [rsp+68h+Type], 2
0x1800a599b  jnz     short loc_1800A59F8
0x1800a599d  xor     r8d, r8d; nSize
0x1800a59a0  xor     edx, edx; lpDst
0x1800a59a2  mov     rcx, rdi; lpSrc
0x1800a59a5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a59ab  mov     ebp, eax
0x1800a59ad  test    eax, eax
0x1800a59af  jz      short loc_1800A59F8
0x1800a59b1  mov     ecx, ebp
0x1800a59b3  add     rcx, rcx; cb
0x1800a59b6  call    cs:__imp_CoTaskMemAlloc
0x1800a59bc  mov     rsi, rax
0x1800a59bf  test    rax, rax
0x1800a59c2  jnz     short loc_1800A59CB
0x1800a59c4  mov     ebx, 8007000Eh
0x1800a59c9  jmp     short loc_1800A5A43
0x1800a59cb  mov     r8d, ebp; nSize
0x1800a59ce  mov     rdx, rsi; lpDst
0x1800a59d1  mov     rcx, rdi; lpSrc
0x1800a59d4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a59da  mov     r14d, eax
0x1800a59dd  test    eax, eax
0x1800a59df  jz      short loc_1800A5A2E
0x1800a59e1  cmp     eax, ebp
0x1800a59e3  ja      short loc_1800A5A2E
0x1800a59e5  mov     rcx, rdi; pv
0x1800a59e8  mov     ebx, r12d
0x1800a59eb  call    cs:__imp_CoTaskMemFree
0x1800a59f1  mov     rdi, rsi
0x1800a59f4  lea     esi, [r14-1]
0x1800a59f8  cmp     [rdi+rsi*2], r12w
0x1800a59fd  jnz     short loc_1800A5A3E
0x1800a59ff  mov     rcx, r15
0x1800a5a02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a5a07  test    rdi, rdi
0x1800a5a0a  jz      short loc_1800A5A29
0x1800a5a0c  lea     eax, [rsi+1]
0x1800a5a0f  mov     ecx, eax
0x1800a5a11  test    eax, eax
0x1800a5a13  jz      short loc_1800A5A29
0x1800a5a15  dec     rax
0x1800a5a18  mov     [r15], rdi
0x1800a5a1b  mov     [r15+8], rax
0x1800a5a1f  mov     [r15+10h], rcx
0x1800a5a23  mov     [rdi+rcx*2-2], r12w
0x1800a5a29  mov     rdi, r12
0x1800a5a2c  jmp     short loc_1800A5A43
0x1800a5a2e  mov     rcx, rsi; pv
0x1800a5a31  mov     ebx, 8007007Ah
0x1800a5a36  call    cs:__imp_CoTaskMemFree
0x1800a5a3c  jmp     short loc_1800A5A43
0x1800a5a3e  mov     ebx, 8007000Dh
0x1800a5a43  mov     rcx, rdi; pv
0x1800a5a46  call    cs:__imp_CoTaskMemFree
0x1800a5a4c  mov     rbp, [rsp+68h+arg_8]
0x1800a5a51  mov     eax, ebx
0x1800a5a53  mov     rbx, [rsp+68h+arg_0]
0x1800a5a58  add     rsp, 40h
0x1800a5a5c  pop     r15
0x1800a5a5e  pop     r14
0x1800a5a60  pop     r12
0x1800a5a62  pop     rdi
0x1800a5a63  pop     rsi
0x1800a5a64  retn
```
