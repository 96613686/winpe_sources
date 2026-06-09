# CSharedBitmap::CreateInstance(HBITMAP__ *,WTS_ALPHATYPE,CGlobalRefCount *,_GUID const &,void * *)

- ea: `0x180012260`
- end: `0x180012440`
- name: `?CreateInstance@CSharedBitmap@@SAJPEAUHBITMAP__@@W4WTS_ALPHATYPE@@PEAVCGlobalRefCount@@AEBU_GUID@@PEAPEAX@Z`
- size: `480`
- prototype: `__int64 __fastcall(HBITMAP ho, enum WTS_ALPHATYPE, struct CGlobalRefCount *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011c10`
- `0x180012128`
- `0x18001c6f0`

## callees

- `0x180012260`
- `0x1800342a0`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800122fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800122fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001234a`
- `OLEAUT32!__imp_SysFreeString` at `0x180012391`
- `OLEAUT32!__imp_SysFreeString` at `0x18001234a`
- `OLEAUT32!__imp_SysFreeString` at `0x180012391`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001235c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001235c`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180012367`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180012367`
- `GDI32!DeleteObject` at `0x180012438`
- `GDI32!DeleteObject` at `0x180012438`
- `GDI32!GetObjectW` at `0x18001240e`
- `GDI32!GetObjectW` at `0x18001240e`

## pseudocode

