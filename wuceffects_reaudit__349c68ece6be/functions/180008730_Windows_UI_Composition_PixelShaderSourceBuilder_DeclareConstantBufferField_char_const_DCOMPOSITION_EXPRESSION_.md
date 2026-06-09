# Windows::UI::Composition::PixelShaderSourceBuilder::DeclareConstantBufferField(char const *,DCOMPOSITION_EXPRESSION_TYPE,uint const *)

- ea: `0x180008730`
- end: `0x18000889a`
- name: `?DeclareConstantBufferField@PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4DCOMPOSITION_EXPRESSION_TYPE@@PEBI@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002e78`

## callees

- `0x180003ad0`
- `0x1800061b0`
- `0x180007920`
- `0x180007d80`
- `0x180008670`
- `0x180008730`
- `0x180021060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltoa_s` at `0x1800087f4`
- `api-ms-win-crt-private-l1-1-0!_o__ltoa_s` at `0x1800087f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int8 *__fastcall Windows::UI::Composition::PixelShaderSourceBuilder::DeclareConstantBufferField(
        _DWORD *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5)
{
  Windows::UI::Composition::StringBuilder *v8; // rbx
  __int64 v9; // rdx
  const char *HlslTypeName; // rax
  int v11; // edi
  char v13[8]; // [rsp+20h] [rbp-30h] BYREF
  int v14; // [rsp+28h] [rbp-28h]
  unsigned __int8 *v15; // [rsp+30h] [rbp-20h]
  char Buffer[16]; // [rsp+38h] [rbp-18h] BYREF

  v15 = a2;
  Windows::UI::Composition::PixelShaderSourceBuilder::GenerateVariableName(a1, a2, a3);
  v14 = 1;
  v8 = (Windows::UI::Composition::StringBuilder *)(a1 + 18);
  Windows::UI::Composition::StringBuilder::Append(v8, "    ");
  if ( a4 == 265 )
    Windows::UI::Composition::StringBuilder::Append(v8, "row_major ");
  LOBYTE(v9) = 1;
  HlslTypeName = (const char *)Windows::UI::Composition::PixelShaderSourceBuilder::GetHlslTypeName(a4, v9);
  Windows::UI::Composition::StringBuilder::Append(v8, HlslTypeName);
  v13[0] = 32;
  std::deque<char>::push_back(v8, v13);
  Windows::UI::Composition::StringBuilder::Append((__int64)v8, a2);
  if ( a5 )
  {
    Windows::UI::Composition::StringBuilder::Append(v8, " : packoffset(c");
    *(_OWORD *)Buffer = 0;
    _ltoa_s(*a5 >> 2, Buffer, 0x10u, 10);
    Windows::UI::Composition::StringBuilder::Append(v8, Buffer);
    v11 = *a5 & 3;
    if ( v11 )
    {
      v13[0] = 46;
      std::deque<char>::push_back(v8, v13);
      v13[0] = aXyzw[v11];
      std::deque<char>::push_back(v8, v13);
    }
    v13[0] = 41;
    std::deque<char>::push_back(v8, v13);
  }
  v13[0] = 59;
  std::deque<char>::push_back(v8, v13);
  v13[0] = 10;
  std::deque<char>::push_back(v8, v13);
  return a2;
}

```

## disassembly

