# dllmain_crt_dispatch

- ea: `0x180009460`
- end: `0x1800094b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009644`

## callees

- `0x180009460`
- `0x1800094b8`
- `0x1800095b8`
- `0x180009880`
- `0x1800098b0`

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
0x180009460  sub     rsp, 28h
0x180009464  test    edx, edx
0x180009466  jz      short loc_1800094A1
0x180009468  sub     edx, 1
0x18000946b  jz      short loc_180009495
0x18000946d  sub     edx, 1
0x180009470  jz      short loc_180009488
0x180009472  cmp     edx, 1
0x180009475  jz      short loc_180009481
0x180009477  mov     eax, 1
0x18000947c  add     rsp, 28h
0x180009480  retn
0x180009481  call    __scrt_dllmain_crt_thread_detach
0x180009486  jmp     short loc_18000948D
0x180009488  call    __scrt_dllmain_crt_thread_attach
0x18000948d  movzx   eax, al
0x180009490  add     rsp, 28h
0x180009494  retn
0x180009495  mov     rdx, r8
0x180009498  add     rsp, 28h
0x18000949c  jmp     dllmain_crt_process_attach
0x1800094a1  test    r8, r8
0x1800094a4  setnz   cl
0x1800094a7  add     rsp, 28h
0x1800094ab  jmp     dllmain_crt_process_detach
```
