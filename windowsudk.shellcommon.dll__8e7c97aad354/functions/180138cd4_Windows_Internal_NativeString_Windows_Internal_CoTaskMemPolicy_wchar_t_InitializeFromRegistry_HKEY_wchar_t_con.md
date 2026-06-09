# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_InitializeFromRegistry(HKEY__ *,wchar_t const *,bool)

- ea: `0x180138cd4`
- end: `0x180138e86`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEB_W_N@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180145674`

## callees

- `0x1800636c4`
- `0x180138cd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180138d24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180138d96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180138d24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180138d96`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180138dc6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180138df5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180138dc6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180138df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180138e67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138dd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180138dd7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        __int64 a3)
{
  BYTE *lpData; // rdi
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rsi
  DWORD v10; // eax
  DWORD v11; // ebp
  WCHAR *v12; // rax
  WCHAR *v13; // rsi
  DWORD v14; // eax
  DWORD v15; // r14d
  __int64 v16; // rax
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF
  int v19; // [rsp+74h] [rbp+1Ch]
  SIZE_T cb; // [rsp+78h] [rbp+20h] BYREF

  v19 = HIDWORD(a3);
  Type = 0;
  LODWORD(cb) = 0;
  lpData = 0;
  v6 = RegQueryValueExW(a2, L"FeatureTogglesList", 0, &Type, 0, (LPDWORD)&cb);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    if ( Type - 1 > 1 || !(_DWORD)cb || (cb & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
    if ( !lpData )
    {
LABEL_14:
      v7 = -2147024882;
      goto LABEL_25;
    }
    v8 = RegQueryValueExW(a2, L"FeatureTogglesList", 0, &Type, lpData, (LPDWORD)&cb);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      v9 = ((unsigned int)cb >> 1) - 1;
      if ( Type == 2 )
      {
        v10 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v11 = v10;
        if ( v10 )
        {
          v12 = (WCHAR *)CoTaskMemAlloc(2LL * v10);
          v13 = v12;
          if ( !v12 )
            goto LABEL_14;
          v14 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v12, v11);
          v15 = v14;
          if ( !v14 || v14 > v11 )
          {
            v7 = -2147024774;
            CoTaskMemFree(v13);
            goto LABEL_25;
          }
          v7 = 0;
          CoTaskMemFree(lpData);
          lpData = (BYTE *)v13;
          v9 = v15 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v9] )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(a1);
        if ( lpData )
        {
          v16 = (unsigned int)(v9 + 1);
          if ( (_DWORD)v9 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v16 - 1);
            a1[2] = (BYTE *)(unsigned int)v16;
            *(_WORD *)&lpData[2 * (unsigned int)v16 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v7 = -2147024883;
    }
  }
LABEL_25:
  CoTaskMemFree(lpData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180138cd4  mov     r11, rsp
0x180138cd7  mov     [r11+8], rbx
0x180138cdb  mov     [r11+10h], rbp
0x180138cdf  mov     [r11+20h], r9b
0x180138ce3  mov     [r11+18h], r8
0x180138ce7  push    rsi
0x180138ce8  push    rdi
0x180138ce9  push    r12
0x180138ceb  push    r14
0x180138ced  push    r15
0x180138cef  sub     rsp, 30h
0x180138cf3  xor     r12d, r12d
0x180138cf6  lea     rax, [r11+20h]
0x180138cfa  mov     rsi, rdx
0x180138cfd  mov     [r11-30h], rax
0x180138d01  mov     r15, rcx
0x180138d04  mov     [r11-38h], r12
0x180138d08  mov     rcx, rsi; hKey
0x180138d0b  mov     [r11+18h], r12d
0x180138d0f  lea     r9, [r11+18h]; lpType
0x180138d13  mov     [r11+20h], r12d
0x180138d17  xor     r8d, r8d; lpReserved
0x180138d1a  lea     rdx, aFeaturetoggles; "FeatureTogglesList"
0x180138d21  mov     edi, r12d
0x180138d24  call    cs:__imp_RegQueryValueExW
0x180138d2a  mov     ebx, eax
0x180138d2c  mov     ebp, 80070000h
0x180138d31  test    eax, eax
0x180138d33  jle     short loc_180138D3A
0x180138d35  movzx   ebx, ax
0x180138d38  or      ebx, ebp
0x180138d3a  test    ebx, ebx
0x180138d3c  js      loc_180138E64
0x180138d42  mov     eax, [rsp+58h+Type]
0x180138d46  dec     eax
0x180138d48  cmp     eax, 1
0x180138d4b  ja      loc_180138E5F
0x180138d51  mov     eax, dword ptr [rsp+58h+cb]
0x180138d55  test    eax, eax
0x180138d57  jz      loc_180138E5F
0x180138d5d  test    al, 1
0x180138d5f  jnz     loc_180138E5F
0x180138d65  mov     ecx, eax; cb
0x180138d67  call    cs:__imp_CoTaskMemAlloc
0x180138d6d  mov     rdi, rax
0x180138d70  test    rax, rax
0x180138d73  jz      short loc_180138DE5
0x180138d75  lea     rax, [rsp+58h+cb]
0x180138d7a  xor     r8d, r8d; lpReserved
0x180138d7d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180138d82  lea     r9, [rsp+58h+Type]; lpType
0x180138d87  lea     rdx, aFeaturetoggles; "FeatureTogglesList"
0x180138d8e  mov     [rsp+58h+lpData], rdi; lpData
0x180138d93  mov     rcx, rsi; hKey
0x180138d96  call    cs:__imp_RegQueryValueExW
0x180138d9c  mov     ebx, eax
0x180138d9e  test    eax, eax
0x180138da0  jle     short loc_180138DA7
0x180138da2  movzx   ebx, ax
0x180138da5  or      ebx, ebp
0x180138da7  test    ebx, ebx
0x180138da9  js      loc_180138E64
0x180138daf  mov     esi, dword ptr [rsp+58h+cb]
0x180138db3  shr     esi, 1
0x180138db5  dec     esi
0x180138db7  cmp     [rsp+58h+Type], 2
0x180138dbc  jnz     short loc_180138E19
0x180138dbe  xor     r8d, r8d; nSize
0x180138dc1  xor     edx, edx; lpDst
0x180138dc3  mov     rcx, rdi; lpSrc
0x180138dc6  call    cs:__imp_ExpandEnvironmentStringsW
0x180138dcc  mov     ebp, eax
0x180138dce  test    eax, eax
0x180138dd0  jz      short loc_180138E19
0x180138dd2  mov     ecx, ebp
0x180138dd4  add     rcx, rcx; cb
0x180138dd7  call    cs:__imp_CoTaskMemAlloc
0x180138ddd  mov     rsi, rax
0x180138de0  test    rax, rax
0x180138de3  jnz     short loc_180138DEC
0x180138de5  mov     ebx, 8007000Eh
0x180138dea  jmp     short loc_180138E64
0x180138dec  mov     r8d, ebp; nSize
0x180138def  mov     rdx, rsi; lpDst
0x180138df2  mov     rcx, rdi; lpSrc
0x180138df5  call    cs:__imp_ExpandEnvironmentStringsW
0x180138dfb  mov     r14d, eax
0x180138dfe  test    eax, eax
0x180138e00  jz      short loc_180138E4F
0x180138e02  cmp     eax, ebp
0x180138e04  ja      short loc_180138E4F
0x180138e06  mov     rcx, rdi; pv
0x180138e09  mov     ebx, r12d
0x180138e0c  call    cs:__imp_CoTaskMemFree
0x180138e12  mov     rdi, rsi
0x180138e15  lea     esi, [r14-1]
0x180138e19  cmp     [rdi+rsi*2], r12w
0x180138e1e  jnz     short loc_180138E5F
0x180138e20  mov     rcx, r15
0x180138e23  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_Free(void)
0x180138e28  test    rdi, rdi
0x180138e2b  jz      short loc_180138E4A
0x180138e2d  lea     eax, [rsi+1]
0x180138e30  mov     ecx, eax
0x180138e32  test    eax, eax
0x180138e34  jz      short loc_180138E4A
0x180138e36  dec     rax
0x180138e39  mov     [r15], rdi
0x180138e3c  mov     [r15+8], rax
0x180138e40  mov     [r15+10h], rcx
0x180138e44  mov     [rdi+rcx*2-2], r12w
0x180138e4a  mov     rdi, r12
0x180138e4d  jmp     short loc_180138E64
0x180138e4f  mov     rcx, rsi; pv
0x180138e52  mov     ebx, 8007007Ah
0x180138e57  call    cs:__imp_CoTaskMemFree
0x180138e5d  jmp     short loc_180138E64
0x180138e5f  mov     ebx, 8007000Dh
0x180138e64  mov     rcx, rdi; pv
0x180138e67  call    cs:__imp_CoTaskMemFree
0x180138e6d  mov     rbp, [rsp+58h+arg_8]
0x180138e72  mov     eax, ebx
0x180138e74  mov     rbx, [rsp+58h+arg_0]
0x180138e79  add     rsp, 30h
0x180138e7d  pop     r15
0x180138e7f  pop     r14
0x180138e81  pop     r12
0x180138e83  pop     rdi
0x180138e84  pop     rsi
0x180138e85  retn
```
