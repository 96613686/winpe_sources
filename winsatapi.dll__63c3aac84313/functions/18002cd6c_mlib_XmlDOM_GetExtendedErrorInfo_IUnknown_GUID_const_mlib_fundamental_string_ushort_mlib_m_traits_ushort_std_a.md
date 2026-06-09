# mlib::XmlDOM::GetExtendedErrorInfo(IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002cd6c`
- end: `0x18002ce4b`
- name: `?GetExtendedErrorInfo@XmlDOM@mlib@@CAXPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000782c`

## callees

- `0x180001a34`
- `0x18000305c`
- `0x18000a770`
- `0x18002cd6c`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002ce2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce2e`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002cdf1`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002cdf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall mlib::XmlDOM::GetExtendedErrorInfo(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        unsigned __int64 **a3)
{
  int v6; // eax
  __int64 v7; // r8
  IErrorInfo *pperrinfo[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  pperrinfo[1] = (IErrorInfo *)-2LL;
  pperrinfo[0] = 0;
  bstrString = 0;
  v10 = 0;
  if ( a3 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)a3);
    v6 = (**a1)(a1, &GUID_df0b3d60_548f_101b_8e65_08002b2bd119, &v10);
    if ( v10 )
    {
      if ( v6 >= 0
        && (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, a2) >= 0
        && GetErrorInfo(0, pperrinfo) >= 0
        && ((int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo[0]->lpVtbl->GetDescription)(pperrinfo[0], &bstrString) >= 0 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
          a3,
          (char *)bstrString,
          v7);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  SysFreeString(bstrString);
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)pperrinfo);
}

```

## disassembly

```asm
0x18002cd6c  push    rbp
0x18002cd6e  push    rsi
0x18002cd6f  push    rdi
0x18002cd70  mov     rbp, rsp
0x18002cd73  sub     rsp, 30h
0x18002cd77  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18002cd7f  mov     [rsp+30h+arg_0], rbx
0x18002cd84  mov     rbx, r8
0x18002cd87  mov     rsi, rdx
0x18002cd8a  mov     rdi, rcx
0x18002cd8d  mov     [rbp+pperrinfo], 0
0x18002cd95  mov     [rbp+bstrString], 0
0x18002cd9d  mov     [rbp+arg_10], 0
0x18002cda5  test    r8, r8
0x18002cda8  jz      short loc_18002CE20
0x18002cdaa  mov     rcx, rbx
0x18002cdad  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18002cdb2  mov     rax, [rdi]
0x18002cdb5  lea     r8, [rbp+arg_10]
0x18002cdb9  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x18002cdc0  mov     rcx, rdi
0x18002cdc3  mov     rax, [rax]
0x18002cdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdcb  mov     rcx, [rbp+arg_10]
0x18002cdcf  test    rcx, rcx
0x18002cdd2  jz      short loc_18002CE20
0x18002cdd4  test    eax, eax
0x18002cdd6  js      short loc_18002CE20
0x18002cdd8  mov     rax, [rcx]
0x18002cddb  mov     rdx, rsi
0x18002cdde  mov     rax, [rax+18h]
0x18002cde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cde7  test    eax, eax
0x18002cde9  js      short loc_18002CE20
0x18002cdeb  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002cdef  xor     ecx, ecx; dwReserved
0x18002cdf1  call    cs:__imp_GetErrorInfo
0x18002cdf7  test    eax, eax
0x18002cdf9  js      short loc_18002CE20
0x18002cdfb  mov     rcx, [rbp+pperrinfo]
0x18002cdff  mov     rax, [rcx]
0x18002ce02  lea     rdx, [rbp+bstrString]
0x18002ce06  mov     rax, [rax+28h]
0x18002ce0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce0f  test    eax, eax
0x18002ce11  js      short loc_18002CE20
0x18002ce13  mov     rdx, [rbp+bstrString]
0x18002ce17  mov     rcx, rbx
0x18002ce1a  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18002ce1f  nop
0x18002ce20  lea     rcx, [rbp+arg_10]
0x18002ce24  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ce29  nop
0x18002ce2a  mov     rcx, [rbp+bstrString]; bstrString
0x18002ce2e  call    cs:__imp_SysFreeString
0x18002ce34  nop
0x18002ce35  lea     rcx, [rbp+pperrinfo]
0x18002ce39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ce3e  mov     rbx, [rsp+30h+arg_0]
0x18002ce43  add     rsp, 30h
0x18002ce47  pop     rdi
0x18002ce48  pop     rsi
0x18002ce49  pop     rbp
0x18002ce4a  retn
```
