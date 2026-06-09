# TraceCloseClientConsoleW

- ea: `0x180005e98`
- end: `0x180005f35`
- name: `TraceCloseClientConsoleW`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001100`
- `0x180001c20`
- `0x180001fa0`
- `0x180002ae0`
- `0x180002c80`
- `0x180006fc4`

## callees

- `0x1800026d0`
- `0x180005e98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f07`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x180005f13`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x180005f13`

## pseudocode

```c
__int64 __fastcall TraceCloseClientConsoleW(__int64 a1, __int64 a2)
{
  char *v4; // rcx
  int v5; // eax
  int v6; // eax
  char *v7; // rcx

  if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
  {
    v4 = *(char **)(a2 + 264);
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    v5 = *(_DWORD *)(a2 + 60);
    *(_QWORD *)(a2 + 264) = 0;
    if ( *(_DWORD *)(a1 + 64) == v5 )
      TraceUpdateConsoleOwner(a1, 1);
    v6 = *(_DWORD *)(a1 + 64);
    if ( v6 == 60 || v6 == *(_DWORD *)(a2 + 60) )
    {
      v7 = *(char **)(a1 + 72);
      *(_DWORD *)(a1 + 64) = 60;
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v7);
      if ( *(_DWORD *)(a1 + 68) == 1 )
      {
        FreeConsole();
        *(_DWORD *)(a1 + 68) = 0;
      }
      *(_QWORD *)(a1 + 72) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005e98  mov     [rsp+arg_0], rbx
0x180005e9d  push    rdi
0x180005e9e  sub     rsp, 20h
0x180005ea2  test    byte ptr [rcx+38h], 4
0x180005ea6  mov     rdi, rdx
0x180005ea9  mov     rbx, rcx
0x180005eac  jz      short loc_180005F28
0x180005eae  mov     rcx, [rdx+108h]; hObject
0x180005eb5  lea     rax, [rcx-1]
0x180005eb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005ebd  ja      short loc_180005EC5
0x180005ebf  call    cs:__imp_CloseHandle
0x180005ec5  mov     eax, [rdi+3Ch]
0x180005ec8  mov     qword ptr [rdi+108h], 0
0x180005ed3  cmp     [rbx+40h], eax
0x180005ed6  jnz     short loc_180005EE5
0x180005ed8  mov     edx, 1
0x180005edd  mov     rcx, rbx
0x180005ee0  call    TraceUpdateConsoleOwner
0x180005ee5  mov     eax, [rbx+40h]
0x180005ee8  cmp     eax, 3Ch ; '<'
0x180005eeb  jz      short loc_180005EF2
0x180005eed  cmp     eax, [rdi+3Ch]
0x180005ef0  jnz     short loc_180005F28
0x180005ef2  mov     rcx, [rbx+48h]; hObject
0x180005ef6  mov     dword ptr [rbx+40h], 3Ch ; '<'
0x180005efd  lea     rax, [rcx-1]
0x180005f01  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005f05  ja      short loc_180005F0D
0x180005f07  call    cs:__imp_CloseHandle
0x180005f0d  cmp     dword ptr [rbx+44h], 1
0x180005f11  jnz     short loc_180005F20
0x180005f13  call    cs:__imp_FreeConsole
0x180005f19  mov     dword ptr [rbx+44h], 0
0x180005f20  mov     qword ptr [rbx+48h], 0
0x180005f28  mov     rbx, [rsp+28h+arg_0]
0x180005f2d  xor     eax, eax
0x180005f2f  add     rsp, 20h
0x180005f33  pop     rdi
0x180005f34  retn
```
