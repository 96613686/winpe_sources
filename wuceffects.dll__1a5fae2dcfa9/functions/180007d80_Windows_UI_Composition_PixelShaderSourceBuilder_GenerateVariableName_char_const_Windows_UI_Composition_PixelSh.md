# Windows::UI::Composition::PixelShaderSourceBuilder::GenerateVariableName(char const *,Windows::UI::Composition::PixelShaderSourceBuilder::VariableScope)

- ea: `0x180007d80`
- end: `0x180007edd`
- name: `?GenerateVariableName@PixelShaderSourceBuilder@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4VariableScope@1234@@Z`
- size: `349`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002928`
- `0x180006e1c`
- `0x180008730`

## callees

- `0x180004db8`
- `0x180007d80`
- `0x180007ee4`
- `0x18001de54`
- `0x180021060`
- `0x180026144`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180007e0d`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180007e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::UI::Composition::PixelShaderSourceBuilder::GenerateVariableName(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  int v6; // r9d
  __int64 v7; // rbx
  __int64 v8; // r8
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12[4]; // [rsp+30h] [rbp-58h] BYREF
  char v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+51h] [rbp-37h]
  char v15; // [rsp+59h] [rbp-2Fh]

  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 0;
  std::string::_Construct_empty(a2);
  if ( v6 )
  {
    v10 = v6 - 1;
    if ( v10 )
    {
      if ( (unsigned int)(v10 - 1) > 1 )
      {
        std::wstring::wstring(v12, L"Unexpected variable scope.");
        Windows::UI::Composition::OriginateException(v11, v12);
      }
    }
  }
  std::string::_Append<char>(a2);
  v13 = 0;
  v14 = 0;
  v15 = 0;
  _o__itoa_s((unsigned int)*a1, &v13, 10);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(&v13 + v8) );
  std::string::_Append<char>(a2);
  ++*a1;
  std::string::_Append<char>(a2);
  do
    ++v7;
  while ( *(_BYTE *)(a3 + v7) );
  std::string::_Append<char>(a2);
  return a2;
}

```

## disassembly

```asm
0x180007d80  mov     [rsp+arg_18], rbx
0x180007d85  push    rsi
0x180007d86  push    rdi
0x180007d87  push    r14
0x180007d89  sub     rsp, 70h
0x180007d8d  mov     rax, cs:__security_cookie
0x180007d94  xor     rax, rsp
0x180007d97  mov     [rsp+88h+var_28], rax
0x180007d9c  mov     rdi, r8
0x180007d9f  mov     rsi, rdx
0x180007da2  mov     r14, rcx
0x180007da5  mov     [rsp+88h+var_60], rdx
0x180007daa  xor     eax, eax
0x180007dac  mov     [rsp+88h+var_68], eax
0x180007db0  xorps   xmm0, xmm0
0x180007db3  movups  xmmword ptr [rdx], xmm0
0x180007db6  mov     [rdx+10h], rax
0x180007dba  mov     [rdx+18h], rax
0x180007dbe  mov     rcx, rdx
0x180007dc1  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x180007dc6  mov     [rsp+88h+var_68], 1
0x180007dce  test    r9d, r9d
0x180007dd1  jnz     loc_180007E89
0x180007dd7  lea     rdx, asc_18003404C; "l"
0x180007dde  mov     r8d, 1
0x180007de4  mov     rcx, rsi; Src
0x180007de7  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180007dec  mov     [rsp+88h+var_38], 0
0x180007df1  xor     eax, eax
0x180007df3  mov     [rsp+88h+var_37], rax
0x180007df8  mov     [rsp+88h+var_2F], al
0x180007dfc  mov     r9d, 0Ah
0x180007e02  mov     r8d, r9d
0x180007e05  lea     rdx, [rsp+88h+var_38]
0x180007e0a  mov     ecx, [r14]
0x180007e0d  call    cs:__imp__o__itoa_s
0x180007e13  lea     rax, [rsp+88h+var_38]
0x180007e18  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007e1f  mov     r8, rbx
0x180007e22  inc     r8
0x180007e25  cmp     byte ptr [rax+r8], 0
0x180007e2a  jnz     short loc_180007E22
0x180007e2c  lea     rdx, [rsp+88h+var_38]
0x180007e31  mov     rcx, rsi; Src
0x180007e34  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180007e39  inc     dword ptr [r14]
0x180007e3c  mov     r8d, 1
0x180007e42  lea     rdx, asc_180034048; "_"
0x180007e49  mov     rcx, rsi; Src
0x180007e4c  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180007e51  inc     rbx
0x180007e54  cmp     byte ptr [rdi+rbx], 0
0x180007e58  jnz     short loc_180007E51
0x180007e5a  mov     r8, rbx
0x180007e5d  mov     rdx, rdi
0x180007e60  mov     rcx, rsi; Src
0x180007e63  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180007e68  mov     rax, rsi
0x180007e6b  mov     rcx, [rsp+88h+var_28]
0x180007e70  xor     rcx, rsp; StackCookie
0x180007e73  call    __security_check_cookie
0x180007e78  mov     rbx, [rsp+88h+arg_18]
0x180007e80  add     rsp, 70h
0x180007e84  pop     r14
0x180007e86  pop     rdi
0x180007e87  pop     rsi
0x180007e88  retn
0x180007e89  sub     r9d, 1
0x180007e8d  jnz     short loc_180007E9B
0x180007e8f  lea     rdx, aP; "p"
0x180007e96  jmp     loc_180007DDE
0x180007e9b  sub     r9d, 1
0x180007e9f  jz      short loc_180007ED0
0x180007ea1  cmp     r9d, 1
0x180007ea5  jnz     short loc_180007EB3
0x180007ea7  lea     rdx, aG_0; "g"
0x180007eae  jmp     loc_180007DDE
0x180007eb3  lea     rdx, aUnexpectedVari; "Unexpected variable scope."
0x180007eba  lea     rcx, [rsp+88h+var_58]
0x180007ebf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180007ec4  nop
0x180007ec5  lea     rdx, [rsp+88h+var_58]
0x180007eca  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180007ed0  lea     rdx, aK; "k"
0x180007ed7  jmp     loc_180007DDE
```
