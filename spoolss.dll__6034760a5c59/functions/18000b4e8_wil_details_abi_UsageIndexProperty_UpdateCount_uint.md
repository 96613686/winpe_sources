# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000b4e8`
- end: `0x18000b531`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003af0`
- `0x180007c64`
- `0x18000ad50`

## callees

- `0x18000b4e8`
- `0x18000f1d8`

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
0x18000b4e8  sub     rsp, 28h
0x18000b4ec  lea     r8, [rcx+4]; Source
0x18000b4f0  cmp     [r8], edx
0x18000b4f3  jz      short loc_18000B52C
0x18000b4f5  mov     al, [rcx+2]
0x18000b4f8  mov     [r8], edx
0x18000b4fb  cmp     al, 1
0x18000b4fd  jnz     short loc_18000B517
0x18000b4ff  mov     r9d, 2
0x18000b505  mov     [rsp+28h+arg_8], dx
0x18000b50a  movzx   eax, dx
0x18000b50d  lea     r8, [rsp+28h+arg_8]
0x18000b512  mov     edx, r9d
0x18000b515  jmp     short loc_18000B523
0x18000b517  cmp     al, 2
0x18000b519  jnz     short loc_18000B52C
0x18000b51b  mov     edx, 4; DestinationSize
0x18000b520  mov     r9d, edx; SourceSize
0x18000b523  mov     rcx, [rcx+10h]; Destination
0x18000b527  call    memcpy_s
0x18000b52c  add     rsp, 28h
0x18000b530  retn
```
