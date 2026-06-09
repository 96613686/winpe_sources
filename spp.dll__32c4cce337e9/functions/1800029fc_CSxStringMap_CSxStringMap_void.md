# CSxStringMap::~CSxStringMap(void)

- ea: `0x1800029fc`
- end: `0x180002a5b`
- name: `??1CSxStringMap@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CSxStringMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e34c`

## callees

- `0x1800029fc`
- `0x18000e308`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x180002a35`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180002a35`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180002a22`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180002a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002a43`

## pseudocode

```c
void __fastcall CSxStringMap::~CSxStringMap(CSxStringMap *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CVolumeEntry *v3; // rbx
  CVolumeEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CVolumeEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CVolumeEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800029fc  mov     [rsp+arg_0], rbx
0x180002a01  push    rdi
0x180002a02  sub     rsp, 20h
0x180002a06  mov     rdi, rcx
0x180002a09  lock inc dword ptr [rcx+8]
0x180002a0d  cmp     qword ptr [rcx], 0
0x180002a11  jz      short loc_180002A50
0x180002a13  lock inc dword ptr [rcx+8]
0x180002a17  mov     rcx, [rcx]
0x180002a1a  jmp     short loc_180002A33
0x180002a1c  mov     rbx, [rax]
0x180002a1f  mov     rdx, rax; Buffer
0x180002a22  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180002a28  mov     rcx, rbx; this
0x180002a2b  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180002a30  mov     rcx, [rdi]; Table
0x180002a33  mov     dl, 1; Restart
0x180002a35  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180002a3b  mov     rcx, [rdi]; pv
0x180002a3e  test    rax, rax
0x180002a41  jnz     short loc_180002A1C
0x180002a43  call    cs:__imp_CoTaskMemFree
0x180002a49  mov     qword ptr [rdi], 0
0x180002a50  mov     rbx, [rsp+28h+arg_0]
0x180002a55  add     rsp, 20h
0x180002a59  pop     rdi
0x180002a5a  retn
```
