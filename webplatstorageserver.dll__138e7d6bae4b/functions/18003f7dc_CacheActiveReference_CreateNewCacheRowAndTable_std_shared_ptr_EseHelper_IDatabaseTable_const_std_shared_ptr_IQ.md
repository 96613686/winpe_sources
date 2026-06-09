# CacheActiveReference::CreateNewCacheRowAndTable(std::shared_ptr<EseHelper::IDatabaseTable> const &,std::shared_ptr<IQuotaSession> const &)

- ea: `0x18003f7dc`
- end: `0x18003fc12`
- name: `?CreateNewCacheRowAndTable@CacheActiveReference@@AEAA?AV?$shared_ptr@UIDatabaseTable@EseHelper@@@std@@AEBV23@AEBV?$shared_ptr@UIQuotaSession@@@3@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003cd50`

## callees

- `0x18000e1c0`
- `0x180015a40`
- `0x180017618`
- `0x180017b70`
- `0x18001ac80`
- `0x180036dc4`
- `0x18003ecc4`
- `0x18003f7dc`
- `0x18003fc20`
- `0x18003fc94`
- `0x180064ec8`
- `0x180065fb8`
- `0x180066010`
- `0x1800660c4`
- `0x180080fb0`
- `0x1800929e4`
- `0x180093f70`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003fbe0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003fbe7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003fbe0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18003fbe7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18003fb46`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18003fb46`

## string_xrefs

- `0x18003fa0c`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cacheactivereference.cxx`
- `0x18003fb57`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cacheactivereference.cxx`
- `0x18003f89b`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cachestorageactivereference.cxx`
- `0x18003f966`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\cachestorageactivereference.cxx`

## pseudocode

