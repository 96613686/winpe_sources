# dllmain_crt_dispatch

- ea: `0x180010740`
- end: `0x180010790`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001093c`

## callees

- `0x1800103d8`
- `0x180010408`
- `0x180010740`
- `0x180010798`
- `0x1800108b0`

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
0x180010740  sub     rsp, 28h
0x180010744  test    edx, edx
0x180010746  jz      short loc_180010781
0x180010748  sub     edx, 1
0x18001074b  jz      short loc_180010775
0x18001074d  sub     edx, 1
0x180010750  jz      short loc_180010768
0x180010752  cmp     edx, 1
0x180010755  jz      short loc_180010761
0x180010757  mov     eax, 1
0x18001075c  add     rsp, 28h
0x180010760  retn
0x180010761  call    __scrt_dllmain_crt_thread_detach
0x180010766  jmp     short loc_18001076D
0x180010768  call    __scrt_dllmain_crt_thread_attach
0x18001076d  movzx   eax, al
0x180010770  add     rsp, 28h
0x180010774  retn
0x180010775  mov     rdx, r8
0x180010778  add     rsp, 28h
0x18001077c  jmp     dllmain_crt_process_attach
0x180010781  test    r8, r8
0x180010784  setnz   cl
0x180010787  add     rsp, 28h
0x18001078b  jmp     dllmain_crt_process_detach
```
