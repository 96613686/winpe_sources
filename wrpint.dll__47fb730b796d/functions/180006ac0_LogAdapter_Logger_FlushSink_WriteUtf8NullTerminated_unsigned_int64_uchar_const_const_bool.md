# LogAdapter::Logger::FlushSink::WriteUtf8NullTerminated(unsigned __int64,uchar const * const,bool)

- ea: `0x180006ac0`
- end: `0x180006aed`
- name: `?WriteUtf8NullTerminated@FlushSink@Logger@LogAdapter@@UEAAX_KQEBE_N@Z`
- size: `45`
- prototype: `void __fastcall(LogAdapter::Logger::FlushSink *this, __int64, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001c010`

## pseudocode

```c
void __fastcall LogAdapter::Logger::FlushSink::WriteUtf8NullTerminated(
        LogAdapter::Logger::FlushSink *this,
        __int64 a2,
        const unsigned __int8 *a3)
{
  int v4; // eax

  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int8 *))(**((_QWORD **)this + 1) + 8LL))(
         *((_QWORD *)this + 1),
         *((unsigned int *)this + 4),
         a3);
  if ( *((int *)this + 5) < 0 )
    v4 = *((_DWORD *)this + 5);
  *((_DWORD *)this + 5) = v4;
}

```

## disassembly

```asm
0x180006ac0  push    rbx
0x180006ac2  sub     rsp, 20h
0x180006ac6  mov     rbx, rcx
0x180006ac9  mov     rcx, [rcx+8]
0x180006acd  mov     rax, [rcx]
0x180006ad0  mov     edx, [rbx+10h]
0x180006ad3  mov     rax, [rax+8]
0x180006ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006adc  cmp     dword ptr [rbx+14h], 0
0x180006ae0  cmovl   eax, [rbx+14h]
0x180006ae4  mov     [rbx+14h], eax
0x180006ae7  add     rsp, 20h
0x180006aeb  pop     rbx
0x180006aec  retn
```
