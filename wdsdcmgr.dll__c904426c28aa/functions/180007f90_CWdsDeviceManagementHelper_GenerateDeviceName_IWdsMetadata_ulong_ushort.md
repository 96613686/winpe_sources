# CWdsDeviceManagementHelper::GenerateDeviceName(IWdsMetadata *,ulong,ushort * *)

- ea: `0x180007f90`
- end: `0x18000846f`
- name: `?GenerateDeviceName@CWdsDeviceManagementHelper@@UEAAJPEAUIWdsMetadata@@KPEAPEAG@Z`
- size: `1247`
- prototype: `__int64 __fastcall(CWdsDeviceManagementHelper *__hidden this, struct IWdsMetadata *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180007ba4`
- `0x180007f90`
- `0x180013648`
- `0x180013c14`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x180015660`
- `0x180015c9d`
- `0x180015cc0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000828d`
- `ADVAPI32!RegCloseKey` at `0x18000843d`
- `ADVAPI32!RegCloseKey` at `0x18000828d`
- `ADVAPI32!RegCloseKey` at `0x18000843d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800082b9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800082b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000805f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800080f9`
- `OLEAUT32!__imp_SysAllocString` at `0x180008140`
- `OLEAUT32!__imp_SysAllocString` at `0x1800081ca`
- `OLEAUT32!__imp_SysAllocString` at `0x1800083a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000805f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800080f9`
- `OLEAUT32!__imp_SysAllocString` at `0x180008140`
- `OLEAUT32!__imp_SysAllocString` at `0x1800081ca`
- `OLEAUT32!__imp_SysAllocString` at `0x1800083a3`
- `OLEAUT32!__imp_SysFreeString` at `0x180008133`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000840c`
- `OLEAUT32!__imp_SysFreeString` at `0x180008133`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000840c`

## string_xrefs

- `0x1800082ab`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Providers\BINLSVC`

## pseudocode

