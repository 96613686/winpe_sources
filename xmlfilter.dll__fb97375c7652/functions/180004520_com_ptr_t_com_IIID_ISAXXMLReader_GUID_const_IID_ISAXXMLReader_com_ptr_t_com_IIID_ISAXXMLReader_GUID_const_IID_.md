# _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>(void)

- ea: `0x180004520`
- end: `0x18000453e`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UISAXXMLReader@@$1?IID_ISAXXMLReader@@3U_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001500c`
- `0x180015581`

## callees

- `0x180004520`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>::~_com_ptr_t<_com_IIID<ISAXXMLReader,&_GUID const IID_ISAXXMLReader>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180004520  sub     rsp, 28h
0x180004524  mov     rcx, [rcx]
0x180004527  test    rcx, rcx
0x18000452a  jz      short loc_180004539
0x18000452c  mov     rax, [rcx]
0x18000452f  mov     rax, [rax+10h]
0x180004533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004538  nop
0x180004539  add     rsp, 28h
0x18000453d  retn
```
