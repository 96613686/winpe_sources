# CWMCService::UpdateSharingStatus(void)

- ea: `0x140030cec`
- end: `0x140031043`
- name: `?UpdateSharingStatus@CWMCService@@AEAAXXZ`
- size: `855`
- prototype: `void __fastcall(CWMCService *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x140052250`

## callees

- `0x14000c920`
- `0x14000cb08`
- `0x1400106b0`
- `0x140011594`
- `0x14002f6dc`
- `0x140030cec`
- `0x14003104c`
- `0x14003510c`
- `0x1400391d0`
- `0x1400398e4`
- `0x14003f17c`
- `0x14004a834`
- `0x14005480c`
- `0x140055e30`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140030ee5`
- `KERNEL32!EnterCriticalSection` at `0x140030ee5`
- `KERNEL32!LeaveCriticalSection` at `0x140030fbe`
- `KERNEL32!LeaveCriticalSection` at `0x140030fbe`
- `ole32!CoCreateInstance` at `0x140030d63`
- `ole32!CoCreateInstance` at `0x140030e5c`
- `ole32!CoCreateInstance` at `0x140030d63`
- `ole32!CoCreateInstance` at `0x140030e5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CWMCService::UpdateSharingStatus(CWMCService *this)
{
  BOOL v2; // ebx
  HRESULT v3; // edi
  int v4; // edi
  const unsigned __int16 *v5; // rdx
  HRESULT Instance; // edi
  __int64 StartPosition; // rsi
  __int64 v8; // r9
  const unsigned __int16 **UserSID; // rax
  int i; // edi
  const unsigned __int16 **v11; // rax
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h]
  _BYTE v14[8]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+48h] BYREF
  struct INetFwPolicy2 *v17; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      256,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      *((unsigned int *)this + 19));
  }
  v2 = 0;
  ppv = 0;
  v3 = CoCreateInstance(
         &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
         0,
         1u,
         &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
         &ppv);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v3 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      257,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v3,
      ppv);
  }
  if ( v3 >= 0 )
  {
    LOWORD(v16) = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 96LL))(ppv, &v16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        258,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)v4);
    }
    if ( v4 >= 0 && (_WORD)v16 == 0xFFFF )
    {
      v17 = 0;
      Instance = CoCreateInstance(
                   &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
                   0,
                   1u,
                   &GUID_98325047_c671_4174_8d81_defcd3f03186,
                   (LPVOID *)&v17);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = (const unsigned __int16 *)(((Instance >> 31) & 0xFFFFFFFD) + 5);
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v5 )
          WPP_SF_dq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            259,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (unsigned int)Instance,
            v17);
      }
      if ( Instance >= 0 )
      {
        v16 = 0;
        if ( (int)IsRuleGroupEnabled(v17, v5, (int *)&v16) >= 0 )
        {
          if ( v16 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
            StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition((char *)this + 272);
            while ( StartPosition )
            {
              if ( v2 )
                break;
              StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::FindNextNode(
                                (char *)this + 272,
                                StartPosition);
              if ( **(_QWORD **)(v8 + 8) )
              {
                UserSID = (const unsigned __int16 **)CMediaServer::GetUserSID();
                CRendererDevicesDB::CRendererDevicesDB((CRendererDevicesDB *)v14, *UserSID);
                v12 = 0;
                v13 = 0;
                if ( !(unsigned int)CDevicesDB::GetAllIDs((CDevicesDB *)v14) )
                {
                  v16 = 0;
                  for ( i = 0; i < (int)v13; ++i )
                  {
                    if ( v2 )
                      break;
                    v11 = (const unsigned __int16 **)ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::operator[](
                                                       &v12,
                                                       (unsigned int)i);
                    if ( !(unsigned int)CDevicesDB::GetDeviceAuthorization((CDevicesDB *)v14, *v11, &v16) )
                      v2 = v16 == 1;
                  }
                }
                ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v12);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v15);
              }
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
          }
        }
      }
      if ( v17 )
        ((void (__fastcall *)(struct INetFwPolicy2 *))v17->lpVtbl->Release)(v17);
    }
  }
  *((_DWORD *)this + 19) = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v2);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x140030cec  push    rbp
