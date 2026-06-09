# AsrSystem::~AsrSystem(void)

- ea: `0x1400d5c90`
- end: `0x1400d5d55`
- name: `??1AsrSystem@@QEAA@XZ`
- size: `197`
- prototype: `void __fastcall(AsrSystem *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14006168c`
- `0x1400e5d12`

## callees

- `0x1400d5c90`
- `0x1400d6d0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d5d3c`

## pseudocode

```c
void __fastcall AsrSystem::~AsrSystem(AsrSystem *this)
{
  LPVOID *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  struct _ASR_DISK_INFO *v7; // rcx
  void *v8; // rcx

  DiskListCleanup((struct _ASR_DISK_INFO **)this + 2);
  DiskListCleanup((struct _ASR_DISK_INFO **)this + 3);
  v2 = (LPVOID *)((char *)this + 32);
  if ( this != (AsrSystem *)-32LL )
  {
    CoTaskMemFree(*v2);
    v3 = (void *)*((_QWORD *)this + 5);
    *v2 = 0;
    CoTaskMemFree(v3);
    v4 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 5) = 0;
    CoTaskMemFree(v4);
    v5 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 6) = 0;
    CoTaskMemFree(v5);
    v6 = (void *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 7) = 0;
    CoTaskMemFree(v6);
    *((_QWORD *)this + 9) = 0;
  }
  CoTaskMemFree(*((LPVOID *)this + 72));
  v7 = *(struct _ASR_DISK_INFO **)this;
  *((_QWORD *)this + 72) = 0;
  CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = 0;
  CoTaskMemFree(v8);
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x1400d5c90  mov     [rsp+arg_0], rbx
0x1400d5c95  push    rdi
0x1400d5c96  sub     rsp, 20h
0x1400d5c9a  mov     rbx, rcx
0x1400d5c9d  add     rcx, 10h; struct _ASR_DISK_INFO **
0x1400d5ca1  call    ?DiskListCleanup@@YAXPEAPEAU_ASR_DISK_INFO@@@Z; DiskListCleanup(_ASR_DISK_INFO * *)
0x1400d5ca6  lea     rcx, [rbx+18h]; struct _ASR_DISK_INFO **
0x1400d5caa  call    ?DiskListCleanup@@YAXPEAPEAU_ASR_DISK_INFO@@@Z; DiskListCleanup(_ASR_DISK_INFO * *)
0x1400d5caf  lea     rdi, [rbx+20h]
0x1400d5cb3  test    rdi, rdi
0x1400d5cb6  jz      short loc_1400D5D10
0x1400d5cb8  mov     rcx, [rdi]; pv
0x1400d5cbb  call    cs:__imp_CoTaskMemFree
0x1400d5cc1  mov     rcx, [rdi+8]; pv
0x1400d5cc5  mov     qword ptr [rdi], 0
0x1400d5ccc  call    cs:__imp_CoTaskMemFree
0x1400d5cd2  mov     rcx, [rdi+10h]; pv
0x1400d5cd6  mov     qword ptr [rdi+8], 0
0x1400d5cde  call    cs:__imp_CoTaskMemFree
0x1400d5ce4  mov     rcx, [rdi+18h]; pv
0x1400d5ce8  mov     qword ptr [rdi+10h], 0
0x1400d5cf0  call    cs:__imp_CoTaskMemFree
0x1400d5cf6  mov     rcx, [rdi+28h]; pv
0x1400d5cfa  mov     qword ptr [rdi+18h], 0
0x1400d5d02  call    cs:__imp_CoTaskMemFree
0x1400d5d08  mov     qword ptr [rdi+28h], 0
0x1400d5d10  mov     rcx, [rbx+240h]; pv
0x1400d5d17  call    cs:__imp_CoTaskMemFree
0x1400d5d1d  mov     rcx, [rbx]; pv
0x1400d5d20  mov     qword ptr [rbx+240h], 0
0x1400d5d2b  call    cs:__imp_CoTaskMemFree
0x1400d5d31  mov     rcx, [rbx+8]; pv
0x1400d5d35  mov     qword ptr [rbx], 0
0x1400d5d3c  call    cs:__imp_CoTaskMemFree
0x1400d5d42  mov     qword ptr [rbx+8], 0
0x1400d5d4a  mov     rbx, [rsp+28h+arg_0]
0x1400d5d4f  add     rsp, 20h
0x1400d5d53  pop     rdi
0x1400d5d54  retn
```
