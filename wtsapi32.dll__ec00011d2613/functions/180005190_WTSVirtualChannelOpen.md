# _WTSVirtualChannelOpen

- ea: `0x180005190`
- end: `0x180005208`
- name: `_WTSVirtualChannelOpen`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005170`
- `0x180006570`

## callees

- `0x180005190`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800051cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800051cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005200`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800051a8`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800051a8`

## pseudocode

```c
_QWORD *__fastcall WTSVirtualChannelOpen(__int64 a1, __int64 a2, _QWORD *a3, int a4)
{
  int v5; // esi
  void *v7; // rbx
  _QWORD *result; // rax

  v5 = a2;
  v7 = (void *)WinStationVirtualOpenEx(a1, a2, a3, a4 & 0xFFFFFF3F);
  if ( !v7 )
    return 0;
  result = LocalAlloc(0x40u, 0x28u);
  if ( !result )
  {
    CloseHandle(v7);
    return 0;
  }
  *(_DWORD *)result = 1145586518;
  result[1] = a1;
  *((_DWORD *)result + 4) = v5;
  result[3] = v7;
  result[4] = *a3;
  return result;
}

```

## disassembly

```asm
0x180005190  push    rbx
0x180005192  push    rbp
0x180005193  push    rsi
0x180005194  push    rdi
0x180005195  sub     rsp, 28h
0x180005199  and     r9d, 0FFFFFF3Fh
0x1800051a0  mov     rdi, r8
0x1800051a3  mov     esi, edx
0x1800051a5  mov     rbp, rcx
0x1800051a8  call    cs:__imp_WinStationVirtualOpenEx
0x1800051ae  mov     rbx, rax
0x1800051b1  test    rax, rax
0x1800051b4  jnz     short loc_1800051C1
0x1800051b6  xor     eax, eax
0x1800051b8  add     rsp, 28h
0x1800051bc  pop     rdi
0x1800051bd  pop     rsi
0x1800051be  pop     rbp
0x1800051bf  pop     rbx
0x1800051c0  retn
0x1800051c1  mov     edx, 28h ; '('; uBytes
0x1800051c6  mov     ecx, 40h ; '@'; uFlags
0x1800051cb  call    cs:__imp_LocalAlloc
0x1800051d1  mov     rcx, rax
0x1800051d4  test    rax, rax
0x1800051d7  jz      short loc_1800051FD
0x1800051d9  mov     dword ptr [rax], 44484356h
0x1800051df  mov     [rax+8], rbp
0x1800051e3  mov     [rax+10h], esi
0x1800051e6  mov     [rax+18h], rbx
0x1800051ea  mov     rax, [rdi]
0x1800051ed  mov     [rcx+20h], rax
0x1800051f1  mov     rax, rcx
0x1800051f4  add     rsp, 28h
0x1800051f8  pop     rdi
0x1800051f9  pop     rsi
0x1800051fa  pop     rbp
0x1800051fb  pop     rbx
0x1800051fc  retn
0x1800051fd  mov     rcx, rbx; hObject
0x180005200  call    cs:__imp_CloseHandle
0x180005206  jmp     short loc_1800051B6
```
