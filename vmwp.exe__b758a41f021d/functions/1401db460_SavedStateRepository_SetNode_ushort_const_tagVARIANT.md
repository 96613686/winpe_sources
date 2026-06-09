# SavedStateRepository::SetNode(ushort const *,tagVARIANT)

- ea: `0x1401db460`
- end: `0x1401db67e`
- name: `?SetNode@SavedStateRepository@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400b2d40`

## callees

- `0x14011ea40`
- `0x1401da7c0`
- `0x1401daec4`
- `0x1401db460`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401db485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401db485`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401db576`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401db576`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401db559`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401db559`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401db53e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401db53e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401db5bb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401db5bb`

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
0x1401db460  mov     [rsp+arg_18], rbx
0x1401db465  push    rsi
0x1401db466  push    rdi
0x1401db467  push    r14
0x1401db469  sub     rsp, 60h
0x1401db46d  mov     rax, cs:__security_cookie
0x1401db474  xor     rax, rsp
0x1401db477  mov     [rsp+78h+var_20], rax
0x1401db47c  mov     r14, r8
0x1401db47f  mov     rsi, rdx
0x1401db482  mov     rdi, rcx
0x1401db485  call    cs:__imp_GetCurrentThreadId
0x1401db48c  nop     dword ptr [rax+rax+00h]
0x1401db491  mov     r8d, [rdi+84h]
0x1401db498  cmp     r8d, eax
0x1401db49b  jz      short loc_1401DB4A7
0x1401db49d  mov     ebx, 8000FFFFh
0x1401db4a2  jmp     loc_1401DB657
0x1401db4a7  mov     [rsp+78h+var_48], 0
0x1401db4b0  lea     r8, [rsp+78h+var_48]; struct tagVARIANT **
0x1401db4b5  mov     rdx, rsi; unsigned __int16 *
0x1401db4b8  mov     rcx, rdi; this
0x1401db4bb  call    ?GetNodeForRollback@SavedStateRepository@@AEAAJPEBGAEAPEAUtagVARIANT@@@Z; SavedStateRepository::GetNodeForRollback(ushort const *,tagVARIANT * &)
0x1401db4c0  mov     ebx, eax
0x1401db4c2  test    eax, eax
0x1401db4c4  js      loc_1401DB657
0x1401db4ca  mov     rcx, [rdi+68h]
0x1401db4ce  mov     rax, [rcx]
0x1401db4d1  mov     rdx, rsi
0x1401db4d4  mov     rax, [rax+0A8h]
0x1401db4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401db4e0  cmp     word ptr [r14], 5
0x1401db4e5  jz      loc_1401DB616
0x1401db4eb  cmp     word ptr [r14], 8
0x1401db4f0  jz      loc_1401DB5F8
0x1401db4f6  cmp     word ptr [r14], 0Bh
0x1401db4fb  jz      loc_1401DB5D6
0x1401db501  cmp     word ptr [r14], 14h
0x1401db506  jz      loc_1401DB5C9
0x1401db50c  mov     eax, 2011h
0x1401db511  cmp     [r14], ax
0x1401db515  jz      short loc_1401DB521
0x1401db517  mov     ebx, 80004005h
0x1401db51c  jmp     loc_1401DB657
0x1401db521  mov     [rsp+78h+ppvData], 0
0x1401db52a  mov     [rsp+78h+plLbound], 0
0x1401db532  mov     r14, [r14+8]
0x1401db536  lea     rdx, [rsp+78h+ppvData]; ppvData
0x1401db53b  mov     rcx, r14; psa
0x1401db53e  call    cs:__imp_SafeArrayAccessData
0x1401db545  nop     dword ptr [rax+rax+00h]
0x1401db54a  lea     r8, [rsp+78h+plLbound]; plLbound
0x1401db54f  mov     ebx, 1
0x1401db554  mov     edx, ebx; nDim
0x1401db556  mov     rcx, r14; psa
0x1401db559  call    cs:__imp_SafeArrayGetLBound
0x1401db560  nop     dword ptr [rax+rax+00h]
0x1401db565  cmp     [rsp+78h+plLbound], 0
0x1401db56a  jnz     short loc_1401DB5B3
0x1401db56c  lea     r8, [rsp+78h+plLbound]; plUbound
0x1401db571  mov     edx, ebx; nDim
0x1401db573  mov     rcx, r14; psa
0x1401db576  call    cs:__imp_SafeArrayGetUBound
0x1401db57d  nop     dword ptr [rax+rax+00h]
0x1401db582  mov     r9d, [rsp+78h+plLbound]
0x1401db587  add     r9d, ebx
0x1401db58a  mov     [rsp+78h+plLbound], r9d
0x1401db58f  mov     rcx, [rdi+68h]
0x1401db593  mov     rax, [rcx]
0x1401db596  mov     [rsp+78h+var_58], r9d
0x1401db59b  mov     r8, [rsp+78h+ppvData]
0x1401db5a0  mov     rdx, rsi
0x1401db5a3  mov     rax, [rax+90h]
0x1401db5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401db5af  mov     ebx, eax
0x1401db5b1  jmp     short loc_1401DB5B8
0x1401db5b3  mov     ebx, 80070057h
0x1401db5b8  mov     rcx, r14; psa
0x1401db5bb  call    cs:__imp_SafeArrayUnaccessData
0x1401db5c2  nop     dword ptr [rax+rax+00h]
0x1401db5c7  jmp     short loc_1401DB631
0x1401db5c9  mov     rcx, [rdi+68h]
0x1401db5cd  mov     rax, [rcx]
0x1401db5d0  mov     rax, [rax+40h]
0x1401db5d4  jmp     short loc_1401DB606
0x1401db5d6  mov     rcx, [rdi+68h]
0x1401db5da  mov     rax, [rcx]
0x1401db5dd  xor     r8d, r8d
0x1401db5e0  cmp     word ptr [r14+8], 0FFFFh
0x1401db5e6  setz    r8b
0x1401db5ea  mov     rdx, rsi
0x1401db5ed  mov     rax, [rax+60h]
0x1401db5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401db5f6  jmp     short loc_1401DB612
0x1401db5f8  mov     rcx, [rdi+68h]
0x1401db5fc  mov     rax, [rcx]
0x1401db5ff  mov     rax, [rax+80h]
0x1401db606  mov     rdx, rsi
0x1401db609  mov     r8, [r14+8]
0x1401db60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401db612  mov     ebx, eax
0x1401db614  jmp     short loc_1401DB631
0x1401db616  mov     rcx, [rdi+68h]
0x1401db61a  mov     rax, [rcx]
0x1401db61d  movsd   xmm2, qword ptr [r14+8]
0x1401db623  mov     rdx, rsi
0x1401db626  mov     rax, [rax+70h]
0x1401db62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401db62f  mov     ebx, eax
0x1401db631  test    ebx, ebx
0x1401db633  js      short loc_1401DB657
0x1401db635  mov     [rsp+78h+ppvData], rsi
0x1401db63a  mov     rax, [rsp+78h+var_48]
0x1401db63f  mov     [rsp+78h+var_30], rax
0x1401db644  lea     rcx, [rdi+70h]
0x1401db648  lea     r8, [rsp+78h+ppvData]
0x1401db64d  lea     rdx, [rsp+78h+var_48]
0x1401db652  call    ??$insert@U?$pair@PEBGPEAUtagVARIANT@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGPEAUtagVARIANT@@@1@@Z; std::map<std::wstring,tagVARIANT *>::insert<std::pair<ushort const *,tagVARIANT *>,0>(std::pair<ushort const *,tagVARIANT *> &&)
0x1401db657  mov     eax, ebx
0x1401db659  jmp     short loc_1401DB65F
0x1401db65b  mov     eax, [rsp+78h+plLbound]
0x1401db65f  mov     rcx, [rsp+78h+var_20]
0x1401db664  xor     rcx, rsp; StackCookie
0x1401db667  call    __security_check_cookie
0x1401db66c  mov     rbx, [rsp+78h+arg_18]
0x1401db674  add     rsp, 60h
0x1401db678  pop     r14
0x1401db67a  pop     rdi
0x1401db67b  pop     rsi
0x1401db67c  retn
```
