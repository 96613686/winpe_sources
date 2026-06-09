# dllmain_crt_dispatch

- ea: `0x1004265b0`
- end: `0x100426600`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1004267b0`

## callees

- `0x1004265b0`
- `0x100426608`
- `0x100426724`
- `0x100426d9c`
- `0x100426dcc`

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
    return dllmain_crt_process_attach();
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
0x1004265b0  sub     rsp, 28h
0x1004265b4  test    edx, edx
0x1004265b6  jz      short loc_1004265F1
0x1004265b8  sub     edx, 1
0x1004265bb  jz      short loc_1004265E5
0x1004265bd  sub     edx, 1
0x1004265c0  jz      short loc_1004265D8
0x1004265c2  cmp     edx, 1
0x1004265c5  jz      short loc_1004265D1
0x1004265c7  mov     eax, 1
0x1004265cc  add     rsp, 28h
0x1004265d0  retn
0x1004265d1  call    __scrt_dllmain_crt_thread_detach
0x1004265d6  jmp     short loc_1004265DD
0x1004265d8  call    __scrt_dllmain_crt_thread_attach
0x1004265dd  movzx   eax, al
0x1004265e0  add     rsp, 28h
0x1004265e4  retn
0x1004265e5  mov     rdx, r8
0x1004265e8  add     rsp, 28h
0x1004265ec  jmp     dllmain_crt_process_attach
0x1004265f1  test    r8, r8
0x1004265f4  setnz   cl
0x1004265f7  add     rsp, 28h
0x1004265fb  jmp     dllmain_crt_process_detach
```
