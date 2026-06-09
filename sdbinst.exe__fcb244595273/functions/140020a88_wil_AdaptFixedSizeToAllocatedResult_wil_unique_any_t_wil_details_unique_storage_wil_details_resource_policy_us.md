# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x140020a88`
- end: `0x140020cb0`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140020cb8`

## callees

- `0x140006844`
- `0x140007d54`
- `0x140020a88`
- `0x14002474c`
- `0x14002e3e2`
- `0x14002e420`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140020be0`
- `KERNEL32!GetLastError` at `0x140020be0`
- `KERNEL32!GetProcessHeap` at `0x140020be8`
- `KERNEL32!GetProcessHeap` at `0x140020c0e`
- `KERNEL32!GetProcessHeap` at `0x140020c2b`
- `KERNEL32!GetProcessHeap` at `0x140020c68`
- `KERNEL32!GetProcessHeap` at `0x140020be8`
- `KERNEL32!GetProcessHeap` at `0x140020c0e`
- `KERNEL32!GetProcessHeap` at `0x140020c2b`
- `KERNEL32!GetProcessHeap` at `0x140020c68`
- `KERNEL32!SetLastError` at `0x140020bfe`
- `KERNEL32!SetLastError` at `0x140020bfe`
- `KERNEL32!HeapFree` at `0x140020bf6`
- `KERNEL32!HeapFree` at `0x140020c1c`
- `KERNEL32!HeapFree` at `0x140020c39`
- `KERNEL32!HeapFree` at `0x140020c76`
- `KERNEL32!HeapFree` at `0x140020bf6`
- `KERNEL32!HeapFree` at `0x140020c1c`
- `KERNEL32!HeapFree` at `0x140020c39`
- `KERNEL32!HeapFree` at `0x140020c76`

## string_xrefs

- `0x140020c4b`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        char *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax
  unsigned __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  void *v9; // rbx
  unsigned __int64 v10; // rdi
  __int64 v11; // rcx
  int v12; // esi
  void *v13; // rsi
  DWORD LastError; // edi
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE ProcessHeap; // rax
  void *v18; // rdi
  HANDLE v19; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 *v25; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[512]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  lpMem = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = &v22;
  v24 = 256;
  v25 = (unsigned __int64 *)v27;
  v4 = *(_QWORD *)(a2 + 112);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  result = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v4 + 32LL))(
             v4,
             &v25,
             &v24,
             &v23);
  if ( (int)result >= 0 )
  {
    v6 = v22;
    if ( v22 > 0x100 )
    {
      while ( 1 )
      {
        v10 = v6;
        v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &lpMem,
               0,
               v6 - 1);
        if ( v7 < 0 )
        {
          v8 = 378;
          goto LABEL_22;
        }
        v25 = &v22;
        v24 = v10;
        v9 = lpMem;
        v23 = (unsigned __int64 *)lpMem;
        v11 = *(_QWORD *)(a2 + 112);
        if ( !v11 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 **, __int64 *, unsigned __int64 **))(*(_QWORD *)v11 + 32LL))(
                v11,
                &v23,
                &v24,
                &v25);
        if ( v12 < 0 )
          break;
        v6 = v22;
        if ( v22 <= v10 )
          goto LABEL_11;
      }
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
      }
      return (unsigned int)v12;
    }
    else
    {
      v7 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &lpMem,
             v27,
             v22 - 1);
      if ( v7 >= 0 )
      {
        v9 = lpMem;
LABEL_11:
        if ( a1 == &v26 )
        {
          if ( v9 )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v9);
          }
        }
        else
        {
          v13 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            LastError = GetLastError();
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v13);
            SetLastError(LastError);
          }
          *(_QWORD *)a1 = v9;
        }
        return 0;
      }
      else
      {
        v8 = 367;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)(unsigned int)v7,
          v20);
        v18 = lpMem;
        if ( lpMem )
        {
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v18);
        }
        return (unsigned int)v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020a88  mov     [rsp-8+arg_10], rbx
