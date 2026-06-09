# RegistryPropertyBag::EncryptedDwordProperty::Write(HKEY__ *)

- ea: `0x18002ee44`
- end: `0x18002eff0`
- name: `?Write@EncryptedDwordProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `428`
- prototype: `int(RegistryPropertyBag::EncryptedDwordProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002e1e0`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002ee44`
- `0x18002f144`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ef79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ef79`
- `ntdll!NtQueryKey` at `0x18002eef8`
- `ntdll!NtQueryKey` at `0x18002eef8`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::EncryptedDwordProperty::Write(
        RegistryPropertyBag::EncryptedDwordProperty *this,
        HKEY a2)
{
  TetheringServiceTelemetry *v4; // rcx
  unsigned __int64 cbData; // rsi
  unsigned __int8 *v6; // rdi
  int v7; // eax
  RegistryPropertyBag::EncryptedDwordProperty *v8; // rcx
  int v9; // eax
  int v10; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD KeyInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v16[540]; // [rsp+54h] [rbp-ACh] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 9) )
  {
    cbData = 0;
    v6 = 0;
    v14 = 0;
    v13 = 0;
    ResultLength = 0;
    KeyInformation = 0;
    memset_0(v16, 0, 0x210u);
    v7 = NtQueryKey(a2, KeyNameInformation, &KeyInformation, 0x214u, &ResultLength) | 0x10000000;
    *((_DWORD *)this + 5) = v7;
    if ( v7 >= 0 )
    {
      if ( KeyInformation > 0x20A )
        goto LABEL_9;
      v9 = RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(v8, (BYTE *)this + 12, KeyInformation, v16, &v14, &v13);
      v6 = v13;
      *((_DWORD *)this + 5) = v9;
      if ( v9 >= 0 )
      {
        cbData = v14;
LABEL_9:
        if ( cbData <= 0x1000 )
        {
          v10 = RegSetValueExW(a2, *((LPCWSTR *)this + 3), 0, 3u, v6, cbData);
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          *((_DWORD *)this + 5) = v10;
        }
        else
        {
          *((_DWORD *)this + 5) = -2147024883;
        }
      }
    }
    if ( v6 )
      LocalFree(v6);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 46, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids, *((unsigned int *)this + 5));
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x18002ee44  mov     [rsp-8+arg_10], rbx
0x18002ee49  push    rbp
0x18002ee4a  push    rsi
0x18002ee4b  push    rdi
0x18002ee4c  push    r12
0x18002ee4e  push    r14
0x18002ee50  lea     rbp, [rsp-180h]
0x18002ee58  sub     rsp, 280h
0x18002ee5f  mov     rax, cs:__security_cookie
0x18002ee66  xor     rax, rsp
0x18002ee69  mov     [rbp+1A0h+var_30], rax
0x18002ee70  mov     r14, rdx
0x18002ee73  mov     rbx, rcx
0x18002ee76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee7d  lea     r12, WPP_GLOBAL_Control
0x18002ee84  cmp     rcx, r12
0x18002ee87  jz      short loc_18002EEAB
0x18002ee89  test    byte ptr [rcx+1Ch], 10h
0x18002ee8d  jz      short loc_18002EEAB
0x18002ee8f  mov     rcx, [rcx+10h]
0x18002ee93  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002ee9a  mov     edx, 2Dh ; '-'
0x18002ee9f  call    WPP_SF_
0x18002eea4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eeab  cmp     byte ptr [rbx+9], 0
0x18002eeaf  jz      loc_18002EFA3
0x18002eeb5  xor     esi, esi
0x18002eeb7  lea     rcx, [rsp+2A0h+var_24C]; void *
0x18002eebc  xor     edi, edi
0x18002eebe  mov     [rsp+2A0h+var_260], rsi
0x18002eec3  xor     edx, edx; Val
0x18002eec5  mov     [rsp+2A0h+var_268], rdi
0x18002eeca  mov     r8d, 210h; Size
0x18002eed0  mov     [rsp+2A0h+var_270], esi
0x18002eed4  mov     [rsp+2A0h+KeyInformation], esi
0x18002eed8  call    memset_0
0x18002eedd  lea     rax, [rsp+2A0h+var_270]
0x18002eee2  mov     r9d, 214h; Length
0x18002eee8  lea     r8, [rsp+2A0h+KeyInformation]; KeyInformation
0x18002eeed  mov     [rsp+2A0h+ResultLength], rax; ResultLength
0x18002eef2  lea     edx, [rsi+3]; KeyInformationClass
0x18002eef5  mov     rcx, r14; KeyHandle
0x18002eef8  call    cs:__imp_NtQueryKey
0x18002eefe  or      eax, 10000000h
0x18002ef03  mov     [rbx+14h], eax
0x18002ef06  jl      loc_18002EF8E
0x18002ef0c  cmp     [rsp+2A0h+KeyInformation], 20Ah
0x18002ef14  ja      short loc_18002EF4E
0x18002ef16  mov     r8d, [rsp+2A0h+KeyInformation]; unsigned __int64
0x18002ef1b  lea     rax, [rsp+2A0h+var_268]
0x18002ef20  mov     qword ptr [rsp+2A0h+cbData], rax; unsigned __int8 **
0x18002ef25  lea     rdx, [rbx+0Ch]; unsigned int *
0x18002ef29  lea     rax, [rsp+2A0h+var_260]
0x18002ef2e  lea     r9, [rsp+2A0h+var_24C]; unsigned __int8 *
0x18002ef33  mov     [rsp+2A0h+ResultLength], rax; unsigned __int64 *
0x18002ef38  call    ?_Encrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJAEBK_KPEAEPEA_KPEAPEAE@Z; RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(ulong const &,unsigned __int64,uchar *,unsigned __int64 *,uchar * *)
0x18002ef3d  mov     rdi, [rsp+2A0h+var_268]
0x18002ef42  mov     [rbx+14h], eax
0x18002ef45  test    eax, eax
0x18002ef47  js      short loc_18002EF8E
0x18002ef49  mov     rsi, [rsp+2A0h+var_260]
0x18002ef4e  cmp     rsi, 1000h
0x18002ef55  jbe     short loc_18002EF60
0x18002ef57  mov     dword ptr [rbx+14h], 8007000Dh
0x18002ef5e  jmp     short loc_18002EF8E
0x18002ef60  mov     rdx, [rbx+18h]; lpValueName
0x18002ef64  mov     r9d, 3; dwType
0x18002ef6a  mov     [rsp+2A0h+cbData], esi; cbData
0x18002ef6e  xor     r8d, r8d; Reserved
0x18002ef71  mov     rcx, r14; hKey
0x18002ef74  mov     [rsp+2A0h+ResultLength], rdi; lpData
0x18002ef79  call    cs:__imp_RegSetValueExW
0x18002ef7f  test    eax, eax
0x18002ef81  jle     short loc_18002EF8B
0x18002ef83  movzx   eax, ax
0x18002ef86  or      eax, 80070000h
0x18002ef8b  mov     [rbx+14h], eax
0x18002ef8e  test    rdi, rdi
0x18002ef91  jz      short loc_18002EF9C
0x18002ef93  mov     rcx, rdi; hMem
0x18002ef96  call    cs:__imp_LocalFree
0x18002ef9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efa3  cmp     rcx, r12
0x18002efa6  jz      short loc_18002EFC7
0x18002efa8  test    byte ptr [rcx+1Ch], 10h
0x18002efac  jz      short loc_18002EFC7
0x18002efae  mov     r9d, [rbx+14h]
0x18002efb2  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18002efb9  mov     rcx, [rcx+10h]
0x18002efbd  mov     edx, 2Eh ; '.'
0x18002efc2  call    WPP_SF_d
0x18002efc7  mov     eax, [rbx+14h]
0x18002efca  mov     rcx, [rbp+1A0h+var_30]
0x18002efd1  xor     rcx, rsp; StackCookie
0x18002efd4  call    __security_check_cookie
0x18002efd9  mov     rbx, [rsp+2A0h+arg_10]
0x18002efe1  add     rsp, 280h
0x18002efe8  pop     r14
0x18002efea  pop     r12
0x18002efec  pop     rdi
0x18002efed  pop     rsi
0x18002efee  pop     rbp
0x18002efef  retn
```
