# CWsmTrackingConfig::RemoveTracking(void)

- ea: `0x14000baf0`
- end: `0x14000bb49`
- name: `?RemoveTracking@CWsmTrackingConfig@@UEAAJXZ`
- size: `89`
- prototype: `__int64 __fastcall(CWsmTrackingConfig *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400088ec`
- `0x14000baf0`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::RemoveTracking(CWsmTrackingConfig *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8

  if ( (**((__int64 (__fastcall ***)(char *))this - 1))((char *)this - 8) )
  {
    v3 = *((_QWORD *)this + 4);
    v4 = *(_QWORD *)(v3 + 8);
    v5 = *(_QWORD *)(v3 + 16) - v4;
    *(_QWORD *)(v3 + 16) = v4;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
      v2,
      v4,
      v5 >> 3);
    *(_QWORD *)(v3 + 40) = *(_QWORD *)(v3 + 32);
    *(_DWORD *)(v3 + 104) = 0;
    *(_QWORD *)(v3 + 112) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14000baf0  push    rbx
0x14000baf2  sub     rsp, 20h
0x14000baf6  mov     rbx, rcx
0x14000baf9  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000bafd  mov     rax, [rcx]
0x14000bb00  mov     rax, [rax]
0x14000bb03  call    _guard_dispatch_icall
0x14000bb08  test    rax, rax
0x14000bb0b  jz      short loc_14000BB40
0x14000bb0d  mov     rbx, [rbx+20h]
0x14000bb11  mov     rdx, [rbx+8]
0x14000bb15  mov     r8, [rbx+10h]
0x14000bb19  sub     r8, rdx
0x14000bb1c  mov     [rbx+10h], rdx
0x14000bb20  sar     r8, 3
0x14000bb24  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000bb29  mov     rax, [rbx+20h]
0x14000bb2d  mov     [rbx+28h], rax
0x14000bb31  mov     dword ptr [rbx+68h], 0
0x14000bb38  mov     qword ptr [rbx+70h], 0
0x14000bb40  xor     eax, eax
0x14000bb42  add     rsp, 20h
0x14000bb46  pop     rbx
0x14000bb47  retn
```
