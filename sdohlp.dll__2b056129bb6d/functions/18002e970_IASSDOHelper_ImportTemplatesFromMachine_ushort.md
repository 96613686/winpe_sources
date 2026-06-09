# IASSDOHelper::ImportTemplatesFromMachine(ushort *)

- ea: `0x18002e970`
- end: `0x18002eab0`
- name: `?ImportTemplatesFromMachine@IASSDOHelper@@UEAAJPEAG@Z`
- size: `320`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x18002d08c`
- `0x18002e970`
- `0x18002efa0`
- `0x18002f08c`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18002ea61`: `Import templates from machine (%ls) failed. hr = %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::ImportTemplatesFromMachine(IASSDOHelper *this, unsigned __int16 *a2)
{
  char *v4; // r14
  int v5; // edi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD *, __int64 *, char *, __int16); // rdi
  _QWORD *v9; // rdx
  __int64 *v10; // rbx
  __int16 v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+28h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  char v15; // [rsp+60h] [rbp+18h] BYREF

  v4 = (char *)this + 96;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 10) + 152LL))(
         *((_QWORD *)this + 10),
         *((_QWORD *)this + 12),
         a2);
  if ( v5 < 0 )
    goto LABEL_9;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 11);
  v14 = 0;
  v5 = (**v6)(v6, &IID_IUnknown, &v14);
  if ( v5 >= 0 )
  {
    v7 = *((_QWORD *)this + 10);
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *, char *, __int16))(*(_QWORD *)v7 + 144LL);
    v9 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v15, L"IAS");
    if ( v9 )
      v9 = (_QWORD *)*v9;
    v12 = -1;
    v5 = v8(v7, v9, &v14, v4, v12);
    _bstr_t::_Free((_bstr_t *)&v15);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  if ( v5 < 0 )
  {
LABEL_9:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v10 = &qword_180061188;
      if ( a2 )
        v10 = (__int64 *)a2;
      WppDbgPrint("Import templates from machine (%ls) failed. hr = %!hresult!");
      v13 = v5;
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)v10,
        v13);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002e970  mov     [rsp+arg_8], rbx
0x18002e975  push    rsi
0x18002e976  push    rdi
0x18002e977  push    r14
0x18002e979  sub     rsp, 30h
0x18002e97d  mov     rbx, rcx
0x18002e980  mov     rsi, rdx
0x18002e983  mov     rcx, [rcx+50h]
0x18002e987  mov     r8, rdx
0x18002e98a  lea     r14, [rbx+60h]
0x18002e98e  mov     rax, [rcx]
0x18002e991  mov     rdx, [r14]
0x18002e994  mov     rax, [rax+98h]
0x18002e99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9a0  mov     edi, eax
0x18002e9a2  test    eax, eax
0x18002e9a4  js      loc_18002EA32
0x18002e9aa  mov     rcx, [rbx+58h]
0x18002e9ae  lea     r8, [rsp+48h+arg_0]
0x18002e9b3  mov     [rsp+48h+arg_0], 0
0x18002e9bc  lea     rdx, IID_IUnknown
0x18002e9c3  mov     rax, [rcx]
0x18002e9c6  mov     rax, [rax]
0x18002e9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9ce  mov     edi, eax
0x18002e9d0  test    eax, eax
0x18002e9d2  js      short loc_18002EA24
0x18002e9d4  mov     rbx, [rbx+50h]
0x18002e9d8  lea     rdx, aIas; "IAS"
0x18002e9df  lea     rcx, [rsp+48h+arg_10]; this
0x18002e9e4  mov     rax, [rbx]
0x18002e9e7  mov     rdi, [rax+90h]
0x18002e9ee  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002e9f3  mov     rdx, [rax]
0x18002e9f6  test    rdx, rdx
0x18002e9f9  jz      short loc_18002E9FE
0x18002e9fb  mov     rdx, [rdx]
0x18002e9fe  mov     r9, r14
0x18002ea01  mov     word ptr [rsp+48h+var_28], 0FFFFh
0x18002ea08  lea     r8, [rsp+48h+arg_0]
0x18002ea0d  mov     rcx, rbx
0x18002ea10  mov     rax, rdi
0x18002ea13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea18  lea     rcx, [rsp+48h+arg_10]; this
0x18002ea1d  mov     edi, eax
0x18002ea1f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002ea24  lea     rcx, [rsp+48h+arg_0]
0x18002ea29  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ea2e  test    edi, edi
0x18002ea30  jns     short loc_18002EAA0
0x18002ea32  mov     rax, cs:WPP_GLOBAL_Control
0x18002ea39  lea     rcx, WPP_GLOBAL_Control
0x18002ea40  cmp     rax, rcx
0x18002ea43  jz      short loc_18002EAA0
0x18002ea45  cmp     byte ptr [rax+19h], 2
0x18002ea49  jb      short loc_18002EAA0
0x18002ea4b  test    dword ptr [rax+1Ch], 400h
0x18002ea52  jz      short loc_18002EAA0
0x18002ea54  test    rsi, rsi
0x18002ea57  lea     rbx, qword_180061188
0x18002ea5e  mov     r8d, edi
0x18002ea61  lea     rcx, aImportTemplate; "Import templates from machine (%ls) fai"...
0x18002ea68  cmovnz  rbx, rsi
0x18002ea6c  mov     rdx, rbx
0x18002ea6f  call    WppDbgPrint
0x18002ea74  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea7b  lea     r9, aNpssdo; "NPSSDO"
0x18002ea82  mov     edx, 29h ; ')'
0x18002ea87  mov     [rsp+48h+var_20], edi
0x18002ea8b  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002ea92  mov     [rsp+48h+var_28], rbx
0x18002ea97  mov     rcx, [rcx+10h]
0x18002ea9b  call    WPP_SF_sSd
0x18002eaa0  mov     rbx, [rsp+48h+arg_8]
0x18002eaa5  mov     eax, edi
0x18002eaa7  add     rsp, 30h
0x18002eaab  pop     r14
0x18002eaad  pop     rdi
0x18002eaae  pop     rsi
0x18002eaaf  retn
```
