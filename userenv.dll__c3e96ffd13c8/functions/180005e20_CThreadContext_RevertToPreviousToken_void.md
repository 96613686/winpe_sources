# CThreadContext::RevertToPreviousToken(void)

- ea: `0x180005e20`
- end: `0x180005e5f`
- name: `?RevertToPreviousToken@CThreadContext@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005de0`
- `0x1800067b0`

## callees

- `0x180005e20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005e34`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4f`

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
0x180005e20  push    rbx
0x180005e22  sub     rsp, 20h
0x180005e26  cmp     dword ptr [rcx], 0
0x180005e29  mov     rbx, rcx
0x180005e2c  jz      short loc_180005E49
0x180005e2e  mov     rdx, [rcx+8]; Token
0x180005e32  xor     ecx, ecx; Thread
0x180005e34  call    cs:__imp_SetThreadToken
0x180005e3a  mov     rcx, [rbx+8]; hObject
0x180005e3e  test    rcx, rcx
0x180005e41  jnz     short loc_180005E4F
0x180005e43  mov     dword ptr [rbx], 0
0x180005e49  add     rsp, 20h
0x180005e4d  pop     rbx
0x180005e4e  retn
0x180005e4f  call    cs:__imp_CloseHandle
0x180005e55  mov     qword ptr [rbx+8], 0
0x180005e5d  jmp     short loc_180005E43
```
