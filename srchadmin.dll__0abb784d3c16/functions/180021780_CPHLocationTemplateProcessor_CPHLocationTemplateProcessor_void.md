# CPHLocationTemplateProcessor::~CPHLocationTemplateProcessor(void)

- ea: `0x180021780`
- end: `0x1800217c7`
- name: `??1CPHLocationTemplateProcessor@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021878`

## callees

- `0x1800214dc`
- `0x180021780`
- `0x18002184c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002179d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002179d`

## pseudocode

```c
void __fastcall CPHLocationTemplateProcessor::~CPHLocationTemplateProcessor(LPVOID *this)
{
  unsigned int v2; // edx
  CLocationTemplate *v3; // rcx

  CoTaskMemFree(this[65]);
  CoTaskMemFree(this[66]);
  SafeRelease<IShellItem>(this + 67);
  v3 = (CLocationTemplate *)this[68];
  if ( v3 )
    CLocationTemplate::`scalar deleting destructor'(v3, v2);
}

```

## disassembly

```asm
0x180021780  push    rbx
0x180021782  sub     rsp, 20h
0x180021786  mov     rbx, rcx
0x180021789  mov     rcx, [rcx+208h]; pv
0x180021790  call    cs:__imp_CoTaskMemFree
0x180021796  mov     rcx, [rbx+210h]; pv
0x18002179d  call    cs:__imp_CoTaskMemFree
0x1800217a3  lea     rcx, [rbx+218h]
0x1800217aa  call    ??$SafeRelease@UIShellItem@@@@YAXPEAPEAUIShellItem@@@Z; SafeRelease<IShellItem>(IShellItem * *)
0x1800217af  mov     rcx, [rbx+220h]; this
0x1800217b6  test    rcx, rcx
0x1800217b9  jz      short loc_1800217C1
0x1800217bb  call    ??_GCLocationTemplate@@QEAAPEAXI@Z; CLocationTemplate::`scalar deleting destructor'(uint)
0x1800217c0  nop
0x1800217c1  add     rsp, 20h
0x1800217c5  pop     rbx
0x1800217c6  retn
```
