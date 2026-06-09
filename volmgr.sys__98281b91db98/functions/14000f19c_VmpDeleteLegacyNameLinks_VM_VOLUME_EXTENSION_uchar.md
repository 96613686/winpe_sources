# VmpDeleteLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)

- ea: `0x14000f19c`
- end: `0x14000f36f`
- name: `?VmpDeleteLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z`
- size: `467`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int8)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000e888`
- `0x14000eba0`
- `0x140010ad8`

## callees

- `0x140005050`
- `0x140005090`
- `0x14000f19c`
- `0x140015490`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f236`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f260`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f28a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2b4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2dc`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2ef`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f30e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f321`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f34a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f236`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f260`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f28a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2b4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2dc`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f2ef`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f30e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f321`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000f34a`

## pseudocode

```c
void __fastcall VmpDeleteLegacyNameLinks(struct VM_VOLUME_EXTENSION *a1, char a2)
{
  bool v2; // zf
  __int64 v5; // rcx
  unsigned int *v6; // rdi
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-89h] BYREF
  char v8; // [rsp+30h] [rbp-79h] BYREF

  v2 = *((_BYTE *)a1 + 426) == 0;
  SymbolicLinkName.Buffer = (PWSTR)&v8;
  *(_QWORD *)&SymbolicLinkName.Length = 10485760;
  if ( v2 )
  {
    v6 = (unsigned int *)((char *)a1 + 388);
    if ( *((_BYTE *)a1 + 155) )
    {
      ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
        &SymbolicLinkName,
        5,
        *((unsigned int *)a1 + 96),
        *v6);
      IoDeleteSymbolicLink(&SymbolicLinkName);
      ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
        &SymbolicLinkName,
        2,
        *((unsigned int *)a1 + 96),
        *v6);
      IoDeleteSymbolicLink(&SymbolicLinkName);
    }
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      4,
      *((unsigned int *)a1 + 96),
      *v6);
    IoDeleteSymbolicLink(&SymbolicLinkName);
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      1,
      *((unsigned int *)a1 + 96),
      *v6);
    IoDeleteSymbolicLink(&SymbolicLinkName);
  }
  else
  {
    v5 = *((_QWORD *)a1 + 54);
    if ( !v5 )
      return;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 192LL))(
      v5,
      *(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL));
  }
  if ( !a2 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x100) != 0 )
    {
      IoDeleteSymbolicLink((PUNICODE_STRING)&::SymbolicLinkName);
      IoDeleteSymbolicLink((PUNICODE_STRING)&stru_140007000);
    }
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x200000) != 0 )
    {
      IoDeleteSymbolicLink((PUNICODE_STRING)&stru_140007050);
      IoDeleteSymbolicLink((PUNICODE_STRING)&stru_140007030);
    }
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      3,
      *((unsigned int *)a1 + 41),
      0);
    IoDeleteSymbolicLink(&SymbolicLinkName);
  }
}

```

## disassembly

