# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18001c35c`
- end: `0x18001c3ad`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `81`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180019218`
- `0x18001b25c`
- `0x18001bc40`

## callees

- `0x18001c35c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001c39b`
- `msvcrt!memcpy_s` at `0x18001c39b`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x18001c35c  sub     rsp, 28h
0x18001c360  lea     r8, [rcx+4]; Source
0x18001c364  cmp     [r8], edx
0x18001c367  jz      short loc_18001C3A7
0x18001c369  mov     al, [rcx+2]
0x18001c36c  mov     [r8], edx
0x18001c36f  cmp     al, 1
0x18001c371  jnz     short loc_18001C38B
0x18001c373  mov     r9d, 2
0x18001c379  mov     [rsp+28h+arg_8], dx
0x18001c37e  movzx   eax, dx
0x18001c381  lea     r8, [rsp+28h+arg_8]
0x18001c386  mov     edx, r9d
0x18001c389  jmp     short loc_18001C397
0x18001c38b  cmp     al, 2
0x18001c38d  jnz     short loc_18001C3A7
0x18001c38f  mov     edx, 4; DestinationSize
0x18001c394  mov     r9d, edx; SourceSize
0x18001c397  mov     rcx, [rcx+10h]; Destination
0x18001c39b  call    cs:__imp_memcpy_s
0x18001c3a2  nop     dword ptr [rax+rax+00h]
0x18001c3a7  add     rsp, 28h
0x18001c3ab  retn
```
