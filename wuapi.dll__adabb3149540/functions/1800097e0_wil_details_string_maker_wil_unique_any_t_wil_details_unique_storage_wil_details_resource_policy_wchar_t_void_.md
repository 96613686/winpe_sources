# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x1800097e0`
- end: `0x18000992b`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009064`

## callees

- `0x1800097e0`
- `0x18000aa58`
- `0x18000fc12`
- `0x18000fc4e`
- `0x180015a80`
- `0x180015e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000985d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800098d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800098ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800098d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800098ec`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  return *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800097e0  mov     rax, rsp
0x1800097e3  mov     [rax+8], rbx
0x1800097e7  mov     [rax+10h], rbp
0x1800097eb  mov     [rax+18h], rsi
0x1800097ef  mov     [rax+20h], rdi
0x1800097f3  push    r12
0x1800097f5  push    r14
0x1800097f7  push    r15
0x1800097f9  sub     rsp, 30h
0x1800097fd  xor     r12d, r12d
0x180009800  mov     rsi, r8
0x180009803  mov     rbp, rdx
0x180009806  mov     r14, rcx
0x180009809  test    rdx, rdx
0x18000980c  jnz     short loc_180009818
0x18000980e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009812  jz      loc_180009920
0x180009818  mov     rbx, rsi
0x18000981b  test    rbp, rbp
0x18000981e  jz      short loc_18000984A
0x180009820  mov     eax, 7FFFFFFFh
0x180009825  mov     rbx, rbp
0x180009828  cmp     rsi, rax
0x18000982b  cmovb   rax, rsi
0x18000982f  test    rax, rax
0x180009832  jz      short loc_180009844
0x180009834  cmp     [rbx], r12w
0x180009838  jz      short loc_180009844
0x18000983a  add     rbx, 2
0x18000983e  sub     rax, 1
0x180009842  jnz     short loc_180009834
0x180009844  sub     rbx, rbp
0x180009847  sar     rbx, 1
0x18000984a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000984e  cmovz   rsi, rbx
0x180009852  lea     r15, ds:2[rsi*2]
0x18000985a  mov     rcx, r15; cb
0x18000985d  call    cs:__imp_CoTaskMemAlloc
0x180009863  mov     rdi, rax
0x180009866  test    rax, rax
0x180009869  jz      short loc_1800098B4
0x18000986b  test    rbp, rbp
0x18000986e  jz      short loc_1800098AB
0x180009870  add     rbx, rbx
0x180009873  jz      short loc_1800098A4
0x180009875  mov     rcx, rax; void *
0x180009878  cmp     r15, rbx
0x18000987b  jb      short loc_18000988A
0x18000987d  mov     r8, rbx; Size
0x180009880  mov     rdx, rbp; Src
0x180009883  call    memmove
0x180009888  jmp     short loc_1800098A4
0x18000988a  mov     r8, r15; Size
0x18000988d  xor     edx, edx; Val
0x18000988f  call    memset
0x180009894  call    _o__errno_0
0x180009899  mov     dword ptr [rax], 22h ; '"'
0x18000989f  call    _invalid_parameter_noinfo
0x1800098a4  mov     [rbx+rdi], r12w
0x1800098a9  jmp     short loc_1800098AF
0x1800098ab  mov     [rax], r12w
0x1800098af  mov     [rdi+rsi*2], r12w
0x1800098b4  lea     rax, [rsp+48h+var_28]
0x1800098b9  cmp     r14, rax
0x1800098bc  jz      short loc_1800098E4
0x1800098be  mov     rsi, [r14]
0x1800098c1  test    rsi, rsi
0x1800098c4  jz      short loc_1800098DF
0x1800098c6  call    cs:__imp_GetLastError
0x1800098cc  mov     rcx, rsi; pv
0x1800098cf  mov     ebx, eax
0x1800098d1  call    cs:__imp_CoTaskMemFree
0x1800098d7  mov     ecx, ebx; dwErrCode
0x1800098d9  call    cs:__imp_SetLastError
0x1800098df  mov     [r14], rdi
0x1800098e2  jmp     short loc_1800098F2
0x1800098e4  test    rdi, rdi
0x1800098e7  jz      short loc_1800098F2
0x1800098e9  mov     rcx, rdi; pv
0x1800098ec  call    cs:__imp_CoTaskMemFree
0x1800098f2  mov     rax, [r14]
0x1800098f5  mov     rbx, [rsp+48h+arg_0]
0x1800098fa  neg     rax
0x1800098fd  mov     rbp, [rsp+48h+arg_8]
0x180009902  mov     rsi, [rsp+48h+arg_10]
0x180009907  sbb     eax, eax
0x180009909  mov     rdi, [rsp+48h+arg_18]
0x18000990e  not     eax
0x180009910  and     eax, 8007000Eh
0x180009915  add     rsp, 30h
0x180009919  pop     r15
0x18000991b  pop     r14
0x18000991d  pop     r12
0x18000991f  retn
0x180009920  mov     rcx, [rsp+48h]; this
0x180009925  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
