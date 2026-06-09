# CSecDescriptor::Initialize(void)

- ea: `0x18000b060`
- end: `0x18000b0ef`
- name: `?Initialize@CSecDescriptor@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(CSecDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000af5c`
- `0x180010638`

## callees

- `0x18000b060`
- `0x18000d038`
- `0x18000dae8`
- `0x18000db28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000b0cc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18000b0cc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b0a8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b0a8`

## pseudocode

```c
void __fastcall CSecDescriptor::Initialize(CSecDescriptor *this)
{
  void *v2; // rdi
  void *v3; // rcx
  DWORD LastError; // eax
  DWORD v5; // eax

  *(_DWORD *)this = 1;
  v2 = operator new(0x28u);
  if ( !v2 )
    TrkRaiseWin32Error(8);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    operator delete(v3);
  *((_QWORD *)this + 1) = v2;
  if ( !InitializeSecurityDescriptor(v2, 1u) )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  if ( !SetSecurityDescriptorControl(*((PSECURITY_DESCRIPTOR *)this + 1), 0x400u, 0x400u) )
  {
    v5 = GetLastError();
    TrkRaiseWin32Error(v5);
  }
}

```

## disassembly

```asm
0x18000b060  mov     [rsp+arg_0], rbx
0x18000b065  push    rdi
0x18000b066  sub     rsp, 20h
0x18000b06a  mov     rbx, rcx
0x18000b06d  mov     dword ptr [rcx], 1
0x18000b073  mov     ecx, 28h ; '('; Size
0x18000b078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b07d  mov     rdi, rax
0x18000b080  test    rax, rax
0x18000b083  jnz     short loc_18000B08E
0x18000b085  lea     ecx, [rax+8]; int
0x18000b088  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000b08e  mov     rcx, [rbx+8]; Block
0x18000b092  test    rcx, rcx
0x18000b095  jz      short loc_18000B09C
0x18000b097  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b09c  mov     edx, 1; dwRevision
0x18000b0a1  mov     [rbx+8], rdi
0x18000b0a5  mov     rcx, rdi; pSecurityDescriptor
0x18000b0a8  call    cs:__imp_InitializeSecurityDescriptor
0x18000b0ae  test    eax, eax
0x18000b0b0  jnz     short loc_18000B0C0
0x18000b0b2  call    cs:__imp_GetLastError
0x18000b0b8  mov     ecx, eax; int
0x18000b0ba  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000b0c0  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18000b0c4  mov     edx, 400h; ControlBitsOfInterest
0x18000b0c9  mov     r8d, edx; ControlBitsToSet
0x18000b0cc  call    cs:__imp_SetSecurityDescriptorControl
0x18000b0d2  test    eax, eax
0x18000b0d4  jnz     short loc_18000B0E4
0x18000b0d6  call    cs:__imp_GetLastError
0x18000b0dc  mov     ecx, eax; int
0x18000b0de  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000b0e4  mov     rbx, [rsp+28h+arg_0]
0x18000b0e9  add     rsp, 20h
0x18000b0ed  pop     rdi
0x18000b0ee  retn
```
