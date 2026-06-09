# wsm_wstring::init(ushort const *)

- ea: `0x14000ce88`
- end: `0x14000cf97`
- name: `?init@wsm_wstring@@IEAAJPEBG@Z`
- size: `271`
- prototype: `__int64 __fastcall(wsm_wstring *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a7a4`
- `0x14000adb8`
- `0x14000b064`
- `0x14000c410`
- `0x14000c570`
- `0x14000cdc0`

## callees

- `0x140009368`
- `0x14000c2bc`
- `0x14000ce88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ced1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ced1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf7f`

## pseudocode

```c
__int64 __fastcall wsm_wstring::init(wsm_wstring *this, const struct std::nothrow_t *a2)
{
  void **v2; // rbx
  void *v5; // rcx
  void **v6; // rax
  void **v7; // rbx
  void *v8; // rcx
  void **v10; // rdi
  void *v11; // rcx

  v2 = (void **)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
  {
    v5 = *v2;
    if ( *v2 != v2 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  if ( a2 )
  {
    v6 = (void **)operator new(0x20u, a2);
    v7 = v6;
    if ( !v6 )
      return 3221225626LL;
    *((_WORD *)v6 + 8) = 0;
    *v6 = v6 + 2;
    v6[1] = v6 + 2;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v6,
                             a2) )
    {
      v8 = *v7;
      if ( *v7 != v7 + 2 )
      {
        if ( v8 )
          ExFreePoolWithTag(v8, 0x6E6D7377u);
      }
      ExFreePoolWithTag(v7, 0x6E6D7377u);
      return 3221225626LL;
    }
    v10 = (void **)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v7;
    if ( v10 )
    {
      v11 = *v10;
      if ( *v10 != v10 + 2 && v11 )
        ExFreePoolWithTag(v11, 0x6E6D7377u);
      ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000ce88  push    rbx
0x14000ce8a  push    rbp
0x14000ce8b  push    rsi
0x14000ce8c  push    rdi
0x14000ce8d  sub     rsp, 28h
0x14000ce91  mov     rbx, [rcx+8]
0x14000ce95  mov     rdi, rdx
0x14000ce98  mov     qword ptr [rcx+8], 0
0x14000cea0  mov     rsi, rcx
0x14000cea3  mov     ebp, 6E6D7377h
0x14000cea8  test    rbx, rbx
0x14000ceab  jz      short loc_14000CEDD
0x14000cead  mov     rcx, [rbx]; P
0x14000ceb0  lea     rax, [rbx+10h]
0x14000ceb4  cmp     rcx, rax
0x14000ceb7  jz      short loc_14000CECC
0x14000ceb9  test    rcx, rcx
0x14000cebc  jz      short loc_14000CECC
0x14000cebe  mov     edx, ebp; Tag
0x14000cec0  call    cs:__imp_ExFreePoolWithTag
0x14000cec7  nop     dword ptr [rax+rax+00h]
0x14000cecc  mov     edx, ebp; Tag
0x14000cece  mov     rcx, rbx; P
0x14000ced1  call    cs:__imp_ExFreePoolWithTag
0x14000ced8  nop     dword ptr [rax+rax+00h]
0x14000cedd  test    rdi, rdi
0x14000cee0  jz      loc_14000CF8B
0x14000cee6  mov     ecx, 20h ; ' '; NumberOfBytes
0x14000ceeb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000cef0  mov     rbx, rax
0x14000cef3  test    rax, rax
0x14000cef6  jz      short loc_14000CF47
0x14000cef8  lea     rdx, [rax+10h]
0x14000cefc  xor     ecx, ecx
0x14000cefe  mov     [rdx], cx
0x14000cf01  mov     rcx, rax
0x14000cf04  mov     [rax], rdx
0x14000cf07  mov     [rax+8], rdx
0x14000cf0b  mov     rdx, rdi
0x14000cf0e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x14000cf13  test    al, al
0x14000cf15  jnz     short loc_14000CF4E
0x14000cf17  mov     rcx, [rbx]; P
0x14000cf1a  lea     rax, [rbx+10h]
0x14000cf1e  cmp     rcx, rax
0x14000cf21  jz      short loc_14000CF36
0x14000cf23  test    rcx, rcx
0x14000cf26  jz      short loc_14000CF36
0x14000cf28  mov     edx, ebp; Tag
0x14000cf2a  call    cs:__imp_ExFreePoolWithTag
0x14000cf31  nop     dword ptr [rax+rax+00h]
0x14000cf36  mov     edx, ebp; Tag
0x14000cf38  mov     rcx, rbx; P
0x14000cf3b  call    cs:__imp_ExFreePoolWithTag
0x14000cf42  nop     dword ptr [rax+rax+00h]
0x14000cf47  mov     eax, 0C000009Ah
0x14000cf4c  jmp     short loc_14000CF8D
0x14000cf4e  mov     rdi, [rsi+8]
0x14000cf52  mov     [rsi+8], rbx
0x14000cf56  test    rdi, rdi
0x14000cf59  jz      short loc_14000CF8B
0x14000cf5b  mov     rcx, [rdi]; P
0x14000cf5e  lea     rax, [rdi+10h]
0x14000cf62  cmp     rcx, rax
0x14000cf65  jz      short loc_14000CF7A
0x14000cf67  test    rcx, rcx
0x14000cf6a  jz      short loc_14000CF7A
0x14000cf6c  mov     edx, ebp; Tag
0x14000cf6e  call    cs:__imp_ExFreePoolWithTag
0x14000cf75  nop     dword ptr [rax+rax+00h]
0x14000cf7a  mov     edx, ebp; Tag
0x14000cf7c  mov     rcx, rdi; P
0x14000cf7f  call    cs:__imp_ExFreePoolWithTag
0x14000cf86  nop     dword ptr [rax+rax+00h]
0x14000cf8b  xor     eax, eax
0x14000cf8d  add     rsp, 28h
0x14000cf91  pop     rdi
0x14000cf92  pop     rsi
0x14000cf93  pop     rbp
0x14000cf94  pop     rbx
0x14000cf95  retn
```
