# _dynamic_initializer_for__UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys__

- ea: `0x180004690`
- end: `0x18000475b`
- name: `_dynamic_initializer_for__UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys__`
- size: `203`
- prototype: `int()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000e7e4`
- `0x18000fb64`
- `0x18000fcc4`
- `0x180030714`
- `0x180030870`

## string_xrefs

- `0x1800046ad`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

## pseudocode

```c
int dynamic_initializer_for__UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys__()
{
  __int64 v0; // rbx
  _OWORD v2[3]; // [rsp+38h] [rbp-30h] BYREF

  memset(v2, 0, 32);
  std::wstring::_Construct<1,wchar_t const *>(v2);
  UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys = 0;
  qword_18004EF70 = 0;
  *(_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys = std::_Allocate<16,std::_Default_allocate_traits>(32);
  *((_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 1) = UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys;
  v0 = UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 32;
  qword_18004EF70 = UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 32;
  std::wstring::wstring(UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys, v2);
  *((_QWORD *)&UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys + 1) = v0;
  `eh vector destructor iterator'(v2, 0x20u, 1u, std::wstring::~wstring);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys__);
}

```

## disassembly

```asm
0x180004690  push    rbx
0x180004692  sub     rsp, 60h
0x180004696  xorps   xmm0, xmm0
0x180004699  movups  [rsp+68h+var_30], xmm0
0x18000469e  xorps   xmm1, xmm1
0x1800046a1  movdqu  [rsp+68h+var_20], xmm1
0x1800046a7  mov     r8d, 31h ; '1'
0x1800046ad  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800046b4  lea     rcx, [rsp+68h+var_30]
0x1800046b9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800046be  nop
0x1800046bf  xorps   xmm0, xmm0
0x1800046c2  movdqu  cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B, xmm0; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800046ca  mov     cs:qword_18004EF70, 0
0x1800046d5  mov     ecx, 20h ; ' '
0x1800046da  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800046df  mov     qword ptr cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B, rax; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800046e6  mov     qword ptr cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B+8, rax; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800046ed  lea     rbx, [rax+20h]
0x1800046f1  mov     cs:qword_18004EF70, rbx
0x1800046f8  lea     r8, ?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x1800046ff  mov     [rsp+68h+arg_0], r8
0x180004704  xorps   xmm0, xmm0
0x180004707  movups  [rsp+68h+var_48], xmm0
0x18000470c  mov     qword ptr [rsp+68h+var_48], rax
0x180004711  mov     qword ptr [rsp+68h+var_48+8], rax
0x180004716  mov     [rsp+68h+var_38], r8
0x18000471b  lea     rdx, [rsp+68h+var_30]
0x180004720  mov     rcx, rax
0x180004723  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180004728  nop
0x180004729  mov     qword ptr cs:?c_vszPolicy_GPCache_Regkeys@UpdatePolicyReader@@2V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@B+8, rbx; std::vector<std::wstring> const UpdatePolicyReader::c_vszPolicy_GPCache_Regkeys
0x180004730  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x180004737  mov     edx, 20h ; ' '; unsigned __int64
0x18000473c  lea     r8d, [rdx-1Fh]; unsigned __int64
0x180004740  lea     rcx, [rsp+68h+var_30]; void *
0x180004745  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000474a  lea     rcx, _dynamic_atexit_destructor_for__UpdatePolicyReader__c_vszPolicy_GPCache_Regkeys__
0x180004751  add     rsp, 60h
0x180004755  pop     rbx
0x180004756  jmp     atexit
```
