# WP_IPM::Terminate(void)

- ea: `0x180008cfc`
- end: `0x180008d6f`
- name: `?Terminate@WP_IPM@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002dbc`
- `0x180008128`

## callees

- `0x180008c0c`
- `0x180008cfc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d48`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x180008d0e`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x180008d0e`

## pseudocode

```c
__int64 __fastcall WP_IPM::Terminate(WP_IPM *this)
{
  IPM_MESSAGE_PIPE *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (IPM_MESSAGE_PIPE *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 3) = 0;
  }
  WP_IPM::SetupCounters(this, 0);
  return 0;
}

```

## disassembly

```asm
0x180008cfc  push    rbx
0x180008cfe  sub     rsp, 20h
0x180008d02  mov     rbx, rcx
0x180008d05  mov     rcx, [rcx+8]
0x180008d09  test    rcx, rcx
0x180008d0c  jz      short loc_180008D22
0x180008d0e  call    cs:__imp_?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ; IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180008d15  nop     dword ptr [rax+rax+00h]
0x180008d1a  mov     qword ptr [rbx+8], 0
0x180008d22  mov     rcx, [rbx+10h]; hObject
0x180008d26  test    rcx, rcx
0x180008d29  jz      short loc_180008D3F
0x180008d2b  call    cs:__imp_CloseHandle
0x180008d32  nop     dword ptr [rax+rax+00h]
0x180008d37  mov     qword ptr [rbx+10h], 0
0x180008d3f  mov     rcx, [rbx+18h]; hObject
0x180008d43  test    rcx, rcx
0x180008d46  jz      short loc_180008D5C
0x180008d48  call    cs:__imp_CloseHandle
0x180008d4f  nop     dword ptr [rax+rax+00h]
0x180008d54  mov     qword ptr [rbx+18h], 0
0x180008d5c  xor     edx, edx; int
0x180008d5e  mov     rcx, rbx; this
0x180008d61  call    ?SetupCounters@WP_IPM@@AEAAXH@Z; WP_IPM::SetupCounters(int)
0x180008d66  xor     eax, eax
0x180008d68  add     rsp, 20h
0x180008d6c  pop     rbx
0x180008d6d  retn
```
