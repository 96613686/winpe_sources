# OPCODE_LIST::AddRef(WinMetaData const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ETW_PROVIDER_ENTRY *,OPCODE_ENTRY const * &,TASK_ENTRY *)

- ea: `0x18003410c`
- end: `0x1800342e6`
- name: `?AddRef@OPCODE_LIST@@QEAAJAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVETW_PROVIDER_ENTRY@@AEAPEBVOPCODE_ENTRY@@PEAVTASK_ENTRY@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001ac70`

## callees

- `0x18001e284`
- `0x18001ed1c`
- `0x18002c570`
- `0x18002e8f4`
- `0x1800313b4`
- `0x180032cac`
- `0x180033df0`
- `0x18003410c`
- `0x18003ab5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OPCODE_LIST::AddRef(STRING_LIST **a1, __int64 a2, _QWORD *a3, __int64 a4, _QWORD *a5, __int64 a6)
{
  _QWORD *v8; // rbx
  unsigned int v9; // r14d
  __int64 *v10; // rdi
  KEYWORD_ENTRY *v11; // rsi
  KEYWORD_ENTRY *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v18; // rbx
  KEYWORD_ENTRY *v19; // rsi
  KEYWORD_ENTRY **v20; // rdx
  __int128 v21; // [rsp+40h] [rbp-40h] BYREF
  __int128 v22; // [rsp+50h] [rbp-30h] BYREF
  __int128 v23; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+70h] [rbp-10h] BYREF
  KEYWORD_ENTRY *v27; // [rsp+D8h] [rbp+58h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = (__int64 *)(a4 + 344);
  v11 = *(KEYWORD_ENTRY **)(a4 + 344);
  v12 = *(KEYWORD_ENTRY **)(a4 + 352);
  v27 = v12;
  while ( v11 != v12 )
  {
    v13 = *(_QWORD **)v11;
    if ( a3[3] <= 7u )
      v14 = a3;
    else
      v14 = (_QWORD *)*a3;
    v15 = v13[2];
    if ( v13[3] > 7u )
      v13 = (_QWORD *)*v13;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v13, v15, v14, a3[2]) )
    {
      v8 = *(_QWORD **)v11;
      v16 = *(_QWORD *)(*(_QWORD *)v11 + 128LL);
      if ( v16 == a6 )
      {
        *a5 = v8;
        return 0;
      }
      if ( v16 )
      {
        v9 = -1073221754;
        if ( a6 )
          v9 = -1073221753;
      }
      else
      {
        v9 = 0;
      }
    }
    v11 = (KEYWORD_ENTRY *)((char *)v11 + 8);
    v12 = v27;
  }
  if ( v8 )
  {
    *a5 = v8;
    return v9;
  }
  v21 = 0;
  v22 = *(_OWORD *)std::wstring::operator std::wstring_view(a3, v24);
  v23 = *(_OWORD *)(a2 + 64);
  v18 = WinMetaData::GenericFindOrThrow<WinMetaTask>(&v23, &v22, &v21);
  *(_QWORD *)&v21 = 0;
  std::make_unique<OPCODE_ENTRY,std::nullptr_t,0>(&v27, &v21);
  v19 = v27;
  std::wstring::_Assign<wchar_t>(v27, *(_QWORD *)v18);
  std::wstring::_Assign<wchar_t>((char *)v19 + 40, *(_QWORD *)(v18 + 16));
  *((_BYTE *)v19 + 32) = *(_BYTE *)(v18 + 40);
  *((_BYTE *)v19 + 112) = 1;
  STRING_LIST::ReferenceStringFromWinmeta(
    *a1,
    *(struct WinMetaString **)(v18 + 32),
    (__int64)L"opcode",
    a4,
    (__int64)v19 + 120,
    (__int64)v19 + 72);
  v20 = (KEYWORD_ENTRY **)v10[1];
  if ( v20 == (KEYWORD_ENTRY **)v10[2] )
  {
    std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(
      v10,
      (__int64)v20,
      (__int64 *)&v27);
  }
  else
  {
    v27 = 0;
    *v20 = v19;
    v10[1] += 8;
  }
  *a5 = *(_QWORD *)(*(_QWORD *)(a4 + 352) - 8LL);
  std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(&v27);
  return 0;
}

```

