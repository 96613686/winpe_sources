# dllmain_crt_dispatch

- ea: `0x1800341a0`
- end: `0x1800341f0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180034384`

## callees

- `0x1800341a0`
- `0x1800341f8`
- `0x1800342f8`
- `0x1800345c0`
- `0x1800345f0`

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
0x1800341a0  sub     rsp, 28h
0x1800341a4  test    edx, edx
0x1800341a6  jz      short loc_1800341E1
0x1800341a8  sub     edx, 1
0x1800341ab  jz      short loc_1800341D5
0x1800341ad  sub     edx, 1
0x1800341b0  jz      short loc_1800341C8
0x1800341b2  cmp     edx, 1
0x1800341b5  jz      short loc_1800341C1
0x1800341b7  mov     eax, 1
0x1800341bc  add     rsp, 28h
0x1800341c0  retn
0x1800341c1  call    __scrt_dllmain_crt_thread_detach
0x1800341c6  jmp     short loc_1800341CD
0x1800341c8  call    __scrt_dllmain_crt_thread_attach
0x1800341cd  movzx   eax, al
0x1800341d0  add     rsp, 28h
0x1800341d4  retn
0x1800341d5  mov     rdx, r8
0x1800341d8  add     rsp, 28h
0x1800341dc  jmp     dllmain_crt_process_attach
0x1800341e1  test    r8, r8
0x1800341e4  setnz   cl
0x1800341e7  add     rsp, 28h
0x1800341eb  jmp     dllmain_crt_process_detach
```
