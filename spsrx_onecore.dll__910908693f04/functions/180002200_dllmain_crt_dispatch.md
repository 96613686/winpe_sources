# dllmain_crt_dispatch

- ea: `0x180002200`
- end: `0x180002250`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800023e4`

## callees

- `0x180002200`
- `0x180002258`
- `0x180002358`
- `0x18000267c`
- `0x1800026ac`

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
0x180002200  sub     rsp, 28h
0x180002204  test    edx, edx
0x180002206  jz      short loc_180002241
0x180002208  sub     edx, 1
0x18000220b  jz      short loc_180002235
0x18000220d  sub     edx, 1
0x180002210  jz      short loc_180002228
0x180002212  cmp     edx, 1
0x180002215  jz      short loc_180002221
0x180002217  mov     eax, 1
0x18000221c  add     rsp, 28h
0x180002220  retn
0x180002221  call    __scrt_dllmain_crt_thread_detach
0x180002226  jmp     short loc_18000222D
0x180002228  call    __scrt_dllmain_crt_thread_attach
0x18000222d  movzx   eax, al
0x180002230  add     rsp, 28h
0x180002234  retn
0x180002235  mov     rdx, r8
0x180002238  add     rsp, 28h
0x18000223c  jmp     dllmain_crt_process_attach
0x180002241  test    r8, r8
0x180002244  setnz   cl
0x180002247  add     rsp, 28h
0x18000224b  jmp     dllmain_crt_process_detach
```