```asm
0x180008730  push    rbp
0x180008732  push    rbx
0x180008733  push    rsi
0x180008734  push    rdi
0x180008735  push    r14
0x180008737  mov     rbp, rsp
0x18000873a  sub     rsp, 50h
0x18000873e  mov     rax, cs:__security_cookie
0x180008745  xor     rax, rsp
0x180008748  mov     [rbp+var_8], rax
0x18000874c  mov     r14d, r9d
0x18000874f  mov     rsi, rdx
0x180008752  mov     rbx, rcx
0x180008755  mov     [rbp+var_20], rdx
0x180008759  mov     rdi, [rbp+arg_20]
0x18000875d  mov     [rbp+var_28], 0
0x180008764  mov     r9d, 3
0x18000876a  call    ?GenerateVariableName@PixelShaderSourceBuilder@Composition@UI@Windows@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDW4VariableScope@1234@@Z; Windows::UI::Composition::PixelShaderSourceBuilder::GenerateVariableName(char const *,Windows::UI::Composition::PixelShaderSourceBuilder::VariableScope)
0x18000876f  mov     [rbp+var_28], 1
0x180008776  add     rbx, 48h ; 'H'
0x18000877a  lea     rdx, asc_18003403C; "    "
0x180008781  mov     rcx, rbx; this
0x180008784  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180008789  cmp     r14d, 109h
0x180008790  jz      loc_180008857
0x180008796  mov     dl, 1
0x180008798  mov     ecx, r14d
0x18000879b  call    ?GetHlslTypeName@PixelShaderSourceBuilder@Composition@UI@Windows@@SAPEBDW4DCOMPOSITION_EXPRESSION_TYPE@@_N@Z; Windows::UI::Composition::PixelShaderSourceBuilder::GetHlslTypeName(DCOMPOSITION_EXPRESSION_TYPE,bool)
0x1800087a0  mov     rdx, rax; char *
0x1800087a3  mov     rcx, rbx; this
0x1800087a6  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800087ab  mov     [rbp+var_30], 20h ; ' '
0x1800087af  lea     rdx, [rbp+var_30]
0x1800087b3  mov     rcx, rbx
0x1800087b6  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x1800087bb  mov     rdx, rsi
0x1800087be  mov     rcx, rbx
0x1800087c1  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Windows::UI::Composition::StringBuilder::Append(std::string const &)
0x1800087c6  test    rdi, rdi
0x1800087c9  jz      short loc_18000881D
0x1800087cb  lea     rdx, aPackoffsetC; " : packoffset(c"
0x1800087d2  mov     rcx, rbx; this
0x1800087d5  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x1800087da  xorps   xmm0, xmm0
0x1800087dd  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800087e1  mov     ecx, [rdi]
0x1800087e3  shr     ecx, 2; Value
0x1800087e6  mov     r9d, 0Ah; Radix
0x1800087ec  lea     r8d, [r9+6]; BufferCount
0x1800087f0  lea     rdx, [rbp+Buffer]; Buffer
0x1800087f4  call    cs:__imp__ltoa_s
0x1800087fa  lea     rdx, [rbp+Buffer]; char *
0x1800087fe  mov     rcx, rbx; this
0x180008801  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180008806  mov     edi, [rdi]
0x180008808  and     edi, 3
0x18000880b  jnz     short loc_18000886B
0x18000880d  mov     [rbp+var_30], 29h ; ')'
0x180008811  lea     rdx, [rbp+var_30]
0x180008815  mov     rcx, rbx
0x180008818  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x18000881d  mov     [rbp+var_30], 3Bh ; ';'
0x180008821  lea     rdx, [rbp+var_30]
0x180008825  mov     rcx, rbx
0x180008828  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x18000882d  mov     [rbp+var_30], 0Ah
0x180008831  lea     rdx, [rbp+var_30]
0x180008835  mov     rcx, rbx
0x180008838  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x18000883d  mov     rax, rsi
0x180008840  mov     rcx, [rbp+var_8]
0x180008844  xor     rcx, rsp; StackCookie
0x180008847  call    __security_check_cookie
0x18000884c  add     rsp, 50h
0x180008850  pop     r14
0x180008852  pop     rdi
0x180008853  pop     rsi
0x180008854  pop     rbx
0x180008855  pop     rbp
0x180008856  retn
0x180008857  lea     rdx, aRowMajor; "row_major "
0x18000885e  mov     rcx, rbx; this
0x180008861  call    ?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD@Z; Windows::UI::Composition::StringBuilder::Append(char const *)
0x180008866  jmp     loc_180008796
0x18000886b  mov     [rbp+var_30], 2Eh ; '.'
0x18000886f  lea     rdx, [rbp+var_30]
0x180008873  mov     rcx, rbx
0x180008876  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x18000887b  lea     rcx, aXyzw; "xyzw"
0x180008882  mov     al, [rdi+rcx]
0x180008885  mov     [rbp+var_30], al
0x180008888  lea     rdx, [rbp+var_30]
0x18000888c  mov     rcx, rbx
0x18000888f  call    ?push_back@?$deque@DV?$allocator@D@std@@@std@@QEAAXAEBD@Z; std::deque<char>::push_back(char const &)
0x180008894  jmp     loc_18000880D
```
