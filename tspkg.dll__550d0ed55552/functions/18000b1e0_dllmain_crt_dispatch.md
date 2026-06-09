# dllmain_crt_dispatch

- ea: `0x18000b1e0`
- end: `0x18000b230`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3c4`

## callees

- `0x18000b1e0`
- `0x18000b238`
- `0x18000b338`
- `0x18000b600`
- `0x18000b630`

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
0x18000b1e0  sub     rsp, 28h
0x18000b1e4  test    edx, edx
0x18000b1e6  jz      short loc_18000B221
0x18000b1e8  sub     edx, 1
0x18000b1eb  jz      short loc_18000B215
0x18000b1ed  sub     edx, 1
0x18000b1f0  jz      short loc_18000B208
0x18000b1f2  cmp     edx, 1
0x18000b1f5  jz      short loc_18000B201
0x18000b1f7  mov     eax, 1
0x18000b1fc  add     rsp, 28h
0x18000b200  retn
0x18000b201  call    __scrt_dllmain_crt_thread_detach
0x18000b206  jmp     short loc_18000B20D
0x18000b208  call    __scrt_dllmain_crt_thread_attach
0x18000b20d  movzx   eax, al
0x18000b210  add     rsp, 28h
0x18000b214  retn
0x18000b215  mov     rdx, r8
0x18000b218  add     rsp, 28h
0x18000b21c  jmp     dllmain_crt_process_attach
0x18000b221  test    r8, r8
0x18000b224  setnz   cl
0x18000b227  add     rsp, 28h
0x18000b22b  jmp     dllmain_crt_process_detach
```
