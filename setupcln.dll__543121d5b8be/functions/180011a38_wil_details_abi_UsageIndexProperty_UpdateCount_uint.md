# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180011a38`
- end: `0x180011a82`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000e4b4`
- `0x180010654`
- `0x1800112e4`

## callees

- `0x180011a38`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011a77`
- `msvcrt!memcpy_s` at `0x180011a77`

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
0x180011a38  sub     rsp, 28h
0x180011a3c  lea     r8, [rcx+4]; Source
0x180011a40  cmp     [r8], edx
0x180011a43  jz      short loc_180011A7D
0x180011a45  mov     al, [rcx+2]
0x180011a48  mov     [r8], edx
0x180011a4b  cmp     al, 1
0x180011a4d  jnz     short loc_180011A67
0x180011a4f  mov     r9d, 2
0x180011a55  mov     [rsp+28h+arg_8], dx
0x180011a5a  movzx   eax, dx
0x180011a5d  lea     r8, [rsp+28h+arg_8]
0x180011a62  mov     edx, r9d
0x180011a65  jmp     short loc_180011A73
0x180011a67  cmp     al, 2
0x180011a69  jnz     short loc_180011A7D
0x180011a6b  mov     edx, 4; DestinationSize
0x180011a70  mov     r9d, edx; SourceSize
0x180011a73  mov     rcx, [rcx+10h]; Destination
0x180011a77  call    cs:__imp_memcpy_s
0x180011a7d  add     rsp, 28h
0x180011a81  retn
```
