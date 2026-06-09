# CFilterDescriptionCache::~CFilterDescriptionCache(void)

- ea: `0x18000dedc`
- end: `0x18000df47`
- name: `??1CFilterDescriptionCache@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000fd48`

## callees

- `0x18000dedc`
- `0x18001a828`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df1b`

## pseudocode

```c
void __fastcall CFilterDescriptionCache::~CFilterDescriptionCache(LPVOID *this)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rsi

  v1 = (unsigned __int64 *)(this + 1);
  if ( *this )
  {
    for ( i = 0; i < *v1; ++i )
      operator delete(*((void **)*this + 3 * i + 2));
    CoTaskMemFree(*this);
    *this = 0;
  }
  this[3] = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x18000dedc  mov     [rsp+arg_0], rbx
0x18000dee1  mov     [rsp+arg_8], rsi
0x18000dee6  push    rdi
0x18000dee7  sub     rsp, 20h
0x18000deeb  cmp     qword ptr [rcx], 0
0x18000deef  lea     rdi, [rcx+8]
0x18000def3  mov     rbx, rcx
0x18000def6  jz      short loc_18000DF28
0x18000def8  xor     esi, esi
0x18000defa  cmp     [rdi], rsi
0x18000defd  jbe     short loc_18000DF18
0x18000deff  mov     rcx, [rbx]
0x18000df02  lea     rax, [rsi+rsi*2]
0x18000df06  mov     rcx, [rcx+rax*8+10h]; lpMem
0x18000df0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df10  inc     rsi
0x18000df13  cmp     rsi, [rdi]
0x18000df16  jb      short loc_18000DEFF
0x18000df18  mov     rcx, [rbx]; pv
0x18000df1b  call    cs:__imp_CoTaskMemFree
0x18000df21  mov     qword ptr [rbx], 0
0x18000df28  mov     rsi, [rsp+28h+arg_8]
0x18000df2d  mov     qword ptr [rbx+18h], 0
0x18000df35  mov     rbx, [rsp+28h+arg_0]
0x18000df3a  mov     qword ptr [rdi], 0
0x18000df41  add     rsp, 20h
0x18000df45  pop     rdi
0x18000df46  retn
```
