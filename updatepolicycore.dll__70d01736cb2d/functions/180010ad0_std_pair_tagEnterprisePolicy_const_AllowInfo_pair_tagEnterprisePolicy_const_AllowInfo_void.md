# std::pair<tagEnterprisePolicy const,AllowInfo>::~pair<tagEnterprisePolicy const,AllowInfo>(void)

- ea: `0x180010ad0`
- end: `0x180010ad9`
- name: `??1?$pair@$$CBW4tagEnterprisePolicy@@UAllowInfo@@@std@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `83`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180037746`
- `0x18003776a`
- `0x18003778e`
- `0x1800377b2`
- `0x1800377d6`
- `0x1800377fa`
- `0x18003781e`
- `0x180037842`
- `0x180037866`
- `0x18003788a`
- `0x1800378ae`
- `0x1800378d2`
- `0x1800378f6`
- `0x18003791a`
- `0x18003793e`
- `0x180037962`
- `0x180037986`
- `0x1800379aa`
- `0x1800379ce`
- `0x1800379f2`
- `0x180037a16`
- `0x180037a3a`
- `0x180037a5e`
- `0x180037a82`
- `0x180037aa6`
- `0x180037aca`
- `0x180037aee`
- `0x180037b12`
- `0x180037b36`
- `0x180037b5a`
- `0x180037b7e`
- `0x180037ba2`
- `0x180037bc6`
- `0x180037bea`
- `0x180037c0e`
- `0x180037c32`
- `0x180037c56`
- `0x180037c7a`
- `0x180037c9e`
- `0x180037cc2`
- `0x180037ce6`
- `0x180037d0a`
- `0x180037d2e`
- `0x180037d52`
- `0x180037d76`
- `0x180037d9a`
- `0x180037dbe`
- `0x180037de2`
- `0x180037e06`
- `0x180037e2a`

## callees

- `0x180010260`

## pseudocode

```c
void __fastcall std::pair<enum tagEnterprisePolicy const,AllowInfo>::~pair<enum tagEnterprisePolicy const,AllowInfo>(
        _QWORD *a1)
{
  std::wstring::~wstring(a1 + 1);
}

```

## disassembly

```asm
0x180010ad0  add     rcx, 8; void *
0x180010ad4  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
