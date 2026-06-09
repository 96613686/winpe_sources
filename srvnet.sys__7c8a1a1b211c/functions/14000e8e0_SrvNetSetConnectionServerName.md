# SrvNetSetConnectionServerName

- ea: `0x14000e8e0`
- end: `0x14000eaaf`
- name: `SrvNetSetConnectionServerName`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000e8e0`
- `0x140017ce0`
- `0x14002a3e0`
- `0x14002ad60`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000e946`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000e946`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ea39`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ea39`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ea19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ea50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ea19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ea50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9fc`

## pseudocode

```c
int __fastcall SrvNetSetConnectionServerName(__int64 a1, const UNICODE_STRING *a2, _BYTE *a3)
{
  int result; // eax
  int v6; // edx
  NTSTATUS v7; // esi
  int v8; // r8d
  _WORD *v9; // rbx
  __int16 v10; // ax
  USHORT Length; // si
  KIRQL v12; // al
  KIRQL v13; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  char v15; // [rsp+40h] [rbp-30h] BYREF
  int v16; // [rsp+44h] [rbp-2Ch]

  *a3 = 0;
  v16 = 0;
  DestinationString = 0;
  if ( a2->Length > 0x20u )
    return -1073741811;
  DestinationString.MaximumLength = 32;
  DestinationString.Buffer = (PWSTR)&v15;
  v7 = RtlUpcaseUnicodeString(&DestinationString, a2, 0);
  if ( v7 < 0 )
    return v7;
  v9 = (_WORD *)(a1 + 576);
  v10 = *(_WORD *)(a1 + 576);
  if ( !v10 )
  {
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
    v13 = v12;
    if ( *(_DWORD *)(a1 + 484) != 3 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v12);
      return -1073741300;
    }
    if ( !*v9 )
    {
      RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 576), &DestinationString);
      *a3 = 1;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v13);
    if ( !*a3 )
    {
      if ( *v9 != DestinationString.Length )
        return -1073741623;
      if ( memcmp(*(const void **)(a1 + 584), DestinationString.Buffer, DestinationString.Length) )
        return -1073741623;
    }
    return v7;
  }
  Length = DestinationString.Length;
  if ( v10 != DestinationString.Length
    || (result = memcmp(*(const void **)(a1 + 584), DestinationString.Buffer, DestinationString.Length)) != 0 )
  {
    if ( (Length != 2 || strcmp((const char *)DestinationString.Buffer, (const char *)L"*"))
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_ZZq(WPP_GLOBAL_Control->AttachedDevice, v6, v8, a1 + 576, (__int64)&DestinationString, a1);
    }
    return -1073741623;
  }
  return result;
}

```

## disassembly

