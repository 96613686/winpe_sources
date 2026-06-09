# ReadLSStatusFromRegistry(int *,_LEAP_SECOND_DATA_REGISTRY_ENTRY * *,ulong *)

- ea: `0x18002b140`
- end: `0x18002b3f6`
- name: `?ReadLSStatusFromRegistry@@YAJPEAHPEAPEAU_LEAP_SECOND_DATA_REGISTRY_ENTRY@@PEAK@Z`
- size: `694`
- prototype: `__int64 __fastcall(int *, struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800092a0`
- `0x18004f97c`

## callees

- `0x18002b140`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067622`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b3e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067622`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b310`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b310`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b19b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b19b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b3c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067642`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b1fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b277`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b369`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b1fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b277`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b369`

## pseudocode

```c
__int64 __fastcall ReadLSStatusFromRegistry(int *a1, struct _LEAP_SECOND_DATA_REGISTRY_ENTRY **a2, unsigned int *a3)
{
  struct _LEAP_SECOND_DATA_REGISTRY_ENTRY *v6; // rsi
  LSTATUS v7; // eax
  unsigned int v8; // edi
  LSTATUS ValueW; // eax
  int v10; // eax
  LSTATUS v11; // eax
  struct _LEAP_SECOND_DATA_REGISTRY_ENTRY *v12; // rax
  LSTATUS v13; // eax
  DWORD pcbData; // [rsp+90h] [rbp+8h] BYREF
  DWORD pdwType; // [rsp+98h] [rbp+10h] BYREF
  int pvData; // [rsp+A0h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+A8h] [rbp+20h] BYREF

  v6 = 0;
  pcbData = 0;
  hkey = 0;
  pdwType = 0;
  pvData = 0;
  *a3 = 0;
  *a2 = 0;
  *a1 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\LeapSecondInformation", 0, 1u, &hkey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"Enabled", 0xFFFFu, &pdwType, &pvData, &pcbData);
    v8 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
    }
    else
    {
      if ( pdwType != 4 || pcbData > 4 )
        goto LABEL_10;
      v10 = pvData;
      *a1 = pvData;
      if ( !v10 )
      {
        v8 = 0;
        goto LABEL_25;
      }
      pcbData = 0;
      v11 = RegGetValueW(hkey, 0, L"LeapSeconds", 0xFFFFu, &pdwType, 0, &pcbData);
      v8 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_25;
      }
      if ( pdwType != 3 )
      {
LABEL_10:
        v8 = -2147418113;
        goto LABEL_25;
      }
      if ( !pcbData )
      {
        v8 = 0;
        goto LABEL_25;
      }
      v12 = (struct _LEAP_SECOND_DATA_REGISTRY_ENTRY *)LocalAlloc(0x40u, pcbData);
      v6 = v12;
      if ( !v12 )
      {
        v8 = -2147024882;
        goto LABEL_25;
      }
      v13 = RegGetValueW(hkey, 0, L"LeapSeconds", 0xFFFFu, &pdwType, v12, &pcbData);
      v8 = v13;
      if ( !v13 )
      {
        if ( pdwType == 3 )
        {
          *a2 = v6;
          *a3 = pcbData / 0xC;
          v6 = 0;
          v8 = 0;
          goto LABEL_25;
        }
        goto LABEL_10;
      }
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
    }
  }
LABEL_25:
  if ( v6 )
    LocalFree(v6);
  if ( hkey )
    RegCloseKey(hkey);
  return v8;
}

