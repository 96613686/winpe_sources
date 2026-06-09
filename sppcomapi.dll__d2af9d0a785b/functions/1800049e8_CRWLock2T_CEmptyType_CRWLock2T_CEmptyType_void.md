# CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(void)

- ea: `0x1800049e8`
- end: `0x180004a71`
- name: `??1?$CRWLock2T@VCEmptyType@@@@QEAA@XZ`
- size: `137`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180004950`
- `0x180019db0`
- `0x180019e48`
- `0x180019ee0`
- `0x180019f78`
- `0x18001a010`
- `0x18001e3c8`
- `0x18001e460`

## callees

- `0x180003838`
- `0x1800049e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a51`

## pseudocode

```c
int __fastcall CRWLock2T<CEmptyType>::~CRWLock2T<CEmptyType>(_QWORD *a1)
{
  int result; // eax
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  void *v5; // rcx
  void *v6; // rcx

  result = CRWLock2T<CEmptyType>::Done((__int64)a1);
  v3 = (void *)a1[11];
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    result = HeapFree(ProcessHeap, 0, v3);
    a1[11] = 0;
  }
  v5 = (void *)a1[7];
  if ( v5 )
  {
    result = CloseHandle(v5);
    a1[7] = 0;
  }
  v6 = (void *)a1[6];
  if ( v6 )
  {
    result = CloseHandle(v6);
    a1[6] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800049e8  mov     [rsp+arg_0], rbx
0x1800049ed  push    rdi
0x1800049ee  sub     rsp, 20h
0x1800049f2  mov     rbx, rcx
0x1800049f5  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x1800049fa  mov     rdi, [rbx+58h]
0x1800049fe  test    rdi, rdi
0x180004a01  jz      short loc_180004A2B
0x180004a03  call    cs:__imp_GetProcessHeap
0x180004a0a  nop     dword ptr [rax+rax+00h]
0x180004a0f  mov     r8, rdi; lpMem
0x180004a12  xor     edx, edx; dwFlags
0x180004a14  mov     rcx, rax; hHeap
0x180004a17  call    cs:__imp_HeapFree
0x180004a1e  nop     dword ptr [rax+rax+00h]
0x180004a23  mov     qword ptr [rbx+58h], 0
0x180004a2b  mov     rcx, [rbx+38h]; hObject
0x180004a2f  test    rcx, rcx
0x180004a32  jz      short loc_180004A48
0x180004a34  call    cs:__imp_CloseHandle
0x180004a3b  nop     dword ptr [rax+rax+00h]
0x180004a40  mov     qword ptr [rbx+38h], 0
0x180004a48  mov     rcx, [rbx+30h]; hObject
0x180004a4c  test    rcx, rcx
0x180004a4f  jz      short loc_180004A65
0x180004a51  call    cs:__imp_CloseHandle
0x180004a58  nop     dword ptr [rax+rax+00h]
0x180004a5d  mov     qword ptr [rbx+30h], 0
0x180004a65  mov     rbx, [rsp+28h+arg_0]
0x180004a6a  add     rsp, 20h
0x180004a6e  pop     rdi
0x180004a6f  retn
```
