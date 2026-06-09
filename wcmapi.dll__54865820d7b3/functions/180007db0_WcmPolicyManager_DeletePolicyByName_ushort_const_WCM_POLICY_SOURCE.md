# WcmPolicyManager::DeletePolicyByName(ushort const *,WCM_POLICY_SOURCE)

- ea: `0x180007db0`
- end: `0x180007ffb`
- name: `?DeletePolicyByName@WcmPolicyManager@@UEAAJPEBGW4WCM_POLICY_SOURCE@@@Z`
- size: `587`
- prototype: `int __high(const unsigned __int16 *, enum WCM_POLICY_SOURCE)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800060e8`
- `0x1800075e8`
- `0x180007db0`
- `0x1800085c8`
- `0x180017a60`
- `0x180017b50`
- `0x180017cb0`
- `0x180017dac`
- `0x18001aa44`

## string_xrefs

- `0x180007dee`: `WcmPolicyManager::DeletePolicyByName`
- `0x180007fb4`: `WcmPolicyManager::DeletePolicyByName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WcmPolicyManager::DeletePolicyByName(__int64 a1, const WCHAR *a2, int a3)
{
  int PolicySourceRegKey; // edi
  WcmPolicyManager *v6; // rcx
  int v7; // esi
  int v9; // [rsp+34h] [rbp-54h]
  HKEY hKey[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v11; // [rsp+48h] [rbp-40h]
  __int128 v12; // [rsp+50h] [rbp-38h] BYREF
  __int64 v13; // [rsp+60h] [rbp-28h]

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      "WcmPolicyManager::DeletePolicyByName");
  }
  hKey[0] = 0;
  hKey[1] = 0;
  v11 = 0;
  v12 = 0u;
  v13 = 0;
  v9 = 0;
  PolicySourceRegKey = OpenOrCreatePolicySourceRegKey(a3, (ATL::CRegKey *)hKey, 0);
  if ( PolicySourceRegKey < 0 )
  {
    PolicySourceRegKey = 0;
    v6 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)&v12, hKey[0], a2, 0xF003Fu) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
        (_DWORD)a2,
        a3);
      v6 = WPP_GLOBAL_Control;
    }
    goto LABEL_26;
  }
  v7 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a2);
  if ( !v7 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
        (_DWORD)a2,
        a3);
      v6 = WPP_GLOBAL_Control;
    }
    v9 = 1;
LABEL_26:
    if ( v9 )
    {
      WcmPolicyManager::SignalPolicyChange(v6);
      v6 = WPP_GLOBAL_Control;
    }
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, a3);
  }
  if ( v7 > 0 )
    PolicySourceRegKey = (unsigned __int16)v7 | 0x80070000;
  else
    PolicySourceRegKey = v7;
  ReportApplicationError(v7, 0x119u);
  v6 = WPP_GLOBAL_Control;
LABEL_28:
  if ( v6 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 5u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v6 + 2),
      28,
      (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      (unsigned int)"WcmPolicyManager::DeletePolicyByName",
      PolicySourceRegKey);
  ATL::CRegKey::Close((ATL::CRegKey *)&v12);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)PolicySourceRegKey;
}

```

## disassembly

