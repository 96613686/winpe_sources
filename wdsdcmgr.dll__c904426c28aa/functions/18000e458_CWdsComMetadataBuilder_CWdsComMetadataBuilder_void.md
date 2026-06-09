# CWdsComMetadataBuilder::CWdsComMetadataBuilder(void)

- ea: `0x18000e458`
- end: `0x18000e4be`
- name: `??0CWdsComMetadataBuilder@@QEAA@XZ`
- size: `102`
- prototype: `CWdsComMetadataBuilder *__fastcall(CWdsComMetadataBuilder *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e194`
- `0x18000e504`

## callees

- `0x180015c9d`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000e4aa`
- `KERNEL32!InitializeCriticalSection` at `0x18000e4aa`

## pseudocode

```c
CWdsComMetadataBuilder *__fastcall CWdsComMetadataBuilder::CWdsComMetadataBuilder(CWdsComMetadataBuilder *this)
{
  *((_DWORD *)this + 2) = 0;
  memset_0((char *)this + 16, 0, 0x28u);
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 25) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_DWORD *)this + 31) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  return this;
}

```

## disassembly

```asm
0x18000e458  mov     [rsp+arg_0], rbx
0x18000e45d  push    rdi
0x18000e45e  sub     rsp, 20h
0x18000e462  and     dword ptr [rcx+8], 0
0x18000e466  xor     edx, edx; Val
0x18000e468  mov     rdi, rcx
0x18000e46b  add     rcx, 10h; void *
0x18000e46f  lea     r8d, [rdx+28h]; Size
0x18000e473  call    memset_0
0x18000e478  mov     byte ptr [rdi+38h], 0
0x18000e47c  lea     rcx, [rdi+88h]; lpCriticalSection
0x18000e483  and     qword ptr [rdi+40h], 0
0x18000e488  and     dword ptr [rdi+48h], 0
0x18000e48c  and     dword ptr [rdi+4Ch], 0
0x18000e490  and     qword ptr [rdi+58h], 0
0x18000e495  and     dword ptr [rdi+60h], 0
0x18000e499  and     dword ptr [rdi+64h], 0
0x18000e49d  and     qword ptr [rdi+70h], 0
0x18000e4a2  and     dword ptr [rdi+78h], 0
0x18000e4a6  and     dword ptr [rdi+7Ch], 0
0x18000e4aa  call    cs:__imp_InitializeCriticalSection
0x18000e4b0  mov     rbx, [rsp+28h+arg_0]
0x18000e4b5  mov     rax, rdi
0x18000e4b8  add     rsp, 20h
0x18000e4bc  pop     rdi
0x18000e4bd  retn
```
