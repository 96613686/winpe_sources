# ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180017e80`
- end: `0x180017efd`
- name: `?Invoke@?$IDispatchImpl@UIAccessible@@$1?IID_IAccessible@@3U_GUID@@B$1?LIBID_Accessibility@@3U3@B$00$00VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180016da4`
- `0x180017e80`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::Invoke(
        ATL::CComTypeInfoHolder *a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 result; // rax

  result = ATL::CComTypeInfoHolder::EnsureTI(a1, a4);
  if ( qword_180025078 )
    return ((__int64 (__fastcall *)(struct ITypeInfo *, ATL::CComTypeInfoHolder *, _QWORD, _QWORD, __int64, __int64, __int64, __int64))qword_180025078->lpVtbl->Invoke)(
             qword_180025078,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x180017e80  mov     [rsp+arg_0], rbx
0x180017e85  push    rdi
0x180017e86  sub     rsp, 50h
0x180017e8a  mov     ebx, edx
0x180017e8c  mov     rdi, rcx
0x180017e8f  mov     edx, r9d; unsigned int
0x180017e92  call    ?EnsureTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::EnsureTI(ulong)
0x180017e97  mov     rcx, cs:qword_180025078
0x180017e9e  test    rcx, rcx
0x180017ea1  jz      short loc_180017EF2
0x180017ea3  mov     r8, [rsp+58h+arg_40]
0x180017eab  mov     rdx, [rsp+58h+arg_38]
0x180017eb3  mov     rax, [rcx]
0x180017eb6  movzx   r9d, [rsp+58h+arg_20]
0x180017ebf  mov     [rsp+58h+var_20], r8
0x180017ec4  mov     r8d, ebx
0x180017ec7  mov     [rsp+58h+var_28], rdx
0x180017ecc  mov     rdx, [rsp+58h+arg_30]
0x180017ed4  mov     rax, [rax+58h]
0x180017ed8  mov     [rsp+58h+var_30], rdx
0x180017edd  mov     rdx, [rsp+58h+arg_28]
0x180017ee5  mov     [rsp+58h+var_38], rdx
0x180017eea  mov     rdx, rdi
0x180017eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ef2  mov     rbx, [rsp+58h+arg_0]
0x180017ef7  add     rsp, 50h
0x180017efb  pop     rdi
0x180017efc  retn
```
