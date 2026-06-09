# CAddChildPage::OnNextButtonClicked(TASKFLOW_TRAVERSAL_FLAGS *,ushort * *)

- ea: `0x18003b870`
- end: `0x18003ba2f`
- name: `?OnNextButtonClicked@CAddChildPage@@UEAAJPEAW4TASKFLOW_TRAVERSAL_FLAGS@@PEAPEAG@Z`
- size: `447`
- prototype: `int(CAddChildPage *__hidden this, enum TASKFLOW_TRAVERSAL_FLAGS *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x180024a34`
- `0x180026218`
- `0x180038f18`
- `0x18003b32c`
- `0x18003b870`
- `0x1800540b4`
- `0x180054134`
- `0x18005f80c`
- `0x18005f8c0`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b959`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003b8d8`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003b8d8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003b96c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003b96c`

## pseudocode

```c
__int64 __fastcall CAddChildPage::OnNextButtonClicked(
        CAddChildPage *this,
        enum TASKFLOW_TRAVERSAL_FLAGS *a2,
        unsigned __int16 **a3)
{
  DirectUI::Element *v5; // rcx
  int v7; // ebx
  const unsigned __int16 *ContentString; // rax
  const unsigned __int16 *v9; // r14
  unsigned __int64 v10; // rdi
  unsigned __int16 *Ptr; // rdi
  unsigned int v12; // r14d
  unsigned int v13; // r8d
  DirectUI::Value *v14; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  struct DirectUI::Value *v19; // [rsp+30h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR pv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h]

  *a3 = 0;
  v5 = (DirectUI::Element *)*((_QWORD *)this + 7);
  if ( (*((_BYTE *)v5 + 149) & 0x40) == 0 )
  {
    v7 = -2147024809;
    DisplayStatusHelper::DisplayRequired(*((DisplayStatusHelper **)this + 10), a2);
    return (unsigned int)v7;
  }
  v19 = 0;
  pv.Ptr = 0;
  *(_QWORD *)&pv.Size = 0;
  v21 = 0;
  ContentString = DirectUI::Element::GetContentString(v5, &v19);
  v9 = ContentString;
  if ( ContentString )
  {
    v10 = -1;
    do
      ++v10;
    while ( ContentString[v10] );
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)&pv,
           v10);
    if ( v7 < 0 )
    {
      Ptr = (unsigned __int16 *)pv.Ptr;
      goto LABEL_11;
    }
    StringCchCopyNW((unsigned __int16 *)pv.Ptr, v10 + 1, v9, v10);
    *(_QWORD *)&pv.Size = v10;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::TrimWhitespace(&pv);
  Ptr = (unsigned __int16 *)pv.Ptr;
  v12 = 3207;
  if ( IsValidEmailAddressFormat((const unsigned __int16 *)pv.Ptr) )
  {
    if ( DoesContainOnlyAllowedEmailCharacters(Ptr) )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 5) + 32LL))(
             *((_QWORD *)this + 5),
             Ptr);
      if ( v7 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 3);
        v16 = CoAllocString(L"WebWizardPage", a3);
        *(_DWORD *)a2 = 2;
        v7 = v16;
        if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            v17,
            (const EVENT_DESCRIPTOR *)UserAccount_Taskflow_AddChildPage_OnNext,
            v18,
            1u,
            &pv);
        goto LABEL_11;
      }
    }
    else
    {
      v7 = -2147024809;
      v12 = 3289;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  DisplayStatusHelper::DisplayError(*((DisplayStatusHelper **)this + 10), (struct DirectUI::Element *)v12, v13);
LABEL_11:
  if ( Ptr )
    CoTaskMemFree(Ptr);
  v14 = v19;
  if ( v19 )
  {
    v19 = 0;
    DirectUI::Value::Release(v14);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003b870  mov     [rsp-38h+arg_18], rbx
0x18003b875  push    rbp
0x18003b876  push    rsi
0x18003b877  push    rdi
0x18003b878  push    r12
0x18003b87a  push    r13
0x18003b87c  push    r14
0x18003b87e  push    r15
0x18003b880  mov     rbp, rsp
0x18003b883  sub     rsp, 60h
0x18003b887  mov     rax, cs:__security_cookie
0x18003b88e  xor     rax, rsp
0x18003b891  mov     [rbp+var_10], rax
0x18003b895  xor     r13d, r13d
0x18003b898  mov     rsi, rcx
0x18003b89b  mov     [r8], r13
0x18003b89e  mov     r15, r8
0x18003b8a1  mov     rcx, [rcx+38h]
0x18003b8a5  mov     r12, rdx
0x18003b8a8  test    byte ptr [rcx+95h], 40h
0x18003b8af  jnz     short loc_18003B8C4
0x18003b8b1  mov     rcx, [rsi+50h]; this
0x18003b8b5  mov     ebx, 80070057h
0x18003b8ba  call    ?DisplayRequired@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayRequired(DirectUI::Element *)
0x18003b8bf  jmp     loc_18003B972
0x18003b8c4  lea     rdx, [rbp+var_30]
0x18003b8c8  mov     [rbp+var_30], r13
0x18003b8cc  mov     [rbp+pv], r13
0x18003b8d0  mov     [rbp+var_20], r13
0x18003b8d4  mov     [rbp+var_18], r13
0x18003b8d8  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18003b8de  mov     r14, rax
0x18003b8e1  test    rax, rax
0x18003b8e4  jz      short loc_18003B921
0x18003b8e6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003b8ea  inc     rdi
0x18003b8ed  cmp     [rax+rdi*2], r13w
0x18003b8f2  jnz     short loc_18003B8EA
0x18003b8f4  mov     rdx, rdi
0x18003b8f7  lea     rcx, [rbp+pv]
0x18003b8fb  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18003b900  mov     ebx, eax
0x18003b902  test    eax, eax
0x18003b904  js      loc_18003B998
0x18003b90a  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18003b90e  lea     rdx, [rdi+1]; unsigned __int64
0x18003b912  mov     r9, rdi; unsigned __int64
0x18003b915  mov     r8, r14; unsigned __int16 *
0x18003b918  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003b91d  mov     [rbp+var_20], rdi
0x18003b921  lea     rcx, [rbp+pv]
0x18003b925  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18003b92a  mov     rdi, [rbp+pv]
0x18003b92e  mov     r14d, 0C87h
0x18003b934  mov     rcx, rdi; unsigned __int16 *
0x18003b937  call    ?IsValidEmailAddressFormat@@YA_NPEBG@Z; IsValidEmailAddressFormat(ushort const *)
0x18003b93c  test    al, al
0x18003b93e  jnz     short loc_18003B99E
0x18003b940  mov     ebx, 80070057h
0x18003b945  mov     rcx, [rsi+50h]; this
0x18003b949  mov     edx, r14d; struct DirectUI::Element *
0x18003b94c  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003b951  test    rdi, rdi
0x18003b954  jz      short loc_18003B95F
0x18003b956  mov     rcx, rdi; pv
0x18003b959  call    cs:__imp_CoTaskMemFree
0x18003b95f  mov     rcx, [rbp+var_30]
0x18003b963  test    rcx, rcx
0x18003b966  jz      short loc_18003B972
0x18003b968  mov     [rbp+var_30], r13
0x18003b96c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18003b972  mov     eax, ebx
0x18003b974  mov     rcx, [rbp+var_10]
0x18003b978  xor     rcx, rsp; StackCookie
0x18003b97b  call    __security_check_cookie
0x18003b980  mov     rbx, [rsp+60h+arg_18]
0x18003b988  add     rsp, 60h
0x18003b98c  pop     r15
0x18003b98e  pop     r14
0x18003b990  pop     r13
0x18003b992  pop     r12
0x18003b994  pop     rdi
0x18003b995  pop     rsi
0x18003b996  pop     rbp
0x18003b997  retn
0x18003b998  mov     rdi, [rbp+pv]
0x18003b99c  jmp     short loc_18003B951
0x18003b99e  mov     rcx, rdi; unsigned __int16 *
0x18003b9a1  call    ?DoesContainOnlyAllowedEmailCharacters@@YA_NPEBG@Z; DoesContainOnlyAllowedEmailCharacters(ushort const *)
0x18003b9a6  test    al, al
0x18003b9a8  jnz     short loc_18003B9B7
0x18003b9aa  mov     ebx, 80070057h
0x18003b9af  mov     r14d, 0CD9h
0x18003b9b5  jmp     short loc_18003B945
0x18003b9b7  mov     rcx, [rsi+28h]
0x18003b9bb  mov     rdx, rdi
0x18003b9be  mov     rax, [rcx]
0x18003b9c1  mov     rax, [rax+20h]
0x18003b9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9ca  mov     ebx, eax
0x18003b9cc  test    eax, eax
0x18003b9ce  js      loc_18003B945
0x18003b9d4  mov     rcx, [rsi+28h]
0x18003b9d8  mov     edx, 3
0x18003b9dd  mov     rax, [rcx]
0x18003b9e0  mov     rax, [rax+18h]
0x18003b9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9e9  mov     rdx, r15; unsigned __int16 **
0x18003b9ec  lea     rcx, aWebwizardpage; "WebWizardPage"
0x18003b9f3  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18003b9f8  mov     dword ptr [r12], 2
0x18003ba00  mov     ebx, eax
0x18003ba02  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003ba09  jz      loc_18003B951
0x18003ba0f  lea     rax, [rbp+pv]
0x18003ba13  mov     r9d, 1
0x18003ba19  lea     rdx, UserAccount_Taskflow_AddChildPage_OnNext
0x18003ba20  mov     [rsp+60h+var_40], rax
0x18003ba25  call    McGenEventWrite_EventWriteTransfer
0x18003ba2a  jmp     loc_18003B951
```
