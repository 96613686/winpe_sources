# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18002bb50`
- end: `0x18002bd05`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028714`

## callees

- `0x180010130`
- `0x18002bb50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bcd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bbe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bc56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bbe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bc56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bc11`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002bc45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002bc74`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002bc45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002bc74`

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
0x18002bb50  mov     r11, rsp
0x18002bb53  mov     [r11+8], rbx
0x18002bb57  mov     [r11+10h], rbp
0x18002bb5b  mov     [r11+20h], r9b
0x18002bb5f  push    rsi
0x18002bb60  push    rdi
0x18002bb61  push    r12
0x18002bb63  push    r14
0x18002bb65  push    r15
0x18002bb67  sub     rsp, 40h
0x18002bb6b  xor     r12d, r12d
0x18002bb6e  lea     rax, [r11+20h]
0x18002bb72  mov     rsi, r8
0x18002bb75  mov     [r11-40h], rax
0x18002bb79  mov     rbp, rdx
0x18002bb7c  mov     [r11-48h], r12
0x18002bb80  mov     r15, rcx
0x18002bb83  mov     [r11-38h], r12d
0x18002bb87  mov     rdx, rsi; lpValueName
0x18002bb8a  mov     [r11+20h], r12d
0x18002bb8e  mov     rcx, rbp; hKey
0x18002bb91  lea     r9, [r11-38h]; lpType
0x18002bb95  xor     r8d, r8d; lpReserved
0x18002bb98  mov     edi, r12d
0x18002bb9b  call    cs:__imp_RegQueryValueExW
0x18002bba1  mov     ebx, eax
0x18002bba3  mov     r14d, 80070000h
0x18002bba9  test    eax, eax
0x18002bbab  jle     short loc_18002BBB3
0x18002bbad  movzx   ebx, ax
0x18002bbb0  or      ebx, r14d
0x18002bbb3  test    ebx, ebx
0x18002bbb5  js      loc_18002BCE3
0x18002bbbb  mov     eax, [rsp+68h+Type]
0x18002bbbf  dec     eax
0x18002bbc1  cmp     eax, 1
0x18002bbc4  ja      loc_18002BCDE
0x18002bbca  mov     eax, dword ptr [rsp+68h+cb]
0x18002bbd1  test    eax, eax
0x18002bbd3  jz      loc_18002BCDE
0x18002bbd9  test    al, 1
0x18002bbdb  jnz     loc_18002BCDE
0x18002bbe1  mov     ecx, eax; cb
0x18002bbe3  call    cs:__imp_CoTaskMemAlloc
0x18002bbe9  mov     rdi, rax
0x18002bbec  test    rax, rax
0x18002bbef  jz      short loc_18002BC64
0x18002bbf1  lea     rax, [rsp+68h+cb]
0x18002bbf9  xor     r8d, r8d; lpReserved
0x18002bbfc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002bc01  lea     r9, [rsp+68h+Type]; lpType
0x18002bc06  mov     rdx, rsi; lpValueName
0x18002bc09  mov     [rsp+68h+lpData], rdi; lpData
0x18002bc0e  mov     rcx, rbp; hKey
0x18002bc11  call    cs:__imp_RegQueryValueExW
0x18002bc17  mov     ebx, eax
0x18002bc19  test    eax, eax
0x18002bc1b  jle     short loc_18002BC23
0x18002bc1d  movzx   ebx, ax
0x18002bc20  or      ebx, r14d
0x18002bc23  test    ebx, ebx
0x18002bc25  js      loc_18002BCE3
0x18002bc2b  mov     esi, dword ptr [rsp+68h+cb]
0x18002bc32  shr     esi, 1
0x18002bc34  dec     esi
0x18002bc36  cmp     [rsp+68h+Type], 2
0x18002bc3b  jnz     short loc_18002BC98
0x18002bc3d  xor     r8d, r8d; nSize
0x18002bc40  xor     edx, edx; lpDst
0x18002bc42  mov     rcx, rdi; lpSrc
0x18002bc45  call    cs:__imp_ExpandEnvironmentStringsW
0x18002bc4b  mov     ebp, eax
0x18002bc4d  test    eax, eax
0x18002bc4f  jz      short loc_18002BC98
0x18002bc51  mov     ecx, ebp
0x18002bc53  add     rcx, rcx; cb
0x18002bc56  call    cs:__imp_CoTaskMemAlloc
0x18002bc5c  mov     rsi, rax
0x18002bc5f  test    rax, rax
0x18002bc62  jnz     short loc_18002BC6B
0x18002bc64  mov     ebx, 8007000Eh
0x18002bc69  jmp     short loc_18002BCE3
0x18002bc6b  mov     r8d, ebp; nSize
0x18002bc6e  mov     rdx, rsi; lpDst
0x18002bc71  mov     rcx, rdi; lpSrc
0x18002bc74  call    cs:__imp_ExpandEnvironmentStringsW
0x18002bc7a  mov     r14d, eax
0x18002bc7d  test    eax, eax
0x18002bc7f  jz      short loc_18002BCCE
0x18002bc81  cmp     eax, ebp
0x18002bc83  ja      short loc_18002BCCE
0x18002bc85  mov     rcx, rdi; pv
0x18002bc88  mov     ebx, r12d
0x18002bc8b  call    cs:__imp_CoTaskMemFree
0x18002bc91  mov     rdi, rsi
0x18002bc94  lea     esi, [r14-1]
0x18002bc98  cmp     [rdi+rsi*2], r12w
0x18002bc9d  jnz     short loc_18002BCDE
0x18002bc9f  mov     rcx, r15
0x18002bca2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002bca7  test    rdi, rdi
0x18002bcaa  jz      short loc_18002BCC9
0x18002bcac  lea     eax, [rsi+1]
0x18002bcaf  mov     ecx, eax
0x18002bcb1  test    eax, eax
0x18002bcb3  jz      short loc_18002BCC9
0x18002bcb5  dec     rax
0x18002bcb8  mov     [r15], rdi
0x18002bcbb  mov     [r15+8], rax
0x18002bcbf  mov     [r15+10h], rcx
0x18002bcc3  mov     [rdi+rcx*2-2], r12w
0x18002bcc9  mov     rdi, r12
0x18002bccc  jmp     short loc_18002BCE3
0x18002bcce  mov     rcx, rsi; pv
0x18002bcd1  mov     ebx, 8007007Ah
0x18002bcd6  call    cs:__imp_CoTaskMemFree
0x18002bcdc  jmp     short loc_18002BCE3
0x18002bcde  mov     ebx, 8007000Dh
0x18002bce3  mov     rcx, rdi; pv
0x18002bce6  call    cs:__imp_CoTaskMemFree
0x18002bcec  mov     rbp, [rsp+68h+arg_8]
0x18002bcf1  mov     eax, ebx
0x18002bcf3  mov     rbx, [rsp+68h+arg_0]
0x18002bcf8  add     rsp, 40h
0x18002bcfc  pop     r15
0x18002bcfe  pop     r14
0x18002bd00  pop     r12
0x18002bd02  pop     rdi
0x18002bd03  pop     rsi
0x18002bd04  retn
```
