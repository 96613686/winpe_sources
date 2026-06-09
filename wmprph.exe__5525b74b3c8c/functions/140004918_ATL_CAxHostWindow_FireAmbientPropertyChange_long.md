# ATL::CAxHostWindow::FireAmbientPropertyChange(long)

- ea: `0x140004918`
- end: `0x14000498b`
- name: `?FireAmbientPropertyChange@CAxHostWindow@ATL@@QEAAJJ@Z`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140009440`
- `0x140009490`
- `0x1400094f0`
- `0x140009520`
- `0x1400095a0`
- `0x1400095d0`
- `0x140009600`
- `0x1400096d0`

## callees

- `0x140004918`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::FireAmbientPropertyChange(ATL::CAxHostWindow *this, unsigned int a2)
{
  void (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v3; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 20);
  v3 = 0;
  v6 = 0;
  if ( v2 )
  {
    (**v2)(v2, &IID_IOleControl, &v6);
    if ( v6 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, a2);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140004918  mov     [rsp+arg_8], rbx
0x14000491d  push    rdi
0x14000491e  sub     rsp, 20h
0x140004922  mov     rcx, [rcx+0A0h]
0x140004929  xor     ebx, ebx
0x14000492b  mov     [rsp+28h+arg_0], rbx
0x140004930  mov     edi, edx
0x140004932  test    rcx, rcx
0x140004935  jz      short loc_14000497E
0x140004937  mov     rax, [rcx]
0x14000493a  lea     r8, [rsp+28h+arg_0]
0x14000493f  lea     rdx, IID_IOleControl
0x140004946  mov     rax, [rax]
0x140004949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000494e  mov     rcx, [rsp+28h+arg_0]
0x140004953  test    rcx, rcx
0x140004956  jz      short loc_14000497E
0x140004958  mov     rax, [rcx]
0x14000495b  mov     edx, edi
0x14000495d  mov     rax, [rax+28h]
0x140004961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004966  mov     rcx, [rsp+28h+arg_0]
0x14000496b  mov     ebx, eax
0x14000496d  test    rcx, rcx
0x140004970  jz      short loc_14000497E
0x140004972  mov     rdx, [rcx]
0x140004975  mov     rax, [rdx+10h]
0x140004979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000497e  mov     eax, ebx
0x140004980  mov     rbx, [rsp+28h+arg_8]
0x140004985  add     rsp, 20h
0x140004989  pop     rdi
0x14000498a  retn
```
