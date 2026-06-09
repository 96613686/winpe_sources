# BoolPolicyFn

- ea: `0x180033680`
- end: `0x180033772`
- name: `BoolPolicyFn`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18001fd10`
- `0x1800206f4`
- `0x1800328d8`
- `0x180032b08`
- `0x180033680`
- `0x180039bb4`

## string_xrefs

- `0x18003370c`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
int __fastcall BoolPolicyFn(__int64 a1, _QWORD *a2)
{
  int ApplicationSetting; // eax
  char v5; // al
  bool v6; // cf
  __int64 v7; // rdx
  __int64 v8; // rcx
  char v10; // al
  int v11; // [rsp+20h] [rbp-30h]
  char v12; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  bool v14; // [rsp+78h] [rbp+28h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  if ( (unsigned __int8)SIPolicyIsBasePolicy(a1) )
  {
    v15 = 0;
    std::vector<std::vector<AppSettingsQuery<bool>>>::emplace_back<int>(a2 + 3, &v15);
  }
  ApplicationSetting = SIPolicyGetApplicationSetting(
                         a1,
                         *a2,
                         a2[1],
                         (unsigned int)&v12,
                         (__int64)&v16,
                         (__int64)&v15,
                         (__int64)&v14);
  v16 = ApplicationSetting;
  if ( ApplicationSetting == -1073741275 )
  {
    v8 = a2[4];
    v5 = *(_BYTE *)(a1 + 46) & 1;
    v6 = *(_DWORD *)(a1 + 40) < 6u;
    v14 = 0;
    v7 = -(__int64)v6;
    LODWORD(v8) = v8 - 24;
  }
  else
  {
    if ( ApplicationSetting < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x14C,
               (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
               (const char *)(unsigned int)ApplicationSetting,
               v11);
    v10 = *(_BYTE *)(a1 + 46);
    v8 = a2[4] - 24LL;
    v14 = v14;
    v5 = v10 & 1;
    v7 = -(__int64)(*(_DWORD *)(a1 + 40) < 6u);
  }
  LOBYTE(v15) = v5;
  std::vector<AppSettingsQuery<bool>>::emplace_back<_GUID const &,unsigned char,bool,long &>(
    v8,
    a1 + (v7 & 0xFFFFFD50) + 704,
    (unsigned int)&v15,
    (unsigned int)&v14,
    (__int64)&v16);
  return 0;
}

```

## disassembly

```asm
0x180033680  push    rbp
0x180033682  push    rbx
0x180033683  push    rdi
0x180033684  mov     rbp, rsp
0x180033687  sub     rsp, 50h
0x18003368b  mov     rdi, rdx
0x18003368e  mov     [rbp+arg_8], 0
0x180033692  mov     rbx, rcx
0x180033695  call    SIPolicyIsBasePolicy
0x18003369a  test    al, al
0x18003369c  jz      short loc_1800336B2
0x18003369e  lea     rcx, [rdi+18h]
0x1800336a2  mov     [rbp+arg_10], 0
0x1800336a9  lea     rdx, [rbp+arg_10]
0x1800336ad  call    ??$emplace_back@H@?$vector@V?$vector@U?$AppSettingsQuery@_N@@V?$allocator@U?$AppSettingsQuery@_N@@@std@@@std@@V?$allocator@V?$vector@U?$AppSettingsQuery@_N@@V?$allocator@U?$AppSettingsQuery@_N@@@std@@@std@@@2@@std@@QEAAAEAV?$vector@U?$AppSettingsQuery@_N@@V?$allocator@U?$AppSettingsQuery@_N@@@std@@@1@$$QEAH@Z; std::vector<std::vector<AppSettingsQuery<bool>>>::emplace_back<int>(int &&)
0x1800336b2  mov     r8, [rdi+8]
0x1800336b6  lea     rax, [rbp+arg_8]
0x1800336ba  mov     rdx, [rdi]
0x1800336bd  lea     r9, [rbp+var_10]
0x1800336c1  mov     [rsp+50h+var_20], rax
0x1800336c6  mov     rcx, rbx
0x1800336c9  lea     rax, [rbp+arg_10]
0x1800336cd  mov     [rsp+50h+var_28], rax
0x1800336d2  lea     rax, [rbp+arg_18]
0x1800336d6  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800336db  call    SIPolicyGetApplicationSetting
0x1800336e0  mov     [rbp+arg_18], eax
0x1800336e3  cmp     eax, 0C0000225h
0x1800336e8  jnz     short loc_180033704
0x1800336ea  mov     al, [rbx+2Eh]
0x1800336ed  mov     rcx, [rdi+20h]
0x1800336f1  and     al, 1
0x1800336f3  cmp     dword ptr [rbx+28h], 6
0x1800336f7  mov     [rbp+arg_8], 0
0x1800336fb  sbb     rdx, rdx
0x1800336fe  sub     rcx, 18h
0x180033702  jmp     short loc_18003373E
0x180033704  test    eax, eax
0x180033706  jns     short loc_180033722
0x180033708  mov     rcx, [rbp+18h]; this
0x18003370c  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180033713  mov     r9d, eax; char *
0x180033716  mov     edx, 14Ch; void *
0x18003371b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033720  jmp     short loc_18003376A
0x180033722  mov     rcx, [rdi+20h]
0x180033726  mov     al, [rbx+2Eh]
0x180033729  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18003372d  cmp     [rbp+arg_8], 0
0x180033731  setnz   [rbp+arg_8]
0x180033735  and     al, 1
0x180033737  cmp     dword ptr [rbx+28h], 6
0x18003373b  sbb     rdx, rdx
0x18003373e  and     rdx, 0FFFFFFFFFFFFFD50h
0x180033745  mov     byte ptr [rbp+arg_10], al
0x180033748  add     rdx, 2C0h
0x18003374f  lea     rax, [rbp+arg_18]
0x180033753  add     rdx, rbx
0x180033756  mov     qword ptr [rsp+50h+var_30], rax
0x18003375b  lea     r9, [rbp+arg_8]
0x18003375f  lea     r8, [rbp+arg_10]
0x180033763  call    ??$emplace_back@AEBU_GUID@@E_NAEAJ@?$vector@U?$AppSettingsQuery@_N@@V?$allocator@U?$AppSettingsQuery@_N@@@std@@@std@@QEAAAEAU?$AppSettingsQuery@_N@@AEBU_GUID@@$$QEAE$$QEA_NAEAJ@Z; std::vector<AppSettingsQuery<bool>>::emplace_back<_GUID const &,uchar,bool,long &>(_GUID const &,uchar &&,bool &&,long &)
0x180033768  xor     eax, eax
0x18003376a  add     rsp, 50h
0x18003376e  pop     rdi
0x18003376f  pop     rbx
0x180033770  pop     rbp
0x180033771  retn
```
