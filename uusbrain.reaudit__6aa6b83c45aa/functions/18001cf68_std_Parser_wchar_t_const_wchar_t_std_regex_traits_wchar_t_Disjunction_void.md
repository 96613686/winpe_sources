# std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Disjunction(void)

- ea: `0x18001cf68`
- end: `0x18001d0a7`
- name: `?_Disjunction@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ`
- size: `319`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18000ea38`
- `0x180020770`
- `0x1800211a8`
- `0x1800211f4`

## callees

- `0x18001cf68`
- `0x18001d0b0`
- `0x18001e954`
- `0x18001e9b0`
- `0x18001eb84`
- `0x18001ec84`
- `0x180042bfc`

## pseudocode

```c
__int64 __fastcall std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Disjunction(__int64 a1)
{
  __int64 v1; // r13
  _DWORD *v2; // rsi
  __int64 result; // rax
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // r15
  __int64 v11; // rax
  __int64 i; // rcx
  _QWORD *v13; // rax

  v1 = *(_QWORD *)(a1 + 72);
  v2 = (_DWORD *)(a1 + 124);
  result = ((__int64 (*)(void))std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Alternative)();
  if ( (_BYTE)result )
  {
    v5 = a1 + 64;
  }
  else
  {
    if ( *v2 != 124 )
      return result;
    v5 = a1 + 64;
    v6 = std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_New_node(a1 + 64, 8);
    std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(a1 + 64, v6);
  }
  result = std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Begin_if(v5, v1);
  v7 = result;
  while ( *v2 == 124 )
  {
    std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(a1);
    if ( !(unsigned __int8)std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Alternative(a1) )
    {
      v8 = std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_New_node(v5, 8);
      std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(v5, v8);
    }
    v9 = *(_QWORD *)(v1 + 16);
    v10 = *(_QWORD *)(v7 + 16);
    *(_QWORD *)(v7 + 16) = 0;
    v11 = *(_QWORD *)(v5 + 8);
    *(_QWORD *)(v5 + 8) = v7;
    *(_QWORD *)(v7 + 16) = 0;
    *(_QWORD *)(v11 + 16) = v7;
    for ( i = *(_QWORD *)(v9 + 40); i; i = *(_QWORD *)(i + 40) )
      v9 = i;
    v13 = operator new(0x30u);
    v13[1] = 16;
    v13[3] = 0;
    *v13 = &std::_Node_if::`vftable';
    v13[4] = v7;
    v13[5] = 0;
    *(_QWORD *)(v9 + 40) = v13;
    v13[2] = v10;
    result = *(_QWORD *)(v9 + 40);
    *(_QWORD *)(v10 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18001cf68  mov     rax, rsp
0x18001cf6b  mov     [rax+8], rbx
0x18001cf6f  mov     [rax+10h], rbp
0x18001cf73  mov     [rax+18h], rsi
0x18001cf77  mov     [rax+20h], rdi
0x18001cf7b  push    r13
0x18001cf7d  push    r14
0x18001cf7f  push    r15
0x18001cf81  sub     rsp, 20h
0x18001cf85  mov     r13, [rcx+48h]
0x18001cf89  lea     rsi, [rcx+7Ch]
0x18001cf8d  mov     rbx, rcx
0x18001cf90  call    ?_Alternative@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAA_NXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Alternative(void)
0x18001cf95  test    al, al
0x18001cf97  jnz     short loc_18001CFC0
0x18001cf99  cmp     dword ptr [rsi], 7Ch ; '|'
0x18001cf9c  jnz     loc_18001D088
0x18001cfa2  lea     rdi, [rbx+40h]
0x18001cfa6  mov     edx, 8
0x18001cfab  mov     rcx, rdi
0x18001cfae  call    ?_New_node@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_New_node(std::_Node_type)
0x18001cfb3  mov     rdx, rax
0x18001cfb6  mov     rcx, rdi
0x18001cfb9  call    ?_End_group@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(std::_Node_base *)
0x18001cfbe  jmp     short loc_18001CFC4
0x18001cfc0  lea     rdi, [rbx+40h]
0x18001cfc4  mov     rdx, r13
0x18001cfc7  mov     rcx, rdi
0x18001cfca  call    ?_Begin_if@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAPEAV_Node_base@2@PEAV32@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Begin_if(std::_Node_base *)
0x18001cfcf  mov     rbp, rax
0x18001cfd2  jmp     loc_18001D07F
0x18001cfd7  mov     rcx, rbx
0x18001cfda  call    ?_Next@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(void)
0x18001cfdf  mov     rcx, rbx
0x18001cfe2  call    ?_Alternative@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAA_NXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Alternative(void)
0x18001cfe7  test    al, al
0x18001cfe9  jnz     short loc_18001D003
0x18001cfeb  mov     edx, 8
0x18001cff0  mov     rcx, rdi
0x18001cff3  call    ?_New_node@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_New_node(std::_Node_type)
0x18001cff8  mov     rdx, rax
0x18001cffb  mov     rcx, rdi
0x18001cffe  call    ?_End_group@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(std::_Node_base *)
0x18001d003  mov     r14, [r13+10h]
0x18001d007  mov     r15, [rbp+10h]
0x18001d00b  mov     qword ptr [rbp+10h], 0
0x18001d013  mov     rax, [rdi+8]
0x18001d017  mov     [rdi+8], rbp
0x18001d01b  mov     qword ptr [rbp+10h], 0
0x18001d023  mov     [rax+10h], rbp
0x18001d027  mov     rcx, [r14+28h]
0x18001d02b  test    rcx, rcx
0x18001d02e  jz      short loc_18001D03F
0x18001d030  mov     rax, [rcx+28h]
0x18001d034  mov     r14, rcx
0x18001d037  mov     rcx, rax
0x18001d03a  test    rax, rax
0x18001d03d  jnz     short loc_18001D030
0x18001d03f  mov     ecx, 30h ; '0'; Size
0x18001d044  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d049  lea     rcx, ??_7_Node_if@std@@6B@; const std::_Node_if::`vftable'
0x18001d050  mov     qword ptr [rax+8], 10h
0x18001d058  mov     qword ptr [rax+18h], 0
0x18001d060  mov     [rax], rcx
0x18001d063  mov     [rax+20h], rbp
0x18001d067  mov     qword ptr [rax+28h], 0
0x18001d06f  mov     [r14+28h], rax
0x18001d073  mov     [rax+10h], r15
0x18001d077  mov     rax, [r14+28h]
0x18001d07b  mov     [r15+18h], rax
0x18001d07f  cmp     dword ptr [rsi], 7Ch ; '|'
0x18001d082  jz      loc_18001CFD7
0x18001d088  mov     rbx, [rsp+38h+arg_0]
0x18001d08d  mov     rbp, [rsp+38h+arg_8]
0x18001d092  mov     rsi, [rsp+38h+arg_10]
0x18001d097  mov     rdi, [rsp+38h+arg_18]
0x18001d09c  add     rsp, 20h
0x18001d0a0  pop     r15
0x18001d0a2  pop     r14
0x18001d0a4  pop     r13
0x18001d0a6  retn
```
