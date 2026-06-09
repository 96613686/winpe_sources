# dllmain_crt_dispatch

- ea: `0x180010180`
- end: `0x1800101d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001037c`

## callees

- `0x18000fd9c`
- `0x18000fdcc`
- `0x180010180`
- `0x1800101d8`
- `0x1800102f0`

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
0x180010180  sub     rsp, 28h
0x180010184  test    edx, edx
0x180010186  jz      short loc_1800101C1
0x180010188  sub     edx, 1
0x18001018b  jz      short loc_1800101B5
0x18001018d  sub     edx, 1
0x180010190  jz      short loc_1800101A8
0x180010192  cmp     edx, 1
0x180010195  jz      short loc_1800101A1
0x180010197  mov     eax, 1
0x18001019c  add     rsp, 28h
0x1800101a0  retn
0x1800101a1  call    __scrt_dllmain_crt_thread_detach
0x1800101a6  jmp     short loc_1800101AD
0x1800101a8  call    __scrt_dllmain_crt_thread_attach
0x1800101ad  movzx   eax, al
0x1800101b0  add     rsp, 28h
0x1800101b4  retn
0x1800101b5  mov     rdx, r8
0x1800101b8  add     rsp, 28h
0x1800101bc  jmp     dllmain_crt_process_attach
0x1800101c1  test    r8, r8
0x1800101c4  setnz   cl
0x1800101c7  add     rsp, 28h
0x1800101cb  jmp     dllmain_crt_process_detach
```
