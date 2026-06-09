# CGroupMap::~CGroupMap(void)

- ea: `0x1800027f8`
- end: `0x180002826`
- name: `??1CGroupMap@@AEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CGroupMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e1c8`

## callees

- `0x1800027f8`
- `0x180007a24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002813`

## pseudocode

```c
void __fastcall CGroupMap::~CGroupMap(CGroupMap *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll();
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800027f8  push    rbx
0x1800027fa  sub     rsp, 20h
0x1800027fe  mov     rbx, rcx
0x180002801  lock inc dword ptr [rcx+8]
0x180002805  cmp     qword ptr [rcx], 0
0x180002809  jz      short loc_180002820
0x18000280b  call    ?DeleteAll@?$CSxRefMap@VCGroupMap@@VCGroupEntry@@@@QEAAXXZ; CSxRefMap<CGroupMap,CGroupEntry>::DeleteAll(void)
0x180002810  mov     rcx, [rbx]; pv
0x180002813  call    cs:__imp_CoTaskMemFree
0x180002819  mov     qword ptr [rbx], 0
0x180002820  add     rsp, 20h
0x180002824  pop     rbx
0x180002825  retn
```
