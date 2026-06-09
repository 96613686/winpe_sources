# ArchiveFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18004a280`
- end: `0x18004a501`
- name: `?CreateViewObject@ArchiveFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `641`
- prototype: `int(ArchiveFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180020f08`
- `0x180030a3c`
- `0x180031e94`
- `0x180036f50`
- `0x18004949c`
- `0x1800495d0`
- `0x1800496e8`
- `0x18004a280`
- `0x18004d03c`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18004a3ce`
- `SHELL32!SHCreateItemFromIDList` at `0x18004a3ce`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18004a31c`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18004a31c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ArchiveFolder::CreateViewObject(
        ArchiveFolder *this,
        HWND a2,
        const struct _GUID *a3,
        IShellView **a4)
{
  void *v8; // rax
  IShellFolderViewCB *v9; // rbx
  HRESULT v10; // eax
  const char *v11; // r9
  unsigned int v12; // esi
  __int64 result; // rax
  HRESULT v14; // eax
  unsigned int v15; // esi
  __int64 (__fastcall ***v16)(_QWORD, const struct _GUID *, IShellView **); // rdi
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  __int64 (__fastcall ***v19)(_QWORD, const struct _GUID *, IShellView **); // [rsp+20h] [rbp-78h] BYREF
  ArchiveFolder *v20; // [rsp+28h] [rbp-70h] BYREF
  void *v21; // [rsp+30h] [rbp-68h] BYREF
  SFV_CREATE pcsfv; // [rsp+38h] [rbp-60h] BYREF
  void *ppv; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HWND v25; // [rsp+A8h] [rbp+10h] BYREF

  v25 = a2;
  try
  {
    *a4 = 0;
    if ( *(_OWORD *)a3 == *(_OWORD *)&IID_IShellView )
    {
      v8 = wil::details::heap_allocator::allocate(0x30u);
      if ( v8 )
        v9 = (IShellFolderViewCB *)winrt::impl::heap_implements<ArchiveFolderViewCallback>::heap_implements<ArchiveFolderViewCallback>(
                                     v8,
                                     this);
      else
        v9 = 0;
      ppv = v9;
      *(_QWORD *)&pcsfv.cbSize = 32;
      pcsfv.psvOuter = 0;
      pcsfv.pshf = (IShellFolder *)this;
      pcsfv.psfvcb = v9;
      v10 = SHCreateShellFolderView(&pcsfv, a4);
      v12 = v10;
      if ( v10 >= 0 )
      {
        *((_QWORD *)this + 17) = a2;
        if ( v9 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
          (const char *)(unsigned int)v10,
          (int)v19);
        if ( v9 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        result = v12;
      }
    }
    else if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource.Data1
           && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_ITransferSource.Data4
           || *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferHelper.Data1
           && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_ITransferHelper.Data4 )
    {
      ppv = 0;
      v14 = SHCreateItemFromIDList(*((LPCITEMIDLIST *)this + 16), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v15 = v14;
      if ( v14 >= 0 )
      {
        v20 = this;
        v21 = ppv;
        winrt::make<ArchiveTransferSource,HWND__ * &,IShellItem *,ArchiveFolder *>(&v19, &v25, &v21, &v20);
        v16 = v19;
        v17 = (**v19)(v19, a3, a4);
        if ( v16 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v19);
        if ( ppv )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        result = v17;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x130,
          (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
          (const char *)(unsigned int)v14,
          (int)v19);
        if ( ppv )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        result = v15;
      }
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SHINE_2602_Bugs>::__private_IsEnabled()
           && *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1
           && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IContextMenu.Data4 )
    {
      winrt::make<ArchiveContextMenu,std::wstring &>(&ppv, (char *)this + 64);
      v18 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, IShellView **))ppv)(ppv, a3, a4);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      result = v18;
    }
    else
    {
      result = 2147500034LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x143,
                           (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18004a280  mov     [rsp+arg_8], rdx
0x18004a285  push    rbx
0x18004a286  push    rsi
0x18004a287  push    rdi
0x18004a288  push    r14
0x18004a28a  push    r15
0x18004a28c  sub     rsp, 70h
0x18004a290  mov     rax, cs:__security_cookie
0x18004a297  xor     rax, rsp
0x18004a29a  mov     [rsp+98h+var_38], rax
0x18004a29f  mov     r14, r9
0x18004a2a2  mov     rbx, r8
0x18004a2a5  mov     r15, rdx
0x18004a2a8  mov     rdi, rcx
0x18004a2ab  mov     qword ptr [r9], 0
0x18004a2b2  mov     rax, [r8]
0x18004a2b5  cmp     rax, qword ptr cs:IID_IShellView.Data1
0x18004a2bc  jnz     loc_18004A378
0x18004a2c2  mov     rax, [r8+8]
0x18004a2c6  cmp     rax, qword ptr cs:IID_IShellView.Data4
0x18004a2cd  jnz     loc_18004A378
0x18004a2d3  mov     ecx, 30h ; '0'; unsigned __int64
0x18004a2d8  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18004a2dd  test    rax, rax
0x18004a2e0  jz      short loc_18004A2F2
0x18004a2e2  mov     rdx, rdi
0x18004a2e5  mov     rcx, rax
0x18004a2e8  call    ??0?$heap_implements@UArchiveFolderViewCallback@@@impl@winrt@@QEAA@PEAVArchiveFolder@@@Z; winrt::impl::heap_implements<ArchiveFolderViewCallback>::heap_implements<ArchiveFolderViewCallback>(ArchiveFolder *)
0x18004a2ed  mov     rbx, rax
0x18004a2f0  jmp     short loc_18004A2F4
0x18004a2f2  xor     ebx, ebx
0x18004a2f4  mov     [rsp+98h+ppv], rbx
0x18004a2f9  mov     qword ptr [rsp+98h+pcsfv.cbSize], 20h ; ' '
0x18004a302  xorps   xmm0, xmm0
0x18004a305  movups  xmmword ptr [rsp+98h+pcsfv.pshf], xmm0
0x18004a30a  mov     [rsp+98h+pcsfv.pshf], rdi
0x18004a30f  mov     [rsp+98h+pcsfv.psfvcb], rbx
0x18004a314  mov     rdx, r14; ppsv
0x18004a317  lea     rcx, [rsp+98h+pcsfv]; pcsfv
0x18004a31c  call    cs:__imp_SHCreateShellFolderView
0x18004a322  mov     esi, eax
0x18004a324  test    eax, eax
0x18004a326  jns     short loc_18004A35B
0x18004a328  mov     rcx, [rsp+98h]; this
0x18004a330  mov     r9d, eax; char *
0x18004a333  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18004a33a  mov     edx, 128h; void *
0x18004a33f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a344  nop
0x18004a345  test    rbx, rbx
0x18004a348  jz      short loc_18004A354
0x18004a34a  lea     rcx, [rsp+98h+ppv]
0x18004a34f  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a354  mov     eax, esi
0x18004a356  jmp     loc_18004A4E7
0x18004a35b  mov     [rdi+88h], r15
0x18004a362  test    rbx, rbx
0x18004a365  jz      short loc_18004A371
0x18004a367  lea     rcx, [rsp+98h+ppv]
0x18004a36c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a371  xor     eax, eax
0x18004a373  jmp     loc_18004A4E7
0x18004a378  mov     rax, [r8]
0x18004a37b  cmp     rax, qword ptr cs:IID_ITransferSource.Data1
0x18004a382  jnz     short loc_18004A391
0x18004a384  mov     rax, [r8+8]
0x18004a388  cmp     rax, qword ptr cs:IID_ITransferSource.Data4
0x18004a38f  jz      short loc_18004A3B2
0x18004a391  mov     rax, [r8]
0x18004a394  cmp     rax, qword ptr cs:IID_ITransferHelper.Data1
0x18004a39b  jnz     loc_18004A47D
0x18004a3a1  mov     rax, [r8+8]
0x18004a3a5  cmp     rax, qword ptr cs:IID_ITransferHelper.Data4
0x18004a3ac  jnz     loc_18004A47D
0x18004a3b2  mov     [rsp+98h+ppv], 0
0x18004a3bb  lea     r8, [rsp+98h+ppv]; ppv
0x18004a3c0  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004a3c7  mov     rcx, [rcx+80h]; pidl
0x18004a3ce  call    cs:__imp_SHCreateItemFromIDList
0x18004a3d4  mov     esi, eax
0x18004a3d6  test    eax, eax
0x18004a3d8  jns     short loc_18004A410
0x18004a3da  mov     rcx, [rsp+98h]; this
0x18004a3e2  mov     r9d, eax; char *
0x18004a3e5  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18004a3ec  mov     edx, 130h; void *
0x18004a3f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a3f6  nop
0x18004a3f7  cmp     [rsp+98h+ppv], 0
0x18004a3fd  jz      short loc_18004A409
0x18004a3ff  lea     rcx, [rsp+98h+ppv]
0x18004a404  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a409  mov     eax, esi
0x18004a40b  jmp     loc_18004A4E7
0x18004a410  mov     [rsp+98h+var_70], rdi
0x18004a415  mov     rax, [rsp+98h+ppv]
0x18004a41a  mov     [rsp+98h+var_68], rax
0x18004a41f  lea     r9, [rsp+98h+var_70]
0x18004a424  lea     r8, [rsp+98h+var_68]
0x18004a429  lea     rdx, [rsp+98h+arg_8]
0x18004a431  lea     rcx, [rsp+98h+var_78]
0x18004a436  call    ??$make@UArchiveTransferSource@@AEAPEAUHWND__@@PEAUIShellItem@@PEAVArchiveFolder@@@winrt@@YA?A_PAEAPEAUHWND__@@$$QEAPEAUIShellItem@@$$QEAPEAVArchiveFolder@@@Z
0x18004a43b  nop
0x18004a43c  mov     rdi, [rsp+98h+var_78]
0x18004a441  mov     rax, [rdi]
0x18004a444  mov     r8, r14
0x18004a447  mov     rdx, rbx
0x18004a44a  mov     rcx, rdi
0x18004a44d  mov     rax, [rax]
0x18004a450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a455  mov     ebx, eax
0x18004a457  test    rdi, rdi
0x18004a45a  jz      short loc_18004A467
0x18004a45c  lea     rcx, [rsp+98h+var_78]
0x18004a461  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a466  nop
0x18004a467  cmp     [rsp+98h+ppv], 0
0x18004a46d  jz      short loc_18004A479
0x18004a46f  lea     rcx, [rsp+98h+ppv]
0x18004a474  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a479  mov     eax, ebx
0x18004a47b  jmp     short loc_18004A4E7
0x18004a47d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SHINE_2602_Bugs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SHINE_2602_Bugs>::__private_IsEnabled(void)
0x18004a482  test    al, al
0x18004a484  jz      short loc_18004A4DC
0x18004a486  mov     rax, [rbx]
0x18004a489  cmp     rax, qword ptr cs:IID_IContextMenu.Data1
0x18004a490  jnz     short loc_18004A4DC
0x18004a492  mov     rax, [rbx+8]
0x18004a496  cmp     rax, qword ptr cs:IID_IContextMenu.Data4
0x18004a49d  jnz     short loc_18004A4DC
0x18004a49f  lea     rdx, [rdi+40h]
0x18004a4a3  lea     rcx, [rsp+98h+ppv]
0x18004a4a8  call    ??$make@UArchiveContextMenu@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@winrt@@YA?A_PAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z
0x18004a4ad  nop
0x18004a4ae  mov     rcx, [rsp+98h+ppv]
0x18004a4b3  mov     rax, [rcx]
0x18004a4b6  mov     r8, r14
0x18004a4b9  mov     rdx, rbx
0x18004a4bc  mov     rax, [rax]
0x18004a4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4c4  mov     ebx, eax
0x18004a4c6  cmp     [rsp+98h+ppv], 0
0x18004a4cc  jz      short loc_18004A4D8
0x18004a4ce  lea     rcx, [rsp+98h+ppv]
0x18004a4d3  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18004a4d8  mov     eax, ebx
0x18004a4da  jmp     short loc_18004A4E7
0x18004a4dc  mov     eax, 80004002h
0x18004a4e1  jmp     short loc_18004A4E7
0x18004a4e3  mov     eax, dword ptr [rsp+98h+ppv]
0x18004a4e7  mov     rcx, [rsp+98h+var_38]
0x18004a4ec  xor     rcx, rsp; StackCookie
0x18004a4ef  call    __security_check_cookie
0x18004a4f4  add     rsp, 70h
0x18004a4f8  pop     r15
0x18004a4fa  pop     r14
0x18004a4fc  pop     rdi
0x18004a4fd  pop     rsi
0x18004a4fe  pop     rbx
0x18004a4ff  retn
```
