# ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>(void)

- ea: `0x140002014`
- end: `0x140002078`
- name: `??1?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14000310c`
- `0x140004360`
- `0x1400079c0`

## callees

- `0x140001008`
- `0x140002014`
- `0x14000f010`

## pseudocode

```c
void __fastcall ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>(
        __int64 a1)
{
  _QWORD *i; // rdi
  __int64 v3; // rcx

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(_QWORD **)(a1 + 16); i != *(_QWORD **)(a1 + 24); ++i )
    {
      if ( *i )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
    }
    operator delete(*(void **)(a1 + 16));
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x140002014  mov     [rsp+arg_0], rbx
0x140002019  push    rdi
0x14000201a  sub     rsp, 20h
0x14000201e  test    byte ptr [rcx+28h], 2
0x140002022  mov     rbx, rcx
0x140002025  jz      short loc_140002058
0x140002027  mov     rdi, [rcx+10h]
0x14000202b  cmp     rdi, [rcx+18h]
0x14000202f  jz      short loc_14000204F
0x140002031  mov     rcx, [rdi]
0x140002034  test    rcx, rcx
0x140002037  jz      short loc_140002045
0x140002039  mov     rax, [rcx]
0x14000203c  mov     rax, [rax+10h]
0x140002040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002045  add     rdi, 8
0x140002049  cmp     rdi, [rbx+18h]
0x14000204d  jnz     short loc_140002031
0x14000204f  mov     rcx, [rbx+10h]; void *
0x140002053  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002058  mov     rcx, [rbx+8]
0x14000205c  test    rcx, rcx
0x14000205f  jz      short loc_14000206D
0x140002061  mov     rax, [rcx]
0x140002064  mov     rax, [rax+10h]
0x140002068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000206d  mov     rbx, [rsp+28h+arg_0]
0x140002072  add     rsp, 20h
0x140002076  pop     rdi
0x140002077  retn
```
