# dllmain_crt_dispatch

- ea: `0x180010130`
- end: `0x180010180`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001032c`

## callees

- `0x18000fd4c`
- `0x18000fd7c`
- `0x180010130`
- `0x180010188`
- `0x1800102a0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
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
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180010130  sub     rsp, 28h
0x180010134  test    edx, edx
0x180010136  jz      short loc_180010171
0x180010138  sub     edx, 1
0x18001013b  jz      short loc_180010165
0x18001013d  sub     edx, 1
0x180010140  jz      short loc_180010158
0x180010142  cmp     edx, 1
0x180010145  jz      short loc_180010151
0x180010147  mov     eax, 1
0x18001014c  add     rsp, 28h
0x180010150  retn
0x180010151  call    __scrt_dllmain_crt_thread_detach
0x180010156  jmp     short loc_18001015D
0x180010158  call    __scrt_dllmain_crt_thread_attach
0x18001015d  movzx   eax, al
0x180010160  add     rsp, 28h
0x180010164  retn
0x180010165  mov     rdx, r8
0x180010168  add     rsp, 28h
0x18001016c  jmp     dllmain_crt_process_attach
0x180010171  test    r8, r8
0x180010174  setnz   cl
0x180010177  add     rsp, 28h
0x18001017b  jmp     dllmain_crt_process_detach
```
