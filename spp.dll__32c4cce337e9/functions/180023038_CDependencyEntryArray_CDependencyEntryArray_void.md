# CDependencyEntryArray::~CDependencyEntryArray(void)

- ea: `0x180023038`
- end: `0x18002309d`
- name: `??1CDependencyEntryArray@@AEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CDependencyEntryArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800236f8`

## callees

- `0x18000e0c0`
- `0x180023038`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023079`

## pseudocode

```c
void __fastcall CDependencyEntryArray::~CDependencyEntryArray(CDependencyEntryArray *this)
{
  __int64 i; // rsi
  void *v3; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
  {
    CDependencyEntry::Release(*(CDependencyEntry **)(*(_QWORD *)this + 8 * i));
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
0x180023038  mov     [rsp+arg_0], rbx
0x18002303d  mov     [rsp+arg_8], rsi
0x180023042  push    rdi
0x180023043  sub     rsp, 20h
0x180023047  xor     esi, esi
0x180023049  mov     rdi, rcx
0x18002304c  cmp     [rcx+8], esi
0x18002304f  jbe     short loc_18002306F
0x180023051  mov     rcx, [rdi]
0x180023054  mov     rcx, [rcx+rsi*8]; this
0x180023058  call    ?Release@CDependencyEntry@@QEAAKXZ; CDependencyEntry::Release(void)
0x18002305d  mov     rax, [rdi]
0x180023060  mov     qword ptr [rax+rsi*8], 0
0x180023068  inc     esi
0x18002306a  cmp     esi, [rdi+8]
0x18002306d  jb      short loc_180023051
0x18002306f  mov     rcx, [rdi]; pv
0x180023072  mov     dword ptr [rdi+8], 0
0x180023079  call    cs:__imp_CoTaskMemFree
0x18002307f  mov     rbx, [rsp+28h+arg_0]
0x180023084  mov     rsi, [rsp+28h+arg_8]
0x180023089  mov     qword ptr [rdi], 0
0x180023090  mov     dword ptr [rdi+0Ch], 0
0x180023097  add     rsp, 20h
0x18002309b  pop     rdi
0x18002309c  retn
```