```asm
0x14000e8e0  mov     [rsp-38h+arg_18], rbx
0x14000e8e5  push    rbp
0x14000e8e6  push    rsi
0x14000e8e7  push    rdi
0x14000e8e8  push    r12
0x14000e8ea  push    r13
0x14000e8ec  push    r14
0x14000e8ee  push    r15
0x14000e8f0  mov     rbp, rsp
0x14000e8f3  sub     rsp, 70h
0x14000e8f7  mov     rax, cs:__security_cookie
0x14000e8fe  xor     rax, rsp
0x14000e901  mov     [rbp+var_10], rax
0x14000e905  xor     eax, eax
0x14000e907  xor     r13d, r13d
0x14000e90a  mov     rdi, rcx
0x14000e90d  mov     [r8], r13b
0x14000e910  xorps   xmm0, xmm0
0x14000e913  mov     [rbp+var_2C], eax
0x14000e916  mov     r12, r8
0x14000e919  lea     ecx, [rax+20h]
0x14000e91c  lea     r14d, [rax+2]
0x14000e920  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e924  cmp     [rdx], cx
0x14000e927  jbe     short loc_14000E933
0x14000e929  mov     eax, 0C000000Dh
0x14000e92e  jmp     loc_14000EA8A
0x14000e933  lea     rax, [rbp+var_30]
0x14000e937  mov     [rbp+DestinationString.MaximumLength], cx
0x14000e93b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e93f  mov     [rbp+DestinationString.Buffer], rax
0x14000e943  xor     r8d, r8d; AllocateDestinationString
0x14000e946  call    cs:__imp_RtlUpcaseUnicodeString
0x14000e94d  nop     dword ptr [rax+rax+00h]
0x14000e952  mov     esi, eax
0x14000e954  test    eax, eax
0x14000e956  js      loc_14000EA88
0x14000e95c  lea     rbx, [rdi+240h]
0x14000e963  movzx   eax, word ptr [rbx]
0x14000e966  test    ax, ax
0x14000e969  jz      loc_14000E9F5
0x14000e96f  movzx   esi, [rbp+DestinationString.Length]
0x14000e973  cmp     ax, si
0x14000e976  jnz     short loc_14000E993
0x14000e978  mov     rdx, [rbp+DestinationString.Buffer]; Buf2
0x14000e97c  mov     r8d, esi; Size
0x14000e97f  mov     rcx, [rdi+248h]; Buf1
0x14000e986  call    memcmp
0x14000e98b  test    eax, eax
0x14000e98d  jz      loc_14000EA8A
0x14000e993  cmp     si, r14w
0x14000e997  jnz     short loc_14000E9B1
0x14000e999  mov     rcx, [rbp+DestinationString.Buffer]; Buf1
0x14000e99d  lea     rdx, Buf2; "*"
0x14000e9a4  movzx   r8d, r14w; Size
0x14000e9a8  call    memcmp
0x14000e9ad  test    eax, eax
0x14000e9af  jz      short loc_14000E9EB
0x14000e9b1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e9b8  lea     rax, WPP_GLOBAL_Control
0x14000e9bf  cmp     rcx, rax
0x14000e9c2  jz      short loc_14000E9EB
0x14000e9c4  mov     eax, [rcx+2Ch]
0x14000e9c7  test    al, 10h
0x14000e9c9  jz      short loc_14000E9EB
0x14000e9cb  cmp     byte ptr [rcx+29h], 1
0x14000e9cf  jb      short loc_14000E9EB
0x14000e9d1  mov     rcx, [rcx+18h]
0x14000e9d5  lea     rax, [rbp+DestinationString]
0x14000e9d9  mov     [rsp+70h+var_48], rdi
0x14000e9de  mov     r9, rbx
0x14000e9e1  mov     [rsp+70h+var_50], rax
0x14000e9e6  call    WPP_SF_ZZq
0x14000e9eb  mov     eax, 0C00000C9h
0x14000e9f0  jmp     loc_14000EA8A
0x14000e9f5  lea     r14, [rdi+50h]
0x14000e9f9  mov     rcx, r14; SpinLock
0x14000e9fc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ea03  nop     dword ptr [rax+rax+00h]
0x14000ea08  cmp     dword ptr [rdi+1E4h], 3
0x14000ea0f  mov     r15b, al
0x14000ea12  jz      short loc_14000EA2C
0x14000ea14  mov     dl, al; NewIrql
0x14000ea16  mov     rcx, r14; SpinLock
0x14000ea19  call    cs:__imp_KeReleaseSpinLock
0x14000ea20  nop     dword ptr [rax+rax+00h]
0x14000ea25  mov     eax, 0C000020Ch
0x14000ea2a  jmp     short loc_14000EA8A
0x14000ea2c  cmp     [rbx], r13w
0x14000ea30  jnz     short loc_14000EA4A
0x14000ea32  lea     rdx, [rbp+DestinationString]; SourceString
0x14000ea36  mov     rcx, rbx; DestinationString
0x14000ea39  call    cs:__imp_RtlCopyUnicodeString
0x14000ea40  nop     dword ptr [rax+rax+00h]
0x14000ea45  mov     byte ptr [r12], 1
0x14000ea4a  mov     dl, r15b; NewIrql
0x14000ea4d  mov     rcx, r14; SpinLock
0x14000ea50  call    cs:__imp_KeReleaseSpinLock
0x14000ea57  nop     dword ptr [rax+rax+00h]
0x14000ea5c  cmp     [r12], r13b
0x14000ea60  jnz     short loc_14000EA88
0x14000ea62  movzx   eax, [rbp+DestinationString.Length]
0x14000ea66  cmp     [rbx], ax
0x14000ea69  jnz     short loc_14000E9EB
0x14000ea6b  mov     rdx, [rbp+DestinationString.Buffer]; Buf2
0x14000ea6f  mov     r8d, eax; Size
0x14000ea72  mov     rcx, [rdi+248h]; Buf1
0x14000ea79  call    memcmp
0x14000ea7e  test    eax, eax
0x14000ea80  mov     ecx, 0C00000C9h
0x14000ea85  cmovnz  esi, ecx
0x14000ea88  mov     eax, esi
0x14000ea8a  mov     rcx, [rbp+var_10]
0x14000ea8e  xor     rcx, rsp; StackCookie
0x14000ea91  call    __security_check_cookie
0x14000ea96  mov     rbx, [rsp+70h+arg_18]
0x14000ea9e  add     rsp, 70h
0x14000eaa2  pop     r15
0x14000eaa4  pop     r14
0x14000eaa6  pop     r13
0x14000eaa8  pop     r12
0x14000eaaa  pop     rdi
0x14000eaab  pop     rsi
0x14000eaac  pop     rbp
0x14000eaad  retn
```
