# StringPolicyFn

- ea: `0x180034300`
- end: `0x180034428`
- name: `StringPolicyFn`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180013900`
- `0x1800159a0`
- `0x18001fd10`
- `0x1800206f4`
- `0x180021ec0`
- `0x180032880`
- `0x180032988`
- `0x180034300`
- `0x180039bb4`

## string_xrefs

- `0x18003438f`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall StringPolicyFn(__int64 a1, _QWORD *a2)
{
  int ApplicationSetting; // eax
  __int64 v6; // rbx
  int v7; // eax
  int v8; // [rsp+20h] [rbp-60h]
  char v9; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+44h] [rbp-3Ch] BYREF
  char v11; // [rsp+48h] [rbp-38h] BYREF
  _OWORD v12[2]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v12[0] = 0;
  if ( (unsigned __int8)SIPolicyIsBasePolicy(a1) )
  {
    v10 = 0;
    std::vector<std::vector<AppSettingsQuery<std::wstring>>>::emplace_back<int>(a2 + 3, &v10);
  }
  ApplicationSetting = SIPolicyGetApplicationSetting(
                         a1,
                         *a2,
                         a2[1],
                         (unsigned int)&v11,
                         (__int64)&v10,
                         (__int64)v12,
                         (__int64)v12 + 8);
  v10 = ApplicationSetting;
  if ( ApplicationSetting != -1073741275 )
  {
    if ( ApplicationSetting < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x20F,
               (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
               (const char *)(unsigned int)ApplicationSetting,
               v8);
    if ( LOWORD(v12[0]) )
    {
      v6 = a2[4];
      v7 = std::wstring::wstring(v12, *((_QWORD *)&v12[0] + 1), (unsigned __int64)LOWORD(v12[0]) >> 1);
      v9 = *(_BYTE *)(a1 + 46) & 1;
      std::vector<AppSettingsQuery<std::wstring>>::emplace_back<_GUID const &,unsigned char,std::wstring,long &>(
        v6 - 24,
        a1 + (*(_DWORD *)(a1 + 40) < 6u ? 16 : 704),
        (unsigned int)&v9,
        v7,
        (__int64)&v10);
      std::wstring::~wstring(v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180034300  mov     [rsp-18h+arg_10], rbx
0x180034305  push    rbp
0x180034306  push    rsi
0x180034307  push    rdi
0x180034308  mov     rbp, rsp
0x18003430b  sub     rsp, 80h
0x180034312  mov     rax, cs:__security_cookie
0x180034319  xor     rax, rsp
0x18003431c  mov     [rbp+var_10], rax
0x180034320  mov     rbx, rdx
0x180034323  mov     rdi, rcx
0x180034326  xorps   xmm0, xmm0
0x180034329  movups  [rbp+var_30], xmm0
0x18003432d  call    SIPolicyIsBasePolicy
0x180034332  xor     esi, esi
0x180034334  test    al, al
0x180034336  jz      short loc_180034348
0x180034338  mov     [rbp+var_3C], esi
0x18003433b  lea     rcx, [rbx+18h]
0x18003433f  lea     rdx, [rbp+var_3C]
0x180034343  call    ??$emplace_back@H@?$vector@V?$vector@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@std@@@std@@V?$allocator@V?$vector@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@std@@@std@@@2@@std@@QEAAAEAV?$vector@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@std@@@1@$$QEAH@Z; std::vector<std::vector<AppSettingsQuery<std::wstring>>>::emplace_back<int>(int &&)
0x180034348  lea     rax, [rbp+var_30+8]
0x18003434c  mov     [rsp+80h+var_50], rax
0x180034351  lea     rax, [rbp+var_30]
0x180034355  mov     [rsp+80h+var_58], rax
0x18003435a  lea     rax, [rbp+var_3C]
0x18003435e  mov     qword ptr [rsp+80h+var_60], rax; int
0x180034363  lea     r9, [rbp+var_38]
0x180034367  mov     r8, [rbx+8]
0x18003436b  mov     rdx, [rbx]
0x18003436e  mov     rcx, rdi
0x180034371  call    SIPolicyGetApplicationSetting
0x180034376  mov     [rbp+var_3C], eax
0x180034379  cmp     eax, 0C0000225h
0x18003437e  jz      loc_180034407
0x180034384  test    eax, eax
0x180034386  jns     short loc_1800343A2
0x180034388  mov     rcx, [rbp+18h]; this
0x18003438c  mov     r9d, eax; char *
0x18003438f  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180034396  mov     edx, 20Fh; void *
0x18003439b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800343a0  jmp     short loc_180034409
0x1800343a2  movzx   ecx, word ptr [rbp+var_30]
0x1800343a6  test    cx, cx
0x1800343a9  jz      short loc_180034407
0x1800343ab  mov     rbx, [rbx+20h]
0x1800343af  mov     r8d, ecx
0x1800343b2  shr     r8, 1
0x1800343b5  mov     rdx, qword ptr [rbp+var_30+8]
0x1800343b9  lea     rcx, [rbp+var_30]
0x1800343bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800343c2  nop
0x1800343c3  mov     dl, [rdi+2Eh]
0x1800343c6  and     dl, 1
0x1800343c9  mov     [rbp+var_40], dl
0x1800343cc  cmp     dword ptr [rdi+28h], 6
0x1800343d0  sbb     rdx, rdx
0x1800343d3  and     rdx, 0FFFFFFFFFFFFFD50h
0x1800343da  add     rdx, 2C0h
0x1800343e1  add     rdx, rdi
0x1800343e4  lea     rcx, [rbp+var_3C]
0x1800343e8  mov     qword ptr [rsp+80h+var_60], rcx
0x1800343ed  mov     r9, rax
0x1800343f0  lea     r8, [rbp+var_40]
0x1800343f4  lea     rcx, [rbx-18h]
0x1800343f8  call    ??$emplace_back@AEBU_GUID@@EV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAJ@?$vector@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@V?$allocator@U?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@@std@@@std@@QEAAAEAU?$AppSettingsQuery@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@AEBU_GUID@@$$QEAE$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAJ@Z; std::vector<AppSettingsQuery<std::wstring>>::emplace_back<_GUID const &,uchar,std::wstring,long &>(_GUID const &,uchar &&,std::wstring &&,long &)
0x1800343fd  nop
0x1800343fe  lea     rcx, [rbp+var_30]
0x180034402  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034407  xor     eax, eax
0x180034409  mov     rcx, [rbp+var_10]
0x18003440d  xor     rcx, rsp; StackCookie
0x180034410  call    __security_check_cookie
0x180034415  mov     rbx, [rsp+80h+arg_10]
0x18003441d  add     rsp, 80h
0x180034424  pop     rdi
0x180034425  pop     rsi
0x180034426  pop     rbp
0x180034427  retn
```
