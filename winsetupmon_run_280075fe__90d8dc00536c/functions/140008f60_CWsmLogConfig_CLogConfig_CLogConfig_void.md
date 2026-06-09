# CWsmLogConfig::CLogConfig::~CLogConfig(void)

- ea: `0x140008f60`
- end: `0x140009010`
- name: `??1CLogConfig@CWsmLogConfig@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(CWsmLogConfig::CLogConfig *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009298`
- `0x14000b064`
- `0x14000bb50`

## callees

- `0x140008f60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008f9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008f9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008ff8`

## pseudocode

```c
void __fastcall CWsmLogConfig::CLogConfig::~CLogConfig(CWsmLogConfig::CLogConfig *this)
{
  void **v2; // rdi
  void *v3; // rcx
  void **v4; // rbx
  void *v5; // rcx

  *(_QWORD *)this = &CWsmLogConfig::CLogConfig::`vftable';
  v2 = (void **)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
  {
    v3 = *v2;
    if ( *v2 != v2 + 2 && v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  *(_OWORD *)((char *)this + 8) = 0;
  v4 = (void **)*((_QWORD *)this + 4);
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
0x140008f60  mov     [rsp+arg_0], rbx
0x140008f65  push    rdi
0x140008f66  sub     rsp, 20h
0x140008f6a  lea     rax, ??_7CLogConfig@CWsmLogConfig@@6B@; const CWsmLogConfig::CLogConfig::`vftable'
0x140008f71  mov     rbx, rcx
0x140008f74  mov     [rcx], rax
0x140008f77  mov     rdi, [rcx+20h]
0x140008f7b  mov     qword ptr [rcx+20h], 0
0x140008f83  test    rdi, rdi
0x140008f86  jz      short loc_140008FBE
0x140008f88  mov     rcx, [rdi]; P
0x140008f8b  lea     rax, [rdi+10h]
0x140008f8f  cmp     rcx, rax
0x140008f92  jz      short loc_140008FAA
0x140008f94  test    rcx, rcx
0x140008f97  jz      short loc_140008FAA
0x140008f99  mov     edx, 6E6D7377h; Tag
0x140008f9e  call    cs:__imp_ExFreePoolWithTag
0x140008fa5  nop     dword ptr [rax+rax+00h]
0x140008faa  mov     edx, 6E6D7377h; Tag
0x140008faf  mov     rcx, rdi; P
0x140008fb2  call    cs:__imp_ExFreePoolWithTag
0x140008fb9  nop     dword ptr [rax+rax+00h]
0x140008fbe  xorps   xmm0, xmm0
0x140008fc1  movups  xmmword ptr [rbx+8], xmm0
0x140008fc5  mov     rbx, [rbx+20h]
0x140008fc9  test    rbx, rbx
0x140008fcc  jz      short loc_140009004
0x140008fce  mov     rcx, [rbx]; P
0x140008fd1  lea     rax, [rbx+10h]
0x140008fd5  cmp     rcx, rax
0x140008fd8  jz      short loc_140008FF0
0x140008fda  test    rcx, rcx
0x140008fdd  jz      short loc_140008FF0
0x140008fdf  mov     edx, 6E6D7377h; Tag
0x140008fe4  call    cs:__imp_ExFreePoolWithTag
0x140008feb  nop     dword ptr [rax+rax+00h]
0x140008ff0  mov     edx, 6E6D7377h; Tag
0x140008ff5  mov     rcx, rbx; P
0x140008ff8  call    cs:__imp_ExFreePoolWithTag
0x140008fff  nop     dword ptr [rax+rax+00h]
0x140009004  mov     rbx, [rsp+28h+arg_0]
0x140009009  add     rsp, 20h
0x14000900d  pop     rdi
0x14000900e  retn
```
