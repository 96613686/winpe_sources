# ATL::CAxHostWindow::UpdateUI(void)

- ea: `0x140008ec0`
- end: `0x140008ee0`
- name: `?UpdateUI@CAxHostWindow@ATL@@UEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140008ec0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::UpdateUI(ATL::CAxHostWindow *this)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *((_QWORD *)this + 10);
  result = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 88LL))(v1);
  return result;
}

```

## disassembly

```asm
0x140008ec0  sub     rsp, 28h
0x140008ec4  mov     rcx, [rcx+50h]
0x140008ec8  xor     eax, eax
0x140008eca  test    rcx, rcx
0x140008ecd  jz      short loc_140008EDB
0x140008ecf  mov     rax, [rcx]
0x140008ed2  mov     rax, [rax+58h]
0x140008ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008edb  add     rsp, 28h
0x140008edf  retn
```
