# CConfirmCredentialPage::OnNextButtonClicked(TASKFLOW_TRAVERSAL_FLAGS *,ushort * *)

- ea: `0x180053650`
- end: `0x1800537b2`
- name: `?OnNextButtonClicked@CConfirmCredentialPage@@UEAAJPEAW4TASKFLOW_TRAVERSAL_FLAGS@@PEAPEAG@Z`
- size: `354`
- prototype: `__int64 __fastcall(CConfirmCredentialPage *__hidden this, enum TASKFLOW_TRAVERSAL_FLAGS *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a74`
- `0x180053650`
- `0x180053900`
- `0x180053f54`
- `0x180063bc8`
- `0x18007510c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053727`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005371f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005378f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005371f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005378f`

## string_xrefs

- `0x180053752`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x18005376e`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`

## pseudocode

```c
__int64 __fastcall CConfirmCredentialPage::OnNextButtonClicked(
        struct DirectUI::Element **this,
        enum TASKFLOW_TRAVERSAL_FLAGS *a2,
        unsigned __int16 **a3)
{
  int v6; // eax
  __int64 v7; // r8
  int v8; // edi
  int v9; // ebp
  __int64 result; // rax
  void *v11; // [rsp+20h] [rbp-78h]
  int v12; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v13; // [rsp+38h] [rbp-60h] BYREF
  char v14; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int16 *pv; // [rsp+A0h] [rbp+8h]

  SetElementContentStringAndAccName(this[6], 0);
  *a3 = 0;
  v6 = CConfirmCredentialPage::_CollectAndVerifyUsersCredential((CConfirmCredentialPage *)(this - 1));
  v8 = v6;
  if ( (v6 & 0x1FFF0000) == 0x70000 )
    v6 = (unsigned __int16)v6;
  if ( v8 >= 0 )
  {
    *a3 = 0;
    result = 0;
    *(_DWORD *)a2 = 0;
  }
  else
  {
    if ( v6 != 1223 )
    {
      pv = 0;
      v13 = 0;
      v14 = 1;
      v9 = TResourceStringAllocCopyEx<unsigned short *>(
             g_hinst,
             3363,
             v7,
             (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
             v11,
             (char *)&v13);
      if ( v14 )
        pv = v13;
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
          (const char *)(unsigned int)v9,
          v12);
      else
        SetElementContentStringAndAccName(this[6], pv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
        (const char *)(unsigned int)v8,
        v12);
      if ( pv )
        CoTaskMemFree(pv);
    }
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180053650  push    rbx
0x180053652  push    rbp
0x180053653  push    rsi
0x180053654  push    rdi
0x180053655  push    r12
0x180053657  push    r13
0x180053659  push    r14
0x18005365b  push    r15
0x18005365d  sub     rsp, 58h
0x180053661  mov     r14, rdx
0x180053664  mov     r13, rcx
0x180053667  mov     rcx, [rcx+30h]; struct DirectUI::Element *
0x18005366b  xor     edx, edx; unsigned __int16 *
0x18005366d  mov     rsi, r8
0x180053670  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180053675  xor     r15d, r15d
0x180053678  lea     rcx, [r13-8]; this
0x18005367c  mov     [rsi], r15
0x18005367f  call    ?_CollectAndVerifyUsersCredential@CConfirmCredentialPage@@AEAAJXZ; CConfirmCredentialPage::_CollectAndVerifyUsersCredential(void)
0x180053684  mov     r9d, eax
0x180053687  mov     edi, eax
0x180053689  and     r9d, 1FFF0000h
0x180053690  cmp     r9d, 70000h
0x180053697  jnz     short loc_18005369C
0x180053699  movzx   eax, di
0x18005369c  test    edi, edi
0x18005369e  jns     loc_180053799
0x1800536a4  cmp     eax, 4C7h
0x1800536a9  jz      loc_180053795
0x1800536af  mov     rcx, cs:g_hinst; int
0x1800536b6  lea     rax, [rsp+98h+pv]
0x1800536be  mov     [rsp+98h+var_68], rax
0x1800536c3  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800536ca  lea     rax, [rsp+98h+var_60]
0x1800536cf  mov     [rsp+98h+pv], r15
0x1800536d7  mov     edx, 0D23h; int
0x1800536dc  mov     [rsp+98h+var_70], rax; void *
0x1800536e1  mov     [rsp+98h+var_60], r15
0x1800536e6  mov     [rsp+98h+var_58], 1
0x1800536eb  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800536f0  mov     esi, eax
0x1800536f2  mov     ebp, eax
0x1800536f4  shr     esi, 1Fh
0x1800536f7  xor     sil, 1
0x1800536fb  cmp     [rsp+98h+var_58], r15b
0x180053700  jz      short loc_180053730
0x180053702  mov     r14, [rsp+98h+var_68]
0x180053707  mov     r12, [rsp+98h+var_60]
0x18005370c  mov     r15, [r14]
0x18005370f  test    r15, r15
0x180053712  jz      short loc_18005372D
0x180053714  call    cs:__imp_GetLastError
0x18005371a  mov     rcx, r15; pv
0x18005371d  mov     ebx, eax
0x18005371f  call    cs:__imp_CoTaskMemFree
0x180053725  mov     ecx, ebx; dwErrCode
0x180053727  call    cs:__imp_SetLastError
0x18005372d  mov     [r14], r12
0x180053730  test    sil, sil
0x180053733  jz      short loc_180053746
0x180053735  mov     rdx, [rsp+98h+pv]; unsigned __int16 *
0x18005373d  mov     rcx, [r13+30h]; struct DirectUI::Element *
0x180053741  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x180053746  test    ebp, ebp
0x180053748  jns     short loc_180053766
0x18005374a  mov     rcx, [rsp+98h]; this
0x180053752  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x180053759  mov     r9d, ebp; char *
0x18005375c  mov     edx, 0ADh; void *
0x180053761  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053766  mov     rcx, [rsp+98h]; this
0x18005376e  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x180053775  mov     r9d, edi; char *
0x180053778  mov     edx, 0AEh; void *
0x18005377d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053782  mov     rcx, [rsp+98h+pv]; pv
0x18005378a  test    rcx, rcx
0x18005378d  jz      short loc_180053795
0x18005378f  call    cs:__imp_CoTaskMemFree
0x180053795  mov     eax, edi
0x180053797  jmp     short loc_1800537A1
0x180053799  mov     [rsi], r15
0x18005379c  xor     eax, eax
0x18005379e  mov     [r14], r15d
0x1800537a1  add     rsp, 58h
0x1800537a5  pop     r15
0x1800537a7  pop     r14
0x1800537a9  pop     r13
0x1800537ab  pop     r12
0x1800537ad  pop     rdi
0x1800537ae  pop     rsi
0x1800537af  pop     rbp
0x1800537b0  pop     rbx
0x1800537b1  retn
```