```c
__int64 __fastcall CacheActiveReference::CreateNewCacheRowAndTable(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  void (__fastcall ***v8)(_QWORD); // rbx
  __int64 v9; // r8
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 CacheFilesPath; // rax
  const WCHAR *v14; // r14
  __int64 v15; // rax
  __int64 v16; // r15
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  const WCHAR *v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 TableName; // rax
  _QWORD *v24; // rdi
  unsigned int v25; // eax
  __int64 v26; // rcx
  unsigned int v28; // [rsp+20h] [rbp-79h]
  __int64 v29; // [rsp+30h] [rbp-69h] BYREF
  int v30; // [rsp+38h] [rbp-61h]
  std::_Ref_count_base *v31[2]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v33; // [rsp+60h] [rbp-39h] BYREF
  __int64 v34; // [rsp+70h] [rbp-29h]
  _QWORD Src[3]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v36; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v34 = a2;
  v30 = 0;
  (*(void (__fastcall **)(_QWORD, std::_Ref_count_base **))(*(_QWORD *)*a3 + 280LL))(*a3, v31);
  v33 = 0;
  LODWORD(v8) = HrJetBeginTransaction(*((_QWORD *)v31[0] + 3));
  if ( (_DWORD)v8 )
  {
LABEL_47:
    EseHelper::HandleUnexpectedEseError((unsigned int)v8, v31);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\inetcore\\lib\\esehelper\\lib\\databasetransaction.cxx",
      (const char *)(unsigned int)v8,
      v28);
  }
  if ( v31[1] )
    _InterlockedIncrement((volatile signed __int32 *)v31[1] + 2);
  v33 = *(_OWORD *)v31;
  LOBYTE(v9) = 1;
  (*(void (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*a3 + 208LL))(*a3, &v29, v9);
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 72) + 136LL) == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cachestorageactivereference.cxx",
      (const char *)0x8000FFFFLL,
      v28);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 56LL))(v29, 1);
  v11 = (_QWORD *)(a1 + 40);
  v12 = *(_QWORD *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 64) > 7u )
    v11 = (_QWORD *)*v11;
  if ( v12 == -1 || !v11 && v12 )
  {
LABEL_46:
    _o_terminate(v10);
    goto LABEL_47;
  }
  v32[0] = *(_QWORD *)(a1 + 56);
  v32[1] = v11;
  (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v29 + 80LL))(v29, 4, v32);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 136LL))(v29);
  if ( v29 )
    std::default_delete<EseHelper::IDatabaseTableUpdate>::operator()();
  *(_QWORD *)(a1 + 104) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a3 + 168LL))(*a3, 0);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 72) + 160LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cachestorageactivereference.cxx",
      (const char *)0x8000FFFFLL,
      v28);
  CacheFilesPath = CacheStoragePath::GetCacheFilesPath(Src);
  v14 = (const WCHAR *)(a1 + 112);
  std::wstring::operator=(a1 + 112, CacheFilesPath);
  if ( v36 > 7 )
    std::_Deallocate<16>(Src[0], 2 * v36 + 2);
  v15 = *(_QWORD *)(a1 + 56) + *(_QWORD *)(a1 + 128);
  v16 = 2 * v15 + 24;
  v8 = 0;
  v32[0] = 0;
  if ( *a4 )
  {
    v17 = (**(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64))*a4)(*a4, &v29, 2 * v15 + 24);
    std::unique_ptr<IQuotaReservation>::operator=<std::default_delete<IQuotaReservation>,0>(v32, v17);
    if ( v29 )
      ((void (*)(void))std::default_delete<IQuotaReservation>::operator())();
    v8 = (void (__fastcall ***)(_QWORD))v32[0];
    if ( !v32[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cacheactivereference.cxx",
        (const char *)0x8070F007LL,
        v28);
  }
  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(*(_QWORD *)*a3 + 208LL))(*a3, &v29, 0);
  v19 = *(_QWORD *)(a1 + 128);
  if ( *(_QWORD *)(a1 + 136) <= 7u )
    v20 = (const WCHAR *)(a1 + 112);
  else
    v20 = *(const WCHAR **)v14;
  if ( v19 == -1 || !v20 && v19 )
  {
    _o_terminate(v18);
    goto LABEL_46;
  }
  Src[0] = *(_QWORD *)(a1 + 128);
  Src[1] = v20;
  (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v29 + 80LL))(v29, 5, Src);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v29 + 56LL))(v29, 7, v16);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 136LL))(v29);
  if ( v29 )
    std::default_delete<EseHelper::IDatabaseTableUpdate>::operator()();
  v21 = *(_QWORD *)(a1 + 104);
  v22 = CacheStorageActiveReference::CacheStorageId(*(CacheStorageActiveReference **)(a1 + 72));
  TableName = CacheTable::GenerateTableName(Src, v22, v21);
  v24 = (_QWORD *)(a1 + 144);
  std::wstring::operator=(a1 + 144, TableName);
  if ( v36 > 7 )
    std::_Deallocate<16>(Src[0], 2 * v36 + 2);
  if ( *(_QWORD *)(a1 + 168) > 7u )
    v24 = (_QWORD *)*v24;
  (**(void (__fastcall ***)(std::_Ref_count_base *, __int64, _QWORD *, void *))v31[0])(
    v31[0],
    a2,
    v24,
    &CacheTable::Schema);
  v30 = 1;
  if ( *(_QWORD *)(a1 + 136) > 7u )
    v14 = *(const WCHAR **)v14;
  v25 = SHCreateDirectoryExW(0, v14, 0);
  if ( v25 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\cacheactivereference.cxx",
      (const char *)v25,
      v28);
  EseHelper::DatabaseTransaction::Commit((EseHelper::DatabaseTransaction *)&v33);
  if ( v8 )
    (**v8)(v8);
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 192) = v16;
  if ( v8 )
    std::default_delete<IQuotaReservation>::operator()(v26, v8);
  EseHelper::DatabaseTransaction::~DatabaseTransaction((EseHelper::DatabaseTransaction *)&v33);
  if ( v31[1] )
    std::_Ref_count_base::_Decref(v31[1]);
  return a2;
}

```

## disassembly

