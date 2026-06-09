# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1802e92d8`
- end: `0x1802e948a`
- name: `?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802e8de8`

## callees

- `0x18008a6f0`
- `0x1802e92d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1802e936b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1802e93db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1802e936b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1802e93db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e9410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e945b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e946b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e9410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e945b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e946b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802e9328`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802e939a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802e9328`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802e939a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e93ca`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e93f9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e93ca`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1802e93f9`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
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
  v6 = RegQueryValueExW(a2, L"NotesApp", 0, &Type, 0, (LPDWORD)&cb);
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
    v8 = RegQueryValueExW(a2, L"NotesApp", 0, &Type, lpData, (LPDWORD)&cb);
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
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
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
0x1802e92d8  mov     r11, rsp
0x1802e92db  mov     [r11+8], rbx
0x1802e92df  mov     [r11+10h], rbp
0x1802e92e3  mov     [r11+20h], r9b
0x1802e92e7  mov     [r11+18h], r8
0x1802e92eb  push    rsi
0x1802e92ec  push    rdi
0x1802e92ed  push    r12
0x1802e92ef  push    r14
0x1802e92f1  push    r15
0x1802e92f3  sub     rsp, 30h
0x1802e92f7  xor     r12d, r12d
0x1802e92fa  lea     rax, [r11+20h]
0x1802e92fe  mov     rsi, rdx
0x1802e9301  mov     [r11-30h], rax
0x1802e9305  mov     r15, rcx
0x1802e9308  mov     [r11-38h], r12
0x1802e930c  mov     rcx, rsi; hKey
0x1802e930f  mov     [r11+18h], r12d
0x1802e9313  lea     r9, [r11+18h]; lpType
0x1802e9317  mov     [r11+20h], r12d
0x1802e931b  xor     r8d, r8d; lpReserved
0x1802e931e  lea     rdx, aNotesapp; "NotesApp"
0x1802e9325  mov     edi, r12d
0x1802e9328  call    cs:__imp_RegQueryValueExW
0x1802e932e  mov     ebx, eax
0x1802e9330  mov     ebp, 80070000h
0x1802e9335  test    eax, eax
0x1802e9337  jle     short loc_1802E933E
0x1802e9339  movzx   ebx, ax
0x1802e933c  or      ebx, ebp
0x1802e933e  test    ebx, ebx
0x1802e9340  js      loc_1802E9468
0x1802e9346  mov     eax, [rsp+58h+Type]
0x1802e934a  dec     eax
0x1802e934c  cmp     eax, 1
0x1802e934f  ja      loc_1802E9463
0x1802e9355  mov     eax, dword ptr [rsp+58h+cb]
0x1802e9359  test    eax, eax
0x1802e935b  jz      loc_1802E9463
0x1802e9361  test    al, 1
0x1802e9363  jnz     loc_1802E9463
0x1802e9369  mov     ecx, eax; cb
0x1802e936b  call    cs:__imp_CoTaskMemAlloc
0x1802e9371  mov     rdi, rax
0x1802e9374  test    rax, rax
0x1802e9377  jz      short loc_1802E93E9
0x1802e9379  lea     rax, [rsp+58h+cb]
0x1802e937e  xor     r8d, r8d; lpReserved
0x1802e9381  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1802e9386  lea     r9, [rsp+58h+Type]; lpType
0x1802e938b  lea     rdx, aNotesapp; "NotesApp"
0x1802e9392  mov     [rsp+58h+lpData], rdi; lpData
0x1802e9397  mov     rcx, rsi; hKey
0x1802e939a  call    cs:__imp_RegQueryValueExW
0x1802e93a0  mov     ebx, eax
0x1802e93a2  test    eax, eax
0x1802e93a4  jle     short loc_1802E93AB
0x1802e93a6  movzx   ebx, ax
0x1802e93a9  or      ebx, ebp
0x1802e93ab  test    ebx, ebx
0x1802e93ad  js      loc_1802E9468
0x1802e93b3  mov     esi, dword ptr [rsp+58h+cb]
0x1802e93b7  shr     esi, 1
0x1802e93b9  dec     esi
0x1802e93bb  cmp     [rsp+58h+Type], 2
0x1802e93c0  jnz     short loc_1802E941D
0x1802e93c2  xor     r8d, r8d; nSize
0x1802e93c5  xor     edx, edx; lpDst
0x1802e93c7  mov     rcx, rdi; lpSrc
0x1802e93ca  call    cs:__imp_ExpandEnvironmentStringsW
0x1802e93d0  mov     ebp, eax
0x1802e93d2  test    eax, eax
0x1802e93d4  jz      short loc_1802E941D
0x1802e93d6  mov     ecx, ebp
0x1802e93d8  add     rcx, rcx; cb
0x1802e93db  call    cs:__imp_CoTaskMemAlloc
0x1802e93e1  mov     rsi, rax
0x1802e93e4  test    rax, rax
0x1802e93e7  jnz     short loc_1802E93F0
0x1802e93e9  mov     ebx, 8007000Eh
0x1802e93ee  jmp     short loc_1802E9468
0x1802e93f0  mov     r8d, ebp; nSize
0x1802e93f3  mov     rdx, rsi; lpDst
0x1802e93f6  mov     rcx, rdi; lpSrc
0x1802e93f9  call    cs:__imp_ExpandEnvironmentStringsW
0x1802e93ff  mov     r14d, eax
0x1802e9402  test    eax, eax
0x1802e9404  jz      short loc_1802E9453
0x1802e9406  cmp     eax, ebp
0x1802e9408  ja      short loc_1802E9453
0x1802e940a  mov     rcx, rdi; pv
0x1802e940d  mov     ebx, r12d
0x1802e9410  call    cs:__imp_CoTaskMemFree
0x1802e9416  mov     rdi, rsi
0x1802e9419  lea     esi, [r14-1]
0x1802e941d  cmp     [rdi+rsi*2], r12w
0x1802e9422  jnz     short loc_1802E9463
0x1802e9424  mov     rcx, r15
0x1802e9427  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e942c  test    rdi, rdi
0x1802e942f  jz      short loc_1802E944E
0x1802e9431  lea     eax, [rsi+1]
0x1802e9434  mov     ecx, eax
0x1802e9436  test    eax, eax
0x1802e9438  jz      short loc_1802E944E
0x1802e943a  dec     rax
0x1802e943d  mov     [r15], rdi
0x1802e9440  mov     [r15+8], rax
0x1802e9444  mov     [r15+10h], rcx
0x1802e9448  mov     [rdi+rcx*2-2], r12w
0x1802e944e  mov     rdi, r12
0x1802e9451  jmp     short loc_1802E9468
0x1802e9453  mov     rcx, rsi; pv
0x1802e9456  mov     ebx, 8007007Ah
0x1802e945b  call    cs:__imp_CoTaskMemFree
0x1802e9461  jmp     short loc_1802E9468
0x1802e9463  mov     ebx, 8007000Dh
0x1802e9468  mov     rcx, rdi; pv
0x1802e946b  call    cs:__imp_CoTaskMemFree
0x1802e9471  mov     rbp, [rsp+58h+arg_8]
0x1802e9476  mov     eax, ebx
0x1802e9478  mov     rbx, [rsp+58h+arg_0]
0x1802e947d  add     rsp, 30h
0x1802e9481  pop     r15
0x1802e9483  pop     r14
0x1802e9485  pop     r12
0x1802e9487  pop     rdi
0x1802e9488  pop     rsi
0x1802e9489  retn
```
