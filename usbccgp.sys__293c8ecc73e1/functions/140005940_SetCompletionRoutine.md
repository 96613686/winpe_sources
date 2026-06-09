# SetCompletionRoutine

- ea: `0x140005940`
- end: `0x1400059dd`
- name: `SetCompletionRoutine`
- size: `157`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004078`
- `0x1400055c0`
- `0x140009590`
- `0x14000a068`
- `0x14000a1b4`
- `0x14000b670`
- `0x14000eb6c`
- `0x140028800`
- `0x140029b50`

## callees

- `0x140005940`
- `0x14000a6cc`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140005978`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140005978`

## pseudocode

```c
int __fastcall SetCompletionRoutine(
        int a1,
        struct _DEVICE_OBJECT *a2,
        IRP *a3,
        IO_COMPLETION_ROUTINE *a4,
        PVOID Context)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v9; // edx

  LODWORD(CurrentStackLocation) = IoSetCompletionRoutineEx(a2, a3, a4, Context, 1u, 1u, 1u);
  if ( (int)CurrentStackLocation < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 3;
      WPP_RECORDER_SF_d(
        a1,
        v9,
        1,
        60,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        (char)CurrentStackLocation);
    }
    CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))a4;
    CurrentStackLocation[-1].Context = Context;
    CurrentStackLocation[-1].Control = -32;
  }
  return (int)CurrentStackLocation;
}

```

## disassembly

```asm
0x140005940  push    rbx
0x140005942  push    rbp
0x140005943  push    rsi
0x140005944  push    rdi
0x140005945  sub     rsp, 48h
0x140005949  mov     rbx, [rsp+68h+Context]
0x140005951  mov     rdi, r9
0x140005954  mov     rsi, r8
0x140005957  mov     [rsp+68h+InvokeOnCancel], 1; InvokeOnCancel
0x14000595c  mov     rax, rdx
0x14000595f  mov     [rsp+68h+InvokeOnError], 1; InvokeOnError
0x140005964  mov     rbp, rcx
0x140005967  mov     [rsp+68h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000596c  mov     r9, rbx; Context
0x14000596f  mov     r8, rdi; CompletionRoutine
0x140005972  mov     rdx, rsi; Irp
0x140005975  mov     rcx, rax; DeviceObject
0x140005978  call    cs:__imp_IoSetCompletionRoutineEx
0x14000597f  nop     dword ptr [rax+rax+00h]
0x140005984  test    eax, eax
0x140005986  js      short loc_140005992
0x140005988  add     rsp, 48h
0x14000598c  pop     rdi
0x14000598d  pop     rsi
0x14000598e  pop     rbp
0x14000598f  pop     rbx
0x140005990  retn
0x140005992  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140005999  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400059a0  jz      short loc_1400059C8
0x1400059a2  mov     dword ptr [rsp+68h+InvokeOnError], eax
0x1400059a6  mov     r9d, 3Ch ; '<'
0x1400059ac  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x1400059b3  mov     r8d, 1
0x1400059b9  mov     dl, 3
0x1400059bb  mov     qword ptr [rsp+68h+InvokeOnSuccess], rax
0x1400059c0  mov     rcx, rbp
0x1400059c3  call    WPP_RECORDER_SF_d
0x1400059c8  mov     rax, [rsi+0B8h]
0x1400059cf  mov     [rax-10h], rdi
0x1400059d3  mov     [rax-8], rbx
0x1400059d7  mov     byte ptr [rax-45h], 0E0h
0x1400059db  jmp     short loc_140005988
```
