# WS_HTTP2_INITIAL_CONNECTION::ProcessRead(ulong,uchar * *,uint *)

- ea: `0x180010f10`
- end: `0x180010f60`
- name: `?ProcessRead@WS_HTTP2_INITIAL_CONNECTION@@UEAAJKPEAPEAEPEAI@Z`
- size: `80`
- prototype: `__int64 __fastcall(WS_HTTP2_INITIAL_CONNECTION *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010f10`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall WS_HTTP2_INITIAL_CONNECTION::ProcessRead(
        WS_HTTP2_INITIAL_CONNECTION *this,
        __int64 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int64 result; // rax

  result = (*((__int64 (__fastcall **)(WS_HTTP2_INITIAL_CONNECTION *, __int64, unsigned __int8 **, unsigned int *))pRuntimeImportTable
            + 56))(
             this,
             a2,
             a3,
             a4);
  if ( !(_DWORD)result )
  {
    if ( (*a3)[2] == 20 )
    {
      *((_DWORD *)this + 2) |= 0x10u;
      return 3221360686LL;
    }
    else
    {
      *(_QWORD *)this = &WS_CONNECTION::`vftable';
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010f10  mov     [rsp+arg_0], rbx
0x180010f15  push    rdi
0x180010f16  sub     rsp, 30h
0x180010f1a  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180010f21  mov     rdi, r8
0x180010f24  mov     rbx, rcx
0x180010f27  mov     rax, [rax+1C0h]
0x180010f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f33  test    eax, eax
0x180010f35  jnz     short loc_180010F55
0x180010f37  mov     rcx, [rdi]
0x180010f3a  cmp     byte ptr [rcx+2], 14h
0x180010f3e  jnz     short loc_180010F4B
0x180010f40  or      dword ptr [rbx+8], 10h
0x180010f44  mov     eax, 0C002102Eh
0x180010f49  jmp     short loc_180010F55
0x180010f4b  lea     rcx, ??_7WS_CONNECTION@@6B@; const WS_CONNECTION::`vftable'
0x180010f52  mov     [rbx], rcx
0x180010f55  mov     rbx, [rsp+38h+arg_0]
0x180010f5a  add     rsp, 30h
0x180010f5e  pop     rdi
0x180010f5f  retn
```
