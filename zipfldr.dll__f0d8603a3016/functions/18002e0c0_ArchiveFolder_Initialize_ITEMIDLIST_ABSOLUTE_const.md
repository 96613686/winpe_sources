# ArchiveFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18002e0c0`
- end: `0x18002e1ff`
- name: `?Initialize@ArchiveFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `319`
- prototype: `int(ArchiveFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180024a24`
- `0x1800280a4`
- `0x18002e0c0`
- `0x180031e94`
- `0x180036f50`
- `0x1800398bc`
- `0x180039a18`
- `0x180048dac`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18002e10d`
- `SHELL32!__imp_ILFree` at `0x18002e10d`
- `SHELL32!__imp_SHGetPathFromIDListAlloc` at `0x18002e16e`
- `SHELL32!__imp_SHGetPathFromIDListAlloc` at `0x18002e16e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ArchiveFolder::Initialize(ArchiveFolder *this, const struct _ITEMIDLIST_ABSOLUTE *a2)
{
  struct _ITEMIDLIST_RELATIVE **v4; // rdi
  const struct _ITEMIDLIST_ABSOLUTE *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  int v12; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (struct _ITEMIDLIST_RELATIVE **)((char *)this + 120);
  v5 = (const struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)this + 15);
  if ( a2 == v5 )
    return 0;
  if ( v5 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
    ILFree((LPITEMIDLIST)v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
  }
  *v4 = 0;
  v6 = SHILClone(a2, v4);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
      (const char *)(unsigned int)v6,
      v12);
    return v7;
  }
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v9 = SHGetPathFromIDListAlloc(a2, &pv, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)pv + v11) );
    std::wstring::_Assign<unsigned short>((char *)this + 56, pv);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28C,
    (unsigned int)"shell\\ext\\zip\\archive\\archivefolder.cpp",
    (const char *)(unsigned int)v9,
    v12);
  if ( pv )
    CoTaskMemFree(pv);
  return v10;
}

```

## disassembly

```asm
0x18002e0c0  mov     [rsp+arg_10], rbx
0x18002e0c5  mov     [rsp+arg_18], rsi
0x18002e0ca  push    rdi
0x18002e0cb  push    r14
0x18002e0cd  push    r15
0x18002e0cf  sub     rsp, 40h
0x18002e0d3  mov     rax, cs:__security_cookie
0x18002e0da  xor     rax, rsp
0x18002e0dd  mov     [rsp+58h+var_28], rax
0x18002e0e2  mov     rsi, rdx
0x18002e0e5  mov     r14, rcx
0x18002e0e8  lea     rdi, [rcx+78h]
0x18002e0ec  mov     rbx, [rdi]
0x18002e0ef  cmp     rdx, rbx
0x18002e0f2  jz      loc_18002E1D5
0x18002e0f8  xor     r15d, r15d
0x18002e0fb  test    rbx, rbx
0x18002e0fe  jz      short loc_18002E11E
0x18002e100  lea     rcx, [rsp+58h+var_38]; this
0x18002e105  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e10a  mov     rcx, rbx; pidl
0x18002e10d  call    cs:__imp_ILFree
0x18002e113  lea     rcx, [rsp+58h+var_38]; this
0x18002e118  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e11d  nop
0x18002e11e  mov     [rdi], r15
0x18002e121  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE **
0x18002e124  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x18002e127  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18002e12c  mov     ebx, eax
0x18002e12e  test    eax, eax
0x18002e130  jns     short loc_18002E152
0x18002e132  mov     rcx, [rsp+58h]; this
0x18002e137  mov     r9d, eax; char *
0x18002e13a  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18002e141  mov     edx, 289h; void *
0x18002e146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e14b  mov     eax, ebx
0x18002e14d  jmp     loc_18002E1DD
0x18002e152  mov     [rsp+58h+pv], r15
0x18002e157  xor     edx, edx
0x18002e159  lea     rcx, [rsp+58h+pv]
0x18002e15e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002e163  xor     r8d, r8d
0x18002e166  lea     rdx, [rsp+58h+pv]
0x18002e16b  mov     rcx, rsi
0x18002e16e  call    cs:__imp_SHGetPathFromIDListAlloc
0x18002e174  mov     ebx, eax
0x18002e176  test    eax, eax
0x18002e178  jns     short loc_18002E1A8
0x18002e17a  mov     rcx, [rsp+58h]; this
0x18002e17f  mov     r9d, eax; char *
0x18002e182  lea     r8, aShellExtZipArc_9; "shell\\ext\\zip\\archive\\archivefolder"...
0x18002e189  mov     edx, 28Ch; void *
0x18002e18e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e193  nop
0x18002e194  mov     rcx, [rsp+58h+pv]; pv
0x18002e199  test    rcx, rcx
0x18002e19c  jz      short loc_18002E1A4
0x18002e19e  call    cs:__imp_CoTaskMemFree
0x18002e1a4  mov     eax, ebx
0x18002e1a6  jmp     short loc_18002E1DD
0x18002e1a8  mov     rdx, [rsp+58h+pv]
0x18002e1ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e1b1  inc     r8
0x18002e1b4  cmp     [rdx+r8*2], r15w
0x18002e1b9  jnz     short loc_18002E1B1
0x18002e1bb  lea     rcx, [r14+38h]
0x18002e1bf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e1c4  nop
0x18002e1c5  mov     rcx, [rsp+58h+pv]; pv
0x18002e1ca  test    rcx, rcx
0x18002e1cd  jz      short loc_18002E1D5
0x18002e1cf  call    cs:__imp_CoTaskMemFree
0x18002e1d5  xor     eax, eax
0x18002e1d7  jmp     short loc_18002E1DD
0x18002e1d9  mov     eax, dword ptr [rsp+58h+pv]
0x18002e1dd  mov     rcx, [rsp+58h+var_28]
0x18002e1e2  xor     rcx, rsp; StackCookie
0x18002e1e5  call    __security_check_cookie
0x18002e1ea  mov     rbx, [rsp+58h+arg_10]
0x18002e1ef  mov     rsi, [rsp+58h+arg_18]
0x18002e1f4  add     rsp, 40h
0x18002e1f8  pop     r15
0x18002e1fa  pop     r14
0x18002e1fc  pop     rdi
0x18002e1fd  retn
```
