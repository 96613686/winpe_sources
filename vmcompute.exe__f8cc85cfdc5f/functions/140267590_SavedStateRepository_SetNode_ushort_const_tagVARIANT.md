# SavedStateRepository::SetNode(ushort const *,tagVARIANT)

- ea: `0x140267590`
- end: `0x1402677ae`
- name: `?SetNode@SavedStateRepository@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1402677f0`

## callees

- `0x1401332f0`
- `0x1402667dc`
- `0x140267034`
- `0x140267590`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402675b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402675b5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1402676a6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1402676a6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140267689`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140267689`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14026766e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14026766e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1402676eb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1402676eb`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall SavedStateRepository::SetNode(
        SavedStateRepository *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  int NodeForRollback; // ebx
  SAFEARRAY *parray; // r14
  int v8; // eax
  struct tagVARIANT *v10[2]; // [rsp+30h] [rbp-48h] BYREF
  void *ppvData[2]; // [rsp+40h] [rbp-38h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 33) != GetCurrentThreadId() )
    return (unsigned int)-2147418113;
  v10[0] = 0;
  NodeForRollback = SavedStateRepository::GetNodeForRollback(this, a2, v10);
  if ( NodeForRollback < 0 )
    return (unsigned int)NodeForRollback;
  (*(void (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 13) + 168LL))(
    *((_QWORD *)this + 13),
    a2);
  if ( a3->vt == 5 )
  {
    NodeForRollback = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 13) + 112LL))(
                        *((_QWORD *)this + 13),
                        a2);
  }
  else
  {
    switch ( a3->vt )
    {
      case 8u:
        v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, LONGLONG))(**((_QWORD **)this + 13) + 128LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->llVal);
        break;
      case 0xBu:
        v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, bool))(**((_QWORD **)this + 13) + 96LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->iVal == -1);
        break;
      case 0x14u:
        v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, LONGLONG))(**((_QWORD **)this + 13) + 64LL))(
               *((_QWORD *)this + 13),
               a2,
               a3->llVal);
        break;
      case 0x2011u:
        ppvData[0] = 0;
        plLbound = 0;
        parray = a3->parray;
        SafeArrayAccessData(parray, ppvData);
        SafeArrayGetLBound(parray, 1u, &plLbound);
        if ( plLbound )
        {
          NodeForRollback = -2147024809;
        }
        else
        {
          SafeArrayGetUBound(parray, 1u, &plLbound);
          ++plLbound;
          NodeForRollback = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void *))(**((_QWORD **)this + 13)
                                                                                                + 144LL))(
                              *((_QWORD *)this + 13),
                              a2,
                              ppvData[0]);
        }
        SafeArrayUnaccessData(parray);
        goto LABEL_19;
      default:
        return (unsigned int)-2147467259;
    }
    NodeForRollback = v8;
  }
LABEL_19:
  if ( NodeForRollback >= 0 )
  {
    ppvData[0] = (void *)a2;
    ppvData[1] = v10[0];
    std::map<std::wstring,tagVARIANT *>::insert<std::pair<unsigned short const *,tagVARIANT *>,0>(
      (char *)this + 112,
      v10,
      ppvData);
  }
  return (unsigned int)NodeForRollback;
}

```

## disassembly

