# std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Wrapped_disjunction(void)

- ea: `0x180020770`
- end: `0x18002089f`
- name: `?_Wrapped_disjunction@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAA_NXZ`
- size: `303`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18001e9b0`

## callees

- `0x18001cd40`
- `0x18001cf68`
- `0x18001d0b0`
- `0x18001d12c`
- `0x18001dc30`
- `0x18001e954`
- `0x180020770`
- `0x1800211a8`
- `0x1800211f4`
- `0x18003fdc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Wrapped_disjunction(__int64 a1)
{
  int *v1; // rbx
  int v2; // eax
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v8; // edx
  __int64 v9; // rdi
  int v10; // edx
  bool v11; // cf
  __int64 v12; // rdx

  ++*(_DWORD *)(a1 + 28);
  v1 = (int *)(a1 + 124);
  v2 = *(_DWORD *)(a1 + 128);
  if ( (v2 & 0x8000000) == 0 && *v1 == 41 )
    std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Error(a1, 5);
  if ( (v2 & 0x20) == 0 || *v1 != 63 )
  {
    if ( (*(_DWORD *)(a1 + 112) & 0x200) == 0 )
    {
      v8 = *(_DWORD *)(a1 + 24) + 1;
      *(_DWORD *)(a1 + 24) = v8;
      if ( v8 >= 0x3E8 )
        std::_Xregex_error(12);
      v9 = std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Begin_capture_group(a1 + 64);
      std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Disjunction(a1);
      std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(a1 + 64, v9);
      v10 = *(_DWORD *)(a1 + 24);
      v11 = __CFADD__(v10, 1);
      v12 = (unsigned int)(v10 + 1);
      if ( v11 )
        v12 = -1;
      std::vector<bool>::resize(a1 + 32, v12);
      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * ((unsigned __int64)*(unsigned int *)(v9 + 32) >> 5)) |= 1 << (*(_BYTE *)(v9 + 32) & 0x1F);
      goto LABEL_17;
    }
LABEL_12:
    std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_noncapture_group(a1);
LABEL_17:
    --*(_DWORD *)(a1 + 28);
    return 1;
  }
  std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(a1);
  v4 = *v1;
  std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(a1);
  switch ( v4 )
  {
    case ':':
      goto LABEL_12;
    case '!':
      LOBYTE(v5) = 1;
      std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_assert_group(a1, v5);
      --*(_DWORD *)(a1 + 28);
      break;
    case '=':
      std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_assert_group(a1, 0);
      --*(_DWORD *)(a1 + 28);
      break;
    default:
      std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Error(v6, 14);
  }
  return 0;
}

```

## disassembly

```asm
0x180020770  mov     [rsp+arg_8], rbx
0x180020775  mov     [rsp+arg_10], rsi
0x18002077a  push    rdi
0x18002077b  sub     rsp, 20h
0x18002077f  inc     dword ptr [rcx+1Ch]
0x180020782  lea     rbx, [rcx+7Ch]
0x180020786  mov     eax, [rcx+80h]
0x18002078c  mov     rsi, rcx
0x18002078f  bt      eax, 1Bh
0x180020793  jb      short loc_18002079E
0x180020795  cmp     dword ptr [rbx], 29h ; ')'
0x180020798  jz      loc_180020889
0x18002079e  test    al, 20h
0x1800207a0  jz      short loc_1800207F0
0x1800207a2  cmp     dword ptr [rbx], 3Fh ; '?'
0x1800207a5  jnz     short loc_1800207F0
0x1800207a7  call    ?_Next@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(void)
0x1800207ac  mov     ebx, [rbx]
0x1800207ae  mov     rcx, rsi
0x1800207b1  call    ?_Next@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Next(void)
0x1800207b6  cmp     ebx, 3Ah ; ':'
0x1800207b9  jz      short loc_1800207F9
0x1800207bb  cmp     ebx, 21h ; '!'
0x1800207be  jnz     short loc_1800207D8
0x1800207c0  mov     dl, 1
0x1800207c2  mov     rcx, rsi
0x1800207c5  call    ?_Do_assert_group@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAX_N@Z; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_assert_group(bool)
0x1800207ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800207ce  add     [rsi+1Ch], eax
0x1800207d1  xor     al, al
0x1800207d3  jmp     loc_18002086E
0x1800207d8  cmp     ebx, 3Dh ; '='
0x1800207db  jnz     loc_180020894
0x1800207e1  xor     edx, edx
0x1800207e3  mov     rcx, rsi
0x1800207e6  call    ?_Do_assert_group@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAX_N@Z; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_assert_group(bool)
0x1800207eb  dec     dword ptr [rsi+1Ch]
0x1800207ee  jmp     short loc_1800207D1
0x1800207f0  test    dword ptr [rcx+70h], 200h
0x1800207f7  jz      short loc_180020803
0x1800207f9  mov     rcx, rsi
0x1800207fc  call    ?_Do_noncapture_group@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Do_noncapture_group(void)
0x180020801  jmp     short loc_180020869
0x180020803  mov     edx, [rcx+18h]
0x180020806  inc     edx
0x180020808  mov     [rcx+18h], edx
0x18002080b  cmp     edx, 3E8h
0x180020811  jnb     short loc_18002087E
0x180020813  add     rcx, 40h ; '@'
0x180020817  call    ?_Begin_capture_group@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Begin_capture_group(uint)
0x18002081c  mov     rcx, rsi
0x18002081f  mov     rdi, rax
0x180020822  call    ?_Disjunction@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXXZ; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Disjunction(void)
0x180020827  mov     rdx, rdi
0x18002082a  lea     rcx, [rsi+40h]
0x18002082e  call    ?_End_group@?$_Builder@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_End_group(std::_Node_base *)
0x180020833  mov     edx, [rsi+18h]
0x180020836  lea     rcx, [rsi+20h]
0x18002083a  add     edx, 1
0x18002083d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020844  cmovb   rdx, rax
0x180020848  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x18002084d  mov     edx, [rdi+20h]
0x180020850  mov     rcx, [rsi+20h]
0x180020854  mov     r8d, edx
0x180020857  shr     r8, 5
0x18002085b  and     edx, 1Fh
0x18002085e  mov     eax, [rcx+r8*4]
0x180020862  bts     eax, edx
0x180020865  mov     [rcx+r8*4], eax
0x180020869  dec     dword ptr [rsi+1Ch]
0x18002086c  mov     al, 1
0x18002086e  mov     rbx, [rsp+28h+arg_8]
0x180020873  mov     rsi, [rsp+28h+arg_10]
0x180020878  add     rsp, 20h
0x18002087c  pop     rdi
0x18002087d  retn
0x18002087e  mov     ecx, 0Ch
0x180020883  call    ?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
0x180020889  mov     edx, 5
0x18002088e  call    ?_Error@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Error(std::regex_constants::error_type)
0x180020894  mov     edx, 0Eh
0x180020899  call    ?_Error@?$_Parser@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Error(std::regex_constants::error_type)
```