```c
__int64 __fastcall CWdsDeviceManagementHelper::GenerateDeviceName(
        CWdsDeviceManagementHelper *this,
        struct IWdsMetadata *a2,
        int a3,
        unsigned __int16 **a4)
{
  const char *v6; // rdx
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // r14
  OLECHAR *v9; // r12
  unsigned int v10; // ebx
  const char *v11; // rdx
  OLECHAR *v12; // rdi
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const char *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rdx
  LSTATUS v20; // esi
  const char *v21; // rdx
  const char *v22; // rdx
  signed int ValueSz; // esi
  const char *v24; // rdx
  unsigned int v25; // r9d
  BSTR v26; // rax
  BSTR v27; // rcx
  unsigned int NameFromTemplate; // eax
  const char *v29; // rdx
  const char *v30; // rdx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-E0h]
  int *v33; // [rsp+28h] [rbp-D8h]
  unsigned int *v34; // [rsp+30h] [rbp-D0h]
  _WORD v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v41; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v43[4]; // [rsp+78h] [rbp-88h] BYREF
  int v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+9Ch] [rbp-64h]
  unsigned __int8 v46[144]; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR psz[64]; // [rsp+130h] [rbp+30h] BYREF

  v40 = a3;
  v35[0] = 0;
  memset_0(v43, 0, 0x28u);
  memset_0(v46, 0, 0x88u);
  v36 = 0;
  LODWORD(v37) = 0;
  memset_0(psz, 0, sizeof(psz));
  Block = 0;
  v7 = 0;
  v41 = 0;
  v8 = 0;
  bstrString = 0;
  v9 = 0;
  hKey = 0;
  if ( !a2 || !a4 )
  {
    v10 = -2147024809;
    if ( (int)ElValidateHr(
                -2147024809,
                v6,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                0xA4u) < 0 )
      goto LABEL_53;
  }
  v10 = 0;
  v12 = SysAllocString(L"WDS.Device.Name");
  if ( !v12 )
    v10 = -2147024882;
  if ( (int)ElValidateHr(v10, v11, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp", 0xADu) >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IWdsMetadata *, OLECHAR *, int *))(*(_QWORD *)a2 + 56LL))(a2, v12, &v36);
    if ( (int)ElValidateHr(v10, v13, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp", 0xB0u) >= 0 )
    {
      if ( !v36
        || (v10 = -2147024809,
            (int)ElValidateHr(
                   -2147024809,
                   v14,
                   "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                   0xB5u) >= 0) )
      {
        v10 = 0;
        v9 = SysAllocString(&word_18001870C);
        if ( !v9 )
          v10 = -2147024882;
        if ( (int)ElValidateHr(v10, v15, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp", 0xBDu) >= 0 )
        {
          v10 = 0;
          if ( v12 )
            SysFreeString(v12);
          v12 = SysAllocString(L"WDS.Device.User");
          if ( !v12 )
            v10 = -2147024882;
          if ( (int)ElValidateHr(
                      v10,
                      v16,
                      "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                      0xC1u) >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(struct IWdsMetadata *, OLECHAR *, OLECHAR *, _WORD *, BSTR *))(*(_QWORD *)a2 + 72LL))(
                    a2,
                    v12,
                    v9,
                    v35,
                    &bstrString);
            if ( (int)ElValidateHr(
                        v10,
                        v17,
                        "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                        0xC7u) >= 0 )
            {
              v10 = 0;
              if ( v12 )
                SysFreeString(v12);
              v12 = SysAllocString(L"WDS.Device.ID");
              if ( !v12 )
                v10 = -2147024882;
              if ( (int)ElValidateHr(
                          v10,
                          v18,
                          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                          0xCBu) >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(struct IWdsMetadata *, OLECHAR *, unsigned __int8 *, __int64, unsigned __int64 *))(*(_QWORD *)a2 + 176LL))(
                        a2,
                        v12,
                        v46,
                        128,
                        &v37);
                if ( (int)ElValidateHr(
                            v10,
                            v19,
                            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                            0xD1u) >= 0 )
                {
                  v20 = HexToString(v46, (unsigned int)v37, (unsigned __int16 **)&Block);
                  v10 = 0;
                  if ( !ElValidateWin32(
                          v20,
                          v21,
                          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                          0xD4u) )
                  {
                    if ( hKey )
                    {
                      RegCloseKey(hKey);
                      hKey = 0;
                    }
                    v20 = RegOpenKeyExW(
                            HKEY_LOCAL_MACHINE,
                            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Providers\\BINLSVC",
                            0,
                            0x20119u,
                            &hKey);
                    if ( !ElValidateWin32(
                            v20,
                            v22,
                            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                            0xDEu) )
                    {
                      ValueSz = CRegKey::GetValueSz((CRegKey *)&hKey, L"netbootNewMachineNamingPolicy", &v41);
                      if ( ElValidateWin32(
                             ValueSz,
                             v24,
                             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                             0xE2u) )
                      {
                        v7 = v41;
                        v10 = (unsigned __int16)ValueSz | 0x80070000;
                        if ( ValueSz <= 0 )
                          v10 = ValueSz;
                        goto LABEL_47;
                      }
                      v26 = bstrString;
                      if ( !bstrString || (v27 = bstrString, !*bstrString) )
                        v27 = 0;
                      v7 = v41;
                      v45 = 0;
                      if ( !v27 )
                        v26 = (BSTR)&word_18001870C;
                      v43[1] = &word_18001870C;
                      v43[0] = v26;
                      v43[3] = Block;
                      v43[2] = &word_18001870C;
                      v44 = v40;
                      NameFromTemplate = GenerateNameFromTemplate(
                                           v41,
                                           (struct _GENNAME_VARIABLES *)v43,
                                           psz,
                                           v25,
                                           phkResult,
                                           v33,
                                           v34);
                      v20 = NameFromTemplate;
                      if ( (NameFromTemplate & 0xFFFFFFFB) == 0
                        || !ElValidateWin32(
                              NameFromTemplate,
                              v29,
                              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                              0xFAu) )
                      {
                        v8 = SysAllocString(psz);
                        if ( !v8 )
                          v10 = -2147024882;
                        if ( (int)ElValidateHr(
                                    v10,
                                    v30,
                                    "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp",
                                    0x102u) >= 0 )
                        {
                          *a4 = v8;
                          v8 = 0;
                        }
                        goto LABEL_47;
                      }
                    }
                  }
                  v10 = (unsigned __int16)v20 | 0x80070000;
                  if ( v20 <= 0 )
                    v10 = v20;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_47:
  if ( v12 )
    SysFreeString(v12);
  if ( v9 )
    SysFreeString(v9);
  if ( v8 )
    SysFreeString(v8);
LABEL_53:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v7 )
    operator delete(v7);
  if ( Block )
    operator delete(Block);
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180007f90  mov     [rsp-8+arg_0], rbx
0x180007f95  push    rbp
0x180007f96  push    rsi
0x180007f97  push    rdi
0x180007f98  push    r12
0x180007f9a  push    r13
0x180007f9c  push    r14
0x180007f9e  push    r15
0x180007fa0  lea     rbp, [rsp-0C0h]
0x180007fa8  sub     rsp, 1C0h
0x180007faf  mov     rax, cs:__security_cookie
0x180007fb6  xor     rax, rsp
0x180007fb9  mov     [rbp+0F0h+var_40], rax
0x180007fc0  xor     edi, edi
0x180007fc2  mov     [rsp+1F0h+var_190], r8d
0x180007fc7  mov     rsi, rdx
0x180007fca  mov     [rsp+1F0h+var_1B0], di
0x180007fcf  xor     edx, edx; Val
0x180007fd1  lea     rcx, [rsp+1F0h+var_178]; void *
0x180007fd6  mov     r13, r9
0x180007fd9  lea     r8d, [rdi+28h]; Size
0x180007fdd  call    memset_0
0x180007fe2  xor     edx, edx; Val
0x180007fe4  lea     rcx, [rbp+0F0h+var_150]; void *
0x180007fe8  mov     r8d, 88h; Size
0x180007fee  call    memset_0
0x180007ff3  xor     edx, edx; Val
0x180007ff5  mov     [rsp+1F0h+var_1AC], edi
0x180007ff9  mov     r8d, 80h; Size
0x180007fff  mov     dword ptr [rsp+1F0h+var_1A8], edi
0x180008003  lea     rcx, [rbp+0F0h+psz]; void *
0x180008007  call    memset_0
0x18000800c  mov     [rsp+1F0h+Block], rdi
0x180008011  mov     r15d, edi
0x180008014  mov     [rsp+1F0h+var_188], rdi
0x180008019  mov     r14d, edi
0x18000801c  mov     [rsp+1F0h+bstrString], rdi
0x180008021  mov     r12d, edi
0x180008024  mov     [rsp+1F0h+hKey], rdi
0x180008029  mov     eax, 80070057h
0x18000802e  test    rsi, rsi
0x180008031  jz      short loc_180008038
0x180008033  test    r13, r13
0x180008036  jnz     short loc_180008056
0x180008038  mov     r9d, 0A4h; unsigned int
0x18000803e  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008045  mov     ecx, eax; int
0x180008047  mov     ebx, eax
0x180008049  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000804e  test    eax, eax
0x180008050  js      loc_180008402
0x180008056  lea     rcx, psz; "WDS.Device.Name"
0x18000805d  mov     ebx, edi
0x18000805f  call    cs:__imp_SysAllocString
0x180008065  mov     ecx, 8007000Eh
0x18000806a  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008071  test    rax, rax
0x180008074  mov     r9d, 0ADh; unsigned int
0x18000807a  mov     rdi, rax
0x18000807d  cmovz   ebx, ecx
0x180008080  mov     ecx, ebx; int
0x180008082  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180008087  test    eax, eax
0x180008089  js      loc_1800083D6
0x18000808f  mov     rax, [rsi]
0x180008092  lea     r8, [rsp+1F0h+var_1AC]
0x180008097  mov     rdx, rdi
0x18000809a  mov     rcx, rsi
0x18000809d  mov     rax, [rax+38h]
0x1800080a1  call    cs:__guard_dispatch_icall_fptr
0x1800080a7  mov     r9d, 0B0h; unsigned int
0x1800080ad  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800080b4  mov     ecx, eax; int
0x1800080b6  mov     ebx, eax
0x1800080b8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800080bd  test    eax, eax
0x1800080bf  js      loc_1800083D6
0x1800080c5  xor     eax, eax
0x1800080c7  cmp     [rsp+1F0h+var_1AC], eax
0x1800080cb  jz      short loc_1800080F0
0x1800080cd  mov     ecx, 80070057h; int
0x1800080d2  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800080d9  mov     r9d, 0B5h; unsigned int
0x1800080df  mov     ebx, ecx
0x1800080e1  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800080e6  test    eax, eax
0x1800080e8  js      loc_1800083D6
0x1800080ee  xor     eax, eax
0x1800080f0  lea     rcx, word_18001870C; psz
0x1800080f7  mov     ebx, eax
0x1800080f9  call    cs:__imp_SysAllocString
0x1800080ff  mov     r9d, 0BDh; unsigned int
0x180008105  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000810c  test    rax, rax
0x18000810f  mov     r12, rax
0x180008112  mov     eax, 8007000Eh
0x180008117  cmovz   ebx, eax
0x18000811a  mov     ecx, ebx; int
0x18000811c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180008121  test    eax, eax
0x180008123  js      loc_1800083D6
0x180008129  xor     ebx, ebx
0x18000812b  test    rdi, rdi
0x18000812e  jz      short loc_180008139
0x180008130  mov     rcx, rdi; bstrString
0x180008133  call    cs:__imp_SysFreeString
0x180008139  lea     rcx, aWdsDeviceUser; "WDS.Device.User"
0x180008140  call    cs:__imp_SysAllocString
0x180008146  mov     r9d, 0C1h; unsigned int
0x18000814c  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008153  test    rax, rax
0x180008156  mov     rdi, rax
0x180008159  mov     eax, 8007000Eh
0x18000815e  cmovz   ebx, eax
0x180008161  mov     ecx, ebx; int
0x180008163  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180008168  test    eax, eax
0x18000816a  js      loc_1800083D6
0x180008170  mov     rax, [rsi]
0x180008173  lea     rcx, [rsp+1F0h+bstrString]
0x180008178  mov     [rsp+1F0h+phkResult], rcx
0x18000817d  lea     r9, [rsp+1F0h+var_1B0]
0x180008182  mov     r8, r12
0x180008185  mov     rdx, rdi
0x180008188  mov     rcx, rsi
0x18000818b  mov     rax, [rax+48h]
0x18000818f  call    cs:__guard_dispatch_icall_fptr
0x180008195  mov     r9d, 0C7h; unsigned int
0x18000819b  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800081a2  mov     ecx, eax; int
0x1800081a4  mov     ebx, eax
0x1800081a6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800081ab  test    eax, eax
0x1800081ad  js      loc_1800083D6
0x1800081b3  xor     ebx, ebx
0x1800081b5  test    rdi, rdi
0x1800081b8  jz      short loc_1800081C3
0x1800081ba  mov     rcx, rdi; bstrString
0x1800081bd  call    cs:__imp_SysFreeString
0x1800081c3  lea     rcx, aWdsDeviceId; "WDS.Device.ID"
0x1800081ca  call    cs:__imp_SysAllocString
0x1800081d0  mov     r9d, 0CBh; unsigned int
0x1800081d6  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800081dd  test    rax, rax
0x1800081e0  mov     rdi, rax
0x1800081e3  mov     eax, 8007000Eh
0x1800081e8  cmovz   ebx, eax
0x1800081eb  mov     ecx, ebx; int
0x1800081ed  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800081f2  test    eax, eax
0x1800081f4  js      loc_1800083D6
0x1800081fa  mov     rax, [rsi]
0x1800081fd  lea     rdx, [rsp+1F0h+var_1A8]
0x180008202  mov     [rsp+1F0h+phkResult], rdx
0x180008207  lea     r8, [rbp+0F0h+var_150]
0x18000820b  mov     r9d, 80h
0x180008211  mov     rdx, rdi
0x180008214  mov     rcx, rsi
0x180008217  mov     rax, [rax+0B0h]
0x18000821e  call    cs:__guard_dispatch_icall_fptr
0x180008224  mov     r9d, 0D1h; unsigned int
0x18000822a  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008231  mov     ecx, eax; int
0x180008233  mov     ebx, eax
0x180008235  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000823a  test    eax, eax
0x18000823c  js      loc_1800083D6
0x180008242  mov     edx, dword ptr [rsp+1F0h+var_1A8]; unsigned __int64
0x180008246  lea     r8, [rsp+1F0h+Block]; unsigned __int16 **
0x18000824b  lea     rcx, [rbp+0F0h+var_150]; unsigned __int8 *
0x18000824f  call    ?HexToString@@YAKPEBE_KPEAPEAG@Z; HexToString(uchar const *,unsigned __int64,ushort * *)
0x180008254  mov     r9d, 0D4h; unsigned int
0x18000825a  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008261  mov     ecx, eax; unsigned int
0x180008263  mov     esi, eax
0x180008265  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000826a  xor     ebx, ebx
0x18000826c  test    eax, eax
0x18000826e  jz      short loc_180008283
0x180008270  movzx   ebx, si
0x180008273  or      ebx, 80070000h
0x180008279  test    esi, esi
0x18000827b  cmovle  ebx, esi
0x18000827e  jmp     loc_1800083D6
0x180008283  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180008288  test    rcx, rcx
0x18000828b  jz      short loc_180008298
0x18000828d  call    cs:__imp_RegCloseKey
0x180008293  mov     [rsp+1F0h+hKey], rbx
0x180008298  lea     rax, [rsp+1F0h+hKey]
0x18000829d  mov     r9d, 20119h; samDesired
0x1800082a3  xor     r8d, r8d; ulOptions
0x1800082a6  mov     [rsp+1F0h+phkResult], rax; unsigned __int16 **
0x1800082ab  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\WD"...
0x1800082b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800082b9  call    cs:__imp_RegOpenKeyExW
0x1800082bf  mov     r9d, 0DEh; unsigned int
0x1800082c5  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800082cc  mov     ecx, eax; unsigned int
0x1800082ce  mov     esi, eax
0x1800082d0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800082d5  test    eax, eax
0x1800082d7  jnz     short loc_180008270
0x1800082d9  lea     r8, [rsp+1F0h+var_188]; unsigned __int16 **
0x1800082de  lea     rdx, aNetbootnewmach; "netbootNewMachineNamingPolicy"
0x1800082e5  lea     rcx, [rsp+1F0h+hKey]; this
0x1800082ea  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x1800082ef  mov     r9d, 0E2h; unsigned int
0x1800082f5  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800082fc  mov     ecx, eax; unsigned int
0x1800082fe  mov     esi, eax
0x180008300  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008305  test    eax, eax
0x180008307  jz      short loc_180008321
0x180008309  mov     r15, [rsp+1F0h+var_188]
0x18000830e  movzx   ebx, si
0x180008311  or      ebx, 80070000h
0x180008317  test    esi, esi
0x180008319  cmovle  ebx, esi
0x18000831c  jmp     loc_1800083D6
0x180008321  mov     rax, [rsp+1F0h+bstrString]
0x180008326  test    rax, rax
0x180008329  jz      short loc_180008333
0x18000832b  mov     rcx, rax
0x18000832e  cmp     [rax], bx
0x180008331  jnz     short loc_180008336
0x180008333  mov     rcx, rbx
0x180008336  mov     r15, [rsp+1F0h+var_188]
0x18000833b  lea     r8, [rbp+0F0h+psz]; unsigned __int16 *
0x18000833f  test    rcx, rcx
0x180008342  mov     [rbp+0F0h+var_154], ebx
0x180008345  lea     rcx, word_18001870C
0x18000834c  cmovz   rax, rcx
0x180008350  mov     [rbp+0F0h+var_170], rcx
0x180008354  mov     [rsp+1F0h+var_178], rax
0x180008359  lea     rdx, [rsp+1F0h+var_178]; struct _GENNAME_VARIABLES *
0x18000835e  mov     rax, [rsp+1F0h+Block]
0x180008363  mov     [rbp+0F0h+var_160], rax
0x180008367  mov     eax, [rsp+1F0h+var_190]
0x18000836b  mov     [rbp+0F0h+var_168], rcx
0x18000836f  mov     rcx, r15; unsigned __int16 *
0x180008372  mov     [rbp+0F0h+var_158], eax
0x180008375  call    ?GenerateNameFromTemplate@@YAKPEAGPEAU_GENNAME_VARIABLES@@0KPEAPEAGPEAHPEAK@Z; GenerateNameFromTemplate(ushort *,_GENNAME_VARIABLES *,ushort *,ulong,ushort * *,int *,ulong *)
0x18000837a  mov     esi, eax
0x18000837c  test    eax, 0FFFFFFFBh
0x180008381  jz      short loc_18000839F
0x180008383  mov     r9d, 0FAh; unsigned int
0x180008389  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180008390  mov     ecx, eax; unsigned int
0x180008392  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180008397  test    eax, eax
0x180008399  jnz     loc_180008270
0x18000839f  lea     rcx, [rbp+0F0h+psz]; psz
0x1800083a3  call    cs:__imp_SysAllocString
0x1800083a9  mov     r9d, 102h; unsigned int
0x1800083af  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x1800083b6  test    rax, rax
0x1800083b9  mov     r14, rax
0x1800083bc  mov     eax, 8007000Eh
0x1800083c1  cmovz   ebx, eax
0x1800083c4  mov     ecx, ebx; int
0x1800083c6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800083cb  test    eax, eax
0x1800083cd  js      short loc_1800083D6
0x1800083cf  mov     [r13+0], r14
0x1800083d3  xor     r14d, r14d
0x1800083d6  test    rdi, rdi
0x1800083d9  jz      short loc_1800083E4
0x1800083db  mov     rcx, rdi; bstrString
0x1800083de  call    cs:__imp_SysFreeString
0x1800083e4  xor     edi, edi
0x1800083e6  test    r12, r12
0x1800083e9  jz      short loc_1800083F4
0x1800083eb  mov     rcx, r12; bstrString
0x1800083ee  call    cs:__imp_SysFreeString
0x1800083f4  test    r14, r14
0x1800083f7  jz      short loc_180008402
0x1800083f9  mov     rcx, r14; bstrString
0x1800083fc  call    cs:__imp_SysFreeString
0x180008402  mov     rcx, [rsp+1F0h+bstrString]; bstrString
0x180008407  test    rcx, rcx
0x18000840a  jz      short loc_180008417
0x18000840c  call    cs:__imp_SysFreeString
0x180008412  mov     [rsp+1F0h+bstrString], rdi
0x180008417  test    r15, r15
0x18000841a  jz      short loc_180008424
0x18000841c  mov     rcx, r15; Block
0x18000841f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008424  mov     rcx, [rsp+1F0h+Block]; Block
0x180008429  test    rcx, rcx
0x18000842c  jz      short loc_180008433
0x18000842e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008433  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180008438  test    rcx, rcx
0x18000843b  jz      short loc_180008443
0x18000843d  call    cs:__imp_RegCloseKey
0x180008443  mov     eax, ebx
0x180008445  mov     rcx, [rbp+0F0h+var_40]
0x18000844c  xor     rcx, rsp; StackCookie
0x18000844f  call    __security_check_cookie
  ... truncated ...
```
