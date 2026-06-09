# CatchErrorFromMiClient(std::system_error const &,CWMIContext &)

- ea: `0x180022660`
- end: `0x180022781`
- name: `?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z`
- size: `289`
- prototype: `enum _MI_Result __fastcall(const struct std::system_error *, struct CWMIContext *)`
- caller_count: `19`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002a40a`
- `0x18002a9bd`
- `0x18002a9f1`
- `0x18002aa5e`
- `0x18002aaa4`
- `0x18002ab44`
- `0x18002abc0`
- `0x18002ac60`
- `0x18002aca9`
- `0x18002ae48`
- `0x18002afff`
- `0x18002b06f`
- `0x18002b0b2`
- `0x18002b4e0`
- `0x18002b712`
- `0x18002b961`
- `0x18002b9b9`
- `0x18002c23e`
- `0x18002c272`

## callees

- `0x1800014e0`
- `0x180006724`
- `0x18000911c`
- `0x18000d9b8`
- `0x18000daf0`
- `0x18000dd0c`
- `0x180021890`
- `0x1800218d8`
- `0x180021cf0`
- `0x180022660`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  std::wstring::_Tidy_deallocate(v17);
  std::string::_Tidy_deallocate(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022660  mov     [rsp-18h+arg_10], rbx
0x180022665  push    rbp
0x180022666  push    rsi
0x180022667  push    rdi
0x180022668  mov     rbp, rsp
0x18002266b  sub     rsp, 70h
0x18002266f  mov     rax, cs:__security_cookie
0x180022676  xor     rax, rsp
0x180022679  mov     [rbp+var_10], rax
0x18002267d  mov     rsi, rdx
0x180022680  mov     r8, rcx
0x180022683  lea     rcx, [rbp+var_50]
0x180022687  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18002268c  nop
0x18002268d  lea     rbx, [r8+18h]
0x180022691  mov     rdx, [r8+20h]
0x180022695  mov     rax, cs:off_1800C3E28
0x18002269c  cmp     [rdx+8], rax
0x1800226a0  jnz     short loc_1800226CF
0x1800226a2  mov     rax, [r8]
0x1800226a5  mov     rcx, r8
0x1800226a8  mov     rax, [rax+8]
0x1800226ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800226b5  inc     r8
0x1800226b8  cmp     byte ptr [rax+r8], 0
0x1800226bd  jnz     short loc_1800226B5
0x1800226bf  mov     rdx, rax
0x1800226c2  lea     rcx, [rbp+var_50]
0x1800226c6  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1800226cb  mov     ebx, [rbx]
0x1800226cd  jmp     short loc_18002270E
0x1800226cf  lea     rdx, [rbp+var_30]
0x1800226d3  mov     rcx, rbx
0x1800226d6  call    ?message@error_code@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::error_code::message(void)
0x1800226db  mov     rdi, rax
0x1800226de  lea     rax, [rbp+var_50]
0x1800226e2  cmp     rax, rdi
0x1800226e5  jz      short loc_1800226FC
0x1800226e7  lea     rcx, [rbp+var_50]
0x1800226eb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800226f0  mov     rdx, rdi
0x1800226f3  lea     rcx, [rbp+var_50]
0x1800226f7  call    ?_Take_contents@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXAEAV12@@Z; std::string::_Take_contents(std::string &)
0x1800226fc  lea     rcx, [rbp+var_30]
0x180022700  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022705  mov     ecx, [rbx]; unsigned int
0x180022707  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18002270c  mov     ebx, eax
0x18002270e  mov     rcx, [rsi]
0x180022711  mov     rdi, [rcx+10h]
0x180022715  mov     r8, [rbp+var_40]
0x180022719  cmp     [rbp+var_38], 0Fh
0x18002271e  ja      short loc_18002272D
0x180022720  lea     rax, [rbp+var_50]
0x180022724  add     r8, rax
0x180022727  lea     rdx, [rbp+var_50]
0x18002272b  jmp     short loc_180022734
0x18002272d  mov     rdx, [rbp+var_50]
0x180022731  add     r8, rdx
0x180022734  lea     rcx, [rbp+var_30]
0x180022738  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<wchar_t> const &)
0x18002273d  nop
0x18002273e  mov     r8, rax
0x180022741  mov     edx, ebx
0x180022743  mov     rcx, rsi
0x180022746  mov     rax, rdi
0x180022749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002274e  nop
0x18002274f  lea     rcx, [rbp+var_30]
0x180022753  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022758  nop
0x180022759  lea     rcx, [rbp+var_50]
0x18002275d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180022762  mov     eax, ebx
0x180022764  mov     rcx, [rbp+var_10]
0x180022768  xor     rcx, rsp; StackCookie
0x18002276b  call    __security_check_cookie
0x180022770  mov     rbx, [rsp+70h+arg_10]
0x180022778  add     rsp, 70h
0x18002277c  pop     rdi
0x18002277d  pop     rsi
0x18002277e  pop     rbp
0x18002277f  retn
```
