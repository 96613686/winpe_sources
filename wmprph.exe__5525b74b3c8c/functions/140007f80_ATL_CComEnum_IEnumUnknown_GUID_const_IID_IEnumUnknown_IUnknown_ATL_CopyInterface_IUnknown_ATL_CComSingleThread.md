# ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>::Reset(void)

- ea: `0x140007f80`
- end: `0x140007f8b`
- name: `?Reset@?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@UEAAJXZ`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>::Reset(
        __int64 a1)
{
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
  return 0;
}

```

## disassembly

```asm
0x140007f80  mov     rax, [rcx+10h]
0x140007f84  mov     [rcx+20h], rax
0x140007f88  xor     eax, eax
0x140007f8a  retn
```
