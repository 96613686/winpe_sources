# ExcHandler::~ExcHandler(void)

- ea: `0x1004010b0`
- end: `0x10040110c`
- name: `??1ExcHandler@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(ExcHandler *__hidden this)`
- caller_count: `27`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100401160`
- `0x1004052b0`
- `0x100405500`
- `0x100405b20`
- `0x10040c8d0`
- `0x10040cda0`
- `0x10040d5d0`
- `0x100418d20`
- `0x10041ef70`
- `0x100429dc0`
- `0x1004369a0`
- `0x100438960`
- `0x100439f60`
- `0x100453834`
- `0x1004538b4`
- `0x100453934`
- `0x100453be0`
- `0x100453d30`
- `0x1004540a0`
- `0x100454580`
- `0x100454910`
- `0x100454974`
- `0x100454b30`
- `0x1004555c0`
- `0x1004557d0`
- `0x100455b40`
- `0x100455d00`

## callees

- `0x1004010b0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405465`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100405465`
- `sqldk!SystemThread_TlsOffset` at `0x1004010d9`
- `sqldk!SystemThread_TlsIndex` at `0x1004010cb`

## pseudocode

```c
void __fastcall ExcHandler::~ExcHandler(ExcHandler *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdi

  v2 = *((_QWORD *)this + 4);
  if ( !v2 )
  {
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v2 = *(_QWORD *)(v3 + 256);
    if ( !v2 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v2 = *(_QWORD *)(v3 + 256);
    }
  }
  *(_QWORD *)(v2 + 192) = *((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1004010b0  push    rbx
0x1004010b2  sub     rsp, 20h
0x1004010b6  mov     rbx, rcx
0x1004010b9  mov     rcx, [rcx+20h]
0x1004010bd  test    rcx, rcx
0x1004010c0  jnz     short loc_1004010FB
0x1004010c2  mov     rdx, gs:58h
0x1004010cb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004010d2  mov     [rsp+28h+arg_0], rdi
0x1004010d7  mov     ecx, [rax]
0x1004010d9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004010e0  mov     edi, [rax]
0x1004010e2  add     rdi, [rdx+rcx*8]
0x1004010e6  mov     rcx, [rdi+100h]
0x1004010ed  test    rcx, rcx
0x1004010f0  jz      loc_100405465
0x1004010f6  mov     rdi, [rsp+28h+arg_0]
0x1004010fb  mov     rax, [rbx+8]
0x1004010ff  mov     [rcx+0C0h], rax
0x100401106  add     rsp, 20h
0x10040110a  pop     rbx
0x10040110b  retn
0x100405465  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040546b  mov     rcx, [rdi+100h]
0x100405472  jmp     loc_1004010F6
```
