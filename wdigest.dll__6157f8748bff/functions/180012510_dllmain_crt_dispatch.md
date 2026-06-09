# dllmain_crt_dispatch

- ea: `0x180012510`
- end: `0x180012560`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800126f4`

## callees

- `0x180012510`
- `0x180012568`
- `0x180012668`
- `0x180012930`
- `0x180012960`

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
0x180012510  sub     rsp, 28h
0x180012514  test    edx, edx
0x180012516  jz      short loc_180012551
0x180012518  sub     edx, 1
0x18001251b  jz      short loc_180012545
0x18001251d  sub     edx, 1
0x180012520  jz      short loc_180012538
0x180012522  cmp     edx, 1
0x180012525  jz      short loc_180012531
0x180012527  mov     eax, 1
0x18001252c  add     rsp, 28h
0x180012530  retn
0x180012531  call    __scrt_dllmain_crt_thread_detach
0x180012536  jmp     short loc_18001253D
0x180012538  call    __scrt_dllmain_crt_thread_attach
0x18001253d  movzx   eax, al
0x180012540  add     rsp, 28h
0x180012544  retn
0x180012545  mov     rdx, r8
0x180012548  add     rsp, 28h
0x18001254c  jmp     dllmain_crt_process_attach
0x180012551  test    r8, r8
0x180012554  setnz   cl
0x180012557  add     rsp, 28h
0x18001255b  jmp     dllmain_crt_process_detach
```