```c
__int64 __fastcall CSharedBitmap::CreateInstance(
        HBITMAP ho,
        enum WTS_ALPHATYPE a2,
        struct CGlobalRefCount *a3,
        const struct _GUID *a4,
        void **a5)
{
  int v9; // ebp
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  OLECHAR *v12; // rcx
  UINT v13; // eax
  BSTR v14; // rax
  __int128 pv; // [rsp+28h] [rbp-60h] BYREF
  __int128 v17; // [rsp+38h] [rbp-50h]

  v9 = -2147024882;
  v10 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
    goto LABEL_17;
  v10[2] = 1;
  *(_QWORD *)v10 = &CSharedBitmap::`vftable';
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *((_QWORD *)v10 + 6) = 0;
  v10[14] = 0;
  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180062B08 = 1;
  (*(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                 + 8LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( a3 )
  {
    *((_QWORD *)v11 + 6) = *((_QWORD *)a3 + 1);
    v11[14] = *((_DWORD *)a3 + 4);
    v12 = *(OLECHAR **)a3;
    if ( *((_QWORD *)v11 + 5) != *(_QWORD *)a3 )
    {
      SysFreeString(*((BSTR *)v11 + 5));
      if ( *(_QWORD *)a3 )
      {
        v13 = SysStringByteLen(*(BSTR *)a3);
        v14 = SysAllocStringByteLen(*(LPCSTR *)a3, v13);
      }
      else
      {
        v14 = 0;
      }
      *((_QWORD *)v11 + 5) = v14;
      v12 = *(OLECHAR **)a3;
      if ( *(_QWORD *)a3 )
      {
        if ( !v14 )
          ATL::AtlThrowImpl((int)v12);
      }
    }
    *((_QWORD *)a3 + 1) = 0;
    *((_DWORD *)a3 + 4) = 0;
    SysFreeString(v12);
    *(_QWORD *)a3 = 0;
  }
  *((_QWORD *)v11 + 2) = ho;
  v11[6] = a2;
  if ( !ho || (pv = 0, v17 = 0, GetObjectW(ho, 32, &pv), *((_QWORD *)&v17 + 1)) )
  {
    ho = 0;
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v11)(v11, a4, a5);
  }
  else
  {
    v9 = -2147024809;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v9 < 0 )
  {
LABEL_17:
    if ( ho )
      DeleteObject(ho);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012260  push    rbx
0x180012262  push    rbp
0x180012263  push    rsi
0x180012264  push    rdi
0x180012265  push    r12
0x180012267  push    r14
0x180012269  push    r15
0x18001226b  sub     rsp, 50h
0x18001226f  mov     rax, cs:__security_cookie
0x180012276  xor     rax, rsp
0x180012279  mov     [rsp+88h+var_40], rax
0x18001227e  mov     r12, [rsp+88h+arg_20]
0x180012286  mov     r14d, edx
0x180012289  mov     rsi, rcx
0x18001228c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012293  mov     ecx, 40h ; '@'; unsigned __int64
0x180012298  mov     r15, r9
0x18001229b  mov     rdi, r8
0x18001229e  mov     ebp, 8007000Eh
0x1800122a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800122a8  mov     [rsp+88h+var_68], rax
0x1800122ad  mov     rbx, rax
0x1800122b0  test    rax, rax
0x1800122b3  jz      loc_180012430
0x1800122b9  mov     dword ptr [rbx+8], 1
0x1800122c0  lea     rax, ??_7CSharedBitmap@@6B@; const CSharedBitmap::`vftable'
0x1800122c7  mov     [rbx], rax
0x1800122ca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800122d1  mov     qword ptr [rbx+20h], 0
0x1800122d9  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800122e0  mov     qword ptr [rbx+28h], 0
0x1800122e8  xor     r9d, r9d; Context
0x1800122eb  xor     r8d, r8d; Parameter
0x1800122ee  mov     qword ptr [rbx+30h], 0
0x1800122f6  mov     dword ptr [rbx+38h], 0
0x1800122fd  call    cs:__imp_InitOnceExecuteOnce
0x180012303  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18001230a  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012311  mov     cs:byte_180062B08, 1
0x180012318  mov     rax, [rax+8]
0x18001231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012321  test    rbx, rbx
0x180012324  jz      loc_180012430
0x18001232a  test    rdi, rdi
0x18001232d  jz      short loc_18001239E
0x18001232f  mov     rax, [rdi+8]
0x180012333  mov     [rbx+30h], rax
0x180012337  mov     eax, [rdi+10h]
0x18001233a  mov     [rbx+38h], eax
0x18001233d  mov     rcx, [rdi]
0x180012340  cmp     [rbx+28h], rcx
0x180012344  jz      short loc_180012382
0x180012346  mov     rcx, [rbx+28h]; bstrString
0x18001234a  call    cs:__imp_SysFreeString
0x180012350  mov     rcx, [rdi]; bstr
0x180012353  test    rcx, rcx
0x180012356  jz      loc_180012423
0x18001235c  call    cs:__imp_SysStringByteLen
0x180012362  mov     rcx, [rdi]; psz
0x180012365  mov     edx, eax; len
0x180012367  call    cs:__imp_SysAllocStringByteLen
0x18001236d  mov     [rbx+28h], rax
0x180012371  mov     rcx, [rdi]; int
0x180012374  test    rcx, rcx
0x180012377  jz      short loc_180012382
0x180012379  test    rax, rax
0x18001237c  jz      loc_18001242A
0x180012382  mov     qword ptr [rdi+8], 0
0x18001238a  mov     dword ptr [rdi+10h], 0
0x180012391  call    cs:__imp_SysFreeString
0x180012397  mov     qword ptr [rdi], 0
0x18001239e  mov     [rbx+10h], rsi
0x1800123a2  mov     [rbx+18h], r14d
0x1800123a6  test    rsi, rsi
0x1800123a9  jnz     short loc_1800123F4
0x1800123ab  mov     rax, [rbx]
0x1800123ae  xor     esi, esi
0x1800123b0  mov     r8, r12
0x1800123b3  mov     rdx, r15
0x1800123b6  mov     rcx, rbx
0x1800123b9  mov     rax, [rax]
0x1800123bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123c1  mov     ebp, eax
0x1800123c3  mov     rdx, [rbx]
0x1800123c6  mov     rcx, rbx
0x1800123c9  mov     rax, [rdx+10h]
0x1800123cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d2  test    ebp, ebp
0x1800123d4  js      short loc_180012430
0x1800123d6  mov     eax, ebp
0x1800123d8  mov     rcx, [rsp+88h+var_40]
0x1800123dd  xor     rcx, rsp; StackCookie
0x1800123e0  call    __security_check_cookie
0x1800123e5  add     rsp, 50h
0x1800123e9  pop     r15
0x1800123eb  pop     r14
0x1800123ed  pop     r12
0x1800123ef  pop     rdi
0x1800123f0  pop     rsi
0x1800123f1  pop     rbp
0x1800123f2  pop     rbx
0x1800123f3  retn
0x1800123f4  xorps   xmm0, xmm0
0x1800123f7  lea     r8, [rsp+88h+pv]; pv
0x1800123fc  mov     edx, 20h ; ' '; c
0x180012401  mov     rcx, rsi; h
0x180012404  movups  [rsp+88h+pv], xmm0
0x180012409  movups  [rsp+88h+var_50], xmm0
0x18001240e  call    cs:__imp_GetObjectW
0x180012414  cmp     qword ptr [rsp+88h+var_50+8], 0
0x18001241a  jnz     short loc_1800123AB
0x18001241c  mov     ebp, 80070057h
0x180012421  jmp     short loc_1800123C3
0x180012423  xor     eax, eax
0x180012425  jmp     loc_18001236D
0x18001242a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012430  test    rsi, rsi
0x180012433  jz      short loc_1800123D6
0x180012435  mov     rcx, rsi; ho
0x180012438  call    cs:__imp_DeleteObject
0x18001243e  jmp     short loc_1800123D6
```
