# WP_IPM::Terminate(void)

- ea: `0x18000840c`
- end: `0x18000846c`
- name: `?Terminate@WP_IPM@@QEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002c20`
- `0x180007958`

## callees

- `0x18000831c`
- `0x18000840c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000844c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000844c`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x18000841e`
- `iisutil!?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ` at `0x18000841e`

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
0x18000840c  push    rbx
0x18000840e  sub     rsp, 20h
0x180008412  mov     rbx, rcx
0x180008415  mov     rcx, [rcx+8]
0x180008419  test    rcx, rcx
0x18000841c  jz      short loc_18000842C
0x18000841e  call    cs:__imp_?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ; IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x180008424  mov     qword ptr [rbx+8], 0
0x18000842c  mov     rcx, [rbx+10h]; hObject
0x180008430  test    rcx, rcx
0x180008433  jz      short loc_180008443
0x180008435  call    cs:__imp_CloseHandle
0x18000843b  mov     qword ptr [rbx+10h], 0
0x180008443  mov     rcx, [rbx+18h]; hObject
0x180008447  test    rcx, rcx
0x18000844a  jz      short loc_18000845A
0x18000844c  call    cs:__imp_CloseHandle
0x180008452  mov     qword ptr [rbx+18h], 0
0x18000845a  xor     edx, edx; int
0x18000845c  mov     rcx, rbx; this
0x18000845f  call    ?SetupCounters@WP_IPM@@AEAAXH@Z; WP_IPM::SetupCounters(int)
0x180008464  xor     eax, eax
0x180008466  add     rsp, 20h
0x18000846a  pop     rbx
0x18000846b  retn
```
