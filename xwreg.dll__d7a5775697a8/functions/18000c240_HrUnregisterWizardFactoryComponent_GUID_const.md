# HrUnregisterWizardFactoryComponent(_GUID const *)

- ea: `0x18000c240`
- end: `0x18000c41f`
- name: `?HrUnregisterWizardFactoryComponent@@YAJPEBU_GUID@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800073f0`
- `0x1800074f0`
- `0x1800076b0`

## callees

- `0x180007820`
- `0x180007a00`
- `0x180007a84`
- `0x1800095a0`
- `0x180009994`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ace0`
- `0x18000af74`
- `0x18000c240`
- `0x18000ebc0`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c286`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c302`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c338`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c338`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrUnregisterWizardFactoryComponent(GUID *rguid)
{
  unsigned int v2; // r11d
  int v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  PVOID *v6; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[24]; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[64]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(rguid, sz, 40);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x3Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, v2, L"Factory");
  CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>((__int64)v9);
  v3 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hKey = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 >= 0 )
    {
      v4 = HrRegDeleteSubKeyTree(hKey, sz);
      RegCloseKey(hKey);
      if ( v4 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
            (unsigned int)SubKey,
            (__int64)sz,
            v4);
        CPXWizardRegistryLockedTransaction<3>::HrRestore(v9);
      }
    }
    CPXWizardRegistryLockedTransaction<3>::HrRelease(v9);
    goto LABEL_14;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids,
      (unsigned int)SubKey,
      v3);
LABEL_14:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    WPP_SF_D(v6[2], 24, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids, (unsigned int)v4);
LABEL_18:
  CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c240  mov     [rsp-8+arg_8], rbx
0x18000c245  mov     [rsp-8+arg_10], rdi
0x18000c24a  push    rbp
0x18000c24b  lea     rbp, [rsp-30h]
0x18000c250  sub     rsp, 130h
0x18000c257  mov     rax, cs:__security_cookie
0x18000c25e  xor     rax, rsp
0x18000c261  mov     [rbp+30h+var_10], rax
0x18000c265  mov     rbx, rcx
0x18000c268  xor     edx, edx; Val
0x18000c26a  lea     r8d, [rdx+50h]; Size
0x18000c26e  lea     rcx, [rsp+130h+sz]; void *
0x18000c273  call    memset_0
0x18000c278  mov     r8d, 28h ; '('; cchMax
0x18000c27e  lea     rdx, [rsp+130h+sz]; lpsz
0x18000c283  mov     rcx, rbx; rguid
0x18000c286  call    cs:__imp_StringFromGUID2
0x18000c28c  xor     eax, eax
0x18000c28e  mov     [rbp+30h+SubKey], ax
0x18000c292  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c299  lea     r11d, [rax+3Dh]
0x18000c29d  mov     edx, r11d; unsigned __int64
0x18000c2a0  lea     rcx, [rbp+30h+SubKey]; unsigned __int16 *
0x18000c2a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c2a9  lea     r8, aFactory_0; "Factory"
0x18000c2b0  mov     edx, r11d; unsigned __int64
0x18000c2b3  lea     rcx, [rbp+30h+SubKey]; unsigned __int16 *
0x18000c2b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c2bc  lea     rcx, [rsp+130h+var_F8]
0x18000c2c1  call    ??0?$CPXWizardRegistryLockedTransaction@$01@@QEAA@XZ; CPXWizardRegistryLockedTransaction<2>::CPXWizardRegistryLockedTransaction<2>(void)
0x18000c2c6  nop
0x18000c2c7  lea     rcx, [rsp+130h+var_F8]
0x18000c2cc  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x18000c2d1  mov     ebx, eax
0x18000c2d3  test    eax, eax
0x18000c2d5  js      loc_18000C391
0x18000c2db  mov     [rsp+130h+hKey], 0
0x18000c2e4  lea     rax, [rsp+130h+hKey]
0x18000c2e9  mov     [rsp+130h+phkResult], rax; phkResult
0x18000c2ee  mov     r9d, 20006h; samDesired
0x18000c2f4  xor     r8d, r8d; ulOptions
0x18000c2f7  lea     rdx, [rbp+30h+SubKey]; lpSubKey
0x18000c2fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c302  call    cs:__imp_RegOpenKeyExW
0x18000c308  mov     ebx, eax
0x18000c30a  test    eax, eax
0x18000c30c  jle     short loc_18000C317
0x18000c30e  movzx   ebx, ax
0x18000c311  or      ebx, 80070000h
0x18000c317  lea     rdi, WPP_GLOBAL_Control
0x18000c31e  test    ebx, ebx
0x18000c320  js      short loc_18000C385
0x18000c322  lea     rdx, [rsp+130h+sz]; unsigned __int16 *
0x18000c327  mov     rcx, [rsp+130h+hKey]; HKEY
0x18000c32c  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000c331  mov     ebx, eax
0x18000c333  mov     rcx, [rsp+130h+hKey]; hKey
0x18000c338  call    cs:__imp_RegCloseKey
0x18000c33e  test    ebx, ebx
0x18000c340  jns     short loc_18000C385
0x18000c342  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c349  cmp     rcx, rdi
0x18000c34c  jz      short loc_18000C37B
0x18000c34e  test    byte ptr [rcx+1Ch], 4
0x18000c352  jz      short loc_18000C37B
0x18000c354  mov     edx, 16h
0x18000c359  mov     [rsp+130h+var_108], ebx
0x18000c35d  lea     rax, [rsp+130h+sz]
0x18000c362  mov     [rsp+130h+phkResult], rax
0x18000c367  lea     r9, [rbp+30h+SubKey]
0x18000c36b  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000c372  mov     rcx, [rcx+10h]
0x18000c376  call    WPP_SF_SSD
0x18000c37b  lea     rcx, [rsp+130h+var_F8]
0x18000c380  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRestore(void)
0x18000c385  lea     rcx, [rsp+130h+var_F8]
0x18000c38a  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRelease(void)
0x18000c38f  jmp     short loc_18000C3C7
0x18000c391  lea     rdi, WPP_GLOBAL_Control
0x18000c398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c39f  cmp     rcx, rdi
0x18000c3a2  jz      short loc_18000C3F2
0x18000c3a4  test    byte ptr [rcx+1Ch], 4
0x18000c3a8  jz      short loc_18000C3CE
0x18000c3aa  mov     edx, 17h
0x18000c3af  mov     dword ptr [rsp+130h+phkResult], eax
0x18000c3b3  lea     r9, [rbp+30h+SubKey]
0x18000c3b7  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000c3be  mov     rcx, [rcx+10h]
0x18000c3c2  call    WPP_SF_SD
0x18000c3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3ce  cmp     rcx, rdi
0x18000c3d1  jz      short loc_18000C3F2
0x18000c3d3  test    byte ptr [rcx+1Ch], 10h
0x18000c3d7  jz      short loc_18000C3F2
0x18000c3d9  mov     edx, 18h
0x18000c3de  mov     r9d, ebx
0x18000c3e1  lea     r8, WPP_f37d908925783d53af397ed2b68cc6c9_Traceguids
0x18000c3e8  mov     rcx, [rcx+10h]
0x18000c3ec  call    WPP_SF_D
0x18000c3f1  nop
0x18000c3f2  lea     rcx, [rsp+130h+var_F8]
0x18000c3f7  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
0x18000c3fc  mov     eax, ebx
0x18000c3fe  mov     rcx, [rbp+30h+var_10]
0x18000c402  xor     rcx, rsp; StackCookie
0x18000c405  call    __security_check_cookie
0x18000c40a  lea     r11, [rsp+130h+var_s0]
0x18000c412  mov     rbx, [r11+18h]
0x18000c416  mov     rdi, [r11+20h]
0x18000c41a  mov     rsp, r11
0x18000c41d  pop     rbp
0x18000c41e  retn
```
