# dllmain_crt_dispatch

- ea: `0x180001ec0`
- end: `0x180001f10`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800020a4`

## callees

- `0x180001ec0`
- `0x180001f18`
- `0x180002018`
- `0x1800022e0`
- `0x180002310`

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
0x180001ec0  sub     rsp, 28h
0x180001ec4  test    edx, edx
0x180001ec6  jz      short loc_180001F01
0x180001ec8  sub     edx, 1
0x180001ecb  jz      short loc_180001EF5
0x180001ecd  sub     edx, 1
0x180001ed0  jz      short loc_180001EE8
0x180001ed2  cmp     edx, 1
0x180001ed5  jz      short loc_180001EE1
0x180001ed7  mov     eax, 1
0x180001edc  add     rsp, 28h
0x180001ee0  retn
0x180001ee1  call    __scrt_dllmain_crt_thread_detach
0x180001ee6  jmp     short loc_180001EED
0x180001ee8  call    __scrt_dllmain_crt_thread_attach
0x180001eed  movzx   eax, al
0x180001ef0  add     rsp, 28h
0x180001ef4  retn
0x180001ef5  mov     rdx, r8
0x180001ef8  add     rsp, 28h
0x180001efc  jmp     dllmain_crt_process_attach
0x180001f01  test    r8, r8
0x180001f04  setnz   cl
0x180001f07  add     rsp, 28h
0x180001f0b  jmp     dllmain_crt_process_detach
```
