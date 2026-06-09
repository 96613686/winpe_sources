# dllmain_crt_dispatch

- ea: `0x1004165c0`
- end: `0x100416610`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1004167c0`

## callees

- `0x1004165c0`
- `0x100416618`
- `0x100416734`
- `0x100416dbc`
- `0x100416dec`

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
    return dllmain_crt_process_attach();
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
0x1004165c0  sub     rsp, 28h
0x1004165c4  test    edx, edx
0x1004165c6  jz      short loc_100416601
0x1004165c8  sub     edx, 1
0x1004165cb  jz      short loc_1004165F5
0x1004165cd  sub     edx, 1
0x1004165d0  jz      short loc_1004165E8
0x1004165d2  cmp     edx, 1
0x1004165d5  jz      short loc_1004165E1
0x1004165d7  mov     eax, 1
0x1004165dc  add     rsp, 28h
0x1004165e0  retn
0x1004165e1  call    __scrt_dllmain_crt_thread_detach
0x1004165e6  jmp     short loc_1004165ED
0x1004165e8  call    __scrt_dllmain_crt_thread_attach
0x1004165ed  movzx   eax, al
0x1004165f0  add     rsp, 28h
0x1004165f4  retn
0x1004165f5  mov     rdx, r8
0x1004165f8  add     rsp, 28h
0x1004165fc  jmp     dllmain_crt_process_attach
0x100416601  test    r8, r8
0x100416604  setnz   cl
0x100416607  add     rsp, 28h
0x10041660b  jmp     dllmain_crt_process_detach
```
