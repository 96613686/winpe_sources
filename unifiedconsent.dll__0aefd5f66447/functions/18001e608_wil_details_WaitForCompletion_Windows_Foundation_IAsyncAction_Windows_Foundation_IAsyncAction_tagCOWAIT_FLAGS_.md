# wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18001e608`
- end: `0x18001e8cd`
- name: `??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002be40`

## callees

- `0x18000383c`
- `0x1800095b8`
- `0x18000c784`
- `0x18000e444`
- `0x18001e608`
- `0x180022034`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e7b5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e7b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e66d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e68e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e6af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e6af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e69a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e69a`

## string_xrefs

- `0x18001e706`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18001e745`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18001e773`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x18001e7ec`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(
        __int64 a1,
        int a2,
        DWORD a3,
        _BYTE *a4)
{
  void *v7; // rax
  unsigned int v8; // edi
  _QWORD *v9; // rbx
  wil::details *v10; // rcx
  HANDLE Event; // r15
  void *v12; // rdi
  DWORD LastError; // r12d
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int LastErrorFailHr; // eax
  HRESULT v19; // eax
  __int64 v20; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  __int64 v23; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  int v26; // [rsp+88h] [rbp+48h] BYREF
  DWORD dwindex; // [rsp+98h] [rbp+58h] BYREF

  v26 = a2;
  if ( a4 )
    *a4 = 0;
  v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    v8 = -2147024882;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)v8,
      lpdwindex);
    return v8;
  }
  v9 = (_QWORD *)`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::CompletionDelegate(v7);
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v12 = (void *)v9[7];
    if ( v12 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
      SetLastError(LastError);
    }
    v9[7] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
    v8 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      if ( v9 )
        (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      goto LABEL_19;
    }
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 48LL))(a1, v9);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v16,
      lpdwindex);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    return v8;
  }
  pHandles = (HANDLE)v9[7];
  dwindex = 0;
  v19 = CoWaitForMultipleHandles(8u, a3, 1u, &pHandles, &dwindex);
  v8 = v19;
  if ( a4 && v19 == -2147417835 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  }
  else
  {
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x655,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)v19,
        lpdwindexa);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      return v8;
    }
    if ( *((_DWORD *)v9 + 12) != 1 )
    {
      v23 = 0;
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
             a1,
             &GUID_00000036_0000_0000_c000_000000000046,
             &v23);
      if ( (v8 & 0x80000000) == 0 )
      {
        v26 = -2147418113;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 64LL))(v23, &v26);
        if ( (v8 & 0x80000000) == 0 )
          v8 = v26;
      }
      v20 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      return v8;
    }
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e608  mov     [rsp-38h+arg_0], rbx
0x18001e60d  mov     [rsp-38h+arg_8], edx
0x18001e611  push    rbp
0x18001e612  push    rsi
0x18001e613  push    rdi
0x18001e614  push    r12
0x18001e616  push    r13
0x18001e618  push    r14
0x18001e61a  push    r15
0x18001e61c  mov     rbp, rsp
0x18001e61f  sub     rsp, 40h
0x18001e623  mov     rsi, r9
0x18001e626  mov     r13d, r8d
0x18001e629  mov     r14, rcx
0x18001e62c  test    r9, r9
0x18001e62f  jz      short loc_18001E635
0x18001e631  mov     byte ptr [r9], 0
0x18001e635  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e63c  mov     ecx, 40h ; '@'; unsigned __int64
0x18001e641  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e646  test    rax, rax
0x18001e649  jnz     short loc_18001E655
0x18001e64b  mov     edi, 8007000Eh
0x18001e650  jmp     loc_18001E76C
0x18001e655  mov     rcx, rax
0x18001e658  call    ??0CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAA@XZ; `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::CompletionDelegate(void)
0x18001e65d  mov     rbx, rax
0x18001e660  mov     r9d, 1F0003h; dwDesiredAccess
0x18001e666  xor     r8d, r8d; dwFlags
0x18001e669  xor     edx, edx; lpName
0x18001e66b  xor     ecx, ecx; lpEventAttributes
0x18001e66d  call    cs:__imp_CreateEventExW
0x18001e673  mov     r15, rax
0x18001e676  test    rax, rax
0x18001e679  jz      loc_18001E72F
0x18001e67f  call    cs:__imp_GetLastError
0x18001e685  mov     rdi, [rbx+38h]
0x18001e689  test    rdi, rdi
0x18001e68c  jz      short loc_18001E6B5
0x18001e68e  call    cs:__imp_GetLastError
0x18001e694  mov     r12d, eax
0x18001e697  mov     rcx, rdi; hObject
0x18001e69a  call    cs:__imp_CloseHandle
0x18001e6a0  mov     rcx, [rbp+38h]; this
0x18001e6a4  test    eax, eax
0x18001e6a6  jz      loc_18001E8C2
0x18001e6ac  mov     ecx, r12d; dwErrCode
0x18001e6af  call    cs:__imp_SetLastError
0x18001e6b5  mov     [rbx+38h], r15
0x18001e6b9  test    rbx, rbx
0x18001e6bc  jz      short loc_18001E6CE
0x18001e6be  mov     rax, [rbx]
0x18001e6c1  mov     rcx, rbx
0x18001e6c4  mov     rax, [rax+8]
0x18001e6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6cd  nop
0x18001e6ce  test    rbx, rbx
0x18001e6d1  jz      short loc_18001E6E3
0x18001e6d3  mov     rax, [rbx]
0x18001e6d6  mov     rcx, rbx
0x18001e6d9  mov     rax, [rax+10h]
0x18001e6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e2  nop
0x18001e6e3  mov     rax, [r14]
0x18001e6e6  mov     rdx, rbx
0x18001e6e9  mov     rcx, r14
0x18001e6ec  mov     rax, [rax+30h]
0x18001e6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f5  mov     edi, eax
0x18001e6f7  test    eax, eax
0x18001e6f9  jns     loc_18001E78C
0x18001e6ff  mov     rcx, [rbp+38h]; this
0x18001e703  mov     r9d, eax; char *
0x18001e706  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e70d  mov     edx, 649h; void *
0x18001e712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e717  nop
0x18001e718  test    rbx, rbx
0x18001e71b  jz      short loc_18001E72D
0x18001e71d  mov     rcx, [rbx]
0x18001e720  mov     rax, [rcx+10h]
0x18001e724  mov     rcx, rbx
0x18001e727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e72c  nop
0x18001e72d  jmp     short loc_18001E785
0x18001e72f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e734  mov     edi, eax
0x18001e736  test    eax, eax
0x18001e738  jns     loc_18001E6B9
0x18001e73e  mov     rcx, [rbp+38h]; this
0x18001e742  mov     r9d, eax; char *
0x18001e745  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e74c  mov     edx, 62Bh; void *
0x18001e751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e756  nop
0x18001e757  test    rbx, rbx
0x18001e75a  jz      short loc_18001E76C
0x18001e75c  mov     rax, [rbx]
0x18001e75f  mov     rcx, rbx
0x18001e762  mov     rax, [rax+10h]
0x18001e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e76b  nop
0x18001e76c  mov     rcx, [rbp+38h]; this
0x18001e770  mov     r9d, edi; char *
0x18001e773  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e77a  mov     edx, 648h; void *
0x18001e77f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e784  nop
0x18001e785  mov     eax, edi
0x18001e787  jmp     loc_18001E8AA
0x18001e78c  mov     rax, [rbx+38h]
0x18001e790  mov     [rbp+pHandles], rax
0x18001e794  mov     [rbp+dwindex], 0
0x18001e79b  lea     rax, [rbp+dwindex]
0x18001e79f  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18001e7a4  lea     r9, [rbp+pHandles]; pHandles
0x18001e7a8  mov     r8d, 1; cHandles
0x18001e7ae  mov     edx, r13d; dwTimeout
0x18001e7b1  lea     ecx, [r8+7]; dwFlags
0x18001e7b5  call    cs:__imp_CoWaitForMultipleHandles
0x18001e7bb  mov     edi, eax
0x18001e7bd  test    rsi, rsi
0x18001e7c0  jz      short loc_18001E7E1
0x18001e7c2  cmp     eax, 80010115h
0x18001e7c7  jnz     short loc_18001E7E1
0x18001e7c9  mov     byte ptr [rsi], 1
0x18001e7cc  mov     rax, [rbx]
0x18001e7cf  mov     rcx, rbx
0x18001e7d2  mov     rax, [rax+10h]
0x18001e7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7db  nop
0x18001e7dc  jmp     loc_18001E8A8
0x18001e7e1  test    edi, edi
0x18001e7e3  jns     short loc_18001E813
0x18001e7e5  mov     rcx, [rbp+38h]; this
0x18001e7e9  mov     r9d, edi; char *
0x18001e7ec  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e7f3  mov     edx, 655h; void *
0x18001e7f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7fd  nop
0x18001e7fe  mov     rax, [rbx]
0x18001e801  mov     rcx, rbx
0x18001e804  mov     rax, [rax+10h]
0x18001e808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80d  nop
0x18001e80e  jmp     loc_18001E785
0x18001e813  mov     eax, [rbx+30h]
0x18001e816  cmp     eax, 1
0x18001e819  jz      short loc_18001E898
0x18001e81b  mov     [rbp+var_10], 0
0x18001e823  mov     rax, [r14]
0x18001e826  lea     r8, [rbp+var_10]
0x18001e82a  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001e831  mov     rcx, r14
0x18001e834  mov     rax, [rax]
0x18001e837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e83c  mov     edi, eax
0x18001e83e  test    eax, eax
0x18001e840  js      short loc_18001E865
0x18001e842  mov     [rbp+arg_8], 8000FFFFh
0x18001e849  mov     rcx, [rbp+var_10]
0x18001e84d  mov     rax, [rcx]
0x18001e850  lea     rdx, [rbp+arg_8]
0x18001e854  mov     rax, [rax+40h]
0x18001e858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e85d  mov     edi, eax
0x18001e85f  test    eax, eax
0x18001e861  cmovns  edi, [rbp+arg_8]
0x18001e865  mov     rcx, [rbp+var_10]
0x18001e869  test    rcx, rcx
0x18001e86c  jz      short loc_18001E883
0x18001e86e  mov     [rbp+var_10], 0
0x18001e876  mov     rax, [rcx]
0x18001e879  mov     rax, [rax+10h]
0x18001e87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e882  nop
0x18001e883  mov     rax, [rbx]
0x18001e886  mov     rcx, rbx
0x18001e889  mov     rax, [rax+10h]
0x18001e88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e892  nop
0x18001e893  jmp     loc_18001E785
0x18001e898  mov     rax, [rbx]
0x18001e89b  mov     rcx, rbx
0x18001e89e  mov     rax, [rax+10h]
0x18001e8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8a7  nop
0x18001e8a8  xor     eax, eax
0x18001e8aa  mov     rbx, [rsp+40h+arg_0]
0x18001e8b2  add     rsp, 40h
0x18001e8b6  pop     r15
0x18001e8b8  pop     r14
0x18001e8ba  pop     r13
0x18001e8bc  pop     r12
0x18001e8be  pop     rdi
0x18001e8bf  pop     rsi
0x18001e8c0  pop     rbp
0x18001e8c1  retn
0x18001e8c2  mov     edx, 0A0Bh; void *
0x18001e8c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
