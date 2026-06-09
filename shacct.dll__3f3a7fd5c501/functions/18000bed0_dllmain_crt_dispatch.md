# dllmain_crt_dispatch

- ea: `0x18000bed0`
- end: `0x18000bf20`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c0b4`

## callees

- `0x18000bed0`
- `0x18000bf28`
- `0x18000c028`
- `0x18000c404`
- `0x18000c434`

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
0x18000bed0  sub     rsp, 28h
0x18000bed4  test    edx, edx
0x18000bed6  jz      short loc_18000BF11
0x18000bed8  sub     edx, 1
0x18000bedb  jz      short loc_18000BF05
0x18000bedd  sub     edx, 1
0x18000bee0  jz      short loc_18000BEF8
0x18000bee2  cmp     edx, 1
0x18000bee5  jz      short loc_18000BEF1
0x18000bee7  mov     eax, 1
0x18000beec  add     rsp, 28h
0x18000bef0  retn
0x18000bef1  call    __scrt_dllmain_crt_thread_detach
0x18000bef6  jmp     short loc_18000BEFD
0x18000bef8  call    __scrt_dllmain_crt_thread_attach
0x18000befd  movzx   eax, al
0x18000bf00  add     rsp, 28h
0x18000bf04  retn
0x18000bf05  mov     rdx, r8
0x18000bf08  add     rsp, 28h
0x18000bf0c  jmp     dllmain_crt_process_attach
0x18000bf11  test    r8, r8
0x18000bf14  setnz   cl
0x18000bf17  add     rsp, 28h
0x18000bf1b  jmp     dllmain_crt_process_detach
```
