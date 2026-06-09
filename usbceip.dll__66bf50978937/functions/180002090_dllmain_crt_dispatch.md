# dllmain_crt_dispatch

- ea: `0x180002090`
- end: `0x1800020e0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002274`

## callees

- `0x180002090`
- `0x1800020e8`
- `0x1800021e8`
- `0x180002644`
- `0x180002674`

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
0x180002090  sub     rsp, 28h
0x180002094  test    edx, edx
0x180002096  jz      short loc_1800020D1
0x180002098  sub     edx, 1
0x18000209b  jz      short loc_1800020C5
0x18000209d  sub     edx, 1
0x1800020a0  jz      short loc_1800020B8
0x1800020a2  cmp     edx, 1
0x1800020a5  jz      short loc_1800020B1
0x1800020a7  mov     eax, 1
0x1800020ac  add     rsp, 28h
0x1800020b0  retn
0x1800020b1  call    __scrt_dllmain_crt_thread_detach
0x1800020b6  jmp     short loc_1800020BD
0x1800020b8  call    __scrt_dllmain_crt_thread_attach
0x1800020bd  movzx   eax, al
0x1800020c0  add     rsp, 28h
0x1800020c4  retn
0x1800020c5  mov     rdx, r8
0x1800020c8  add     rsp, 28h
0x1800020cc  jmp     dllmain_crt_process_attach
0x1800020d1  test    r8, r8
0x1800020d4  setnz   cl
0x1800020d7  add     rsp, 28h
0x1800020db  jmp     dllmain_crt_process_detach
```
