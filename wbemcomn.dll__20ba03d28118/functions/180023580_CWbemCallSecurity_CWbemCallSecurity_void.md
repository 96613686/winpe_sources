# CWbemCallSecurity::~CWbemCallSecurity(void)

- ea: `0x180023580`
- end: `0x1800235c9`
- name: `??1CWbemCallSecurity@@AEAA@XZ`
- size: `73`
- prototype: `void __fastcall(CWbemCallSecurity *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800234fc`
- `0x180023530`
- `0x1800280c0`
- `0x18004590d`

## callees

- `0x180023580`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002359c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002359c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800235c1`

## pseudocode

```c
void __fastcall CWbemCallSecurity::~CWbemCallSecurity(CWbemCallSecurity *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CWbemCallSecurity::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
    CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180023580  push    rbx
0x180023582  sub     rsp, 20h
0x180023586  mov     rbx, rcx
0x180023589  lea     rax, ??_7CWbemCallSecurity@@6B@; const CWbemCallSecurity::`vftable'
0x180023590  mov     [rcx], rax
0x180023593  mov     rcx, [rcx+10h]; hObject
0x180023597  test    rcx, rcx
0x18002359a  jz      short loc_1800235A2
0x18002359c  call    cs:__imp_CloseHandle
0x1800235a2  mov     rcx, [rbx+30h]; pv
0x1800235a6  test    rcx, rcx
0x1800235a9  jnz     short loc_1800235C1
0x1800235ab  mov     rcx, [rbx+38h]; pv
0x1800235af  test    rcx, rcx
0x1800235b2  jz      short loc_1800235BB
0x1800235b4  call    cs:__imp_CoTaskMemFree
0x1800235ba  nop
0x1800235bb  add     rsp, 20h
0x1800235bf  pop     rbx
0x1800235c0  retn
0x1800235c1  call    cs:__imp_CoTaskMemFree
0x1800235c7  jmp     short loc_1800235AB
```
