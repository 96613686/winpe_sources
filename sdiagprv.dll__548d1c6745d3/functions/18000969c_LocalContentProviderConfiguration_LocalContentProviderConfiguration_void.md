# LocalContentProviderConfiguration::~LocalContentProviderConfiguration(void)

- ea: `0x18000969c`
- end: `0x1800096e3`
- name: `??1LocalContentProviderConfiguration@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(LocalContentProviderConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800096f0`

## callees

- `0x18000969c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096bc`

## pseudocode

```c
void __fastcall LocalContentProviderConfiguration::~LocalContentProviderConfiguration(
        LocalContentProviderConfiguration *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = &LocalContentProviderConfiguration::`vftable';
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000969c  mov     [rsp+arg_0], rbx
0x1800096a1  push    rdi
0x1800096a2  sub     rsp, 20h
0x1800096a6  mov     rdi, [rcx+8]
0x1800096aa  lea     rax, ??_7LocalContentProviderConfiguration@@6B@; const LocalContentProviderConfiguration::`vftable'
0x1800096b1  mov     [rcx], rax
0x1800096b4  mov     rbx, rcx
0x1800096b7  test    rdi, rdi
0x1800096ba  jz      short loc_1800096D8
0x1800096bc  call    cs:__imp_GetProcessHeap
0x1800096c2  mov     r8, rdi; lpMem
0x1800096c5  xor     edx, edx; dwFlags
0x1800096c7  mov     rcx, rax; hHeap
0x1800096ca  call    cs:__imp_HeapFree
0x1800096d0  mov     qword ptr [rbx+8], 0
0x1800096d8  mov     rbx, [rsp+28h+arg_0]
0x1800096dd  add     rsp, 20h
0x1800096e1  pop     rdi
0x1800096e2  retn
```
