# CDevicesDB::GetDeviceProperty(ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14000e3c8`
- end: `0x14000e5e2`
- name: `?GetDeviceProperty@CDevicesDB@@QEAAJPEBG0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(CDevicesDB *this)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000e848`
- `0x14000faac`
- `0x140043c90`

## callees

- `0x140003750`
- `0x1400065e0`
- `0x140006d70`
- `0x140007b94`
- `0x14000b3f0`
- `0x14000c920`
- `0x14000e3c8`
- `0x14000e5e8`
- `0x14000e660`
- `0x14003f17c`
- `0x140047798`
- `0x140054534`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000e5cb`
- `ADVAPI32!RegCloseKey` at `0x14000e5cb`
- `KERNEL32!CompareStringOrdinal` at `0x14000e485`
- `KERNEL32!CompareStringOrdinal` at `0x14000e485`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDevicesDB::GetDeviceProperty(CDevicesDB *this, char *a2, unsigned __int16 *a3, _QWORD *a4)
{
  unsigned __int16 *v8; // rbx
  unsigned int v9; // eax
  unsigned int StringValue; // edi
  _QWORD *v11; // rax
  PVOID *v12; // r10
  unsigned __int16 *v14; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3);
  }
  memset(hKey, 0, sizeof(hKey));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v14,
    a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::MakeUpper(&v14);
  v8 = v14;
  v9 = CDevicesDB::OpenRegKeyForRead(this, (struct ATL::CRegKey *)hKey, v14);
  StringValue = v9;
  if ( v9 )
  {
    if ( v9 == 2 )
      StringValue = (*(__int64 (__fastcall **)(CDevicesDB *, char *, unsigned __int16 *, _QWORD *))(*(_QWORD *)this
                                                                                                  + 64LL))(
                      this,
                      a2,
                      a3,
                      a4);
    goto LABEL_21;
  }
  if ( CompareStringOrdinal(a3, -1, L"FriendlyName", -1, 1) == 2 )
  {
    StringValue = GetStringValue((ATL::CRegKey *)hKey, L"CustomFriendlyName");
    if ( StringValue || !*(_DWORD *)(*a4 - 16LL) )
      StringValue = GetStringValue((ATL::CRegKey *)hKey, L"FriendlyName");
    if ( *(_DWORD *)(*a4 - 16LL) )
    {
      v11 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                        a4,
                        &v14,
                        128);
      ATL::CSimpleStringT<unsigned short,0>::operator=(a4, v11);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
    }
  }
  else
  {
    StringValue = GetStringValue((ATL::CRegKey *)hKey, a3);
  }
  if ( StringValue != 2 && *(_DWORD *)(*a4 - 16LL) )
  {
LABEL_21:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  StringValue = 1168;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_26;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids);
    goto LABEL_21;
  }
LABEL_22:
  if ( v12 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v12 + 28) & 1) != 0
    && *((unsigned __int8 *)v12 + 25) >= (unsigned int)(StringValue != 0 ? 2 : 5) )
  {
    WPP_SF_d(v12[2], 79, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, StringValue);
  }
LABEL_26:
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return StringValue;
}

```

## disassembly

