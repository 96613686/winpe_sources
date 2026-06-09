# CFciConfigObject::LoadFromStore(ushort const *,ushort const *,ulong,CFG_ATTRIB_ASSOC const *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180032eb8`
- end: `0x1800333ce`
- name: `?LoadFromStore@CFciConfigObject@@KAXPEBG0KPEBUCFG_ATTRIB_ASSOC@@PEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1302`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *Src@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, service_task`

## callers

- `0x180022fac`
- `0x18002aba8`
- `0x1800383dc`
- `0x180038704`

## callees

- `0x180001350`
- `0x18000266c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000a1c8`
- `0x18000fd74`
- `0x1800101e8`
- `0x180026124`
- `0x1800325e4`
- `0x180032eb8`
- `0x180033f34`
- `0x1800350f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180033021`
- `KERNEL32!GetSystemTime` at `0x180033041`
- `KERNEL32!GetSystemTime` at `0x180033021`
- `KERNEL32!GetSystemTime` at `0x180033041`

## string_xrefs

- `0x180032efb`: `base\fs\fsrm\service\globalstore\fciconfigobject.cpp`
- `0x180032f07`: `CFciConfigObject::LoadFromStore`

## pseudocode

```c

```
