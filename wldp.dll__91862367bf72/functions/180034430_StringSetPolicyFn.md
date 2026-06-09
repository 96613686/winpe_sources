# StringSetPolicyFn

- ea: `0x180034430`
- end: `0x18003465c`
- name: `StringSetPolicyFn`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180013900`
- `0x1800159a0`
- `0x18001fd10`
- `0x1800206f4`
- `0x180021ec0`
- `0x180032730`
- `0x180032828`
- `0x180032a48`
- `0x180032db0`
- `0x18003301c`
- `0x180034430`
- `0x180039bb4`
- `0x180042010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800345a0`

## string_xrefs

- `0x180034524`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StringSetPolicyFn(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r14
  int ApplicationSetting; // eax
  unsigned int v5; // ebx
  unsigned int v6; // edi
  unsigned int v7; // r15d
  __int64 v8; // r14
  _WORD *v9; // r13
  _QWORD *v10; // rdx
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v12; // r12
  int v14; // [rsp+20h] [rbp-99h]
  char v15; // [rsp+40h] [rbp-79h] BYREF
  int v16; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-71h] BYREF
  char v18; // [rsp+4Ch] [rbp-6Dh] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD *v20; // [rsp+60h] [rbp-59h]
  _BYTE v21[64]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v22[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v23; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = a2;
  v20 = a2;
  v17 = 0;
  v19[0] = 0;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v21);
  if ( (unsigned __int8)SIPolicyIsBasePolicy(a1) )
  {
    v16 = 0;
    ___emplace_back_H___vector_V__vector_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std____V__allocator_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std_____std___std__V__allocator_V__vector_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std____V__allocator_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std_____std___std___2__std__QEAAAEAV__vector_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std____V__allocator_U__AppSettingsQuery_V__unordered_set_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__std_____std___1___QEAH_Z(
      v2 + 3,
      &v16);
  }
  ApplicationSetting = SIPolicyGetApplicationSetting(
                         a1,
                         *v2,
                         v2[1],
                         (unsigned int)&v18,
                         (__int64)&v16,
                         (__int64)&v17,
                         (__int64)v19);
  v16 = ApplicationSetting;
  if ( ApplicationSetting == -1073741275 )
    goto LABEL_18;
  if ( ApplicationSetting >= 0 )
  {
    v6 = v17 >> 4;
    v7 = 0;
    if ( v17 >> 4 )
    {
      v8 = v19[0];
      do
      {
        std::wstring::wstring(
          v22,
          *(_QWORD *)(v8 + 16LL * v7 + 8),
          (unsigned __int64)*(unsigned __int16 *)(v8 + 16LL * v7) >> 1);
        if ( v23 <= 7 )
        {
          v9 = v22;
          v10 = v22;
        }
        else
        {
          v9 = (_WORD *)v22[0];
          v10 = (_QWORD *)v22[0];
        }
        v11 = (unsigned __int16 *)v10 + v22[2];
        v12 = (unsigned __int16 *)v22;
        if ( v23 > 7 )
          v12 = (unsigned __int16 *)v22[0];
        while ( v12 != v11 )
          *v9++ = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*v12++);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
          v21,
          v19,
          v22);
        std::wstring::~wstring(v22);
        ++v7;
      }
      while ( v7 < v6 );
      v2 = v20;
    }
LABEL_18:
    v15 = *(_BYTE *)(a1 + 46) & 1;
    std::vector<AppSettingsQuery<std::unordered_set<std::wstring>>>::emplace_back<_GUID const &,unsigned char,std::unordered_set<std::wstring> &,long &>(
      v2[4] - 24,
      a1 + (*(_DWORD *)(a1 + 40) < 6u ? 16 : 704),
      (unsigned int)&v15,
      (unsigned int)v21,
      (__int64)&v16);
    v5 = 0;
    goto LABEL_19;
  }
  v5 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x2DA,
         (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
         (const char *)(unsigned int)ApplicationSetting,
         v14);
LABEL_19:
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v21);
  return v5;
}

```

