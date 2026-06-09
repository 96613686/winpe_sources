# dllmain_crt_dispatch

- ea: `0x1800013f0`
- end: `0x180001440`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015d4`

## callees

- `0x1800013f0`
- `0x180001448`
- `0x180001548`
- `0x180001858`
- `0x180001888`

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
0x1800013f0  sub     rsp, 28h
0x1800013f4  test    edx, edx
0x1800013f6  jz      short loc_180001431
0x1800013f8  sub     edx, 1
0x1800013fb  jz      short loc_180001425
0x1800013fd  sub     edx, 1
0x180001400  jz      short loc_180001418
0x180001402  cmp     edx, 1
0x180001405  jz      short loc_180001411
0x180001407  mov     eax, 1
0x18000140c  add     rsp, 28h
0x180001410  retn
0x180001411  call    __scrt_dllmain_crt_thread_detach
0x180001416  jmp     short loc_18000141D
0x180001418  call    __scrt_dllmain_crt_thread_attach
0x18000141d  movzx   eax, al
0x180001420  add     rsp, 28h
0x180001424  retn
0x180001425  mov     rdx, r8
0x180001428  add     rsp, 28h
0x18000142c  jmp     dllmain_crt_process_attach
0x180001431  test    r8, r8
0x180001434  setnz   cl
0x180001437  add     rsp, 28h
0x18000143b  jmp     dllmain_crt_process_detach
```
