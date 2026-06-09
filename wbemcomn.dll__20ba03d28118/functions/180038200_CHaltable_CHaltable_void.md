# CHaltable::~CHaltable(void)

- ea: `0x180038200`
- end: `0x180038233`
- name: `??1CHaltable@@UEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CHaltable *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180030400`
- `0x180038460`
- `0x180044948`
- `0x180046068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038226`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003821b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003821b`

## pseudocode

```c
void __fastcall CHaltable::~CHaltable(CHaltable *this)
{
  *(_QWORD *)this = &CHaltable::`vftable';
  CloseHandle(*((HANDLE *)this + 6));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180038200  mov     [rsp+arg_0], rcx
0x180038205  push    rbx
0x180038206  sub     rsp, 20h
0x18003820a  mov     rbx, rcx
0x18003820d  lea     rax, ??_7CHaltable@@6B@; const CHaltable::`vftable'
0x180038214  mov     [rcx], rax
0x180038217  mov     rcx, [rcx+30h]; hObject
0x18003821b  call    cs:__imp_CloseHandle
0x180038221  nop
0x180038222  lea     rcx, [rbx+8]; lpCriticalSection
0x180038226  call    cs:__imp_DeleteCriticalSection
0x18003822c  nop
0x18003822d  add     rsp, 20h
0x180038231  pop     rbx
0x180038232  retn
```
