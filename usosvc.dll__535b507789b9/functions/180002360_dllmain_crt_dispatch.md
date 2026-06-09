# dllmain_crt_dispatch

- ea: `0x180002360`
- end: `0x1800023b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002544`

## callees

- `0x180002360`
- `0x1800023b8`
- `0x1800024b8`
- `0x180002780`
- `0x1800027b0`

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
0x180002360  sub     rsp, 28h
0x180002364  test    edx, edx
0x180002366  jz      short loc_1800023A1
0x180002368  sub     edx, 1
0x18000236b  jz      short loc_180002395
0x18000236d  sub     edx, 1
0x180002370  jz      short loc_180002388
0x180002372  cmp     edx, 1
0x180002375  jz      short loc_180002381
0x180002377  mov     eax, 1
0x18000237c  add     rsp, 28h
0x180002380  retn
0x180002381  call    __scrt_dllmain_crt_thread_detach
0x180002386  jmp     short loc_18000238D
0x180002388  call    __scrt_dllmain_crt_thread_attach
0x18000238d  movzx   eax, al
0x180002390  add     rsp, 28h
0x180002394  retn
0x180002395  mov     rdx, r8
0x180002398  add     rsp, 28h
0x18000239c  jmp     dllmain_crt_process_attach
0x1800023a1  test    r8, r8
0x1800023a4  setnz   cl
0x1800023a7  add     rsp, 28h
0x1800023ab  jmp     dllmain_crt_process_detach
```
