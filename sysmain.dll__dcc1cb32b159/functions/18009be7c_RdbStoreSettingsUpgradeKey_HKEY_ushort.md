# RdbStoreSettingsUpgradeKey(HKEY__ *,ushort *)

- ea: `0x18009be7c`
- end: `0x18009c147`
- name: `?RdbStoreSettingsUpgradeKey@@YAKPEAUHKEY__@@PEAG@Z`
- size: `715`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009bd90`

## callees

- `0x1800382e0`
- `0x18009bc08`
- `0x18009be7c`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c11c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c0be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009c11c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bf01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009bf01`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18009c0d2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18009c0d2`

## string_xrefs

- `0x18009c005`: `CacheSizeInMB`
- `0x18009bfb3`: `ReadSpeedKBs`
- `0x18009bfdc`: `WriteSpeedKBs`

## pseudocode

```c
__int64 __fastcall RdbStoreSettingsUpgradeKey(HKEY hKey, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  unsigned int Value; // eax
  int v6; // esi
  __int64 v7; // rax
  HKEY hKeya; // [rsp+30h] [rbp-49h] BYREF
  int v10; // [rsp+38h] [rbp-41h] BYREF
  __int64 v11; // [rsp+3Ch] [rbp-3Dh] BYREF
  int v12; // [rsp+44h] [rbp-35h] BYREF
  __int64 v13; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v14[40]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v15[36]; // [rsp+78h] [rbp-1h] BYREF

  v10 = 0;
  hKeya = 0;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  memset(v14, 0, sizeof(v14));
  memset(v15, 0, sizeof(v15));
  v4 = RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, &hKeya);
  if ( !v4 )
  {
    Value = PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"Attributes", 3, 36, (__int64)v15);
    v4 = Value;
    if ( Value )
    {
      v6 = 0;
      if ( Value != 2 )
      {
        v4 = 0;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v15[0] == 3 )
        goto LABEL_29;
      v6 = 1;
    }
    v4 = PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"DeviceStatus", 4, 4, (__int64)&v10);
    if ( v4 )
      goto LABEL_29;
    if ( v10 == 2 )
    {
      if ( v6 )
      {
        v11 = *(_QWORD *)&v15[12];
      }
      else
      {
        v4 = PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"ReadSpeedKBs", 4, 4, (__int64)&v11);
        if ( v4 )
          goto LABEL_29;
        v4 = PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"WriteSpeedKBs", 4, 4, (__int64)&v11 + 4);
        if ( v4 )
          goto LABEL_29;
      }
      v4 = PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"CacheSizeInMB", 4, 4, (__int64)&v12);
      if ( v4 )
        goto LABEL_29;
    }
    else
    {
      v11 = 0;
      v12 = 0;
      if ( (unsigned int)(v10 - 3) <= 1 || v10 == 14 )
        v10 = 5;
    }
    if ( (unsigned int)PfsRegQueryValue((_DWORD)hKeya, (unsigned int)L"LastTestedTime", 11, 8, (__int64)&v13) )
    {
      v7 = 0;
      v13 = 0;
    }
    else
    {
      v7 = v13;
    }
    *(_QWORD *)&v14[8] = v7;
    *(_DWORD *)v14 = (unsigned __int16)v10;
    *(_QWORD *)&v14[16] = v11;
    *(_DWORD *)&v14[4] = v12;
    *(_OWORD *)&v14[24] = 0;
    if ( v6 )
    {
      *(_WORD *)&v14[2] = v15[1];
      *(_OWORD *)&v14[24] = *(_OWORD *)&v15[20];
    }
    RegCloseKey(hKeya);
    hKeya = 0;
    RegDeleteKeyW(hKey, a2);
    if ( *a2 == 35 && a2[1] == 63 && a2[2] == 63 && a2[3] == 35 )
    {
      *a2 = 95;
      a2[3] = 95;
    }
    RdbStoreSettingsRegWrite(hKey, a2, (struct _RDB_REGISTRY_DATA *)v14);
    v4 = 28;
  }
LABEL_29:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v4;
}

