# HTTP2ClientVirtualConnection::AbortChannels(long)

- ea: `0x180003ffc`
- end: `0x180004050`
- name: `?AbortChannels@HTTP2ClientVirtualConnection@@QEAAXJ@Z`
- size: `84`
- prototype: `void __fastcall(HTTP2ClientVirtualConnection *__hidden this, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038a0`
- `0x180004180`
- `0x1800106b8`
- `0x180012110`
- `0x1800183e0`

## callees

- `0x180003ffc`
- `0x180004058`

## import_xrefs

- `KERNEL32!Sleep` at `0x180004027`
- `KERNEL32!Sleep` at `0x180004027`

## pseudocode

```c
void __fastcall HTTP2ClientVirtualConnection::AbortChannels(HTTP2ClientVirtualConnection *this, unsigned int a2)
{
  int i; // eax
  signed __int32 v5[10]; // [rsp+0h] [rbp-28h] BYREF

  *((_DWORD *)this + 150) = 1;
  _InterlockedOr(v5, 0);
  for ( i = *((_DWORD *)this + 149); i; i = *((_DWORD *)this + 149) )
  {
    Sleep(2u);
    _InterlockedOr(v5, 0);
  }
  HTTP2VirtualConnection::AbortChannels(this, a2);
}

```

## disassembly

```asm
0x180003ffc  mov     [rsp+arg_0], rbx
0x180004001  push    rdi
0x180004002  sub     rsp, 20h
0x180004006  mov     edi, edx
0x180004008  mov     dword ptr [rcx+258h], 1
0x180004012  mov     rbx, rcx
0x180004015  lock or [rsp+28h+var_28], 0
0x18000401a  mov     eax, [rcx+254h]
0x180004020  jmp     short loc_180004038
0x180004022  mov     ecx, 2; dwMilliseconds
0x180004027  call    cs:__imp_Sleep
0x18000402d  lock or [rsp+28h+var_28], 0
0x180004032  mov     eax, [rbx+254h]
0x180004038  test    eax, eax
0x18000403a  jnz     short loc_180004022
0x18000403c  mov     edx, edi; int
0x18000403e  mov     rcx, rbx; this
0x180004041  mov     rbx, [rsp+28h+arg_0]
0x180004046  add     rsp, 20h
0x18000404a  pop     rdi
0x18000404b  jmp     ?AbortChannels@HTTP2VirtualConnection@@QEAAXJ@Z; HTTP2VirtualConnection::AbortChannels(long)
```
