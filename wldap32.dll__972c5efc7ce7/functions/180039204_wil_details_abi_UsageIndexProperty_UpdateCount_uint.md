# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180039204`
- end: `0x18003924e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180033dd8`
- `0x1800367bc`
- `0x180038be8`

## callees

- `0x18002a804`
- `0x180039204`

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
0x180039204  sub     rsp, 28h
0x180039208  lea     r8, [rcx+4]; Source
0x18003920c  cmp     [r8], edx
0x18003920f  jz      short loc_180039248
0x180039211  mov     al, [rcx+2]
0x180039214  mov     [r8], edx
0x180039217  cmp     al, 1
0x180039219  jnz     short loc_180039233
0x18003921b  mov     r9d, 2
0x180039221  mov     [rsp+28h+arg_8], dx
0x180039226  movzx   eax, dx
0x180039229  lea     r8, [rsp+28h+arg_8]
0x18003922e  mov     edx, r9d
0x180039231  jmp     short loc_18003923F
0x180039233  cmp     al, 2
0x180039235  jnz     short loc_180039248
0x180039237  mov     edx, 4; DestinationSize
0x18003923c  mov     r9d, edx; SourceSize
0x18003923f  mov     rcx, [rcx+10h]; Destination
0x180039243  call    memcpy_s
0x180039248  add     rsp, 28h
0x18003924c  retn
```
