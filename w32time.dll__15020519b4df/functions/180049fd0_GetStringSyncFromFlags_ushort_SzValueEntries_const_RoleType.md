# GetStringSyncFromFlags(ushort * *,SzValueEntries const *,RoleType)

- ea: `0x180049fd0`
- end: `0x18004a2dd`
- name: `?GetStringSyncFromFlags@@YAJPEAPEAGPEBUSzValueEntries@@W4RoleType@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18004a2f0`
- `0x18004a310`

## callees

- `0x18000bde0`
- `0x18003d270`
- `0x180049fd0`
- `0x18004a3cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a0c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004a0c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a108`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a1ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a248`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a108`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a1ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004a248`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a03d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a152`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a03d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a2a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a2a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a210`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a210`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a08b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a1a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a08b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a1a2`

## string_xrefs

- `0x18004a02f`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004a144`: `System\CurrentControlSet\Services\W32Time`

## pseudocode

```c
__int64 __fastcall GetStringSyncFromFlags(unsigned __int16 **a1, __int64 a2, int a3)
{
  signed int v6; // ebx
  unsigned __int16 *v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rdx
  LSTATUS ValueW; // eax
  bool v14; // cc
  unsigned __int16 *v15; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rbx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 pvData[259]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v24; // [rsp+266h] [rbp+166h]

  pcbData = 0;
  pdwType = 0;
  hKey = 0;
  hkey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 3u, &hkey) )
  {
    pcbData = 520;
    if ( !RegGetValueW(hkey, 0, L"Type", 0xFFFFu, &pdwType, pvData, &pcbData) )
    {
      if ( pdwType != 1 )
      {
LABEL_4:
        v6 = -2147418113;
        goto LABEL_32;
      }
      v24 = 0;
      if ( (unsigned int)_o__wcsicmp(pvData, L"NoSync") && (a3 == 3 || !(unsigned int)HasNewPeerlist()) )
        v7 = *(unsigned __int16 **)(a2 + 16);
      else
        v7 = pvData;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      v9 = v8 + 1;
      v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v8 + 1));
      *a1 = v10;
      if ( !v10 )
        goto LABEL_13;
      v11 = v7;
      v12 = v9;
LABEL_27:
      v6 = StringCchCopyW(v10, v12, v11);
      if ( v6 < 0 )
        goto LABEL_32;
      goto LABEL_28;
    }
  }
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time", 0, 3u, &hKey);
  v6 = ValueW;
  v14 = ValueW <= 0;
  if ( !ValueW )
  {
    pcbData = 520;
    ValueW = RegGetValueW(hKey, 0, L"SpecialType", 0xFFFFu, &pdwType, pvData, &pcbData);
    v6 = ValueW;
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v14 = ValueW <= 0;
        goto LABEL_30;
      }
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v16) );
      v17 = v16 + 1;
      v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v16 + 1));
      *a1 = v10;
      if ( v10 )
      {
        v11 = *(const unsigned __int16 **)(a2 + 16);
        v12 = v17;
        goto LABEL_27;
      }
    }
    else
    {
      if ( pdwType != 1 )
        goto LABEL_4;
      v24 = 0;
      v15 = (unsigned __int16 *)LocalAlloc(0x40u, pcbData);
      *a1 = v15;
      if ( v15 )
      {
        v6 = StringCchCopyW(v15, (unsigned __int64)pcbData >> 1, pvData);
        if ( v6 < 0 )
          goto LABEL_32;
        ValueW = RegDeleteValueW(hKey, L"SpecialType");
        v6 = ValueW;
        v14 = ValueW <= 0;
        if ( !ValueW )
        {
LABEL_28:
          v6 = 0;
          goto LABEL_32;
        }
        goto LABEL_30;
      }
    }
LABEL_13:
    v6 = -2147024882;
    goto LABEL_32;
  }
LABEL_30:
  if ( !v14 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049fd0  mov     [rsp-8+arg_10], rbx
0x180049fd5  mov     [rsp-8+arg_18], rsi
0x180049fda  push    rbp
0x180049fdb  push    rdi
0x180049fdc  push    r14
0x180049fde  lea     rbp, [rsp-180h]
0x180049fe6  sub     rsp, 280h
0x180049fed  mov     rax, cs:__security_cookie
0x180049ff4  xor     rax, rsp
0x180049ff7  mov     [rbp+190h+var_20], rax
0x180049ffe  xor     r14d, r14d
0x18004a001  lea     rax, [rsp+290h+hkey]
0x18004a006  mov     ebx, r8d
0x18004a009  mov     [rsp+290h+var_250], r14d
0x18004a00e  mov     rdi, rdx
0x18004a011  mov     [rsp+290h+pdwType], r14d
0x18004a016  mov     rsi, rcx
0x18004a019  mov     [rsp+290h+hKey], r14
0x18004a01e  lea     r9d, [r14+3]; samDesired
0x18004a022  mov     [rsp+290h+hkey], r14
0x18004a027  xor     r8d, r8d; ulOptions
0x18004a02a  mov     [rsp+290h+phkResult], rax; phkResult
0x18004a02f  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004a036  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a03d  call    cs:__imp_RegOpenKeyExW
0x18004a044  nop     dword ptr [rax+rax+00h]
0x18004a049  test    eax, eax
0x18004a04b  jnz     loc_18004A131
0x18004a051  mov     rcx, [rsp+290h+hkey]; hkey
0x18004a056  lea     rax, [rsp+290h+var_250]
0x18004a05b  mov     [rsp+290h+pcbData], rax; pcbData
0x18004a060  lea     r8, aType; "Type"
0x18004a067  lea     rax, [rsp+290h+var_230]
0x18004a06c  mov     [rsp+290h+var_250], 208h
0x18004a074  mov     [rsp+290h+pvData], rax; pvData
0x18004a079  mov     r9d, 0FFFFh; dwFlags
0x18004a07f  lea     rax, [rsp+290h+pdwType]
0x18004a084  xor     edx, edx; lpSubKey
0x18004a086  mov     [rsp+290h+phkResult], rax; pdwType
0x18004a08b  call    cs:__imp_RegGetValueW
0x18004a092  nop     dword ptr [rax+rax+00h]
0x18004a097  test    eax, eax
0x18004a099  jnz     loc_18004A131
0x18004a09f  cmp     [rsp+290h+pdwType], 1
0x18004a0a4  jz      short loc_18004A0B0
0x18004a0a6  mov     ebx, 8000FFFFh
0x18004a0ab  jmp     loc_18004A287
0x18004a0b0  lea     rdx, aNosync; "NoSync"
0x18004a0b7  mov     [rbp+190h+var_2A], r14w
0x18004a0bf  lea     rcx, [rsp+290h+var_230]
0x18004a0c4  call    cs:__imp__o__wcsicmp
0x18004a0cb  nop     dword ptr [rax+rax+00h]
0x18004a0d0  test    eax, eax
0x18004a0d2  jz      short loc_18004A0E8
0x18004a0d4  cmp     ebx, 3
0x18004a0d7  jz      short loc_18004A0E2
0x18004a0d9  call    ?HasNewPeerlist@@YAHXZ; HasNewPeerlist(void)
0x18004a0de  test    eax, eax
0x18004a0e0  jnz     short loc_18004A0E8
0x18004a0e2  mov     rbx, [rdi+10h]
0x18004a0e6  jmp     short loc_18004A0ED
0x18004a0e8  lea     rbx, [rsp+290h+var_230]
0x18004a0ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a0f1  inc     rax
0x18004a0f4  cmp     [rbx+rax*2], r14w
0x18004a0f9  jnz     short loc_18004A0F1
0x18004a0fb  lea     rdi, [rax+1]
0x18004a0ff  mov     ecx, 40h ; '@'; uFlags
0x18004a104  lea     rdx, [rdi+rdi]; uBytes
0x18004a108  call    cs:__imp_LocalAlloc
0x18004a10f  nop     dword ptr [rax+rax+00h]
0x18004a114  mov     [rsi], rax
0x18004a117  test    rax, rax
0x18004a11a  jnz     short loc_18004A126
0x18004a11c  mov     ebx, 8007000Eh
0x18004a121  jmp     loc_18004A287
0x18004a126  mov     r8, rbx
0x18004a129  mov     rdx, rdi
0x18004a12c  jmp     loc_18004A267
0x18004a131  lea     rax, [rsp+290h+hKey]
0x18004a136  mov     r9d, 3; samDesired
0x18004a13c  xor     r8d, r8d; ulOptions
0x18004a13f  mov     [rsp+290h+phkResult], rax; phkResult
0x18004a144  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\W3"...
0x18004a14b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a152  call    cs:__imp_RegOpenKeyExW
0x18004a159  nop     dword ptr [rax+rax+00h]
0x18004a15e  mov     ebx, eax
0x18004a160  test    eax, eax
0x18004a162  jnz     loc_18004A27C
0x18004a168  mov     rcx, [rsp+290h+hKey]; hkey
0x18004a16d  lea     rax, [rsp+290h+var_250]
0x18004a172  mov     [rsp+290h+pcbData], rax; pcbData
0x18004a177  lea     r8, aSpecialtype; "SpecialType"
0x18004a17e  lea     rax, [rsp+290h+var_230]
0x18004a183  mov     [rsp+290h+var_250], 208h
0x18004a18b  mov     [rsp+290h+pvData], rax; pvData
0x18004a190  mov     r9d, 0FFFFh; dwFlags
0x18004a196  lea     rax, [rsp+290h+pdwType]
0x18004a19b  xor     edx, edx; lpSubKey
0x18004a19d  mov     [rsp+290h+phkResult], rax; pdwType
0x18004a1a2  call    cs:__imp_RegGetValueW
0x18004a1a9  nop     dword ptr [rax+rax+00h]
0x18004a1ae  mov     ebx, eax
0x18004a1b0  test    eax, eax
0x18004a1b2  jnz     short loc_18004A224
0x18004a1b4  cmp     [rsp+290h+pdwType], 1
0x18004a1b9  jnz     loc_18004A0A6
0x18004a1bf  mov     edx, [rsp+290h+var_250]; uBytes
0x18004a1c3  lea     ecx, [rax+40h]; uFlags
0x18004a1c6  mov     [rbp+190h+var_2A], r14w
0x18004a1ce  call    cs:__imp_LocalAlloc
0x18004a1d5  nop     dword ptr [rax+rax+00h]
0x18004a1da  mov     [rsi], rax
0x18004a1dd  test    rax, rax
0x18004a1e0  jz      loc_18004A11C
0x18004a1e6  mov     edx, [rsp+290h+var_250]
0x18004a1ea  lea     r8, [rsp+290h+var_230]; unsigned __int16 *
0x18004a1ef  shr     rdx, 1; unsigned __int64
0x18004a1f2  mov     rcx, rax; unsigned __int16 *
0x18004a1f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a1fa  mov     ebx, eax
0x18004a1fc  test    eax, eax
0x18004a1fe  js      loc_18004A287
0x18004a204  mov     rcx, [rsp+290h+hKey]; hKey
0x18004a209  lea     rdx, aSpecialtype; "SpecialType"
0x18004a210  call    cs:__imp_RegDeleteValueW
0x18004a217  nop     dword ptr [rax+rax+00h]
0x18004a21c  mov     ebx, eax
0x18004a21e  test    eax, eax
0x18004a220  jz      short loc_18004A275
0x18004a222  jmp     short loc_18004A27C
0x18004a224  cmp     eax, 2
0x18004a227  jnz     short loc_18004A27A
0x18004a229  mov     rcx, [rdi+10h]
0x18004a22d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a231  inc     rax
0x18004a234  cmp     [rcx+rax*2], r14w
0x18004a239  jnz     short loc_18004A231
0x18004a23b  lea     rbx, [rax+1]
0x18004a23f  mov     ecx, 40h ; '@'; uFlags
0x18004a244  lea     rdx, [rbx+rbx]; uBytes
0x18004a248  call    cs:__imp_LocalAlloc
0x18004a24f  nop     dword ptr [rax+rax+00h]
0x18004a254  mov     [rsi], rax
0x18004a257  test    rax, rax
0x18004a25a  jz      loc_18004A11C
0x18004a260  mov     r8, [rdi+10h]; unsigned __int16 *
0x18004a264  mov     rdx, rbx; unsigned __int64
0x18004a267  mov     rcx, rax; unsigned __int16 *
0x18004a26a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a26f  mov     ebx, eax
0x18004a271  test    eax, eax
0x18004a273  js      short loc_18004A287
0x18004a275  mov     ebx, r14d
0x18004a278  jmp     short loc_18004A287
0x18004a27a  test    eax, eax
0x18004a27c  jle     short loc_18004A287
0x18004a27e  movzx   ebx, ax
0x18004a281  or      ebx, 80070000h
0x18004a287  mov     rcx, [rsp+290h+hKey]; hKey
0x18004a28c  test    rcx, rcx
0x18004a28f  jz      short loc_18004A29D
0x18004a291  call    cs:__imp_RegCloseKey
0x18004a298  nop     dword ptr [rax+rax+00h]
0x18004a29d  mov     rcx, [rsp+290h+hkey]; hKey
0x18004a2a2  test    rcx, rcx
0x18004a2a5  jz      short loc_18004A2B3
0x18004a2a7  call    cs:__imp_RegCloseKey
0x18004a2ae  nop     dword ptr [rax+rax+00h]
0x18004a2b3  mov     eax, ebx
0x18004a2b5  mov     rcx, [rbp+190h+var_20]
0x18004a2bc  xor     rcx, rsp; StackCookie
0x18004a2bf  call    __security_check_cookie
0x18004a2c4  lea     r11, [rsp+290h+var_10]
0x18004a2cc  mov     rbx, [r11+30h]
0x18004a2d0  mov     rsi, [r11+38h]
0x18004a2d4  mov     rsp, r11
0x18004a2d7  pop     r14
0x18004a2d9  pop     rdi
0x18004a2da  pop     rbp
0x18004a2db  retn
```
