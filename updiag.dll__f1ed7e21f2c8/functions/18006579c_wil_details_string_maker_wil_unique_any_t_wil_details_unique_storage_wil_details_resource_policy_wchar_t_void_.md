# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x18006579c`
- end: `0x1800658e7`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180065954`

## callees

- `0x18006576c`
- `0x18006579c`
- `0x18008fa9b`
- `0x18008fb37`
- `0x1800961f0`
- `0x1800965b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180065819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180065819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006588d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800658a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006588d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800658a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065895`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065882`

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
0x18006579c  mov     rax, rsp
0x18006579f  mov     [rax+8], rbx
0x1800657a3  mov     [rax+10h], rbp
0x1800657a7  mov     [rax+18h], rsi
0x1800657ab  mov     [rax+20h], rdi
0x1800657af  push    r12
0x1800657b1  push    r14
0x1800657b3  push    r15
0x1800657b5  sub     rsp, 30h
0x1800657b9  xor     r12d, r12d
0x1800657bc  mov     rsi, r8
0x1800657bf  mov     rbp, rdx
0x1800657c2  mov     r14, rcx
0x1800657c5  test    rdx, rdx
0x1800657c8  jnz     short loc_1800657D4
0x1800657ca  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800657ce  jz      loc_1800658DC
0x1800657d4  mov     rbx, rsi
0x1800657d7  test    rbp, rbp
0x1800657da  jz      short loc_180065806
0x1800657dc  mov     eax, 7FFFFFFFh
0x1800657e1  mov     rbx, rbp
0x1800657e4  cmp     rsi, rax
0x1800657e7  cmovb   rax, rsi
0x1800657eb  test    rax, rax
0x1800657ee  jz      short loc_180065800
0x1800657f0  cmp     [rbx], r12w
0x1800657f4  jz      short loc_180065800
0x1800657f6  add     rbx, 2
0x1800657fa  sub     rax, 1
0x1800657fe  jnz     short loc_1800657F0
0x180065800  sub     rbx, rbp
0x180065803  sar     rbx, 1
0x180065806  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006580a  cmovz   rsi, rbx
0x18006580e  lea     r15, ds:2[rsi*2]
0x180065816  mov     rcx, r15; cb
0x180065819  call    cs:__imp_CoTaskMemAlloc
0x18006581f  mov     rdi, rax
0x180065822  test    rax, rax
0x180065825  jz      short loc_180065870
0x180065827  test    rbp, rbp
0x18006582a  jz      short loc_180065867
0x18006582c  add     rbx, rbx
0x18006582f  jz      short loc_180065860
0x180065831  mov     rcx, rax; void *
0x180065834  cmp     r15, rbx
0x180065837  jb      short loc_180065846
0x180065839  mov     r8, rbx; Size
0x18006583c  mov     rdx, rbp; Src
0x18006583f  call    memmove
0x180065844  jmp     short loc_180065860
0x180065846  mov     r8, r15; Size
0x180065849  xor     edx, edx; Val
0x18006584b  call    memset
0x180065850  call    _o__errno_0
0x180065855  mov     dword ptr [rax], 22h ; '"'
0x18006585b  call    _invalid_parameter_noinfo
0x180065860  mov     [rbx+rdi], r12w
0x180065865  jmp     short loc_18006586B
0x180065867  mov     [rax], r12w
0x18006586b  mov     [rdi+rsi*2], r12w
0x180065870  lea     rax, [rsp+48h+var_28]
0x180065875  cmp     r14, rax
0x180065878  jz      short loc_1800658A0
0x18006587a  mov     rsi, [r14]
0x18006587d  test    rsi, rsi
0x180065880  jz      short loc_18006589B
0x180065882  call    cs:__imp_GetLastError
0x180065888  mov     rcx, rsi; pv
0x18006588b  mov     ebx, eax
0x18006588d  call    cs:__imp_CoTaskMemFree
0x180065893  mov     ecx, ebx; dwErrCode
0x180065895  call    cs:__imp_SetLastError
0x18006589b  mov     [r14], rdi
0x18006589e  jmp     short loc_1800658AE
0x1800658a0  test    rdi, rdi
0x1800658a3  jz      short loc_1800658AE
0x1800658a5  mov     rcx, rdi; pv
0x1800658a8  call    cs:__imp_CoTaskMemFree
0x1800658ae  mov     rax, [r14]
0x1800658b1  mov     rbx, [rsp+48h+arg_0]
0x1800658b6  neg     rax
0x1800658b9  mov     rbp, [rsp+48h+arg_8]
0x1800658be  mov     rsi, [rsp+48h+arg_10]
0x1800658c3  sbb     eax, eax
0x1800658c5  mov     rdi, [rsp+48h+arg_18]
0x1800658ca  not     eax
0x1800658cc  and     eax, 8007000Eh
0x1800658d1  add     rsp, 30h
0x1800658d5  pop     r15
0x1800658d7  pop     r14
0x1800658d9  pop     r12
0x1800658db  retn
0x1800658dc  mov     rcx, [rsp+48h]; this
0x1800658e1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
