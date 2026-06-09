# CUpgradeUserSetting::set_UInt32(uint)

- ea: `0x180007020`
- end: `0x180007116`
- name: `?set_UInt32@CUpgradeUserSetting@@UEAAJI@Z`
- size: `246`
- prototype: `__int64 __fastcall(CUpgradeUserSetting *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002a34`
- `0x1800056a0`
- `0x180007020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007031`
- `KERNEL32!GetLastError` at `0x180007031`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800070fc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800070fc`
- `WDSCORE!CurrentIP` at `0x18000703f`
- `WDSCORE!CurrentIP` at `0x18000703f`

## string_xrefs

- `0x180007052`: `User selected clean install option`

## pseudocode

```c
__int64 __fastcall CUpgradeUserSetting::set_UInt32(CUpgradeUserSetting *this, unsigned int a2)
{
  DWORD LastError; // edi
  __int64 v4; // rax
  bool v5; // zf
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  struct tagLOG_PARTIAL_MSG *v8; // rax

  CUInt32UserSetting::SerializeUInt32(this, a2);
  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = a2 == 0;
  v6 = v4;
  if ( v5 )
  {
    v7 = ConstructPartialMsgW(0x4000056u, "User selected clean install option");
    WdsSetupLogMessageW(
      v7,
      589824,
      L"D",
      0,
      930,
      L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
      L"CUpgradeUserSetting::set_UInt32",
      v6,
      LastError,
      0,
      0);
  }
  else
  {
    v8 = ConstructPartialMsgW(0x4000057u, "User selected upgrade option");
    WdsSetupLogMessageW(
      v8,
      589824,
      L"D",
      0,
      934,
      L"base\\ntsetup\\panther\\wdsutil\\usersetting.cpp",
      L"CUpgradeUserSetting::set_UInt32",
      v6,
      LastError,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180007020  mov     [rsp+arg_0], rbx
0x180007025  push    rdi
0x180007026  sub     rsp, 60h
0x18000702a  mov     ebx, edx
0x18000702c  call    ?SerializeUInt32@CUInt32UserSetting@@IEAAXI@Z; CUInt32UserSetting::SerializeUInt32(uint)
0x180007031  call    cs:__imp_GetLastError
0x180007038  nop     dword ptr [rax+rax+00h]
0x18000703d  mov     edi, eax
0x18000703f  call    cs:__imp_CurrentIP
0x180007046  nop     dword ptr [rax+rax+00h]
0x18000704b  test    ebx, ebx
0x18000704d  mov     rbx, rax
0x180007050  jnz     short loc_18000709F
0x180007052  lea     rdx, aUserSelectedCl; "User selected clean install option"
0x180007059  mov     ecx, 4000056h; unsigned int
0x18000705e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007063  mov     [rsp+68h+var_18], 0
0x18000706b  lea     rcx, aCupgradeuserse_0; "CUpgradeUserSetting::set_UInt32"
0x180007072  mov     [rsp+68h+var_20], 0
0x18000707b  mov     [rsp+68h+var_28], edi
0x18000707f  mov     [rsp+68h+var_30], rbx
0x180007084  mov     [rsp+68h+var_38], rcx
0x180007089  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x180007090  mov     [rsp+68h+var_40], rcx
0x180007095  mov     [rsp+68h+var_48], 3A2h
0x18000709d  jmp     short loc_1800070EA
0x18000709f  lea     rdx, aUserSelectedUp; "User selected upgrade option"
0x1800070a6  mov     ecx, 4000057h; unsigned int
0x1800070ab  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800070b0  mov     [rsp+68h+var_18], 0
0x1800070b8  lea     rcx, aCupgradeuserse_0; "CUpgradeUserSetting::set_UInt32"
0x1800070bf  mov     [rsp+68h+var_20], 0
0x1800070c8  mov     [rsp+68h+var_28], edi
0x1800070cc  mov     [rsp+68h+var_30], rbx
0x1800070d1  mov     [rsp+68h+var_38], rcx
0x1800070d6  lea     rcx, aBaseNtsetupPan_1; "base\\ntsetup\\panther\\wdsutil\\userse"...
0x1800070dd  mov     [rsp+68h+var_40], rcx
0x1800070e2  mov     [rsp+68h+var_48], 3A6h
0x1800070ea  xor     r9d, r9d
0x1800070ed  lea     r8, aD; "D"
0x1800070f4  mov     edx, 90000h
0x1800070f9  mov     rcx, rax
0x1800070fc  call    cs:__imp_WdsSetupLogMessageW
0x180007103  nop     dword ptr [rax+rax+00h]
0x180007108  mov     rbx, [rsp+68h+arg_0]
0x18000710d  xor     eax, eax
0x18000710f  add     rsp, 60h
0x180007113  pop     rdi
0x180007114  retn
```
