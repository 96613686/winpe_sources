# CVolumeIdMap::~CVolumeIdMap(void)

- ea: `0x180027504`
- end: `0x180027563`
- name: `??1CVolumeIdMap@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CVolumeIdMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180027d1c`

## callees

- `0x180027504`
- `0x180027cdc`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002753d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002753d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002752a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002752a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002754b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002754b`

## pseudocode

```c
void __fastcall CVolumeIdMap::~CVolumeIdMap(CVolumeIdMap *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeIdEntry *v3; // rbx
  CVolumeIdEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CVolumeIdEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeIdEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180027504  mov     [rsp+arg_0], rbx
0x180027509  push    rdi
0x18002750a  sub     rsp, 20h
0x18002750e  mov     rdi, rcx
0x180027511  lock inc dword ptr [rcx+8]
0x180027515  cmp     qword ptr [rcx], 0
0x180027519  jz      short loc_180027558
0x18002751b  lock inc dword ptr [rcx+8]
0x18002751f  mov     rcx, [rcx]
0x180027522  jmp     short loc_18002753B
0x180027524  mov     rbx, [rax]
0x180027527  mov     rdx, rax; Buffer
0x18002752a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180027530  mov     rcx, rbx; this
0x180027533  call    ?Release@CVolumeIdEntry@@QEAAKXZ; CVolumeIdEntry::Release(void)
0x180027538  mov     rcx, [rdi]; Table
0x18002753b  mov     dl, 1; Restart
0x18002753d  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180027543  mov     rcx, [rdi]; pv
0x180027546  test    rax, rax
0x180027549  jnz     short loc_180027524
0x18002754b  call    cs:__imp_CoTaskMemFree
0x180027551  mov     qword ptr [rdi], 0
0x180027558  mov     rbx, [rsp+28h+arg_0]
0x18002755d  add     rsp, 20h
0x180027561  pop     rdi
0x180027562  retn
```
