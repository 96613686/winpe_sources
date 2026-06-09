# WcmPolicyManager::DeletePolicyByKey(IWcmConnectionMappingPolicyKey *,WCM_POLICY_SOURCE)

- ea: `0x180006750`
- end: `0x180006b04`
- name: `?DeletePolicyByKey@WcmPolicyManager@@UEAAJPEAUIWcmConnectionMappingPolicyKey@@W4WCM_POLICY_SOURCE@@@Z`
- size: `948`
- prototype: `int __high(struct IWcmConnectionMappingPolicyKey *, enum WCM_POLICY_SOURCE)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800060e8`
- `0x180006750`
- `0x180006b0c`
- `0x1800075e8`
- `0x180007754`
- `0x180008a90`
- `0x18000953c`
- `0x180017664`
- `0x180017a60`
- `0x180017b50`
- `0x180017cb0`
- `0x180017d3c`
- `0x180017dac`
- `0x180017f7c`
- `0x180018594`
- `0x180018624`
- `0x18001aa44`

## string_xrefs

- `0x1800067a6`: `WcmPolicyManager::DeletePolicyByKey`
- `0x180006aab`: `WcmPolicyManager::DeletePolicyByKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=2
__int64 __fastcall WcmPolicyManager::DeletePolicyByKey(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // r15d
  int PolicySourceRegKey; // ebx
  unsigned int v7; // eax
  int v8; // esi
  int v9; // eax
  WcmPolicyManager *v10; // rcx
  struct _FILETIME *v12; // [rsp+20h] [rbp-308h]
  int v13; // [rsp+34h] [rbp-2F4h]
  HKEY hKey[2]; // [rsp+40h] [rbp-2E8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-2D8h]
  __int128 v16; // [rsp+58h] [rbp-2D0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-2C0h]
  unsigned int v18[4]; // [rsp+70h] [rbp-2B8h] BYREF
  _BYTE v19[112]; // [rsp+80h] [rbp-2A8h] BYREF
  WCHAR SubKey[256]; // [rsp+F0h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      "WcmPolicyManager::DeletePolicyByKey");
  }
  hKey[0] = 0;
  hKey[1] = 0;
  v15 = 0;
  v16 = 0u;
  v17 = 0;
  v13 = 0;
  v5 = 0;
  PolicySourceRegKey = OpenOrCreatePolicySourceRegKey(a3, hKey, 0);
  if ( PolicySourceRegKey < 0 )
  {
    PolicySourceRegKey = 0;
    goto LABEL_48;
  }
  while ( 1 )
  {
    memset_0(SubKey, 0, 0x1FEu);
    v18[0] = 255;
    WcmConnectionMappingPolicyKey::WcmConnectionMappingPolicyKey((WcmConnectionMappingPolicyKey *)v19);
    v7 = ATL::CRegKey::EnumKey((ATL::CRegKey *)hKey, v5, SubKey, v18, v12);
    v8 = v7;
    if ( v7 == 259 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids, a3, v5);
      }
      goto LABEL_44;
    }
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids, v7, v5);
      }
      if ( v8 <= 0 )
      {
        PolicySourceRegKey = v8;
        goto LABEL_44;
      }
      PolicySourceRegKey = (unsigned __int16)v8;
      goto LABEL_20;
    }
    PolicySourceRegKey = ATL::CRegKey::Open((ATL::CRegKey *)&v16, hKey[0], SubKey, 0x20019u);
    if ( PolicySourceRegKey )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)SubKey, a3);
      }
      if ( PolicySourceRegKey <= 0 )
        goto LABEL_44;
      PolicySourceRegKey = (unsigned __int16)PolicySourceRegKey;
LABEL_20:
      PolicySourceRegKey |= 0x80070000;
      goto LABEL_44;
    }
    PolicySourceRegKey = WcmConnectionMappingPolicyKey::ReadFromRegistry(
                           (WcmConnectionMappingPolicyKey *)v19,
                           (struct ATL::CRegKey *)&v16);
    if ( PolicySourceRegKey < 0 )
      goto LABEL_44;
    if ( (unsigned __int8)WcmConnectionMappingPolicyKey::operator==(a2, v19) )
      break;
    ++v5;
    WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey((WcmConnectionMappingPolicyKey *)v19);
  }
  v9 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, SubKey);
  if ( v9 )
  {
    if ( v9 > 0 )
      PolicySourceRegKey = (unsigned __int16)v9 | 0x80070000;
    else
      PolicySourceRegKey = v9;
  }
  if ( PolicySourceRegKey < 0 )
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)SubKey, a3);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
        (unsigned int)SubKey,
        a3);
    }
    v13 = 1;
  }
LABEL_44:
  WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey((WcmConnectionMappingPolicyKey *)v19);
  if ( v13 )
    WcmPolicyManager::SignalPolicyChange(v10);
LABEL_48:
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      (unsigned int)"WcmPolicyManager::DeletePolicyByKey",
      PolicySourceRegKey);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)&v16);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)PolicySourceRegKey;
}

```