0x140020a8d  push    rbp
0x140020a8e  push    rsi
0x140020a8f  push    rdi
0x140020a90  push    r14
0x140020a92  push    r15
0x140020a94  lea     rbp, [rsp-170h]
0x140020a9c  sub     rsp, 270h
0x140020aa3  mov     rax, cs:__security_cookie
0x140020aaa  xor     rax, rsp
0x140020aad  mov     [rbp+190h+var_30], rax
0x140020ab4  mov     r15, rdx
0x140020ab7  mov     r14, rcx
0x140020aba  mov     [rsp+290h+lpMem], 0
0x140020ac3  xor     edx, edx; Val
0x140020ac5  mov     r8d, 200h; Size
0x140020acb  lea     rcx, [rsp+290h+var_230]; void *
0x140020ad0  call    memset_0
0x140020ad5  mov     [rsp+290h+var_258], 0
0x140020ade  lea     rax, [rsp+290h+var_258]
0x140020ae3  mov     [rsp+290h+var_250], rax
0x140020ae8  mov     ebx, 100h
0x140020aed  mov     [rsp+290h+var_248], rbx
0x140020af2  lea     rax, [rsp+290h+var_230]
0x140020af7  mov     [rsp+290h+var_240], rax
0x140020afc  mov     rcx, [r15+70h]; this
0x140020b00  test    rcx, rcx
0x140020b03  jz      loc_140020CAA
0x140020b09  mov     rax, [rcx]
0x140020b0c  lea     r9, [rsp+290h+var_250]
0x140020b11  lea     r8, [rsp+290h+var_248]
0x140020b16  lea     rdx, [rsp+290h+var_240]
0x140020b1b  mov     rax, [rax+20h]
0x140020b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020b24  test    eax, eax
0x140020b26  js      loc_140020C7E
0x140020b2c  mov     rax, [rsp+290h+var_258]
0x140020b31  cmp     rax, rbx
0x140020b34  ja      short loc_140020B60
0x140020b36  lea     r8, [rax-1]
0x140020b3a  lea     rdx, [rsp+290h+var_230]
0x140020b3f  lea     rcx, [rsp+290h+lpMem]
0x140020b44  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140020b49  mov     ebx, eax
0x140020b4b  test    eax, eax
0x140020b4d  jns     short loc_140020B59
0x140020b4f  mov     edx, 16Fh
0x140020b54  jmp     loc_140020C48
0x140020b59  mov     rbx, [rsp+290h+lpMem]
0x140020b5e  jmp     short loc_140020BCE
0x140020b60  mov     rdi, rax
0x140020b63  lea     r8, [rax-1]
0x140020b67  xor     edx, edx
0x140020b69  lea     rcx, [rsp+290h+lpMem]
0x140020b6e  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140020b73  mov     ebx, eax
0x140020b75  test    eax, eax
0x140020b77  js      loc_140020C43
0x140020b7d  lea     rax, [rsp+290h+var_258]
0x140020b82  mov     [rsp+290h+var_240], rax
0x140020b87  mov     [rsp+290h+var_248], rdi
0x140020b8c  mov     rbx, [rsp+290h+lpMem]
0x140020b91  mov     [rsp+290h+var_250], rbx
0x140020b96  mov     rcx, [r15+70h]; this
0x140020b9a  test    rcx, rcx
0x140020b9d  jz      loc_140020CA4
0x140020ba3  mov     rax, [rcx]
0x140020ba6  lea     r9, [rsp+290h+var_240]
0x140020bab  lea     r8, [rsp+290h+var_248]
0x140020bb0  lea     rdx, [rsp+290h+var_250]
0x140020bb5  mov     rax, [rax+20h]
0x140020bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020bbe  mov     esi, eax
0x140020bc0  test    eax, eax
0x140020bc2  js      short loc_140020C26
0x140020bc4  mov     rax, [rsp+290h+var_258]
0x140020bc9  cmp     rax, rdi
0x140020bcc  ja      short loc_140020B60
0x140020bce  lea     rax, [rsp+290h+var_238]
0x140020bd3  cmp     r14, rax
0x140020bd6  jz      short loc_140020C09
0x140020bd8  mov     rsi, [r14]
0x140020bdb  test    rsi, rsi
0x140020bde  jz      short loc_140020C04
0x140020be0  call    cs:__imp_GetLastError
0x140020be6  mov     edi, eax
0x140020be8  call    cs:__imp_GetProcessHeap
0x140020bee  mov     rcx, rax; hHeap
0x140020bf1  mov     r8, rsi; lpMem
0x140020bf4  xor     edx, edx; dwFlags
0x140020bf6  call    cs:__imp_HeapFree
0x140020bfc  mov     ecx, edi; dwErrCode
0x140020bfe  call    cs:__imp_SetLastError
0x140020c04  mov     [r14], rbx
0x140020c07  jmp     short loc_140020C22
0x140020c09  test    rbx, rbx
0x140020c0c  jz      short loc_140020C22
0x140020c0e  call    cs:__imp_GetProcessHeap
0x140020c14  mov     rcx, rax; hHeap
0x140020c17  mov     r8, rbx; lpMem
0x140020c1a  xor     edx, edx; dwFlags
0x140020c1c  call    cs:__imp_HeapFree
0x140020c22  xor     eax, eax
0x140020c24  jmp     short loc_140020C7E
0x140020c26  test    rbx, rbx
0x140020c29  jz      short loc_140020C3F
0x140020c2b  call    cs:__imp_GetProcessHeap
0x140020c31  mov     rcx, rax; hHeap
0x140020c34  mov     r8, rbx; lpMem
0x140020c37  xor     edx, edx; dwFlags
0x140020c39  call    cs:__imp_HeapFree
0x140020c3f  mov     eax, esi
0x140020c41  jmp     short loc_140020C7E
0x140020c43  mov     edx, 17Ah; void *
0x140020c48  mov     r9d, ebx; char *
0x140020c4b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140020c52  mov     rcx, [rbp+198h]; this
0x140020c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020c5e  mov     rdi, [rsp+290h+lpMem]
0x140020c63  test    rdi, rdi
0x140020c66  jz      short loc_140020C7C
0x140020c68  call    cs:__imp_GetProcessHeap
0x140020c6e  mov     r8, rdi; lpMem
0x140020c71  xor     edx, edx; dwFlags
0x140020c73  mov     rcx, rax; hHeap
0x140020c76  call    cs:__imp_HeapFree
0x140020c7c  mov     eax, ebx
0x140020c7e  mov     rcx, [rbp+190h+var_30]
0x140020c85  xor     rcx, rsp; StackCookie
0x140020c88  call    __security_check_cookie
0x140020c8d  mov     rbx, [rsp+290h+arg_10]
0x140020c95  add     rsp, 270h
0x140020c9c  pop     r15
0x140020c9e  pop     r14
0x140020ca0  pop     rdi
0x140020ca1  pop     rsi
0x140020ca2  pop     rbp
0x140020ca3  retn
0x140020ca4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140020caa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
