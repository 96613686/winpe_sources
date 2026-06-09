# CComponentEntryArray::~CComponentEntryArray(void)

- ea: `0x180022fcc`
- end: `0x180023031`
- name: `??1CComponentEntryArray@@AEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CComponentEntryArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800236b8`

## callees

- `0x18000e080`
- `0x180022fcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002300d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002300d`

## pseudocode

```c
void __fastcall CComponentEntryArray::~CComponentEntryArray(CComponentEntryArray *this)
{
  __int64 i; // rsi
  void *v3; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
  {
    CComponentEntry::Release(*(CComponentEntry **)(*(_QWORD *)this + 8 * i));
    *(_QWORD *)(*(_QWORD *)this + 8 * i) = 0;
  }
  v3 = *(void **)this;
  *((_DWORD *)this + 2) = 0;
  CoTaskMemFree(v3);
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180022fcc  mov     [rsp+arg_0], rbx
0x180022fd1  mov     [rsp+arg_8], rsi
0x180022fd6  push    rdi
0x180022fd7  sub     rsp, 20h
0x180022fdb  xor     esi, esi
0x180022fdd  mov     rdi, rcx
0x180022fe0  cmp     [rcx+8], esi
0x180022fe3  jbe     short loc_180023003
0x180022fe5  mov     rcx, [rdi]
0x180022fe8  mov     rcx, [rcx+rsi*8]; this
0x180022fec  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x180022ff1  mov     rax, [rdi]
0x180022ff4  mov     qword ptr [rax+rsi*8], 0
0x180022ffc  inc     esi
0x180022ffe  cmp     esi, [rdi+8]
0x180023001  jb      short loc_180022FE5
0x180023003  mov     rcx, [rdi]; pv
0x180023006  mov     dword ptr [rdi+8], 0
0x18002300d  call    cs:__imp_CoTaskMemFree
0x180023013  mov     rbx, [rsp+28h+arg_0]
0x180023018  mov     rsi, [rsp+28h+arg_8]
0x18002301d  mov     qword ptr [rdi], 0
0x180023024  mov     dword ptr [rdi+0Ch], 0
0x18002302b  add     rsp, 20h
0x18002302f  pop     rdi
0x180023030  retn
```
