# GetModificationDateFromElement(IXMLDOMElement *,_FILETIME *)

- ea: `0x180088d50`
- end: `0x180088e79`
- name: `?GetModificationDateFromElement@@YAJPEAUIXMLDOMElement@@PEAU_FILETIME@@@Z`
- size: `297`
- prototype: `int(struct IXMLDOMElement *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18008ca20`

## callees

- `0x180005d08`
- `0x180088d50`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!__imp_StringToSystemTime` at `0x180088e02`
- `MSOERT2!__imp_StringToSystemTime` at `0x180088e02`
- `KERNEL32!SystemTimeToFileTime` at `0x180088e14`
- `KERNEL32!SystemTimeToFileTime` at `0x180088e14`
- `OLEAUT32!__imp_SysAllocString` at `0x180088da4`
- `OLEAUT32!__imp_SysAllocString` at `0x180088da4`
- `OLEAUT32!__imp_SysFreeString` at `0x180088e54`
- `OLEAUT32!__imp_SysFreeString` at `0x180088e54`
- `OLEAUT32!__imp_VariantClear` at `0x180088e37`
- `OLEAUT32!__imp_VariantClear` at `0x180088e37`

## pseudocode

```c

```
