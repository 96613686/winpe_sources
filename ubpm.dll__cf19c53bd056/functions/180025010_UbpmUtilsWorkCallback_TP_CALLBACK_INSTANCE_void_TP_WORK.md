# UbpmUtilsWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180025010`
- end: `0x18002506a`
- name: `?UbpmUtilsWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `90`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180025010`
- `0x18003e010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180025050`
- `ntdll!RtlFreeHeap` at `0x180025050`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180025026`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180025026`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180025063`

## pseudocode

```c
void __fastcall UbpmUtilsWorkCallback(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context, PTP_WORK Work)
{
  void (__fastcall **v4)(_QWORD, _BYTE *, _QWORD); // rbx

  v4 = (void (__fastcall **)(_QWORD, _BYTE *, _QWORD))Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 2;
  v4[2](v4[1], Context, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  CloseThreadpoolWork(Work);
}

```

## disassembly

```asm
0x180025010  mov     [rsp+arg_0], rbx
0x180025015  push    rdi
0x180025016  sub     rsp, 20h
0x18002501a  test    byte ptr [rdx+18h], 1
0x18002501e  mov     rdi, r8
0x180025021  mov     rbx, rdx
0x180025024  jz      short loc_18002502C
0x180025026  call    cs:__imp_CallbackMayRunLong
0x18002502c  mov     rcx, [rbx+8]
0x180025030  xor     r8d, r8d
0x180025033  mov     rax, [rbx+10h]
0x180025037  mov     dl, 2
0x180025039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002503e  mov     rcx, gs:60h
0x180025047  mov     r8, rbx; P
0x18002504a  xor     edx, edx; Flags
0x18002504c  mov     rcx, [rcx+30h]; HeapHandle
0x180025050  call    cs:__imp_RtlFreeHeap
0x180025056  mov     rcx, rdi
0x180025059  mov     rbx, [rsp+28h+arg_0]
0x18002505e  add     rsp, 20h
0x180025062  pop     rdi
0x180025063  jmp     cs:__imp_CloseThreadpoolWork
```
