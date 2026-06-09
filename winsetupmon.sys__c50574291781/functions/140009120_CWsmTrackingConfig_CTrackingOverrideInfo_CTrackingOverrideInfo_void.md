# CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)

- ea: `0x140009120`
- end: `0x1400091c6`
- name: `??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ`
- size: `166`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingOverrideInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000888c`
- `0x140008b58`
- `0x140009b70`
- `0x14000a7a4`
- `0x14000adb8`
- `0x14000cad0`

## callees

- `0x140009120`
- `0x14000b358`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000915b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000916f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000919a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400091ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000915b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000916f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000919a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400091ae`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void ***this)
{
  void **v2; // rbx
  void *v3; // rcx
  void **v4; // rbx
  void *v5; // rcx

  *this = &CWsmTrackingConfig::CTrackingOverrideInfo::`vftable';
  CWsmTrackingConfig::CTrackingOverrideInfo::Release((CWsmTrackingConfig::CTrackingOverrideInfo *)this);
  v2 = this[4];
  if ( v2 )
  {
    v3 = *v2;
    if ( *v2 != v2 + 2 && v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  v4 = this[2];
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 != v4 + 2 )
    {
      if ( v5 )
        ExFreePoolWithTag(v5, 0x6E6D7377u);
    }
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x140009120  mov     [rsp+arg_0], rbx
0x140009125  push    rdi
0x140009126  sub     rsp, 20h
0x14000912a  lea     rax, ??_7CTrackingOverrideInfo@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingOverrideInfo::`vftable'
0x140009131  mov     rdi, rcx
0x140009134  mov     [rcx], rax
0x140009137  call    ?Release@CTrackingOverrideInfo@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingOverrideInfo::Release(void)
0x14000913c  mov     rbx, [rdi+20h]
0x140009140  test    rbx, rbx
0x140009143  jz      short loc_14000917B
0x140009145  mov     rcx, [rbx]; P
0x140009148  lea     rax, [rbx+10h]
0x14000914c  cmp     rcx, rax
0x14000914f  jz      short loc_140009167
0x140009151  test    rcx, rcx
0x140009154  jz      short loc_140009167
0x140009156  mov     edx, 6E6D7377h; Tag
0x14000915b  call    cs:__imp_ExFreePoolWithTag
0x140009162  nop     dword ptr [rax+rax+00h]
0x140009167  mov     edx, 6E6D7377h; Tag
0x14000916c  mov     rcx, rbx; P
0x14000916f  call    cs:__imp_ExFreePoolWithTag
0x140009176  nop     dword ptr [rax+rax+00h]
0x14000917b  mov     rbx, [rdi+10h]
0x14000917f  test    rbx, rbx
0x140009182  jz      short loc_1400091BA
0x140009184  mov     rcx, [rbx]; P
0x140009187  lea     rax, [rbx+10h]
0x14000918b  cmp     rcx, rax
0x14000918e  jz      short loc_1400091A6
0x140009190  test    rcx, rcx
0x140009193  jz      short loc_1400091A6
0x140009195  mov     edx, 6E6D7377h; Tag
0x14000919a  call    cs:__imp_ExFreePoolWithTag
0x1400091a1  nop     dword ptr [rax+rax+00h]
0x1400091a6  mov     edx, 6E6D7377h; Tag
0x1400091ab  mov     rcx, rbx; P
0x1400091ae  call    cs:__imp_ExFreePoolWithTag
0x1400091b5  nop     dword ptr [rax+rax+00h]
0x1400091ba  mov     rbx, [rsp+28h+arg_0]
0x1400091bf  add     rsp, 20h
0x1400091c3  pop     rdi
0x1400091c4  retn
```
