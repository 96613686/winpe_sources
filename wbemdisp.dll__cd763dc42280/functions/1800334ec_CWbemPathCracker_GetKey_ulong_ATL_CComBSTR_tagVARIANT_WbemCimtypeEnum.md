# CWbemPathCracker::GetKey(ulong,ATL::CComBSTR &,tagVARIANT &,WbemCimtypeEnum &)

- ea: `0x1800334ec`
- end: `0x180033628`
- name: `?GetKey@CWbemPathCracker@@QEAA_NKAEAVCComBSTR@ATL@@AEAUtagVARIANT@@AEAW4WbemCimtypeEnum@@@Z`
- size: `316`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, unsigned int, struct ATL::CComBSTR *, struct tagVARIANT *, enum WbemCimtypeEnum *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023320`
- `0x180032db4`

## callees

- `0x18000c0b0`
- `0x1800334ec`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800335f0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800335f0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800335a5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800335a5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033608`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033608`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CWbemPathCracker::GetKey(
        CWbemPathCracker *this,
        unsigned int a2,
        struct ATL::CComBSTR *a3,
        struct tagVARIANT *a4,
        enum WbemCimtypeEnum *a5)
{
  char v8; // di
  __int64 v9; // rcx
  OLECHAR *v10; // rax
  OLECHAR *v11; // rbx
  enum WbemCimtypeEnum v13; // [rsp+40h] [rbp-18h] BYREF
  __int64 v14[2]; // [rsp+48h] [rbp-10h] BYREF
  int v15; // [rsp+90h] [rbp+38h] BYREF

  v8 = 0;
  if ( *((_DWORD *)this + 7) == 1 )
  {
    v9 = *((_QWORD *)this + 1);
    if ( v9 )
    {
      v14[0] = 0;
      if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 176LL))(v9, v14) >= 0 )
      {
        if ( v14[0] )
        {
          v15 = 0;
          v13 = 0;
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, int *, _QWORD, struct tagVARIANT *, enum WbemCimtypeEnum *))(*(_QWORD *)v14[0] + 56LL))(
            v14[0],
            a2,
            0,
            &v15,
            0,
            a4,
            &v13);
          v10 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v15 + 1), 2u));
          v11 = v10;
          if ( v10 )
          {
            v10[v15] = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, int *, OLECHAR *, struct tagVARIANT *, enum WbemCimtypeEnum *))(*(_QWORD *)v14[0] + 56LL))(
                   v14[0],
                   a2,
                   0,
                   &v15,
                   v10,
                   a4,
                   &v13) >= 0 )
            {
              *(_QWORD *)a3 = SysAllocString(v11);
              *a5 = v13;
              v8 = 1;
            }
            CWin32DefaultArena::WbemMemFree(v11);
          }
        }
      }
      ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(v14);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800334ec  push    rbp
0x1800334ee  push    rbx
0x1800334ef  push    rsi
0x1800334f0  push    rdi
0x1800334f1  push    r14
0x1800334f3  push    r15
0x1800334f5  mov     rbp, rsp
0x1800334f8  sub     rsp, 58h
0x1800334fc  mov     r14, r9
0x1800334ff  mov     rsi, r8
0x180033502  mov     r15d, edx
0x180033505  xor     dil, dil
0x180033508  cmp     dword ptr [rcx+1Ch], 1
0x18003350c  jnz     loc_180033618
0x180033512  mov     rcx, [rcx+8]
0x180033516  test    rcx, rcx
0x180033519  jz      loc_180033618
0x18003351f  mov     [rbp+var_10], 0
0x180033527  mov     rax, [rcx]
0x18003352a  lea     rdx, [rbp+var_10]
0x18003352e  mov     rax, [rax+0B0h]
0x180033535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003353a  test    eax, eax
0x18003353c  js      loc_18003360F
0x180033542  mov     rcx, [rbp+var_10]
0x180033546  test    rcx, rcx
0x180033549  jz      loc_18003360F
0x18003354f  mov     [rbp+arg_0], 0
0x180033556  mov     [rbp+var_18], 0
0x18003355d  mov     rax, [rcx]
0x180033560  lea     rdx, [rbp+var_18]
0x180033564  mov     [rsp+58h+var_28], rdx
0x180033569  mov     [rsp+58h+var_30], r14
0x18003356e  mov     [rsp+58h+var_38], 0
0x180033577  lea     r9, [rbp+arg_0]
0x18003357b  xor     r8d, r8d
0x18003357e  mov     edx, r15d
0x180033581  mov     rax, [rax+38h]
0x180033585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003358a  mov     ecx, [rbp+arg_0]
0x18003358d  inc     ecx
0x18003358f  mov     eax, 2
0x180033594  mul     rcx
0x180033597  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003359e  cmovb   rax, rcx
0x1800335a2  mov     rcx, rax
0x1800335a5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800335ab  mov     rbx, rax
0x1800335ae  test    rax, rax
0x1800335b1  jz      short loc_18003360F
0x1800335b3  mov     ecx, [rbp+arg_0]
0x1800335b6  xor     eax, eax
0x1800335b8  mov     [rbx+rcx*2], ax
0x1800335bc  mov     rcx, [rbp+var_10]
0x1800335c0  mov     rax, [rcx]
0x1800335c3  lea     rdx, [rbp+var_18]
0x1800335c7  mov     [rsp+58h+var_28], rdx
0x1800335cc  mov     [rsp+58h+var_30], r14
0x1800335d1  mov     [rsp+58h+var_38], rbx
0x1800335d6  lea     r9, [rbp+arg_0]
0x1800335da  xor     r8d, r8d
0x1800335dd  mov     edx, r15d
0x1800335e0  mov     rax, [rax+38h]
0x1800335e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335e9  test    eax, eax
0x1800335eb  js      short loc_180033605
0x1800335ed  mov     rcx, rbx; psz
0x1800335f0  call    cs:__imp_SysAllocString
0x1800335f6  mov     [rsi], rax
0x1800335f9  mov     rcx, [rbp+arg_20]
0x1800335fd  mov     eax, [rbp+var_18]
0x180033600  mov     [rcx], eax
0x180033602  mov     dil, 1
0x180033605  mov     rcx, rbx
0x180033608  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003360e  nop
0x18003360f  lea     rcx, [rbp+var_10]
0x180033613  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180033618  mov     al, dil
0x18003361b  add     rsp, 58h
0x18003361f  pop     r15
0x180033621  pop     r14
0x180033623  pop     rdi
0x180033624  pop     rsi
0x180033625  pop     rbx
0x180033626  pop     rbp
0x180033627  retn
```
