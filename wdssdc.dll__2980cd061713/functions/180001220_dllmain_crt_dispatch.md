# dllmain_crt_dispatch

- ea: `0x180001220`
- end: `0x180001270`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000141c`

## callees

- `0x180001220`
- `0x180001278`
- `0x180001390`
- `0x1800019f0`
- `0x180001a20`

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
0x180001220  sub     rsp, 28h
0x180001224  test    edx, edx
0x180001226  jz      short loc_180001261
0x180001228  sub     edx, 1
0x18000122b  jz      short loc_180001255
0x18000122d  sub     edx, 1
0x180001230  jz      short loc_180001248
0x180001232  cmp     edx, 1
0x180001235  jz      short loc_180001241
0x180001237  mov     eax, 1
0x18000123c  add     rsp, 28h
0x180001240  retn
0x180001241  call    __scrt_dllmain_crt_thread_detach
0x180001246  jmp     short loc_18000124D
0x180001248  call    __scrt_dllmain_crt_thread_attach
0x18000124d  movzx   eax, al
0x180001250  add     rsp, 28h
0x180001254  retn
0x180001255  mov     rdx, r8
0x180001258  add     rsp, 28h
0x18000125c  jmp     dllmain_crt_process_attach
0x180001261  test    r8, r8
0x180001264  setnz   cl
0x180001267  add     rsp, 28h
0x18000126b  jmp     dllmain_crt_process_detach
```