```asm
0x140267590  mov     [rsp+arg_18], rbx
0x140267595  push    rsi
0x140267596  push    rdi
0x140267597  push    r14
0x140267599  sub     rsp, 60h
0x14026759d  mov     rax, cs:__security_cookie
0x1402675a4  xor     rax, rsp
0x1402675a7  mov     [rsp+78h+var_20], rax
0x1402675ac  mov     r14, r8
0x1402675af  mov     rsi, rdx
0x1402675b2  mov     rdi, rcx
0x1402675b5  call    cs:__imp_GetCurrentThreadId
0x1402675bc  nop     dword ptr [rax+rax+00h]
0x1402675c1  mov     r8d, [rdi+84h]
0x1402675c8  cmp     r8d, eax
0x1402675cb  jz      short loc_1402675D7
0x1402675cd  mov     ebx, 8000FFFFh
0x1402675d2  jmp     loc_140267787
0x1402675d7  mov     [rsp+78h+var_48], 0
0x1402675e0  lea     r8, [rsp+78h+var_48]; struct tagVARIANT **
0x1402675e5  mov     rdx, rsi; unsigned __int16 *
0x1402675e8  mov     rcx, rdi; this
0x1402675eb  call    ?GetNodeForRollback@SavedStateRepository@@AEAAJPEBGAEAPEAUtagVARIANT@@@Z; SavedStateRepository::GetNodeForRollback(ushort const *,tagVARIANT * &)
0x1402675f0  mov     ebx, eax
0x1402675f2  test    eax, eax
0x1402675f4  js      loc_140267787
0x1402675fa  mov     rcx, [rdi+68h]
0x1402675fe  mov     rax, [rcx]
0x140267601  mov     rdx, rsi
0x140267604  mov     rax, [rax+0A8h]
0x14026760b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140267610  cmp     word ptr [r14], 5
0x140267615  jz      loc_140267746
0x14026761b  cmp     word ptr [r14], 8
0x140267620  jz      loc_140267728
0x140267626  cmp     word ptr [r14], 0Bh
0x14026762b  jz      loc_140267706
0x140267631  cmp     word ptr [r14], 14h
0x140267636  jz      loc_1402676F9
0x14026763c  mov     eax, 2011h
0x140267641  cmp     [r14], ax
0x140267645  jz      short loc_140267651
0x140267647  mov     ebx, 80004005h
0x14026764c  jmp     loc_140267787
0x140267651  mov     [rsp+78h+ppvData], 0
0x14026765a  mov     [rsp+78h+plLbound], 0
0x140267662  mov     r14, [r14+8]
0x140267666  lea     rdx, [rsp+78h+ppvData]; ppvData
0x14026766b  mov     rcx, r14; psa
0x14026766e  call    cs:__imp_SafeArrayAccessData
0x140267675  nop     dword ptr [rax+rax+00h]
0x14026767a  lea     r8, [rsp+78h+plLbound]; plLbound
0x14026767f  mov     ebx, 1
0x140267684  mov     edx, ebx; nDim
0x140267686  mov     rcx, r14; psa
0x140267689  call    cs:__imp_SafeArrayGetLBound
0x140267690  nop     dword ptr [rax+rax+00h]
0x140267695  cmp     [rsp+78h+plLbound], 0
0x14026769a  jnz     short loc_1402676E3
0x14026769c  lea     r8, [rsp+78h+plLbound]; plUbound
0x1402676a1  mov     edx, ebx; nDim
0x1402676a3  mov     rcx, r14; psa
0x1402676a6  call    cs:__imp_SafeArrayGetUBound
0x1402676ad  nop     dword ptr [rax+rax+00h]
0x1402676b2  mov     r9d, [rsp+78h+plLbound]
0x1402676b7  add     r9d, ebx
0x1402676ba  mov     [rsp+78h+plLbound], r9d
0x1402676bf  mov     rcx, [rdi+68h]
0x1402676c3  mov     rax, [rcx]
0x1402676c6  mov     [rsp+78h+var_58], r9d
0x1402676cb  mov     r8, [rsp+78h+ppvData]
0x1402676d0  mov     rdx, rsi
0x1402676d3  mov     rax, [rax+90h]
0x1402676da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402676df  mov     ebx, eax
0x1402676e1  jmp     short loc_1402676E8
0x1402676e3  mov     ebx, 80070057h
0x1402676e8  mov     rcx, r14; psa
0x1402676eb  call    cs:__imp_SafeArrayUnaccessData
0x1402676f2  nop     dword ptr [rax+rax+00h]
0x1402676f7  jmp     short loc_140267761
0x1402676f9  mov     rcx, [rdi+68h]
0x1402676fd  mov     rax, [rcx]
0x140267700  mov     rax, [rax+40h]
0x140267704  jmp     short loc_140267736
0x140267706  mov     rcx, [rdi+68h]
0x14026770a  mov     rax, [rcx]
0x14026770d  xor     r8d, r8d
0x140267710  cmp     word ptr [r14+8], 0FFFFh
0x140267716  setz    r8b
0x14026771a  mov     rdx, rsi
0x14026771d  mov     rax, [rax+60h]
0x140267721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140267726  jmp     short loc_140267742
0x140267728  mov     rcx, [rdi+68h]
0x14026772c  mov     rax, [rcx]
0x14026772f  mov     rax, [rax+80h]
0x140267736  mov     rdx, rsi
0x140267739  mov     r8, [r14+8]
0x14026773d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140267742  mov     ebx, eax
0x140267744  jmp     short loc_140267761
0x140267746  mov     rcx, [rdi+68h]
0x14026774a  mov     rax, [rcx]
0x14026774d  movsd   xmm2, qword ptr [r14+8]
0x140267753  mov     rdx, rsi
0x140267756  mov     rax, [rax+70h]
0x14026775a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14026775f  mov     ebx, eax
0x140267761  test    ebx, ebx
0x140267763  js      short loc_140267787
0x140267765  mov     [rsp+78h+ppvData], rsi
0x14026776a  mov     rax, [rsp+78h+var_48]
0x14026776f  mov     [rsp+78h+var_30], rax
0x140267774  lea     rcx, [rdi+70h]
0x140267778  lea     r8, [rsp+78h+ppvData]
0x14026777d  lea     rdx, [rsp+78h+var_48]
0x140267782  call    ??$insert@U?$pair@PEBGPEAUtagVARIANT@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGPEAUtagVARIANT@@@1@@Z; std::map<std::wstring,tagVARIANT *>::insert<std::pair<ushort const *,tagVARIANT *>,0>(std::pair<ushort const *,tagVARIANT *> &&)
0x140267787  mov     eax, ebx
0x140267789  jmp     short loc_14026778F
0x14026778b  mov     eax, [rsp+78h+plLbound]
0x14026778f  mov     rcx, [rsp+78h+var_20]
0x140267794  xor     rcx, rsp; StackCookie
0x140267797  call    __security_check_cookie
0x14026779c  mov     rbx, [rsp+78h+arg_18]
0x1402677a4  add     rsp, 60h
0x1402677a8  pop     r14
0x1402677aa  pop     rdi
0x1402677ab  pop     rsi
0x1402677ac  retn
```