0x140030cee  push    rbx
0x140030cef  push    rsi
0x140030cf0  push    rdi
0x140030cf1  push    r12
0x140030cf3  push    r14
0x140030cf5  push    r15
0x140030cf7  mov     rbp, rsp
0x140030cfa  sub     rsp, 50h
0x140030cfe  mov     r15, rcx
0x140030d01  lea     rax, WPP_GLOBAL_Control
0x140030d08  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140030d0f  mov     esi, 1
0x140030d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d1b  cmp     rcx, rax
0x140030d1e  jz      short loc_140030D41
0x140030d20  test    [rcx+1Ch], sil
0x140030d24  jz      short loc_140030D41
0x140030d26  cmp     byte ptr [rcx+19h], 5
0x140030d2a  jb      short loc_140030D41
0x140030d2c  mov     edx, 100h
0x140030d31  mov     r9d, [r15+4Ch]
0x140030d35  mov     r8, r12
0x140030d38  mov     rcx, [rcx+10h]
0x140030d3c  call    WPP_SF_d
0x140030d41  xor     ebx, ebx
0x140030d43  mov     [rbp+arg_18], rbx
0x140030d47  lea     rax, [rbp+arg_18]
0x140030d4b  mov     [rsp+50h+ppv], rax; ppv
0x140030d50  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x140030d57  mov     r8d, esi; dwClsContext
0x140030d5a  xor     edx, edx; pUnkOuter
0x140030d5c  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x140030d63  call    cs:__imp_CoCreateInstance
0x140030d69  mov     edi, eax
0x140030d6b  mov     r14b, 2
0x140030d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d75  lea     rax, WPP_GLOBAL_Control
0x140030d7c  cmp     rcx, rax
0x140030d7f  jz      short loc_140030DB7
0x140030d81  test    [rcx+1Ch], r14b
0x140030d85  jz      short loc_140030DB7
0x140030d87  mov     edx, edi
0x140030d89  sar     edx, 1Fh
0x140030d8c  and     edx, 0FFFFFFFDh
0x140030d8f  add     edx, 5
0x140030d92  movzx   eax, byte ptr [rcx+19h]
0x140030d96  cmp     eax, edx
0x140030d98  jb      short loc_140030DB7
0x140030d9a  mov     edx, 101h
0x140030d9f  mov     rax, [rbp+arg_18]
0x140030da3  mov     [rsp+50h+ppv], rax
0x140030da8  mov     r9d, edi
0x140030dab  mov     r8, r12
0x140030dae  mov     rcx, [rcx+10h]
0x140030db2  call    WPP_SF_dq
0x140030db7  test    edi, edi
0x140030db9  js      loc_140030FE6
0x140030dbf  xor     eax, eax
0x140030dc1  mov     word ptr [rbp+arg_8], ax
0x140030dc5  mov     rcx, [rbp+arg_18]
0x140030dc9  mov     rax, [rcx]
0x140030dcc  lea     rdx, [rbp+arg_8]
0x140030dd0  mov     rax, [rax+60h]
0x140030dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030dd9  mov     edi, eax
0x140030ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x140030de2  lea     rax, WPP_GLOBAL_Control
0x140030de9  cmp     rcx, rax
0x140030dec  jz      short loc_140030E23
0x140030dee  test    [rcx+1Ch], r14b
0x140030df2  jz      short loc_140030E23
0x140030df4  mov     edx, edi
0x140030df6  sar     edx, 1Fh
0x140030df9  and     edx, 0FFFFFFFDh
0x140030dfc  add     edx, 5
0x140030dff  movzx   eax, byte ptr [rcx+19h]
0x140030e03  cmp     eax, edx
0x140030e05  jb      short loc_140030E23
0x140030e07  movsx   eax, word ptr [rbp+arg_8]
0x140030e0b  mov     edx, 102h
0x140030e10  mov     dword ptr [rsp+50h+ppv], eax
0x140030e14  mov     r9d, edi
0x140030e17  mov     r8, r12
0x140030e1a  mov     rcx, [rcx+10h]
0x140030e1e  call    WPP_SF_Dd
0x140030e23  test    edi, edi
0x140030e25  js      loc_140030FE6
0x140030e2b  or      eax, 0FFFFFFFFh
0x140030e2e  cmp     ax, word ptr [rbp+arg_8]
0x140030e32  jnz     loc_140030FE6
0x140030e38  mov     [rbp+arg_10], 0
0x140030e40  lea     rax, [rbp+arg_10]
0x140030e44  mov     [rsp+50h+ppv], rax; ppv
0x140030e49  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x140030e50  mov     r8d, esi; dwClsContext
0x140030e53  xor     edx, edx; pUnkOuter
0x140030e55  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x140030e5c  call    cs:__imp_CoCreateInstance
0x140030e62  mov     edi, eax
0x140030e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e6b  lea     rax, WPP_GLOBAL_Control
0x140030e72  cmp     rcx, rax
0x140030e75  jz      short loc_140030EAD
0x140030e77  test    [rcx+1Ch], r14b
0x140030e7b  jz      short loc_140030EAD
0x140030e7d  mov     edx, edi
0x140030e7f  sar     edx, 1Fh
0x140030e82  and     edx, 0FFFFFFFDh
0x140030e85  add     edx, 5
0x140030e88  movzx   eax, byte ptr [rcx+19h]
0x140030e8c  cmp     eax, edx
0x140030e8e  jb      short loc_140030EAD
0x140030e90  mov     edx, 103h
0x140030e95  mov     rax, [rbp+arg_10]
0x140030e99  mov     [rsp+50h+ppv], rax
0x140030e9e  mov     r9d, edi
0x140030ea1  mov     r8, r12
0x140030ea4  mov     rcx, [rcx+10h]
0x140030ea8  call    WPP_SF_dq
0x140030ead  test    edi, edi
0x140030eaf  js      loc_140030FD0
0x140030eb5  mov     [rbp+arg_8], 0
0x140030ebc  lea     r8, [rbp+arg_8]; int *
0x140030ec0  mov     rcx, [rbp+arg_10]; struct INetFwPolicy2 *
0x140030ec4  call    ?IsRuleGroupEnabled@@YAJPEAUINetFwPolicy2@@PEBGPEAH@Z; IsRuleGroupEnabled(INetFwPolicy2 *,ushort const *,int *)
0x140030ec9  test    eax, eax
0x140030ecb  js      loc_140030FD0
0x140030ed1  cmp     [rbp+arg_8], 0
0x140030ed5  jz      loc_140030FD0
0x140030edb  lea     r14, [r15+0E8h]
0x140030ee2  mov     rcx, r14; lpCriticalSection
0x140030ee5  call    cs:__imp_EnterCriticalSection
0x140030eeb  lea     r12, [r15+110h]
0x140030ef2  mov     rcx, r12
0x140030ef5  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::GetStartPosition(void)
0x140030efa  mov     rsi, rax
0x140030efd  test    rax, rax
0x140030f00  jz      loc_140030FBB
0x140030f06  test    ebx, ebx
0x140030f08  jnz     loc_140030FBB
0x140030f0e  mov     r9, rsi
0x140030f11  mov     rdx, rsi
0x140030f14  mov     rcx, r12
0x140030f17  call    ?FindNextNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@AEBAPEAVCNode@12@PEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::FindNextNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::CNode *)
0x140030f1c  mov     rsi, rax
0x140030f1f  mov     rax, [r9+8]
0x140030f23  mov     rcx, [rax]
0x140030f26  test    rcx, rcx
0x140030f29  jz      loc_140030FB2
0x140030f2f  call    ?GetUserSID@CMediaServer@@QEAAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@XZ; CMediaServer::GetUserSID(void)
0x140030f34  mov     rdx, [rax]; unsigned __int16 *
0x140030f37  lea     rcx, [rbp+var_10]; this
0x140030f3b  call    ??0CRendererDevicesDB@@QEAA@PEBG@Z; CRendererDevicesDB::CRendererDevicesDB(ushort const *)
0x140030f40  nop
0x140030f41  mov     [rbp+var_20], 0
0x140030f49  mov     [rbp+var_18], 0
0x140030f51  lea     rdx, [rbp+var_20]
0x140030f55  lea     rcx, [rbp+var_10]; this
0x140030f59  call    ?GetAllIDs@CDevicesDB@@QEAAJAEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CDevicesDB::GetAllIDs(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x140030f5e  test    eax, eax
0x140030f60  jnz     short loc_140030F9F
0x140030f62  mov     [rbp+arg_8], eax
0x140030f65  xor     edi, edi
0x140030f67  cmp     dword ptr [rbp+var_18], edi
0x140030f6a  jle     short loc_140030F9F
0x140030f6c  test    ebx, ebx
0x140030f6e  jnz     short loc_140030F9F
0x140030f70  mov     edx, edi
0x140030f72  lea     rcx, [rbp+var_20]
0x140030f76  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x140030f7b  lea     r8, [rbp+arg_8]; unsigned int *
0x140030f7f  mov     rdx, [rax]; unsigned __int16 *
0x140030f82  lea     rcx, [rbp+var_10]; this
0x140030f86  call    ?GetDeviceAuthorization@CDevicesDB@@UEAAJPEBGAEAK@Z; CDevicesDB::GetDeviceAuthorization(ushort const *,ulong &)
0x140030f8b  test    eax, eax
0x140030f8d  lea     eax, [rbx+1]
0x140030f90  jnz     short loc_140030F98
0x140030f92  cmp     [rbp+arg_8], eax
0x140030f95  cmovz   ebx, eax
0x140030f98  add     edi, eax
0x140030f9a  cmp     edi, dword ptr [rbp+var_18]
0x140030f9d  jl      short loc_140030F6C
0x140030f9f  lea     rcx, [rbp+var_20]
0x140030fa3  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x140030fa8  nop
0x140030fa9  lea     rcx, [rbp+var_8]
0x140030fad  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140030fb2  test    rsi, rsi
0x140030fb5  jnz     loc_140030F06
0x140030fbb  mov     rcx, r14; lpCriticalSection
0x140030fbe  call    cs:__imp_LeaveCriticalSection
0x140030fc4  mov     esi, 1
0x140030fc9  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140030fd0  mov     rcx, [rbp+arg_10]
0x140030fd4  test    rcx, rcx
0x140030fd7  jz      short loc_140030FE6
0x140030fd9  mov     rax, [rcx]
0x140030fdc  mov     rax, [rax+10h]
0x140030fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030fe5  nop
0x140030fe6  mov     [r15+4Ch], ebx
0x140030fea  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ff1  lea     rax, WPP_GLOBAL_Control
0x140030ff8  cmp     rcx, rax
0x140030ffb  jz      short loc_14003101E
0x140030ffd  test    [rcx+1Ch], sil
0x140031001  jz      short loc_14003101E
0x140031003  cmp     byte ptr [rcx+19h], 5
0x140031007  jb      short loc_14003101E
0x140031009  mov     edx, 104h
0x14003100e  mov     r9d, ebx
0x140031011  mov     r8, r12
0x140031014  mov     rcx, [rcx+10h]
0x140031018  call    WPP_SF_d
0x14003101d  nop
0x14003101e  mov     rcx, [rbp+arg_18]
0x140031022  test    rcx, rcx
0x140031025  jz      short loc_140031034
0x140031027  mov     rax, [rcx]
0x14003102a  mov     rax, [rax+10h]
0x14003102e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031033  nop
0x140031034  add     rsp, 50h
0x140031038  pop     r15
0x14003103a  pop     r14
0x14003103c  pop     r12
0x14003103e  pop     rdi
0x14003103f  pop     rsi
0x140031040  pop     rbx
0x140031041  pop     rbp
0x140031042  retn
```
