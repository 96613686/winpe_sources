# CUpgradeUserSetting::UnattendChecked(void)

- ea: `0x180005a50`
- end: `0x180005d2f`
- name: `?UnattendChecked@CUpgradeUserSetting@@SAHXZ`
- size: `735`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002a34`
- `0x180005a50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005a9c`
- `KERNEL32!GetLastError` at `0x180005b49`
- `KERNEL32!GetLastError` at `0x180005c11`
- `KERNEL32!GetLastError` at `0x180005c7e`
- `KERNEL32!GetLastError` at `0x180005a9c`
- `KERNEL32!GetLastError` at `0x180005b49`
- `KERNEL32!GetLastError` at `0x180005c11`
- `KERNEL32!GetLastError` at `0x180005c7e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005bc6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005cfb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005bc6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005cfb`
- `WDSCORE!CurrentIP` at `0x180005aaa`
- `WDSCORE!CurrentIP` at `0x180005b57`
- `WDSCORE!CurrentIP` at `0x180005c1f`
- `WDSCORE!CurrentIP` at `0x180005c8c`
- `WDSCORE!CurrentIP` at `0x180005aaa`
- `WDSCORE!CurrentIP` at `0x180005b57`
- `WDSCORE!CurrentIP` at `0x180005c1f`
- `WDSCORE!CurrentIP` at `0x180005c8c`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180005be3`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180005be3`
- `WDSCORE!WdsSetBlackboardValue` at `0x180005c01`
- `WDSCORE!WdsSetBlackboardValue` at `0x180005c01`
- `WDSCORE!WdsGetBlackboardValue` at `0x180005b1b`
- `WDSCORE!WdsGetBlackboardValue` at `0x180005b1b`
- `WDSCORE!WdsCreateBlackboard` at `0x180005a83`
- `WDSCORE!WdsCreateBlackboard` at `0x180005a83`
- `WDSCORE!WdsDestroyBlackboard` at `0x180005d11`
- `WDSCORE!WdsDestroyBlackboard` at `0x180031e9a`
- `WDSCORE!WdsDestroyBlackboard` at `0x180005d11`
- `WDSCORE!WdsDestroyBlackboard` at `0x180031e9a`

## string_xrefs

- `0x180005ab9`: `CUpgradeUserSetting::UnattendChecked couldn't create BB`
- `0x180005b69`: `Upgrade Unattend Processed: %s\UnattendDone already set to 1.`

## pseudocode

```c
__int64 CUpgradeUserSetting::UnattendChecked(void)
{
  unsigned int v0; // esi
  __int64 Blackboard; // rax
  __int64 v2; // r14
  DWORD v3; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  __int128 v16; // [rsp+68h] [rbp-50h] BYREF
  _OWORD v17[4]; // [rsp+78h] [rbp-40h] BYREF

  v0 = 0;
  v16 = 0;
  v17[0] = 0;
  Blackboard = WdsCreateBlackboard(8, L"SetupInfo", 0);
  v2 = Blackboard;
  if ( Blackboard )
  {
    if ( (unsigned int)WdsGetBlackboardValue(Blackboard, L"Upgrade", L"UnattendDone", &v16)
      && (_DWORD)v16 == 4
      && (v0 = 1, DWORD2(v16) == 1) )
    {
      LastError = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(
             0x400005Au,
             "Upgrade Unattend Processed: %s\\UnattendDone already set to 1.",
             (const char *)L"Upgrade");
      WdsSetupLogMessageW(
        v8,
        589824,
        L"D",
        0,
        985,
        L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
        L"CUpgradeUserSetting::UnattendChecked",
        v7,
        LastError,
        0,
        0);
    }
    else
    {
      WdsInitializeDataUInt32(v17, 1);
      if ( (unsigned int)WdsSetBlackboardValue(v2, L"Upgrade", L"UnattendDone", v17) )
      {
        v9 = GetLastError();
        v10 = CurrentIP();
        v11 = ConstructPartialMsgW(
                0x400005Bu,
                "Upgrade Unattend Processed: Set %s\\UnattendDone value to 1.",
                (const char *)L"Upgrade");
        WdsSetupLogMessageW(
          v11,
          589824,
          L"D",
          0,
          1001,
          L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
          L"CUpgradeUserSetting::UnattendChecked",
          v10,
          v9,
          0,
          0);
      }
      else
      {
        v12 = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(
                0x200005Cu,
                "Upgrade Unattend Processed: Error setting %s\\UnattendDone value.",
                (const char *)L"Upgrade");
        WdsSetupLogMessageW(
          v14,
          589824,
          L"D",
          0,
          1006,
          L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
          L"CUpgradeUserSetting::UnattendChecked",
          v13,
          v12,
          0,
          0);
      }
      v0 = 0;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = CurrentIP();
    v5 = ConstructPartialMsgW(0x2000059u, "CUpgradeUserSetting::UnattendChecked couldn't create BB");
    WdsSetupLogMessageW(
      v5,
      589824,
      L"D",
      0,
      974,
      L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
      L"CUpgradeUserSetting::UnattendChecked",
      v4,
      v3,
      0,
      0);
  }
  if ( v2 )
    WdsDestroyBlackboard(v2);
  return v0;
}

```

