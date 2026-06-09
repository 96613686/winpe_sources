# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800c09d8`
- end: `0x1800c0bcb`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a24c`
- `0x18003902c`
- `0x18004e850`

## callees

- `0x18000af00`
- `0x1800c09d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0a23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0aa9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0a23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c0aa9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0ae3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0b21`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0ae3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800c0b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0afa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c0afa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0ba5`

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
0x1800c09d8  mov     r11, rsp
0x1800c09db  mov     [r11+8], rbx
0x1800c09df  mov     [r11+10h], rbp
0x1800c09e3  mov     [r11+20h], r9b
0x1800c09e7  push    rsi
0x1800c09e8  push    rdi
0x1800c09e9  push    r12
0x1800c09eb  push    r14
0x1800c09ed  push    r15
0x1800c09ef  sub     rsp, 40h
0x1800c09f3  xor     r12d, r12d
0x1800c09f6  lea     rax, [r11+20h]
0x1800c09fa  mov     rsi, r8
0x1800c09fd  mov     [r11-40h], rax
0x1800c0a01  mov     rbp, rdx
0x1800c0a04  mov     [r11-48h], r12
0x1800c0a08  mov     r15, rcx
0x1800c0a0b  mov     [r11-38h], r12d
0x1800c0a0f  mov     rdx, rsi; lpValueName
0x1800c0a12  mov     [r11+20h], r12d
0x1800c0a16  mov     rcx, rbp; hKey
0x1800c0a19  lea     r9, [r11-38h]; lpType
0x1800c0a1d  xor     r8d, r8d; lpReserved
0x1800c0a20  mov     edi, r12d
0x1800c0a23  call    cs:__imp_RegQueryValueExW
0x1800c0a2a  nop     dword ptr [rax+rax+00h]
0x1800c0a2f  mov     ebx, eax
0x1800c0a31  mov     r14d, 80070000h
0x1800c0a37  test    eax, eax
0x1800c0a39  jle     short loc_1800C0A41
0x1800c0a3b  movzx   ebx, ax
0x1800c0a3e  or      ebx, r14d
0x1800c0a41  test    ebx, ebx
0x1800c0a43  js      loc_1800C0BA2
0x1800c0a49  mov     eax, [rsp+68h+Type]
0x1800c0a4d  dec     eax
0x1800c0a4f  cmp     eax, 1
0x1800c0a52  ja      loc_1800C0B9D
0x1800c0a58  mov     eax, dword ptr [rsp+68h+cb]
0x1800c0a5f  test    eax, eax
0x1800c0a61  jz      loc_1800C0B9D
0x1800c0a67  test    al, 1
0x1800c0a69  jnz     loc_1800C0B9D
0x1800c0a6f  mov     ecx, eax; cb
0x1800c0a71  call    cs:__imp_CoTaskMemAlloc
0x1800c0a78  nop     dword ptr [rax+rax+00h]
0x1800c0a7d  mov     rdi, rax
0x1800c0a80  test    rax, rax
0x1800c0a83  jz      loc_1800C0B0E
0x1800c0a89  lea     rax, [rsp+68h+cb]
0x1800c0a91  xor     r8d, r8d; lpReserved
0x1800c0a94  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800c0a99  lea     r9, [rsp+68h+Type]; lpType
0x1800c0a9e  mov     rdx, rsi; lpValueName
0x1800c0aa1  mov     [rsp+68h+lpData], rdi; lpData
0x1800c0aa6  mov     rcx, rbp; hKey
0x1800c0aa9  call    cs:__imp_RegQueryValueExW
0x1800c0ab0  nop     dword ptr [rax+rax+00h]
0x1800c0ab5  mov     ebx, eax
0x1800c0ab7  test    eax, eax
0x1800c0ab9  jle     short loc_1800C0AC1
0x1800c0abb  movzx   ebx, ax
0x1800c0abe  or      ebx, r14d
0x1800c0ac1  test    ebx, ebx
0x1800c0ac3  js      loc_1800C0BA2
0x1800c0ac9  mov     esi, dword ptr [rsp+68h+cb]
0x1800c0ad0  shr     esi, 1
0x1800c0ad2  dec     esi
0x1800c0ad4  cmp     [rsp+68h+Type], 2
0x1800c0ad9  jnz     short loc_1800C0B51
0x1800c0adb  xor     r8d, r8d; nSize
0x1800c0ade  xor     edx, edx; lpDst
0x1800c0ae0  mov     rcx, rdi; lpSrc
0x1800c0ae3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c0aea  nop     dword ptr [rax+rax+00h]
0x1800c0aef  mov     ebp, eax
0x1800c0af1  test    eax, eax
0x1800c0af3  jz      short loc_1800C0B51
0x1800c0af5  mov     ecx, ebp
0x1800c0af7  add     rcx, rcx; cb
0x1800c0afa  call    cs:__imp_CoTaskMemAlloc
0x1800c0b01  nop     dword ptr [rax+rax+00h]
0x1800c0b06  mov     rsi, rax
0x1800c0b09  test    rax, rax
0x1800c0b0c  jnz     short loc_1800C0B18
0x1800c0b0e  mov     ebx, 8007000Eh
0x1800c0b13  jmp     loc_1800C0BA2
0x1800c0b18  mov     r8d, ebp; nSize
0x1800c0b1b  mov     rdx, rsi; lpDst
0x1800c0b1e  mov     rcx, rdi; lpSrc
0x1800c0b21  call    cs:__imp_ExpandEnvironmentStringsW
0x1800c0b28  nop     dword ptr [rax+rax+00h]
0x1800c0b2d  mov     r14d, eax
0x1800c0b30  test    eax, eax
0x1800c0b32  jz      short loc_1800C0B87
0x1800c0b34  cmp     eax, ebp
0x1800c0b36  ja      short loc_1800C0B87
0x1800c0b38  mov     rcx, rdi; pv
0x1800c0b3b  mov     ebx, r12d
0x1800c0b3e  call    cs:__imp_CoTaskMemFree
0x1800c0b45  nop     dword ptr [rax+rax+00h]
0x1800c0b4a  mov     rdi, rsi
0x1800c0b4d  lea     esi, [r14-1]
0x1800c0b51  cmp     [rdi+rsi*2], r12w
0x1800c0b56  jnz     short loc_1800C0B9D
0x1800c0b58  mov     rcx, r15
0x1800c0b5b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c0b60  test    rdi, rdi
0x1800c0b63  jz      short loc_1800C0B82
0x1800c0b65  lea     eax, [rsi+1]
0x1800c0b68  mov     ecx, eax
0x1800c0b6a  test    eax, eax
0x1800c0b6c  jz      short loc_1800C0B82
0x1800c0b6e  dec     rax
0x1800c0b71  mov     [r15], rdi
0x1800c0b74  mov     [r15+8], rax
0x1800c0b78  mov     [r15+10h], rcx
0x1800c0b7c  mov     [rdi+rcx*2-2], r12w
0x1800c0b82  mov     rdi, r12
0x1800c0b85  jmp     short loc_1800C0BA2
0x1800c0b87  mov     rcx, rsi; pv
0x1800c0b8a  mov     ebx, 8007007Ah
0x1800c0b8f  call    cs:__imp_CoTaskMemFree
0x1800c0b96  nop     dword ptr [rax+rax+00h]
0x1800c0b9b  jmp     short loc_1800C0BA2
0x1800c0b9d  mov     ebx, 8007000Dh
0x1800c0ba2  mov     rcx, rdi; pv
0x1800c0ba5  call    cs:__imp_CoTaskMemFree
0x1800c0bac  nop     dword ptr [rax+rax+00h]
0x1800c0bb1  mov     rbp, [rsp+68h+arg_8]
0x1800c0bb6  mov     eax, ebx
0x1800c0bb8  mov     rbx, [rsp+68h+arg_0]
0x1800c0bbd  add     rsp, 40h
0x1800c0bc1  pop     r15
0x1800c0bc3  pop     r14
0x1800c0bc5  pop     r12
0x1800c0bc7  pop     rdi
0x1800c0bc8  pop     rsi
0x1800c0bc9  retn
```
