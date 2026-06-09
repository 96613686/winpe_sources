# ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>(void)

- ea: `0x180011dec`
- end: `0x180011dfe`
- name: `??1?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@QEAA@XZ`
- size: `18`
- prototype: `void __fastcall(CFciPropertiesShellExt *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e58c`
- `0x18001e77c`

## callees

- `0x18000505c`

## pseudocode

```c
void __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>(
        CFciPropertiesShellExt *a1)
{
  CFciPropertiesShellExt::~CFciPropertiesShellExt(a1);
}

```

## disassembly

```asm
0x180011dec  mov     [rsp+arg_0], rcx
0x180011df1  sub     rsp, 28h
0x180011df5  add     rsp, 28h
0x180011df9  jmp     ??1CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::~CFciPropertiesShellExt(void)
```