```asm
0x180007db0  mov     [rsp+arg_0], rsi
0x180007db5  mov     [rsp+arg_18], rdi
0x180007dba  push    r12
0x180007dbc  push    r14
0x180007dbe  push    r15
0x180007dc0  sub     rsp, 70h
0x180007dc4  mov     r12d, r8d
0x180007dc7  mov     r15, rdx
0x180007dca  lea     r14, WPP_GLOBAL_Control
0x180007dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd8  cmp     rcx, r14
0x180007ddb  jz      short loc_180007E05
0x180007ddd  cmp     byte ptr [rcx+19h], 5
0x180007de1  jb      short loc_180007E05
0x180007de3  test    byte ptr [rcx+1Ch], 1
0x180007de7  jz      short loc_180007E05
0x180007de9  mov     edx, 18h
0x180007dee  lea     r9, aWcmpolicymanag_1; "WcmPolicyManager::DeletePolicyByName"
0x180007df5  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180007dfc  mov     rcx, [rcx+10h]
0x180007e00  call    WPP_SF_s
0x180007e05  xorps   xmm0, xmm0
0x180007e08  xor     eax, eax
0x180007e0a  movups  xmmword ptr [rsp+88h+hKey], xmm0
0x180007e0f  mov     [rsp+88h+hKey], rax
0x180007e14  mov     [rsp+88h+hKey+8], rax
0x180007e19  mov     [rsp+88h+var_40], rax
0x180007e1e  movups  [rsp+88h+var_38], xmm0
0x180007e23  mov     qword ptr [rsp+88h+var_38], rax
0x180007e28  mov     qword ptr [rsp+88h+var_38+8], rax
0x180007e2d  mov     [rsp+88h+var_28], rax
0x180007e32  mov     [rsp+88h+var_54], eax
0x180007e36  xor     r8d, r8d
0x180007e39  lea     rdx, [rsp+88h+hKey]
0x180007e3e  mov     ecx, r12d
0x180007e41  call    ?OpenOrCreatePolicySourceRegKey@@YAJW4WCM_POLICY_SOURCE@@AEAVCRegKey@ATL@@H@Z; OpenOrCreatePolicySourceRegKey(WCM_POLICY_SOURCE,ATL::CRegKey &,int)
0x180007e46  mov     edi, eax
0x180007e48  test    eax, eax
0x180007e4a  jns     short loc_180007E5A
0x180007e4c  xor     edi, edi
0x180007e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e55  jmp     loc_180007F9A
0x180007e5a  mov     r9d, 0F003Fh; unsigned int
0x180007e60  mov     r8, r15; lpSubKey
0x180007e63  mov     rdx, [rsp+88h+hKey]; hKey
0x180007e68  lea     rcx, [rsp+88h+var_38]; this
0x180007e6d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007e72  test    eax, eax
0x180007e74  jnz     loc_180007F35
0x180007e7a  mov     rdx, r15; unsigned __int16 *
0x180007e7d  lea     rcx, [rsp+88h+hKey]; this
0x180007e82  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007e87  mov     esi, eax
0x180007e89  test    eax, eax
0x180007e8b  jnz     short loc_180007ED4
0x180007e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e94  cmp     rcx, r14
0x180007e97  jz      short loc_180007EC7
0x180007e99  cmp     byte ptr [rcx+19h], 4
0x180007e9d  jb      short loc_180007EC7
0x180007e9f  test    byte ptr [rcx+1Ch], 1
0x180007ea3  jz      short loc_180007EC7
0x180007ea5  lea     edx, [rax+19h]
0x180007ea8  mov     dword ptr [rsp+88h+var_68], r12d
0x180007ead  mov     r9, r15
0x180007eb0  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180007eb7  mov     rcx, [rcx+10h]
0x180007ebb  call    WPP_SF_SD
0x180007ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ec7  mov     [rsp+88h+var_54], 1
0x180007ecf  jmp     loc_180007F71
0x180007ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007edb  cmp     rcx, r14
0x180007ede  jz      short loc_180007F0E
0x180007ee0  cmp     byte ptr [rcx+19h], 1
0x180007ee4  jb      short loc_180007F0E
0x180007ee6  test    byte ptr [rcx+1Ch], 1
0x180007eea  jz      short loc_180007F0E
0x180007eec  mov     edx, 1Ah
0x180007ef1  mov     dword ptr [rsp+88h+var_60], r12d; char
0x180007ef6  mov     [rsp+88h+var_68], r15; __int64
0x180007efb  mov     r9d, esi
0x180007efe  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180007f05  mov     rcx, [rcx+10h]; LoggerHandle
0x180007f09  call    WPP_SF_DSD
0x180007f0e  test    esi, esi
0x180007f10  jg      short loc_180007F16
0x180007f12  mov     edi, esi
0x180007f14  jmp     short loc_180007F1F
0x180007f16  movzx   edi, si
0x180007f19  or      edi, 80070000h
0x180007f1f  mov     edx, 119h; unsigned int
0x180007f24  mov     ecx, esi; int
0x180007f26  call    ?ReportApplicationError@@YAXJK@Z; ReportApplicationError(long,ulong)
0x180007f2b  nop
0x180007f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f33  jmp     short loc_180007F9A
0x180007f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f3c  cmp     rcx, r14
0x180007f3f  jz      short loc_180007F71
0x180007f41  cmp     byte ptr [rcx+19h], 4
0x180007f45  jb      short loc_180007F71
0x180007f47  test    byte ptr [rcx+1Ch], 1
0x180007f4b  jz      short loc_180007F71
0x180007f4d  mov     edx, 1Bh
0x180007f52  mov     dword ptr [rsp+88h+var_68], r12d
0x180007f57  mov     r9, r15
0x180007f5a  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180007f61  mov     rcx, [rcx+10h]
0x180007f65  call    WPP_SF_SD
0x180007f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f71  jmp     short loc_180007F87
0x180007f73  jmp     short $+2
0x180007f75  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180007f7c  mov     edi, [rsp+88h+var_58]
0x180007f80  lea     r14, WPP_GLOBAL_Control
0x180007f87  cmp     [rsp+88h+var_54], 0
0x180007f8c  jz      short loc_180007F9A
0x180007f8e  call    ?SignalPolicyChange@WcmPolicyManager@@AEAAXXZ; WcmPolicyManager::SignalPolicyChange(void)
0x180007f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f9a  cmp     rcx, r14
0x180007f9d  jz      short loc_180007FCC
0x180007f9f  cmp     byte ptr [rcx+19h], 5
0x180007fa3  jb      short loc_180007FCC
0x180007fa5  test    byte ptr [rcx+1Ch], 1
0x180007fa9  jz      short loc_180007FCC
0x180007fab  mov     edx, 1Ch
0x180007fb0  mov     dword ptr [rsp+88h+var_68], edi
0x180007fb4  lea     r9, aWcmpolicymanag_1; "WcmPolicyManager::DeletePolicyByName"
0x180007fbb  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180007fc2  mov     rcx, [rcx+10h]
0x180007fc6  call    WPP_SF_sL
0x180007fcb  nop
0x180007fcc  lea     rcx, [rsp+88h+var_38]; this
0x180007fd1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007fd6  nop
0x180007fd7  lea     rcx, [rsp+88h+hKey]; this
0x180007fdc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007fe1  mov     eax, edi
0x180007fe3  lea     r11, [rsp+88h+var_18]
0x180007fe8  mov     rsi, [r11+20h]
0x180007fec  mov     rdi, [r11+38h]
0x180007ff0  mov     rsp, r11
0x180007ff3  pop     r15
0x180007ff5  pop     r14
0x180007ff7  pop     r12
0x180007ff9  retn
```
