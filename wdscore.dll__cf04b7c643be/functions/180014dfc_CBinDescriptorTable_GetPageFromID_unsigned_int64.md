# CBinDescriptorTable::GetPageFromID(unsigned __int64)

- ea: `0x180014dfc`
- end: `0x180014e55`
- name: `?GetPageFromID@CBinDescriptorTable@@IEAA_K_K@Z`
- size: `89`
- prototype: `unsigned __int64 __fastcall(CBinDescriptorTable *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f798`
- `0x18000fa70`

## callees

- `0x180012408`
- `0x180013480`
- `0x180013738`
- `0x180014dfc`

## pseudocode

```c
__int64 __fastcall CBinDescriptorTable::GetPageFromID(CBinDescriptorTable *this, __int64 a2)
{
  unsigned __int64 v3; // r8
  __int64 v4; // rbx
  __int64 *v5; // rax
  unsigned __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( !(unsigned int)CBin::EnumReset(this, 8 * a2) )
    return 0;
  v7 = 0;
  v5 = (__int64 *)CBin::EnumView(this, &v7, v3);
  if ( !v5 )
    return 0;
  if ( v7 >= 8 )
    v4 = *v5;
  CBin::EnumFinish(this);
  return v4;
}

```

## disassembly

```asm
0x180014dfc  mov     [rsp+arg_0], rbx
0x180014e01  push    rdi
0x180014e02  sub     rsp, 20h
0x180014e06  shl     rdx, 3; unsigned __int64
0x180014e0a  mov     rdi, rcx
0x180014e0d  call    ?EnumReset@CBin@@QEAAH_K@Z; CBin::EnumReset(unsigned __int64)
0x180014e12  xor     ebx, ebx
0x180014e14  test    eax, eax
0x180014e16  jz      short loc_180014E47
0x180014e18  lea     rdx, [rsp+28h+arg_8]; unsigned __int64 *
0x180014e1d  mov     [rsp+28h+arg_8], rbx
0x180014e22  mov     rcx, rdi; this
0x180014e25  call    ?EnumView@CBin@@QEAAPEAXAEA_K_K@Z; CBin::EnumView(unsigned __int64 &,unsigned __int64)
0x180014e2a  test    rax, rax
0x180014e2d  jz      short loc_180014E47
0x180014e2f  cmp     [rsp+28h+arg_8], 8
0x180014e35  jb      short loc_180014E3A
0x180014e37  mov     rbx, [rax]
0x180014e3a  mov     rcx, rdi; this
0x180014e3d  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180014e42  mov     rax, rbx
0x180014e45  jmp     short loc_180014E49
0x180014e47  xor     eax, eax
0x180014e49  mov     rbx, [rsp+28h+arg_0]
0x180014e4e  add     rsp, 20h
0x180014e52  pop     rdi
0x180014e53  retn
```
