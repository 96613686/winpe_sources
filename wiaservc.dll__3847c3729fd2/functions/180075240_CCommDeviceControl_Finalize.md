# CCommDeviceControl_Finalize

- ea: `0x180075240`
- end: `0x1800752af`
- name: `CCommDeviceControl_Finalize`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180075240`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007528d`
- `KERNEL32!CloseHandle` at `0x18007528d`
- `api-ms-win-core-comm-l1-1-0!EscapeCommFunction` at `0x180075264`
- `api-ms-win-core-comm-l1-1-0!EscapeCommFunction` at `0x180075264`
- `api-ms-win-core-comm-l1-1-0!SetCommMask` at `0x180075252`
- `api-ms-win-core-comm-l1-1-0!SetCommMask` at `0x180075252`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x180075276`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x180075276`

## pseudocode

```c
int __fastcall CCommDeviceControl_Finalize(__int64 a1)
{
  char *v2; // rcx
  int result; // eax

  SetCommMask(*(HANDLE *)(a1 + 552), 0);
  EscapeCommFunction(*(HANDLE *)(a1 + 552), 6u);
  PurgeComm(*(HANDLE *)(a1 + 552), 0xFu);
  v2 = *(char **)(a1 + 552);
  result = (_DWORD)v2 - 1;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = CloseHandle(v2);
  *(_QWORD *)(a1 + 544) = 0;
  *(_QWORD *)(a1 + 552) = -1;
  return result;
}

```

## disassembly

```asm
0x180075240  push    rbx
0x180075242  sub     rsp, 20h
0x180075246  mov     rbx, rcx
0x180075249  xor     edx, edx; dwEvtMask
0x18007524b  mov     rcx, [rcx+228h]; hFile
0x180075252  call    cs:__imp_SetCommMask
0x180075258  mov     rcx, [rbx+228h]; hFile
0x18007525f  mov     edx, 6; dwFunc
0x180075264  call    cs:__imp_EscapeCommFunction
0x18007526a  mov     rcx, [rbx+228h]; hFile
0x180075271  mov     edx, 0Fh; dwFlags
0x180075276  call    cs:__imp_PurgeComm
0x18007527c  mov     rcx, [rbx+228h]; hObject
0x180075283  lea     rax, [rcx-1]
0x180075287  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007528b  ja      short loc_180075293
0x18007528d  call    cs:__imp_CloseHandle
0x180075293  mov     qword ptr [rbx+220h], 0
0x18007529e  mov     qword ptr [rbx+228h], 0FFFFFFFFFFFFFFFFh
0x1800752a9  add     rsp, 20h
0x1800752ad  pop     rbx
0x1800752ae  retn
```
