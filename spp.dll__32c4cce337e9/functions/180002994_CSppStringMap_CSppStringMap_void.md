# CSppStringMap::~CSppStringMap(void)

- ea: `0x180002994`
- end: `0x1800029f3`
- name: `??1CSppStringMap@@AEAA@XZ`
- size: `95`
- prototype: `void __fastcall(CSppStringMap *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e288`

## callees

- `0x180002994`
- `0x18000e208`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800029cd`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800029cd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800029ba`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800029ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800029db`

## pseudocode

```c
void __fastcall CSppStringMap::~CSppStringMap(CSppStringMap *this)
{
  struct _RTL_AVL_TABLE *i; // rcx
  CSppStringMapEntry *v3; // rbx
  CSppStringMapEntry **v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx

  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( *(_QWORD *)this )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    for ( i = *(struct _RTL_AVL_TABLE **)this; ; i = *(struct _RTL_AVL_TABLE **)this )
    {
      v4 = (CSppStringMapEntry **)RtlEnumerateGenericTableAvl(i, 1u);
      v5 = *(struct _RTL_AVL_TABLE **)this;
      if ( !v4 )
        break;
      v3 = *v4;
      RtlDeleteElementGenericTableAvl(v5, v4);
      CSppStringMapEntry::Release(v3);
    }
    CoTaskMemFree(v5);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180002994  mov     [rsp+arg_0], rbx
0x180002999  push    rdi
0x18000299a  sub     rsp, 20h
0x18000299e  mov     rdi, rcx
0x1800029a1  lock inc dword ptr [rcx+8]
0x1800029a5  cmp     qword ptr [rcx], 0
0x1800029a9  jz      short loc_1800029E8
0x1800029ab  lock inc dword ptr [rcx+8]
0x1800029af  mov     rcx, [rcx]
0x1800029b2  jmp     short loc_1800029CB
0x1800029b4  mov     rbx, [rax]
0x1800029b7  mov     rdx, rax; Buffer
0x1800029ba  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800029c0  mov     rcx, rbx; this
0x1800029c3  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x1800029c8  mov     rcx, [rdi]; Table
0x1800029cb  mov     dl, 1; Restart
0x1800029cd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800029d3  mov     rcx, [rdi]; pv
0x1800029d6  test    rax, rax
0x1800029d9  jnz     short loc_1800029B4
0x1800029db  call    cs:__imp_CoTaskMemFree
0x1800029e1  mov     qword ptr [rdi], 0
0x1800029e8  mov     rbx, [rsp+28h+arg_0]
0x1800029ed  add     rsp, 20h
0x1800029f1  pop     rdi
0x1800029f2  retn
```
