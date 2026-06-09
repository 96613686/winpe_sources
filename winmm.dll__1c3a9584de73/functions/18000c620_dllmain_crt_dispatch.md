# dllmain_crt_dispatch

- ea: `0x18000c620`
- end: `0x18000c670`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c804`

## callees

- `0x18000c620`
- `0x18000c678`
- `0x18000c778`
- `0x18000cb2c`
- `0x18000cb5c`

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
0x18000c620  sub     rsp, 28h
0x18000c624  test    edx, edx
0x18000c626  jz      short loc_18000C661
0x18000c628  sub     edx, 1
0x18000c62b  jz      short loc_18000C655
0x18000c62d  sub     edx, 1
0x18000c630  jz      short loc_18000C648
0x18000c632  cmp     edx, 1
0x18000c635  jz      short loc_18000C641
0x18000c637  mov     eax, 1
0x18000c63c  add     rsp, 28h
0x18000c640  retn
0x18000c641  call    __scrt_dllmain_crt_thread_detach
0x18000c646  jmp     short loc_18000C64D
0x18000c648  call    __scrt_dllmain_crt_thread_attach
0x18000c64d  movzx   eax, al
0x18000c650  add     rsp, 28h
0x18000c654  retn
0x18000c655  mov     rdx, r8
0x18000c658  add     rsp, 28h
0x18000c65c  jmp     dllmain_crt_process_attach
0x18000c661  test    r8, r8
0x18000c664  setnz   cl
0x18000c667  add     rsp, 28h
0x18000c66b  jmp     dllmain_crt_process_detach
```
