# ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180017de0`
- end: `0x180017e40`
- name: `?GetTypeInfo@?$IDispatchImpl@UIAccessible@@$1?IID_IAccessible@@3U_GUID@@B$1?LIBID_Accessibility@@3U3@B$00$00VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001795c`
- `0x180017de0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IAccessible,&_GUID const IID_IAccessible,&_GUID const LIBID_Accessibility,1,1,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  __int64 result; // rax
  struct ITypeInfo *v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_180025078;
  result = 0;
  if ( !qword_180025078 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(0, a3);
    v6 = qword_180025078;
  }
  *a4 = v6;
  if ( qword_180025078 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_180025078->lpVtbl->AddRef)(qword_180025078);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180017de0  push    rbx
0x180017de2  sub     rsp, 20h
0x180017de6  mov     rbx, r9
0x180017de9  test    edx, edx
0x180017deb  jz      short loc_180017DF4
0x180017ded  mov     eax, 8002000Bh
0x180017df2  jmp     short loc_180017E3A
0x180017df4  test    rbx, rbx
0x180017df7  jnz     short loc_180017E00
0x180017df9  mov     eax, 80004003h
0x180017dfe  jmp     short loc_180017E3A
0x180017e00  mov     rcx, cs:qword_180025078; this
0x180017e07  xor     eax, eax
0x180017e09  test    rcx, rcx
0x180017e0c  jnz     short loc_180017E1D
0x180017e0e  mov     edx, r8d; unsigned int
0x180017e11  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180017e16  mov     rcx, cs:qword_180025078
0x180017e1d  mov     [rbx], rcx
0x180017e20  mov     rcx, cs:qword_180025078
0x180017e27  test    rcx, rcx
0x180017e2a  jz      short loc_180017E3A
0x180017e2c  mov     rax, [rcx]
0x180017e2f  mov     rax, [rax+8]
0x180017e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e38  xor     eax, eax
0x180017e3a  add     rsp, 20h
0x180017e3e  pop     rbx
0x180017e3f  retn
```
