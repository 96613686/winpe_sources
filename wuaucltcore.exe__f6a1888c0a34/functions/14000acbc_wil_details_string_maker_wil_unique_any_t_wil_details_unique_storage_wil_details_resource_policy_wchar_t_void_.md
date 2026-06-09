# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x14000acbc`
- end: `0x14000ae0c`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `336`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000997c`
- `0x14000ae78`

## callees

- `0x14000acbc`
- `0x14000b794`
- `0x14001a943`
- `0x14001a98b`
- `0x140020760`
- `0x140020b20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000adad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000adc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000adad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000adc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ad39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ad39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ada2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ada2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adb5`

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
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0xDB5, 0xFFFFFFFF, a4);
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
0x14000acbc  mov     rax, rsp
0x14000acbf  mov     [rax+8], rbx
0x14000acc3  mov     [rax+10h], rbp
0x14000acc7  mov     [rax+18h], rsi
0x14000accb  mov     [rax+20h], rdi
0x14000accf  push    r12
0x14000acd1  push    r14
0x14000acd3  push    r15
0x14000acd5  sub     rsp, 30h
0x14000acd9  xor     r12d, r12d
0x14000acdc  mov     rsi, r8
0x14000acdf  mov     rbp, rdx
0x14000ace2  mov     r14, rcx
0x14000ace5  test    rdx, rdx
0x14000ace8  jnz     short loc_14000ACF4
0x14000acea  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000acee  jz      loc_14000ADFC
0x14000acf4  mov     rbx, rsi
0x14000acf7  test    rbp, rbp
0x14000acfa  jz      short loc_14000AD26
0x14000acfc  mov     eax, 7FFFFFFFh
0x14000ad01  mov     rbx, rbp
0x14000ad04  cmp     rsi, rax
0x14000ad07  cmovb   rax, rsi
0x14000ad0b  test    rax, rax
0x14000ad0e  jz      short loc_14000AD20
0x14000ad10  cmp     [rbx], r12w
0x14000ad14  jz      short loc_14000AD20
0x14000ad16  add     rbx, 2
0x14000ad1a  sub     rax, 1
0x14000ad1e  jnz     short loc_14000AD10
0x14000ad20  sub     rbx, rbp
0x14000ad23  sar     rbx, 1
0x14000ad26  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000ad2a  cmovz   rsi, rbx
0x14000ad2e  lea     r15, ds:2[rsi*2]
0x14000ad36  mov     rcx, r15; cb
0x14000ad39  call    cs:__imp_CoTaskMemAlloc
0x14000ad3f  mov     rdi, rax
0x14000ad42  test    rax, rax
0x14000ad45  jz      short loc_14000AD90
0x14000ad47  test    rbp, rbp
0x14000ad4a  jz      short loc_14000AD87
0x14000ad4c  add     rbx, rbx
0x14000ad4f  jz      short loc_14000AD80
0x14000ad51  mov     rcx, rax; void *
0x14000ad54  cmp     r15, rbx
0x14000ad57  jb      short loc_14000AD66
0x14000ad59  mov     r8, rbx; Size
0x14000ad5c  mov     rdx, rbp; Src
0x14000ad5f  call    memmove
0x14000ad64  jmp     short loc_14000AD80
0x14000ad66  mov     r8, r15; Size
0x14000ad69  xor     edx, edx; Val
0x14000ad6b  call    memset
0x14000ad70  call    _o__errno_0
0x14000ad75  mov     dword ptr [rax], 22h ; '"'
0x14000ad7b  call    _invalid_parameter_noinfo
0x14000ad80  mov     [rbx+rdi], r12w
0x14000ad85  jmp     short loc_14000AD8B
0x14000ad87  mov     [rax], r12w
0x14000ad8b  mov     [rdi+rsi*2], r12w
0x14000ad90  lea     rax, [rsp+48h+var_28]
0x14000ad95  cmp     r14, rax
0x14000ad98  jz      short loc_14000ADC0
0x14000ad9a  mov     rsi, [r14]
0x14000ad9d  test    rsi, rsi
0x14000ada0  jz      short loc_14000ADBB
0x14000ada2  call    cs:__imp_GetLastError
0x14000ada8  mov     rcx, rsi; pv
0x14000adab  mov     ebx, eax
0x14000adad  call    cs:__imp_CoTaskMemFree
0x14000adb3  mov     ecx, ebx; dwErrCode
0x14000adb5  call    cs:__imp_SetLastError
0x14000adbb  mov     [r14], rdi
0x14000adbe  jmp     short loc_14000ADCE
0x14000adc0  test    rdi, rdi
0x14000adc3  jz      short loc_14000ADCE
0x14000adc5  mov     rcx, rdi; pv
0x14000adc8  call    cs:__imp_CoTaskMemFree
0x14000adce  mov     rax, [r14]
0x14000add1  mov     rbx, [rsp+48h+arg_0]
0x14000add6  neg     rax
0x14000add9  mov     rbp, [rsp+48h+arg_8]
0x14000adde  mov     rsi, [rsp+48h+arg_10]
0x14000ade3  sbb     eax, eax
0x14000ade5  mov     rdi, [rsp+48h+arg_18]
0x14000adea  not     eax
0x14000adec  and     eax, 8007000Eh
0x14000adf1  add     rsp, 30h
0x14000adf5  pop     r15
0x14000adf7  pop     r14
0x14000adf9  pop     r12
0x14000adfb  retn
0x14000adfc  mov     rcx, [rsp+48h]; this
0x14000ae01  mov     edx, 0DB5h; void *
0x14000ae06  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
