# dllmain_crt_dispatch

- ea: `0x180001d60`
- end: `0x180001db0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f44`

## callees

- `0x180001d60`
- `0x180001db8`
- `0x180001eb8`
- `0x180002218`
- `0x180002248`

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
0x180001d60  sub     rsp, 28h
0x180001d64  test    edx, edx
0x180001d66  jz      short loc_180001DA1
0x180001d68  sub     edx, 1
0x180001d6b  jz      short loc_180001D95
0x180001d6d  sub     edx, 1
0x180001d70  jz      short loc_180001D88
0x180001d72  cmp     edx, 1
0x180001d75  jz      short loc_180001D81
0x180001d77  mov     eax, 1
0x180001d7c  add     rsp, 28h
0x180001d80  retn
0x180001d81  call    __scrt_dllmain_crt_thread_detach
0x180001d86  jmp     short loc_180001D8D
0x180001d88  call    __scrt_dllmain_crt_thread_attach
0x180001d8d  movzx   eax, al
0x180001d90  add     rsp, 28h
0x180001d94  retn
0x180001d95  mov     rdx, r8
0x180001d98  add     rsp, 28h
0x180001d9c  jmp     dllmain_crt_process_attach
0x180001da1  test    r8, r8
0x180001da4  setnz   cl
0x180001da7  add     rsp, 28h
0x180001dab  jmp     dllmain_crt_process_detach
```