## disassembly

```asm
0x180005a50  push    rbx
0x180005a52  push    rsi
0x180005a53  push    rdi
0x180005a54  push    r12
0x180005a56  push    r14
0x180005a58  sub     rsp, 90h
0x180005a5f  xor     esi, esi
0x180005a61  xorps   xmm0, xmm0
0x180005a64  movups  [rsp+0B8h+var_50], xmm0
0x180005a69  xorps   xmm1, xmm1
0x180005a6c  movups  [rsp+0B8h+var_40], xmm1
0x180005a71  mov     [rsp+0B8h+var_58], rsi
0x180005a76  xor     r8d, r8d
0x180005a79  lea     rdx, aSetupinfo; "SetupInfo"
0x180005a80  lea     ecx, [rsi+8]
0x180005a83  call    cs:__imp_WdsCreateBlackboard
0x180005a8a  nop     dword ptr [rax+rax+00h]
0x180005a8f  mov     r14, rax
0x180005a92  mov     [rsp+0B8h+var_58], rax
0x180005a97  test    rax, rax
0x180005a9a  jnz     short loc_180005B02
0x180005a9c  call    cs:__imp_GetLastError
0x180005aa3  nop     dword ptr [rax+rax+00h]
0x180005aa8  mov     edi, eax
0x180005aaa  call    cs:__imp_CurrentIP
0x180005ab1  nop     dword ptr [rax+rax+00h]
0x180005ab6  mov     rbx, rax
0x180005ab9  lea     rdx, aCupgradeuserse; "CUpgradeUserSetting::UnattendChecked co"...
0x180005ac0  mov     ecx, 2000059h; unsigned int
0x180005ac5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005aca  mov     [rsp+0B8h+var_68], r14d
0x180005acf  mov     [rsp+0B8h+var_70], r14
0x180005ad4  mov     [rsp+0B8h+var_78], edi
0x180005ad8  mov     [rsp+0B8h+var_80], rbx
0x180005add  lea     rcx, aCupgradeuserse_1; "CUpgradeUserSetting::UnattendChecked"
0x180005ae4  mov     [rsp+0B8h+var_88], rcx
0x180005ae9  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x180005af0  mov     [rsp+0B8h+var_90], rcx
0x180005af5  mov     [rsp+0B8h+var_98], 3CEh
0x180005afd  jmp     loc_180005BB4
0x180005b02  lea     r9, [rsp+0B8h+var_50]
0x180005b07  lea     r8, aUnattenddone; "UnattendDone"
0x180005b0e  lea     r12, aUpgrade; "Upgrade"
0x180005b15  mov     rdx, r12
0x180005b18  mov     rcx, r14
0x180005b1b  call    cs:__imp_WdsGetBlackboardValue
0x180005b22  nop     dword ptr [rax+rax+00h]
0x180005b27  test    eax, eax
0x180005b29  jz      loc_180005BD7
0x180005b2f  cmp     dword ptr [rsp+0B8h+var_50], 4
0x180005b34  jnz     loc_180005BD7
0x180005b3a  mov     esi, 1
0x180005b3f  cmp     dword ptr [rsp+0B8h+var_50+8], esi
0x180005b43  jnz     loc_180005BDC
0x180005b49  call    cs:__imp_GetLastError
0x180005b50  nop     dword ptr [rax+rax+00h]
0x180005b55  mov     edi, eax
0x180005b57  call    cs:__imp_CurrentIP
0x180005b5e  nop     dword ptr [rax+rax+00h]
0x180005b63  mov     rbx, rax
0x180005b66  mov     r8, r12
0x180005b69  lea     rdx, aUpgradeUnatten_0; "Upgrade Unattend Processed: %s\\Unatten"...
0x180005b70  mov     ecx, 400005Ah; unsigned int
0x180005b75  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005b7a  mov     [rsp+0B8h+var_68], 0
0x180005b82  mov     [rsp+0B8h+var_70], 0
0x180005b8b  mov     [rsp+0B8h+var_78], edi
0x180005b8f  mov     [rsp+0B8h+var_80], rbx
0x180005b94  lea     rcx, aCupgradeuserse_1; "CUpgradeUserSetting::UnattendChecked"
0x180005b9b  mov     [rsp+0B8h+var_88], rcx
0x180005ba0  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x180005ba7  mov     [rsp+0B8h+var_90], rcx
0x180005bac  mov     [rsp+0B8h+var_98], 3D9h
0x180005bb4  xor     r9d, r9d
0x180005bb7  lea     r8, aD; "D"
0x180005bbe  mov     edx, 90000h
0x180005bc3  mov     rcx, rax
0x180005bc6  call    cs:__imp_WdsSetupLogMessageW
0x180005bcd  nop     dword ptr [rax+rax+00h]
0x180005bd2  jmp     loc_180005D09
0x180005bd7  mov     esi, 1
0x180005bdc  mov     edx, esi
0x180005bde  lea     rcx, [rsp+0B8h+var_40]
0x180005be3  call    cs:__imp_WdsInitializeDataUInt32
0x180005bea  nop     dword ptr [rax+rax+00h]
0x180005bef  lea     r9, [rsp+0B8h+var_40]
0x180005bf4  lea     r8, aUnattenddone; "UnattendDone"
0x180005bfb  mov     rdx, r12
0x180005bfe  mov     rcx, r14
0x180005c01  call    cs:__imp_WdsSetBlackboardValue
0x180005c08  nop     dword ptr [rax+rax+00h]
0x180005c0d  test    eax, eax
0x180005c0f  jz      short loc_180005C7E
0x180005c11  call    cs:__imp_GetLastError
0x180005c18  nop     dword ptr [rax+rax+00h]
0x180005c1d  mov     edi, eax
0x180005c1f  call    cs:__imp_CurrentIP
0x180005c26  nop     dword ptr [rax+rax+00h]
0x180005c2b  mov     rbx, rax
0x180005c2e  mov     r8, r12
0x180005c31  lea     rdx, aUpgradeUnatten_1; "Upgrade Unattend Processed: Set %s\\Una"...
0x180005c38  mov     ecx, 400005Bh; unsigned int
0x180005c3d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005c42  mov     [rsp+0B8h+var_68], 0
0x180005c4a  mov     [rsp+0B8h+var_70], 0
0x180005c53  mov     [rsp+0B8h+var_78], edi
0x180005c57  mov     [rsp+0B8h+var_80], rbx
0x180005c5c  lea     rcx, aCupgradeuserse_1; "CUpgradeUserSetting::UnattendChecked"
0x180005c63  mov     [rsp+0B8h+var_88], rcx
0x180005c68  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x180005c6f  mov     [rsp+0B8h+var_90], rcx
0x180005c74  mov     [rsp+0B8h+var_98], 3E9h
0x180005c7c  jmp     short loc_180005CE9
0x180005c7e  call    cs:__imp_GetLastError
0x180005c85  nop     dword ptr [rax+rax+00h]
0x180005c8a  mov     edi, eax
0x180005c8c  call    cs:__imp_CurrentIP
0x180005c93  nop     dword ptr [rax+rax+00h]
0x180005c98  mov     rbx, rax
0x180005c9b  mov     r8, r12
0x180005c9e  lea     rdx, aUpgradeUnatten; "Upgrade Unattend Processed: Error setti"...
0x180005ca5  mov     ecx, 200005Ch; unsigned int
0x180005caa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005caf  mov     [rsp+0B8h+var_68], 0
0x180005cb7  mov     [rsp+0B8h+var_70], 0
0x180005cc0  mov     [rsp+0B8h+var_78], edi
0x180005cc4  mov     [rsp+0B8h+var_80], rbx
0x180005cc9  lea     rcx, aCupgradeuserse_1; "CUpgradeUserSetting::UnattendChecked"
0x180005cd0  mov     [rsp+0B8h+var_88], rcx
0x180005cd5  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x180005cdc  mov     [rsp+0B8h+var_90], rcx
0x180005ce1  mov     [rsp+0B8h+var_98], 3EEh
0x180005ce9  xor     r9d, r9d
0x180005cec  lea     r8, aD; "D"
0x180005cf3  mov     edx, 90000h
0x180005cf8  mov     rcx, rax
0x180005cfb  call    cs:__imp_WdsSetupLogMessageW
0x180005d02  nop     dword ptr [rax+rax+00h]
0x180005d07  xor     esi, esi
0x180005d09  test    r14, r14
0x180005d0c  jz      short loc_180005D1D
0x180005d0e  mov     rcx, r14
0x180005d11  call    cs:__imp_WdsDestroyBlackboard
0x180005d18  nop     dword ptr [rax+rax+00h]
0x180005d1d  mov     eax, esi
0x180005d1f  add     rsp, 90h
0x180005d26  pop     r14
0x180005d28  pop     r12
0x180005d2a  pop     rdi
0x180005d2b  pop     rsi
0x180005d2c  pop     rbx
0x180005d2d  retn
0x180031e88  push    rbp
0x180031e8a  sub     rsp, 60h
0x180031e8e  mov     rbp, rdx
0x180031e91  mov     rcx, [rbp+60h]
0x180031e95  test    rcx, rcx
0x180031e98  jz      short loc_180031EA7
0x180031e9a  call    cs:__imp_WdsDestroyBlackboard
0x180031ea1  nop     dword ptr [rax+rax+00h]
0x180031ea6  nop
0x180031ea7  add     rsp, 60h
0x180031eab  pop     rbp
0x180031eac  retn
```
