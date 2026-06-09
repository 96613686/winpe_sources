# CThreadContext::RevertToPreviousToken(void)

- ea: `0x1800062ac`
- end: `0x1800062f8`
- name: `?RevertToPreviousToken@CThreadContext@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006160`
- `0x1800065d8`
- `0x180006ce0`

## callees

- `0x1800062ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800062c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800062c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062e2`

## pseudocode

```c
void __fastcall CThreadContext::RevertToPreviousToken(HANDLE *this)
{
  HANDLE v2; // rcx

  if ( *(_DWORD *)this )
  {
    SetThreadToken(0, this[1]);
    v2 = this[1];
    if ( v2 )
    {
      CloseHandle(v2);
      this[1] = 0;
    }
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800062ac  push    rbx
0x1800062ae  sub     rsp, 20h
0x1800062b2  cmp     dword ptr [rcx], 0
0x1800062b5  mov     rbx, rcx
0x1800062b8  jz      short loc_1800062DB
0x1800062ba  mov     rdx, [rcx+8]; Token
0x1800062be  xor     ecx, ecx; Thread
0x1800062c0  call    cs:__imp_SetThreadToken
0x1800062c7  nop     dword ptr [rax+rax+00h]
0x1800062cc  mov     rcx, [rbx+8]; hObject
0x1800062d0  test    rcx, rcx
0x1800062d3  jnz     short loc_1800062E2
0x1800062d5  mov     dword ptr [rbx], 0
0x1800062db  add     rsp, 20h
0x1800062df  pop     rbx
0x1800062e0  retn
0x1800062e2  call    cs:__imp_CloseHandle
0x1800062e9  nop     dword ptr [rax+rax+00h]
0x1800062ee  mov     qword ptr [rbx+8], 0
0x1800062f6  jmp     short loc_1800062D5
```
