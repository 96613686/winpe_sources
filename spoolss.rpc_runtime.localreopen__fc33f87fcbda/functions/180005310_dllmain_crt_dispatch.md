# dllmain_crt_dispatch

- ea: `0x180005310`
- end: `0x180005360`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800054f4`

## callees

- `0x180005310`
- `0x180005368`
- `0x180005468`
- `0x180005730`
- `0x180005760`

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
0x180005310  sub     rsp, 28h
0x180005314  test    edx, edx
0x180005316  jz      short loc_180005351
0x180005318  sub     edx, 1
0x18000531b  jz      short loc_180005345
0x18000531d  sub     edx, 1
0x180005320  jz      short loc_180005338
0x180005322  cmp     edx, 1
0x180005325  jz      short loc_180005331
0x180005327  mov     eax, 1
0x18000532c  add     rsp, 28h
0x180005330  retn
0x180005331  call    __scrt_dllmain_crt_thread_detach
0x180005336  jmp     short loc_18000533D
0x180005338  call    __scrt_dllmain_crt_thread_attach
0x18000533d  movzx   eax, al
0x180005340  add     rsp, 28h
0x180005344  retn
0x180005345  mov     rdx, r8
0x180005348  add     rsp, 28h
0x18000534c  jmp     dllmain_crt_process_attach
0x180005351  test    r8, r8
0x180005354  setnz   cl
0x180005357  add     rsp, 28h
0x18000535b  jmp     dllmain_crt_process_detach
```