## disassembly

```asm
0x180006750  mov     [rsp+arg_0], rbx
0x180006755  push    rsi
0x180006756  push    r12
0x180006758  push    r13
0x18000675a  push    r14
0x18000675c  push    r15
0x18000675e  sub     rsp, 300h
0x180006765  mov     rax, cs:__security_cookie
0x18000676c  xor     rax, rsp
0x18000676f  mov     [rsp+328h+var_38], rax
0x180006777  mov     r12d, r8d
0x18000677a  mov     r13, rdx
0x18000677d  mov     [rsp+328h+var_2F0], r8d
0x180006782  lea     r14, WPP_GLOBAL_Control
0x180006789  mov     rcx, cs:WPP_GLOBAL_Control
0x180006790  cmp     rcx, r14
0x180006793  jz      short loc_1800067BD
0x180006795  cmp     byte ptr [rcx+19h], 5
0x180006799  jb      short loc_1800067BD
0x18000679b  test    byte ptr [rcx+1Ch], 1
0x18000679f  jz      short loc_1800067BD
0x1800067a1  mov     edx, 1Dh
0x1800067a6  lea     r9, aWcmpolicymanag; "WcmPolicyManager::DeletePolicyByKey"
0x1800067ad  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800067b4  mov     rcx, [rcx+10h]
0x1800067b8  call    WPP_SF_s
0x1800067bd  xorps   xmm0, xmm0
0x1800067c0  xor     eax, eax
0x1800067c2  movups  xmmword ptr [rsp+328h+hKey], xmm0
0x1800067c7  mov     [rsp+328h+hKey], rax
0x1800067cc  mov     [rsp+328h+hKey+8], rax
0x1800067d1  mov     [rsp+328h+var_2D8], rax
0x1800067d6  movups  [rsp+328h+var_2D0], xmm0
0x1800067db  mov     qword ptr [rsp+328h+var_2D0], rax
0x1800067e0  mov     qword ptr [rsp+328h+var_2D0+8], rax
0x1800067e5  mov     [rsp+328h+var_2C0], rax
0x1800067ea  mov     [rsp+328h+var_2F4], eax
0x1800067ee  xor     r15d, r15d
0x1800067f1  xor     r8d, r8d
0x1800067f4  lea     rdx, [rsp+328h+hKey]
0x1800067f9  mov     ecx, r12d
0x1800067fc  call    ?OpenOrCreatePolicySourceRegKey@@YAJW4WCM_POLICY_SOURCE@@AEAVCRegKey@ATL@@H@Z; OpenOrCreatePolicySourceRegKey(WCM_POLICY_SOURCE,ATL::CRegKey &,int)
0x180006801  mov     ebx, eax
0x180006803  test    eax, eax
0x180006805  jns     short loc_18000680E
0x180006807  xor     ebx, ebx
0x180006809  jmp     loc_180006A8A
0x18000680e  xor     edx, edx; Val
0x180006810  mov     r8d, 1FEh; Size
0x180006816  lea     rcx, [rsp+328h+SubKey]; void *
0x18000681e  call    memset_0
0x180006823  mov     [rsp+328h+var_2B8], 0FFh
0x18000682b  lea     rcx, [rsp+328h+var_2A8]; this
0x180006833  call    ??0WcmConnectionMappingPolicyKey@@QEAA@XZ; WcmConnectionMappingPolicyKey::WcmConnectionMappingPolicyKey(void)
0x180006838  nop
0x180006839  lea     r9, [rsp+328h+var_2B8]; unsigned int *
0x18000683e  lea     r8, [rsp+328h+SubKey]; unsigned __int16 *
0x180006846  mov     edx, r15d; unsigned int
0x180006849  lea     rcx, [rsp+328h+hKey]; this
0x18000684e  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x180006853  mov     esi, eax
0x180006855  cmp     eax, 103h
0x18000685a  jnz     short loc_1800068A2
0x18000685c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006863  cmp     rcx, r14
0x180006866  jz      loc_180006A4E
0x18000686c  cmp     byte ptr [rcx+19h], 4
0x180006870  jb      loc_180006A4E
0x180006876  test    byte ptr [rcx+1Ch], 1
0x18000687a  jz      loc_180006A4E
0x180006880  mov     edx, 1Eh
0x180006885  mov     dword ptr [rsp+328h+var_308], r15d
0x18000688a  mov     r9d, r12d
0x18000688d  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180006894  mov     rcx, [rcx+10h]
0x180006898  call    WPP_SF_DD
0x18000689d  jmp     loc_180006A4E
0x1800068a2  test    esi, esi
0x1800068a4  jz      short loc_1800068F4
0x1800068a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ad  cmp     rcx, r14
0x1800068b0  jz      short loc_1800068DB
0x1800068b2  cmp     byte ptr [rcx+19h], 1
0x1800068b6  jb      short loc_1800068DB
0x1800068b8  test    byte ptr [rcx+1Ch], 1
0x1800068bc  jz      short loc_1800068DB
0x1800068be  mov     edx, 1Fh
0x1800068c3  mov     dword ptr [rsp+328h+var_308], r15d
0x1800068c8  mov     r9d, esi
0x1800068cb  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800068d2  mov     rcx, [rcx+10h]
0x1800068d6  call    WPP_SF_DD
0x1800068db  test    esi, esi
0x1800068dd  jg      short loc_1800068E6
0x1800068df  mov     ebx, esi
0x1800068e1  jmp     loc_180006A4E
0x1800068e6  movzx   ebx, si
0x1800068e9  or      ebx, 80070000h
0x1800068ef  jmp     loc_180006A4E
0x1800068f4  mov     r9d, 20019h; unsigned int
0x1800068fa  lea     r8, [rsp+328h+SubKey]; lpSubKey
0x180006902  mov     rdx, [rsp+328h+hKey]; hKey
0x180006907  lea     rcx, [rsp+328h+var_2D0]; this
0x18000690c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180006911  mov     ebx, eax
0x180006913  test    eax, eax
0x180006915  jz      short loc_180006966
0x180006917  mov     rcx, cs:WPP_GLOBAL_Control
0x18000691e  cmp     rcx, r14
0x180006921  jz      short loc_180006959
0x180006923  cmp     byte ptr [rcx+19h], 1
0x180006927  jb      short loc_180006959
0x180006929  test    byte ptr [rcx+1Ch], 1
0x18000692d  jz      short loc_180006959
0x18000692f  mov     edx, 20h ; ' '
0x180006934  mov     dword ptr [rsp+328h+var_300], r12d; char
0x180006939  lea     rax, [rsp+328h+SubKey]
0x180006941  mov     [rsp+328h+var_308], rax; __int64
0x180006946  mov     r9d, ebx
0x180006949  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180006950  mov     rcx, [rcx+10h]; LoggerHandle
0x180006954  call    WPP_SF_DSD
0x180006959  test    ebx, ebx
0x18000695b  jle     loc_180006A4E
0x180006961  movzx   ebx, bx
0x180006964  jmp     short loc_1800068E9
0x180006966  lea     rdx, [rsp+328h+var_2D0]; struct ATL::CRegKey *
0x18000696b  lea     rcx, [rsp+328h+var_2A8]; this
0x180006973  call    ?ReadFromRegistry@WcmConnectionMappingPolicyKey@@QEAAJAEAVCRegKey@ATL@@@Z; WcmConnectionMappingPolicyKey::ReadFromRegistry(ATL::CRegKey &)
0x180006978  mov     ebx, eax
0x18000697a  test    eax, eax
0x18000697c  js      loc_180006A4E
0x180006982  lea     rdx, [rsp+328h+var_2A8]
0x18000698a  mov     rcx, r13
0x18000698d  call    ??8WcmConnectionMappingPolicyKey@@QEAA_NAEBV0@@Z; WcmConnectionMappingPolicyKey::operator==(WcmConnectionMappingPolicyKey const &)
0x180006992  test    al, al
0x180006994  jz      loc_180006A5E
0x18000699a  lea     rdx, [rsp+328h+SubKey]; unsigned __int16 *
0x1800069a2  lea     rcx, [rsp+328h+hKey]; this
0x1800069a7  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800069ac  test    eax, eax
0x1800069ae  jz      short loc_1800069BF
0x1800069b0  jg      short loc_1800069B6
0x1800069b2  mov     ebx, eax
0x1800069b4  jmp     short loc_1800069BF
0x1800069b6  movzx   ebx, ax
0x1800069b9  or      ebx, 80070000h
0x1800069bf  test    ebx, ebx
0x1800069c1  js      short loc_180006A17
0x1800069c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ca  cmp     rcx, r14
0x1800069cd  jz      short loc_1800069FD
0x1800069cf  cmp     byte ptr [rcx+19h], 1
0x1800069d3  jb      short loc_1800069FD
0x1800069d5  test    byte ptr [rcx+1Ch], 1
0x1800069d9  jz      short loc_1800069FD
0x1800069db  mov     edx, 21h ; '!'
0x1800069e0  mov     dword ptr [rsp+328h+var_308], r12d
0x1800069e5  lea     r9, [rsp+328h+SubKey]
0x1800069ed  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800069f4  mov     rcx, [rcx+10h]
0x1800069f8  call    WPP_SF_SD
0x1800069fd  mov     [rsp+328h+var_2F4], 1
0x180006a05  jmp     short loc_180006A4E
0x180006a07  lea     r14, WPP_GLOBAL_Control
0x180006a0e  mov     ebx, [rsp+328h+var_2F8]
0x180006a12  mov     r12d, [rsp+328h+var_2F0]
0x180006a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a1e  cmp     rcx, r14
0x180006a21  jz      short loc_180006A4E
0x180006a23  cmp     byte ptr [rcx+19h], 4
0x180006a27  jb      short loc_180006A4E
0x180006a29  test    byte ptr [rcx+1Ch], 1
0x180006a2d  jz      short loc_180006A4E
0x180006a2f  mov     dword ptr [rsp+328h+var_300], r12d; char
0x180006a34  lea     rax, [rsp+328h+SubKey]
0x180006a3c  mov     [rsp+328h+var_308], rax; __int64
0x180006a41  mov     r9d, ebx
0x180006a44  mov     rcx, [rcx+10h]; LoggerHandle
0x180006a48  call    WPP_SF_dSD
0x180006a4d  nop
0x180006a4e  lea     rcx, [rsp+328h+var_2A8]; this
0x180006a56  call    ??1WcmConnectionMappingPolicyKey@@UEAA@XZ; WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey(void)
0x180006a5b  nop
0x180006a5c  jmp     short loc_180006A7E
0x180006a5e  inc     r15d
0x180006a61  lea     rcx, [rsp+328h+var_2A8]; this
0x180006a69  call    ??1WcmConnectionMappingPolicyKey@@UEAA@XZ; WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey(void)
0x180006a6e  jmp     loc_18000680E
0x180006a73  lea     r14, WPP_GLOBAL_Control
0x180006a7a  mov     ebx, [rsp+328h+var_2F8]
0x180006a7e  cmp     [rsp+328h+var_2F4], 0
0x180006a83  jz      short loc_180006A8A
0x180006a85  call    ?SignalPolicyChange@WcmPolicyManager@@AEAAXXZ; WcmPolicyManager::SignalPolicyChange(void)
0x180006a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a91  cmp     rcx, r14
0x180006a94  jz      short loc_180006AC3
0x180006a96  cmp     byte ptr [rcx+19h], 5
0x180006a9a  jb      short loc_180006AC3
0x180006a9c  test    byte ptr [rcx+1Ch], 1
0x180006aa0  jz      short loc_180006AC3
0x180006aa2  mov     edx, 23h ; '#'
0x180006aa7  mov     dword ptr [rsp+328h+var_308], ebx
0x180006aab  lea     r9, aWcmpolicymanag; "WcmPolicyManager::DeletePolicyByKey"
0x180006ab2  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180006ab9  mov     rcx, [rcx+10h]
0x180006abd  call    WPP_SF_sL
0x180006ac2  nop
0x180006ac3  lea     rcx, [rsp+328h+var_2D0]; this
0x180006ac8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006acd  nop
0x180006ace  lea     rcx, [rsp+328h+hKey]; this
0x180006ad3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006ad8  mov     eax, ebx
0x180006ada  mov     rcx, [rsp+328h+var_38]
0x180006ae2  xor     rcx, rsp; StackCookie
0x180006ae5  call    __security_check_cookie
0x180006aea  mov     rbx, [rsp+328h+arg_0]
0x180006af2  add     rsp, 300h
0x180006af9  pop     r15
0x180006afb  pop     r14
0x180006afd  pop     r13
0x180006aff  pop     r12
0x180006b01  pop     rsi
0x180006b02  retn
```
