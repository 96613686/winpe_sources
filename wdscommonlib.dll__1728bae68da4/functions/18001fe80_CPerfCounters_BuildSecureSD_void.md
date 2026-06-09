# CPerfCounters::BuildSecureSD(void * *)

- ea: `0x18001fe80`
- end: `0x18001febf`
- name: `?BuildSecureSD@CPerfCounters@@IEAAKPEAPEAX@Z`
- size: `63`
- prototype: `unsigned int(CPerfCounters *__hidden this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800204b0`

## callees

- `0x18001fe80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001fea8`
- `KERNEL32!GetLastError` at `0x18001fea8`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001fe98`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001fe98`

## pseudocode

```c
__int64 __fastcall CPerfCounters::BuildSecureSD(CPerfCounters *this, void **a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;LU)(A;;GR;;;MU)",
          1u,
          a2,
          0) )
    return GetLastError();
  return v2;
}

```

## disassembly

```asm
0x18001fe80  push    rbx
0x18001fe82  sub     rsp, 20h
0x18001fe86  mov     r8, rdx; SecurityDescriptor
0x18001fe89  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;LU)("...
0x18001fe90  xor     ebx, ebx
0x18001fe92  xor     r9d, r9d; SecurityDescriptorSize
0x18001fe95  lea     edx, [rbx+1]; StringSDRevision
0x18001fe98  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001fe9f  nop     dword ptr [rax+rax+00h]
0x18001fea4  test    eax, eax
0x18001fea6  jnz     short loc_18001FEB6
0x18001fea8  call    cs:__imp_GetLastError
0x18001feaf  nop     dword ptr [rax+rax+00h]
0x18001feb4  mov     ebx, eax
0x18001feb6  mov     eax, ebx
0x18001feb8  add     rsp, 20h
0x18001febc  pop     rbx
0x18001febd  retn
```
