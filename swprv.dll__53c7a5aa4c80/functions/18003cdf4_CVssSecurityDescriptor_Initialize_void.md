# CVssSecurityDescriptor::Initialize(void)

- ea: `0x18003cdf4`
- end: `0x18003cec7`
- name: `?Initialize@CVssSecurityDescriptor@@QEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CVssSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x180001674`
- `0x180001acc`
- `0x18003cdf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ce90`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003ce86`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003ce86`

## pseudocode

```c
__int64 __fastcall CVssSecurityDescriptor::Initialize(CVssSecurityDescriptor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rax
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v9; // edi

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    operator delete(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)this = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( InitializeSecurityDescriptor(v6, 1u) )
    return 0;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  operator delete(*(void **)this);
  result = v9;
  *(_QWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18003cdf4  mov     [rsp+arg_0], rbx
0x18003cdf9  push    rdi
0x18003cdfa  sub     rsp, 20h
0x18003cdfe  mov     rbx, rcx
0x18003ce01  mov     rcx, [rcx]; Block
0x18003ce04  test    rcx, rcx
0x18003ce07  jz      short loc_18003CE17
0x18003ce09  xor     edx, edx
0x18003ce0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ce10  mov     qword ptr [rbx], 0
0x18003ce17  mov     rcx, [rbx+8]; Block
0x18003ce1b  test    rcx, rcx
0x18003ce1e  jz      short loc_18003CE2D
0x18003ce20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ce25  mov     qword ptr [rbx+8], 0
0x18003ce2d  mov     rcx, [rbx+10h]; Block
0x18003ce31  test    rcx, rcx
0x18003ce34  jz      short loc_18003CE43
0x18003ce36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ce3b  mov     qword ptr [rbx+10h], 0
0x18003ce43  mov     rcx, [rbx+18h]; Block
0x18003ce47  test    rcx, rcx
0x18003ce4a  jz      short loc_18003CE5E
0x18003ce4c  mov     edx, 8
0x18003ce51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ce56  mov     qword ptr [rbx+18h], 0
0x18003ce5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ce65  mov     ecx, 28h ; '('; unsigned __int64
0x18003ce6a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ce6f  mov     [rbx], rax
0x18003ce72  test    rax, rax
0x18003ce75  jnz     short loc_18003CE7E
0x18003ce77  mov     eax, 8007000Eh
0x18003ce7c  jmp     short loc_18003CEBC
0x18003ce7e  mov     edx, 1; dwRevision
0x18003ce83  mov     rcx, rax; pSecurityDescriptor
0x18003ce86  call    cs:__imp_InitializeSecurityDescriptor
0x18003ce8c  test    eax, eax
0x18003ce8e  jnz     short loc_18003CEBA
0x18003ce90  call    cs:__imp_GetLastError
0x18003ce96  mov     edi, eax
0x18003ce98  test    eax, eax
0x18003ce9a  jle     short loc_18003CEA5
0x18003ce9c  movzx   edi, ax
0x18003ce9f  or      edi, 80070000h
0x18003cea5  mov     rcx, [rbx]; Block
0x18003cea8  xor     edx, edx
0x18003ceaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ceaf  mov     eax, edi
0x18003ceb1  mov     qword ptr [rbx], 0
0x18003ceb8  jmp     short loc_18003CEBC
0x18003ceba  xor     eax, eax
0x18003cebc  mov     rbx, [rsp+28h+arg_0]
0x18003cec1  add     rsp, 20h
0x18003cec5  pop     rdi
0x18003cec6  retn
```
