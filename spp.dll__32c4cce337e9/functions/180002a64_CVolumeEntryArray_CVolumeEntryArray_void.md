# CVolumeEntryArray::~CVolumeEntryArray(void)

- ea: `0x180002a64`
- end: `0x180002ac9`
- name: `??1CVolumeEntryArray@@AEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CVolumeEntryArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e44c`

## callees

- `0x180002a64`
- `0x18000e308`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aa5`

## pseudocode

```c
void __fastcall CVolumeEntryArray::~CVolumeEntryArray(CVolumeEntryArray *this)
{
  __int64 i; // rsi
  void *v3; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
  {
    CVolumeEntry::Release(*(CVolumeEntry **)(*(_QWORD *)this + 8 * i));
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
0x180002a64  mov     [rsp+arg_0], rbx
0x180002a69  mov     [rsp+arg_8], rsi
0x180002a6e  push    rdi
0x180002a6f  sub     rsp, 20h
0x180002a73  xor     esi, esi
0x180002a75  mov     rdi, rcx
0x180002a78  cmp     [rcx+8], esi
0x180002a7b  jbe     short loc_180002A9B
0x180002a7d  mov     rcx, [rdi]
0x180002a80  mov     rcx, [rcx+rsi*8]; this
0x180002a84  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180002a89  mov     rax, [rdi]
0x180002a8c  mov     qword ptr [rax+rsi*8], 0
0x180002a94  inc     esi
0x180002a96  cmp     esi, [rdi+8]
0x180002a99  jb      short loc_180002A7D
0x180002a9b  mov     rcx, [rdi]; pv
0x180002a9e  mov     dword ptr [rdi+8], 0
0x180002aa5  call    cs:__imp_CoTaskMemFree
0x180002aab  mov     rbx, [rsp+28h+arg_0]
0x180002ab0  mov     rsi, [rsp+28h+arg_8]
0x180002ab5  mov     qword ptr [rdi], 0
0x180002abc  mov     dword ptr [rdi+0Ch], 0
0x180002ac3  add     rsp, 20h
0x180002ac7  pop     rdi
0x180002ac8  retn
```
