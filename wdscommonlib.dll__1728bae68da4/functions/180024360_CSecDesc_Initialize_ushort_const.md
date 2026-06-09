# CSecDesc::Initialize(ushort const *)

- ea: `0x180024360`
- end: `0x180024413`
- name: `?Initialize@CSecDesc@@QEAAKPEBG@Z`
- size: `179`
- prototype: `unsigned int(CSecDesc *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000214c`
- `0x1800024b2`
- `0x180024360`
- `0x180024480`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800243a4`
- `KERNEL32!GetLastError` at `0x1800243a4`
- `KERNEL32!LocalFree` at `0x1800243f4`
- `KERNEL32!LocalFree` at `0x1800243f4`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180024394`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180024394`

## pseudocode

```c
__int64 __fastcall CSecDesc::Initialize(CSecDesc *this, const unsigned __int16 *a2)
{
  DWORD LastError; // edi
  void *v5; // rax
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp+20h] BYREF

  LastError = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  CSecDesc::Shutdown(this);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, &SecurityDescriptor, &SecurityDescriptorSize) )
  {
    v5 = operator new[](SecurityDescriptorSize, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)this = v5;
    if ( v5 )
    {
      memmove_0(v5, SecurityDescriptor, SecurityDescriptorSize);
      *((_DWORD *)this + 2) = SecurityDescriptorSize;
    }
    else
    {
      LastError = 8;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x180024360  mov     rax, rsp
0x180024363  mov     [rax+8], rbx
0x180024367  mov     [rax+10h], rsi
0x18002436b  push    rdi
0x18002436c  sub     rsp, 20h
0x180024370  xor     edi, edi
0x180024372  mov     rbx, rdx
0x180024375  and     [rax+20h], rdi
0x180024379  mov     rsi, rcx
0x18002437c  and     [rax+18h], edi
0x18002437f  call    ?Shutdown@CSecDesc@@QEAAKXZ; CSecDesc::Shutdown(void)
0x180024384  lea     r9, [rsp+28h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180024389  mov     rcx, rbx; StringSecurityDescriptor
0x18002438c  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180024391  lea     edx, [rdi+1]; StringSDRevision
0x180024394  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002439b  nop     dword ptr [rax+rax+00h]
0x1800243a0  test    eax, eax
0x1800243a2  jnz     short loc_1800243B4
0x1800243a4  call    cs:__imp_GetLastError
0x1800243ab  nop     dword ptr [rax+rax+00h]
0x1800243b0  mov     edi, eax
0x1800243b2  jmp     short loc_1800243EA
0x1800243b4  mov     ecx, [rsp+28h+SecurityDescriptorSize]; unsigned __int64
0x1800243b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800243bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800243c4  mov     [rsi], rax
0x1800243c7  test    rax, rax
0x1800243ca  jnz     short loc_1800243D1
0x1800243cc  lea     edi, [rax+8]
0x1800243cf  jmp     short loc_1800243EA
0x1800243d1  mov     r8d, [rsp+28h+SecurityDescriptorSize]; Size
0x1800243d6  mov     rcx, rax; void *
0x1800243d9  mov     rdx, [rsp+28h+SecurityDescriptor]; Src
0x1800243de  call    memmove_0
0x1800243e3  mov     eax, [rsp+28h+SecurityDescriptorSize]
0x1800243e7  mov     [rsi+8], eax
0x1800243ea  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x1800243ef  test    rcx, rcx
0x1800243f2  jz      short loc_180024400
0x1800243f4  call    cs:__imp_LocalFree
0x1800243fb  nop     dword ptr [rax+rax+00h]
0x180024400  mov     rbx, [rsp+28h+arg_0]
0x180024405  mov     eax, edi
0x180024407  mov     rsi, [rsp+28h+arg_8]
0x18002440c  add     rsp, 20h
0x180024410  pop     rdi
0x180024411  retn
```