```asm
0x14000f19c  push    rbp
0x14000f19e  push    rbx
0x14000f19f  push    rsi
0x14000f1a0  push    rdi
0x14000f1a1  lea     rbp, [rsp-3Fh]
0x14000f1a6  sub     rsp, 0E8h
0x14000f1ad  mov     rax, cs:__security_cookie
0x14000f1b4  xor     rax, rsp
0x14000f1b7  mov     [rbp+57h+var_30], rax
0x14000f1bb  cmp     byte ptr [rcx+1AAh], 0
0x14000f1c2  lea     rax, [rbp+57h+var_D0]
0x14000f1c6  mov     [rsp+100h+SymbolicLinkName.Buffer], rax
0x14000f1cb  mov     sil, dl
0x14000f1ce  mov     rbx, rcx
0x14000f1d1  mov     qword ptr [rsp+100h+SymbolicLinkName.Length], 0A00000h
0x14000f1da  jz      short loc_14000F208
0x14000f1dc  mov     rcx, [rcx+1B0h]
0x14000f1e3  test    rcx, rcx
0x14000f1e6  jz      loc_14000F356
0x14000f1ec  mov     rax, [rbx+8]
0x14000f1f0  mov     rdx, [rax+188h]
0x14000f1f7  mov     rax, [rdx+0C0h]
0x14000f1fe  call    _guard_dispatch_icall
0x14000f203  jmp     loc_14000F2C0
0x14000f208  cmp     byte ptr [rcx+9Bh], 0
0x14000f20f  lea     rdi, [rcx+184h]
0x14000f216  jz      short loc_14000F26C
0x14000f218  mov     r8d, [rcx+180h]
0x14000f21f  mov     edx, 5
0x14000f224  mov     r9d, [rdi]
0x14000f227  lea     rcx, [rsp+100h+SymbolicLinkName]
0x14000f22c  call    VmpBuildName
0x14000f231  lea     rcx, [rsp+100h+SymbolicLinkName]; SymbolicLinkName
0x14000f236  call    cs:__imp_IoDeleteSymbolicLink
0x14000f23d  nop     dword ptr [rax+rax+00h]
0x14000f242  mov     r9d, [rdi]
0x14000f245  lea     rcx, [rsp+100h+SymbolicLinkName]
0x14000f24a  mov     r8d, [rbx+180h]
0x14000f251  mov     edx, 2
0x14000f256  call    VmpBuildName
0x14000f25b  lea     rcx, [rsp+100h+SymbolicLinkName]; SymbolicLinkName
0x14000f260  call    cs:__imp_IoDeleteSymbolicLink
0x14000f267  nop     dword ptr [rax+rax+00h]
0x14000f26c  mov     r9d, [rdi]
0x14000f26f  lea     rcx, [rsp+100h+SymbolicLinkName]
0x14000f274  mov     r8d, [rbx+180h]
0x14000f27b  mov     edx, 4
0x14000f280  call    VmpBuildName
0x14000f285  lea     rcx, [rsp+100h+SymbolicLinkName]; SymbolicLinkName
0x14000f28a  call    cs:__imp_IoDeleteSymbolicLink
0x14000f291  nop     dword ptr [rax+rax+00h]
0x14000f296  mov     r9d, [rdi]
0x14000f299  lea     rcx, [rsp+100h+SymbolicLinkName]
0x14000f29e  mov     r8d, [rbx+180h]
0x14000f2a5  mov     edx, 1
0x14000f2aa  call    VmpBuildName
0x14000f2af  lea     rcx, [rsp+100h+SymbolicLinkName]; SymbolicLinkName
0x14000f2b4  call    cs:__imp_IoDeleteSymbolicLink
0x14000f2bb  nop     dword ptr [rax+rax+00h]
0x14000f2c0  test    sil, sil
0x14000f2c3  jnz     loc_14000F356
0x14000f2c9  mov     rax, [rbx]
0x14000f2cc  mov     ecx, [rax+30h]
0x14000f2cf  bt      ecx, 8
0x14000f2d3  jnb     short loc_14000F2FB
0x14000f2d5  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x14000f2dc  call    cs:__imp_IoDeleteSymbolicLink
0x14000f2e3  nop     dword ptr [rax+rax+00h]
0x14000f2e8  lea     rcx, stru_140007000; SymbolicLinkName
0x14000f2ef  call    cs:__imp_IoDeleteSymbolicLink
0x14000f2f6  nop     dword ptr [rax+rax+00h]
0x14000f2fb  mov     rax, [rbx]
0x14000f2fe  mov     ecx, [rax+30h]
0x14000f301  bt      ecx, 15h
0x14000f305  jnb     short loc_14000F32D
0x14000f307  lea     rcx, stru_140007050; SymbolicLinkName
0x14000f30e  call    cs:__imp_IoDeleteSymbolicLink
0x14000f315  nop     dword ptr [rax+rax+00h]
0x14000f31a  lea     rcx, stru_140007030; SymbolicLinkName
0x14000f321  call    cs:__imp_IoDeleteSymbolicLink
0x14000f328  nop     dword ptr [rax+rax+00h]
0x14000f32d  mov     r8d, [rbx+0A4h]
0x14000f334  lea     rcx, [rsp+100h+SymbolicLinkName]
0x14000f339  xor     r9d, r9d
0x14000f33c  lea     edx, [r9+3]
0x14000f340  call    VmpBuildName
0x14000f345  lea     rcx, [rsp+100h+SymbolicLinkName]; SymbolicLinkName
0x14000f34a  call    cs:__imp_IoDeleteSymbolicLink
0x14000f351  nop     dword ptr [rax+rax+00h]
0x14000f356  mov     rcx, [rbp+57h+var_30]
0x14000f35a  xor     rcx, rsp; StackCookie
0x14000f35d  call    __security_check_cookie
0x14000f362  add     rsp, 0E8h
0x14000f369  pop     rdi
0x14000f36a  pop     rsi
0x14000f36b  pop     rbx
0x14000f36c  pop     rbp
0x14000f36d  retn
```
