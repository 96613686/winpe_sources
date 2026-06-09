# MonitorProc

- ea: `0x14000b0b0`
- end: `0x14000b12d`
- name: `MonitorProc`
- size: `125`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000b0b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000b0fc`
- `KERNEL32!CloseHandle` at `0x14000b109`
- `KERNEL32!CloseHandle` at `0x14000b0fc`
- `KERNEL32!CloseHandle` at `0x14000b109`
- `KERNEL32!WaitForSingleObject` at `0x14000b0c3`
- `KERNEL32!WaitForSingleObject` at `0x14000b0dc`
- `KERNEL32!WaitForSingleObject` at `0x14000b0c3`
- `KERNEL32!WaitForSingleObject` at `0x14000b0dc`
- `USER32!PostThreadMessageW` at `0x14000b11f`
- `USER32!PostThreadMessageW` at `0x14000b11f`

## pseudocode

```c
__int64 __fastcall MonitorProc(LPVOID lpThreadParameter)
{
  void *v2; // rcx

  do
  {
    WaitForSingleObject(*((HANDLE *)lpThreadParameter + 32), 0xFFFFFFFF);
    do
    {
      v2 = (void *)*((_QWORD *)lpThreadParameter + 32);
      *((_BYTE *)lpThreadParameter + 272) = 0;
    }
    while ( !WaitForSingleObject(v2, 0x1388u) );
  }
  while ( *((_BYTE *)lpThreadParameter + 272) || *((_DWORD *)lpThreadParameter + 10) );
  CloseHandle(*((HANDLE *)lpThreadParameter + 32));
  CloseHandle(*((HANDLE *)lpThreadParameter + 33));
  PostThreadMessageW(*((_DWORD *)lpThreadParameter + 62), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14000b0b0  push    rbx
0x14000b0b2  sub     rsp, 20h
0x14000b0b6  mov     rbx, rcx
0x14000b0b9  mov     rcx, [rbx+100h]; hHandle
0x14000b0c0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000b0c3  call    cs:__imp_WaitForSingleObject
0x14000b0c9  mov     rcx, [rbx+100h]; hHandle
0x14000b0d0  mov     edx, 1388h; dwMilliseconds
0x14000b0d5  mov     byte ptr [rbx+110h], 0
0x14000b0dc  call    cs:__imp_WaitForSingleObject
0x14000b0e2  test    eax, eax
0x14000b0e4  jz      short loc_14000B0C9
0x14000b0e6  cmp     byte ptr [rbx+110h], 0
0x14000b0ed  jnz     short loc_14000B0B9
0x14000b0ef  cmp     dword ptr [rbx+28h], 0
0x14000b0f3  jnz     short loc_14000B0B9
0x14000b0f5  mov     rcx, [rbx+100h]; hObject
0x14000b0fc  call    cs:__imp_CloseHandle
0x14000b102  mov     rcx, [rbx+108h]; hObject
0x14000b109  call    cs:__imp_CloseHandle
0x14000b10f  mov     ecx, [rbx+0F8h]; idThread
0x14000b115  xor     r9d, r9d; lParam
0x14000b118  xor     r8d, r8d; wParam
0x14000b11b  lea     edx, [r9+12h]; Msg
0x14000b11f  call    cs:__imp_PostThreadMessageW
0x14000b125  xor     eax, eax
0x14000b127  add     rsp, 20h
0x14000b12b  pop     rbx
0x14000b12c  retn
```
