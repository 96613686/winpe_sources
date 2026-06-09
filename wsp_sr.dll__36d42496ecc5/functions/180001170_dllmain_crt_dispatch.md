# dllmain_crt_dispatch

- ea: `0x180001170`
- end: `0x1800011c0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001354`

## callees

- `0x180001170`
- `0x1800011c8`
- `0x1800012c8`
- `0x1800016b4`
- `0x1800016e4`

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
0x180001170  sub     rsp, 28h
0x180001174  test    edx, edx
0x180001176  jz      short loc_1800011B1
0x180001178  sub     edx, 1
0x18000117b  jz      short loc_1800011A5
0x18000117d  sub     edx, 1
0x180001180  jz      short loc_180001198
0x180001182  cmp     edx, 1
0x180001185  jz      short loc_180001191
0x180001187  mov     eax, 1
0x18000118c  add     rsp, 28h
0x180001190  retn
0x180001191  call    __scrt_dllmain_crt_thread_detach
0x180001196  jmp     short loc_18000119D
0x180001198  call    __scrt_dllmain_crt_thread_attach
0x18000119d  movzx   eax, al
0x1800011a0  add     rsp, 28h
0x1800011a4  retn
0x1800011a5  mov     rdx, r8
0x1800011a8  add     rsp, 28h
0x1800011ac  jmp     dllmain_crt_process_attach
0x1800011b1  test    r8, r8
0x1800011b4  setnz   cl
0x1800011b7  add     rsp, 28h
0x1800011bb  jmp     dllmain_crt_process_detach
```
