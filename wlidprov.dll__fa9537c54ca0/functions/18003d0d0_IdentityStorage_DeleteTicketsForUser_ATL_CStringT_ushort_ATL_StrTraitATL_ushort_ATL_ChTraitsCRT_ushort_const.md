# IdentityStorage::DeleteTicketsForUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18003d0d0`
- end: `0x18003d50a`
- name: `?DeleteTicketsForUser@IdentityStorage@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003dd2c`

## callees

- `0x180002eb4`
- `0x1800034c0`
- `0x1800035cc`
- `0x180003990`
- `0x180003c44`
- `0x180003cf0`
- `0x180004b00`
- `0x180004fdc`
- `0x1800050f8`
- `0x18000535c`
- `0x1800061a8`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x1800113e8`
- `0x180013434`
- `0x1800185c8`
- `0x18003d0d0`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d3fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d3fd`

## string_xrefs

- `0x18003d426`: `DeleteBufferFromRegistry failed = 0x%x`
- `0x18003d1bc`: `hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useKeyCurrentUser, &hkeyCurrentUser)`
- `0x18003d15b`: `IdentityStorage::DeleteTicketsForUser`
- `0x18003d475`: `IdentityStorage::DeleteTicketsForUser`
- `0x18003d133`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IdentityStorage::DeleteTicketsForUser(__int64 *a1, _QWORD *a2)
{
  struct IRegistryFunctions *v4; // r14
  RegistryHelper *v5; // rcx
  int RootKey; // eax
  signed int v7; // eax
  signed int v8; // eax
  unsigned int v9; // esi
  unsigned __int16 *v10; // rbx
  __int64 (__fastcall *v11)(struct IRegistryFunctions *, _QWORD, _QWORD, __int64, int *, _QWORD, _QWORD, _QWORD, _QWORD); // rdi
  __int64 BufferSetLength; // rax
  signed int v13; // edi
  __int64 v14; // rdx
  int *v15; // rdi
  __int64 v16; // rbx
  int v17; // eax
  unsigned int v18; // ebx
  HKEY *v20; // [rsp+20h] [rbp-E0h]
  HKEY *v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+70h] [rbp-90h] BYREF
  HKEY v23; // [rsp+78h] [rbp-88h] BYREF
  char v24[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v29[3]; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v30[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v31; // [rsp+D8h] [rbp-28h] BYREF
  char v32[8]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v33[11]; // [rsp+E8h] [rbp-18h] BYREF
  int v34; // [rsp+150h] [rbp+50h] BYREF
  int v35; // [rsp+160h] [rbp+60h] BYREF
  int v36; // [rsp+168h] [rbp+68h] BYREF

  v35 = 0;
  v22 = 0;
  v36 = 0;
  v4 = (struct IRegistryFunctions *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a1 + 8LL))(*a1);
  v30[0] = 0;
  v30[2] = (HKEY)v4;
  v30[1] = 0;
  v29[0] = 0;
  v29[2] = v4;
  v29[1] = 0;
  v28 = *a1;
  IdentityStorage::GetEnvironmentSpecificRegistryKey(
    a1,
    &v27,
    (__int64)L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  v33[0] = "IdentityStorage::DeleteTicketsForUser";
  v33[1] = &v35;
  v33[2] = 0;
  v33[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::DeleteTicketsForUser",
    (const char *)0x555,
    0,
    (const unsigned __int16 *)v20);
  v23 = HKEY_CURRENT_USER;
  RootKey = RegistryHelper::GetRootKey(v5, v4, &v23, (bool *)&v34, v30);
  v35 = RootKey;
  if ( RootKey >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, HKEY, __int64, _QWORD, int, _QWORD *))(*(_QWORD *)v4 + 80LL))(
           v4,
           v30[0],
           v27,
           0,
           131097,
           v29);
    if ( v7 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v35 = v7;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::DeleteTicketsForUser",
        0x55Au,
        v7,
        "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 96LL))(
             v4,
             v29[0],
             0,
             0,
             0,
             &v22,
             &v36,
             0,
             0,
             0,
             0,
             0,
             0);
      if ( v8 )
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        v35 = v8;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          "IdentityStorage::DeleteTicketsForUser",
          0x567u,
          v8,
          "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
      }
      else
      {
        ++v36;
        v9 = 0;
        if ( v22 )
        {
          v10 = v25;
          while ( 1 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v24);
            v34 = v36;
            v23 = 0;
            v11 = *(__int64 (__fastcall **)(struct IRegistryFunctions *, _QWORD, _QWORD, __int64, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 48LL);
            BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(v24);
            v13 = v11(v4, v29[0], v9, BufferSetLength, &v34, 0, 0, 0, 0);
            ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v24, 0xFFFFFFFFLL);
            if ( v13 == 259 )
              break;
            if ( v13 )
            {
              if ( v13 > 0 )
                v13 = (unsigned __int16)v13 | 0x80070000;
              v35 = v13;
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
                "IdentityStorage::DeleteTicketsForUser",
                0x581u,
                v13,
                "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
              break;
            }
            v14 = *(_QWORD *)ATL::operator+(v32, &v27, v24);
            v15 = (int *)(v10 - 12);
            if ( (unsigned __int16 *)(v14 - 24) != v10 - 12 )
            {
              if ( v15[4] >= 0 && *(_QWORD *)(v14 - 24) == *(_QWORD *)v15 )
              {
                v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
                ATL::CStringData::Release((ATL::CStringData *)v15);
                v10 = (unsigned __int16 *)(v16 + 24);
                v25 = v10;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v25, v14, *(unsigned int *)(v14 - 16));
                v10 = v25;
              }
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v32);
            if ( (int)RegistryHelper::ReadBufferFromRegistry(
                        (RegistryHelper *)&v28,
                        0,
                        v10,
                        L"UserId",
                        2u,
                        (unsigned __int8 **)&v23,
                        &v31) >= 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v23);
              if ( !(unsigned int)_o__wcsicmp(*a2, v26) )
              {
                v17 = RegistryHelper::DeleteBufferFromRegistry((RegistryHelper *)&v28, v30[0], v10, L"UserTicket");
                if ( v17 < 0 )
                {
                  LODWORD(v21) = v17;
                  TracePrintW(
                    2u,
                    "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
                    0x58Du,
                    L"DeleteBufferFromRegistry failed = 0x%x",
                    v21);
                }
              }
            }
            CMIDLPtr<unsigned short *>::Clear(&v23);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v24);
            if ( ++v9 >= v22 )
              goto LABEL_34;
          }
          CMIDLPtr<unsigned short *>::Clear(&v23);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v24);
        }
      }
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::DeleteTicketsForUser",
      0x557u,
      RootKey,
      "hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useKeyCurrentUser, &hkeyCurrentUser)");
  }
