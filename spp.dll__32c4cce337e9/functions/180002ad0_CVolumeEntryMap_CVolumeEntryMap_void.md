# CVolumeEntryMap::~CVolumeEntryMap(void)

- ea: `0x180002ad0`
- end: `0x180002afe`
- name: `??1CVolumeEntryMap@@AEAA@XZ`
- size: `46`
- prototype: `void __fastcall(CVolumeEntryMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e48c`

## callees

- `0x180002ad0`
- `0x180007a74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aeb`

## pseudocode

```c
void __fastcall CVolumeEntryMap::~CVolumeEntryMap(CVolumeEntryMap *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll();
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180002ad0  push    rbx
0x180002ad2  sub     rsp, 20h
0x180002ad6  mov     rbx, rcx
0x180002ad9  lock inc dword ptr [rcx+8]
0x180002add  cmp     qword ptr [rcx], 0
0x180002ae1  jz      short loc_180002AF8
0x180002ae3  call    ?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)
0x180002ae8  mov     rcx, [rbx]; pv
0x180002aeb  call    cs:__imp_CoTaskMemFree
0x180002af1  mov     qword ptr [rbx], 0
0x180002af8  add     rsp, 20h
0x180002afc  pop     rbx
0x180002afd  retn
```
