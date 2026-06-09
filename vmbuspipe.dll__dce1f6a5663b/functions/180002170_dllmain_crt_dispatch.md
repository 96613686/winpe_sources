# dllmain_crt_dispatch

- ea: `0x180002170`
- end: `0x1800021c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002354`

## callees

- `0x180002170`
- `0x1800021c8`
- `0x1800022c8`
- `0x1800025c0`
- `0x1800025f0`

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
0x180002170  sub     rsp, 28h
0x180002174  test    edx, edx
0x180002176  jz      short loc_1800021B1
0x180002178  sub     edx, 1
0x18000217b  jz      short loc_1800021A5
0x18000217d  sub     edx, 1
0x180002180  jz      short loc_180002198
0x180002182  cmp     edx, 1
0x180002185  jz      short loc_180002191
0x180002187  mov     eax, 1
0x18000218c  add     rsp, 28h
0x180002190  retn
0x180002191  call    __scrt_dllmain_crt_thread_detach
0x180002196  jmp     short loc_18000219D
0x180002198  call    __scrt_dllmain_crt_thread_attach
0x18000219d  movzx   eax, al
0x1800021a0  add     rsp, 28h
0x1800021a4  retn
0x1800021a5  mov     rdx, r8
0x1800021a8  add     rsp, 28h
0x1800021ac  jmp     dllmain_crt_process_attach
0x1800021b1  test    r8, r8
0x1800021b4  setnz   cl
0x1800021b7  add     rsp, 28h
0x1800021bb  jmp     dllmain_crt_process_detach
```
