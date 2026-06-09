# LOOPBACK_HTTP2_CONNECTION::ProcessRead(ulong,uchar * *,uint *)

- ea: `0x180010ec0`
- end: `0x180010f06`
- name: `?ProcessRead@LOOPBACK_HTTP2_CONNECTION@@UEAAJKPEAPEAEPEAI@Z`
- size: `70`
- prototype: `__int64 __fastcall(LOOPBACK_HTTP2_CONNECTION *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010ec0`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall LOOPBACK_HTTP2_CONNECTION::ProcessRead(
        LOOPBACK_HTTP2_CONNECTION *this,
        __int64 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int64 result; // rax

  if ( *((_DWORD *)this + 58) )
    return 0;
  result = (*((__int64 (__fastcall **)(LOOPBACK_HTTP2_CONNECTION *, __int64, unsigned __int8 **, unsigned int *))pRuntimeImportTable
            + 56))(
             this,
             a2,
             a3,
             a4);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)this + 2) |= 0x10u;
    result = 3221360686LL;
    *((_DWORD *)this + 58) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180010ec0  push    rbx
0x180010ec2  sub     rsp, 30h
0x180010ec6  cmp     dword ptr [rcx+0E8h], 0
0x180010ecd  mov     rbx, rcx
0x180010ed0  jnz     short loc_180010EFE
0x180010ed2  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180010ed9  mov     rax, [rax+1C0h]
0x180010ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee5  test    eax, eax
0x180010ee7  jnz     short loc_180010F00
0x180010ee9  or      dword ptr [rbx+8], 10h
0x180010eed  mov     eax, 0C002102Eh
0x180010ef2  mov     dword ptr [rbx+0E8h], 1
0x180010efc  jmp     short loc_180010F00
0x180010efe  xor     eax, eax
0x180010f00  add     rsp, 30h
0x180010f04  pop     rbx
0x180010f05  retn
```
