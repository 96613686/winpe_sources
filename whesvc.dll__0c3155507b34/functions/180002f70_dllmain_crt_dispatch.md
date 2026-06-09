# dllmain_crt_dispatch

- ea: `0x180002f70`
- end: `0x180002fc0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003154`

## callees

- `0x180002f70`
- `0x180002fc8`
- `0x1800030c8`
- `0x1800033c8`
- `0x1800033f8`

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
0x180002f70  sub     rsp, 28h
0x180002f74  test    edx, edx
0x180002f76  jz      short loc_180002FB1
0x180002f78  sub     edx, 1
0x180002f7b  jz      short loc_180002FA5
0x180002f7d  sub     edx, 1
0x180002f80  jz      short loc_180002F98
0x180002f82  cmp     edx, 1
0x180002f85  jz      short loc_180002F91
0x180002f87  mov     eax, 1
0x180002f8c  add     rsp, 28h
0x180002f90  retn
0x180002f91  call    __scrt_dllmain_crt_thread_detach
0x180002f96  jmp     short loc_180002F9D
0x180002f98  call    __scrt_dllmain_crt_thread_attach
0x180002f9d  movzx   eax, al
0x180002fa0  add     rsp, 28h
0x180002fa4  retn
0x180002fa5  mov     rdx, r8
0x180002fa8  add     rsp, 28h
0x180002fac  jmp     dllmain_crt_process_attach
0x180002fb1  test    r8, r8
0x180002fb4  setnz   cl
0x180002fb7  add     rsp, 28h
0x180002fbb  jmp     dllmain_crt_process_detach
```
