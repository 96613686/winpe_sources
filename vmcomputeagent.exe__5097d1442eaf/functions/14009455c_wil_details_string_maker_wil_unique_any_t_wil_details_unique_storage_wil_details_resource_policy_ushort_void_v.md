# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x14009455c`
- end: `0x14009469b`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `319`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007d7bc`

## callees

- `0x140005fe2`
- `0x140006080`
- `0x140006098`
- `0x140009f8c`
- `0x14009455c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140094607`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140094607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009464d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14009464d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009463a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009463a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400945d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400945d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140094645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140094660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140094645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140094660`

## string_xrefs

- `0x140094689`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
  }
  else
  {
    v9 = a3;
  }
  if ( a3 == -1 )
    v4 = v9;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v9;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
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
0x14009455c  push    rbx
0x14009455e  push    rbp
0x14009455f  push    rsi
0x140094560  push    rdi
0x140094561  push    r12
0x140094563  push    r14
0x140094565  push    r15
0x140094567  sub     rsp, 30h
0x14009456b  xor     r12d, r12d
0x14009456e  mov     rsi, r8
0x140094571  mov     rbp, rdx
0x140094574  mov     r14, rcx
0x140094577  test    rdx, rdx
0x14009457a  jnz     short loc_140094586
0x14009457c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140094580  jz      loc_140094684
0x140094586  test    rbp, rbp
0x140094589  jz      short loc_1400945BA
0x14009458b  mov     ecx, 7FFFFFFFh
0x140094590  mov     rax, rsi
0x140094593  cmp     rsi, rcx
0x140094596  mov     rbx, rbp
0x140094599  cmovnb  rax, rcx
0x14009459d  test    rax, rax
0x1400945a0  jz      short loc_1400945B2
0x1400945a2  cmp     [rbx], r12w
0x1400945a6  jz      short loc_1400945B2
0x1400945a8  add     rbx, 2
0x1400945ac  sub     rax, 1
0x1400945b0  jnz     short loc_1400945A2
0x1400945b2  sub     rbx, rbp
0x1400945b5  sar     rbx, 1
0x1400945b8  jmp     short loc_1400945BD
0x1400945ba  mov     rbx, rsi
0x1400945bd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400945c1  cmovz   rsi, rbx
0x1400945c5  lea     r15, ds:2[rsi*2]
0x1400945cd  mov     rcx, r15; cb
0x1400945d0  call    cs:__imp_CoTaskMemAlloc
0x1400945d6  mov     rdi, rax
0x1400945d9  test    rax, rax
0x1400945dc  jz      short loc_140094628
0x1400945de  test    rbp, rbp
0x1400945e1  jz      short loc_14009461F
0x1400945e3  add     rbx, rbx
0x1400945e6  jz      short loc_140094618
0x1400945e8  mov     rcx, rax; void *
0x1400945eb  cmp     r15, rbx
0x1400945ee  jb      short loc_1400945FD
0x1400945f0  mov     r8, rbx; Size
0x1400945f3  mov     rdx, rbp; Src
0x1400945f6  call    memcpy_0
0x1400945fb  jmp     short loc_140094618
0x1400945fd  mov     r8, r15; Size
0x140094600  xor     edx, edx; Val
0x140094602  call    memset_0
0x140094607  call    cs:__imp__o__errno
0x14009460d  mov     dword ptr [rax], 22h ; '"'
0x140094613  call    _invalid_parameter_noinfo
0x140094618  mov     [rbx+rdi], r12w
0x14009461d  jmp     short loc_140094623
0x14009461f  mov     [rax], r12w
0x140094623  mov     [rdi+rsi*2], r12w
0x140094628  lea     rax, [rsp+68h+var_48]
0x14009462d  cmp     r14, rax
0x140094630  jz      short loc_140094658
0x140094632  mov     rsi, [r14]
0x140094635  test    rsi, rsi
0x140094638  jz      short loc_140094653
0x14009463a  call    cs:__imp_GetLastError
0x140094640  mov     rcx, rsi; pv
0x140094643  mov     ebx, eax
0x140094645  call    cs:__imp_CoTaskMemFree
0x14009464b  mov     ecx, ebx; dwErrCode
0x14009464d  call    cs:__imp_SetLastError
0x140094653  mov     [r14], rdi
0x140094656  jmp     short loc_140094666
0x140094658  test    rdi, rdi
0x14009465b  jz      short loc_140094666
0x14009465d  mov     rcx, rdi; pv
0x140094660  call    cs:__imp_CoTaskMemFree
0x140094666  mov     rax, [r14]
0x140094669  neg     rax
0x14009466c  sbb     eax, eax
0x14009466e  not     eax
0x140094670  and     eax, 8007000Eh
0x140094675  add     rsp, 30h
0x140094679  pop     r15
0x14009467b  pop     r14
0x14009467d  pop     r12
0x14009467f  pop     rdi
0x140094680  pop     rsi
0x140094681  pop     rbp
0x140094682  pop     rbx
0x140094683  retn
0x140094684  mov     rcx, [rsp+68h]; this
0x140094689  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140094690  mov     edx, 0F89h; void *
0x140094695  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
