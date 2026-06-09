# CWSHRemote::ThreadProc(void *)

- ea: `0x140002d50`
- end: `0x140002dab`
- name: `?ThreadProc@CWSHRemote@@CAXPEAX@Z`
- size: `91`
- prototype: `void __cdecl(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002310`
- `0x140002d50`
- `0x140018010`

## import_xrefs

- `msvcrt!_endthread` at `0x140002da4`
- `KERNEL32!GetCurrentThreadId` at `0x140002d5d`
- `KERNEL32!GetCurrentThreadId` at `0x140002d5d`
- `ole32!CoUninitialize` at `0x140002d94`
- `ole32!CoUninitialize` at `0x140002d94`
- `ole32!CoInitialize` at `0x140002d6a`
- `ole32!CoInitialize` at `0x140002d6a`

## pseudocode

```c
void __fastcall CWSHRemote::ThreadProc(_DWORD *a1)
{
  int v2; // edi

  a1[9] = GetCurrentThreadId();
  v2 = 0;
  if ( CoInitialize(0) >= 0 )
  {
    v2 = 1;
    CWSHRemote::DoScript((WPARAM)a1);
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v2 )
    CoUninitialize();
  _endthread();
}

```

## disassembly

```asm
0x140002d50  mov     [rsp+arg_0], rbx
0x140002d55  push    rdi
0x140002d56  sub     rsp, 20h
0x140002d5a  mov     rbx, rcx
0x140002d5d  call    cs:__imp_GetCurrentThreadId
0x140002d63  xor     ecx, ecx; pvReserved
0x140002d65  mov     [rbx+24h], eax
0x140002d68  xor     edi, edi
0x140002d6a  call    cs:__imp_CoInitialize
0x140002d70  test    eax, eax
0x140002d72  js      short loc_140002D81
0x140002d74  mov     rcx, rbx; wParam
0x140002d77  mov     edi, 1
0x140002d7c  call    ?DoScript@CWSHRemote@@AEAAJXZ; CWSHRemote::DoScript(void)
0x140002d81  mov     rax, [rbx]
0x140002d84  mov     rcx, rbx
0x140002d87  mov     rax, [rax+10h]
0x140002d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d90  test    edi, edi
0x140002d92  jz      short loc_140002D9A
0x140002d94  call    cs:__imp_CoUninitialize
0x140002d9a  mov     rbx, [rsp+28h+arg_0]
0x140002d9f  add     rsp, 20h
0x140002da3  pop     rdi
0x140002da4  jmp     cs:__imp__endthread
```
