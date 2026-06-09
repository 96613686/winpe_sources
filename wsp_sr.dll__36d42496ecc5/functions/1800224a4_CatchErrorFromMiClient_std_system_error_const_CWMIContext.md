# CatchErrorFromMiClient(std::system_error const &,CWMIContext &)

- ea: `0x1800224a4`
- end: `0x1800225c4`
- name: `?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(const struct std::system_error *, struct CWMIContext *)`
- caller_count: `19`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180029f5a`
- `0x18002a4f0`
- `0x18002a524`
- `0x18002a591`
- `0x18002a5d7`
- `0x18002a677`
- `0x18002a6f3`
- `0x18002a793`
- `0x18002a7dc`
- `0x18002a97b`
- `0x18002ab31`
- `0x18002aba1`
- `0x18002abe4`
- `0x18002b00a`
- `0x18002b238`
- `0x18002b481`
- `0x18002b4d9`
- `0x18002bd4a`
- `0x18002bd7e`

## callees

- `0x1800014e0`
- `0x1800066d8`
- `0x180008f64`
- `0x18000dafc`
- `0x18000dc04`
- `0x18000de10`
- `0x1800216fc`
- `0x180021744`
- `0x180021b50`
- `0x1800224a4`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall CatchErrorFromMiClient(const struct std::system_error *a1, struct CWMIContext *a2)
{
  unsigned int *v3; // r8
  unsigned int *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // r8
  enum _MI_Result v7; // ebx
  _QWORD *v8; // rdi
  void (__fastcall *v9)(struct CWMIContext *, _QWORD, __int64); // rdi
  char *v10; // r8
  _QWORD *v11; // rdx
  __int64 v12; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+30h] [rbp-40h]
  unsigned __int64 v16; // [rsp+38h] [rbp-38h]
  _BYTE v17[32]; // [rsp+40h] [rbp-30h] BYREF

  std::string::string(v14, a2, a1);
  v4 = v3 + 6;
  if ( *(void ****)(*((_QWORD *)v3 + 4) + 8LL) == off_1800C3E28[0] )
  {
    v5 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v3 + 8LL))(v3);
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(v5 + v6) );
    std::string::_Assign<char>(v14, v5);
    v7 = *v4;
  }
  else
  {
    v8 = (_QWORD *)std::error_code::message(v3 + 6, v17);
    if ( v14 != v8 )
    {
      std::string::_Tidy_deallocate(v14);
      std::string::_Take_contents(v14, v8);
    }
    std::string::_Tidy_deallocate(v17);
    v7 = MapWinErrorToMIResult(*v4);
  }
  v9 = *(void (__fastcall **)(struct CWMIContext *, _QWORD, __int64))(*(_QWORD *)a2 + 16LL);
  if ( v16 > 0xF )
  {
    v11 = (_QWORD *)v14[0];
    v10 = (char *)(v14[0] + v15);
  }
  else
  {
    v10 = (char *)v14 + v15;
    v11 = v14;
  }
  v12 = std::wstring::wstring(v17, v11, v10);
  v9(a2, (unsigned int)v7, v12);
  std::wstring::_Tidy_deallocate((__int64)v17);
  std::string::_Tidy_deallocate(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800224a4  mov     [rsp-18h+arg_10], rbx
0x1800224a9  push    rbp
0x1800224aa  push    rsi
0x1800224ab  push    rdi
0x1800224ac  mov     rbp, rsp
0x1800224af  sub     rsp, 70h
0x1800224b3  mov     rax, cs:__security_cookie
0x1800224ba  xor     rax, rsp
0x1800224bd  mov     [rbp+var_10], rax
0x1800224c1  mov     rsi, rdx
0x1800224c4  mov     r8, rcx
0x1800224c7  lea     rcx, [rbp+var_50]
0x1800224cb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800224d0  nop
0x1800224d1  lea     rbx, [r8+18h]
0x1800224d5  mov     rdx, [r8+20h]
0x1800224d9  mov     rax, cs:off_1800C3E28
0x1800224e0  cmp     [rdx+8], rax
0x1800224e4  jnz     short loc_180022513
0x1800224e6  mov     rax, [r8]
0x1800224e9  mov     rcx, r8
0x1800224ec  mov     rax, [rax+8]
0x1800224f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224f5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800224f9  inc     r8
0x1800224fc  cmp     byte ptr [rax+r8], 0
0x180022501  jnz     short loc_1800224F9
0x180022503  mov     rdx, rax
0x180022506  lea     rcx, [rbp+var_50]
0x18002250a  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18002250f  mov     ebx, [rbx]
0x180022511  jmp     short loc_180022552
0x180022513  lea     rdx, [rbp+var_30]
0x180022517  mov     rcx, rbx
0x18002251a  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x18002251f  mov     rdi, rax
0x180022522  lea     rax, [rbp+var_50]
0x180022526  cmp     rax, rdi
0x180022529  jz      short loc_180022540
0x18002252b  lea     rcx, [rbp+var_50]
0x18002252f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022534  mov     rdx, rdi
0x180022537  lea     rcx, [rbp+var_50]
0x18002253b  call    ?_Take_contents@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXAEAV12@@Z; std::string::_Take_contents(std::string &)
0x180022540  lea     rcx, [rbp+var_30]
0x180022544  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022549  mov     ecx, [rbx]; unsigned int
0x18002254b  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180022550  mov     ebx, eax
0x180022552  mov     rcx, [rsi]
0x180022555  mov     rdi, [rcx+10h]
0x180022559  mov     r8, [rbp+var_40]
0x18002255d  cmp     [rbp+var_38], 0Fh
0x180022562  ja      short loc_180022571
0x180022564  lea     rax, [rbp+var_50]
0x180022568  add     r8, rax
0x18002256b  lea     rdx, [rbp+var_50]
0x18002256f  jmp     short loc_180022578
0x180022571  mov     rdx, [rbp+var_50]
0x180022575  add     r8, rdx
0x180022578  lea     rcx, [rbp+var_30]
0x18002257c  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x180022581  nop
0x180022582  mov     r8, rax
0x180022585  mov     edx, ebx
0x180022587  mov     rcx, rsi
0x18002258a  mov     rax, rdi
0x18002258d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022592  nop
0x180022593  lea     rcx, [rbp+var_30]
0x180022597  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002259c  nop
0x18002259d  lea     rcx, [rbp+var_50]
0x1800225a1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800225a6  mov     eax, ebx
0x1800225a8  mov     rcx, [rbp+var_10]
0x1800225ac  xor     rcx, rsp; StackCookie
0x1800225af  call    __security_check_cookie
0x1800225b4  mov     rbx, [rsp+70h+arg_10]
0x1800225bc  add     rsp, 70h
0x1800225c0  pop     rdi
0x1800225c1  pop     rsi
0x1800225c2  pop     rbp
0x1800225c3  retn
```
