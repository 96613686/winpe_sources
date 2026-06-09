# CWMCService::IsWMPNSSContextCurrentlyEnabled(void)

- ea: `0x14004f094`
- end: `0x14004f2d8`
- name: `?IsWMPNSSContextCurrentlyEnabled@CWMCService@@QEAAHXZ`
- size: `580`
- prototype: `__int64 __fastcall(CWMCService *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140043c90`
- `0x140068f70`

## callees

- `0x140008eac`
- `0x14003104c`
- `0x1400329d4`
- `0x140032eec`
- `0x14003bf64`
- `0x14003f17c`
- `0x140047798`
- `0x14004aa4c`
- `0x14004af64`
- `0x14004f094`
- `0x14005480c`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x14004f182`
- `KERNEL32!GetTickCount64` at `0x14004f23a`
- `KERNEL32!GetTickCount64` at `0x14004f182`
- `KERNEL32!GetTickCount64` at `0x14004f23a`
- `ole32!CoCreateInstance` at `0x14004f1ce`
- `ole32!CoCreateInstance` at `0x14004f1ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWMCService::IsWMPNSSContextCurrentlyEnabled(CWMCService *this)
{
  CNTService *v1; // rdi
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // rdx
  struct INetFwPolicy2 **v4; // rsi
  HRESULT Instance; // eax
  struct INetFwPolicy2 *v6; // rcx
  _BYTE v8[16]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v9[5]; // [rsp+40h] [rbp-28h] BYREF
  CWMCService *v10; // [rsp+A0h] [rbp+38h] BYREF

  v10 = this;
  v1 = g_WMCService;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  v2 = 1;
  memset(v9, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v9,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0",
                       0x20119u)
    || (LODWORD(v10) = 0,
        (unsigned int)ATL::CRegKey::QueryDWORDValue(
                        (ATL::CRegKey *)v9,
                        L"SkipFirewallCheckOnUPnPAction",
                        (unsigned int *)&v10)) )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      (__int64)v8,
      (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 648));
    if ( GetTickCount64() - *((_QWORD *)v1 + 88) >= g_dwMillisecondsToCacheFirewallStatus )
    {
      v4 = (struct INetFwPolicy2 **)((char *)v1 + 688);
      if ( !*((_QWORD *)v1 + 86) )
      {
        Instance = CoCreateInstance(
                     &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
                     0,
                     1u,
                     &GUID_98325047_c671_4174_8d81_defcd3f03186,
                     (LPVOID *)v1 + 86);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v3 = (const unsigned __int16 *)(((Instance >> 31) & 0xFFFFFFFD) + 5);
          if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v3 )
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              79,
              &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
              (unsigned int)Instance,
              *v4);
        }
      }
      v6 = *v4;
      if ( *v4 )
      {
        LODWORD(v10) = 0;
        if ( (int)IsRuleGroupEnabled(v6, v3, (int *)&v10) >= 0 )
          v2 = (_DWORD)v10 != 0;
        *((_QWORD *)v1 + 88) = GetTickCount64();
        *((_DWORD *)v1 + 174) = v2;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v2);
        }
      }
    }
    else
    {
      v2 = *((_DWORD *)v1 + 174);
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v8);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  }
  MyInterlockedExchangeMax64((volatile unsigned __int64 *)v1 + 14, *((_QWORD *)v1 + 88));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v2);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v9);
  return v2;
}

