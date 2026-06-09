# SrvAdminSetSessionName

- ea: `0x14004c430`
- end: `0x14004c4cd`
- name: `SrvAdminSetSessionName`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140005470`
- `0x1400054f0`
- `0x140009960`
- `0x14000bfa0`
- `0x14004c430`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c494`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004c494`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004c47b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004c47b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c4a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c4a3`

## pseudocode

```c
__int64 __fastcall SrvAdminSetSessionName(__int64 a1, __int64 a2, const UNICODE_STRING *a3, unsigned int a4)
{
  __int64 v5; // rax
  __int64 v6; // rbx
  struct _UNICODE_STRING *v8; // rdi

  v5 = SrvAdminInstanceGetFromType(a4);
  v6 = v5;
  if ( !v5 )
    return 3221225987LL;
  v8 = (struct _UNICODE_STRING *)RfsTable64Lookup(*(PEX_SPIN_LOCK *)(v5 + 64));
  if ( v8 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 304), 1u);
    if ( !v8[7].Length )
      RtlCopyUnicodeString(v8 + 7, a3);
    ExReleaseResourceLite((PERESOURCE)(v6 + 304));
    SrvAdminDereferenceSession(v8);
  }
  SrvAdminDereferenceInstance(v6);
  return 0;
}

```

## disassembly

```asm
0x14004c430  push    rbx
0x14004c432  push    rbp
0x14004c433  push    rsi
0x14004c434  push    rdi
0x14004c435  push    r14
0x14004c437  sub     rsp, 20h
0x14004c43b  mov     ecx, r9d
0x14004c43e  mov     rbp, r8
0x14004c441  mov     rdi, rdx
0x14004c444  call    SrvAdminInstanceGetFromType
0x14004c449  xor     r14d, r14d
0x14004c44c  mov     rbx, rax
0x14004c44f  test    rax, rax
0x14004c452  jnz     short loc_14004C45B
0x14004c454  mov     eax, 0C0000203h
0x14004c459  jmp     short loc_14004C4C1
0x14004c45b  mov     rcx, [rax+40h]; SpinLock
0x14004c45f  mov     rdx, rdi
0x14004c462  call    RfsTable64Lookup
0x14004c467  mov     rdi, rax
0x14004c46a  test    rax, rax
0x14004c46d  jz      short loc_14004C4B7
0x14004c46f  lea     rsi, [rbx+130h]
0x14004c476  mov     dl, 1; Wait
0x14004c478  mov     rcx, rsi; Resource
0x14004c47b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004c482  nop     dword ptr [rax+rax+00h]
0x14004c487  lea     rcx, [rdi+70h]; DestinationString
0x14004c48b  cmp     [rcx], r14w
0x14004c48f  jnz     short loc_14004C4A0
0x14004c491  mov     rdx, rbp; SourceString
0x14004c494  call    cs:__imp_RtlCopyUnicodeString
0x14004c49b  nop     dword ptr [rax+rax+00h]
0x14004c4a0  mov     rcx, rsi; Resource
0x14004c4a3  call    cs:__imp_ExReleaseResourceLite
0x14004c4aa  nop     dword ptr [rax+rax+00h]
0x14004c4af  mov     rcx, rdi
0x14004c4b2  call    SrvAdminDereferenceSession
0x14004c4b7  mov     rcx, rbx
0x14004c4ba  call    SrvAdminDereferenceInstance
0x14004c4bf  xor     eax, eax
0x14004c4c1  add     rsp, 20h
0x14004c4c5  pop     r14
0x14004c4c7  pop     rdi
0x14004c4c8  pop     rsi
0x14004c4c9  pop     rbp
0x14004c4ca  pop     rbx
0x14004c4cb  retn
```
