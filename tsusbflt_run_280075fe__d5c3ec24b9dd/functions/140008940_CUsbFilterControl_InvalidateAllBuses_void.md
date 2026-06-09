# CUsbFilterControl::InvalidateAllBuses(void)

- ea: `0x140008940`
- end: `0x1400089de`
- name: `?InvalidateAllBuses@CUsbFilterControl@@AEAAXXZ`
- size: `158`
- prototype: `void __fastcall(CUsbFilterControl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000711c`
- `0x1400094a0`

## callees

- `0x140008940`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400089bb`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400089bb`

## pseudocode

```c
void __fastcall CUsbFilterControl::InvalidateAllBuses(CUsbFilterControl *this)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  __int64 v4; // rax
  struct _DEVICE_OBJECT *v5; // rax

  v2 = 0;
  v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         *((_QWORD *)this + 1));
  if ( v3 )
  {
    do
    {
      v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             *((_QWORD *)this + 1),
             v2);
      v5 = (struct _DEVICE_OBJECT *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[89].Blink)(
                                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                                      v4);
      IoInvalidateDeviceRelations(v5, BusRelations);
      ++v2;
    }
    while ( v2 < v3 );
  }
}

```

## disassembly

```asm
0x140008940  mov     [rsp+arg_0], rbx
0x140008945  mov     [rsp+arg_8], rsi
0x14000894a  push    rdi
0x14000894b  sub     rsp, 20h
0x14000894f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008956  mov     rbx, rcx
0x140008959  mov     rdx, [rcx+8]
0x14000895d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008964  mov     rax, [rax+70h]
0x140008968  call    _guard_dispatch_icall
0x14000896d  xor     esi, esi
0x14000896f  mov     edi, eax
0x140008971  test    eax, eax
0x140008973  jz      short loc_1400089CD
0x140008975  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000897c  mov     r8d, esi
0x14000897f  mov     rdx, [rbx+8]
0x140008983  mov     rax, [rcx+90h]
0x14000898a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008991  call    _guard_dispatch_icall
0x140008996  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000899d  mov     rdx, rax
0x1400089a0  mov     r8, [rcx+598h]
0x1400089a7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400089ae  mov     rax, r8
0x1400089b1  call    _guard_dispatch_icall
0x1400089b6  xor     edx, edx; Type
0x1400089b8  mov     rcx, rax; DeviceObject
0x1400089bb  call    cs:__imp_IoInvalidateDeviceRelations
0x1400089c2  nop     dword ptr [rax+rax+00h]
0x1400089c7  inc     esi
0x1400089c9  cmp     esi, edi
0x1400089cb  jb      short loc_140008975
0x1400089cd  mov     rbx, [rsp+28h+arg_0]
0x1400089d2  mov     rsi, [rsp+28h+arg_8]
0x1400089d7  add     rsp, 20h
0x1400089db  pop     rdi
0x1400089dc  retn
```
