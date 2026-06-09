# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180011000`
- end: `0x1800112a2`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `674`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int *)`
- caller_count: `14`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010f38`
- `0x180010f60`
- `0x180010f88`
- `0x180010fb0`
- `0x180010fd8`
- `0x1800112a8`
- `0x1800112d0`
- `0x1800112f8`
- `0x180011320`
- `0x180011348`
- `0x180011370`
- `0x180011398`
- `0x1800113c0`
- `0x180017b60`

## callees

- `0x180003e10`
- `0x180003e34`
- `0x1800045b1`
- `0x1800045bd`
- `0x1800045d5`
- `0x1800045e1`
- `0x180006424`
- `0x1800066dc`
- `0x180011000`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001129b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001129b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001116b`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18001116b`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  BSTR *v7; // rsi
  BSTR v8; // rbx
  BSTR v9; // r15
  BSTR v10; // rbx
  void (__fastcall *v11)(BSTR, __int64); // rdi
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *hstring_on_heap; // rbx
  UINT v14; // ebx
  unsigned int v15; // r8d
  winrt::impl *v16; // r12
  OLECHAR *i; // r15
  OLECHAR *v18; // rdi
  int v19; // eax
  HANDLE ProcessHeap; // rax
  IErrorInfo *v22; // [rsp+30h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-30h] BYREF
  BSTR v24; // [rsp+40h] [rbp-28h] BYREF
  __int64 v25; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+A8h] [rbp+40h]
  IErrorInfo *pperrinfo; // [rsp+B0h] [rbp+48h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (BSTR *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    pbstr = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
    v8 = pbstr;
    v24 = pbstr;
  }
  else
  {
    v24 = 0;
    v8 = 0;
  }
  if ( v7 == &v24 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v24);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v7);
    *v7 = v8;
    v9 = v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v7;
    if ( *v7 )
    {
      pbstr = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      v26[0] = pbstr;
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v26);
      }
    }
  }
  else
  {
    pbstr = 0;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
      hstring_on_heap = 0;
      if ( pbstr )
      {
        v14 = SysStringLen_0(pbstr);
        v16 = (winrt::impl *)pbstr;
        for ( i = &pbstr[v14 - 1]; v14; --v14 )
        {
          if ( !(unsigned int)_o_iswspace(*i) )
            break;
          --i;
        }
        hstring_on_heap = (volatile signed __int32 *)winrt::impl::create_hstring_on_heap(
                                                       v16,
                                                       (const unsigned __int16 *)v14,
                                                       v15);
      }
    }
    else
    {
      hstring_on_heap = 0;
    }
    RoOriginateLanguageException_0(a2, hstring_on_heap, 0);
    if ( winrt_throw_hresult_handler )
      winrt_throw_hresult_handler(*a4, *((_QWORD *)a4 + 1), *((_QWORD *)a4 + 2), retaddr, a2);
    v22 = 0;
    GetErrorInfo_0(0, &v22);
    if ( v22 )
    {
      v26[0] = 0;
      ((void (__fastcall *)(IErrorInfo *, __int64 *, _QWORD *))v22->lpVtbl->QueryInterface)(
        v22,
        winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
        v26);
      v18 = (OLECHAR *)v26[0];
      v25 = v26[0];
    }
    else
    {
      v25 = 0;
      v18 = 0;
    }
    if ( v7 == (BSTR *)&v25 )
    {
      if ( v18 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v25);
    }
    else
    {
      if ( *v7 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(v7);
      *v7 = v18;
    }
    if ( v22 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v22);
    if ( hstring_on_heap )
    {
      v19 = _InterlockedDecrement(hstring_on_heap + 6);
      if ( v19 )
      {
        if ( v19 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)hstring_on_heap);
      }
    }
    if ( pbstr )
      WINRT_IMPL_SysFreeString(pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180011000  push    rbp
0x180011002  push    rbx
0x180011003  push    rsi
0x180011004  push    rdi
0x180011005  push    r12
0x180011007  push    r13
0x180011009  push    r14
0x18001100b  push    r15
0x18001100d  mov     rbp, rsp
0x180011010  sub     rsp, 68h
0x180011014  mov     r13, r9
0x180011017  mov     edi, edx
0x180011019  mov     r14, rcx
0x18001101c  xor     r12d, r12d
0x18001101f  mov     [rcx], r12
0x180011022  mov     dword ptr [rcx+8], 0AABBCCDDh
0x180011029  mov     [rcx+0Ch], edx
0x18001102c  lea     rsi, [rcx+10h]
0x180011030  mov     [rsi], r12
0x180011033  mov     [rbp+pperrinfo], r12
0x180011037  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001103b  xor     ecx, ecx; dwReserved
0x18001103d  call    GetErrorInfo_0
0x180011042  mov     rcx, [rbp+pperrinfo]
0x180011046  test    rcx, rcx
0x180011049  jnz     short loc_180011054
0x18001104b  mov     [rbp+var_28], r12
0x18001104f  mov     ebx, r12d
0x180011052  jmp     short loc_180011076
0x180011054  mov     [rbp+pbstr], r12
0x180011058  mov     rax, [rcx]
0x18001105b  lea     r8, [rbp+pbstr]
0x18001105f  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x180011066  mov     rax, [rax]
0x180011069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001106e  mov     rbx, [rbp+pbstr]
0x180011072  mov     [rbp+var_28], rbx
0x180011076  lea     rax, [rbp+var_28]
0x18001107a  cmp     rsi, rax
0x18001107d  jz      short loc_180011094
0x18001107f  cmp     [rsi], r12
0x180011082  jz      short loc_18001108C
0x180011084  mov     rcx, rsi
0x180011087  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001108c  mov     [rsi], rbx
0x18001108f  mov     r15, rbx
0x180011092  jmp     short loc_1800110A5
0x180011094  mov     r15, [rsi]
0x180011097  test    rbx, rbx
0x18001109a  jz      short loc_1800110A5
0x18001109c  lea     rcx, [rbp+var_28]
0x1800110a0  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800110a5  test    r15, r15
0x1800110a8  jz      short loc_180011125
0x1800110aa  mov     rbx, [rsi]
0x1800110ad  mov     rax, [rbx]
0x1800110b0  mov     rdi, [rax+20h]
0x1800110b4  mov     rcx, [r14]; bstrString
0x1800110b7  test    rcx, rcx
0x1800110ba  jz      short loc_1800110C4
0x1800110bc  call    WINRT_IMPL_SysFreeString
0x1800110c1  mov     [r14], r12
0x1800110c4  mov     rdx, r14
0x1800110c7  mov     rcx, rbx
0x1800110ca  mov     rax, rdi
0x1800110cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d2  mov     rcx, [rsi]
0x1800110d5  test    rcx, rcx
0x1800110d8  jz      loc_180011274
0x1800110de  mov     [rbp+pbstr], r12
0x1800110e2  mov     rax, [rcx]
0x1800110e5  lea     r8, [rbp+pbstr]
0x1800110e9  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x1800110f0  mov     rax, [rax]
0x1800110f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110f8  mov     rcx, [rbp+pbstr]
0x1800110fc  mov     [rbp+var_18], rcx
0x180011100  test    rcx, rcx
0x180011103  jz      loc_180011274
0x180011109  mov     rax, [rcx]
0x18001110c  xor     edx, edx
0x18001110e  mov     rax, [rax+28h]
0x180011112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011117  lea     rcx, [rbp+var_18]
0x18001111b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180011120  jmp     loc_180011274
0x180011125  mov     [rbp+pbstr], r12
0x180011129  mov     rcx, [rbp+pperrinfo]
0x18001112d  test    rcx, rcx
0x180011130  jz      short loc_180011190
0x180011132  mov     rax, [rcx]
0x180011135  lea     rdx, [rbp+pbstr]
0x180011139  mov     rax, [rax+28h]
0x18001113d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011142  mov     rbx, r12
0x180011145  mov     rcx, [rbp+pbstr]; pbstr
0x180011149  test    rcx, rcx
0x18001114c  jz      short loc_180011193
0x18001114e  call    SysStringLen_0
0x180011153  mov     ebx, eax
0x180011155  mov     r12, [rbp+pbstr]
0x180011159  mov     r15d, eax
0x18001115c  dec     r15
0x18001115f  lea     r15, [r12+r15*2]
0x180011163  test    eax, eax
0x180011165  jz      short loc_18001117E
0x180011167  movzx   ecx, word ptr [r15]
0x18001116b  call    cs:__imp__o_iswspace
0x180011171  test    eax, eax
0x180011173  jz      short loc_18001117E
0x180011175  sub     r15, 2
0x180011179  add     ebx, 0FFFFFFFFh
0x18001117c  jnz     short loc_180011167
0x18001117e  mov     edx, ebx; unsigned __int16 *
0x180011180  mov     rcx, r12; this
0x180011183  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180011188  mov     rbx, rax
0x18001118b  xor     r12d, r12d
0x18001118e  jmp     short loc_180011193
0x180011190  mov     rbx, r12
0x180011193  xor     r8d, r8d
0x180011196  mov     rdx, rbx
0x180011199  mov     ecx, edi
0x18001119b  call    RoOriginateLanguageException_0
0x1800111a0  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x1800111a7  test    rax, rax
0x1800111aa  jz      short loc_1800111C5
0x1800111ac  mov     r9, [rbp+40h]
0x1800111b0  mov     [rsp+68h+var_48], edi
0x1800111b4  mov     r8, [r13+10h]
0x1800111b8  mov     rdx, [r13+8]
0x1800111bc  mov     ecx, [r13+0]
0x1800111c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111c5  mov     [rbp+var_38], r12
0x1800111c9  lea     rdx, [rbp+var_38]; pperrinfo
0x1800111cd  xor     ecx, ecx; dwReserved
0x1800111cf  call    GetErrorInfo_0
0x1800111d4  mov     rcx, [rbp+var_38]
0x1800111d8  test    rcx, rcx
0x1800111db  jnz     short loc_1800111E6
0x1800111dd  mov     [rbp+var_20], r12
0x1800111e1  mov     rdi, r12
0x1800111e4  jmp     short loc_180011208
0x1800111e6  mov     [rbp+var_18], r12
0x1800111ea  mov     rax, [rcx]
0x1800111ed  lea     r8, [rbp+var_18]
0x1800111f1  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x1800111f8  mov     rax, [rax]
0x1800111fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011200  mov     rdi, [rbp+var_18]
0x180011204  mov     [rbp+var_20], rdi
0x180011208  lea     rax, [rbp+var_20]
0x18001120c  cmp     rsi, rax
0x18001120f  jz      short loc_180011223
0x180011211  cmp     [rsi], r12
0x180011214  jz      short loc_18001121E
0x180011216  mov     rcx, rsi
0x180011219  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001121e  mov     [rsi], rdi
0x180011221  jmp     short loc_180011231
0x180011223  test    rdi, rdi
0x180011226  jz      short loc_180011231
0x180011228  lea     rcx, [rbp+var_20]
0x18001122c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180011231  cmp     [rbp+var_38], r12
0x180011235  jz      short loc_180011241
0x180011237  lea     rcx, [rbp+var_38]
0x18001123b  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180011240  nop
0x180011241  test    rbx, rbx
0x180011244  jz      short loc_180011266
0x180011246  or      eax, 0FFFFFFFFh
0x180011249  lock xadd [rbx+18h], eax
0x18001124e  sub     eax, 1
0x180011251  jnz     short loc_180011297
0x180011253  nop
0x180011254  call    WINRT_IMPL_GetProcessHeap
0x180011259  mov     rcx, rax; hHeap
0x18001125c  mov     r8, rbx; lpMem
0x18001125f  xor     edx, edx; dwFlags
0x180011261  call    WINRT_IMPL_HeapFree
0x180011266  mov     rcx, [rbp+pbstr]; bstrString
0x18001126a  test    rcx, rcx
0x18001126d  jz      short loc_180011274
0x18001126f  call    WINRT_IMPL_SysFreeString
0x180011274  cmp     [rbp+pperrinfo], r12
0x180011278  jz      short loc_180011283
0x18001127a  lea     rcx, [rbp+pperrinfo]
0x18001127e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180011283  mov     rax, r14
0x180011286  add     rsp, 68h
0x18001128a  pop     r15
0x18001128c  pop     r14
0x18001128e  pop     r13
0x180011290  pop     r12
0x180011292  pop     rdi
0x180011293  pop     rsi
0x180011294  pop     rbx
0x180011295  pop     rbp
0x180011296  retn
0x180011297  test    eax, eax
0x180011299  jns     short loc_180011266
0x18001129b  call    cs:__imp_abort
```
