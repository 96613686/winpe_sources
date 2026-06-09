# dllmain_crt_dispatch

- ea: `0x180002610`
- end: `0x180002660`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800027f4`

## callees

- `0x180002610`
- `0x180002668`
- `0x180002768`
- `0x180002b38`
- `0x180002b68`

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
0x180002610  sub     rsp, 28h
0x180002614  test    edx, edx
0x180002616  jz      short loc_180002651
0x180002618  sub     edx, 1
0x18000261b  jz      short loc_180002645
0x18000261d  sub     edx, 1
0x180002620  jz      short loc_180002638
0x180002622  cmp     edx, 1
0x180002625  jz      short loc_180002631
0x180002627  mov     eax, 1
0x18000262c  add     rsp, 28h
0x180002630  retn
0x180002631  call    __scrt_dllmain_crt_thread_detach
0x180002636  jmp     short loc_18000263D
0x180002638  call    __scrt_dllmain_crt_thread_attach
0x18000263d  movzx   eax, al
0x180002640  add     rsp, 28h
0x180002644  retn
0x180002645  mov     rdx, r8
0x180002648  add     rsp, 28h
0x18000264c  jmp     dllmain_crt_process_attach
0x180002651  test    r8, r8
0x180002654  setnz   cl
0x180002657  add     rsp, 28h
0x18000265b  jmp     dllmain_crt_process_detach
```
