# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180011bcc`
- end: `0x180011c16`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000d7c0`
- `0x1800101d8`
- `0x180011294`

## callees

- `0x180011bcc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011c0b`
- `msvcrt!memcpy_s` at `0x180011c0b`

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
0x180011bcc  sub     rsp, 28h
0x180011bd0  lea     r8, [rcx+4]; Source
0x180011bd4  cmp     [r8], edx
0x180011bd7  jz      short loc_180011C11
0x180011bd9  mov     al, [rcx+2]
0x180011bdc  mov     [r8], edx
0x180011bdf  cmp     al, 1
0x180011be1  jnz     short loc_180011BFB
0x180011be3  mov     r9d, 2
0x180011be9  mov     [rsp+28h+arg_8], dx
0x180011bee  movzx   eax, dx
0x180011bf1  lea     r8, [rsp+28h+arg_8]
0x180011bf6  mov     edx, r9d
0x180011bf9  jmp     short loc_180011C07
0x180011bfb  cmp     al, 2
0x180011bfd  jnz     short loc_180011C11
0x180011bff  mov     edx, 4; DestinationSize
0x180011c04  mov     r9d, edx; SourceSize
0x180011c07  mov     rcx, [rcx+10h]; Destination
0x180011c0b  call    cs:__imp_memcpy_s
0x180011c11  add     rsp, 28h
0x180011c15  retn
```
