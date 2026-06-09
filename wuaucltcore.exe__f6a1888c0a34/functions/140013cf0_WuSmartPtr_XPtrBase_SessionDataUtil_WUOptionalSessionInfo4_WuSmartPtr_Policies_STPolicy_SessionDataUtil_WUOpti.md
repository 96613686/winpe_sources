# WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)

- ea: `0x140013cf0`
- end: `0x140013d6a`
- name: `?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ`
- size: `122`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140013a74`
- `0x140013bbc`
- `0x140013c18`
- `0x140013d70`
- `0x140016b20`
- `0x140016ef8`
- `0x1400170dc`
- `0x140017624`
- `0x140017b48`

## callees

- `0x14000d4cc`
- `0x140013cf0`
- `0x140013de4`
- `0x14001acf4`

## pseudocode

```c
void __fastcall WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(
        __int64 *a1)
{
  __int64 v1; // rbx
  void *v3; // rcx
  void *v4; // rsi

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *(void **)(v1 + 16);
    if ( v3 )
    {
      SusFree(v3);
      *(_QWORD *)(v1 + 16) = 0;
    }
    v4 = *(void **)(v1 + 8);
    if ( v4 )
    {
      SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(*(SessionDataUtil::WUOptionalSessionInfo3 **)(v1 + 8));
      operator delete(v4, (const struct std::nothrow_t *)0x18);
      *(_QWORD *)(v1 + 8) = 0;
    }
    operator delete((void *)v1, (const struct std::nothrow_t *)0x18);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140013cf0  mov     [rsp+arg_0], rbx
0x140013cf5  mov     [rsp+arg_8], rsi
0x140013cfa  push    rdi
0x140013cfb  sub     rsp, 20h
0x140013cff  mov     rbx, [rcx]
0x140013d02  mov     rdi, rcx
0x140013d05  test    rbx, rbx
0x140013d08  jz      short loc_140013D5A
0x140013d0a  mov     rcx, [rbx+10h]; lpMem
0x140013d0e  test    rcx, rcx
0x140013d11  jz      short loc_140013D20
0x140013d13  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140013d18  mov     qword ptr [rbx+10h], 0
0x140013d20  mov     rsi, [rbx+8]
0x140013d24  test    rsi, rsi
0x140013d27  jz      short loc_140013D46
0x140013d29  mov     rcx, rsi; this
0x140013d2c  call    ??1WUOptionalSessionInfo3@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(void)
0x140013d31  mov     edx, 18h; struct std::nothrow_t *
0x140013d36  mov     rcx, rsi; void *
0x140013d39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013d3e  mov     qword ptr [rbx+8], 0
0x140013d46  mov     edx, 18h; struct std::nothrow_t *
0x140013d4b  mov     rcx, rbx; void *
0x140013d4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140013d53  mov     qword ptr [rdi], 0
0x140013d5a  mov     rbx, [rsp+28h+arg_0]
0x140013d5f  mov     rsi, [rsp+28h+arg_8]
0x140013d64  add     rsp, 20h
0x140013d68  pop     rdi
0x140013d69  retn
```
