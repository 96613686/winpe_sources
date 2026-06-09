# dllmain_crt_dispatch

- ea: `0x180001a50`
- end: `0x180001aa0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c34`

## callees

- `0x180001a50`
- `0x180001aa8`
- `0x180001ba8`
- `0x180001e70`
- `0x180001ea0`

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
0x180001a50  sub     rsp, 28h
0x180001a54  test    edx, edx
0x180001a56  jz      short loc_180001A91
0x180001a58  sub     edx, 1
0x180001a5b  jz      short loc_180001A85
0x180001a5d  sub     edx, 1
0x180001a60  jz      short loc_180001A78
0x180001a62  cmp     edx, 1
0x180001a65  jz      short loc_180001A71
0x180001a67  mov     eax, 1
0x180001a6c  add     rsp, 28h
0x180001a70  retn
0x180001a71  call    __scrt_dllmain_crt_thread_detach
0x180001a76  jmp     short loc_180001A7D
0x180001a78  call    __scrt_dllmain_crt_thread_attach
0x180001a7d  movzx   eax, al
0x180001a80  add     rsp, 28h
0x180001a84  retn
0x180001a85  mov     rdx, r8
0x180001a88  add     rsp, 28h
0x180001a8c  jmp     dllmain_crt_process_attach
0x180001a91  test    r8, r8
0x180001a94  setnz   cl
0x180001a97  add     rsp, 28h
0x180001a9b  jmp     dllmain_crt_process_detach
```
