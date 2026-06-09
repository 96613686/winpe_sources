# ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::AddRef(void)

- ea: `0x140002a80`
- end: `0x140002a93`
- name: `?AddRef@?$CComObject@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002a80`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::AddRef(
        __int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 48);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 48) = result;
  }
  return result;
}

```

## disassembly

```asm
0x140002a80  mov     edx, [rcx+30h]
0x140002a83  mov     eax, 7FFFFFFFh
0x140002a88  cmp     edx, eax
0x140002a8a  jz      short locret_140002A92
0x140002a8c  lea     eax, [rdx+1]
0x140002a8f  mov     [rcx+30h], eax
0x140002a92  retn
```
