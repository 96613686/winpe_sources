# CVolumeOnDiskPropCacheMap::~CVolumeOnDiskPropCacheMap(void)

- ea: `0x180002b38`
- end: `0x180002b97`
- name: `??1CVolumeOnDiskPropCacheMap@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CVolumeOnDiskPropCacheMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e50c`

## callees

- `0x180002b38`
- `0x18000e4cc`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180002b71`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180002b71`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180002b5e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180002b5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002b7f`

## pseudocode

```c
void __fastcall CVolumeOnDiskPropCacheMap::~CVolumeOnDiskPropCacheMap(CVolumeOnDiskPropCacheMap *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeOnDiskPropCacheEntry *v3; // rbx
  CVolumeOnDiskPropCacheEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CVolumeOnDiskPropCacheEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeOnDiskPropCacheEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180002b38  mov     [rsp+arg_0], rbx
0x180002b3d  push    rdi
0x180002b3e  sub     rsp, 20h
0x180002b42  mov     rdi, rcx
0x180002b45  lock inc dword ptr [rcx+8]
0x180002b49  cmp     qword ptr [rcx], 0
0x180002b4d  jz      short loc_180002B8C
0x180002b4f  lock inc dword ptr [rcx+8]
0x180002b53  mov     rcx, [rcx]
0x180002b56  jmp     short loc_180002B6F
0x180002b58  mov     rbx, [rax]
0x180002b5b  mov     rdx, rax; Buffer
0x180002b5e  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180002b64  mov     rcx, rbx; this
0x180002b67  call    ?Release@CVolumeOnDiskPropCacheEntry@@QEAAKXZ; CVolumeOnDiskPropCacheEntry::Release(void)
0x180002b6c  mov     rcx, [rdi]; Table
0x180002b6f  mov     dl, 1; Restart
0x180002b71  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180002b77  mov     rcx, [rdi]; pv
0x180002b7a  test    rax, rax
0x180002b7d  jnz     short loc_180002B58
0x180002b7f  call    cs:__imp_CoTaskMemFree
0x180002b85  mov     qword ptr [rdi], 0
0x180002b8c  mov     rbx, [rsp+28h+arg_0]
0x180002b91  add     rsp, 20h
0x180002b95  pop     rdi
0x180002b96  retn
```
