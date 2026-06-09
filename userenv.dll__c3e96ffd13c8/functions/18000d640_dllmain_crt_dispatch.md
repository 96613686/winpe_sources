# dllmain_crt_dispatch

- ea: `0x18000d640`
- end: `0x18000d690`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d824`

## callees

- `0x18000d640`
- `0x18000d698`
- `0x18000d798`
- `0x18000da98`
- `0x18000dac8`

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
0x18000d640  sub     rsp, 28h
0x18000d644  test    edx, edx
0x18000d646  jz      short loc_18000D681
0x18000d648  sub     edx, 1
0x18000d64b  jz      short loc_18000D675
0x18000d64d  sub     edx, 1
0x18000d650  jz      short loc_18000D668
0x18000d652  cmp     edx, 1
0x18000d655  jz      short loc_18000D661
0x18000d657  mov     eax, 1
0x18000d65c  add     rsp, 28h
0x18000d660  retn
0x18000d661  call    __scrt_dllmain_crt_thread_detach
0x18000d666  jmp     short loc_18000D66D
0x18000d668  call    __scrt_dllmain_crt_thread_attach
0x18000d66d  movzx   eax, al
0x18000d670  add     rsp, 28h
0x18000d674  retn
0x18000d675  mov     rdx, r8
0x18000d678  add     rsp, 28h
0x18000d67c  jmp     dllmain_crt_process_attach
0x18000d681  test    r8, r8
0x18000d684  setnz   cl
0x18000d687  add     rsp, 28h
0x18000d68b  jmp     dllmain_crt_process_detach
```
