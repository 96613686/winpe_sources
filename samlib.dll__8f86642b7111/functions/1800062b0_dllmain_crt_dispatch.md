# dllmain_crt_dispatch

- ea: `0x1800062b0`
- end: `0x180006300`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180006494`

## callees

- `0x1800062b0`
- `0x180006308`
- `0x180006408`
- `0x1800067d8`
- `0x180006808`

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
0x1800062b0  sub     rsp, 28h
0x1800062b4  test    edx, edx
0x1800062b6  jz      short loc_1800062F1
0x1800062b8  sub     edx, 1
0x1800062bb  jz      short loc_1800062E5
0x1800062bd  sub     edx, 1
0x1800062c0  jz      short loc_1800062D8
0x1800062c2  cmp     edx, 1
0x1800062c5  jz      short loc_1800062D1
0x1800062c7  mov     eax, 1
0x1800062cc  add     rsp, 28h
0x1800062d0  retn
0x1800062d1  call    __scrt_dllmain_crt_thread_detach
0x1800062d6  jmp     short loc_1800062DD
0x1800062d8  call    __scrt_dllmain_crt_thread_attach
0x1800062dd  movzx   eax, al
0x1800062e0  add     rsp, 28h
0x1800062e4  retn
0x1800062e5  mov     rdx, r8
0x1800062e8  add     rsp, 28h
0x1800062ec  jmp     dllmain_crt_process_attach
0x1800062f1  test    r8, r8
0x1800062f4  setnz   cl
0x1800062f7  add     rsp, 28h
0x1800062fb  jmp     dllmain_crt_process_detach
```
