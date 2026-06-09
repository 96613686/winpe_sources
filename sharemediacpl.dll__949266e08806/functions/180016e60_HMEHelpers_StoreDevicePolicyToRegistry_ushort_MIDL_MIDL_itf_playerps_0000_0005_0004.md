# HMEHelpers::StoreDevicePolicyToRegistry(ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x180016e60`
- end: `0x18001714f`
- name: `?StoreDevicePolicyToRegistry@HMEHelpers@@YAJPEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(HMEHelpers *__hidden this, unsigned __int16 *, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005e74`

## callees

- `0x180001954`
- `0x180016728`
- `0x18001699c`
- `0x180016e60`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x18001710e`
- `KERNEL32!RegCloseKey` at `0x180017118`
- `KERNEL32!RegCloseKey` at `0x18001710e`
- `KERNEL32!RegCloseKey` at `0x180017118`
- `KERNEL32!RegDeleteKeyExW` at `0x180016ee3`
- `KERNEL32!RegDeleteKeyExW` at `0x180016ee3`
- `KERNEL32!RegCreateKeyExW` at `0x180016f2e`
- `KERNEL32!RegCreateKeyExW` at `0x180016f2e`
- `KERNEL32!RegSetValueExW` at `0x180016f7c`
- `KERNEL32!RegSetValueExW` at `0x180016fc4`
- `KERNEL32!RegSetValueExW` at `0x180017001`
- `KERNEL32!RegSetValueExW` at `0x180017049`
- `KERNEL32!RegSetValueExW` at `0x180017091`
- `KERNEL32!RegSetValueExW` at `0x1800170ef`
- `KERNEL32!RegSetValueExW` at `0x180016f7c`
- `KERNEL32!RegSetValueExW` at `0x180016fc4`
- `KERNEL32!RegSetValueExW` at `0x180017001`
- `KERNEL32!RegSetValueExW` at `0x180017049`
- `KERNEL32!RegSetValueExW` at `0x180017091`
- `KERNEL32!RegSetValueExW` at `0x1800170ef`
- `KERNEL32!RegOpenKeyExW` at `0x180016eab`
- `KERNEL32!RegOpenKeyExW` at `0x180016eab`

## string_xrefs

- `0x180016f50`: `AccessPrivateContent`

## pseudocode

```c
__int64 __fastcall HMEHelpers::StoreDevicePolicyToRegistry(
        WCHAR *this,
        unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a3)
{
  signed int v5; // ebx
  BYTE *v6; // rsi
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  struct __MIDL___MIDL_itf_playerps_0000_0005_0001 **v15; // r9
  HMEHelpers *v16; // rcx
  int v17; // eax
  LSTATUS v18; // eax
  const unsigned __int16 *v19; // rdx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-8h] BYREF
  BOOL Data; // [rsp+A0h] [rbp+40h] BYREF
  HKEY v24; // [rsp+A8h] [rbp+48h] BYREF

  v5 = 0;
  v6 = 0;
  hKey = 0;
  lpData = 0;
  v7 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME", 0, 0x2011Fu, &hKey);
  if ( v7 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    else
      v5 = v7;
  }
  else
  {
    if ( *(_DWORD *)a2 )
    {
      v8 = RegDeleteKeyExW(hKey, this, 0x100u, 0);
      if ( v8 )
      {
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        else
          v5 = v8;
      }
    }
    else
    {
      v24 = 0;
      v9 = RegCreateKeyExW(hKey, this, 0, 0, 0, 0xF003Fu, 0, &v24, 0);
      if ( v9 )
      {
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        else
          v5 = v9;
      }
      if ( v5 >= 0 )
      {
        Data = *((_DWORD *)a2 + 1) != 0;
        v10 = RegSetValueExW(v24, L"AccessPrivateContent", 0, 4u, (const BYTE *)&Data, 4u);
        if ( v10 )
        {
          if ( v10 > 0 )
            v5 = (unsigned __int16)v10 | 0x80070000;
          else
            v5 = v10;
        }
        else
        {
          Data = *((_DWORD *)a2 + 4) != 0;
          v11 = RegSetValueExW(v24, L"ZeroStars", 0, 4u, (const BYTE *)&Data, 4u);
          if ( v11 )
          {
            if ( v11 > 0 )
              v5 = (unsigned __int16)v11 | 0x80070000;
            else
              v5 = v11;
          }
          else
          {
            v12 = RegSetValueExW(v24, L"MinStars", 0, 4u, (const BYTE *)a2 + 12, 4u);
            if ( v12 )
            {
              if ( v12 > 0 )
                v5 = (unsigned __int16)v12 | 0x80070000;
              else
                v5 = v12;
            }
            else
            {
              Data = *((_DWORD *)a2 + 2) != 0;
              v13 = RegSetValueExW(v24, L"AllStars", 0, 4u, (const BYTE *)&Data, 4u);
              if ( v13 )
              {
                if ( v13 > 0 )
                  v5 = (unsigned __int16)v13 | 0x80070000;
                else
                  v5 = v13;
              }
              else
              {
                Data = *((_DWORD *)a2 + 5) != 0;
                v14 = RegSetValueExW(v24, L"AllParentalRatings", 0, 4u, (const BYTE *)&Data, 4u);
                if ( v14 )
                {
                  if ( v14 > 0 )
                    v5 = (unsigned __int16)v14 | 0x80070000;
                  else
                    v5 = v14;
                }
                else
                {
                  v16 = (HMEHelpers *)*((unsigned int *)a2 + 6);
                  if ( (_DWORD)v16 )
                  {
                    v17 = HMEHelpers::ConvertParentalRating(
                            v16,
                            *((_QWORD *)a2 + 4),
                            (const struct __MIDL___MIDL_itf_playerps_0000_0005_0003 *)&lpData,
                            v15);
                    v6 = lpData;
                    v5 = v17;
                    if ( v17 >= 0 )
                    {
                      v18 = RegSetValueExW(v24, L"ParentalRatingData", 0, 3u, lpData, 12 * *((_DWORD *)a2 + 6));
                      if ( v18 )
                      {
                        if ( v18 > 0 )
                          v5 = (unsigned __int16)v18 | 0x80070000;
                        else
                          v5 = v18;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( v24 )
        RegCloseKey(v24);
    }
    RegCloseKey(hKey);
    if ( v5 >= 0 )
      v5 = HMEHelpers::EnableServiceAccessForKey((HMEHelpers *)this, v19);
  }
  operator delete(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016e60  mov     [rsp-28h+arg_0], rbx
0x180016e65  mov     [rsp-28h+arg_8], rsi
0x180016e6a  push    rbp
0x180016e6b  push    rdi
0x180016e6c  push    r12
0x180016e6e  push    r13
0x180016e70  push    r14
0x180016e72  mov     rbp, rsp
0x180016e75  sub     rsp, 60h
0x180016e79  mov     rdi, rdx
0x180016e7c  lea     rax, [rbp+hKey]
0x180016e80  mov     r14, rcx
0x180016e83  mov     [rsp+60h+phkResult], rax; phkResult
0x180016e88  xor     ebx, ebx
0x180016e8a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x180016e91  xor     esi, esi
0x180016e93  mov     [rbp+hKey], rbx
0x180016e97  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180016e9e  mov     [rbp+lpData], rsi
0x180016ea2  mov     r9d, 2011Fh; samDesired
0x180016ea8  xor     r8d, r8d; ulOptions
0x180016eab  call    cs:__imp_RegOpenKeyExW
0x180016eb1  mov     r12d, 80070000h
0x180016eb7  test    eax, eax
0x180016eb9  jz      short loc_180016ECF
0x180016ebb  jg      short loc_180016EC1
0x180016ebd  mov     ebx, eax
0x180016ebf  jmp     short loc_180016EC7
0x180016ec1  movzx   ebx, ax
0x180016ec4  or      ebx, r12d
0x180016ec7  test    ebx, ebx
0x180016ec9  js      loc_18001712C
0x180016ecf  mov     rdx, r14; lpSubKey
0x180016ed2  mov     rcx, [rbp+hKey]; hKey
0x180016ed6  cmp     [rdi], esi
0x180016ed8  jz      short loc_180016F05
0x180016eda  xor     r9d, r9d; Reserved
0x180016edd  mov     r8d, 100h; samDesired
0x180016ee3  call    cs:__imp_RegDeleteKeyExW
0x180016ee9  test    eax, eax
0x180016eeb  jz      loc_180017114
0x180016ef1  jg      short loc_180016EFA
0x180016ef3  mov     ebx, eax
0x180016ef5  jmp     loc_180017114
0x180016efa  movzx   ebx, ax
0x180016efd  or      ebx, r12d
0x180016f00  jmp     loc_180017114
0x180016f05  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180016f0a  lea     rax, [rbp+arg_18]
0x180016f0e  mov     [rsp+60h+var_28], rax; phkResult
0x180016f13  xor     r9d, r9d; lpClass
0x180016f16  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180016f1b  xor     r8d, r8d; Reserved
0x180016f1e  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180016f26  mov     dword ptr [rsp+60h+phkResult], esi; dwOptions
0x180016f2a  mov     [rbp+arg_18], rsi
0x180016f2e  call    cs:__imp_RegCreateKeyExW
0x180016f34  test    eax, eax
0x180016f36  jz      short loc_180016F44
0x180016f38  jg      short loc_180016F3E
0x180016f3a  mov     ebx, eax
0x180016f3c  jmp     short loc_180016F44
0x180016f3e  movzx   ebx, ax
0x180016f41  or      ebx, r12d
0x180016f44  test    ebx, ebx
0x180016f46  js      loc_180017105
0x180016f4c  mov     rcx, [rbp+arg_18]; hKey
0x180016f50  lea     rdx, aAccessprivatec; "AccessPrivateContent"
0x180016f57  xor     eax, eax
0x180016f59  mov     r13d, 4
0x180016f5f  cmp     [rdi+4], eax
0x180016f62  mov     r9d, r13d; dwType
0x180016f65  mov     [rsp+60h+samDesired], r13d; cbData
0x180016f6a  setnz   al
0x180016f6d  xor     r8d, r8d; Reserved
0x180016f70  mov     [rbp+Data], eax
0x180016f73  lea     rax, [rbp+Data]
0x180016f77  mov     [rsp+60h+phkResult], rax; lpData
0x180016f7c  call    cs:__imp_RegSetValueExW
0x180016f82  test    eax, eax
0x180016f84  jz      short loc_180016F9A
0x180016f86  jg      short loc_180016F8C
0x180016f88  mov     ebx, eax
0x180016f8a  jmp     short loc_180016F92
0x180016f8c  movzx   ebx, ax
0x180016f8f  or      ebx, r12d
0x180016f92  test    ebx, ebx
0x180016f94  js      loc_180017105
0x180016f9a  mov     rcx, [rbp+arg_18]; hKey
0x180016f9e  lea     rdx, aZerostars; "ZeroStars"
0x180016fa5  xor     eax, eax
0x180016fa7  mov     [rsp+60h+samDesired], r13d; cbData
0x180016fac  cmp     [rdi+10h], eax
0x180016faf  mov     r9d, r13d; dwType
0x180016fb2  setnz   al
0x180016fb5  xor     r8d, r8d; Reserved
0x180016fb8  mov     [rbp+Data], eax
0x180016fbb  lea     rax, [rbp+Data]
0x180016fbf  mov     [rsp+60h+phkResult], rax; lpData
0x180016fc4  call    cs:__imp_RegSetValueExW
0x180016fca  test    eax, eax
0x180016fcc  jz      short loc_180016FE2
0x180016fce  jg      short loc_180016FD4
0x180016fd0  mov     ebx, eax
0x180016fd2  jmp     short loc_180016FDA
0x180016fd4  movzx   ebx, ax
0x180016fd7  or      ebx, r12d
0x180016fda  test    ebx, ebx
0x180016fdc  js      loc_180017105
0x180016fe2  mov     rcx, [rbp+arg_18]; hKey
0x180016fe6  lea     rax, [rdi+0Ch]
0x180016fea  mov     [rsp+60h+samDesired], r13d; cbData
0x180016fef  lea     rdx, aMinstars; "MinStars"
0x180016ff6  mov     r9d, r13d; dwType
0x180016ff9  mov     [rsp+60h+phkResult], rax; lpData
0x180016ffe  xor     r8d, r8d; Reserved
0x180017001  call    cs:__imp_RegSetValueExW
0x180017007  test    eax, eax
0x180017009  jz      short loc_18001701F
0x18001700b  jg      short loc_180017011
0x18001700d  mov     ebx, eax
0x18001700f  jmp     short loc_180017017
0x180017011  movzx   ebx, ax
0x180017014  or      ebx, r12d
0x180017017  test    ebx, ebx
0x180017019  js      loc_180017105
0x18001701f  mov     rcx, [rbp+arg_18]; hKey
0x180017023  lea     rdx, aAllstars; "AllStars"
0x18001702a  xor     eax, eax
0x18001702c  mov     [rsp+60h+samDesired], r13d; cbData
0x180017031  cmp     [rdi+8], eax
0x180017034  mov     r9d, r13d; dwType
0x180017037  setnz   al
0x18001703a  xor     r8d, r8d; Reserved
0x18001703d  mov     [rbp+Data], eax
0x180017040  lea     rax, [rbp+Data]
0x180017044  mov     [rsp+60h+phkResult], rax; lpData
0x180017049  call    cs:__imp_RegSetValueExW
0x18001704f  test    eax, eax
0x180017051  jz      short loc_180017067
0x180017053  jg      short loc_180017059
0x180017055  mov     ebx, eax
0x180017057  jmp     short loc_18001705F
0x180017059  movzx   ebx, ax
0x18001705c  or      ebx, r12d
0x18001705f  test    ebx, ebx
0x180017061  js      loc_180017105
0x180017067  mov     rcx, [rbp+arg_18]; hKey
0x18001706b  lea     rdx, aAllparentalrat; "AllParentalRatings"
0x180017072  xor     eax, eax
0x180017074  mov     [rsp+60h+samDesired], r13d; cbData
0x180017079  cmp     [rdi+14h], eax
0x18001707c  mov     r9d, r13d; dwType
0x18001707f  setnz   al
0x180017082  xor     r8d, r8d; Reserved
0x180017085  mov     [rbp+Data], eax
0x180017088  lea     rax, [rbp+Data]
0x18001708c  mov     [rsp+60h+phkResult], rax; lpData
0x180017091  call    cs:__imp_RegSetValueExW
0x180017097  test    eax, eax
0x180017099  jz      short loc_1800170AB
0x18001709b  jg      short loc_1800170A1
0x18001709d  mov     ebx, eax
0x18001709f  jmp     short loc_1800170A7
0x1800170a1  movzx   ebx, ax
0x1800170a4  or      ebx, r12d
0x1800170a7  test    ebx, ebx
0x1800170a9  js      short loc_180017105
0x1800170ab  mov     ecx, [rdi+18h]; this
0x1800170ae  test    ecx, ecx
0x1800170b0  jz      short loc_180017105
0x1800170b2  mov     rdx, [rdi+20h]; int
0x1800170b6  lea     r8, [rbp+lpData]; struct __MIDL___MIDL_itf_playerps_0000_0005_0003 *
0x1800170ba  call    ?ConvertParentalRating@HMEHelpers@@YAJHPEBU__MIDL___MIDL_itf_playerps_0000_0005_0003@@PEAPEAU__MIDL___MIDL_itf_playerps_0000_0005_0001@@@Z; HMEHelpers::ConvertParentalRating(int,__MIDL___MIDL_itf_playerps_0000_0005_0003 const *,__MIDL___MIDL_itf_playerps_0000_0005_0001 * *)
0x1800170bf  mov     rsi, [rbp+lpData]
0x1800170c3  mov     ebx, eax
0x1800170c5  test    eax, eax
0x1800170c7  js      short loc_180017105
0x1800170c9  mov     ecx, [rdi+18h]
0x1800170cc  mov     r9d, 3; dwType
0x1800170d2  xor     r8d, r8d; Reserved
0x1800170d5  lea     edx, [rcx+rcx*2]
0x1800170d8  mov     rcx, [rbp+arg_18]; hKey
0x1800170dc  shl     edx, 2
0x1800170df  mov     [rsp+60h+samDesired], edx; cbData
0x1800170e3  lea     rdx, aParentalrating; "ParentalRatingData"
0x1800170ea  mov     [rsp+60h+phkResult], rsi; lpData
0x1800170ef  call    cs:__imp_RegSetValueExW
0x1800170f5  test    eax, eax
0x1800170f7  jz      short loc_180017105
0x1800170f9  jg      short loc_1800170FF
0x1800170fb  mov     ebx, eax
0x1800170fd  jmp     short loc_180017105
0x1800170ff  movzx   ebx, ax
0x180017102  or      ebx, r12d
0x180017105  mov     rcx, [rbp+arg_18]; hKey
0x180017109  test    rcx, rcx
0x18001710c  jz      short loc_180017114
0x18001710e  call    cs:__imp_RegCloseKey
0x180017114  mov     rcx, [rbp+hKey]; hKey
0x180017118  call    cs:__imp_RegCloseKey
0x18001711e  test    ebx, ebx
0x180017120  js      short loc_18001712C
0x180017122  mov     rcx, r14; this
0x180017125  call    ?EnableServiceAccessForKey@HMEHelpers@@YAJPEBG@Z; HMEHelpers::EnableServiceAccessForKey(ushort const *)
0x18001712a  mov     ebx, eax
0x18001712c  mov     rcx, rsi; Block
0x18001712f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017134  lea     r11, [rsp+60h+var_s0]
0x180017139  mov     eax, ebx
0x18001713b  mov     rbx, [r11+30h]
0x18001713f  mov     rsi, [r11+38h]
0x180017143  mov     rsp, r11
0x180017146  pop     r14
0x180017148  pop     r13
0x18001714a  pop     r12
0x18001714c  pop     rdi
0x18001714d  pop     rbp
0x18001714e  retn
```
