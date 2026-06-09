# dllmain_crt_dispatch

- ea: `0x1800053c0`
- end: `0x180005410`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800055a4`

## callees

- `0x1800053c0`
- `0x180005418`
- `0x180005518`
- `0x180005914`
- `0x180005944`

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
0x1800053c0  sub     rsp, 28h
0x1800053c4  test    edx, edx
0x1800053c6  jz      short loc_180005401
0x1800053c8  sub     edx, 1
0x1800053cb  jz      short loc_1800053F5
0x1800053cd  sub     edx, 1
0x1800053d0  jz      short loc_1800053E8
0x1800053d2  cmp     edx, 1
0x1800053d5  jz      short loc_1800053E1
0x1800053d7  mov     eax, 1
0x1800053dc  add     rsp, 28h
0x1800053e0  retn
0x1800053e1  call    __scrt_dllmain_crt_thread_detach
0x1800053e6  jmp     short loc_1800053ED
0x1800053e8  call    __scrt_dllmain_crt_thread_attach
0x1800053ed  movzx   eax, al
0x1800053f0  add     rsp, 28h
0x1800053f4  retn
0x1800053f5  mov     rdx, r8
0x1800053f8  add     rsp, 28h
0x1800053fc  jmp     dllmain_crt_process_attach
0x180005401  test    r8, r8
0x180005404  setnz   cl
0x180005407  add     rsp, 28h
0x18000540b  jmp     dllmain_crt_process_detach
```
