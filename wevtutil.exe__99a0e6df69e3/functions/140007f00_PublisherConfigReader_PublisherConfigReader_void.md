# PublisherConfigReader::~PublisherConfigReader(void)

- ea: `0x140007f00`
- end: `0x140007fbb`
- name: `??1PublisherConfigReader@@QEAA@XZ`
- size: `187`
- prototype: `void __fastcall(PublisherConfigReader *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140017fbc`
- `0x14001e0c0`
- `0x14002ef94`
- `0x140032abe`
- `0x140032d63`
- `0x140033808`

## callees

- `0x140007f00`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007f98`

## pseudocode

```c
void __fastcall PublisherConfigReader::~PublisherConfigReader(PublisherConfigReader *this)
{
  char *v1; // rdi
  HANDLE ProcessHeap; // rax
  char *v4; // rdi
  HANDLE v5; // rax
  char *v6; // rdi
  HANDLE v7; // rax
  __int64 v8; // rcx

  v1 = (char *)*((_QWORD *)this + 13);
  if ( v1 != (char *)this + 120 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (char *)*((_QWORD *)this + 9);
  if ( v4 != (char *)this + 88 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (char *)*((_QWORD *)this + 5);
  if ( v6 != (char *)this + 56 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  v8 = *((_QWORD *)this + 4);
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
  *((_QWORD *)this + 4) = 0;
  if ( *(_QWORD *)this )
    RegCloseKey(*(HKEY *)this);
}

```

## disassembly

```asm
0x140007f00  mov     [rsp+arg_8], rbx
0x140007f05  push    rdi
0x140007f06  sub     rsp, 20h
0x140007f0a  mov     rdi, [rcx+68h]
0x140007f0e  lea     rax, [rcx+78h]
0x140007f12  mov     rbx, rcx
0x140007f15  cmp     rdi, rax
0x140007f18  jz      short loc_140007F2E
0x140007f1a  call    cs:__imp_GetProcessHeap
0x140007f20  mov     r8, rdi; lpMem
0x140007f23  xor     edx, edx; dwFlags
0x140007f25  mov     rcx, rax; hHeap
0x140007f28  call    cs:__imp_HeapFree
0x140007f2e  mov     rdi, [rbx+48h]
0x140007f32  lea     rax, [rbx+58h]
0x140007f36  cmp     rdi, rax
0x140007f39  jz      short loc_140007F4F
0x140007f3b  call    cs:__imp_GetProcessHeap
0x140007f41  mov     r8, rdi; lpMem
0x140007f44  xor     edx, edx; dwFlags
0x140007f46  mov     rcx, rax; hHeap
0x140007f49  call    cs:__imp_HeapFree
0x140007f4f  mov     rdi, [rbx+28h]
0x140007f53  lea     rax, [rbx+38h]
0x140007f57  cmp     rdi, rax
0x140007f5a  jz      short loc_140007F70
0x140007f5c  call    cs:__imp_GetProcessHeap
0x140007f62  mov     r8, rdi; lpMem
0x140007f65  xor     edx, edx; dwFlags
0x140007f67  mov     rcx, rax; hHeap
0x140007f6a  call    cs:__imp_HeapFree
0x140007f70  mov     rcx, [rbx+20h]
0x140007f74  test    rcx, rcx
0x140007f77  jz      short loc_140007F88
0x140007f79  mov     eax, 0FFFFFFFFh
0x140007f7e  lock xadd [rcx+8], eax
0x140007f83  cmp     eax, 1
0x140007f86  jz      short loc_140007FA9
0x140007f88  mov     qword ptr [rbx+20h], 0
0x140007f90  mov     rcx, [rbx]; hKey
0x140007f93  test    rcx, rcx
0x140007f96  jz      short loc_140007F9E
0x140007f98  call    cs:__imp_RegCloseKey
0x140007f9e  mov     rbx, [rsp+28h+arg_8]
0x140007fa3  add     rsp, 20h
0x140007fa7  pop     rdi
0x140007fa8  retn
0x140007fa9  mov     rax, [rcx]
0x140007fac  mov     edx, 1
0x140007fb1  mov     rax, [rax]
0x140007fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fb9  jmp     short loc_140007F88
```
