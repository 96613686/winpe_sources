# dllmain_crt_dispatch

- ea: `0x180001b40`
- end: `0x180001b90`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d24`

## callees

- `0x180001b40`
- `0x180001b98`
- `0x180001c98`
- `0x180002040`
- `0x180002070`

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
0x180001b40  sub     rsp, 28h
0x180001b44  test    edx, edx
0x180001b46  jz      short loc_180001B81
0x180001b48  sub     edx, 1
0x180001b4b  jz      short loc_180001B75
0x180001b4d  sub     edx, 1
0x180001b50  jz      short loc_180001B68
0x180001b52  cmp     edx, 1
0x180001b55  jz      short loc_180001B61
0x180001b57  mov     eax, 1
0x180001b5c  add     rsp, 28h
0x180001b60  retn
0x180001b61  call    __scrt_dllmain_crt_thread_detach
0x180001b66  jmp     short loc_180001B6D
0x180001b68  call    __scrt_dllmain_crt_thread_attach
0x180001b6d  movzx   eax, al
0x180001b70  add     rsp, 28h
0x180001b74  retn
0x180001b75  mov     rdx, r8
0x180001b78  add     rsp, 28h
0x180001b7c  jmp     dllmain_crt_process_attach
0x180001b81  test    r8, r8
0x180001b84  setnz   cl
0x180001b87  add     rsp, 28h
0x180001b8b  jmp     dllmain_crt_process_detach
```
