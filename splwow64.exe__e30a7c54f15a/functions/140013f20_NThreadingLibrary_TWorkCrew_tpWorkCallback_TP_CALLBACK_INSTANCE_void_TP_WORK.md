# NThreadingLibrary::TWorkCrew::tpWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140013f20`
- end: `0x140013f6e`
- name: `?tpWorkCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `78`
- prototype: `static void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400139b0`
- `0x140013f20`
- `0x140016010`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::tpWorkCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        __int64 a2,
        struct _TP_WORK *a3)
{
  NThreadingLibrary::TWorkCrew *v4; // rcx

  if ( *(_DWORD *)(a2 + 64) == 1953063799 )
  {
    if ( !*(_DWORD *)(a2 + 68) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
    _InterlockedDecrement((volatile signed __int32 *)(a2 + 104));
    v4 = *(NThreadingLibrary::TWorkCrew **)(a2 + 80);
    if ( v4 && !*(_DWORD *)(a2 + 104) )
    {
      if ( *(_DWORD *)(a2 + 108) )
        NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(v4, a2);
    }
  }
}

```

## disassembly

```asm
0x140013f20  push    rbx
0x140013f22  sub     rsp, 20h
0x140013f26  cmp     dword ptr [rdx+40h], 74696377h
0x140013f2d  mov     rbx, rdx
0x140013f30  jnz     short loc_140013F68
0x140013f32  cmp     dword ptr [rdx+44h], 0
0x140013f36  jnz     short loc_140013F47
0x140013f38  mov     rax, [rdx]
0x140013f3b  mov     rcx, rdx
0x140013f3e  mov     rax, [rax+18h]
0x140013f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f47  lock dec dword ptr [rbx+68h]
0x140013f4b  mov     rcx, [rbx+50h]; this
0x140013f4f  test    rcx, rcx
0x140013f52  jz      short loc_140013F68
0x140013f54  cmp     dword ptr [rbx+68h], 0
0x140013f58  jnz     short loc_140013F68
0x140013f5a  cmp     dword ptr [rbx+6Ch], 0
0x140013f5e  jz      short loc_140013F68
0x140013f60  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x140013f63  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140013f68  add     rsp, 20h
0x140013f6c  pop     rbx
0x140013f6d  retn
```
