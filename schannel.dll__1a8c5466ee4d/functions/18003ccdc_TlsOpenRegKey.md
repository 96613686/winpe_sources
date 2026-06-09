# TlsOpenRegKey

- ea: `0x18003ccdc`
- end: `0x18003ce1e`
- name: `TlsOpenRegKey`
- size: `322`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003cbf8`
- `0x180087038`
- `0x1800873b0`
- `0x1800876f8`
- `0x180087a30`

## callees

- `0x18003ccdc`
- `0x180087df0`
- `0x180087e10`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18003cdbe`
- `ntdll!RtlAppendUnicodeToString` at `0x18003cdce`
- `ntdll!RtlAppendUnicodeToString` at `0x18003cdda`
- `ntdll!RtlAppendUnicodeToString` at `0x18003cdbe`
- `ntdll!RtlAppendUnicodeToString` at `0x18003cdce`
- `ntdll!RtlAppendUnicodeToString` at `0x18003cdda`
- `ntdll!NtOpenKey` at `0x18003cd55`
- `ntdll!NtOpenKey` at `0x18003cd55`
- `ntdll!RtlInitUnicodeString` at `0x18003cd1a`
- `ntdll!RtlInitUnicodeString` at `0x18003cd1a`

## pseudocode

```c
__int64 __fastcall TlsOpenRegKey(PCWSTR Source, PCWSTR a2, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  USHORT v10; // r14
  struct _UNICODE_STRING *v11; // rax
  struct _UNICODE_STRING v13; // [rsp+28h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-70h] BYREF

  v13 = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a2 )
  {
    RtlInitUnicodeString(&v13, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v13;
LABEL_3:
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
    goto LABEL_10;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  do
    ++v8;
  while ( Source[v8] );
  v10 = 2 * (v9 + v8) + 4;
  v11 = (struct _UNICODE_STRING *)SafeAllocaAllocateFromHeap((unsigned int)(2 * (v9 + v8) + 4) + 16LL);
  v6 = v11;
  if ( v11 )
  {
    v11->Length = 0;
    v11->MaximumLength = v10;
    v11->Buffer = &v11[1].Length;
    RtlAppendUnicodeToString(v11, Source);
    RtlAppendUnicodeToString(v6, L"\\");
    RtlAppendUnicodeToString(v6, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v6;
    goto LABEL_3;
  }
  v7 = -1073741801;
LABEL_10:
  if ( v6 )
    SchannelFree(v6);
  return v7;
}

```

## disassembly

```asm
0x18003ccdc  mov     rax, rsp
0x18003ccdf  push    rbx
0x18003cce0  push    rsi
0x18003cce1  push    rdi
0x18003cce2  push    r12
0x18003cce4  push    r14
0x18003cce6  push    r15
0x18003cce8  sub     rsp, 78h
0x18003ccec  mov     r15, r8
0x18003ccef  mov     rdi, rdx
0x18003ccf2  mov     rsi, rcx
0x18003ccf5  xorps   xmm0, xmm0
0x18003ccf8  movups  xmmword ptr [rax-80h], xmm0
0x18003ccfc  xor     r12d, r12d
0x18003ccff  mov     ebx, r12d
0x18003cd02  movups  xmmword ptr [rax-70h], xmm0
0x18003cd06  movups  xmmword ptr [rax-60h], xmm0
0x18003cd0a  movups  xmmword ptr [rax-50h], xmm0
0x18003cd0e  test    rdx, rdx
0x18003cd11  jnz     short loc_18003CD62
0x18003cd13  mov     rdx, rcx; SourceString
0x18003cd16  lea     rcx, [rax-80h]; DestinationString
0x18003cd1a  call    cs:__imp_RtlInitUnicodeString
0x18003cd20  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18003cd28  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x18003cd2d  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x18003cd35  lea     rax, [rsp+0A8h+var_80]
0x18003cd3a  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x18003cd3f  xorps   xmm0, xmm0
0x18003cd42  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003cd48  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x18003cd4d  mov     edx, 20019h; DesiredAccess
0x18003cd52  mov     rcx, r15; KeyHandle
0x18003cd55  call    cs:__imp_NtOpenKey
0x18003cd5b  mov     edi, eax
0x18003cd5d  jmp     loc_18003CDFF
0x18003cd62  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003cd66  mov     rcx, rax
0x18003cd69  inc     rcx
0x18003cd6c  cmp     [rdx+rcx*2], r12w
0x18003cd71  jnz     short loc_18003CD69
0x18003cd73  inc     rax
0x18003cd76  cmp     [rsi+rax*2], r12w
0x18003cd7b  jnz     short loc_18003CD73
0x18003cd7d  add     eax, ecx
0x18003cd7f  lea     r14d, ds:4[rax*2]
0x18003cd87  mov     ecx, r14d
0x18003cd8a  add     rcx, 10h
0x18003cd8e  call    SafeAllocaAllocateFromHeap
0x18003cd93  mov     rbx, rax
0x18003cd96  mov     [rsp+0A8h+var_88], rax
0x18003cd9b  test    rax, rax
0x18003cd9e  jnz     short loc_18003CDA7
0x18003cda0  mov     edi, 0C0000017h
0x18003cda5  jmp     short loc_18003CDFF
0x18003cda7  mov     [rax], r12w
0x18003cdab  mov     [rax+2], r14w
0x18003cdb0  add     rax, 10h
0x18003cdb4  mov     [rbx+8], rax
0x18003cdb8  mov     rdx, rsi; Source
0x18003cdbb  mov     rcx, rbx; Destination
0x18003cdbe  call    cs:__imp_RtlAppendUnicodeToString
0x18003cdc4  lea     rdx, Source; "\\"
0x18003cdcb  mov     rcx, rbx; Destination
0x18003cdce  call    cs:__imp_RtlAppendUnicodeToString
0x18003cdd4  mov     rdx, rdi; Source
0x18003cdd7  mov     rcx, rbx; Destination
0x18003cdda  call    cs:__imp_RtlAppendUnicodeToString
0x18003cde0  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18003cde8  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x18003cded  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x18003cdf5  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x18003cdfa  jmp     loc_18003CD3F
0x18003cdff  test    rbx, rbx
0x18003ce02  jnz     short loc_18003CE14
0x18003ce04  mov     eax, edi
0x18003ce06  add     rsp, 78h
0x18003ce0a  pop     r15
0x18003ce0c  pop     r14
0x18003ce0e  pop     r12
0x18003ce10  pop     rdi
0x18003ce11  pop     rsi
0x18003ce12  pop     rbx
0x18003ce13  retn
0x18003ce14  mov     rcx, rbx
0x18003ce17  call    SchannelFree
0x18003ce1c  jmp     short loc_18003CE04
0x180088b2c  push    rbp
0x180088b2e  sub     rsp, 20h
0x180088b32  mov     rbp, rdx
0x180088b35  add     rsp, 20h
0x180088b39  pop     rbp
0x180088b3a  retn
```
