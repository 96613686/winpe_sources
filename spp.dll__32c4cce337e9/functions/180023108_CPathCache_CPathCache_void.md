# CPathCache::~CPathCache(void)

- ea: `0x180023108`
- end: `0x180023167`
- name: `??1CPathCache@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CPathCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180023778`

## callees

- `0x18000e104`
- `0x180023108`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023141`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023141`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002312e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002312e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002314f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002314f`

## pseudocode

```c
void __fastcall CPathCache::~CPathCache(CPathCache *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CFileDescriptorEntry *v3; // rbx
  CFileDescriptorEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CFileDescriptorEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CFileDescriptorEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180023108  mov     [rsp+arg_0], rbx
0x18002310d  push    rdi
0x18002310e  sub     rsp, 20h
0x180023112  mov     rdi, rcx
0x180023115  lock inc dword ptr [rcx+8]
0x180023119  cmp     qword ptr [rcx], 0
0x18002311d  jz      short loc_18002315C
0x18002311f  lock inc dword ptr [rcx+8]
0x180023123  mov     rcx, [rcx]
0x180023126  jmp     short loc_18002313F
0x180023128  mov     rbx, [rax]
0x18002312b  mov     rdx, rax; Buffer
0x18002312e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180023134  mov     rcx, rbx; this
0x180023137  call    ?Release@CFileDescriptorEntry@@QEAAKXZ; CFileDescriptorEntry::Release(void)
0x18002313c  mov     rcx, [rdi]; Table
0x18002313f  mov     dl, 1; Restart
0x180023141  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180023147  mov     rcx, [rdi]; pv
0x18002314a  test    rax, rax
0x18002314d  jnz     short loc_180023128
0x18002314f  call    cs:__imp_CoTaskMemFree
0x180023155  mov     qword ptr [rdi], 0
0x18002315c  mov     rbx, [rsp+28h+arg_0]
0x180023161  add     rsp, 20h
0x180023165  pop     rdi
0x180023166  retn
```
