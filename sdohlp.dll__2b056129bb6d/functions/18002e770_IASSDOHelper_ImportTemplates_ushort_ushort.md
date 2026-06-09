# IASSDOHelper::ImportTemplates(ushort *,ushort *)

- ea: `0x18002e770`
- end: `0x18002e962`
- name: `?ImportTemplates@IASSDOHelper@@UEAAJPEAG0@Z`
- size: `498`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002e770`
- `0x18002ee50`
- `0x18002efa0`
- `0x18002f08c`
- `0x18003cee8`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18002e81c`: `Failed to get templates SDO in Sdo helper after templates import, %!hresult!`
- `0x18002e90e`: `Import templates (%ls) failed. hr = %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::ImportTemplates(IASSDOHelper *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v5; // edi
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, _QWORD *, char *); // rdi
  _QWORD *v8; // rdx
  int v9; // ebx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD *, __int64 *, char *, __int16); // rdi
  _QWORD *v13; // rdx
  __int64 *v14; // rbx
  __int16 v15; // [rsp+20h] [rbp-28h]
  int v16; // [rsp+28h] [rbp-20h]
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF
  char v18; // [rsp+68h] [rbp+20h] BYREF

  v5 = IASExim::ImportTemplates((IASSDOHelper *)((char *)this + 120), a2, a3);
  if ( v5 < 0 )
  {
LABEL_15:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v14 = &qword_180061188;
      if ( a3 )
        v14 = (__int64 *)a3;
      WppDbgPrint("Import templates (%ls) failed. hr = %!hresult!");
      v16 = v5;
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)v14,
        v16);
    }
    return (unsigned int)v5;
  }
  v17 = 0;
  ATL::CComPtrBase<IIASItem>::Release((char *)this + 96);
  v6 = *((_QWORD *)this + 10);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(*(_QWORD *)v6 + 128LL);
  v8 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v18, L"IAS");
  if ( v8 )
    v8 = (_QWORD *)*v8;
  v9 = v7(v6, v8, (char *)this + 96);
  _bstr_t::_Free((_bstr_t *)&v18);
  if ( v9 >= 0 )
  {
    v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 11))(
           *((_QWORD *)this + 11),
           &IID_IUnknown,
           &v17);
    if ( v5 >= 0 )
    {
      v11 = *((_QWORD *)this + 10);
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *, char *, __int16))(*(_QWORD *)v11 + 144LL);
      v13 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v18, L"IAS");
      if ( v13 )
        v13 = (_QWORD *)*v13;
      v15 = -1;
      v5 = v12(v11, v13, &v17, (char *)this + 96, v15);
      _bstr_t::_Free((_bstr_t *)&v18);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    if ( v5 >= 0 )
      return (unsigned int)v5;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("Failed to get templates SDO in Sdo helper after templates import, %!hresult!");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
      (unsigned int)"NPSSDO",
      v9);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002e770  mov     [rsp+arg_8], rbx
0x18002e775  mov     [rsp+arg_10], rbp
0x18002e77a  push    rsi
0x18002e77b  push    rdi
0x18002e77c  push    r14
0x18002e77e  sub     rsp, 30h
0x18002e782  mov     rsi, rcx
0x18002e785  mov     r14, r8
0x18002e788  add     rcx, 78h ; 'x'; this
0x18002e78c  call    ?ImportTemplates@IASExim@@QEAAJPEAG0@Z; IASExim::ImportTemplates(ushort *,ushort *)
0x18002e791  mov     edi, eax
0x18002e793  test    eax, eax
0x18002e795  js      loc_18002E8DF
0x18002e79b  lea     rbp, [rsi+60h]
0x18002e79f  mov     [rsp+48h+arg_0], 0
0x18002e7a8  mov     rcx, rbp
0x18002e7ab  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x18002e7b0  mov     rbx, [rsi+50h]
0x18002e7b4  lea     rdx, aIas; "IAS"
0x18002e7bb  lea     rcx, [rsp+48h+arg_18]; this
0x18002e7c0  mov     rax, [rbx]
0x18002e7c3  mov     rdi, [rax+80h]
0x18002e7ca  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002e7cf  mov     rdx, [rax]
0x18002e7d2  test    rdx, rdx
0x18002e7d5  jz      short loc_18002E7DA
0x18002e7d7  mov     rdx, [rdx]
0x18002e7da  mov     r8, rbp
0x18002e7dd  mov     rcx, rbx
0x18002e7e0  mov     rax, rdi
0x18002e7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7e8  lea     rcx, [rsp+48h+arg_18]; this
0x18002e7ed  mov     ebx, eax
0x18002e7ef  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e7f4  test    ebx, ebx
0x18002e7f6  jns     short loc_18002E860
0x18002e7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7ff  lea     rdx, WPP_GLOBAL_Control
0x18002e806  cmp     rcx, rdx
0x18002e809  jz      short loc_18002E84F
0x18002e80b  cmp     byte ptr [rcx+19h], 2
0x18002e80f  jb      short loc_18002E84F
0x18002e811  test    dword ptr [rcx+1Ch], 400h
0x18002e818  jz      short loc_18002E84F
0x18002e81a  mov     edx, ebx
0x18002e81c  lea     rcx, aFailedToGetTem; "Failed to get templates SDO in Sdo help"...
0x18002e823  call    WppDbgPrint
0x18002e828  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e82f  lea     r9, aNpssdo; "NPSSDO"
0x18002e836  mov     edx, 27h ; '''
0x18002e83b  mov     dword ptr [rsp+48h+var_28], ebx
0x18002e83f  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002e846  mov     rcx, [rcx+10h]
0x18002e84a  call    WPP_SF_sd
0x18002e84f  lea     rcx, [rsp+48h+arg_0]
0x18002e854  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e859  mov     eax, ebx
0x18002e85b  jmp     loc_18002E94F
0x18002e860  mov     rcx, [rsi+58h]
0x18002e864  lea     r8, [rsp+48h+arg_0]
0x18002e869  lea     rdx, IID_IUnknown
0x18002e870  mov     rax, [rcx]
0x18002e873  mov     rax, [rax]
0x18002e876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e87b  mov     edi, eax
0x18002e87d  test    eax, eax
0x18002e87f  js      short loc_18002E8D1
0x18002e881  mov     rbx, [rsi+50h]
0x18002e885  lea     rdx, aIas; "IAS"
0x18002e88c  lea     rcx, [rsp+48h+arg_18]; this
0x18002e891  mov     rax, [rbx]
0x18002e894  mov     rdi, [rax+90h]
0x18002e89b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002e8a0  mov     rdx, [rax]
0x18002e8a3  test    rdx, rdx
0x18002e8a6  jz      short loc_18002E8AB
0x18002e8a8  mov     rdx, [rdx]
0x18002e8ab  mov     r9, rbp
0x18002e8ae  mov     word ptr [rsp+48h+var_28], 0FFFFh
0x18002e8b5  lea     r8, [rsp+48h+arg_0]
0x18002e8ba  mov     rcx, rbx
0x18002e8bd  mov     rax, rdi
0x18002e8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c5  lea     rcx, [rsp+48h+arg_18]; this
0x18002e8ca  mov     edi, eax
0x18002e8cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e8d1  lea     rcx, [rsp+48h+arg_0]
0x18002e8d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e8db  test    edi, edi
0x18002e8dd  jns     short loc_18002E94D
0x18002e8df  mov     rax, cs:WPP_GLOBAL_Control
0x18002e8e6  lea     rdx, WPP_GLOBAL_Control
0x18002e8ed  cmp     rax, rdx
0x18002e8f0  jz      short loc_18002E94D
0x18002e8f2  cmp     byte ptr [rax+19h], 2
0x18002e8f6  jb      short loc_18002E94D
0x18002e8f8  test    dword ptr [rax+1Ch], 400h
0x18002e8ff  jz      short loc_18002E94D
0x18002e901  test    r14, r14
0x18002e904  lea     rbx, qword_180061188
0x18002e90b  mov     r8d, edi
0x18002e90e  lea     rcx, aImportTemplate_0; "Import templates (%ls) failed. hr = %!h"...
0x18002e915  cmovnz  rbx, r14
0x18002e919  mov     rdx, rbx
0x18002e91c  call    WppDbgPrint
0x18002e921  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e928  lea     r9, aNpssdo; "NPSSDO"
0x18002e92f  mov     edx, 28h ; '('
0x18002e934  mov     [rsp+48h+var_20], edi
0x18002e938  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002e93f  mov     [rsp+48h+var_28], rbx
0x18002e944  mov     rcx, [rcx+10h]
0x18002e948  call    WPP_SF_sSd
0x18002e94d  mov     eax, edi
0x18002e94f  mov     rbx, [rsp+48h+arg_8]
0x18002e954  mov     rbp, [rsp+48h+arg_10]
0x18002e959  add     rsp, 30h
0x18002e95d  pop     r14
0x18002e95f  pop     rdi
0x18002e960  pop     rsi
0x18002e961  retn
```