## disassembly

```asm
0x18003410c  mov     [rsp-38h+arg_8], rdx
0x180034111  mov     [rsp-38h+arg_0], rcx
0x180034116  push    rbp
0x180034117  push    rbx
0x180034118  push    rsi
0x180034119  push    rdi
0x18003411a  push    r13
0x18003411c  push    r14
0x18003411e  push    r15
0x180034120  mov     rbp, rsp
0x180034123  sub     rsp, 80h
0x18003412a  mov     r13, r9
0x18003412d  mov     r15, r8
0x180034130  xor     ebx, ebx
0x180034132  xor     r14d, r14d
0x180034135  lea     rdi, [r9+158h]
0x18003413c  mov     rsi, [rdi]
0x18003413f  mov     rax, [rdi+8]
0x180034143  mov     [rbp+arg_18], rax
0x180034147  cmp     rsi, rax
0x18003414a  jz      short loc_1800341BC
0x18003414c  mov     rcx, [rsi]
0x18003414f  cmp     qword ptr [r15+18h], 7
0x180034154  jbe     short loc_18003415B
0x180034156  mov     r8, [r15]
0x180034159  jmp     short loc_18003415E
0x18003415b  mov     r8, r15
0x18003415e  mov     rdx, [rcx+10h]
0x180034162  cmp     qword ptr [rcx+18h], 7
0x180034167  jbe     short loc_18003416C
0x180034169  mov     rcx, [rcx]
0x18003416c  mov     r9, [r15+10h]
0x180034170  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180034175  test    al, al
0x180034177  jz      short loc_1800341A6
0x180034179  mov     rbx, [rsi]
0x18003417c  mov     rax, [rbx+80h]
0x180034183  cmp     rax, [rbp+arg_28]
0x180034187  jz      short loc_1800341B0
0x180034189  test    rax, rax
0x18003418c  jnz     short loc_180034193
0x18003418e  xor     r14d, r14d
0x180034191  jmp     short loc_1800341A6
0x180034193  cmp     [rbp+arg_28], 0
0x180034198  mov     r14d, 0C007EF86h
0x18003419e  jz      short loc_1800341A6
0x1800341a0  mov     r14d, 0C007EF87h
0x1800341a6  add     rsi, 8
0x1800341aa  mov     rax, [rbp+arg_18]
0x1800341ae  jmp     short loc_180034147
0x1800341b0  mov     rax, [rbp+arg_20]
0x1800341b4  mov     [rax], rbx
0x1800341b7  jmp     loc_1800342D2
0x1800341bc  test    rbx, rbx
0x1800341bf  jz      short loc_1800341D0
0x1800341c1  mov     rcx, [rbp+arg_20]
0x1800341c5  mov     [rcx], rbx
0x1800341c8  mov     eax, r14d
0x1800341cb  jmp     loc_1800342D4
0x1800341d0  lea     rdx, [rbp+var_10]
0x1800341d4  mov     rcx, r15
0x1800341d7  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800341dc  xorps   xmm0, xmm0
0x1800341df  movdqa  [rbp+var_40], xmm0
0x1800341e4  movups  xmm1, xmmword ptr [rax]
0x1800341e7  movdqu  [rbp+var_30], xmm1
0x1800341ec  mov     rax, [rbp+arg_8]
0x1800341f0  movups  xmm0, xmmword ptr [rax+40h]
0x1800341f4  movdqu  [rbp+var_20], xmm0
0x1800341f9  lea     r8, [rbp+var_40]
0x1800341fd  lea     rdx, [rbp+var_30]
0x180034201  lea     rcx, [rbp+var_20]
0x180034205  call    ??$GenericFindOrThrow@UWinMetaTask@@@WinMetaData@@SAAEBUWinMetaTask@@V?$span@$$CBUWinMetaTask@@$0?0@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@1@Z; WinMetaData::GenericFindOrThrow<WinMetaTask>(std::span<WinMetaTask const,-1>,std::wstring_view,std::wstring_view)
0x18003420a  mov     rbx, rax
0x18003420d  mov     qword ptr [rbp+var_40], 0
0x180034215  lea     rdx, [rbp+var_40]
0x180034219  lea     rcx, [rbp+arg_18]
0x18003421d  call    ??$make_unique@VOPCODE_ENTRY@@$$T$0A@@std@@YA?AV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@0@$$QEA$$T@Z
0x180034222  nop
0x180034223  mov     r8, [rbx+8]
0x180034227  mov     rdx, [rbx]
0x18003422a  mov     rsi, [rbp+arg_18]
0x18003422e  mov     rcx, rsi
0x180034231  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180034236  lea     rcx, [rsi+28h]
0x18003423a  mov     r8, [rbx+18h]
0x18003423e  mov     rdx, [rbx+10h]
0x180034242  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180034247  mov     al, [rbx+28h]
0x18003424a  mov     [rsi+20h], al
0x18003424d  mov     byte ptr [rsi+70h], 1
0x180034251  lea     rax, [rsi+48h]
0x180034255  lea     rcx, [rsi+78h]
0x180034259  movzx   r9d, byte ptr [rsi+20h]
0x18003425e  mov     [rsp+80h+var_48], rax; __int64
0x180034263  mov     [rsp+80h+var_50], rcx; __int64
0x180034268  mov     [rsp+80h+var_58], r13; __int64
0x18003426d  lea     rax, aOpcode; "opcode"
0x180034274  mov     [rsp+80h+var_60], rax; __int64
0x180034279  mov     r8d, 1
0x18003427f  mov     rdx, [rbx+20h]; struct WinMetaString *
0x180034283  mov     rcx, [rbp+arg_0]
0x180034287  mov     rcx, [rcx]; this
0x18003428a  call    ?ReferenceStringFromWinmeta@STRING_LIST@@QEAAXPEBUWinMetaString@@W4TableType@@_KPEB_WAEAVETW_PROVIDER_ENTRY@@PEAPEAVSTRING_ENTRY@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; STRING_LIST::ReferenceStringFromWinmeta(WinMetaString const *,TableType,unsigned __int64,wchar_t const *,ETW_PROVIDER_ENTRY &,STRING_ENTRY * *,std::wstring *)
0x18003428f  mov     rdx, [rdi+8]
0x180034293  cmp     rdx, [rdi+10h]
0x180034297  jz      short loc_1800342AB
0x180034299  mov     [rbp+arg_18], 0
0x1800342a1  mov     [rdx], rsi
0x1800342a4  add     qword ptr [rdi+8], 8
0x1800342a9  jmp     short loc_1800342B7
0x1800342ab  lea     r8, [rbp+arg_18]
0x1800342af  mov     rcx, rdi
0x1800342b2  call    ??$_Emplace_reallocate@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<OPCODE_ENTRY>>::_Emplace_reallocate<std::unique_ptr<OPCODE_ENTRY>>(std::unique_ptr<OPCODE_ENTRY> * const,std::unique_ptr<OPCODE_ENTRY> &&)
0x1800342b7  mov     rax, [r13+160h]
0x1800342be  mov     rcx, [rax-8]
0x1800342c2  mov     rax, [rbp+arg_20]
0x1800342c6  mov     [rax], rcx
0x1800342c9  lea     rcx, [rbp+arg_18]
0x1800342cd  call    ??1?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@QEAA@XZ; std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(void)
0x1800342d2  xor     eax, eax
0x1800342d4  add     rsp, 80h
0x1800342db  pop     r15
0x1800342dd  pop     r14
0x1800342df  pop     r13
0x1800342e1  pop     rdi
0x1800342e2  pop     rsi
0x1800342e3  pop     rbx
0x1800342e4  pop     rbp
0x1800342e5  retn
```