```

## disassembly

```asm
0x18009be7c  mov     [rsp-8+arg_10], rbx
0x18009be81  push    rbp
0x18009be82  push    rsi
0x18009be83  push    rdi
0x18009be84  push    r12
0x18009be86  push    r14
0x18009be88  lea     rbp, [rsp-37h]
0x18009be8d  sub     rsp, 0B0h
0x18009be94  mov     rax, cs:__security_cookie
0x18009be9b  xor     rax, rsp
0x18009be9e  mov     [rbp+57h+var_30], rax
0x18009bea2  xor     eax, eax
0x18009bea4  mov     [rbp+57h+var_98], 0
0x18009beab  xorps   xmm0, xmm0
0x18009beae  mov     [rbp+57h+var_60], rax
0x18009beb2  xorps   xmm1, xmm1
0x18009beb5  mov     [rbp+57h+var_38], eax
0x18009beb8  mov     [rbp+57h+hKey], rax
0x18009bebc  mov     r9d, 0F003Fh; samDesired
0x18009bec2  lea     rax, [rbp+57h+hKey]
0x18009bec6  mov     [rbp+57h+var_8C], 0
0x18009becd  xor     r8d, r8d; ulOptions
0x18009bed0  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18009bed5  mov     rdi, rdx
0x18009bed8  mov     dword ptr [rbp+57h+var_94], 0
0x18009bedf  mov     r14, rcx
0x18009bee2  mov     dword ptr [rbp+57h+var_94+4], 0
0x18009bee9  mov     [rbp+57h+var_88], 0
0x18009bef1  movups  [rbp+57h+var_80], xmm0
0x18009bef5  movups  [rbp+57h+var_70], xmm0
0x18009bef9  movups  [rbp+57h+var_58], xmm1
0x18009befd  movups  [rbp+57h+var_48], xmm1
0x18009bf01  call    cs:__imp_RegOpenKeyExW
0x18009bf07  mov     ebx, eax
0x18009bf09  test    eax, eax
0x18009bf0b  jnz     loc_18009C113
0x18009bf11  mov     rcx, [rbp+57h+hKey]
0x18009bf15  lea     rax, [rbp+57h+var_58]
0x18009bf19  lea     r9d, [rbx+24h]
0x18009bf1d  mov     [rsp+0D0h+phkResult], rax
0x18009bf22  lea     r8d, [rbx+3]
0x18009bf26  lea     rdx, aAttributes; "Attributes"
0x18009bf2d  call    PfsRegQueryValue
0x18009bf32  mov     ebx, eax
0x18009bf34  test    eax, eax
0x18009bf36  jnz     short loc_18009BF92
0x18009bf38  cmp     byte ptr [rbp+57h+var_58], 3
0x18009bf3c  jz      loc_18009C113
0x18009bf42  lea     esi, [rax+1]
0x18009bf45  mov     rcx, [rbp+57h+hKey]
0x18009bf49  lea     rax, [rbp+57h+var_98]
0x18009bf4d  mov     r12d, 4
0x18009bf53  mov     [rsp+0D0h+phkResult], rax
0x18009bf58  mov     r9d, r12d
0x18009bf5b  lea     rdx, aDevicestatus; "DeviceStatus"
0x18009bf62  mov     r8d, r12d
0x18009bf65  call    PfsRegQueryValue
0x18009bf6a  mov     ebx, eax
0x18009bf6c  test    eax, eax
0x18009bf6e  jnz     loc_18009C113
0x18009bf74  mov     ecx, [rbp+57h+var_98]
0x18009bf77  cmp     ecx, 2
0x18009bf7a  jnz     loc_18009C01D
0x18009bf80  test    esi, esi
0x18009bf82  jz      short loc_18009BFA0
0x18009bf84  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x18009bf87  mov     dword ptr [rbp+57h+var_94], eax
0x18009bf8a  mov     eax, dword ptr [rbp+57h+var_48]
0x18009bf8d  mov     dword ptr [rbp+57h+var_94+4], eax
0x18009bf90  jmp     short loc_18009BFF2
0x18009bf92  xor     esi, esi
0x18009bf94  cmp     eax, 2
0x18009bf97  jz      short loc_18009BF45
0x18009bf99  xor     ebx, ebx
0x18009bf9b  jmp     loc_18009C113
0x18009bfa0  mov     rcx, [rbp+57h+hKey]
0x18009bfa4  lea     rax, [rbp+57h+var_94]
0x18009bfa8  mov     r9d, r12d
0x18009bfab  mov     [rsp+0D0h+phkResult], rax
0x18009bfb0  mov     r8d, r12d
0x18009bfb3  lea     rdx, aReadspeedkbs; "ReadSpeedKBs"
0x18009bfba  call    PfsRegQueryValue
0x18009bfbf  mov     ebx, eax
0x18009bfc1  test    eax, eax
0x18009bfc3  jnz     loc_18009C113
0x18009bfc9  mov     rcx, [rbp+57h+hKey]
0x18009bfcd  lea     rax, [rbp+57h+var_94+4]
0x18009bfd1  mov     r9d, r12d
0x18009bfd4  mov     [rsp+0D0h+phkResult], rax
0x18009bfd9  mov     r8d, r12d
0x18009bfdc  lea     rdx, aWritespeedkbs; "WriteSpeedKBs"
0x18009bfe3  call    PfsRegQueryValue
0x18009bfe8  mov     ebx, eax
0x18009bfea  test    eax, eax
0x18009bfec  jnz     loc_18009C113
0x18009bff2  mov     rcx, [rbp+57h+hKey]
0x18009bff6  lea     rax, [rbp+57h+var_8C]
0x18009bffa  mov     r9d, r12d
0x18009bffd  mov     [rsp+0D0h+phkResult], rax
0x18009c002  mov     r8d, r12d
0x18009c005  lea     rdx, aCachesizeinmb; "CacheSizeInMB"
0x18009c00c  call    PfsRegQueryValue
0x18009c011  mov     ebx, eax
0x18009c013  test    eax, eax
0x18009c015  jnz     loc_18009C113
0x18009c01b  jmp     short loc_18009C046
0x18009c01d  lea     eax, [rcx-3]
0x18009c020  mov     dword ptr [rbp+57h+var_94], 0
0x18009c027  mov     dword ptr [rbp+57h+var_94+4], 0
0x18009c02e  mov     [rbp+57h+var_8C], 0
0x18009c035  cmp     eax, 1
0x18009c038  jbe     short loc_18009C03F
0x18009c03a  cmp     ecx, 0Eh
0x18009c03d  jnz     short loc_18009C046
0x18009c03f  mov     [rbp+57h+var_98], 5
0x18009c046  mov     rcx, [rbp+57h+hKey]
0x18009c04a  lea     rax, [rbp+57h+var_88]
0x18009c04e  mov     r9d, 8
0x18009c054  mov     [rsp+0D0h+phkResult], rax
0x18009c059  lea     rdx, aLasttestedtime; "LastTestedTime"
0x18009c060  lea     r8d, [r9+3]
0x18009c064  call    PfsRegQueryValue
0x18009c069  test    eax, eax
0x18009c06b  jz      short loc_18009C075
0x18009c06d  xor     eax, eax
0x18009c06f  mov     [rbp+57h+var_88], rax
0x18009c073  jmp     short loc_18009C079
0x18009c075  mov     rax, [rbp+57h+var_88]
0x18009c079  xor     ecx, ecx
0x18009c07b  mov     qword ptr [rbp+57h+var_80+8], rax
0x18009c07f  mov     eax, dword ptr [rbp+57h+var_94]
0x18009c082  xorps   xmm0, xmm0
0x18009c085  mov     word ptr [rbp+57h+var_80+2], cx
0x18009c089  movzx   ecx, word ptr [rbp+57h+var_98]
0x18009c08d  mov     word ptr [rbp+57h+var_80], cx
0x18009c091  mov     ecx, [rbp+57h+var_8C]
0x18009c094  mov     dword ptr [rbp+57h+var_70], eax
0x18009c097  mov     eax, dword ptr [rbp+57h+var_94+4]
0x18009c09a  mov     dword ptr [rbp+57h+var_80+4], ecx
0x18009c09d  mov     dword ptr [rbp+57h+var_70+4], eax
0x18009c0a0  movdqu  [rbp+57h+var_70+8], xmm0
0x18009c0a5  test    esi, esi
0x18009c0a7  jz      short loc_18009C0BA
0x18009c0a9  movups  xmm0, [rbp+57h+var_48+4]
0x18009c0ad  movzx   eax, byte ptr [rbp+57h+var_58+1]
0x18009c0b1  mov     word ptr [rbp+57h+var_80+2], ax
0x18009c0b5  movdqu  [rbp+57h+var_70+8], xmm0
0x18009c0ba  mov     rcx, [rbp+57h+hKey]; hKey
0x18009c0be  call    cs:__imp_RegCloseKey
0x18009c0c4  mov     rdx, rdi; lpSubKey
0x18009c0c7  mov     [rbp+57h+hKey], 0
0x18009c0cf  mov     rcx, r14; hKey
0x18009c0d2  call    cs:__imp_RegDeleteKeyW
0x18009c0d8  cmp     word ptr [rdi], 23h ; '#'
0x18009c0dc  jnz     short loc_18009C0FF
0x18009c0de  cmp     word ptr [rdi+2], 3Fh ; '?'
0x18009c0e3  jnz     short loc_18009C0FF
0x18009c0e5  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18009c0ea  jnz     short loc_18009C0FF
0x18009c0ec  cmp     word ptr [rdi+6], 23h ; '#'
0x18009c0f1  jnz     short loc_18009C0FF
0x18009c0f3  mov     eax, 5Fh ; '_'
0x18009c0f8  mov     [rdi], ax
0x18009c0fb  mov     [rdi+6], ax
0x18009c0ff  lea     r8, [rbp+57h+var_80]; struct _RDB_REGISTRY_DATA *
0x18009c103  mov     rdx, rdi; unsigned __int16 *
0x18009c106  mov     rcx, r14; hKey
0x18009c109  call    ?RdbStoreSettingsRegWrite@@YAKPEAUHKEY__@@PEAGPEAU_RDB_REGISTRY_DATA@@K@Z; RdbStoreSettingsRegWrite(HKEY__ *,ushort *,_RDB_REGISTRY_DATA *,ulong)
0x18009c10e  mov     ebx, 1Ch
0x18009c113  mov     rcx, [rbp+57h+hKey]; hKey
0x18009c117  test    rcx, rcx
0x18009c11a  jz      short loc_18009C122
0x18009c11c  call    cs:__imp_RegCloseKey
0x18009c122  mov     eax, ebx
0x18009c124  mov     rcx, [rbp+57h+var_30]
0x18009c128  xor     rcx, rsp; StackCookie
0x18009c12b  call    __security_check_cookie
0x18009c130  mov     rbx, [rsp+0D0h+arg_10]
0x18009c138  add     rsp, 0B0h
0x18009c13f  pop     r14
0x18009c141  pop     r12
0x18009c143  pop     rdi
0x18009c144  pop     rsi
0x18009c145  pop     rbp
0x18009c146  retn
```
