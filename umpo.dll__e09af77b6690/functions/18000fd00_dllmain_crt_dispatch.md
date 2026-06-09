# dllmain_crt_dispatch

- ea: `0x18000fd00`
- end: `0x18000fd50`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000fee4`

## callees

- `0x18000fd00`
- `0x18000fd58`
- `0x18000fe58`
- `0x180010280`
- `0x1800102b0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x18000fd00  sub     rsp, 28h
0x18000fd04  test    edx, edx
0x18000fd06  jz      short loc_18000FD41
0x18000fd08  sub     edx, 1
0x18000fd0b  jz      short loc_18000FD35
0x18000fd0d  sub     edx, 1
0x18000fd10  jz      short loc_18000FD28
0x18000fd12  cmp     edx, 1
0x18000fd15  jz      short loc_18000FD21
0x18000fd17  mov     eax, 1
0x18000fd1c  add     rsp, 28h
0x18000fd20  retn
0x18000fd21  call    __scrt_dllmain_crt_thread_detach
0x18000fd26  jmp     short loc_18000FD2D
0x18000fd28  call    __scrt_dllmain_crt_thread_attach
0x18000fd2d  movzx   eax, al
0x18000fd30  add     rsp, 28h
0x18000fd34  retn
0x18000fd35  mov     rdx, r8
0x18000fd38  add     rsp, 28h
0x18000fd3c  jmp     dllmain_crt_process_attach
0x18000fd41  test    r8, r8
0x18000fd44  setnz   cl
0x18000fd47  add     rsp, 28h
0x18000fd4b  jmp     dllmain_crt_process_detach
```
