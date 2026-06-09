# CDescriptionManager::HrGetAdditionalResponseHeadersAndCount(IUPnPDeviceControlHttpHeaders *,ushort const *,ushort * *,long *)

- ea: `0x18000ecf0`
- end: `0x18000ee49`
- name: `?HrGetAdditionalResponseHeadersAndCount@CDescriptionManager@@AEAAJPEAUIUPnPDeviceControlHttpHeaders@@PEBGPEAPEAGPEAJ@Z`
- size: `345`
- prototype: `int(CDescriptionManager *__hidden this, struct IUPnPDeviceControlHttpHeaders *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800062c0`

## callees

- `0x18000ecf0`
- `0x18000f7e0`
- `0x180034098`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000edd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000edd9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000edba`
- `OLEAUT32!__imp_SysAllocString` at `0x18000edba`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed9a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ee02`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ee02`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrGetAdditionalResponseHeadersAndCount(
        OLECHAR *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        int *a5)
{
  int v8; // ebx
  OLECHAR *v9; // rdx
  CDescriptionManager *v11; // rcx
  int *v12; // rcx
  BSTR bstrString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+28h] [rbp-10h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp+38h] BYREF

  psz = this;
  v8 = HrEnableStaticCloaking(a2);
  if ( v8 >= 0 )
  {
    v14 = 0;
    bstrString = 0;
    if ( a3
      && *a3
      && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_6d8ff8ea_730d_11d4_bf42_00b0d0118b56,
           &v14) >= 0 )
    {
      psz = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, OLECHAR **))(*(_QWORD *)v14 + 24LL))(
             v14,
             a3,
             &psz);
      if ( v8 >= 0 )
      {
        bstrString = SysAllocString(psz);
        if ( !bstrString )
          v8 = -2147024882;
        CoTaskMemFree(psz);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    else
    {
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))a2->lpVtbl[1].QueryInterface)(a2, &bstrString);
    }
    if ( v8 >= 0
      && SysStringLen(bstrString)
      && (LODWORD(psz) = 0,
          v8 = CDescriptionManager::HrValidateAdditionalResponseHeaders(v11, bstrString, (int *)&psz),
          v8 >= 0) )
    {
      v9 = 0;
      v12 = a5;
      *a4 = bstrString;
      bstrString = 0;
      *v12 = (int)psz;
    }
    else
    {
      v9 = bstrString;
    }
    SysFreeString(v9);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ecf0  mov     [rsp-30h+psz], rcx
0x18000ecf5  push    rbp
0x18000ecf6  push    rbx
0x18000ecf7  push    rsi
0x18000ecf8  push    rdi
0x18000ecf9  push    r14
0x18000ecfb  push    r15
0x18000ecfd  mov     rbp, rsp
0x18000ed00  sub     rsp, 38h
0x18000ed04  mov     rcx, rdx; struct IUnknown *
0x18000ed07  mov     r14, r9
0x18000ed0a  mov     rdi, r8
0x18000ed0d  mov     rsi, rdx
0x18000ed10  call    ?HrEnableStaticCloaking@@YAJPEAUIUnknown@@@Z; HrEnableStaticCloaking(IUnknown *)
0x18000ed15  xor     r15d, r15d
0x18000ed18  mov     ebx, eax
0x18000ed1a  test    eax, eax
0x18000ed1c  js      loc_18000EDA6
0x18000ed22  mov     [rbp+var_10], r15
0x18000ed26  mov     [rbp+bstrString], r15
0x18000ed2a  test    rdi, rdi
0x18000ed2d  jz      loc_18000EDE7
0x18000ed33  cmp     [rdi], r15w
0x18000ed37  jz      loc_18000EDE7
0x18000ed3d  mov     rax, [rsi]
0x18000ed40  lea     r8, [rbp+var_10]
0x18000ed44  lea     rdx, _GUID_6d8ff8ea_730d_11d4_bf42_00b0d0118b56
0x18000ed4b  mov     rcx, rsi
0x18000ed4e  mov     rax, [rax]
0x18000ed51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed56  test    eax, eax
0x18000ed58  js      loc_18000EDE7
0x18000ed5e  mov     rcx, [rbp+var_10]
0x18000ed62  lea     r8, [rbp+psz]
0x18000ed66  mov     [rbp+psz], r15
0x18000ed6a  mov     rdx, rdi
0x18000ed6d  mov     rax, [rcx]
0x18000ed70  mov     rax, [rax+18h]
0x18000ed74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed79  mov     ebx, eax
0x18000ed7b  test    eax, eax
0x18000ed7d  jns     short loc_18000EDB6
0x18000ed7f  mov     rcx, [rbp+var_10]
0x18000ed83  mov     rax, [rcx]
0x18000ed86  mov     rax, [rax+10h]
0x18000ed8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed8f  test    ebx, ebx
0x18000ed91  jns     short loc_18000EDFE
0x18000ed93  mov     rdx, [rbp+bstrString]
0x18000ed97  mov     rcx, rdx; bstrString
0x18000ed9a  call    cs:__imp_SysFreeString
0x18000eda1  nop     dword ptr [rax+rax+00h]
0x18000eda6  mov     eax, ebx
0x18000eda8  add     rsp, 38h
0x18000edac  pop     r15
0x18000edae  pop     r14
0x18000edb0  pop     rdi
0x18000edb1  pop     rsi
0x18000edb2  pop     rbx
0x18000edb3  pop     rbp
0x18000edb4  retn
0x18000edb6  mov     rcx, [rbp+psz]; psz
0x18000edba  call    cs:__imp_SysAllocString
0x18000edc1  nop     dword ptr [rax+rax+00h]
0x18000edc6  test    rax, rax
0x18000edc9  mov     [rbp+bstrString], rax
0x18000edcd  mov     ecx, 8007000Eh
0x18000edd2  cmovz   ebx, ecx
0x18000edd5  mov     rcx, [rbp+psz]; pv
0x18000edd9  call    cs:__imp_CoTaskMemFree
0x18000ede0  nop     dword ptr [rax+rax+00h]
0x18000ede5  jmp     short loc_18000ED7F
0x18000ede7  mov     rax, [rsi]
0x18000edea  lea     rdx, [rbp+bstrString]
0x18000edee  mov     rcx, rsi
0x18000edf1  mov     rax, [rax+18h]
0x18000edf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edfa  mov     ebx, eax
0x18000edfc  jmp     short loc_18000ED8F
0x18000edfe  mov     rcx, [rbp+bstrString]; pbstr
0x18000ee02  call    cs:__imp_SysStringLen
0x18000ee09  nop     dword ptr [rax+rax+00h]
0x18000ee0e  test    eax, eax
0x18000ee10  jz      short loc_18000ED93
0x18000ee12  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18000ee16  lea     r8, [rbp+psz]; int *
0x18000ee1a  mov     dword ptr [rbp+psz], r15d
0x18000ee1e  call    ?HrValidateAdditionalResponseHeaders@CDescriptionManager@@AEAAJPEAGPEAJ@Z; CDescriptionManager::HrValidateAdditionalResponseHeaders(ushort *,long *)
0x18000ee23  mov     ebx, eax
0x18000ee25  test    eax, eax
0x18000ee27  js      loc_18000ED93
0x18000ee2d  mov     rax, [rbp+bstrString]
0x18000ee31  mov     rdx, r15
0x18000ee34  mov     rcx, [rbp+arg_20]
0x18000ee38  mov     [r14], rax
0x18000ee3b  mov     eax, dword ptr [rbp+psz]
0x18000ee3e  mov     [rbp+bstrString], rdx
0x18000ee42  mov     [rcx], eax
0x18000ee44  jmp     loc_18000ED97
```
