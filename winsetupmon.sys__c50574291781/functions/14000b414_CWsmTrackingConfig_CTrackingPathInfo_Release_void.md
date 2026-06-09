# CWsmTrackingConfig::CTrackingPathInfo::Release(void)

- ea: `0x14000b414`
- end: `0x14000b4a1`
- name: `?Release@CTrackingPathInfo@CWsmTrackingConfig@@IEAAXXZ`
- size: `141`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingPathInfo *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400091cc`
- `0x14000cad0`

## callees

- `0x14000888c`
- `0x14000b414`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b460`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b474`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b460`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b474`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingPathInfo::Release(CWsmTrackingConfig::CTrackingPathInfo *this)
{
  __int64 v1; // rdx
  __int64 v3; // r8
  void **v4; // rdi
  void *v5; // rcx

  v1 = *((_QWORD *)this + 1);
  v3 = *((_QWORD *)this + 2) - v1;
  *((_QWORD *)this + 2) = v1;
  utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
    (__int64)this,
    v1,
    v3 >> 3);
  v4 = (void **)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 != v4 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  }
  *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x14000b414  mov     [rsp+arg_0], rbx
0x14000b419  push    rdi
0x14000b41a  sub     rsp, 20h
0x14000b41e  mov     rdx, [rcx+8]
0x14000b422  mov     rbx, rcx
0x14000b425  mov     r8, [rcx+10h]
0x14000b429  sub     r8, rdx
0x14000b42c  mov     [rcx+10h], rdx
0x14000b430  sar     r8, 3
0x14000b434  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x14000b439  mov     rdi, [rbx+28h]
0x14000b43d  mov     qword ptr [rbx+28h], 0
0x14000b445  test    rdi, rdi
0x14000b448  jz      short loc_14000B480
0x14000b44a  mov     rcx, [rdi]; P
0x14000b44d  lea     rax, [rdi+10h]
0x14000b451  cmp     rcx, rax
0x14000b454  jz      short loc_14000B46C
0x14000b456  test    rcx, rcx
0x14000b459  jz      short loc_14000B46C
0x14000b45b  mov     edx, 6E6D7377h; Tag
0x14000b460  call    cs:__imp_ExFreePoolWithTag
0x14000b467  nop     dword ptr [rax+rax+00h]
0x14000b46c  mov     edx, 6E6D7377h; Tag
0x14000b471  mov     rcx, rdi; P
0x14000b474  call    cs:__imp_ExFreePoolWithTag
0x14000b47b  nop     dword ptr [rax+rax+00h]
0x14000b480  mov     rax, [rbx+30h]
0x14000b484  xorps   xmm0, xmm0
0x14000b487  mov     [rbx+38h], rax
0x14000b48b  xor     eax, eax
0x14000b48d  movups  xmmword ptr [rbx+48h], xmm0
0x14000b491  mov     [rbx+58h], rax
0x14000b495  mov     rbx, [rsp+28h+arg_0]
0x14000b49a  add     rsp, 20h
0x14000b49e  pop     rdi
0x14000b49f  retn
```
