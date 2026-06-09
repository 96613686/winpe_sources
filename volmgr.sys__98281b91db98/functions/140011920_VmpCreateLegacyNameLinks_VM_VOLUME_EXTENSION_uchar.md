# VmpCreateLegacyNameLinks(VM_VOLUME_EXTENSION *,uchar)

- ea: `0x140011920`
- end: `0x140011bd0`
- name: `?VmpCreateLegacyNameLinks@@YAXPEAVVM_VOLUME_EXTENSION@@E@Z`
- size: `688`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400046a4`
- `0x14000eba0`
- `0x140010ad8`

## callees

- `0x140005050`
- `0x140005090`
- `0x140011920`
- `0x140014d8c`
- `0x140015490`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140011a11`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140011a83`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140011a11`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140011a83`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119b5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119d9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119f1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a27`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a4b`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a63`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a99`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011afd`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b30`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b6c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b9f`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119b5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119d9`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400119f1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a27`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a4b`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a63`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011a99`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011afd`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b30`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b6c`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140011b9f`

## pseudocode

```c
void __fastcall VmpCreateLegacyNameLinks(struct VM_VOLUME_EXTENSION *a1, char a2)
{
  __int64 v2; // r8
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[128]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[192]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = *((unsigned int *)a1 + 41);
  DeviceName.Buffer = (PWSTR)v7;
  *(_QWORD *)&DeviceName.Length = 0x800000;
  ((void (__fastcall *)(struct _UNICODE_STRING *, _QWORD, __int64, _QWORD, __int64, _BYTE *))VmpBuildName)(
    &DeviceName,
    0,
    v2,
    0,
    12582912,
    v8);
  if ( !a2 )
  {
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      3,
      *((unsigned int *)a1 + 41),
      0);
    IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x200000) != 0 )
    {
      IoCreateSymbolicLink((PUNICODE_STRING)&stru_140007030, &DeviceName);
      IoCreateSymbolicLink((PUNICODE_STRING)&stru_140007050, &DeviceName);
      VmpBuildArcName(&SymbolicLinkName, 6);
      IoDeleteSymbolicLink(&SymbolicLinkName);
      IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    }
    if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x100) != 0 )
    {
      IoCreateSymbolicLink((PUNICODE_STRING)&stru_140007000, &DeviceName);
      IoCreateSymbolicLink((PUNICODE_STRING)&::SymbolicLinkName, &DeviceName);
      VmpBuildArcName(&SymbolicLinkName, 7);
      IoDeleteSymbolicLink(&SymbolicLinkName);
      IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    }
  }
  if ( *((_BYTE *)a1 + 426) )
  {
    (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 184LL))(
      *((_QWORD *)a1 + 54),
      v7);
  }
  else
  {
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      1,
      *((unsigned int *)a1 + 96),
      *((unsigned int *)a1 + 97));
    IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
      &SymbolicLinkName,
      4,
      *((unsigned int *)a1 + 96),
      *((unsigned int *)a1 + 97));
    IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    if ( *((_BYTE *)a1 + 155) )
    {
      ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
        &SymbolicLinkName,
        2,
        *((unsigned int *)a1 + 96),
        *((unsigned int *)a1 + 97));
      IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
      ((void (__fastcall *)(struct _UNICODE_STRING *, __int64, _QWORD, _QWORD))VmpBuildName)(
        &SymbolicLinkName,
        5,
        *((unsigned int *)a1 + 96),
        *((unsigned int *)a1 + 97));
      IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    }
  }
}

