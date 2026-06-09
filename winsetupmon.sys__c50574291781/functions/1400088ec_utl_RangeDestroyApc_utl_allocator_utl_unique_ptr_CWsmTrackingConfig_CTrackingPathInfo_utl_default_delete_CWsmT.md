# utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)

- ea: `0x1400088ec`
- end: `0x140008944`
- name: `??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z`
- size: `88`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009018`
- `0x14000b280`
- `0x14000b77c`
- `0x14000baf0`
- `0x14000c1d8`
- `0x14000d21c`

## callees

- `0x1400088ec`
- `0x1400091cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008922`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008922`

## pseudocode

```c
void __fastcall utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  void *v5; // rdi

  if ( a3 )
  {
    v3 = a3;
    do
    {
      --v3;
      v5 = *(void **)(a2 + 8 * v3);
      if ( v5 )
      {
        CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(*(void ****)(a2 + 8 * v3));
        ExFreePoolWithTag(v5, 0x6E6D7377u);
      }
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x1400088ec  test    r8, r8
0x1400088ef  jz      short locret_140008942
0x1400088f1  mov     [rsp+arg_0], rbx
0x1400088f6  mov     [rsp+arg_8], rsi
0x1400088fb  push    rdi
0x1400088fc  sub     rsp, 20h
0x140008900  mov     rbx, r8
0x140008903  mov     rsi, rdx
0x140008906  dec     rbx
0x140008909  mov     rdi, [rsi+rbx*8]
0x14000890d  test    rdi, rdi
0x140008910  jz      short loc_14000892E
0x140008912  mov     rcx, rdi; this
0x140008915  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000891a  mov     edx, 6E6D7377h; Tag
0x14000891f  mov     rcx, rdi; P
0x140008922  call    cs:__imp_ExFreePoolWithTag
0x140008929  nop     dword ptr [rax+rax+00h]
0x14000892e  test    rbx, rbx
0x140008931  jnz     short loc_140008906
0x140008933  mov     rbx, [rsp+28h+arg_0]
0x140008938  mov     rsi, [rsp+28h+arg_8]
0x14000893d  add     rsp, 20h
0x140008941  pop     rdi
0x140008942  retn
```