## disassembly

```asm
0x180034430  mov     [rsp-8+arg_10], rbx
0x180034435  push    rbp
0x180034436  push    rsi
0x180034437  push    rdi
0x180034438  push    r12
0x18003443a  push    r13
0x18003443c  push    r14
0x18003443e  push    r15
0x180034440  lea     rbp, [rsp-27h]
0x180034445  sub     rsp, 0E0h
0x18003444c  mov     rax, cs:__security_cookie
0x180034453  xor     rax, rsp
0x180034456  mov     [rbp+57h+var_40], rax
0x18003445a  mov     r14, rdx
0x18003445d  mov     [rbp+57h+var_B0], rdx
0x180034461  mov     rsi, rcx
0x180034464  mov     [rbp+57h+var_C8], 0
0x18003446b  mov     [rbp+57h+var_C0], 0
0x180034473  lea     rcx, [rbp+57h+var_A0]
0x180034477  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18003447c  nop
0x18003447d  mov     rcx, rsi
0x180034480  call    SIPolicyIsBasePolicy
0x180034485  test    al, al
0x180034487  jz      short loc_18003449D
0x180034489  mov     [rbp+57h+var_CC], 0
0x180034490  lea     rcx, [r14+18h]
0x180034494  lea     rdx, [rbp+57h+var_CC]
0x180034498  call    ??$emplace_back@H@?$vector@V?$vector@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@@std@@@std@@V?$allocator@V?$vector@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@@std@@@std@@@2@@std@@QEAAAEAV?$vector@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@@std@@@1@$$QEAH@Z
0x18003449d  lea     rax, [rbp+57h+var_C0]
0x1800344a1  mov     [rsp+110h+var_E0], rax
0x1800344a6  lea     rax, [rbp+57h+var_C8]
0x1800344aa  mov     [rsp+110h+var_E8], rax
0x1800344af  lea     rax, [rbp+57h+var_CC]
0x1800344b3  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800344b8  lea     r9, [rbp+57h+var_C4]
0x1800344bc  mov     r8, [r14+8]
0x1800344c0  mov     rdx, [r14]
0x1800344c3  mov     rcx, rsi
0x1800344c6  call    SIPolicyGetApplicationSetting
0x1800344cb  mov     [rbp+57h+var_CC], eax
0x1800344ce  cmp     eax, 0C0000225h
0x1800344d3  jnz     short loc_180034519
0x1800344d5  mov     al, [rsi+2Eh]
0x1800344d8  and     al, 1
0x1800344da  mov     [rbp+57h+var_D0], al
0x1800344dd  cmp     dword ptr [rsi+28h], 6
0x1800344e1  sbb     rdx, rdx
0x1800344e4  and     rdx, 0FFFFFFFFFFFFFD50h
0x1800344eb  add     rdx, 2C0h
0x1800344f2  add     rdx, rsi
0x1800344f5  mov     rcx, [r14+20h]
0x1800344f9  sub     rcx, 18h
0x1800344fd  lea     rax, [rbp+57h+var_CC]
0x180034501  mov     qword ptr [rsp+110h+var_F0], rax
0x180034506  lea     r9, [rbp+57h+var_A0]
0x18003450a  lea     r8, [rbp+57h+var_D0]
0x18003450e  call    ??$emplace_back@AEBU_GUID@@EAEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAJ@?$vector@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@@std@@@std@@QEAAAEAU?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@AEBU_GUID@@$$QEAEAEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEAJ@Z
0x180034513  nop
0x180034514  jmp     loc_180034628
0x180034519  test    eax, eax
0x18003451b  jns     short loc_18003453C
0x18003451d  mov     rcx, [rbp+5Fh]; this
0x180034521  mov     r9d, eax; char *
0x180034524  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003452b  mov     edx, 2DAh; void *
0x180034530  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180034535  mov     ebx, eax
0x180034537  jmp     loc_18003462A
0x18003453c  mov     edi, [rbp+57h+var_C8]
0x18003453f  shr     edi, 4
0x180034542  xor     r15d, r15d
0x180034545  test    edi, edi
0x180034547  jz      loc_1800345E9
0x18003454d  mov     r14, [rbp+57h+var_C0]
0x180034551  mov     edx, r15d
0x180034554  add     rdx, rdx
0x180034557  movzx   r8d, word ptr [r14+rdx*8]
0x18003455c  shr     r8, 1
0x18003455f  mov     rdx, [r14+rdx*8+8]
0x180034564  lea     rcx, [rbp+57h+var_60]
0x180034568  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18003456d  nop
0x18003456e  mov     rcx, [rbp+57h+var_60]
0x180034572  cmp     [rbp+57h+var_48], 7
0x180034577  jbe     short loc_180034581
0x180034579  mov     r13, rcx
0x18003457c  mov     rdx, rcx
0x18003457f  jmp     short loc_180034589
0x180034581  lea     r13, [rbp+57h+var_60]
0x180034585  lea     rdx, [rbp+57h+var_60]
0x180034589  mov     rax, [rbp+57h+var_50]
0x18003458d  lea     rbx, [rdx+rax*2]
0x180034591  lea     r12, [rbp+57h+var_60]
0x180034595  cmova   r12, rcx
0x180034599  jmp     short loc_1800345B9
0x18003459b  movzx   ecx, word ptr [r12]
0x1800345a0  mov     rax, cs:__imp__o_towlower
0x1800345a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800345ac  mov     [r13+0], ax
0x1800345b1  lea     r13, [r13+2]
0x1800345b5  add     r12, 2
0x1800345b9  cmp     r12, rbx
0x1800345bc  jnz     short loc_18003459B
0x1800345be  lea     r8, [rbp+57h+var_60]
0x1800345c2  lea     rdx, [rbp+57h+var_C0]
0x1800345c6  lea     rcx, [rbp+57h+var_A0]
0x1800345ca  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x1800345cf  nop
0x1800345d0  lea     rcx, [rbp+57h+var_60]
0x1800345d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800345d9  inc     r15d
0x1800345dc  cmp     r15d, edi
0x1800345df  jb      loc_180034551
0x1800345e5  mov     r14, [rbp+57h+var_B0]
0x1800345e9  mov     al, [rsi+2Eh]
0x1800345ec  and     al, 1
0x1800345ee  mov     [rbp+57h+var_D0], al
0x1800345f1  cmp     dword ptr [rsi+28h], 6
0x1800345f5  sbb     rdx, rdx
0x1800345f8  and     rdx, 0FFFFFFFFFFFFFD50h
0x1800345ff  add     rdx, 2C0h
0x180034606  add     rdx, rsi
0x180034609  mov     rcx, [r14+20h]
0x18003460d  sub     rcx, 18h
0x180034611  lea     rax, [rbp+57h+var_CC]
0x180034615  mov     qword ptr [rsp+110h+var_F0], rax
0x18003461a  lea     r9, [rbp+57h+var_A0]
0x18003461e  lea     r8, [rbp+57h+var_D0]
0x180034622  call    ??$emplace_back@AEBU_GUID@@EAEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAJ@?$vector@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@@std@@@std@@QEAAAEAU?$AppSettingsQuery@V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@AEBU_GUID@@$$QEAEAEAV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEAJ@Z
0x180034627  nop
0x180034628  xor     ebx, ebx
0x18003462a  lea     rcx, [rbp+57h+var_A0]
0x18003462e  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180034633  mov     eax, ebx
0x180034635  mov     rcx, [rbp+57h+var_40]
0x180034639  xor     rcx, rsp; StackCookie
0x18003463c  call    __security_check_cookie
0x180034641  mov     rbx, [rsp+110h+arg_10]
0x180034649  add     rsp, 0E0h
0x180034650  pop     r15
0x180034652  pop     r14
0x180034654  pop     r13
0x180034656  pop     r12
0x180034658  pop     rdi
0x180034659  pop     rsi
0x18003465a  pop     rbp
0x18003465b  retn
```
