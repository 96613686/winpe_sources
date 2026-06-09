# GetAppSettingBoolean

- ea: `0x180033778`
- end: `0x1800339f0`
- name: `GetAppSettingBoolean`
- size: `632`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800351e0`

## callees

- `0x180013930`
- `0x1800159a0`
- `0x18001f3fc`
- `0x1800206f4`
- `0x180021ec0`
- `0x180032ef0`
- `0x180033778`
- `0x180034164`
- `0x1800392b0`
- `0x180039cb0`

## string_xrefs

- `0x1800337f1`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetAppSettingBoolean(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  char v5; // r12
  int v6; // r14d
  int v7; // r13d
  __int64 v8; // r10
  int v9; // eax
  unsigned int v10; // ebx
  char v11; // si
  char v12; // di
  char v13; // r15
  __int64 *v14; // r10
  char v15; // r14
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  char v19; // r11
  char v20; // bl
  const wchar_t *v21; // rsi
  const wchar_t *v22; // rdx
  _QWORD *v23; // r11
  _QWORD *v24; // r10
  _QWORD *v25; // rcx
  int v27; // [rsp+20h] [rbp-B1h]
  int v28; // [rsp+50h] [rbp-81h]
  _QWORD v29[2]; // [rsp+60h] [rbp-71h] BYREF
  int v30; // [rsp+70h] [rbp-61h]
  int v31; // [rsp+74h] [rbp-5Dh]
  __int64 *v32; // [rsp+78h] [rbp-59h] BYREF
  __int64 *v33; // [rsp+80h] [rbp-51h]
  _QWORD v34[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-31h]
  unsigned __int64 v36; // [rsp+A8h] [rbp-29h]
  _QWORD v37[2]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-11h]
  unsigned __int64 v39; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v5 = a4;
  v6 = a3;
  v28 = a3;
  v7 = a2;
  v29[0] = a2;
  v29[1] = a3;
  v30 = a4;
  v31 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v32);
  v9 = SIPolicyForEachPolicy(v8, BoolPolicyFn, v29);
  if ( v9 < 0 )
  {
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
            (const char *)(unsigned int)v9,
            v27);
    goto LABEL_38;
  }
  v11 = 1;
  v12 = 1;
  v13 = 0;
  v14 = v32;
  if ( v32 == v33 )
    goto LABEL_24;
  do
  {
    v15 = 0;
    v16 = v14[1];
    v17 = *v14;
    if ( *v14 != v16 )
    {
      do
      {
        if ( !(unsigned __int8)SIPolicyIsSystemPolicy(v17) || *(_DWORD *)(v18 + 20) != -1073741275 )
        {
          v15 = 1;
          if ( v19 || *(_BYTE *)(v18 + 24) )
            v19 = 1;
        }
        v17 = v18 + 28;
      }
      while ( v17 != v16 );
      if ( v15 )
      {
        if ( !*(_BYTE *)(v16 - 12) || (v5 & 1) == 0 )
        {
          v13 = 1;
          if ( v19 && v11 )
          {
            v11 = 1;
            goto LABEL_19;
          }
          v11 = 0;
        }
        if ( !v19 )
        {
LABEL_21:
          v12 = 0;
          goto LABEL_22;
        }
LABEL_19:
        if ( v12 )
        {
          v12 = 1;
          goto LABEL_22;
        }
        goto LABEL_21;
      }
    }
LABEL_22:
    v14 += 3;
  }
  while ( v14 != v33 );
  v6 = v28;
LABEL_24:
  v20 = v13 != 0 ? v11 : 0;
  *a5 = v20 != 0;
  v21 = L"true";
  v22 = L"true";
  if ( !v20 )
    v22 = L"false";
  std::wstring::wstring(v34, v22);
  if ( v12 == v20 )
  {
    v25 = v34;
    if ( v36 > 7 )
      v25 = (_QWORD *)v34[0];
    LogApplicationSettingQuery(v7, v6, 0, 1, 2 * v35 + 2, (__int64)v25, 0, 0, 0);
  }
  else
  {
    if ( !v12 )
      v21 = L"false";
    std::wstring::wstring(v37, v21);
    v23 = v37;
    if ( v39 > 7 )
      v23 = (_QWORD *)v37[0];
    v24 = v34;
    if ( v36 > 7 )
      v24 = (_QWORD *)v34[0];
    LogApplicationSettingQuery(v7, v6, 0, 1, 2 * v35 + 2, (__int64)v24, 1, 2 * v38 + 2, (__int64)v23);
    std::wstring::~wstring(v37);
  }
  std::wstring::~wstring(v34);
  v10 = 0;
LABEL_38:
  AppSettingsContext<bool>::~AppSettingsContext<bool>(v29);
  return v10;
}

```

