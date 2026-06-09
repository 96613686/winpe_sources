# CWriterEntryMap::~CWriterEntryMap(void)

- ea: `0x1800231ec`
- end: `0x18002324b`
- name: `??1CWriterEntryMap@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CWriterEntryMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e5cc`

## callees

- `0x18000e54c`
- `0x1800231ec`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023225`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180023225`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023212`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180023212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023233`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023233`

## pseudocode

```c
void __fastcall CWriterEntryMap::~CWriterEntryMap(CWriterEntryMap *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CWriterEntry *v3; // rbx
  CWriterEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CWriterEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CWriterEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800231ec  mov     [rsp+arg_0], rbx
0x1800231f1  push    rdi
0x1800231f2  sub     rsp, 20h
0x1800231f6  mov     rdi, rcx
0x1800231f9  lock inc dword ptr [rcx+8]
0x1800231fd  cmp     qword ptr [rcx], 0
0x180023201  jz      short loc_180023240
0x180023203  lock inc dword ptr [rcx+8]
0x180023207  mov     rcx, [rcx]
0x18002320a  jmp     short loc_180023223
0x18002320c  mov     rbx, [rax]
0x18002320f  mov     rdx, rax; Buffer
0x180023212  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180023218  mov     rcx, rbx; this
0x18002321b  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x180023220  mov     rcx, [rdi]; Table
0x180023223  mov     dl, 1; Restart
0x180023225  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002322b  mov     rcx, [rdi]; pv
0x18002322e  test    rax, rax
0x180023231  jnz     short loc_18002320C
0x180023233  call    cs:__imp_CoTaskMemFree
0x180023239  mov     qword ptr [rdi], 0
0x180023240  mov     rbx, [rsp+28h+arg_0]
0x180023245  add     rsp, 20h
0x180023249  pop     rdi
0x18002324a  retn
```
