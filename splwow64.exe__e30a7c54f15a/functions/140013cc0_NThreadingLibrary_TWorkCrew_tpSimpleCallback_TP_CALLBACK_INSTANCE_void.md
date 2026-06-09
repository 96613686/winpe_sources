# NThreadingLibrary::TWorkCrew::tpSimpleCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x140013cc0`
- end: `0x140013cf9`
- name: `?tpSimpleCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `57`
- prototype: `static void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400139b0`
- `0x140013cc0`
- `0x140016010`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::tpSimpleCallback(struct _TP_CALLBACK_INSTANCE *a1, __int64 a2)
{
  if ( *(_DWORD *)(a2 + 64) == 1953063799 )
  {
    if ( !*(_DWORD *)(a2 + 68) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
    NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(*(NThreadingLibrary::TWorkCrew **)(a2 + 80), a2);
  }
}

```

## disassembly

```asm
0x140013cc0  push    rbx
0x140013cc2  sub     rsp, 20h
0x140013cc6  cmp     dword ptr [rdx+40h], 74696377h
0x140013ccd  mov     rbx, rdx
0x140013cd0  jnz     short loc_140013CF3
0x140013cd2  cmp     dword ptr [rdx+44h], 0
0x140013cd6  jnz     short loc_140013CE7
0x140013cd8  mov     rax, [rdx]
0x140013cdb  mov     rcx, rdx
0x140013cde  mov     rax, [rax+18h]
0x140013ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ce7  mov     rcx, [rbx+50h]; this
0x140013ceb  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x140013cee  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140013cf3  add     rsp, 20h
0x140013cf7  pop     rbx
0x140013cf8  retn
```
