# CDescriptionManager::HrGetAdditionalResponseHeadersAndCount(IUPnPDeviceControlHttpHeaders *,ushort const *,ushort * *,long *)

- ea: `0x18001a060`
- end: `0x18001a194`
- name: `?HrGetAdditionalResponseHeadersAndCount@CDescriptionManager@@AEAAJPEAUIUPnPDeviceControlHttpHeaders@@PEBGPEAPEAGPEAJ@Z`
- size: `308`
- prototype: `int(CDescriptionManager *__hidden this, struct IUPnPDeviceControlHttpHeaders *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012310`

## callees

- `0x18001a060`
- `0x18001aad0`
- `0x1800322f8`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a134`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a11b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a11b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a102`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a102`
- `OLEAUT32!__imp_SysStringLen` at `0x18001a157`
- `OLEAUT32!__imp_SysStringLen` at `0x18001a157`

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
0x18001a060  mov     [rsp-30h+psz], rcx
0x18001a065  push    rbp
0x18001a066  push    rbx
0x18001a067  push    rsi
0x18001a068  push    rdi
0x18001a069  push    r14
0x18001a06b  push    r15
0x18001a06d  mov     rbp, rsp
0x18001a070  sub     rsp, 38h
0x18001a074  mov     rcx, rdx; struct IUnknown *
0x18001a077  mov     r14, r9
0x18001a07a  mov     rdi, r8
0x18001a07d  mov     rsi, rdx
0x18001a080  call    ?HrEnableStaticCloaking@@YAJPEAUIUnknown@@@Z; HrEnableStaticCloaking(IUnknown *)
0x18001a085  xor     r15d, r15d
0x18001a088  mov     ebx, eax
0x18001a08a  test    eax, eax
0x18001a08c  js      short loc_18001A108
0x18001a08e  mov     [rbp+var_10], r15
0x18001a092  mov     [rbp+bstrString], r15
0x18001a096  test    rdi, rdi
0x18001a099  jz      loc_18001A13C
0x18001a09f  cmp     [rdi], r15w
0x18001a0a3  jz      loc_18001A13C
0x18001a0a9  mov     rax, [rsi]
0x18001a0ac  lea     r8, [rbp+var_10]
0x18001a0b0  lea     rdx, _GUID_6d8ff8ea_730d_11d4_bf42_00b0d0118b56
0x18001a0b7  mov     rcx, rsi
0x18001a0ba  mov     rax, [rax]
0x18001a0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c2  test    eax, eax
0x18001a0c4  js      short loc_18001A13C
0x18001a0c6  mov     rcx, [rbp+var_10]
0x18001a0ca  lea     r8, [rbp+psz]
0x18001a0ce  mov     [rbp+psz], r15
0x18001a0d2  mov     rdx, rdi
0x18001a0d5  mov     rax, [rcx]
0x18001a0d8  mov     rax, [rax+18h]
0x18001a0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0e1  mov     ebx, eax
0x18001a0e3  test    eax, eax
0x18001a0e5  jns     short loc_18001A117
0x18001a0e7  mov     rcx, [rbp+var_10]
0x18001a0eb  mov     rax, [rcx]
0x18001a0ee  mov     rax, [rax+10h]
0x18001a0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0f7  test    ebx, ebx
0x18001a0f9  jns     short loc_18001A153
0x18001a0fb  mov     rdx, [rbp+bstrString]
0x18001a0ff  mov     rcx, rdx; bstrString
0x18001a102  call    cs:__imp_SysFreeString
0x18001a108  mov     eax, ebx
0x18001a10a  add     rsp, 38h
0x18001a10e  pop     r15
0x18001a110  pop     r14
0x18001a112  pop     rdi
0x18001a113  pop     rsi
0x18001a114  pop     rbx
0x18001a115  pop     rbp
0x18001a116  retn
0x18001a117  mov     rcx, [rbp+psz]; psz
0x18001a11b  call    cs:__imp_SysAllocString
0x18001a121  test    rax, rax
0x18001a124  mov     [rbp+bstrString], rax
0x18001a128  mov     ecx, 8007000Eh
0x18001a12d  cmovz   ebx, ecx
0x18001a130  mov     rcx, [rbp+psz]; pv
0x18001a134  call    cs:__imp_CoTaskMemFree
0x18001a13a  jmp     short loc_18001A0E7
0x18001a13c  mov     rax, [rsi]
0x18001a13f  lea     rdx, [rbp+bstrString]
0x18001a143  mov     rcx, rsi
0x18001a146  mov     rax, [rax+18h]
0x18001a14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a14f  mov     ebx, eax
0x18001a151  jmp     short loc_18001A0F7
0x18001a153  mov     rcx, [rbp+bstrString]; pbstr
0x18001a157  call    cs:__imp_SysStringLen
0x18001a15d  test    eax, eax
0x18001a15f  jz      short loc_18001A0FB
0x18001a161  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18001a165  lea     r8, [rbp+psz]; int *
0x18001a169  mov     dword ptr [rbp+psz], r15d
0x18001a16d  call    ?HrValidateAdditionalResponseHeaders@CDescriptionManager@@AEAAJPEAGPEAJ@Z; CDescriptionManager::HrValidateAdditionalResponseHeaders(ushort *,long *)
0x18001a172  mov     ebx, eax
0x18001a174  test    eax, eax
0x18001a176  js      short loc_18001A0FB
0x18001a178  mov     rax, [rbp+bstrString]
0x18001a17c  mov     rdx, r15
0x18001a17f  mov     rcx, [rbp+arg_20]
0x18001a183  mov     [r14], rax
0x18001a186  mov     eax, dword ptr [rbp+psz]
0x18001a189  mov     [rbp+bstrString], rdx
0x18001a18d  mov     [rcx], eax
0x18001a18f  jmp     loc_18001A0FF
```
