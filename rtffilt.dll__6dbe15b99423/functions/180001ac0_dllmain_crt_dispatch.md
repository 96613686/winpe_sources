# dllmain_crt_dispatch

- ea: `0x180001ac0`
- end: `0x180001b10`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ca4`

## callees

- `0x180001ac0`
- `0x180001b18`
- `0x180001c18`
- `0x180001f84`
- `0x180001fb4`

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
0x180001ac0  sub     rsp, 28h
0x180001ac4  test    edx, edx
0x180001ac6  jz      short loc_180001B01
0x180001ac8  sub     edx, 1
0x180001acb  jz      short loc_180001AF5
0x180001acd  sub     edx, 1
0x180001ad0  jz      short loc_180001AE8
0x180001ad2  cmp     edx, 1
0x180001ad5  jz      short loc_180001AE1
0x180001ad7  mov     eax, 1
0x180001adc  add     rsp, 28h
0x180001ae0  retn
0x180001ae1  call    __scrt_dllmain_crt_thread_detach
0x180001ae6  jmp     short loc_180001AED
0x180001ae8  call    __scrt_dllmain_crt_thread_attach
0x180001aed  movzx   eax, al
0x180001af0  add     rsp, 28h
0x180001af4  retn
0x180001af5  mov     rdx, r8
0x180001af8  add     rsp, 28h
0x180001afc  jmp     dllmain_crt_process_attach
0x180001b01  test    r8, r8
0x180001b04  setnz   cl
0x180001b07  add     rsp, 28h
0x180001b0b  jmp     dllmain_crt_process_detach
```
