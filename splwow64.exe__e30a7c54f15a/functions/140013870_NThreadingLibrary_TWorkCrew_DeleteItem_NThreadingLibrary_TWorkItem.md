# NThreadingLibrary::TWorkCrew::DeleteItem(NThreadingLibrary::TWorkItem *)

- ea: `0x140013870`
- end: `0x1400138c6`
- name: `?DeleteItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z`
- size: `86`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001140c`
- `0x140012390`
- `0x140013b24`

## callees

- `0x140013870`
- `0x1400139b0`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::DeleteItem(
        NThreadingLibrary::TWorkCrew *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  unsigned int v4; // edi

  if ( a2 )
  {
    v4 = 0;
    (*(void (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)a2 + 32LL))(a2);
    if ( *((_DWORD *)a2 + 22) )
      return (unsigned int)NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(this, (__int64)a2);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140013870  mov     [rsp+arg_0], rbx
0x140013875  mov     [rsp+arg_8], rsi
0x14001387a  push    rdi
0x14001387b  sub     rsp, 20h
0x14001387f  mov     rbx, rdx
0x140013882  mov     rsi, rcx
0x140013885  test    rdx, rdx
0x140013888  jz      short loc_1400138AF
0x14001388a  mov     rax, [rdx]
0x14001388d  mov     rcx, rdx
0x140013890  xor     edi, edi
0x140013892  mov     rax, [rax+20h]
0x140013896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001389b  cmp     [rbx+58h], edi
0x14001389e  jz      short loc_1400138B4
0x1400138a0  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x1400138a3  mov     rcx, rsi; this
0x1400138a6  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x1400138ab  mov     edi, eax
0x1400138ad  jmp     short loc_1400138B4
0x1400138af  mov     edi, 80070057h
0x1400138b4  mov     rbx, [rsp+28h+arg_0]
0x1400138b9  mov     eax, edi
0x1400138bb  mov     rsi, [rsp+28h+arg_8]
0x1400138c0  add     rsp, 20h
0x1400138c4  pop     rdi
0x1400138c5  retn
```
