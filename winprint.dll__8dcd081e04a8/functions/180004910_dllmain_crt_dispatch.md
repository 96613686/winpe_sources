# dllmain_crt_dispatch

- ea: `0x180004910`
- end: `0x180004960`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004af4`

## callees

- `0x180004910`
- `0x180004968`
- `0x180004a68`
- `0x180004e38`
- `0x180004e68`

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
0x180004910  sub     rsp, 28h
0x180004914  test    edx, edx
0x180004916  jz      short loc_180004951
0x180004918  sub     edx, 1
0x18000491b  jz      short loc_180004945
0x18000491d  sub     edx, 1
0x180004920  jz      short loc_180004938
0x180004922  cmp     edx, 1
0x180004925  jz      short loc_180004931
0x180004927  mov     eax, 1
0x18000492c  add     rsp, 28h
0x180004930  retn
0x180004931  call    __scrt_dllmain_crt_thread_detach
0x180004936  jmp     short loc_18000493D
0x180004938  call    __scrt_dllmain_crt_thread_attach
0x18000493d  movzx   eax, al
0x180004940  add     rsp, 28h
0x180004944  retn
0x180004945  mov     rdx, r8
0x180004948  add     rsp, 28h
0x18000494c  jmp     dllmain_crt_process_attach
0x180004951  test    r8, r8
0x180004954  setnz   cl
0x180004957  add     rsp, 28h
0x18000495b  jmp     dllmain_crt_process_detach
```
