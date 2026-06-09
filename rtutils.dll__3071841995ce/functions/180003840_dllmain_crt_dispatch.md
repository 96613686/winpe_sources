# dllmain_crt_dispatch

- ea: `0x180003840`
- end: `0x180003890`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003a24`

## callees

- `0x180003840`
- `0x180003898`
- `0x180003998`
- `0x180003d94`
- `0x180003dc4`

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
0x180003840  sub     rsp, 28h
0x180003844  test    edx, edx
0x180003846  jz      short loc_180003881
0x180003848  sub     edx, 1
0x18000384b  jz      short loc_180003875
0x18000384d  sub     edx, 1
0x180003850  jz      short loc_180003868
0x180003852  cmp     edx, 1
0x180003855  jz      short loc_180003861
0x180003857  mov     eax, 1
0x18000385c  add     rsp, 28h
0x180003860  retn
0x180003861  call    __scrt_dllmain_crt_thread_detach
0x180003866  jmp     short loc_18000386D
0x180003868  call    __scrt_dllmain_crt_thread_attach
0x18000386d  movzx   eax, al
0x180003870  add     rsp, 28h
0x180003874  retn
0x180003875  mov     rdx, r8
0x180003878  add     rsp, 28h
0x18000387c  jmp     dllmain_crt_process_attach
0x180003881  test    r8, r8
0x180003884  setnz   cl
0x180003887  add     rsp, 28h
0x18000388b  jmp     dllmain_crt_process_detach
```
