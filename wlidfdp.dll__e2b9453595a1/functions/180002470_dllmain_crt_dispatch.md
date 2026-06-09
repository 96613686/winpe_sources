# dllmain_crt_dispatch

- ea: `0x180002470`
- end: `0x1800024c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002654`

## callees

- `0x180002470`
- `0x1800024c8`
- `0x1800025c8`
- `0x1800028d8`
- `0x180002908`

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
0x180002470  sub     rsp, 28h
0x180002474  test    edx, edx
0x180002476  jz      short loc_1800024B1
0x180002478  sub     edx, 1
0x18000247b  jz      short loc_1800024A5
0x18000247d  sub     edx, 1
0x180002480  jz      short loc_180002498
0x180002482  cmp     edx, 1
0x180002485  jz      short loc_180002491
0x180002487  mov     eax, 1
0x18000248c  add     rsp, 28h
0x180002490  retn
0x180002491  call    __scrt_dllmain_crt_thread_detach
0x180002496  jmp     short loc_18000249D
0x180002498  call    __scrt_dllmain_crt_thread_attach
0x18000249d  movzx   eax, al
0x1800024a0  add     rsp, 28h
0x1800024a4  retn
0x1800024a5  mov     rdx, r8
0x1800024a8  add     rsp, 28h
0x1800024ac  jmp     dllmain_crt_process_attach
0x1800024b1  test    r8, r8
0x1800024b4  setnz   cl
0x1800024b7  add     rsp, 28h
0x1800024bb  jmp     dllmain_crt_process_detach
```
