# CDVRSink::SetAsyncIOWriter(IDVRAsyncWriter *)

- ea: `0x180004b00`
- end: `0x180004b69`
- name: `?SetAsyncIOWriter@CDVRSink@@UEAAJPEAUIDVRAsyncWriter@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this, struct IDVRAsyncWriter *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004b00`
- `0x18002b010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004b51`
- `KERNEL32!LeaveCriticalSection` at `0x180004b51`
- `KERNEL32!EnterCriticalSection` at `0x180004b1f`
- `KERNEL32!EnterCriticalSection` at `0x180004b1f`

## pseudocode

```c
__int64 __fastcall CDVRSink::SetAsyncIOWriter(CDVRSink *this, struct IDVRAsyncWriter *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v5; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 9224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 9224));
  if ( *((_QWORD *)this + 40) )
  {
    v5 = -2147418113;
  }
  else
  {
    *((_QWORD *)this + 40) = a2;
    (*(void (__fastcall **)(struct IDVRAsyncWriter *))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = 0;
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180004b00  mov     [rsp+arg_0], rbx
0x180004b05  mov     [rsp+arg_8], rsi
0x180004b0a  push    rdi
0x180004b0b  sub     rsp, 20h
0x180004b0f  lea     rdi, [rcx-2408h]
0x180004b16  mov     rbx, rcx
0x180004b19  mov     rcx, rdi; lpCriticalSection
0x180004b1c  mov     rsi, rdx
0x180004b1f  call    cs:__imp_EnterCriticalSection
0x180004b25  cmp     qword ptr [rbx+140h], 0
0x180004b2d  jnz     short loc_180004B49
0x180004b2f  mov     [rbx+140h], rsi
0x180004b36  mov     rcx, rsi
0x180004b39  mov     rax, [rsi]
0x180004b3c  mov     rax, [rax+8]
0x180004b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b45  xor     ebx, ebx
0x180004b47  jmp     short loc_180004B4E
0x180004b49  mov     ebx, 8000FFFFh
0x180004b4e  mov     rcx, rdi; lpCriticalSection
0x180004b51  call    cs:__imp_LeaveCriticalSection
0x180004b57  mov     rsi, [rsp+28h+arg_8]
0x180004b5c  mov     eax, ebx
0x180004b5e  mov     rbx, [rsp+28h+arg_0]
0x180004b63  add     rsp, 20h
0x180004b67  pop     rdi
0x180004b68  retn
```
