# CPVRAsyncWriter::~CPVRAsyncWriter(void)

- ea: `0x1800783ac`
- end: `0x180078443`
- name: `??1CPVRAsyncWriter@@UEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CPVRAsyncWriter *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007849c`
- `0x180078600`

## callees

- `0x18000c1c4`
- `0x1800783ac`
- `0x18007b5a0`
- `0x18007c130`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800783f5`
- `KERNEL32!CloseHandle` at `0x180078405`
- `KERNEL32!CloseHandle` at `0x180078417`
- `KERNEL32!CloseHandle` at `0x1800783f5`
- `KERNEL32!CloseHandle` at `0x180078405`
- `KERNEL32!CloseHandle` at `0x180078417`
- `KERNEL32!DeleteCriticalSection` at `0x180078421`
- `KERNEL32!DeleteCriticalSection` at `0x180078421`

## pseudocode

```c
void __fastcall CPVRAsyncWriter::~CPVRAsyncWriter(CPVRAsyncWriter *this)
{
  CPVRWriteBufferStream *v1; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v1 = (CPVRAsyncWriter *)((char *)this + 80);
  *(_QWORD *)this = &CPVRAsyncWriter::`vftable';
  (*(void (__fastcall **)(CPVRWriteBufferStream *))(*(_QWORD *)v1 + 8LL))(v1);
  CAsyncIo::Release(*((CAsyncIo **)this + 1));
  CPVRIOCounters::Release(*((CPVRIOCounters **)this + 17));
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 != (void *)-1LL )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 20);
  if ( v5 )
    CloseHandle(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  *(_QWORD *)v1 = &CPVRWriteBufferStream::`vftable';
  CPVRWriteBufferStream::Uninitialize(v1);
}

```

## disassembly

```asm
0x1800783ac  mov     [rsp+arg_0], rbx
0x1800783b1  push    rdi
0x1800783b2  sub     rsp, 20h
0x1800783b6  lea     rdi, [rcx+50h]
0x1800783ba  mov     rbx, rcx
0x1800783bd  lea     rax, ??_7CPVRAsyncWriter@@6B@; const CPVRAsyncWriter::`vftable'
0x1800783c4  mov     [rcx], rax
0x1800783c7  mov     rcx, rdi
0x1800783ca  mov     rax, [rdi]
0x1800783cd  mov     rax, [rax+8]
0x1800783d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783d6  mov     rcx, [rbx+8]; this
0x1800783da  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x1800783df  mov     rcx, [rbx+88h]; this
0x1800783e6  call    ?Release@CPVRIOCounters@@QEAAJXZ; CPVRIOCounters::Release(void)
0x1800783eb  mov     rcx, [rbx+10h]; hObject
0x1800783ef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800783f3  jz      short loc_1800783FB
0x1800783f5  call    cs:__imp_CloseHandle
0x1800783fb  mov     rcx, [rbx+18h]; hObject
0x1800783ff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180078403  jz      short loc_18007840B
0x180078405  call    cs:__imp_CloseHandle
0x18007840b  mov     rcx, [rbx+0A0h]; hObject
0x180078412  test    rcx, rcx
0x180078415  jz      short loc_18007841D
0x180078417  call    cs:__imp_CloseHandle
0x18007841d  lea     rcx, [rbx+28h]; lpCriticalSection
0x180078421  call    cs:__imp_DeleteCriticalSection
0x180078427  lea     rax, ??_7CPVRWriteBufferStream@@6B@; const CPVRWriteBufferStream::`vftable'
0x18007842e  mov     rcx, rdi; this
0x180078431  mov     [rdi], rax
0x180078434  mov     rbx, [rsp+28h+arg_0]
0x180078439  add     rsp, 20h
0x18007843d  pop     rdi
0x18007843e  jmp     ?Uninitialize@CPVRWriteBufferStream@@UEAAXXZ; CPVRWriteBufferStream::Uninitialize(void)
```
