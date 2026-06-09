# EventProcessorManager::CreateEventProcessor(ushort const *,ushort const *)

- ea: `0x180003ea0`
- end: `0x180003eff`
- name: `?CreateEventProcessor@EventProcessorManager@@UEAA?AV?$AutoRef@VAbstractEventProcessor@@@wmi@@PEBG0@Z`
- size: `95`
- prototype: `volatile signed __int32 **__fastcall(__int64, volatile signed __int32 **, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003430`
- `0x180003ea0`
- `0x18001c750`

## pseudocode

```c
volatile signed __int32 **__fastcall EventProcessorManager::CreateEventProcessor(
        __int64 a1,
        volatile signed __int32 **a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  volatile signed __int32 *v7; // rax

  v7 = (volatile signed __int32 *)operator new(0x78u);
  if ( v7 )
    v7 = (volatile signed __int32 *)VistaEventProcessor::VistaEventProcessor((VistaEventProcessor *)v7, a3, a4);
  *a2 = v7;
  if ( v7 )
    _InterlockedIncrement(v7 + 2);
  return a2;
}

```

## disassembly

```asm
0x180003ea0  mov     [rsp+arg_0], rbx
0x180003ea5  mov     [rsp+arg_10], rsi
0x180003eaa  mov     [rsp+arg_8], rdx
0x180003eaf  push    rdi
0x180003eb0  sub     rsp, 30h
0x180003eb4  mov     rdi, r9
0x180003eb7  mov     rsi, r8
0x180003eba  mov     rbx, rdx
0x180003ebd  mov     ecx, 78h ; 'x'; dwBytes
0x180003ec2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ec7  mov     [rsp+38h+arg_8], rax
0x180003ecc  test    rax, rax
0x180003ecf  jz      short loc_180003EE0
0x180003ed1  mov     r8, rdi; unsigned __int16 *
0x180003ed4  mov     rdx, rsi; unsigned __int16 *
0x180003ed7  mov     rcx, rax; this
0x180003eda  call    ??0VistaEventProcessor@@QEAA@PEBG0@Z; VistaEventProcessor::VistaEventProcessor(ushort const *,ushort const *)
0x180003edf  nop
0x180003ee0  mov     [rbx], rax
0x180003ee3  test    rax, rax
0x180003ee6  jz      short loc_180003EEC
0x180003ee8  lock inc dword ptr [rax+8]
0x180003eec  mov     rax, rbx
0x180003eef  mov     rbx, [rsp+38h+arg_0]
0x180003ef4  mov     rsi, [rsp+38h+arg_10]
0x180003ef9  add     rsp, 30h
0x180003efd  pop     rdi
0x180003efe  retn
```
