# CEmailPage::OnNextButtonClicked(TASKFLOW_TRAVERSAL_FLAGS *,ushort * *)

- ea: `0x18003ae80`
- end: `0x18003b051`
- name: `?OnNextButtonClicked@CEmailPage@@UEAAJPEAW4TASKFLOW_TRAVERSAL_FLAGS@@PEAPEAG@Z`
- size: `465`
- prototype: `int(CEmailPage *__hidden this, enum TASKFLOW_TRAVERSAL_FLAGS *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x180024a34`
- `0x180026218`
- `0x180038f18`
- `0x18003ae80`
- `0x18003b32c`
- `0x1800540b4`
- `0x180054134`
- `0x18005f80c`
- `0x18005f8c0`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af69`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003aee8`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003aee8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003af7c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18003af7c`

## pseudocode

```c
__int64 __fastcall CEmailPage::OnNextButtonClicked(
        CEmailPage *this,
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
    DisplayStatusHelper::DisplayRequired(*((DisplayStatusHelper **)this + 12), a2);
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
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 80LL))(*((_QWORD *)this + 5), 0);
        v16 = CoAllocString(L"WebWizardPage", a3);
        *(_DWORD *)a2 = 2;
        v7 = v16;
        if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(
            v17,
            (const EVENT_DESCRIPTOR *)UserAccount_Taskflow_EmailPage_OnNext,
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
  DisplayStatusHelper::DisplayError(*((DisplayStatusHelper **)this + 12), (struct DirectUI::Element *)v12, v13);
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
0x18003ae80  mov     [rsp-38h+arg_18], rbx
0x18003ae85  push    rbp
0x18003ae86  push    rsi
0x18003ae87  push    rdi
0x18003ae88  push    r12
0x18003ae8a  push    r13
0x18003ae8c  push    r14
0x18003ae8e  push    r15
0x18003ae90  mov     rbp, rsp
0x18003ae93  sub     rsp, 60h
0x18003ae97  mov     rax, cs:__security_cookie
0x18003ae9e  xor     rax, rsp
0x18003aea1  mov     [rbp+var_10], rax
0x18003aea5  xor     r13d, r13d
0x18003aea8  mov     rsi, rcx
0x18003aeab  mov     [r8], r13
0x18003aeae  mov     r15, r8
0x18003aeb1  mov     rcx, [rcx+38h]
0x18003aeb5  mov     r12, rdx
0x18003aeb8  test    byte ptr [rcx+95h], 40h
0x18003aebf  jnz     short loc_18003AED4
0x18003aec1  mov     rcx, [rsi+60h]; this
0x18003aec5  mov     ebx, 80070057h
0x18003aeca  call    ?DisplayRequired@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayRequired(DirectUI::Element *)
0x18003aecf  jmp     loc_18003AF82
0x18003aed4  lea     rdx, [rbp+var_30]
0x18003aed8  mov     [rbp+var_30], r13
0x18003aedc  mov     [rbp+pv], r13
0x18003aee0  mov     [rbp+var_20], r13
0x18003aee4  mov     [rbp+var_18], r13
0x18003aee8  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18003aeee  mov     r14, rax
0x18003aef1  test    rax, rax
0x18003aef4  jz      short loc_18003AF31
0x18003aef6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003aefa  inc     rdi
0x18003aefd  cmp     [rax+rdi*2], r13w
0x18003af02  jnz     short loc_18003AEFA
0x18003af04  mov     rdx, rdi
0x18003af07  lea     rcx, [rbp+pv]
0x18003af0b  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18003af10  mov     ebx, eax
0x18003af12  test    eax, eax
0x18003af14  js      loc_18003AFA8
0x18003af1a  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18003af1e  lea     rdx, [rdi+1]; unsigned __int64
0x18003af22  mov     r9, rdi; unsigned __int64
0x18003af25  mov     r8, r14; unsigned __int16 *
0x18003af28  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003af2d  mov     [rbp+var_20], rdi
0x18003af31  lea     rcx, [rbp+pv]
0x18003af35  call    ?TrimWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::TrimWhitespace(void)
0x18003af3a  mov     rdi, [rbp+pv]
0x18003af3e  mov     r14d, 0C87h
0x18003af44  mov     rcx, rdi; unsigned __int16 *
0x18003af47  call    ?IsValidEmailAddressFormat@@YA_NPEBG@Z; IsValidEmailAddressFormat(ushort const *)
0x18003af4c  test    al, al
0x18003af4e  jnz     short loc_18003AFAE
0x18003af50  mov     ebx, 80070057h
0x18003af55  mov     rcx, [rsi+60h]; this
0x18003af59  mov     edx, r14d; struct DirectUI::Element *
0x18003af5c  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@I@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *,uint)
0x18003af61  test    rdi, rdi
0x18003af64  jz      short loc_18003AF6F
0x18003af66  mov     rcx, rdi; pv
0x18003af69  call    cs:__imp_CoTaskMemFree
0x18003af6f  mov     rcx, [rbp+var_30]
0x18003af73  test    rcx, rcx
0x18003af76  jz      short loc_18003AF82
0x18003af78  mov     [rbp+var_30], r13
0x18003af7c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18003af82  mov     eax, ebx
0x18003af84  mov     rcx, [rbp+var_10]
0x18003af88  xor     rcx, rsp; StackCookie
0x18003af8b  call    __security_check_cookie
0x18003af90  mov     rbx, [rsp+60h+arg_18]
0x18003af98  add     rsp, 60h
0x18003af9c  pop     r15
0x18003af9e  pop     r14
0x18003afa0  pop     r13
0x18003afa2  pop     r12
0x18003afa4  pop     rdi
0x18003afa5  pop     rsi
0x18003afa6  pop     rbp
0x18003afa7  retn
0x18003afa8  mov     rdi, [rbp+pv]
0x18003afac  jmp     short loc_18003AF61
0x18003afae  mov     rcx, rdi; unsigned __int16 *
0x18003afb1  call    ?DoesContainOnlyAllowedEmailCharacters@@YA_NPEBG@Z; DoesContainOnlyAllowedEmailCharacters(ushort const *)
0x18003afb6  test    al, al
0x18003afb8  jnz     short loc_18003AFC7
0x18003afba  mov     ebx, 80070057h
0x18003afbf  mov     r14d, 0CD9h
0x18003afc5  jmp     short loc_18003AF55
0x18003afc7  mov     rcx, [rsi+28h]
0x18003afcb  mov     rdx, rdi
0x18003afce  mov     rax, [rcx]
0x18003afd1  mov     rax, [rax+20h]
0x18003afd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afda  mov     ebx, eax
0x18003afdc  test    eax, eax
0x18003afde  js      loc_18003AF55
0x18003afe4  mov     rcx, [rsi+28h]
0x18003afe8  mov     edx, 3
0x18003afed  mov     rax, [rcx]
0x18003aff0  mov     rax, [rax+18h]
0x18003aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aff9  mov     rcx, [rsi+28h]
0x18003affd  xor     edx, edx
0x18003afff  mov     rax, [rcx]
0x18003b002  mov     rax, [rax+50h]
0x18003b006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b00b  mov     rdx, r15; unsigned __int16 **
0x18003b00e  lea     rcx, aWebwizardpage; "WebWizardPage"
0x18003b015  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18003b01a  mov     dword ptr [r12], 2
0x18003b022  mov     ebx, eax
0x18003b024  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003b02b  jz      loc_18003AF61
0x18003b031  lea     rax, [rbp+pv]
0x18003b035  mov     r9d, 1
0x18003b03b  lea     rdx, UserAccount_Taskflow_EmailPage_OnNext
0x18003b042  mov     [rsp+60h+var_40], rax
0x18003b047  call    McGenEventWrite_EventWriteTransfer
0x18003b04c  jmp     loc_18003AF61
```
