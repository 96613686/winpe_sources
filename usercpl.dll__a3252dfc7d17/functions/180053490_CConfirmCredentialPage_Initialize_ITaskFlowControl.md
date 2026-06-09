# CConfirmCredentialPage::Initialize(ITaskFlowControl *)

- ea: `0x180053490`
- end: `0x18005363e`
- name: `?Initialize@CConfirmCredentialPage@@UEAAJPEAUITaskFlowControl@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(CConfirmCredentialPage *__hidden this, struct ITaskFlowControl *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18003d010`
- `0x180053490`
- `0x180053f54`
- `0x180063bc8`
- `0x180074f14`
- `0x18007510c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005352e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005352e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535f9`

## string_xrefs

- `0x180053546`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x1800535a3`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x180053605`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`

## pseudocode

```c
__int64 __fastcall CConfirmCredentialPage::Initialize(CConfirmCredentialPage *this, struct ITaskFlowControl *a2)
{
  struct DirectUI::Element *Element; // rax
  __int64 v4; // rcx
  struct DirectUI::Element *v5; // rdi
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rdx
  struct DirectUI::Element *v9; // rax
  __int64 v10; // rcx
  struct DirectUI::Element *v11; // rdi
  int v12; // eax
  struct DirectUI::Element *v13; // rax
  struct DirectUI::Element *v14; // rdi
  int v15; // eax
  struct DirectUI::Element *v16; // rax
  void *v18; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v20; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF

  *((_QWORD *)this + 3) = a2;
  (*(void (__fastcall **)(struct ITaskFlowControl *))(*(_QWORD *)a2 + 8LL))(a2);
  Element = CBaseTaskFlowPage::_FindElement(this, L"idDescription");
  v4 = *((_QWORD *)this + 6);
  v5 = Element;
  v20 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, &v20, 0, 0);
  if ( v6 < 0 )
  {
    v8 = 114;
  }
  else
  {
    pv = 0;
    v6 = TResourceStringAllocCopyEx<unsigned short *>(
           g_hinst,
           *((unsigned int *)&`CConfirmCredentialPage::Initialize'::`12'::rguPageTextResIds + v20),
           v7,
           (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
           v18,
           (char *)&pv);
    if ( v6 >= 0 )
    {
      SetElementContentStringAndAccName(v5, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
      goto LABEL_7;
    }
    v8 = 110;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
    (const char *)(unsigned int)v6,
    (int)v18);
LABEL_7:
  v9 = CBaseTaskFlowPage::_FindElement(this, L"idUsername");
  v10 = *((_QWORD *)this + 6);
  v11 = v9;
  v21 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v10 + 24LL))(v10, &v21);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
      (const char *)(unsigned int)v12,
      (int)v18);
  }
  else
  {
    SetElementContentStringAndAccName(v11, v21);
    CoTaskMemFree(v21);
  }
  v13 = CBaseTaskFlowPage::_FindElement(this, L"idAccountName");
  v14 = (struct DirectUI::Element *)element_cast<DirectUI::RichText>(v13);
  v15 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          &v21);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
      (const char *)(unsigned int)v15,
      (int)v18);
  }
  else
  {
    SetElementContentStringAndAccName(v14, v21);
    CoTaskMemFree(v21);
  }
  v16 = CBaseTaskFlowPage::_FindElement(this, L"idErrorMessage");
  *((_QWORD *)this + 7) = element_cast<DirectUI::RichText>(v16);
  return 0;
}