```asm
0x14000e3c8  push    rbp
0x14000e3ca  push    rbx
0x14000e3cb  push    rsi
0x14000e3cc  push    rdi
0x14000e3cd  push    r12
0x14000e3cf  push    r14
0x14000e3d1  push    r15
0x14000e3d3  mov     rbp, rsp
0x14000e3d6  sub     rsp, 50h
0x14000e3da  mov     rsi, r9
0x14000e3dd  mov     r14, r8
0x14000e3e0  mov     r15, rdx
0x14000e3e3  mov     r12, rcx
0x14000e3e6  lea     rax, WPP_GLOBAL_Control
0x14000e3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3f4  cmp     rcx, rax
0x14000e3f7  jz      short loc_14000E422
0x14000e3f9  test    byte ptr [rcx+1Ch], 1
0x14000e3fd  jz      short loc_14000E422
0x14000e3ff  cmp     byte ptr [rcx+19h], 5
0x14000e403  jb      short loc_14000E422
0x14000e405  mov     edx, 4Dh ; 'M'
0x14000e40a  mov     qword ptr [rsp+50h+bIgnoreCase], r8; __int64
0x14000e40f  mov     r9, r15
0x14000e412  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000e419  mov     rcx, [rcx+10h]; LoggerHandle
0x14000e41d  call    WPP_SF_SS
0x14000e422  mov     [rbp+hKey], 0
0x14000e42a  mov     [rbp+var_10], 0
0x14000e432  mov     [rbp+var_8], 0
0x14000e43a  mov     rdx, r15
0x14000e43d  lea     rcx, [rbp+var_20]
0x14000e441  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14000e446  nop
0x14000e447  lea     rcx, [rbp+var_20]
0x14000e44b  call    ?MakeUpper@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::MakeUpper(void)
0x14000e450  mov     rbx, [rbp+var_20]
0x14000e454  mov     r8, rbx; unsigned __int16 *
0x14000e457  lea     rdx, [rbp+hKey]; struct ATL::CRegKey *
0x14000e45b  mov     rcx, r12; this
0x14000e45e  call    ?OpenRegKeyForRead@CDevicesDB@@AEAAJAEAVCRegKey@ATL@@PEBG@Z; CDevicesDB::OpenRegKeyForRead(ATL::CRegKey &,ushort const *)
0x14000e463  mov     edi, eax
0x14000e465  test    eax, eax
0x14000e467  jnz     loc_14000E550
0x14000e46d  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x14000e475  or      edx, 0FFFFFFFFh; cchCount1
0x14000e478  mov     r9d, edx; cchCount2
0x14000e47b  lea     r8, aFriendlyname_0; "FriendlyName"
0x14000e482  mov     rcx, r14; lpString1
0x14000e485  call    cs:__imp_CompareStringOrdinal
0x14000e48b  mov     r8, rsi
0x14000e48e  lea     rcx, [rbp+hKey]; this
0x14000e492  cmp     eax, 2
0x14000e495  jnz     short loc_14000E4F7
0x14000e497  lea     rdx, aCustomfriendly; "CustomFriendlyName"
0x14000e49e  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14000e4a3  mov     edi, eax
0x14000e4a5  test    eax, eax
0x14000e4a7  jnz     short loc_14000E4B1
0x14000e4a9  mov     rax, [rsi]
0x14000e4ac  cmp     [rax-10h], edi
0x14000e4af  jnz     short loc_14000E4C6
0x14000e4b1  mov     r8, rsi
0x14000e4b4  lea     rdx, aFriendlyname_0; "FriendlyName"
0x14000e4bb  lea     rcx, [rbp+hKey]; this
0x14000e4bf  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14000e4c4  mov     edi, eax
0x14000e4c6  mov     rax, [rsi]
0x14000e4c9  cmp     dword ptr [rax-10h], 0
0x14000e4cd  jz      short loc_14000E501
0x14000e4cf  mov     r8d, 80h
0x14000e4d5  lea     rdx, [rbp+var_20]
0x14000e4d9  mov     rcx, rsi
0x14000e4dc  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x14000e4e1  mov     rdx, rax
0x14000e4e4  mov     rcx, rsi
0x14000e4e7  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14000e4ec  lea     rcx, [rbp+var_20]
0x14000e4f0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000e4f5  jmp     short loc_14000E501
0x14000e4f7  mov     rdx, r14; unsigned __int16 *
0x14000e4fa  call    ?GetStringValue@@YAJAEAVCRegKey@ATL@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; GetStringValue(ATL::CRegKey &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14000e4ff  mov     edi, eax
0x14000e501  cmp     edi, 2
0x14000e504  jz      short loc_14000E50F
0x14000e506  mov     rax, [rsi]
0x14000e509  cmp     dword ptr [rax-10h], 0
0x14000e50d  jnz     short loc_14000E570
0x14000e50f  mov     edi, 490h
0x14000e514  mov     r10, cs:WPP_GLOBAL_Control
0x14000e51b  lea     rsi, WPP_GLOBAL_Control
0x14000e522  cmp     r10, rsi
0x14000e525  jz      loc_14000E5B8
0x14000e52b  test    byte ptr [r10+1Ch], 2
0x14000e530  jz      short loc_14000E57E
0x14000e532  cmp     byte ptr [r10+19h], 4
0x14000e537  jb      short loc_14000E57E
0x14000e539  mov     edx, 4Eh ; 'N'
0x14000e53e  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000e545  mov     rcx, [r10+10h]
0x14000e549  call    WPP_SF_
0x14000e54e  jmp     short loc_14000E577
0x14000e550  cmp     eax, 2
0x14000e553  jnz     short loc_14000E570
0x14000e555  mov     rax, [r12]
0x14000e559  mov     r9, rsi
0x14000e55c  mov     r8, r14
0x14000e55f  mov     rdx, r15
0x14000e562  mov     rcx, r12
0x14000e565  mov     rax, [rax+40h]
0x14000e569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e56e  mov     edi, eax
0x14000e570  lea     rsi, WPP_GLOBAL_Control
0x14000e577  mov     r10, cs:WPP_GLOBAL_Control
0x14000e57e  cmp     r10, rsi
0x14000e581  jz      short loc_14000E5B8
0x14000e583  test    byte ptr [r10+1Ch], 1
0x14000e588  jz      short loc_14000E5B8
0x14000e58a  movzx   edx, byte ptr [r10+19h]
0x14000e58f  mov     eax, edi
0x14000e591  neg     eax
0x14000e593  sbb     ecx, ecx
0x14000e595  and     ecx, 0FFFFFFFDh
0x14000e598  add     ecx, 5
0x14000e59b  cmp     edx, ecx
0x14000e59d  jb      short loc_14000E5B8
0x14000e59f  mov     edx, 4Fh ; 'O'
0x14000e5a4  mov     r9d, edi
0x14000e5a7  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000e5ae  mov     rcx, [r10+10h]
0x14000e5b2  call    WPP_SF_d
0x14000e5b7  nop
0x14000e5b8  lea     rcx, [rbx-18h]; this
0x14000e5bc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000e5c1  nop
0x14000e5c2  mov     rcx, [rbp+hKey]; hKey
0x14000e5c6  test    rcx, rcx
0x14000e5c9  jz      short loc_14000E5D1
0x14000e5cb  call    cs:__imp_RegCloseKey
0x14000e5d1  mov     eax, edi
0x14000e5d3  add     rsp, 50h
0x14000e5d7  pop     r15
0x14000e5d9  pop     r14
0x14000e5db  pop     r12
0x14000e5dd  pop     rdi
0x14000e5de  pop     rsi
0x14000e5df  pop     rbx
0x14000e5e0  pop     rbp
0x14000e5e1  retn
```
