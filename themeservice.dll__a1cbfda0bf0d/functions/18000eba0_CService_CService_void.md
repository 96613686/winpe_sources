# CService::~CService(void)

- ea: `0x18000eba0`
- end: `0x18000ec42`
- name: `??1CService@@MEAA@XZ`
- size: `162`
- prototype: `void __fastcall(CService *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000ce10`
- `0x18000ec50`

## callees

- `0x180003f90`
- `0x18000e0fc`
- `0x18000eba0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebfd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ec1f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ec1f`

## pseudocode

```c
void __fastcall CService::~CService(CService *this)
{
  CCountedObject *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  SERVICE_STATUS_HANDLE v4; // rcx

  *((_DWORD *)this + 4) = 1145128260;
  *(_QWORD *)this = &CService::`vftable';
  CCountedObject::Release(*((CCountedObject **)this + 11));
  v2 = (CCountedObject *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 11) = 0;
  CCountedObject::Release(v2);
  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
  {
    CAPIDispatchSync::~CAPIDispatchSync(v3);
    HeapFree(s_hHeapToUse, 0, v3);
  }
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 3);
  *((_QWORD *)this + 10) = 0;
  if ( v4 )
  {
    *((_DWORD *)this + 9) = 1;
    SetServiceStatus(v4, (LPSERVICE_STATUS)((char *)this + 32));
    *((_QWORD *)this + 3) = 0;
  }
  *(_QWORD *)this = &CQueueElement::`vftable';
}

```

## disassembly

```asm
0x18000eba0  mov     [rsp+arg_0], rbx
0x18000eba5  push    rdi
0x18000eba6  sub     rsp, 20h
0x18000ebaa  lea     rax, ??_7CService@@6B@; const CService::`vftable'
0x18000ebb1  mov     dword ptr [rcx+10h], 44414544h
0x18000ebb8  mov     [rcx], rax
0x18000ebbb  mov     rbx, rcx
0x18000ebbe  mov     rcx, [rcx+58h]; this
0x18000ebc2  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000ebc7  mov     rcx, [rbx+48h]; this
0x18000ebcb  mov     qword ptr [rbx+58h], 0
0x18000ebd3  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000ebd8  mov     rdi, [rbx+50h]
0x18000ebdc  mov     qword ptr [rbx+48h], 0
0x18000ebe4  test    rdi, rdi
0x18000ebe7  jz      short loc_18000EC03
0x18000ebe9  mov     rcx, rdi; this
0x18000ebec  call    ??1CAPIDispatchSync@@QEAA@XZ; CAPIDispatchSync::~CAPIDispatchSync(void)
0x18000ebf1  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000ebf8  mov     r8, rdi; lpMem
0x18000ebfb  xor     edx, edx; dwFlags
0x18000ebfd  call    cs:__imp_HeapFree
0x18000ec03  mov     rcx, [rbx+18h]; hServiceStatus
0x18000ec07  mov     qword ptr [rbx+50h], 0
0x18000ec0f  test    rcx, rcx
0x18000ec12  jz      short loc_18000EC2D
0x18000ec14  lea     rdx, [rbx+20h]; lpServiceStatus
0x18000ec18  mov     dword ptr [rdx+4], 1
0x18000ec1f  call    cs:__imp_SetServiceStatus
0x18000ec25  mov     qword ptr [rbx+18h], 0
0x18000ec2d  lea     rax, ??_7CQueueElement@@6B@; const CQueueElement::`vftable'
0x18000ec34  mov     [rbx], rax
0x18000ec37  mov     rbx, [rsp+28h+arg_0]
0x18000ec3c  add     rsp, 20h
0x18000ec40  pop     rdi
0x18000ec41  retn
```
