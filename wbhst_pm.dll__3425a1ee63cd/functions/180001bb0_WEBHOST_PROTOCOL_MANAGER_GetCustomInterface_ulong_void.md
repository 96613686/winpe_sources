# WEBHOST_PROTOCOL_MANAGER::GetCustomInterface(ulong,void * *)

- ea: `0x180001bb0`
- end: `0x180001bf0`
- name: `?GetCustomInterface@WEBHOST_PROTOCOL_MANAGER@@UEAAJKPEAPEAX@Z`
- size: `64`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, unsigned int, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::GetCustomInterface(WEBHOST_PROTOCOL_MANAGER *this, int a2, void **a3)
{
  if ( a2 != 1 )
    return 2147942487LL;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
  *a3 = (void *)*((_QWORD *)this + 9);
  return 0;
}

```

## disassembly

```asm
0x180001bb0  mov     [rsp+arg_0], rbx
0x180001bb5  push    rdi
0x180001bb6  sub     rsp, 20h
0x180001bba  mov     rdi, r8
0x180001bbd  mov     rbx, rcx
0x180001bc0  cmp     edx, 1
0x180001bc3  jz      short loc_180001BCC
0x180001bc5  mov     eax, 80070057h
0x180001bca  jmp     short loc_180001BE5
0x180001bcc  mov     rcx, [rcx+48h]
0x180001bd0  mov     rax, [rcx]
0x180001bd3  mov     rax, [rax+8]
0x180001bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bdc  mov     rax, [rbx+48h]
0x180001be0  mov     [rdi], rax
0x180001be3  xor     eax, eax
0x180001be5  mov     rbx, [rsp+28h+arg_0]
0x180001bea  add     rsp, 20h
0x180001bee  pop     rdi
0x180001bef  retn
```
