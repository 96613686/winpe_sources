# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18002a0cc`
- end: `0x18002a131`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `101`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800277a4`
- `0x180028cf4`
- `0x180029878`

## callees

- `0x1800050f0`
- `0x180005c4c`
- `0x18002a0cc`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+20h] [rbp-18h] BYREF

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
0x18002a0cc  sub     rsp, 38h
0x18002a0d0  mov     rax, cs:__security_cookie
0x18002a0d7  xor     rax, rsp
0x18002a0da  mov     [rsp+38h+var_10], rax
0x18002a0df  lea     r8, [rcx+4]; Source
0x18002a0e3  cmp     [r8], edx
0x18002a0e6  jz      short loc_18002A11F
0x18002a0e8  mov     al, [rcx+2]
0x18002a0eb  mov     [r8], edx
0x18002a0ee  cmp     al, 1
0x18002a0f0  jnz     short loc_18002A10A
0x18002a0f2  mov     r9d, 2
0x18002a0f8  mov     [rsp+38h+var_18], dx
0x18002a0fd  movzx   eax, dx
0x18002a100  lea     r8, [rsp+38h+var_18]
0x18002a105  mov     edx, r9d
0x18002a108  jmp     short loc_18002A116
0x18002a10a  cmp     al, 2
0x18002a10c  jnz     short loc_18002A11F
0x18002a10e  mov     edx, 4; DestinationSize
0x18002a113  mov     r9d, edx; SourceSize
0x18002a116  mov     rcx, [rcx+10h]; Destination
0x18002a11a  call    memcpy_s
0x18002a11f  mov     rcx, [rsp+38h+var_10]
0x18002a124  xor     rcx, rsp; StackCookie
0x18002a127  call    __security_check_cookie
0x18002a12c  add     rsp, 38h
0x18002a130  retn
```
