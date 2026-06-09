# CWSHRemote::FireEvent(long)

- ea: `0x1400026e8`
- end: `0x140002736`
- name: `?FireEvent@CWSHRemote@@QEAAXJ@Z`
- size: `78`
- prototype: `void __fastcall(WPARAM wParam, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002310`
- `0x140005990`
- `0x140005ab0`
- `0x140005bc0`

## callees

- `0x1400026e8`
- `0x140018010`

## import_xrefs

- `USER32!PostThreadMessageA` at `0x140002712`
- `USER32!PostThreadMessageA` at `0x140002712`

## pseudocode

```c
void __fastcall CWSHRemote::FireEvent(DWORD *wParam, int a2)
{
  LPARAM v3; // rbx

  v3 = a2;
  (*(void (__fastcall **)(DWORD *))(*(_QWORD *)wParam + 8LL))(wParam);
  if ( !PostThreadMessageA(wParam[10], 0x40Au, (WPARAM)wParam, v3) )
    (*(void (__fastcall **)(DWORD *))(*(_QWORD *)wParam + 16LL))(wParam);
}

```

## disassembly

```asm
0x1400026e8  mov     [rsp+arg_0], rbx
0x1400026ed  push    rdi
0x1400026ee  sub     rsp, 20h
0x1400026f2  mov     rax, [rcx]
0x1400026f5  mov     rdi, rcx
0x1400026f8  movsxd  rbx, edx
0x1400026fb  mov     rax, [rax+8]
0x1400026ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002704  mov     ecx, [rdi+28h]; idThread
0x140002707  mov     r9, rbx; lParam
0x14000270a  mov     r8, rdi; wParam
0x14000270d  mov     edx, 40Ah; Msg
0x140002712  call    cs:__imp_PostThreadMessageA
0x140002718  test    eax, eax
0x14000271a  jnz     short loc_14000272B
0x14000271c  mov     rax, [rdi]
0x14000271f  mov     rcx, rdi
0x140002722  mov     rax, [rax+10h]
0x140002726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000272b  mov     rbx, [rsp+28h+arg_0]
0x140002730  add     rsp, 20h
0x140002734  pop     rdi
0x140002735  retn
```
