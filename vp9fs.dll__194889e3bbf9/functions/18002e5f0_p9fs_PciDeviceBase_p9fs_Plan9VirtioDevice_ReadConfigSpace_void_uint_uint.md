# p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::ReadConfigSpace(void *,uint,uint *)

- ea: `0x18002e5f0`
- end: `0x18002e72f`
- name: `?ReadConfigSpace@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@SAJPEAXIPEAI@Z`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180004120`
- `0x180004c74`
- `0x180004c80`
- `0x180009fe4`
- `0x18001c93c`
- `0x18002e5f0`

## import_xrefs

- `vmvirtio!VirtioReadConfigSpace` at `0x18002e644`
- `vmvirtio!VirtioReadConfigSpace` at `0x18002e644`

## string_xrefs

- `0x18002e658`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::ReadConfigSpace(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  gsl::details *v4; // rcx
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  void *v8; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v9; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+3Ch] [rbp-2Ch]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = 0;
  v10 = 0;
  v9 = 0;
  v3 = VirtioReadConfigSpace(*(_QWORD *)(a1 + 136), a2, a3, &v9);
  v6 = v3;
  if ( v3 >= 0 )
  {
    if ( v10 )
      gsl::details::terminate(v4);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v3,
      (int)&v8);
  }
  result = v6;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v9 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x52,
             (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
             v5);
      result = v9;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002e5f0  mov     r11, rsp
0x18002e5f3  mov     [r11+20h], rbx
0x18002e5f7  push    rsi
0x18002e5f8  push    rdi
0x18002e5f9  push    r14
0x18002e5fb  sub     rsp, 50h
0x18002e5ff  mov     rax, cs:__security_cookie
0x18002e606  xor     rax, rsp
0x18002e609  mov     [rsp+68h+var_28], rax
0x18002e60e  mov     rsi, rcx
0x18002e611  mov     qword ptr [r11-38h], 0
0x18002e619  mov     [rsp+68h+var_2C], 0
0x18002e621  mov     [rsp+68h+var_30], 0
0x18002e629  lea     rax, [r11-2Ch]
0x18002e62d  mov     [r11-40h], rax
0x18002e631  lea     rax, [r11-38h]
0x18002e635  mov     [r11-48h], rax
0x18002e639  lea     r9, [r11-30h]
0x18002e63d  mov     rcx, [rcx+88h]
0x18002e644  call    cs:__imp_VirtioReadConfigSpace
0x18002e64a  mov     ebx, eax
0x18002e64c  test    eax, eax
0x18002e64e  jns     short loc_18002E66E
0x18002e650  mov     rcx, [rsp+68h]; this
0x18002e655  mov     r9d, eax; char *
0x18002e658  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002e65f  mov     edx, 8Ch; void *
0x18002e664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e669  jmp     loc_18002E702
0x18002e66e  mov     eax, [rsp+68h+var_2C]
0x18002e672  test    eax, eax
0x18002e674  jz      loc_18002E700
0x18002e67a  add     rsi, 58h ; 'X'
0x18002e67e  jz      loc_18002E728
0x18002e684  mov     r14, [rsp+68h+var_38]
0x18002e689  mov     ebx, eax
0x18002e68b  test    r14, r14
0x18002e68e  jnz     short loc_18002E698
0x18002e690  test    eax, eax
0x18002e692  jnz     loc_18002E728
0x18002e698  mov     eax, [rsp+68h+var_30]
0x18002e69c  xor     edi, edi
0x18002e69e  lea     r8d, [rdi+10h]
0x18002e6a2  cmp     rax, r8
0x18002e6a5  jnb     short loc_18002E6E2
0x18002e6a7  sub     r8, rax
0x18002e6aa  mov     rdi, rbx
0x18002e6ad  cmp     rbx, r8
0x18002e6b0  cmovnb  rdi, r8
0x18002e6b4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002e6b8  jnz     short loc_18002E6C1
0x18002e6ba  cmp     r8, rdi
0x18002e6bd  jz      short loc_18002E728
0x18002e6bf  jmp     short loc_18002E6C9
0x18002e6c1  cmp     r8, rdi
0x18002e6c4  jb      short loc_18002E728
0x18002e6c6  mov     r8, rdi; Size
0x18002e6c9  mov     rcx, rsi
0x18002e6cc  cmp     rbx, r8
0x18002e6cf  jb      short loc_18002E728
0x18002e6d1  test    r8, r8
0x18002e6d4  jz      short loc_18002E6E2
0x18002e6d6  lea     rdx, [rax+rcx]; Src
0x18002e6da  mov     rcx, r14; void *
0x18002e6dd  call    memmove_0
0x18002e6e2  cmp     rbx, rdi
0x18002e6e5  jbe     short loc_18002E700
0x18002e6e7  sub     rbx, rdi
0x18002e6ea  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x18002e6ee  ja      short loc_18002E728
0x18002e6f0  movzx   edx, byte ptr [rsi+10h]; Val
0x18002e6f4  lea     rcx, [rdi+r14]; void *
0x18002e6f8  mov     r8, rbx; Size
0x18002e6fb  call    memset_0
0x18002e700  xor     ebx, ebx
0x18002e702  mov     eax, ebx
0x18002e704  jmp     short loc_18002E70A
0x18002e706  mov     eax, [rsp+68h+var_30]
0x18002e70a  mov     rcx, [rsp+68h+var_28]
0x18002e70f  xor     rcx, rsp; StackCookie
0x18002e712  call    __security_check_cookie
0x18002e717  mov     rbx, [rsp+68h+arg_18]
0x18002e71f  add     rsp, 50h
0x18002e723  pop     r14
0x18002e725  pop     rdi
0x18002e726  pop     rsi
0x18002e727  retn
0x18002e728  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
