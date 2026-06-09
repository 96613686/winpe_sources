# dllmain_crt_dispatch

- ea: `0x180004fb0`
- end: `0x180005000`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180005194`

## callees

- `0x180004fb0`
- `0x180005008`
- `0x180005108`
- `0x1800053d0`
- `0x180005400`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 1;
    LOBYTE(result) = _scrt_dllmain_crt_thread_detach();
  }
  else
  {
    LOBYTE(result) = _scrt_dllmain_crt_thread_attach();
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x180004fb0  sub     rsp, 28h
0x180004fb4  test    edx, edx
0x180004fb6  jz      short loc_180004FF1
0x180004fb8  sub     edx, 1
0x180004fbb  jz      short loc_180004FE5
0x180004fbd  sub     edx, 1
0x180004fc0  jz      short loc_180004FD8
0x180004fc2  cmp     edx, 1
0x180004fc5  jz      short loc_180004FD1
0x180004fc7  mov     eax, 1
0x180004fcc  add     rsp, 28h
0x180004fd0  retn
0x180004fd1  call    __scrt_dllmain_crt_thread_detach
0x180004fd6  jmp     short loc_180004FDD
0x180004fd8  call    __scrt_dllmain_crt_thread_attach
0x180004fdd  movzx   eax, al
0x180004fe0  add     rsp, 28h
0x180004fe4  retn
0x180004fe5  mov     rdx, r8
0x180004fe8  add     rsp, 28h
0x180004fec  jmp     dllmain_crt_process_attach
0x180004ff1  test    r8, r8
0x180004ff4  setnz   cl
0x180004ff7  add     rsp, 28h
0x180004ffb  jmp     dllmain_crt_process_detach
```
