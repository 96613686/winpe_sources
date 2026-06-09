# SplWOWCreateSecurityDescriptor(ulong,NCoreLibrary::TString &,bool,void * *)

- ea: `0x14000f9cc`
- end: `0x14000fa9d`
- name: `?SplWOWCreateSecurityDescriptor@@YAJKAEAVTString@NCoreLibrary@@_NPEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(unsigned int, struct NCoreLibrary::TString *, bool, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000805c`
- `0x14000fae0`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x140005f18`
- `0x14000f9cc`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000fa56`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000fa56`
- `KERNEL32!GetLastError` at `0x14000fa60`
- `KERNEL32!GetLastError` at `0x14000fa60`

## pseudocode

```c
__int64 __fastcall SplWOWCreateSecurityDescriptor(
        unsigned int a1,
        struct NCoreLibrary::TString *a2,
        char a3,
        void **a4)
{
  __int64 v8; // r9
  unsigned int v9; // eax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // ebp
  signed int LastError; // eax
  __int64 result; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-258h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+40h] [rbp-248h] BYREF

  memset_0(StringSecurityDescriptor, 0, 0x208u);
  v8 = *(_QWORD *)a2;
  v9 = 0;
  v10 = L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;CO)(A;;GA;;;%ws)(A;;GA;;;AC)(A;;GA;;;S-1-15-3-1024-4044835139-2658482041-31279731"
         "64-329287231-3865880861-1938685643-461067658-1087000422)S:(ML;;0x7;;;S-1-16-%u)";
  v11 = 0;
  SecurityDescriptor = 0;
  if ( a1 > 0x2000 )
    v9 = a1;
  if ( !a3 )
    v10 = L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;CO)(A;;GA;;;%ws)(A;;GA;;;S-1-15-3-65536-1683377966-140338-1592318436-1629742377"
           "-1825994449-940391111-2274003474-4026619131)S:(ML;;0x7;;;S-1-16-%u)";
  StringCchPrintfW(StringSecurityDescriptor, 0x104u, v10, v8, v9);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
  }
  result = v11;
  *a4 = SecurityDescriptor;
  return result;
}

```

## disassembly

```asm
0x14000f9cc  push    rbx
0x14000f9ce  push    rbp
0x14000f9cf  push    rsi
0x14000f9d0  push    rdi
0x14000f9d1  push    r14
0x14000f9d3  sub     rsp, 260h
0x14000f9da  mov     rax, cs:__security_cookie
0x14000f9e1  xor     rax, rsp
0x14000f9e4  mov     [rsp+288h+var_38], rax
0x14000f9ec  mov     dil, r8b
0x14000f9ef  mov     rsi, rdx
0x14000f9f2  mov     ebx, ecx
0x14000f9f4  xor     edx, edx; Val
0x14000f9f6  mov     r8d, 208h; Size
0x14000f9fc  lea     rcx, [rsp+288h+StringSecurityDescriptor]; void *
0x14000fa01  mov     r14, r9
0x14000fa04  call    memset_0
0x14000fa09  mov     r9, [rsi]
0x14000fa0c  lea     rcx, aDAOiciGaSyAOic_0; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;CO)(A;;G"...
0x14000fa13  xor     eax, eax
0x14000fa15  lea     r8, aDAOiciGaSyAOic; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;CO)(A;;G"...
0x14000fa1c  xor     ebp, ebp
0x14000fa1e  mov     edx, 104h; unsigned __int64
0x14000fa23  cmp     ebx, 2000h
0x14000fa29  mov     [rsp+288h+SecurityDescriptor], rbp
0x14000fa2e  cmova   eax, ebx
0x14000fa31  test    dil, dil
0x14000fa34  mov     [rsp+288h+var_268], eax
0x14000fa38  cmovz   r8, rcx; unsigned __int16 *
0x14000fa3c  lea     rcx, [rsp+288h+StringSecurityDescriptor]; unsigned __int16 *
0x14000fa41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fa46  xor     r9d, r9d; SecurityDescriptorSize
0x14000fa49  lea     r8, [rsp+288h+SecurityDescriptor]; SecurityDescriptor
0x14000fa4e  lea     edx, [rbp+1]; StringSDRevision
0x14000fa51  lea     rcx, [rsp+288h+StringSecurityDescriptor]; StringSecurityDescriptor
0x14000fa56  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14000fa5c  test    eax, eax
0x14000fa5e  jnz     short loc_14000FA75
0x14000fa60  call    cs:__imp_GetLastError
0x14000fa66  mov     ebp, eax
0x14000fa68  test    eax, eax
0x14000fa6a  jle     short loc_14000FA75
0x14000fa6c  movzx   ebp, ax
0x14000fa6f  or      ebp, 80070000h
0x14000fa75  mov     rcx, [rsp+288h+SecurityDescriptor]
0x14000fa7a  mov     eax, ebp
0x14000fa7c  mov     [r14], rcx
0x14000fa7f  mov     rcx, [rsp+288h+var_38]
0x14000fa87  xor     rcx, rsp; StackCookie
0x14000fa8a  call    __security_check_cookie
0x14000fa8f  add     rsp, 260h
0x14000fa96  pop     r14
0x14000fa98  pop     rdi
0x14000fa99  pop     rsi
0x14000fa9a  pop     rbp
0x14000fa9b  pop     rbx
0x14000fa9c  retn
```
