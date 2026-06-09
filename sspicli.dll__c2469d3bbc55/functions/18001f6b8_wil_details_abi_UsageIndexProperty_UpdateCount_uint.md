# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18001f6b8`
- end: `0x18001f702`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180012620`
- `0x180012784`
- `0x180016a3c`

## callees

- `0x18001f6b8`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001f6f7`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001f6f7`

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
0x18001f6b8  sub     rsp, 28h
0x18001f6bc  lea     r8, [rcx+4]; Source
0x18001f6c0  cmp     [r8], edx
0x18001f6c3  jz      short loc_18001F6FD
0x18001f6c5  mov     al, [rcx+2]
0x18001f6c8  mov     [r8], edx
0x18001f6cb  cmp     al, 1
0x18001f6cd  jnz     short loc_18001F6E7
0x18001f6cf  mov     r9d, 2
0x18001f6d5  mov     [rsp+28h+arg_8], dx
0x18001f6da  movzx   eax, dx
0x18001f6dd  lea     r8, [rsp+28h+arg_8]
0x18001f6e2  mov     edx, r9d
0x18001f6e5  jmp     short loc_18001F6F3
0x18001f6e7  cmp     al, 2
0x18001f6e9  jnz     short loc_18001F6FD
0x18001f6eb  mov     edx, 4; DestinationSize
0x18001f6f0  mov     r9d, edx; SourceSize
0x18001f6f3  mov     rcx, [rcx+10h]; Destination
0x18001f6f7  call    cs:__imp_memcpy_s
0x18001f6fd  add     rsp, 28h
0x18001f701  retn
```
