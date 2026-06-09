# BWCContentProviderConfiguration::~BWCContentProviderConfiguration(void)

- ea: `0x18000f9f0`
- end: `0x18000fa81`
- name: `??1BWCContentProviderConfiguration@@UEAA@XZ`
- size: `145`
- prototype: `void __fastcall(BWCContentProviderConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fa90`

## callees

- `0x18000f9f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fa68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fa5a`

## pseudocode

```c
void __fastcall BWCContentProviderConfiguration::~BWCContentProviderConfiguration(
        BWCContentProviderConfiguration *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = &BWCContentProviderConfiguration::`vftable';
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x18000f9f0  mov     [rsp+arg_0], rbx
0x18000f9f5  push    rdi
0x18000f9f6  sub     rsp, 20h
0x18000f9fa  mov     rdi, [rcx+8]
0x18000f9fe  lea     rax, ??_7BWCContentProviderConfiguration@@6B@; const BWCContentProviderConfiguration::`vftable'
0x18000fa05  mov     [rcx], rax
0x18000fa08  mov     rbx, rcx
0x18000fa0b  test    rdi, rdi
0x18000fa0e  jz      short loc_18000FA2C
0x18000fa10  call    cs:__imp_GetProcessHeap
0x18000fa16  mov     r8, rdi; lpMem
0x18000fa19  xor     edx, edx; dwFlags
0x18000fa1b  mov     rcx, rax; hHeap
0x18000fa1e  call    cs:__imp_HeapFree
0x18000fa24  mov     qword ptr [rbx+8], 0
0x18000fa2c  mov     rdi, [rbx+10h]
0x18000fa30  test    rdi, rdi
0x18000fa33  jz      short loc_18000FA51
0x18000fa35  call    cs:__imp_GetProcessHeap
0x18000fa3b  mov     r8, rdi; lpMem
0x18000fa3e  xor     edx, edx; dwFlags
0x18000fa40  mov     rcx, rax; hHeap
0x18000fa43  call    cs:__imp_HeapFree
0x18000fa49  mov     qword ptr [rbx+10h], 0
0x18000fa51  mov     rdi, [rbx+18h]
0x18000fa55  test    rdi, rdi
0x18000fa58  jz      short loc_18000FA76
0x18000fa5a  call    cs:__imp_GetProcessHeap
0x18000fa60  mov     r8, rdi; lpMem
0x18000fa63  xor     edx, edx; dwFlags
0x18000fa65  mov     rcx, rax; hHeap
0x18000fa68  call    cs:__imp_HeapFree
0x18000fa6e  mov     qword ptr [rbx+18h], 0
0x18000fa76  mov     rbx, [rsp+28h+arg_0]
0x18000fa7b  add     rsp, 20h
0x18000fa7f  pop     rdi
0x18000fa80  retn
```
