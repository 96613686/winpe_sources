# dllmain_crt_dispatch

- ea: `0x180001260`
- end: `0x1800012b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001444`

## callees

- `0x180001260`
- `0x1800012b8`
- `0x1800013b8`
- `0x180001680`
- `0x1800016b0`

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
0x180001260  sub     rsp, 28h
0x180001264  test    edx, edx
0x180001266  jz      short loc_1800012A1
0x180001268  sub     edx, 1
0x18000126b  jz      short loc_180001295
0x18000126d  sub     edx, 1
0x180001270  jz      short loc_180001288
0x180001272  cmp     edx, 1
0x180001275  jz      short loc_180001281
0x180001277  mov     eax, 1
0x18000127c  add     rsp, 28h
0x180001280  retn
0x180001281  call    __scrt_dllmain_crt_thread_detach
0x180001286  jmp     short loc_18000128D
0x180001288  call    __scrt_dllmain_crt_thread_attach
0x18000128d  movzx   eax, al
0x180001290  add     rsp, 28h
0x180001294  retn
0x180001295  mov     rdx, r8
0x180001298  add     rsp, 28h
0x18000129c  jmp     dllmain_crt_process_attach
0x1800012a1  test    r8, r8
0x1800012a4  setnz   cl
0x1800012a7  add     rsp, 28h
0x1800012ab  jmp     dllmain_crt_process_detach
```
