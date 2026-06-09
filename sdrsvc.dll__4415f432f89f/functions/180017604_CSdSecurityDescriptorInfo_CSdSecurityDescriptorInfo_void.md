# CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo(void)

- ea: `0x180017604`
- end: `0x180017643`
- name: `??1CSdSecurityDescriptorInfo@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(CSdSecurityDescriptorInfo *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016a78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001762f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001762f`

## pseudocode

```c
void __fastcall CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo(CSdSecurityDescriptorInfo *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 2) = 0;
  CoTaskMemFree(*((LPVOID *)this + 4));
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180017604  push    rbx
0x180017606  sub     rsp, 20h
0x18001760a  mov     rbx, rcx
0x18001760d  mov     qword ptr [rcx], 0
0x180017614  mov     qword ptr [rcx+10h], 0
0x18001761c  mov     qword ptr [rcx+18h], 0
0x180017624  mov     dword ptr [rcx+8], 0
0x18001762b  mov     rcx, [rcx+20h]; pv
0x18001762f  call    cs:__imp_CoTaskMemFree
0x180017635  mov     qword ptr [rbx+20h], 0
0x18001763d  add     rsp, 20h
0x180017641  pop     rbx
0x180017642  retn
```
