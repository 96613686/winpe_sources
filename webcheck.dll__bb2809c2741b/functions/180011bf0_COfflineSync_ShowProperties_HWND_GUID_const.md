# COfflineSync::ShowProperties(HWND__ *,_GUID const &)

- ea: `0x180011bf0`
- end: `0x180011d0f`
- name: `?ShowProperties@COfflineSync@@UEAAJPEAUHWND__@@AEBU_GUID@@@Z`
- size: `287`
- prototype: `int(COfflineSync *__hidden this, HWND, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011bf0`
- `0x180019ae0`
- `0x18001d7c8`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180011c6f`
- `ole32!CoCreateInstance` at `0x180011c6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ccd`

## pseudocode

```c
__int64 __fastcall COfflineSync::ShowProperties(COfflineSync *this, HWND a2, const struct _GUID *a3)
{
  unsigned int v5; // ebx
  struct ISubscriptionItem *v6; // rdi
  __int64 v7; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  struct ISubscriptionItem *v10; // [rsp+60h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  v5 = 0;
  v10 = 0;
  if ( (int)SubscriptionItemFromCookie(0, a3, &v10) >= 0 )
  {
    v6 = v10;
    bstrString = 0;
    if ( (int)ReadBSTR(v10, L"URL", &bstrString) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr2, &ppv) >= 0 )
      {
        LODWORD(v10) = 0;
        (*(void (__fastcall **)(LPVOID, BSTR, HWND))(*(_QWORD *)ppv + 72LL))(ppv, bstrString, a2);
        if ( (*(int (__fastcall **)(LPVOID, BSTR, struct ISubscriptionItem **))(*(_QWORD *)ppv + 48LL))(
               ppv,
               bstrString,
               &v10) < 0
          || !(_DWORD)v10 )
        {
          v5 = 262672;
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      SysFreeString(bstrString);
    }
    ((void (__fastcall *)(struct ISubscriptionItem *))v6->lpVtbl->Release)(v6);
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, v5);
  return v5;
}

```

## disassembly

```asm
0x180011bf0  mov     [rsp-18h+arg_8], rbx
0x180011bf5  mov     [rsp-18h+arg_10], rdi
0x180011bfa  push    rbp
0x180011bfb  push    r14
0x180011bfd  push    r15
0x180011bff  mov     rbp, rsp
0x180011c02  sub     rsp, 40h
0x180011c06  mov     rax, r8
0x180011c09  mov     r15, rdx
0x180011c0c  mov     r14, rcx
0x180011c0f  lea     r8, [rbp+arg_0]; struct ISubscriptionItem **
0x180011c13  xor     ebx, ebx
0x180011c15  mov     rdx, rax; struct _GUID *
0x180011c18  xor     ecx, ecx; int
0x180011c1a  mov     [rbp+arg_0], rbx
0x180011c1e  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x180011c23  test    eax, eax
0x180011c25  js      loc_180011CE2
0x180011c2b  mov     rdi, [rbp+arg_0]
0x180011c2f  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180011c33  mov     rcx, rdi; struct ISubscriptionItem *
0x180011c36  mov     [rbp+bstrString], rbx
0x180011c3a  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x180011c41  call    ?ReadBSTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z; ReadBSTR(ISubscriptionItem *,ushort const *,ushort * *)
0x180011c46  test    eax, eax
0x180011c48  js      loc_180011CD3
0x180011c4e  lea     rax, [rbp+arg_18]
0x180011c52  mov     [rbp+arg_18], rbx
0x180011c56  lea     r9, IID_ISubscriptionMgr2; riid
0x180011c5d  mov     [rsp+40h+ppv], rax; ppv
0x180011c62  xor     edx, edx; pUnkOuter
0x180011c64  lea     r8d, [rbx+1]; dwClsContext
0x180011c68  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x180011c6f  call    cs:__imp_CoCreateInstance
0x180011c75  test    eax, eax
0x180011c77  js      short loc_180011CC9
0x180011c79  mov     rcx, [rbp+arg_18]
0x180011c7d  mov     r8, r15
0x180011c80  mov     rdx, [rbp+bstrString]
0x180011c84  mov     dword ptr [rbp+arg_0], ebx
0x180011c87  mov     rax, [rcx]
0x180011c8a  mov     rax, [rax+48h]
0x180011c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c93  mov     rcx, [rbp+arg_18]
0x180011c97  lea     r8, [rbp+arg_0]
0x180011c9b  mov     rdx, [rbp+bstrString]
0x180011c9f  mov     rax, [rcx]
0x180011ca2  mov     rax, [rax+30h]
0x180011ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cab  test    eax, eax
0x180011cad  js      short loc_180011CB4
0x180011caf  cmp     dword ptr [rbp+arg_0], ebx
0x180011cb2  jnz     short loc_180011CB9
0x180011cb4  mov     ebx, 40210h
0x180011cb9  mov     rcx, [rbp+arg_18]
0x180011cbd  mov     rax, [rcx]
0x180011cc0  mov     rax, [rax+10h]
0x180011cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc9  mov     rcx, [rbp+bstrString]; bstrString
0x180011ccd  call    cs:__imp_SysFreeString
0x180011cd3  mov     rax, [rdi]
0x180011cd6  mov     rcx, rdi
0x180011cd9  mov     rax, [rax+10h]
0x180011cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce2  mov     rcx, [r14+18h]
0x180011ce6  test    rcx, rcx
0x180011ce9  jz      short loc_180011CF9
0x180011ceb  mov     rdx, [rcx]
0x180011cee  mov     rax, [rdx+18h]
0x180011cf2  mov     edx, ebx
0x180011cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf9  mov     rdi, [rsp+40h+arg_10]
0x180011cfe  mov     eax, ebx
0x180011d00  mov     rbx, [rsp+40h+arg_8]
0x180011d05  add     rsp, 40h
0x180011d09  pop     r15
0x180011d0b  pop     r14
0x180011d0d  pop     rbp
0x180011d0e  retn
```