## disassembly

```asm
0x180033778  push    rbp
0x18003377a  push    rbx
0x18003377b  push    rsi
0x18003377c  push    rdi
0x18003377d  push    r12
0x18003377f  push    r13
0x180033781  push    r14
0x180033783  push    r15
0x180033785  lea     rbp, [rsp-17h]
0x18003378a  sub     rsp, 0E8h
0x180033791  mov     rax, cs:__security_cookie
0x180033798  xor     rax, rsp
0x18003379b  mov     [rbp+4Fh+var_50], rax
0x18003379f  mov     r12d, r9d
0x1800337a2  mov     r14, r8
0x1800337a5  mov     [rsp+120h+var_D0], r8
0x1800337aa  mov     r13, rdx
0x1800337ad  mov     r10, rcx
0x1800337b0  mov     rax, [rbp+4Fh+arg_20]
0x1800337b4  mov     [rbp+4Fh+var_C8], rax
0x1800337b8  mov     [rbp+4Fh+var_C0], rdx
0x1800337bc  mov     [rbp+4Fh+var_B8], r8
0x1800337c0  mov     [rbp+4Fh+var_B0], r9d
0x1800337c4  xor     eax, eax
0x1800337c6  mov     [rbp+4Fh+var_AC], eax
0x1800337c9  lea     rcx, [rbp+4Fh+var_A8]
0x1800337cd  call    ??$?0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(std::allocator<std::wstring> const &)
0x1800337d2  nop
0x1800337d3  lea     r8, [rbp+4Fh+var_C0]
0x1800337d7  lea     rdx, BoolPolicyFn
0x1800337de  mov     rcx, r10
0x1800337e1  call    SIPolicyForEachPolicy
0x1800337e6  test    eax, eax
0x1800337e8  jns     short loc_180033809
0x1800337ea  mov     rcx, [rbp+57h]; this
0x1800337ee  mov     r9d, eax; char *
0x1800337f1  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800337f8  mov     edx, 184h; void *
0x1800337fd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180033802  mov     ebx, eax
0x180033804  jmp     loc_1800339C5
0x180033809  mov     sil, 1
0x18003380c  mov     dil, sil
0x18003380f  xor     r15b, r15b
0x180033812  mov     r10, [rbp+4Fh+var_A8]
0x180033816  cmp     r10, [rbp+4Fh+var_A0]
0x18003381a  jz      loc_1800338A5
0x180033820  xor     r11b, r11b
0x180033823  xor     r14b, r14b
0x180033826  mov     rbx, [r10+8]
0x18003382a  mov     rcx, [r10]
0x18003382d  cmp     rcx, rbx
0x180033830  jz      short loc_180033896
0x180033832  call    SIPolicyIsSystemPolicy
0x180033837  test    al, al
0x180033839  jz      short loc_180033844
0x18003383b  cmp     dword ptr [rcx+14h], 0C0000225h
0x180033842  jz      short loc_180033855
0x180033844  mov     r14b, 1
0x180033847  test    r11b, r11b
0x18003384a  jnz     short loc_180033852
0x18003384c  cmp     [rcx+18h], r11b
0x180033850  jz      short loc_180033855
0x180033852  mov     r11b, r14b
0x180033855  add     rcx, 1Ch
0x180033859  cmp     rcx, rbx
0x18003385c  jnz     short loc_180033832
0x18003385e  test    r14b, r14b
0x180033861  jz      short loc_180033896
0x180033863  cmp     byte ptr [rbx-0Ch], 0
0x180033867  jz      short loc_18003386F
0x180033869  test    r12b, 1
0x18003386d  jnz     short loc_180033884
0x18003386f  mov     r15b, 1
0x180033872  test    r11b, r11b
0x180033875  jz      short loc_180033881
0x180033877  test    sil, sil
0x18003387a  jz      short loc_180033881
0x18003387c  mov     sil, r15b
0x18003387f  jmp     short loc_180033889
0x180033881  xor     sil, sil
0x180033884  test    r11b, r11b
0x180033887  jz      short loc_180033893
0x180033889  test    dil, dil
0x18003388c  jz      short loc_180033893
0x18003388e  mov     dil, 1
0x180033891  jmp     short loc_180033896
0x180033893  xor     dil, dil
0x180033896  add     r10, 18h
0x18003389a  cmp     r10, [rbp+4Fh+var_A0]
0x18003389e  jnz     short loc_180033820
0x1800338a0  mov     r14, [rsp+120h+var_D0]
0x1800338a5  neg     r15b
0x1800338a8  sbb     bl, bl
0x1800338aa  and     bl, sil
0x1800338ad  mov     eax, 0
0x1800338b2  setnz   al
0x1800338b5  mov     rcx, [rbp+4Fh+var_C8]
0x1800338b9  mov     [rcx], eax
0x1800338bb  lea     r15, aFalse; "false"
0x1800338c2  lea     rsi, aTrue; "true"
0x1800338c9  mov     rdx, rsi
0x1800338cc  test    bl, bl
0x1800338ce  cmovz   rdx, r15
0x1800338d2  lea     rcx, [rbp+4Fh+var_90]
0x1800338d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338db  nop
0x1800338dc  cmp     dil, bl
0x1800338df  jz      loc_180033966
0x1800338e5  test    dil, dil
0x1800338e8  cmovz   rsi, r15
0x1800338ec  mov     rdx, rsi
0x1800338ef  lea     rcx, [rbp+4Fh+var_70]
0x1800338f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338f8  nop
0x1800338f9  lea     r11, [rbp+4Fh+var_70]
0x1800338fd  cmp     [rbp+4Fh+var_58], 7
0x180033902  cmova   r11, [rbp+4Fh+var_70]
0x180033907  mov     r8, [rbp+4Fh+var_60]
0x18003390b  lea     r10, [rbp+4Fh+var_90]
0x18003390f  cmp     [rbp+4Fh+var_78], 7
0x180033914  cmova   r10, [rbp+4Fh+var_90]
0x180033919  lea     r8, ds:2[r8*2]
0x180033921  mov     rax, [rbp+4Fh+var_80]
0x180033925  lea     rax, ds:2[rax*2]
0x18003392d  mov     [rsp+120h+var_E0], r11
0x180033932  mov     [rsp+120h+var_E8], r8
0x180033937  mov     r9d, 1
0x18003393d  mov     [rsp+120h+var_F0], r9
0x180033942  mov     [rsp+120h+var_F8], r10
0x180033947  mov     [rsp+120h+var_100], rax
0x18003394c  xor     r8d, r8d
0x18003394f  mov     rdx, r14
0x180033952  mov     rcx, r13
0x180033955  call    LogApplicationSettingQuery
0x18003395a  nop
0x18003395b  lea     rcx, [rbp+4Fh+var_70]
0x18003395f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033964  jmp     short loc_1800339BA
0x180033966  lea     rcx, [rbp+4Fh+var_90]
0x18003396a  cmp     [rbp+4Fh+var_78], 7
0x18003396f  cmova   rcx, [rbp+4Fh+var_90]
0x180033974  mov     rax, [rbp+4Fh+var_80]
0x180033978  lea     rax, ds:2[rax*2]
0x180033980  mov     [rsp+120h+var_E0], 0
0x180033989  mov     [rsp+120h+var_E8], 0
0x180033992  mov     [rsp+120h+var_F0], 0
0x18003399b  mov     [rsp+120h+var_F8], rcx
0x1800339a0  mov     [rsp+120h+var_100], rax
0x1800339a5  mov     r9d, 1
0x1800339ab  xor     r8d, r8d
0x1800339ae  mov     rdx, r14
0x1800339b1  mov     rcx, r13
0x1800339b4  call    LogApplicationSettingQuery
0x1800339b9  nop
0x1800339ba  lea     rcx, [rbp+4Fh+var_90]
0x1800339be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800339c3  xor     ebx, ebx
0x1800339c5  lea     rcx, [rbp+4Fh+var_C0]
0x1800339c9  call    ??1?$AppSettingsContext@_N@@QEAA@XZ; AppSettingsContext<bool>::~AppSettingsContext<bool>(void)
0x1800339ce  mov     eax, ebx
0x1800339d0  mov     rcx, [rbp+4Fh+var_50]
0x1800339d4  xor     rcx, rsp; StackCookie
0x1800339d7  call    __security_check_cookie
0x1800339dc  add     rsp, 0E8h
0x1800339e3  pop     r15
0x1800339e5  pop     r14
0x1800339e7  pop     r13
0x1800339e9  pop     r12
0x1800339eb  pop     rdi
0x1800339ec  pop     rsi
0x1800339ed  pop     rbx
0x1800339ee  pop     rbp
0x1800339ef  retn
```
