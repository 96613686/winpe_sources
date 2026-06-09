# dllmain_crt_dispatch

- ea: `0x18000e2d0`
- end: `0x18000e320`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e4b4`

## callees

- `0x18000e2d0`
- `0x18000e328`
- `0x18000e428`
- `0x18000e728`
- `0x18000e758`

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
0x18000e2d0  sub     rsp, 28h
0x18000e2d4  test    edx, edx
0x18000e2d6  jz      short loc_18000E311
0x18000e2d8  sub     edx, 1
0x18000e2db  jz      short loc_18000E305
0x18000e2dd  sub     edx, 1
0x18000e2e0  jz      short loc_18000E2F8
0x18000e2e2  cmp     edx, 1
0x18000e2e5  jz      short loc_18000E2F1
0x18000e2e7  mov     eax, 1
0x18000e2ec  add     rsp, 28h
0x18000e2f0  retn
0x18000e2f1  call    __scrt_dllmain_crt_thread_detach
0x18000e2f6  jmp     short loc_18000E2FD
0x18000e2f8  call    __scrt_dllmain_crt_thread_attach
0x18000e2fd  movzx   eax, al
0x18000e300  add     rsp, 28h
0x18000e304  retn
0x18000e305  mov     rdx, r8
0x18000e308  add     rsp, 28h
0x18000e30c  jmp     dllmain_crt_process_attach
0x18000e311  test    r8, r8
0x18000e314  setnz   cl
0x18000e317  add     rsp, 28h
0x18000e31b  jmp     dllmain_crt_process_detach
```
