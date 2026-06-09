# dllmain_crt_dispatch

- ea: `0x180001300`
- end: `0x180001350`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014e4`

## callees

- `0x180001300`
- `0x180001358`
- `0x180001458`
- `0x1800017e8`
- `0x180001818`

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
0x180001300  sub     rsp, 28h
0x180001304  test    edx, edx
0x180001306  jz      short loc_180001341
0x180001308  sub     edx, 1
0x18000130b  jz      short loc_180001335
0x18000130d  sub     edx, 1
0x180001310  jz      short loc_180001328
0x180001312  cmp     edx, 1
0x180001315  jz      short loc_180001321
0x180001317  mov     eax, 1
0x18000131c  add     rsp, 28h
0x180001320  retn
0x180001321  call    __scrt_dllmain_crt_thread_detach
0x180001326  jmp     short loc_18000132D
0x180001328  call    __scrt_dllmain_crt_thread_attach
0x18000132d  movzx   eax, al
0x180001330  add     rsp, 28h
0x180001334  retn
0x180001335  mov     rdx, r8
0x180001338  add     rsp, 28h
0x18000133c  jmp     dllmain_crt_process_attach
0x180001341  test    r8, r8
0x180001344  setnz   cl
0x180001347  add     rsp, 28h
0x18000134b  jmp     dllmain_crt_process_detach
```
