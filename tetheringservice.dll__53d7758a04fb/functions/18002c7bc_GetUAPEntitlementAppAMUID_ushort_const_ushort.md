# GetUAPEntitlementAppAMUID(ushort const *,ushort * *)

- ea: `0x18002c7bc`
- end: `0x18002cb3b`
- name: `?GetUAPEntitlementAppAMUID@@YAJPEBGPEAPEAG@Z`
- size: `895`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000dfd8`
- `0x18002d868`

## callees

- `0x180002590`
- `0x180002960`
- `0x180003088`
- `0x18000380c`
- `0x1800094bc`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ea08`
- `0x18002c7bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c902`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c915`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c915`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c90d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cb08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c90d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cb08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c945`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c945`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c9bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ca74`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c9bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ca74`
- `MobileNetworking!GetPersistentRegPath` at `0x18002c8bb`
- `MobileNetworking!GetPersistentRegPath` at `0x18002c8bb`

## pseudocode

```c
__int64 __fastcall GetUAPEntitlementAppAMUID(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  int v5; // eax
  signed int v6; // ebx
  TetheringServiceTelemetry *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int PersistentRegPath; // eax
  LSTATUS v11; // eax
  LSTATUS ValueW; // eax
  unsigned __int64 v13; // rax
  unsigned __int16 *pvData; // rax
  LSTATUS v15; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v20[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  memset_0(v20, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  v19[0] = 260;
  v4 = 0;
  hKey = 0;
  v5 = StringCchPrintfW(v20, 0x104u, L"ICCIDSpecific\\%s\\CellUX", a1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    PersistentRegPath = GetPersistentRegPath(1, v20, v19, SubKey);
    v6 = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      v6 = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( v6 >= 0 )
    {
      hKey = 0;
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 >= 0 )
      {
        pcbData = 0;
        ValueW = RegGetValueW(hKey, 0, L"AppID", 2u, 0, 0, &pcbData);
        v6 = ValueW;
        if ( ValueW > 0 )
          v6 = (unsigned __int16)ValueW | 0x80070000;
        if ( v6 >= 0 )
        {
          v13 = 2 * ((unsigned __int64)pcbData >> 1);
          if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
            v13 = -1;
          pvData = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
          v4 = pvData;
          if ( pvData )
          {
            v15 = RegGetValueW(hKey, 0, L"AppID", 2u, 0, pvData, &pcbData);
            v6 = v15;
            if ( v15 > 0 )
              v6 = (unsigned __int16)v15 | 0x80070000;
            if ( v6 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v4);
              }
              *a2 = v4;
              v4 = 0;
              goto LABEL_44;
            }
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_44;
            }
            v8 = 51;
          }
          else
          {
            v6 = -2147024882;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_44;
            }
            v8 = 50;
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_44;
          }
          v8 = 49;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_44;
        }
        v8 = 48;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_44;
      }
      v8 = 47;
    }
    v9 = (unsigned int)v6;
    goto LABEL_8;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 46;
    v9 = (unsigned int)v5;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v9);
  }
LABEL_44:
  operator delete(v4);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids,
      (unsigned int)v6);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c7bc  mov     [rsp-8+arg_10], rbx
0x18002c7c1  mov     [rsp-8+arg_18], rsi
0x18002c7c6  push    rbp
0x18002c7c7  push    rdi
0x18002c7c8  push    r12
0x18002c7ca  push    r13
0x18002c7cc  push    r14
0x18002c7ce  lea     rbp, [rsp-390h]
0x18002c7d6  sub     rsp, 490h
0x18002c7dd  mov     rax, cs:__security_cookie
0x18002c7e4  xor     rax, rsp
0x18002c7e7  mov     [rbp+3B0h+var_30], rax
0x18002c7ee  mov     r14, rdx
0x18002c7f1  mov     rbx, rcx
0x18002c7f4  lea     r12, WPP_GLOBAL_Control
0x18002c7fb  lea     r13, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002c802  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c809  cmp     rcx, r12
0x18002c80c  jz      short loc_18002C825
0x18002c80e  test    byte ptr [rcx+1Ch], 8
0x18002c812  jz      short loc_18002C825
0x18002c814  mov     edx, 2Dh ; '-'
0x18002c819  mov     r8, r13
0x18002c81c  mov     rcx, [rcx+10h]
0x18002c820  call    WPP_SF_
0x18002c825  mov     edi, 208h
0x18002c82a  mov     r8d, edi; Size
0x18002c82d  xor     edx, edx; Val
0x18002c82f  lea     rcx, [rsp+4B0h+var_450]; void *
0x18002c834  call    memset_0
0x18002c839  mov     r8d, edi; Size
0x18002c83c  xor     edx, edx; Val
0x18002c83e  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18002c845  call    memset_0
0x18002c84a  mov     edx, 104h; unsigned __int64
0x18002c84f  mov     [rsp+4B0h+var_460], edx
0x18002c853  xor     esi, esi
0x18002c855  mov     [rsp+4B0h+hKey], rsi
0x18002c85a  mov     r9, rbx
0x18002c85d  lea     r8, aIccidspecificS; "ICCIDSpecific\\%s\\CellUX"
0x18002c864  lea     rcx, [rsp+4B0h+var_450]; unsigned __int16 *
0x18002c869  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c86e  mov     ebx, eax
0x18002c870  test    eax, eax
0x18002c872  jns     short loc_18002C8A5
0x18002c874  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c87b  cmp     rcx, r12
0x18002c87e  jz      loc_18002CAD0
0x18002c884  test    byte ptr [rcx+1Ch], 1
0x18002c888  jz      loc_18002CAD0
0x18002c88e  lea     edx, [rsi+2Eh]
0x18002c891  mov     r9d, eax
0x18002c894  mov     r8, r13
0x18002c897  mov     rcx, [rcx+10h]
0x18002c89b  call    WPP_SF_d
0x18002c8a0  jmp     loc_18002CAD0
0x18002c8a5  lea     r9, [rbp+3B0h+SubKey]
0x18002c8ac  lea     r8, [rsp+4B0h+var_460]
0x18002c8b1  lea     rdx, [rsp+4B0h+var_450]
0x18002c8b6  mov     ecx, 1
0x18002c8bb  call    cs:__imp_GetPersistentRegPath
0x18002c8c1  mov     ebx, eax
0x18002c8c3  test    eax, eax
0x18002c8c5  jle     short loc_18002C8D0
0x18002c8c7  movzx   ebx, ax
0x18002c8ca  or      ebx, 80070000h
0x18002c8d0  test    ebx, ebx
0x18002c8d2  jns     short loc_18002C8F8
0x18002c8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8db  cmp     rcx, r12
0x18002c8de  jz      loc_18002CAD0
0x18002c8e4  test    byte ptr [rcx+1Ch], 1
0x18002c8e8  jz      loc_18002CAD0
0x18002c8ee  mov     edx, 2Fh ; '/'
0x18002c8f3  mov     r9d, ebx
0x18002c8f6  jmp     short loc_18002C894
0x18002c8f8  mov     rdi, [rsp+4B0h+hKey]
0x18002c8fd  test    rdi, rdi
0x18002c900  jz      short loc_18002C91B
0x18002c902  call    cs:__imp_GetLastError
0x18002c908  mov     ebx, eax
0x18002c90a  mov     rcx, rdi; hKey
0x18002c90d  call    cs:__imp_RegCloseKey
0x18002c913  mov     ecx, ebx; dwErrCode
0x18002c915  call    cs:__imp_SetLastError
0x18002c91b  mov     [rsp+4B0h+hKey], 0
0x18002c924  lea     rax, [rsp+4B0h+hKey]
0x18002c929  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18002c92e  mov     r9d, 20019h; samDesired
0x18002c934  xor     r8d, r8d; ulOptions
0x18002c937  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18002c93e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c945  call    cs:__imp_RegOpenKeyExW
0x18002c94b  mov     ebx, eax
0x18002c94d  mov     edi, 80070000h
0x18002c952  test    eax, eax
0x18002c954  jle     short loc_18002C95B
0x18002c956  movzx   ebx, ax
0x18002c959  or      ebx, edi
0x18002c95b  test    ebx, ebx
0x18002c95d  jns     short loc_18002C983
0x18002c95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c966  cmp     rcx, r12
0x18002c969  jz      loc_18002CAD0
0x18002c96f  test    byte ptr [rcx+1Ch], 1
0x18002c973  jz      loc_18002CAD0
0x18002c979  mov     edx, 30h ; '0'
0x18002c97e  jmp     loc_18002C8F3
0x18002c983  mov     [rsp+4B0h+var_470], 0
0x18002c98b  lea     rax, [rsp+4B0h+var_470]
0x18002c990  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18002c995  mov     [rsp+4B0h+pvData], 0; pvData
0x18002c99e  mov     [rsp+4B0h+phkResult], 0; pdwType
0x18002c9a7  mov     r9d, 2; dwFlags
0x18002c9ad  lea     r8, aAppid; "AppID"
0x18002c9b4  xor     edx, edx; lpSubKey
0x18002c9b6  mov     rcx, [rsp+4B0h+hKey]; hkey
0x18002c9bb  call    cs:__imp_RegGetValueW
0x18002c9c1  mov     ebx, eax
0x18002c9c3  test    eax, eax
0x18002c9c5  jle     short loc_18002C9CC
0x18002c9c7  movzx   ebx, ax
0x18002c9ca  or      ebx, edi
0x18002c9cc  test    ebx, ebx
0x18002c9ce  jns     short loc_18002C9F4
0x18002c9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9d7  cmp     rcx, r12
0x18002c9da  jz      loc_18002CAD0
0x18002c9e0  test    byte ptr [rcx+1Ch], 1
0x18002c9e4  jz      loc_18002CAD0
0x18002c9ea  mov     edx, 31h ; '1'
0x18002c9ef  jmp     loc_18002C8F3
0x18002c9f4  mov     ecx, [rsp+4B0h+var_470]
0x18002c9f8  shr     rcx, 1
0x18002c9fb  mov     ebx, 2
0x18002ca00  mov     eax, ebx
0x18002ca02  mul     rcx
0x18002ca05  lea     rcx, [rbx-3]
0x18002ca09  cmovb   rax, rcx
0x18002ca0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ca14  mov     rcx, rax; unsigned __int64
0x18002ca17  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ca1c  mov     rsi, rax
0x18002ca1f  test    rax, rax
0x18002ca22  jnz     short loc_18002CA4B
0x18002ca24  mov     ebx, 8007000Eh
0x18002ca29  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca30  cmp     rcx, r12
0x18002ca33  jz      loc_18002CAD0
0x18002ca39  test    byte ptr [rcx+1Ch], 1
0x18002ca3d  jz      loc_18002CAD0
0x18002ca43  lea     edx, [rax+32h]
0x18002ca46  jmp     loc_18002C8F3
0x18002ca4b  lea     rax, [rsp+4B0h+var_470]
0x18002ca50  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18002ca55  mov     [rsp+4B0h+pvData], rsi; pvData
0x18002ca5a  mov     [rsp+4B0h+phkResult], 0; pdwType
0x18002ca63  mov     r9d, ebx; dwFlags
0x18002ca66  lea     r8, aAppid; "AppID"
0x18002ca6d  xor     edx, edx; lpSubKey
0x18002ca6f  mov     rcx, [rsp+4B0h+hKey]; hkey
0x18002ca74  call    cs:__imp_RegGetValueW
0x18002ca7a  mov     ebx, eax
0x18002ca7c  test    eax, eax
0x18002ca7e  jle     short loc_18002CA85
0x18002ca80  movzx   ebx, ax
0x18002ca83  or      ebx, edi
0x18002ca85  test    ebx, ebx
0x18002ca87  jns     short loc_18002CAA5
0x18002ca89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca90  cmp     rcx, r12
0x18002ca93  jz      short loc_18002CAD0
0x18002ca95  test    byte ptr [rcx+1Ch], 1
0x18002ca99  jz      short loc_18002CAD0
0x18002ca9b  mov     edx, 33h ; '3'
0x18002caa0  jmp     loc_18002C8F3
0x18002caa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002caac  cmp     rcx, r12
0x18002caaf  jz      short loc_18002CACB
0x18002cab1  test    byte ptr [rcx+1Ch], 4
0x18002cab5  jz      short loc_18002CACB
0x18002cab7  mov     edx, 34h ; '4'
0x18002cabc  mov     r9, rsi
0x18002cabf  mov     r8, r13
0x18002cac2  mov     rcx, [rcx+10h]
0x18002cac6  call    WPP_SF_S
0x18002cacb  mov     [r14], rsi
0x18002cace  xor     esi, esi
0x18002cad0  mov     rcx, rsi; Block
0x18002cad3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cad8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cadf  cmp     rcx, r12
0x18002cae2  jz      short loc_18002CAFE
0x18002cae4  test    byte ptr [rcx+1Ch], 8
0x18002cae8  jz      short loc_18002CAFE
0x18002caea  mov     edx, 35h ; '5'
0x18002caef  mov     r9d, ebx
0x18002caf2  mov     r8, r13
0x18002caf5  mov     rcx, [rcx+10h]
0x18002caf9  call    WPP_SF_d
0x18002cafe  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18002cb03  test    rcx, rcx
0x18002cb06  jz      short loc_18002CB0E
0x18002cb08  call    cs:__imp_RegCloseKey
0x18002cb0e  mov     eax, ebx
0x18002cb10  mov     rcx, [rbp+3B0h+var_30]
0x18002cb17  xor     rcx, rsp; StackCookie
0x18002cb1a  call    __security_check_cookie
0x18002cb1f  lea     r11, [rsp+4B0h+var_20]
0x18002cb27  mov     rbx, [r11+40h]
0x18002cb2b  mov     rsi, [r11+48h]
0x18002cb2f  mov     rsp, r11
0x18002cb32  pop     r14
0x18002cb34  pop     r13
0x18002cb36  pop     r12
0x18002cb38  pop     rdi
0x18002cb39  pop     rbp
0x18002cb3a  retn
```