```

## disassembly

```asm
0x14004f094  mov     [rsp-30h+arg_0], rcx
0x14004f099  push    rbp
0x14004f09a  push    rbx
0x14004f09b  push    rsi
0x14004f09c  push    rdi
0x14004f09d  push    r12
0x14004f09f  push    r15
0x14004f0a1  mov     rbp, rsp
0x14004f0a4  sub     rsp, 68h
0x14004f0a8  mov     rdi, cs:g_WMCService
0x14004f0af  lea     r12, WPP_GLOBAL_Control
0x14004f0b6  lea     r15, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004f0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f0c4  cmp     rcx, r12
0x14004f0c7  jz      short loc_14004F0E0
0x14004f0c9  test    byte ptr [rcx+1Ch], 1
0x14004f0cd  jz      short loc_14004F0E0
0x14004f0cf  mov     edx, 4Dh ; 'M'
0x14004f0d4  mov     r8, r15
0x14004f0d7  mov     rcx, [rcx+10h]
0x14004f0db  call    WPP_SF_
0x14004f0e0  mov     ebx, 1
0x14004f0e5  mov     [rbp+var_28], 0
0x14004f0ed  mov     [rbp+var_20], 0
0x14004f0f5  mov     [rbp+var_18], 0
0x14004f0fd  mov     r9d, 20119h; unsigned int
0x14004f103  lea     r8, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x14004f10a  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14004f111  lea     rcx, [rbp+var_28]; this
0x14004f115  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14004f11a  test    eax, eax
0x14004f11c  jnz     short loc_14004F171
0x14004f11e  mov     dword ptr [rbp+arg_0], eax
0x14004f121  lea     r8, [rbp+arg_0]; unsigned int *
0x14004f125  lea     rdx, aSkipfirewallch; "SkipFirewallCheckOnUPnPAction"
0x14004f12c  lea     rcx, [rbp+var_28]; this
0x14004f130  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14004f135  test    eax, eax
0x14004f137  jnz     short loc_14004F171
0x14004f139  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f140  cmp     rcx, r12
0x14004f143  jz      loc_14004F283
0x14004f149  test    byte ptr [rcx+1Ch], 2
0x14004f14d  jz      loc_14004F283
0x14004f153  cmp     byte ptr [rcx+19h], 5
0x14004f157  jb      loc_14004F283
0x14004f15d  lea     edx, [rbx+4Dh]
0x14004f160  mov     r8, r15
0x14004f163  mov     rcx, [rcx+10h]
0x14004f167  call    WPP_SF_
0x14004f16c  jmp     loc_14004F283
0x14004f171  lea     rdx, [rdi+288h]
0x14004f178  lea     rcx, [rbp+var_38]
0x14004f17c  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x14004f181  nop
0x14004f182  call    cs:__imp_GetTickCount64
0x14004f188  mov     rcx, rax
0x14004f18b  sub     rcx, [rdi+2C0h]
0x14004f192  mov     eax, cs:?g_dwMillisecondsToCacheFirewallStatus@@3KA; ulong g_dwMillisecondsToCacheFirewallStatus
0x14004f198  cmp     rcx, rax
0x14004f19b  jnb     short loc_14004F1A8
0x14004f19d  mov     ebx, [rdi+2B8h]
0x14004f1a3  jmp     loc_14004F27A
0x14004f1a8  lea     rsi, [rdi+2B0h]
0x14004f1af  cmp     qword ptr [rsi], 0
0x14004f1b3  jnz     short loc_14004F215
0x14004f1b5  mov     [rsp+68h+ppv], rsi; ppv
0x14004f1ba  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x14004f1c1  xor     edx, edx; pUnkOuter
0x14004f1c3  lea     r8d, [rdx+1]; dwClsContext
0x14004f1c7  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x14004f1ce  call    cs:__imp_CoCreateInstance
0x14004f1d4  mov     r9d, eax
0x14004f1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f1de  cmp     rcx, r12
0x14004f1e1  jz      short loc_14004F215
0x14004f1e3  test    byte ptr [rcx+1Ch], 2
0x14004f1e7  jz      short loc_14004F215
0x14004f1e9  mov     edx, eax
0x14004f1eb  sar     edx, 1Fh
0x14004f1ee  and     edx, 0FFFFFFFDh
0x14004f1f1  add     edx, 5
0x14004f1f4  movzx   eax, byte ptr [rcx+19h]
0x14004f1f8  cmp     eax, edx
0x14004f1fa  jb      short loc_14004F215
0x14004f1fc  mov     edx, 4Fh ; 'O'
0x14004f201  mov     rax, [rsi]
0x14004f204  mov     [rsp+68h+ppv], rax
0x14004f209  mov     r8, r15
0x14004f20c  mov     rcx, [rcx+10h]
0x14004f210  call    WPP_SF_dq
0x14004f215  mov     rcx, [rsi]; struct INetFwPolicy2 *
0x14004f218  test    rcx, rcx
0x14004f21b  jz      short loc_14004F27A
0x14004f21d  mov     dword ptr [rbp+arg_0], 0
0x14004f224  lea     r8, [rbp+arg_0]; int *
0x14004f228  call    ?IsRuleGroupEnabled@@YAJPEAUINetFwPolicy2@@PEBGPEAH@Z; IsRuleGroupEnabled(INetFwPolicy2 *,ushort const *,int *)
0x14004f22d  test    eax, eax
0x14004f22f  js      short loc_14004F23A
0x14004f231  mov     eax, dword ptr [rbp+arg_0]
0x14004f234  neg     eax
0x14004f236  sbb     ecx, ecx
0x14004f238  and     ebx, ecx
0x14004f23a  call    cs:__imp_GetTickCount64
0x14004f240  mov     [rdi+2C0h], rax
0x14004f247  mov     [rdi+2B8h], ebx
0x14004f24d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f254  cmp     rcx, r12
0x14004f257  jz      short loc_14004F27A
0x14004f259  test    byte ptr [rcx+1Ch], 2
0x14004f25d  jz      short loc_14004F27A
0x14004f25f  cmp     byte ptr [rcx+19h], 5
0x14004f263  jb      short loc_14004F27A
0x14004f265  mov     edx, 50h ; 'P'
0x14004f26a  mov     r9d, ebx
0x14004f26d  mov     r8, r15
0x14004f270  mov     rcx, [rcx+10h]
0x14004f274  call    WPP_SF_d
0x14004f279  nop
0x14004f27a  lea     rcx, [rbp+var_38]
0x14004f27e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x14004f283  lea     rcx, [rdi+70h]; volatile unsigned __int64 *
0x14004f287  mov     rdx, [rdi+2C0h]; unsigned __int64
0x14004f28e  call    ?MyInterlockedExchangeMax64@@YA_KPEC_K_K@Z; MyInterlockedExchangeMax64(unsigned __int64 volatile *,unsigned __int64)
0x14004f293  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f29a  cmp     rcx, r12
0x14004f29d  jz      short loc_14004F2C0
0x14004f29f  test    byte ptr [rcx+1Ch], 1
0x14004f2a3  jz      short loc_14004F2C0
0x14004f2a5  cmp     byte ptr [rcx+19h], 5
0x14004f2a9  jb      short loc_14004F2C0
0x14004f2ab  mov     edx, 51h ; 'Q'
0x14004f2b0  mov     r9d, ebx
0x14004f2b3  mov     r8, r15
0x14004f2b6  mov     rcx, [rcx+10h]
0x14004f2ba  call    WPP_SF_d
0x14004f2bf  nop
0x14004f2c0  lea     rcx, [rbp+var_28]; this
0x14004f2c4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004f2c9  mov     eax, ebx
0x14004f2cb  add     rsp, 68h
0x14004f2cf  pop     r15
0x14004f2d1  pop     r12
0x14004f2d3  pop     rdi
0x14004f2d4  pop     rsi
0x14004f2d5  pop     rbx
0x14004f2d6  pop     rbp
0x14004f2d7  retn
```