```

## disassembly

```asm
0x140011920  mov     [rsp-8+arg_8], rbx
0x140011925  mov     [rsp-8+arg_10], rdi
0x14001192a  push    rbp
0x14001192b  lea     rbp, [rsp-90h]
0x140011933  sub     rsp, 190h
0x14001193a  mov     rax, cs:__security_cookie
0x140011941  xor     rax, rsp
0x140011944  mov     [rbp+90h+var_10], rax
0x14001194b  mov     r8d, [rcx+0A4h]
0x140011952  lea     rax, [rsp+190h+var_150]
0x140011957  mov     [rsp+190h+DeviceName.Buffer], rax
0x14001195c  mov     bl, dl
0x14001195e  lea     rax, [rbp+90h+var_D0]
0x140011962  mov     qword ptr [rsp+190h+DeviceName.Length], 800000h
0x14001196b  mov     rdi, rcx
0x14001196e  mov     [rsp+190h+SymbolicLinkName.Buffer], rax
0x140011973  xor     r9d, r9d
0x140011976  mov     qword ptr [rsp+190h+SymbolicLinkName.Length], 0C00000h
0x14001197f  xor     edx, edx
0x140011981  lea     rcx, [rsp+190h+DeviceName]
0x140011986  call    VmpBuildName
0x14001198b  test    bl, bl
0x14001198d  jnz     loc_140011AA5
0x140011993  mov     r8d, [rdi+0A4h]
0x14001199a  lea     rcx, [rsp+190h+SymbolicLinkName]
0x14001199f  xor     r9d, r9d
0x1400119a2  lea     edx, [r9+3]
0x1400119a6  call    VmpBuildName
0x1400119ab  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x1400119b0  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x1400119b5  call    cs:__imp_IoCreateSymbolicLink
0x1400119bc  nop     dword ptr [rax+rax+00h]
0x1400119c1  mov     rax, [rdi]
0x1400119c4  mov     ecx, [rax+30h]
0x1400119c7  bt      ecx, 15h
0x1400119cb  jnb     short loc_140011A33
0x1400119cd  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x1400119d2  lea     rcx, stru_140007030; SymbolicLinkName
0x1400119d9  call    cs:__imp_IoCreateSymbolicLink
0x1400119e0  nop     dword ptr [rax+rax+00h]
0x1400119e5  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x1400119ea  lea     rcx, stru_140007050; SymbolicLinkName
0x1400119f1  call    cs:__imp_IoCreateSymbolicLink
0x1400119f8  nop     dword ptr [rax+rax+00h]
0x1400119fd  mov     edx, 6
0x140011a02  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011a07  call    VmpBuildArcName
0x140011a0c  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011a11  call    cs:__imp_IoDeleteSymbolicLink
0x140011a18  nop     dword ptr [rax+rax+00h]
0x140011a1d  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011a22  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011a27  call    cs:__imp_IoCreateSymbolicLink
0x140011a2e  nop     dword ptr [rax+rax+00h]
0x140011a33  mov     rax, [rdi]
0x140011a36  mov     ecx, [rax+30h]
0x140011a39  bt      ecx, 8
0x140011a3d  jnb     short loc_140011AA5
0x140011a3f  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011a44  lea     rcx, stru_140007000; SymbolicLinkName
0x140011a4b  call    cs:__imp_IoCreateSymbolicLink
0x140011a52  nop     dword ptr [rax+rax+00h]
0x140011a57  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011a5c  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x140011a63  call    cs:__imp_IoCreateSymbolicLink
0x140011a6a  nop     dword ptr [rax+rax+00h]
0x140011a6f  mov     edx, 7
0x140011a74  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011a79  call    VmpBuildArcName
0x140011a7e  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011a83  call    cs:__imp_IoDeleteSymbolicLink
0x140011a8a  nop     dword ptr [rax+rax+00h]
0x140011a8f  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011a94  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011a99  call    cs:__imp_IoCreateSymbolicLink
0x140011aa0  nop     dword ptr [rax+rax+00h]
0x140011aa5  cmp     byte ptr [rdi+1AAh], 0
0x140011aac  jz      short loc_140011AD6
0x140011aae  mov     rax, [rdi+8]
0x140011ab2  mov     rcx, [rdi+1B0h]
0x140011ab9  mov     rdx, [rax+188h]
0x140011ac0  mov     rax, [rdx+0B8h]
0x140011ac7  lea     rdx, [rsp+190h+var_150]
0x140011acc  call    _guard_dispatch_icall
0x140011ad1  jmp     loc_140011BAB
0x140011ad6  mov     r9d, [rdi+184h]
0x140011add  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011ae2  mov     r8d, [rdi+180h]
0x140011ae9  mov     edx, 1
0x140011aee  call    VmpBuildName
0x140011af3  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011af8  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011afd  call    cs:__imp_IoCreateSymbolicLink
0x140011b04  nop     dword ptr [rax+rax+00h]
0x140011b09  mov     r9d, [rdi+184h]
0x140011b10  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011b15  mov     r8d, [rdi+180h]
0x140011b1c  mov     edx, 4
0x140011b21  call    VmpBuildName
0x140011b26  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011b2b  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011b30  call    cs:__imp_IoCreateSymbolicLink
0x140011b37  nop     dword ptr [rax+rax+00h]
0x140011b3c  cmp     byte ptr [rdi+9Bh], 0
0x140011b43  jz      short loc_140011BAB
0x140011b45  mov     r9d, [rdi+184h]
0x140011b4c  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011b51  mov     r8d, [rdi+180h]
0x140011b58  mov     edx, 2
0x140011b5d  call    VmpBuildName
0x140011b62  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011b67  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011b6c  call    cs:__imp_IoCreateSymbolicLink
0x140011b73  nop     dword ptr [rax+rax+00h]
0x140011b78  mov     r9d, [rdi+184h]
0x140011b7f  lea     rcx, [rsp+190h+SymbolicLinkName]
0x140011b84  mov     r8d, [rdi+180h]
0x140011b8b  mov     edx, 5
0x140011b90  call    VmpBuildName
0x140011b95  lea     rdx, [rsp+190h+DeviceName]; DeviceName
0x140011b9a  lea     rcx, [rsp+190h+SymbolicLinkName]; SymbolicLinkName
0x140011b9f  call    cs:__imp_IoCreateSymbolicLink
0x140011ba6  nop     dword ptr [rax+rax+00h]
0x140011bab  mov     rcx, [rbp+90h+var_10]
0x140011bb2  xor     rcx, rsp; StackCookie
0x140011bb5  call    __security_check_cookie
0x140011bba  lea     r11, [rsp+190h+var_s0]
0x140011bc2  mov     rbx, [r11+18h]
0x140011bc6  mov     rdi, [r11+20h]
0x140011bca  mov     rsp, r11
0x140011bcd  pop     rbp
0x140011bce  retn
```
