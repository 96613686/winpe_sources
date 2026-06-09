# SavedStateRepository::SetNode(ushort const *,tagVARIANT)

- ea: `0x1401eba70`
- end: `0x1401ebc8e`
- name: `?SetNode@SavedStateRepository@@UEAAJPEBGUtagVARIANT@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(SavedStateRepository *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400a2110`

## callees

- `0x140132960`
- `0x1401eadd0`
- `0x1401eb4d4`
- `0x1401eba70`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401eba95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401eba95`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ebb86`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1401ebb86`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ebb69`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1401ebb69`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ebb4e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1401ebb4e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ebbcb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1401ebbcb`

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
0x1401eba70  mov     [rsp+arg_18], rbx
0x1401eba75  push    rsi
0x1401eba76  push    rdi
0x1401eba77  push    r14
0x1401eba79  sub     rsp, 60h
0x1401eba7d  mov     rax, cs:__security_cookie
0x1401eba84  xor     rax, rsp
0x1401eba87  mov     [rsp+78h+var_20], rax
0x1401eba8c  mov     r14, r8
0x1401eba8f  mov     rsi, rdx
0x1401eba92  mov     rdi, rcx
0x1401eba95  call    cs:__imp_GetCurrentThreadId
0x1401eba9c  nop     dword ptr [rax+rax+00h]
0x1401ebaa1  mov     r8d, [rdi+84h]
0x1401ebaa8  cmp     r8d, eax
0x1401ebaab  jz      short loc_1401EBAB7
0x1401ebaad  mov     ebx, 8000FFFFh
0x1401ebab2  jmp     loc_1401EBC67
0x1401ebab7  mov     [rsp+78h+var_48], 0
0x1401ebac0  lea     r8, [rsp+78h+var_48]; struct tagVARIANT **
0x1401ebac5  mov     rdx, rsi; unsigned __int16 *
0x1401ebac8  mov     rcx, rdi; this
0x1401ebacb  call    ?GetNodeForRollback@SavedStateRepository@@AEAAJPEBGAEAPEAUtagVARIANT@@@Z; SavedStateRepository::GetNodeForRollback(ushort const *,tagVARIANT * &)
0x1401ebad0  mov     ebx, eax
0x1401ebad2  test    eax, eax
0x1401ebad4  js      loc_1401EBC67
0x1401ebada  mov     rcx, [rdi+68h]
0x1401ebade  mov     rax, [rcx]
0x1401ebae1  mov     rdx, rsi
0x1401ebae4  mov     rax, [rax+0A8h]
0x1401ebaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebaf0  cmp     word ptr [r14], 5
0x1401ebaf5  jz      loc_1401EBC26
0x1401ebafb  cmp     word ptr [r14], 8
0x1401ebb00  jz      loc_1401EBC08
0x1401ebb06  cmp     word ptr [r14], 0Bh
0x1401ebb0b  jz      loc_1401EBBE6
0x1401ebb11  cmp     word ptr [r14], 14h
0x1401ebb16  jz      loc_1401EBBD9
0x1401ebb1c  mov     eax, 2011h
0x1401ebb21  cmp     [r14], ax
0x1401ebb25  jz      short loc_1401EBB31
0x1401ebb27  mov     ebx, 80004005h
0x1401ebb2c  jmp     loc_1401EBC67
0x1401ebb31  mov     [rsp+78h+ppvData], 0
0x1401ebb3a  mov     [rsp+78h+plLbound], 0
0x1401ebb42  mov     r14, [r14+8]
0x1401ebb46  lea     rdx, [rsp+78h+ppvData]; ppvData
0x1401ebb4b  mov     rcx, r14; psa
0x1401ebb4e  call    cs:__imp_SafeArrayAccessData
0x1401ebb55  nop     dword ptr [rax+rax+00h]
0x1401ebb5a  lea     r8, [rsp+78h+plLbound]; plLbound
0x1401ebb5f  mov     ebx, 1
0x1401ebb64  mov     edx, ebx; nDim
0x1401ebb66  mov     rcx, r14; psa
0x1401ebb69  call    cs:__imp_SafeArrayGetLBound
0x1401ebb70  nop     dword ptr [rax+rax+00h]
0x1401ebb75  cmp     [rsp+78h+plLbound], 0
0x1401ebb7a  jnz     short loc_1401EBBC3
0x1401ebb7c  lea     r8, [rsp+78h+plLbound]; plUbound
0x1401ebb81  mov     edx, ebx; nDim
0x1401ebb83  mov     rcx, r14; psa
0x1401ebb86  call    cs:__imp_SafeArrayGetUBound
0x1401ebb8d  nop     dword ptr [rax+rax+00h]
0x1401ebb92  mov     r9d, [rsp+78h+plLbound]
0x1401ebb97  add     r9d, ebx
0x1401ebb9a  mov     [rsp+78h+plLbound], r9d
0x1401ebb9f  mov     rcx, [rdi+68h]
0x1401ebba3  mov     rax, [rcx]
0x1401ebba6  mov     [rsp+78h+var_58], r9d
0x1401ebbab  mov     r8, [rsp+78h+ppvData]
0x1401ebbb0  mov     rdx, rsi
0x1401ebbb3  mov     rax, [rax+90h]
0x1401ebbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebbbf  mov     ebx, eax
0x1401ebbc1  jmp     short loc_1401EBBC8
0x1401ebbc3  mov     ebx, 80070057h
0x1401ebbc8  mov     rcx, r14; psa
0x1401ebbcb  call    cs:__imp_SafeArrayUnaccessData
0x1401ebbd2  nop     dword ptr [rax+rax+00h]
0x1401ebbd7  jmp     short loc_1401EBC41
0x1401ebbd9  mov     rcx, [rdi+68h]
0x1401ebbdd  mov     rax, [rcx]
0x1401ebbe0  mov     rax, [rax+40h]
0x1401ebbe4  jmp     short loc_1401EBC16
0x1401ebbe6  mov     rcx, [rdi+68h]
0x1401ebbea  mov     rax, [rcx]
0x1401ebbed  xor     r8d, r8d
0x1401ebbf0  cmp     word ptr [r14+8], 0FFFFh
0x1401ebbf6  setz    r8b
0x1401ebbfa  mov     rdx, rsi
0x1401ebbfd  mov     rax, [rax+60h]
0x1401ebc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebc06  jmp     short loc_1401EBC22
0x1401ebc08  mov     rcx, [rdi+68h]
0x1401ebc0c  mov     rax, [rcx]
0x1401ebc0f  mov     rax, [rax+80h]
0x1401ebc16  mov     rdx, rsi
0x1401ebc19  mov     r8, [r14+8]
0x1401ebc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebc22  mov     ebx, eax
0x1401ebc24  jmp     short loc_1401EBC41
0x1401ebc26  mov     rcx, [rdi+68h]
0x1401ebc2a  mov     rax, [rcx]
0x1401ebc2d  movsd   xmm2, qword ptr [r14+8]
0x1401ebc33  mov     rdx, rsi
0x1401ebc36  mov     rax, [rax+70h]
0x1401ebc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ebc3f  mov     ebx, eax
0x1401ebc41  test    ebx, ebx
0x1401ebc43  js      short loc_1401EBC67
0x1401ebc45  mov     [rsp+78h+ppvData], rsi
0x1401ebc4a  mov     rax, [rsp+78h+var_48]
0x1401ebc4f  mov     [rsp+78h+var_30], rax
0x1401ebc54  lea     rcx, [rdi+70h]
0x1401ebc58  lea     r8, [rsp+78h+ppvData]
0x1401ebc5d  lea     rdx, [rsp+78h+var_48]
0x1401ebc62  call    ??$insert@U?$pair@PEBGPEAUtagVARIANT@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGPEAUtagVARIANT@@@1@@Z; std::map<std::wstring,tagVARIANT *>::insert<std::pair<ushort const *,tagVARIANT *>,0>(std::pair<ushort const *,tagVARIANT *> &&)
0x1401ebc67  mov     eax, ebx
0x1401ebc69  jmp     short loc_1401EBC6F
0x1401ebc6b  mov     eax, [rsp+78h+plLbound]
0x1401ebc6f  mov     rcx, [rsp+78h+var_20]
0x1401ebc74  xor     rcx, rsp; StackCookie
0x1401ebc77  call    __security_check_cookie
0x1401ebc7c  mov     rbx, [rsp+78h+arg_18]
0x1401ebc84  add     rsp, 60h
0x1401ebc88  pop     r14
0x1401ebc8a  pop     rdi
0x1401ebc8b  pop     rsi
0x1401ebc8c  retn
```