```

## disassembly

```asm
0x18002b140  mov     r11, rsp
0x18002b143  push    rbx
0x18002b144  push    rsi
0x18002b145  push    rdi
0x18002b146  push    r12
0x18002b148  push    r14
0x18002b14a  push    r15
0x18002b14c  sub     rsp, 58h
0x18002b150  mov     r14, r8
0x18002b153  mov     r15, rdx
0x18002b156  mov     rbx, rcx
0x18002b159  xor     r12d, r12d
0x18002b15c  mov     esi, r12d
0x18002b15f  mov     [r11-48h], r12
0x18002b163  mov     [r11+8], r12d
0x18002b167  mov     [r11+20h], r12
0x18002b16b  mov     [r11+10h], r12d
0x18002b16f  mov     [r11+18h], r12d
0x18002b173  mov     [r8], r12d
0x18002b176  mov     [rdx], r12
0x18002b179  mov     [rcx], r12d
0x18002b17c  lea     rax, [r11+20h]
0x18002b180  mov     [r11-68h], rax
0x18002b184  mov     r9d, 1; samDesired
0x18002b18a  xor     r8d, r8d; ulOptions
0x18002b18d  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lea"...
0x18002b194  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b19b  call    cs:__imp_RegOpenKeyExW
0x18002b1a2  nop     dword ptr [rax+rax+00h]
0x18002b1a7  mov     edi, eax
0x18002b1a9  test    eax, eax
0x18002b1ab  jnz     loc_18002B2B1
0x18002b1b1  mov     [rsp+88h+arg_0], 4
0x18002b1bc  lea     rax, [rsp+88h+arg_0]
0x18002b1c4  mov     [rsp+88h+pcbData], rax; pcbData
0x18002b1c9  lea     rax, [rsp+88h+arg_10]
0x18002b1d1  mov     [rsp+88h+pvData], rax; pvData
0x18002b1d6  lea     rax, [rsp+88h+arg_8]
0x18002b1de  mov     [rsp+88h+pdwType], rax; pdwType
0x18002b1e3  mov     r9d, 0FFFFh; dwFlags
0x18002b1e9  lea     r8, aEnabled; "Enabled"
0x18002b1f0  xor     edx, edx; lpSubKey
0x18002b1f2  mov     rcx, [rsp+88h+hkey]; hkey
0x18002b1fa  call    cs:__imp_RegGetValueW
0x18002b201  nop     dword ptr [rax+rax+00h]
0x18002b206  mov     edi, eax
0x18002b208  test    eax, eax
0x18002b20a  jnz     loc_18002B2C5
0x18002b210  cmp     [rsp+88h+arg_8], 4
0x18002b218  jnz     loc_18002B2A7
0x18002b21e  cmp     [rsp+88h+arg_0], 4
0x18002b226  ja      short loc_18002B2A7
0x18002b228  mov     eax, [rsp+88h+arg_10]
0x18002b22f  mov     [rbx], eax
0x18002b231  test    eax, eax
0x18002b233  jz      loc_18002B2ED
0x18002b239  mov     [rsp+88h+arg_0], r12d
0x18002b241  lea     rax, [rsp+88h+arg_0]
0x18002b249  mov     [rsp+88h+pcbData], rax; pcbData
0x18002b24e  mov     [rsp+88h+pvData], r12; pvData
0x18002b253  lea     rax, [rsp+88h+arg_8]
0x18002b25b  mov     [rsp+88h+pdwType], rax; pdwType
0x18002b260  mov     r9d, 0FFFFh; dwFlags
0x18002b266  lea     r8, aLeapseconds; "LeapSeconds"
0x18002b26d  xor     edx, edx; lpSubKey
0x18002b26f  mov     rcx, [rsp+88h+hkey]; hkey
0x18002b277  call    cs:__imp_RegGetValueW
0x18002b27e  nop     dword ptr [rax+rax+00h]
0x18002b283  mov     edi, eax
0x18002b285  test    eax, eax
0x18002b287  jz      short loc_18002B29D
0x18002b289  jle     loc_18002B3B6
0x18002b28f  movzx   edi, ax
0x18002b292  or      edi, 80070000h
0x18002b298  jmp     loc_18002B3B6
0x18002b29d  cmp     [rsp+88h+arg_8], 3
0x18002b2a5  jz      short loc_18002B2F5
0x18002b2a7  mov     edi, 8000FFFFh
0x18002b2ac  jmp     loc_18002B3B6
0x18002b2b1  jle     loc_18002B3B6
0x18002b2b7  movzx   edi, ax
0x18002b2ba  or      edi, 80070000h
0x18002b2c0  jmp     loc_18002B3B6
0x18002b2c5  jle     loc_18002B3B6
0x18002b2cb  movzx   edi, ax
0x18002b2ce  or      edi, 80070000h
0x18002b2d4  jmp     loc_18002B3B6
0x18002b2d9  jle     loc_18002B3B6
0x18002b2df  movzx   edi, ax
0x18002b2e2  or      edi, 80070000h
0x18002b2e8  jmp     loc_18002B3B6
0x18002b2ed  mov     edi, r12d
0x18002b2f0  jmp     loc_18002B3B6
0x18002b2f5  mov     eax, [rsp+88h+arg_0]
0x18002b2fc  test    eax, eax
0x18002b2fe  jnz     short loc_18002B308
0x18002b300  mov     edi, r12d
0x18002b303  jmp     loc_18002B3B6
0x18002b308  mov     rdx, rax; uBytes
0x18002b30b  mov     ecx, 40h ; '@'; uFlags
0x18002b310  call    cs:__imp_LocalAlloc
0x18002b317  nop     dword ptr [rax+rax+00h]
0x18002b31c  mov     rsi, rax
0x18002b31f  mov     [rsp+88h+var_48], rax
0x18002b324  test    rax, rax
0x18002b327  jnz     short loc_18002B333
0x18002b329  mov     edi, 8007000Eh
0x18002b32e  jmp     loc_18002B3B6
0x18002b333  lea     rax, [rsp+88h+arg_0]
0x18002b33b  mov     [rsp+88h+pcbData], rax; pcbData
0x18002b340  mov     [rsp+88h+pvData], rsi; pvData
0x18002b345  lea     rax, [rsp+88h+arg_8]
0x18002b34d  mov     [rsp+88h+pdwType], rax; pdwType
0x18002b352  mov     r9d, 0FFFFh; dwFlags
0x18002b358  lea     r8, aLeapseconds; "LeapSeconds"
0x18002b35f  xor     edx, edx; lpSubKey
0x18002b361  mov     rcx, [rsp+88h+hkey]; hkey
0x18002b369  call    cs:__imp_RegGetValueW
0x18002b370  nop     dword ptr [rax+rax+00h]
0x18002b375  mov     edi, eax
0x18002b377  test    eax, eax
0x18002b379  jnz     loc_18002B2D9
0x18002b37f  cmp     [rsp+88h+arg_8], 3
0x18002b387  jnz     loc_18002B2A7
0x18002b38d  mov     [r15], rsi
0x18002b390  mov     ecx, [rsp+88h+arg_0]
0x18002b397  mov     rax, 0AAAAAAAAAAAAAAABh
0x18002b3a1  mul     rcx
0x18002b3a4  shr     rdx, 3
0x18002b3a8  mov     [r14], edx
0x18002b3ab  mov     rsi, r12
0x18002b3ae  mov     [rsp+88h+var_48], r12
0x18002b3b3  mov     edi, r12d
0x18002b3b6  test    rsi, rsi
0x18002b3b9  jnz     short loc_18002B3E5
0x18002b3bb  mov     rcx, [rsp+88h+hkey]; hKey
0x18002b3c3  test    rcx, rcx
0x18002b3c6  jz      short loc_18002B3D4
0x18002b3c8  call    cs:__imp_RegCloseKey
0x18002b3cf  nop     dword ptr [rax+rax+00h]
0x18002b3d4  mov     eax, edi
0x18002b3d6  add     rsp, 58h
0x18002b3da  pop     r15
0x18002b3dc  pop     r14
0x18002b3de  pop     r12
0x18002b3e0  pop     rdi
0x18002b3e1  pop     rsi
0x18002b3e2  pop     rbx
0x18002b3e3  retn
0x18002b3e5  mov     rcx, rsi; hMem
0x18002b3e8  call    cs:__imp_LocalFree
0x18002b3ef  nop     dword ptr [rax+rax+00h]
0x18002b3f4  jmp     short loc_18002B3BB
0x180067610  push    rbp
0x180067612  sub     rsp, 40h
0x180067616  mov     rbp, rdx
0x180067619  mov     rcx, [rbp+40h]; hMem
0x18006761d  test    rcx, rcx
0x180067620  jz      short loc_180067636
0x180067622  call    cs:__imp_LocalFree
0x180067629  nop     dword ptr [rax+rax+00h]
0x18006762e  mov     qword ptr [rbp+40h], 0
0x180067636  mov     rcx, [rbp+0A8h]; hKey
0x18006763d  test    rcx, rcx
0x180067640  jz      short loc_18006764F
0x180067642  call    cs:__imp_RegCloseKey
0x180067649  nop     dword ptr [rax+rax+00h]
0x18006764e  nop
0x18006764f  add     rsp, 40h
0x180067653  pop     rbp
0x180067654  retn
```
