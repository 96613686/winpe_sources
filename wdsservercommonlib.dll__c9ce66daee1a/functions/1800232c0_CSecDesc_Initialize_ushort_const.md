# CSecDesc::Initialize(ushort const *)

- ea: `0x1800232c0`
- end: `0x180023373`
- name: `?Initialize@CSecDesc@@QEAAKPEBG@Z`
- size: `179`
- prototype: `unsigned int(CSecDesc *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000179c`
- `0x1800232c0`
- `0x1800233e0`
- `0x18002f3ae`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023304`
- `KERNEL32!GetLastError` at `0x180023304`
- `KERNEL32!LocalFree` at `0x180023354`
- `KERNEL32!LocalFree` at `0x180023354`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800232f4`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800232f4`

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
0x1800232c0  mov     rax, rsp
0x1800232c3  mov     [rax+8], rbx
0x1800232c7  mov     [rax+10h], rsi
0x1800232cb  push    rdi
0x1800232cc  sub     rsp, 20h
0x1800232d0  xor     edi, edi
0x1800232d2  mov     rbx, rdx
0x1800232d5  and     [rax+20h], rdi
0x1800232d9  mov     rsi, rcx
0x1800232dc  and     [rax+18h], edi
0x1800232df  call    ?Shutdown@CSecDesc@@QEAAKXZ; CSecDesc::Shutdown(void)
0x1800232e4  lea     r9, [rsp+28h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800232e9  mov     rcx, rbx; StringSecurityDescriptor
0x1800232ec  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x1800232f1  lea     edx, [rdi+1]; StringSDRevision
0x1800232f4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800232fb  nop     dword ptr [rax+rax+00h]
0x180023300  test    eax, eax
0x180023302  jnz     short loc_180023314
0x180023304  call    cs:__imp_GetLastError
0x18002330b  nop     dword ptr [rax+rax+00h]
0x180023310  mov     edi, eax
0x180023312  jmp     short loc_18002334A
0x180023314  mov     ecx, [rsp+28h+SecurityDescriptorSize]; unsigned __int64
0x180023318  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002331f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023324  mov     [rsi], rax
0x180023327  test    rax, rax
0x18002332a  jnz     short loc_180023331
0x18002332c  lea     edi, [rax+8]
0x18002332f  jmp     short loc_18002334A
0x180023331  mov     r8d, [rsp+28h+SecurityDescriptorSize]; Size
0x180023336  mov     rcx, rax; void *
0x180023339  mov     rdx, [rsp+28h+SecurityDescriptor]; Src
0x18002333e  call    memmove_0
0x180023343  mov     eax, [rsp+28h+SecurityDescriptorSize]
0x180023347  mov     [rsi+8], eax
0x18002334a  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x18002334f  test    rcx, rcx
0x180023352  jz      short loc_180023360
0x180023354  call    cs:__imp_LocalFree
0x18002335b  nop     dword ptr [rax+rax+00h]
0x180023360  mov     rbx, [rsp+28h+arg_0]
0x180023365  mov     eax, edi
0x180023367  mov     rsi, [rsp+28h+arg_8]
0x18002336c  add     rsp, 20h
0x180023370  pop     rdi
0x180023371  retn
```
