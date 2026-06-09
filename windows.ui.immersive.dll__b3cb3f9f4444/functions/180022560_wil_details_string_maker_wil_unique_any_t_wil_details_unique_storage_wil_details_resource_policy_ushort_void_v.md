# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x180022560`
- end: `0x1800226f8`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a360`

## callees

- `0x180022560`
- `0x180054a42`
- `0x180054ad4`
- `0x18005a1b6`
- `0x18005c174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800226ac`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800226ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800226e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022673`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226d9`

## string_xrefs

- `0x180022690`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rbx
  __int64 v7; // r15
  SIZE_T v8; // r14
  char *v9; // rax
  char *v10; // rdi
  size_t v11; // rbx
  void *v12; // rbp
  __int64 result; // rax
  __int64 v14; // rax
  char *v15; // rbx
  DWORD LastError; // ebx
  char v17; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v14 = a3;
    v15 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v14 = 0x7FFFFFFF;
    for ( ; v14; --v14 )
    {
      if ( !*(_WORD *)v15 )
        break;
      v15 += 2;
    }
    v6 = (v15 - a2) >> 1;
  }
  else
  {
    v6 = a3;
  }
  if ( a3 == -1 )
    a3 = v6;
  v7 = 2 * a3;
  v8 = 2 * a3 + 2;
  v9 = (char *)CoTaskMemAlloc(v8);
  v10 = v9;
  if ( v9 )
  {
    if ( a2 )
    {
      v11 = 2 * v6;
      if ( v11 )
      {
        if ( v8 < v11 )
        {
          memset_0(v9, 0, v8);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v9, a2, v11);
        }
      }
      *(_WORD *)&v10[v11] = 0;
    }
    else
    {
      *(_WORD *)v9 = 0;
    }
    *(_WORD *)&v10[v7] = 0;
  }
  if ( a1 == &v17 )
  {
    if ( v10 )
      CoTaskMemFree(v10);
  }
  else
  {
    v12 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v12);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v10;
  }
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x180022560  push    rbp
0x180022562  push    rsi
0x180022563  sub     rsp, 38h
0x180022567  mov     rbp, rdx
0x18002256a  mov     rsi, rcx
0x18002256d  test    rdx, rdx
0x180022570  jz      loc_180022681
0x180022576  mov     [rsp+48h+arg_0], rbx
0x18002257b  mov     [rsp+48h+arg_8], rdi
0x180022580  mov     [rsp+48h+arg_10], r14
0x180022585  mov     [rsp+48h+var_18], r15
0x18002258a  test    rbp, rbp
0x18002258d  jnz     loc_180022634
0x180022593  mov     rbx, r8
0x180022596  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002259a  cmovz   r8, rbx
0x18002259e  lea     r15, [r8+r8]
0x1800225a2  lea     r14, [r15+2]
0x1800225a6  mov     rcx, r14; cb
0x1800225a9  call    cs:__imp_CoTaskMemAlloc
0x1800225b0  nop     dword ptr [rax+rax+00h]
0x1800225b5  mov     rdi, rax
0x1800225b8  test    rax, rax
0x1800225bb  jz      short loc_1800225EB
0x1800225bd  test    rbp, rbp
0x1800225c0  jz      short loc_18002262D
0x1800225c2  add     rbx, rbx
0x1800225c5  jz      short loc_1800225DE
0x1800225c7  mov     rcx, rax; void *
0x1800225ca  cmp     r14, rbx
0x1800225cd  jb      loc_1800226A2
0x1800225d3  mov     r8, rbx; Size
0x1800225d6  mov     rdx, rbp; Src
0x1800225d9  call    memcpy_0
0x1800225de  xor     eax, eax
0x1800225e0  mov     [rbx+rdi], ax
0x1800225e4  xor     eax, eax
0x1800225e6  mov     [r15+rdi], ax
0x1800225eb  mov     r15, [rsp+48h+var_18]
0x1800225f0  lea     rax, [rsp+48h+var_28]
0x1800225f5  mov     r14, [rsp+48h+arg_10]
0x1800225fa  cmp     rsi, rax
0x1800225fd  jz      short loc_18002266B
0x1800225ff  mov     rbp, [rsi]
0x180022602  test    rbp, rbp
0x180022605  jnz     loc_1800226C8
0x18002260b  mov     [rsi], rdi
0x18002260e  mov     rdi, [rsp+48h+arg_8]
0x180022613  xor     eax, eax
0x180022615  cmp     [rsi], rax
0x180022618  mov     ecx, 8007000Eh
0x18002261d  mov     rbx, [rsp+48h+arg_0]
0x180022622  cmovz   eax, ecx
0x180022625  add     rsp, 38h
0x180022629  pop     rsi
0x18002262a  pop     rbp
0x18002262b  retn
0x18002262d  xor     eax, eax
0x18002262f  mov     [rdi], ax
0x180022632  jmp     short loc_1800225E4
0x180022634  mov     ecx, 7FFFFFFFh
0x180022639  mov     rax, r8
0x18002263c  cmp     r8, rcx
0x18002263f  mov     rbx, rbp
0x180022642  cmovnb  rax, rcx
0x180022646  test    rax, rax
0x180022649  jz      short loc_180022660
0x18002264b  nop     dword ptr [rax+rax+00h]
0x180022650  cmp     word ptr [rbx], 0
0x180022654  jz      short loc_180022660
0x180022656  add     rbx, 2
0x18002265a  sub     rax, 1
0x18002265e  jnz     short loc_180022650
0x180022660  sub     rbx, rbp
0x180022663  sar     rbx, 1
0x180022666  jmp     loc_180022596
0x18002266b  test    rdi, rdi
0x18002266e  jz      short loc_18002260E
0x180022670  mov     rcx, rdi; pv
0x180022673  call    cs:__imp_CoTaskMemFree
0x18002267a  nop     dword ptr [rax+rax+00h]
0x18002267f  jmp     short loc_18002260E
0x180022681  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180022685  jnz     loc_180022576
0x18002268b  mov     rcx, [rsp+48h]; this
0x180022690  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022697  mov     edx, 0F89h; void *
0x18002269c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800226a2  mov     r8, r14; Size
0x1800226a5  xor     edx, edx; Val
0x1800226a7  call    memset_0
0x1800226ac  call    cs:__imp__o__errno
0x1800226b3  nop     dword ptr [rax+rax+00h]
0x1800226b8  mov     dword ptr [rax], 22h ; '"'
0x1800226be  call    _invalid_parameter_noinfo
0x1800226c3  jmp     loc_1800225DE
0x1800226c8  call    cs:__imp_GetLastError
0x1800226cf  nop     dword ptr [rax+rax+00h]
0x1800226d4  mov     rcx, rbp; pv
0x1800226d7  mov     ebx, eax
0x1800226d9  call    cs:__imp_CoTaskMemFree
0x1800226e0  nop     dword ptr [rax+rax+00h]
0x1800226e5  mov     ecx, ebx; dwErrCode
0x1800226e7  call    cs:__imp_SetLastError
0x1800226ee  nop     dword ptr [rax+rax+00h]
0x1800226f3  jmp     loc_18002260B
```
