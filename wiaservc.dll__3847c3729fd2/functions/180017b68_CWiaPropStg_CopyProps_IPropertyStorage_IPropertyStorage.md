# CWiaPropStg::CopyProps(IPropertyStorage *,IPropertyStorage *)

- ea: `0x180017b68`
- end: `0x180017c75`
- name: `?CopyProps@CWiaPropStg@@AEAAJPEAUIPropertyStorage@@0@Z`
- size: `269`
- prototype: `int(CWiaPropStg *__hidden this, struct IPropertyStorage *, struct IPropertyStorage *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18005c6c4`
- `0x18005dd2c`

## callees

- `0x180017b68`
- `0x180017c7c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180017c39`
- `ole32!CoTaskMemFree` at `0x180017c4d`
- `ole32!CoTaskMemFree` at `0x180017c39`
- `ole32!CoTaskMemFree` at `0x180017c4d`

## string_xrefs

- `0x180017c15`: `CopyProps`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::CopyProps(CWiaPropStg *this, struct IPropertyStorage *a2, struct IPropertyStorage *a3)
{
  struct IPropertyStorageVtbl *lpVtbl; // rax
  HRESULT (__stdcall *Enum)(IPropertyStorage *, IEnumSTATPROPSTG **); // rax
  __int64 result; // rax
  int v8; // ebx
  CWiaPropStg *v9; // rcx
  LPVOID v10; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h] BYREF
  struct tagPROPSPEC v12; // [rsp+48h] [rbp-18h] BYREF
  CWiaPropStg *v13; // [rsp+80h] [rbp+20h] BYREF
  int v14; // [rsp+88h] [rbp+28h] BYREF
  __int64 v15; // [rsp+98h] [rbp+38h] BYREF

  v13 = this;
  lpVtbl = a2->lpVtbl;
  v15 = 0;
  Enum = lpVtbl->Enum;
  *(_OWORD *)pv = 0;
  result = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64 *))Enum)(a2, &v15);
  v8 = result;
  if ( (int)result >= 0 )
  {
    LODWORD(v13) = 0;
    v12.ulKind = 1;
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, CWiaPropStg **))(*(_QWORD *)v15 + 24LL))(
               v15,
               1,
               pv,
               &v13) )
    {
      v9 = (CWiaPropStg *)LODWORD(pv[1]);
      v14 = (int)pv[1];
      v10 = pv[0];
      if ( pv[0] )
      {
        v8 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64, int *, LPVOID *))a3->lpVtbl->WritePropertyNames)(
               a3,
               1,
               &v14,
               &v10);
        if ( v8 < 0 )
        {
          CoTaskMemFree(pv[0]);
          break;
        }
        v9 = (CWiaPropStg *)LODWORD(pv[1]);
      }
      v12.propid = (unsigned int)v9;
      v8 = CWiaPropStg::CopyItemProp(v9, a2, a3, &v12, "CopyProps");
      CoTaskMemFree(pv[0]);
      if ( v8 < 0 )
        break;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180017b68  mov     [rsp-18h+arg_10], rbx
0x180017b6d  mov     [rsp-18h+arg_0], rcx
0x180017b72  push    rbp
0x180017b73  push    rsi
0x180017b74  push    rdi
0x180017b75  mov     rbp, rsp
0x180017b78  sub     rsp, 60h
0x180017b7c  mov     rax, [rdx]
0x180017b7f  mov     rsi, rdx
0x180017b82  xorps   xmm0, xmm0
0x180017b85  mov     [rbp+arg_18], 0
0x180017b8d  lea     rdx, [rbp+arg_18]
0x180017b91  mov     rcx, rsi
0x180017b94  mov     rdi, r8
0x180017b97  mov     rax, [rax+58h]
0x180017b9b  movups  xmmword ptr [rbp+pv], xmm0
0x180017b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ba4  mov     ebx, eax
0x180017ba6  test    eax, eax
0x180017ba8  js      loc_180017C65
0x180017bae  mov     dword ptr [rbp+arg_0], 0
0x180017bb5  mov     [rbp+var_18.ulKind], 1
0x180017bbc  mov     rcx, [rbp+arg_18]
0x180017bc0  lea     r9, [rbp+arg_0]
0x180017bc4  lea     r8, [rbp+pv]
0x180017bc8  mov     rdx, [rcx]
0x180017bcb  mov     rax, [rdx+18h]
0x180017bcf  mov     edx, 1
0x180017bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bd9  test    eax, eax
0x180017bdb  jnz     short loc_180017C53
0x180017bdd  mov     rax, [rbp+pv]
0x180017be1  mov     ecx, dword ptr [rbp+pv+8]
0x180017be4  mov     [rbp+arg_8], ecx
0x180017be7  mov     [rbp+var_30], rax
0x180017beb  test    rax, rax
0x180017bee  jz      short loc_180017C15
0x180017bf0  mov     rax, [rdi]
0x180017bf3  lea     r9, [rbp+var_30]
0x180017bf7  lea     r8, [rbp+arg_8]
0x180017bfb  mov     edx, 1
0x180017c00  mov     rcx, rdi
0x180017c03  mov     rax, [rax+38h]
0x180017c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c0c  mov     ebx, eax
0x180017c0e  test    eax, eax
0x180017c10  js      short loc_180017C49
0x180017c12  mov     ecx, dword ptr [rbp+pv+8]; this
0x180017c15  lea     rax, aCopyprops; "CopyProps"
0x180017c1c  mov     dword ptr [rbp+var_18.8], ecx
0x180017c1f  lea     r9, [rbp+var_18]; struct tagPROPSPEC *
0x180017c23  mov     [rsp+60h+var_40], rax; char *
0x180017c28  mov     r8, rdi; struct IPropertyStorage *
0x180017c2b  mov     rdx, rsi; struct IPropertyStorage *
0x180017c2e  call    ?CopyItemProp@CWiaPropStg@@AEAAJPEAUIPropertyStorage@@0PEAUtagPROPSPEC@@PEAD@Z; CWiaPropStg::CopyItemProp(IPropertyStorage *,IPropertyStorage *,tagPROPSPEC *,char *)
0x180017c33  mov     rcx, [rbp+pv]; pv
0x180017c37  mov     ebx, eax
0x180017c39  call    cs:__imp_CoTaskMemFree
0x180017c3f  test    ebx, ebx
0x180017c41  jns     loc_180017BBC
0x180017c47  jmp     short loc_180017C53
0x180017c49  mov     rcx, [rbp+pv]; pv
0x180017c4d  call    cs:__imp_CoTaskMemFree
0x180017c53  mov     rcx, [rbp+arg_18]
0x180017c57  mov     rax, [rcx]
0x180017c5a  mov     rax, [rax+10h]
0x180017c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c63  mov     eax, ebx
0x180017c65  mov     rbx, [rsp+60h+arg_10]
0x180017c6d  add     rsp, 60h
0x180017c71  pop     rdi
0x180017c72  pop     rsi
0x180017c73  pop     rbp
0x180017c74  retn
```