```

## disassembly

```asm
0x180053490  push    rbp
0x180053492  push    rbx
0x180053493  push    rdi
0x180053494  mov     rbp, rsp
0x180053497  sub     rsp, 30h
0x18005349b  mov     [rcx+18h], rdx
0x18005349f  mov     rbx, rcx
0x1800534a2  mov     rax, [rdx]
0x1800534a5  mov     rcx, rdx
0x1800534a8  mov     rax, [rax+8]
0x1800534ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534b1  lea     rdx, aIddescription; "idDescription"
0x1800534b8  mov     rcx, rbx; this
0x1800534bb  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x1800534c0  mov     rcx, [rbx+30h]
0x1800534c4  mov     rdi, rax
0x1800534c7  mov     [rbp+arg_0], 0
0x1800534ce  xor     r9d, r9d
0x1800534d1  xor     r8d, r8d
0x1800534d4  mov     rdx, [rcx]
0x1800534d7  mov     rax, [rdx+30h]
0x1800534db  lea     rdx, [rbp+arg_0]
0x1800534df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534e4  test    eax, eax
0x1800534e6  js      short loc_18005353D
0x1800534e8  movsxd  rdx, [rbp+arg_0]
0x1800534ec  lea     rcx, ?rguPageTextResIds@?M@??Initialize@CConfirmCredentialPage@@UEAAJPEAUITaskFlowControl@@@Z@4PAIA; uint near * `CConfirmCredentialPage::Initialize(ITaskFlowControl *)'::`12'::rguPageTextResIds
0x1800534f3  lea     rax, [rbp+pv]
0x1800534f7  mov     [rbp+pv], 0
0x1800534ff  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180053506  mov     [rsp+30h+var_8], rax; void *
0x18005350b  mov     edx, [rcx+rdx*4]; int
0x18005350e  mov     rcx, cs:g_hinst; int
0x180053515  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18005351a  test    eax, eax
0x18005351c  js      short loc_180053536
0x18005351e  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180053522  mov     rcx, rdi; struct DirectUI::Element *
0x180053525  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18005352a  mov     rcx, [rbp+pv]; pv
0x18005352e  call    cs:__imp_CoTaskMemFree
0x180053534  jmp     short loc_180053555
0x180053536  mov     edx, 6Eh ; 'n'
0x18005353b  jmp     short loc_180053542
0x18005353d  mov     edx, 72h ; 'r'; void *
0x180053542  mov     rcx, [rbp+18h]; this
0x180053546  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x18005354d  mov     r9d, eax; char *
0x180053550  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053555  lea     rdx, aIdusername; "idUsername"
0x18005355c  mov     rcx, rbx; this
0x18005355f  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x180053564  mov     rcx, [rbx+30h]
0x180053568  mov     rdi, rax
0x18005356b  mov     [rbp+arg_8], 0
0x180053573  mov     rdx, [rcx]
0x180053576  mov     rax, [rdx+18h]
0x18005357a  lea     rdx, [rbp+arg_8]
0x18005357e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053583  test    eax, eax
0x180053585  js      short loc_18005359F
0x180053587  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18005358b  mov     rcx, rdi; struct DirectUI::Element *
0x18005358e  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180053593  mov     rcx, [rbp+arg_8]; pv
0x180053597  call    cs:__imp_CoTaskMemFree
0x18005359d  jmp     short loc_1800535B7
0x18005359f  mov     rcx, [rbp+18h]; this
0x1800535a3  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x1800535aa  mov     r9d, eax; char *
0x1800535ad  mov     edx, 7Dh ; '}'; void *
0x1800535b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800535b7  lea     rdx, aIdaccountname; "idAccountName"
0x1800535be  mov     rcx, rbx; this
0x1800535c1  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x1800535c6  mov     rcx, rax
0x1800535c9  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x1800535ce  mov     rcx, [rbx+30h]
0x1800535d2  mov     rdi, rax
0x1800535d5  mov     rdx, [rcx]
0x1800535d8  mov     rax, [rdx+20h]
0x1800535dc  lea     rdx, [rbp+arg_8]
0x1800535e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535e5  test    eax, eax
0x1800535e7  js      short loc_180053601
0x1800535e9  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x1800535ed  mov     rcx, rdi; struct DirectUI::Element *
0x1800535f0  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x1800535f5  mov     rcx, [rbp+arg_8]; pv
0x1800535f9  call    cs:__imp_CoTaskMemFree
0x1800535ff  jmp     short loc_180053619
0x180053601  mov     rcx, [rbp+18h]; this
0x180053605  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x18005360c  mov     r9d, eax; char *
0x18005360f  mov     edx, 86h; void *
0x180053614  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053619  lea     rdx, aIderrormessage_0; "idErrorMessage"
0x180053620  mov     rcx, rbx; this
0x180053623  call    ?_FindElement@CBaseTaskFlowPage@@IEAAPEAVElement@DirectUI@@PEBG@Z; CBaseTaskFlowPage::_FindElement(ushort const *)
0x180053628  mov     rcx, rax
0x18005362b  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x180053630  mov     [rbx+38h], rax
0x180053634  xor     eax, eax
0x180053636  add     rsp, 30h
0x18005363a  pop     rdi
0x18005363b  pop     rbx
0x18005363c  pop     rbp
0x18005363d  retn
```