```asm
0x18003f7dc  push    rbp
0x18003f7de  push    rbx
0x18003f7df  push    rsi
0x18003f7e0  push    rdi
0x18003f7e1  push    r12
0x18003f7e3  push    r13
0x18003f7e5  push    r14
0x18003f7e7  push    r15
0x18003f7e9  lea     rbp, [rsp-1Fh]
0x18003f7ee  sub     rsp, 0B8h
0x18003f7f5  mov     rax, cs:__security_cookie
0x18003f7fc  xor     rax, rsp
0x18003f7ff  mov     [rbp+57h+var_50], rax
0x18003f803  mov     r13, r9
0x18003f806  mov     rdi, r8
0x18003f809  mov     r12, rdx
0x18003f80c  mov     rsi, rcx
0x18003f80f  mov     [rbp+57h+var_80], rdx
0x18003f813  mov     [rbp+57h+var_B8], 0
0x18003f81a  mov     rcx, [r8]
0x18003f81d  mov     rax, [rcx]
0x18003f820  lea     rdx, [rbp+57h+var_B0]
0x18003f824  mov     rax, [rax+118h]
0x18003f82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f830  nop
0x18003f831  xorps   xmm0, xmm0
0x18003f834  movdqa  [rbp+57h+var_90], xmm0
0x18003f839  mov     rcx, [rbp+57h+var_B0]
0x18003f83d  mov     rcx, [rcx+18h]; unsigned __int64
0x18003f841  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x18003f846  mov     ebx, eax
0x18003f848  test    eax, eax
0x18003f84a  jnz     loc_18003FBEE
0x18003f850  mov     rax, [rbp+57h+var_B0+8]
0x18003f854  test    rax, rax
0x18003f857  jz      short loc_18003F85D
0x18003f859  lock inc dword ptr [rax+8]
0x18003f85d  movaps  xmm0, xmmword ptr [rbp+57h+var_B0]
0x18003f861  movdqa  [rbp+57h+var_90], xmm0
0x18003f866  mov     rcx, [rdi]
0x18003f869  mov     rax, [rcx]
0x18003f86c  mov     r8b, 1
0x18003f86f  lea     rdx, [rbp+57h+var_C0]
0x18003f873  mov     rax, [rax+0D0h]
0x18003f87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f87f  nop
0x18003f880  mov     rax, [rsi+48h]
0x18003f884  mov     r8, [rax+88h]
0x18003f88b  mov     rcx, [rbp+5Fh]; this
0x18003f88f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003f893  jnz     short loc_18003F8AD
0x18003f895  mov     r9d, 8000FFFFh; char *
0x18003f89b  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003f8a2  mov     edx, 0A8h; void *
0x18003f8a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f8ad  mov     rcx, [rbp+57h+var_C0]
0x18003f8b1  mov     rax, [rcx]
0x18003f8b4  mov     edx, 1
0x18003f8b9  mov     rax, [rax+38h]
0x18003f8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8c2  lea     rax, [rsi+28h]
0x18003f8c6  mov     rdx, [rax+10h]
0x18003f8ca  cmp     qword ptr [rax+18h], 7
0x18003f8cf  jbe     short loc_18003F8D4
0x18003f8d1  mov     rax, [rax]
0x18003f8d4  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18003f8d8  jz      loc_18003FBE7
0x18003f8de  test    rax, rax
0x18003f8e1  jnz     short loc_18003F8EC
0x18003f8e3  test    rdx, rdx
0x18003f8e6  jnz     loc_18003FBE7
0x18003f8ec  mov     rcx, [rbp+57h+var_C0]
0x18003f8f0  mov     [rbp+57h+var_A0], rdx
0x18003f8f4  mov     [rbp+57h+var_98], rax
0x18003f8f8  mov     rax, [rcx]
0x18003f8fb  lea     r8, [rbp+57h+var_A0]
0x18003f8ff  mov     edx, 4
0x18003f904  mov     rax, [rax+50h]
0x18003f908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f90d  mov     rcx, [rbp+57h+var_C0]
0x18003f911  mov     rax, [rcx]
0x18003f914  mov     rax, [rax+88h]
0x18003f91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f920  nop
0x18003f921  mov     rdx, [rbp+57h+var_C0]
0x18003f925  test    rdx, rdx
0x18003f928  jz      short loc_18003F92F
0x18003f92a  call    ??R?$default_delete@UIDatabaseTableUpdate@EseHelper@@@std@@QEBAXPEAUIDatabaseTableUpdate@EseHelper@@@Z; std::default_delete<EseHelper::IDatabaseTableUpdate>::operator()(EseHelper::IDatabaseTableUpdate *)
0x18003f92f  mov     rcx, [rdi]
0x18003f932  mov     rax, [rcx]
0x18003f935  xor     edx, edx
0x18003f937  mov     rax, [rax+0A8h]
0x18003f93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f943  mov     r8, rax
0x18003f946  mov     [rsi+68h], rax
0x18003f94a  mov     rdx, [rsi+48h]
0x18003f94e  add     rdx, 90h
0x18003f955  mov     rcx, [rbp+5Fh]; this
0x18003f959  cmp     qword ptr [rdx+10h], 0
0x18003f95e  jnz     short loc_18003F978
0x18003f960  mov     r9d, 8000FFFFh; char *
0x18003f966  lea     r8, aOnecoreuapInet_25; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003f96d  mov     edx, 0AEh; void *
0x18003f972  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f978  lea     rcx, [rbp+57h+Src]; Src
0x18003f97c  call    ?GetCacheFilesPath@CacheStoragePath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_J@Z; CacheStoragePath::GetCacheFilesPath(std::wstring const &,__int64)
0x18003f981  lea     r14, [rsi+70h]
0x18003f985  mov     rdx, rax
0x18003f988  mov     rcx, r14
0x18003f98b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003f990  mov     rdx, [rbp+57h+var_58]
0x18003f994  cmp     rdx, 7
0x18003f998  jbe     short loc_18003F9AB
0x18003f99a  lea     rdx, ds:2[rdx*2]
0x18003f9a2  mov     rcx, [rbp+57h+Src]
0x18003f9a6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003f9ab  mov     rax, [rsi+80h]
0x18003f9b2  add     rax, [rsi+38h]
0x18003f9b6  lea     r15, ds:18h[rax*2]
0x18003f9be  xor     ebx, ebx
0x18003f9c0  mov     [rbp+57h+var_A0], rbx
0x18003f9c4  mov     rcx, [r13+0]
0x18003f9c8  test    rcx, rcx
0x18003f9cb  jz      short loc_18003FA1E
0x18003f9cd  mov     rax, [rcx]
0x18003f9d0  mov     r8, r15
0x18003f9d3  lea     rdx, [rbp+57h+var_C0]
0x18003f9d7  mov     rax, [rax]
0x18003f9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9df  mov     rdx, rax
0x18003f9e2  lea     rcx, [rbp+57h+var_A0]
0x18003f9e6  call    ??$?4U?$default_delete@UIQuotaReservation@@@std@@$0A@@?$unique_ptr@UIQuotaReservation@@U?$default_delete@UIQuotaReservation@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<IQuotaReservation>::operator=<std::default_delete<IQuotaReservation>,0>(std::unique_ptr<IQuotaReservation> &&)
0x18003f9eb  mov     rdx, [rbp+57h+var_C0]
0x18003f9ef  test    rdx, rdx
0x18003f9f2  jz      short loc_18003F9F9
0x18003f9f4  call    ??R?$default_delete@UIQuotaReservation@@@std@@QEBAXPEAUIQuotaReservation@@@Z; std::default_delete<IQuotaReservation>::operator()(IQuotaReservation *)
0x18003f9f9  mov     rcx, [rbp+5Fh]; this
0x18003f9fd  mov     rbx, [rbp+57h+var_A0]
0x18003fa01  test    rbx, rbx
0x18003fa04  jnz     short loc_18003FA1E
0x18003fa06  mov     r9d, 8070F007h; char *
0x18003fa0c  lea     r8, aOnecoreuapInet_24; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003fa13  mov     edx, 0C5h; void *
0x18003fa18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fa1e  mov     rcx, [rdi]
0x18003fa21  mov     rax, [rcx]
0x18003fa24  xor     r8d, r8d
0x18003fa27  lea     rdx, [rbp+57h+var_C0]
0x18003fa2b  mov     rax, [rax+0D0h]
0x18003fa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa37  nop
0x18003fa38  mov     rdx, [r14+10h]
0x18003fa3c  mov     r13d, 7
0x18003fa42  cmp     [r14+18h], r13
0x18003fa46  jbe     short loc_18003FA4D
0x18003fa48  mov     rax, [r14]
0x18003fa4b  jmp     short loc_18003FA50
0x18003fa4d  mov     rax, r14
0x18003fa50  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18003fa54  jz      loc_18003FBE0
0x18003fa5a  test    rax, rax
0x18003fa5d  jnz     short loc_18003FA68
0x18003fa5f  test    rdx, rdx
0x18003fa62  jnz     loc_18003FBE0
0x18003fa68  mov     rcx, [rbp+57h+var_C0]
0x18003fa6c  mov     [rbp+57h+Src], rdx
0x18003fa70  mov     [rbp+57h+var_68], rax
0x18003fa74  mov     rax, [rcx]
0x18003fa77  lea     r8, [rbp+57h+Src]
0x18003fa7b  mov     edx, 5
0x18003fa80  mov     rax, [rax+50h]
0x18003fa84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa89  mov     rcx, [rbp+57h+var_C0]
0x18003fa8d  mov     rax, [rcx]
0x18003fa90  mov     r8, r15
0x18003fa93  mov     rdx, r13
0x18003fa96  mov     rax, [rax+38h]
0x18003fa9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa9f  mov     rcx, [rbp+57h+var_C0]
0x18003faa3  mov     rax, [rcx]
0x18003faa6  mov     rax, [rax+88h]
0x18003faad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fab2  nop
0x18003fab3  mov     rdx, [rbp+57h+var_C0]
0x18003fab7  test    rdx, rdx
0x18003faba  jz      short loc_18003FAC1
0x18003fabc  call    ??R?$default_delete@UIDatabaseTableUpdate@EseHelper@@@std@@QEBAXPEAUIDatabaseTableUpdate@EseHelper@@@Z; std::default_delete<EseHelper::IDatabaseTableUpdate>::operator()(EseHelper::IDatabaseTableUpdate *)
0x18003fac1  mov     rdi, [rsi+68h]
0x18003fac5  mov     rcx, [rsi+48h]; this
0x18003fac9  call    ?CacheStorageId@CacheStorageActiveReference@@QEBA_JXZ; CacheStorageActiveReference::CacheStorageId(void)
0x18003face  mov     r8, rdi
0x18003fad1  mov     rdx, rax
0x18003fad4  lea     rcx, [rbp+57h+Src]
0x18003fad8  call    ?GenerateTableName@CacheTable@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J0@Z; CacheTable::GenerateTableName(__int64,__int64)
0x18003fadd  lea     rdi, [rsi+90h]
0x18003fae4  mov     rdx, rax
0x18003fae7  mov     rcx, rdi
0x18003faea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003faef  mov     rdx, [rbp+57h+var_58]
0x18003faf3  cmp     rdx, r13
0x18003faf6  jbe     short loc_18003FB09
0x18003faf8  lea     rdx, ds:2[rdx*2]
0x18003fb00  mov     rcx, [rbp+57h+Src]
0x18003fb04  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003fb09  mov     rcx, [rbp+57h+var_B0]
0x18003fb0d  mov     rax, [rcx]
0x18003fb10  cmp     [rdi+18h], r13
0x18003fb14  jbe     short loc_18003FB19
0x18003fb16  mov     rdi, [rdi]
0x18003fb19  lea     r9, ?Schema@CacheTable@@3UTableDefinition@DatabaseSchema@EseHelper@@B; EseHelper::DatabaseSchema::TableDefinition const CacheTable::Schema
0x18003fb20  mov     r8, rdi
0x18003fb23  mov     rdx, r12
0x18003fb26  mov     rax, [rax]
0x18003fb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb2e  mov     [rbp+57h+var_B8], 1
0x18003fb35  cmp     [r14+18h], r13
0x18003fb39  jbe     short loc_18003FB3E
0x18003fb3b  mov     r14, [r14]
0x18003fb3e  xor     r8d, r8d; psa
0x18003fb41  mov     rdx, r14; pszPath
0x18003fb44  xor     ecx, ecx; hwnd
0x18003fb46  call    cs:__imp_SHCreateDirectoryExW
0x18003fb4c  mov     rcx, [rbp+5Fh]; this
0x18003fb50  test    eax, eax
0x18003fb52  jz      short loc_18003FB69
0x18003fb54  mov     r9d, eax; char *
0x18003fb57  lea     r8, aOnecoreuapInet_24; "onecoreuap\\inetcore\\webplatstorageser"...
0x18003fb5e  mov     edx, 0D7h; void *
0x18003fb63  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003fb69  lea     rcx, [rbp+57h+var_90]; this
0x18003fb6d  call    ?Commit@DatabaseTransaction@EseHelper@@QEAAXXZ; EseHelper::DatabaseTransaction::Commit(void)
0x18003fb72  test    rbx, rbx
0x18003fb75  jz      short loc_18003FB85
0x18003fb77  mov     rax, [rbx]
0x18003fb7a  mov     rcx, rbx
0x18003fb7d  mov     rax, [rax]
0x18003fb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb85  mov     qword ptr [rsi+0B0h], 0
0x18003fb90  mov     [rsi+0C0h], r15
0x18003fb97  test    rbx, rbx
0x18003fb9a  jz      short loc_18003FBA5
0x18003fb9c  mov     rdx, rbx
0x18003fb9f  call    ??R?$default_delete@UIQuotaReservation@@@std@@QEBAXPEAUIQuotaReservation@@@Z; std::default_delete<IQuotaReservation>::operator()(IQuotaReservation *)
0x18003fba4  nop
0x18003fba5  lea     rcx, [rbp+57h+var_90]; this
0x18003fba9  call    ??1DatabaseTransaction@EseHelper@@QEAA@XZ; EseHelper::DatabaseTransaction::~DatabaseTransaction(void)
0x18003fbae  nop
0x18003fbaf  mov     rcx, [rbp+57h+var_B0+8]; this
0x18003fbb3  test    rcx, rcx
0x18003fbb6  jz      short loc_18003FBBD
0x18003fbb8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003fbbd  mov     rax, r12
0x18003fbc0  mov     rcx, [rbp+57h+var_50]
0x18003fbc4  xor     rcx, rsp; StackCookie
0x18003fbc7  call    __security_check_cookie
0x18003fbcc  add     rsp, 0B8h
0x18003fbd3  pop     r15
0x18003fbd5  pop     r14
0x18003fbd7  pop     r13
0x18003fbd9  pop     r12
0x18003fbdb  pop     rdi
0x18003fbdc  pop     rsi
0x18003fbdd  pop     rbx
0x18003fbde  pop     rbp
0x18003fbdf  retn
0x18003fbe0  call    cs:__imp__o_terminate
0x18003fbe6  nop
0x18003fbe7  call    cs:__imp__o_terminate
0x18003fbed  nop
0x18003fbee  lea     rdx, [rbp+57h+var_B0]
0x18003fbf2  mov     ecx, ebx
0x18003fbf4  call    ?HandleUnexpectedEseError@EseHelper@@YAXJAEBV?$shared_ptr@UIDatabaseSession@EseHelper@@@std@@@Z; EseHelper::HandleUnexpectedEseError(long,std::shared_ptr<EseHelper::IDatabaseSession> const &)
0x18003fbf9  mov     rcx, [rbp+5Fh]; this
0x18003fbfd  mov     r9d, ebx; char *
0x18003fc00  lea     r8, aOnecoreuapInet_49; "onecoreuap\\inetcore\\lib\\esehelper\\l"...
0x18003fc07  mov     edx, 15h; void *
0x18003fc0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