LABEL_34:
  if ( v35 == -2147024894 || v35 == -2147023878 )
    v35 = 0;
  v18 = v35;
  CTraceFuncW<long>::~CTraceFuncW<long>(v33);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v26);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v25);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v27);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v29);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v30);
  return v18;
}

```

## disassembly

```asm
0x18003d0d0  mov     [rsp-8+arg_8], rbx
0x18003d0d5  push    rbp
0x18003d0d6  push    rsi
0x18003d0d7  push    rdi
0x18003d0d8  push    r12
0x18003d0da  push    r13
0x18003d0dc  push    r14
0x18003d0de  push    r15
0x18003d0e0  lea     rbp, [rsp-10h]
0x18003d0e5  sub     rsp, 110h
0x18003d0ec  mov     r15, rdx
0x18003d0ef  mov     rbx, rcx
0x18003d0f2  xor     r12d, r12d
0x18003d0f5  mov     [rbp+40h+arg_10], r12d
0x18003d0f9  mov     [rsp+140h+var_D0], r12d
0x18003d0fe  mov     [rbp+40h+arg_18], r12d
0x18003d102  mov     rcx, [rcx]
0x18003d105  mov     rax, [rcx]
0x18003d108  mov     rax, [rax+8]
0x18003d10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d111  mov     r14, rax
0x18003d114  mov     [rbp+40h+var_80], r12
0x18003d118  mov     [rbp+40h+var_70], rax
0x18003d11c  mov     [rbp+40h+var_78], r12
0x18003d120  mov     [rbp+40h+var_98], r12
0x18003d124  mov     [rbp+40h+var_88], rax
0x18003d128  mov     [rbp+40h+var_90], r12
0x18003d12c  mov     rcx, [rbx]
0x18003d12f  mov     [rbp+40h+var_A0], rcx
0x18003d133  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18003d13a  lea     rdx, [rbp+40h+var_A8]
0x18003d13e  mov     rcx, rbx
0x18003d141  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x18003d146  nop
0x18003d147  lea     rcx, [rbp+40h+var_B8]; void *
0x18003d14b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003d150  nop
0x18003d151  lea     rcx, [rbp+40h+var_B0]; void *
0x18003d155  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003d15a  nop
0x18003d15b  lea     rbx, aIdentitystorag_15; "IdentityStorage::DeleteTicketsForUser"
0x18003d162  mov     [rbp+40h+var_58], rbx
0x18003d166  lea     rax, [rbp+40h+arg_10]
0x18003d16a  mov     [rbp+40h+var_50], rax
0x18003d16e  mov     [rbp+40h+var_48], r12
0x18003d172  mov     [rbp+40h+var_40], r12
0x18003d176  xor     r9d, r9d; unsigned int
0x18003d179  mov     r8d, 555h; char *
0x18003d17f  mov     rdx, rbx; char *
0x18003d182  lea     r13, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003d189  mov     rcx, r13; this
0x18003d18c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003d191  nop
0x18003d192  mov     [rsp+140h+var_C8], 0FFFFFFFF80000001h
0x18003d19b  lea     rax, [rbp+40h+var_80]
0x18003d19f  mov     [rsp+140h+var_120], rax; HKEY *
0x18003d1a4  lea     r9, [rbp+40h+arg_0]; bool *
0x18003d1a8  lea     r8, [rsp+140h+var_C8]; HKEY *
0x18003d1ad  mov     rdx, r14; struct IRegistryFunctions *
0x18003d1b0  call    ?GetRootKey@RegistryHelper@@QEAAJPEAVIRegistryFunctions@@AEBQEAUHKEY__@@PEA_NPEAPEAU3@@Z; RegistryHelper::GetRootKey(IRegistryFunctions *,HKEY__ * const &,bool *,HKEY__ * *)
0x18003d1b5  mov     [rbp+40h+arg_10], eax
0x18003d1b8  test    eax, eax
0x18003d1ba  jns     short loc_18003D1E1
0x18003d1bc  lea     r8, aHrRegistryhelp_15; "hr = registryHelper.GetRootKey(pRegistr"...
0x18003d1c3  mov     [rsp+140h+var_120], r8; char *
0x18003d1c8  mov     r8d, 557h; unsigned int
0x18003d1ce  mov     r9d, eax; int
0x18003d1d1  mov     rdx, rbx; char *
0x18003d1d4  mov     rcx, r13; char *
0x18003d1d7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003d1dc  jmp     loc_18003D499
0x18003d1e1  mov     rax, [r14]
0x18003d1e4  lea     rcx, [rbp+40h+var_98]
0x18003d1e8  mov     [rsp+140h+var_118], rcx
0x18003d1ed  mov     dword ptr [rsp+140h+var_120], 20019h
0x18003d1f5  xor     r9d, r9d
0x18003d1f8  mov     r8, [rbp+40h+var_A8]
0x18003d1fc  mov     rdx, [rbp+40h+var_80]
0x18003d200  mov     rcx, r14
0x18003d203  mov     rax, [rax+50h]
0x18003d207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d20c  mov     edi, 80070000h
0x18003d211  test    eax, eax
0x18003d213  jz      short loc_18003D237
0x18003d215  jle     short loc_18003D21C
0x18003d217  movzx   eax, ax
0x18003d21a  or      eax, edi
0x18003d21c  mov     [rbp+40h+arg_10], eax
0x18003d21f  test    eax, eax
0x18003d221  jns     short loc_18003D237
0x18003d223  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18003d22a  mov     [rsp+140h+var_120], rcx
0x18003d22f  mov     r8d, 55Ah
0x18003d235  jmp     short loc_18003D1CE
0x18003d237  mov     rax, [r14]
0x18003d23a  mov     [rsp+140h+var_E0], r12
0x18003d23f  mov     [rsp+140h+var_E8], r12
0x18003d244  mov     [rsp+140h+var_F0], r12
0x18003d249  mov     [rsp+140h+var_F8], r12
0x18003d24e  mov     [rsp+140h+var_100], r12
0x18003d253  mov     [rsp+140h+var_108], r12
0x18003d258  lea     rcx, [rbp+40h+arg_18]
0x18003d25c  mov     [rsp+140h+var_110], rcx
0x18003d261  lea     rcx, [rsp+140h+var_D0]
0x18003d266  mov     [rsp+140h+var_118], rcx
0x18003d26b  mov     [rsp+140h+var_120], r12
0x18003d270  xor     r9d, r9d
0x18003d273  xor     r8d, r8d
0x18003d276  mov     rdx, [rbp+40h+var_98]
0x18003d27a  mov     rcx, r14
0x18003d27d  mov     rax, [rax+60h]
0x18003d281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d286  test    eax, eax
0x18003d288  jz      short loc_18003D2AF
0x18003d28a  jle     short loc_18003D291
0x18003d28c  movzx   eax, ax
0x18003d28f  or      eax, edi
0x18003d291  mov     [rbp+40h+arg_10], eax
0x18003d294  test    eax, eax
0x18003d296  jns     short loc_18003D2AF
0x18003d298  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18003d29f  mov     [rsp+140h+var_120], rcx
0x18003d2a4  mov     r8d, 567h
0x18003d2aa  jmp     loc_18003D1CE
0x18003d2af  inc     [rbp+40h+arg_18]
0x18003d2b2  mov     esi, r12d
0x18003d2b5  cmp     [rsp+140h+var_D0], r12d
0x18003d2ba  jbe     loc_18003D499
0x18003d2c0  mov     rbx, [rbp+40h+var_B8]
0x18003d2c4  lea     rcx, [rbp+40h+var_C0]; void *
0x18003d2c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003d2cd  nop
0x18003d2ce  mov     edx, [rbp+40h+arg_18]
0x18003d2d1  mov     [rbp+40h+arg_0], edx
0x18003d2d4  mov     [rsp+140h+var_C8], r12
0x18003d2d9  mov     rax, [r14]
0x18003d2dc  mov     rdi, [rax+30h]
0x18003d2e0  lea     rcx, [rbp+40h+var_C0]
0x18003d2e4  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18003d2e9  mov     [rsp+140h+var_100], r12
0x18003d2ee  mov     [rsp+140h+var_108], r12
0x18003d2f3  mov     [rsp+140h+var_110], r12
0x18003d2f8  mov     [rsp+140h+var_118], r12
0x18003d2fd  lea     rcx, [rbp+40h+arg_0]
0x18003d301  mov     [rsp+140h+var_120], rcx
0x18003d306  mov     r9, rax
0x18003d309  mov     r8d, esi
0x18003d30c  mov     rdx, [rbp+40h+var_98]
0x18003d310  mov     rcx, r14
0x18003d313  mov     rax, rdi
0x18003d316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d31b  mov     edi, eax
0x18003d31d  or      edx, 0FFFFFFFFh
0x18003d320  lea     rcx, [rbp+40h+var_C0]
0x18003d324  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18003d329  cmp     edi, 103h
0x18003d32f  jz      loc_18003D485
0x18003d335  test    edi, edi
0x18003d337  jz      short loc_18003D34F
0x18003d339  jle     short loc_18003D344
0x18003d33b  movzx   edi, di
0x18003d33e  or      edi, 80070000h
0x18003d344  mov     [rbp+40h+arg_10], edi
0x18003d347  test    edi, edi
0x18003d349  js      loc_18003D460
0x18003d34f  lea     r8, [rbp+40h+var_C0]
0x18003d353  lea     rdx, [rbp+40h+var_A8]
0x18003d357  lea     rcx, [rbp+40h+var_60]
0x18003d35b  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003d360  nop
0x18003d361  mov     rdx, [rax]
0x18003d364  lea     rcx, [rdx-18h]
0x18003d368  lea     rdi, [rbx-18h]
0x18003d36c  cmp     rcx, rdi
0x18003d36f  jz      short loc_18003D3AA
0x18003d371  cmp     [rdi+10h], r12d
0x18003d375  jl      short loc_18003D399
0x18003d377  mov     rax, [rdi]
0x18003d37a  cmp     [rcx], rax
0x18003d37d  jnz     short loc_18003D399
0x18003d37f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18003d384  mov     rbx, rax
0x18003d387  mov     rcx, rdi; this
0x18003d38a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003d38f  add     rbx, 18h
0x18003d393  mov     [rbp+40h+var_B8], rbx
0x18003d397  jmp     short loc_18003D3AA
0x18003d399  mov     r8d, [rdx-10h]
0x18003d39d  lea     rcx, [rbp+40h+var_B8]
0x18003d3a1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003d3a6  mov     rbx, [rbp+40h+var_B8]
0x18003d3aa  lea     rcx, [rbp+40h+var_60]; void *
0x18003d3ae  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d3b3  lea     rax, [rbp+40h+var_68]
0x18003d3b7  mov     [rsp+140h+var_110], rax; unsigned int *
0x18003d3bc  lea     rax, [rsp+140h+var_C8]
0x18003d3c1  mov     [rsp+140h+var_118], rax; unsigned __int8 **
0x18003d3c6  mov     edi, 2
0x18003d3cb  mov     dword ptr [rsp+140h+var_120], edi; unsigned int
0x18003d3cf  lea     r9, aUserid; "UserId"
0x18003d3d6  mov     r8, rbx; unsigned __int16 *
0x18003d3d9  xor     edx, edx; HKEY
0x18003d3db  lea     rcx, [rbp+40h+var_A0]; this
0x18003d3df  call    ?ReadBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; RegistryHelper::ReadBufferFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18003d3e4  test    eax, eax
0x18003d3e6  js      short loc_18003D43E
0x18003d3e8  mov     rdx, [rsp+140h+var_C8]
0x18003d3ed  lea     rcx, [rbp+40h+var_B0]
0x18003d3f1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18003d3f6  mov     rdx, [rbp+40h+var_B0]
0x18003d3fa  mov     rcx, [r15]
0x18003d3fd  call    cs:__imp__o__wcsicmp
0x18003d403  test    eax, eax
0x18003d405  jnz     short loc_18003D43E
0x18003d407  lea     r9, aUserticket; "UserTicket"
0x18003d40e  mov     r8, rbx; unsigned __int16 *
0x18003d411  mov     rdx, [rbp+40h+var_80]; HKEY
0x18003d415  lea     rcx, [rbp+40h+var_A0]; this
0x18003d419  call    ?DeleteBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryHelper::DeleteBufferFromRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003d41e  test    eax, eax
0x18003d420  jns     short loc_18003D43E
0x18003d422  mov     dword ptr [rsp+140h+var_120], eax
0x18003d426  lea     r9, aDeletebufferfr_0; "DeleteBufferFromRegistry failed = 0x%x"
0x18003d42d  mov     r8d, 58Dh; unsigned int
0x18003d433  mov     rdx, r13; char *
0x18003d436  mov     ecx, edi; unsigned __int8
0x18003d438  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003d43d  nop
0x18003d43e  lea     rcx, [rsp+140h+var_C8]
0x18003d443  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003d448  nop
0x18003d449  lea     rcx, [rbp+40h+var_C0]; void *
0x18003d44d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d452  inc     esi
0x18003d454  cmp     esi, [rsp+140h+var_D0]
0x18003d458  jb      loc_18003D2C4
0x18003d45e  jmp     short loc_18003D499
0x18003d460  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18003d467  mov     [rsp+140h+var_120], rcx; char *
0x18003d46c  mov     r9d, edi; int
0x18003d46f  mov     r8d, 581h; unsigned int
0x18003d475  lea     rdx, aIdentitystorag_15; "IdentityStorage::DeleteTicketsForUser"
0x18003d47c  mov     rcx, r13; char *
0x18003d47f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003d484  nop
0x18003d485  lea     rcx, [rsp+140h+var_C8]
0x18003d48a  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003d48f  nop
0x18003d490  lea     rcx, [rbp+40h+var_C0]; void *
0x18003d494  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d499  cmp     [rbp+40h+arg_10], 80070002h
0x18003d4a0  jz      short loc_18003D4AB
0x18003d4a2  cmp     [rbp+40h+arg_10], 800703FAh
0x18003d4a9  jnz     short loc_18003D4AF
0x18003d4ab  mov     [rbp+40h+arg_10], r12d
0x18003d4af  mov     ebx, [rbp+40h+arg_10]
0x18003d4b2  lea     rcx, [rbp+40h+var_58]
0x18003d4b6  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003d4bb  nop
0x18003d4bc  lea     rcx, [rbp+40h+var_B0]; void *
0x18003d4c0  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d4c5  nop
0x18003d4c6  lea     rcx, [rbp+40h+var_B8]; void *
0x18003d4ca  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d4cf  nop
0x18003d4d0  lea     rcx, [rbp+40h+var_A8]; void *
0x18003d4d4  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003d4d9  nop
0x18003d4da  lea     rcx, [rbp+40h+var_98]
0x18003d4de  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x18003d4e3  nop
0x18003d4e4  lea     rcx, [rbp+40h+var_80]
0x18003d4e8  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x18003d4ed  mov     eax, ebx
0x18003d4ef  mov     rbx, [rsp+140h+arg_8]
0x18003d4f7  add     rsp, 110h
0x18003d4fe  pop     r15
0x18003d500  pop     r14
0x18003d502  pop     r13
0x18003d504  pop     r12
0x18003d506  pop     rdi
0x18003d507  pop     rsi
0x18003d508  pop     rbp
0x18003d509  retn
```
