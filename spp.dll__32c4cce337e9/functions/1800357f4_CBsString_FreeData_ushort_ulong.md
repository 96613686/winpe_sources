# CBsString::_FreeData(ushort *,ulong)

- ea: `0x1800357f4`
- end: `0x18003580f`
- name: `?_FreeData@CBsString@@CAXPEAGK@Z`
- size: `27`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034fe4`
- `0x180035b00`

## callees

- `0x1800357f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035804`

## pseudocode

```c
void __fastcall CBsString::_FreeData(unsigned __int16 *a1)
{
  if ( a1 != &FileName )
    CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x1800357f4  sub     rsp, 28h
0x1800357f8  lea     rax, FileName
0x1800357ff  cmp     rcx, rax
0x180035802  jz      short loc_18003580A
0x180035804  call    cs:__imp_CoTaskMemFree
0x18003580a  add     rsp, 28h
0x18003580e  retn
```
