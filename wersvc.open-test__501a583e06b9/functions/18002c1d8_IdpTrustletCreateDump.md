# IdpTrustletCreateDump

- ea: `0x18002c1d8`
- end: `0x18002c35f`
- name: `IdpTrustletCreateDump`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002c3fc`

## callees

- `0x1800029d0`
- `0x18002c1d8`
- `0x18002c908`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002c260`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002c260`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c30b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c336`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c23a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002c23a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IdpTrustletCreateDump(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  unsigned int v4; // edi
  unsigned int i; // ebx
  HANDLE v10; // rax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  __int64 v15; // [rsp+38h] [rbp-C8h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  __int64 v17; // [rsp+48h] [rbp-B8h]
  __int64 v18; // [rsp+50h] [rbp-B0h]
  __int64 v19; // [rsp+58h] [rbp-A8h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SystemTime = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    GetLocalTime(&SystemTime);
    for ( i = 0; i < 4; ++i )
    {
      LODWORD(v19) = i;
      LODWORD(v18) = a3;
      LODWORD(v17) = SystemTime.wSecond;
      LODWORD(v16) = SystemTime.wMinute;
      LODWORD(v15) = SystemTime.wHour;
      LODWORD(hTemplateFile) = SystemTime.wYear % 0x64u;
      LODWORD(dwFlagsAndAttributes) = SystemTime.wDay;
      LODWORD(dwCreationDisposition) = SystemTime.wMonth;
      if ( StringCbPrintfW(
             pszDest,
             0x105u,
             L"IUM-%s-%2.2d%2.2d%2.2d-%2.2d%2.2d%2.2d-%u-%2.2d.%ws",
             a1,
             dwCreationDisposition,
             dwFlagsAndAttributes,
             hTemplateFile,
             v15,
             v16,
             v17,
             v18,
             v19,
             a2) < 0 )
        break;
      pszDest[260] = 0;
      v10 = CreateFileW(pszDest, 0x40040000u, 1u, &SecurityAttributes, 1u, 0x80u, 0);
      if ( v10 != (HANDLE)-1LL )
      {
        *a4 = v10;
        v4 = 1;
        break;
      }
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x18002c1d8  push    rbp
0x18002c1da  push    rbx
0x18002c1db  push    rsi
0x18002c1dc  push    rdi
0x18002c1dd  push    r12
0x18002c1df  push    r14
0x18002c1e1  push    r15
0x18002c1e3  lea     rbp, [rsp-1C0h]
0x18002c1eb  sub     rsp, 2C0h
0x18002c1f2  mov     rax, cs:__security_cookie
0x18002c1f9  xor     rax, rsp
0x18002c1fc  mov     [rbp+1F0h+var_40], rax
0x18002c203  xorps   xmm0, xmm0
0x18002c206  xor     edi, edi
0x18002c208  mov     rsi, r9
0x18002c20b  mov     [rsp+2F0h+SecurityDescriptor], rdi
0x18002c210  mov     r12d, r8d
0x18002c213  mov     r15, rdx
0x18002c216  mov     r14, rcx
0x18002c219  lea     r8, [rsp+2F0h+SecurityDescriptor]; SecurityDescriptor
0x18002c21e  xor     eax, eax
0x18002c220  lea     edx, [rdi+1]; StringSDRevision
0x18002c223  xor     r9d, r9d; SecurityDescriptorSize
0x18002c226  mov     qword ptr [rbp+1F0h+SecurityAttributes.bInheritHandle], rax
0x18002c22a  lea     rcx, aDPAOiciGaBaAOi; "D:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)"
0x18002c231  movups  xmmword ptr [rsp+2F0h+SecurityAttributes.nLength], xmm0
0x18002c236  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18002c23a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002c240  test    eax, eax
0x18002c242  jz      loc_18002C32C
0x18002c248  mov     rax, [rsp+2F0h+SecurityDescriptor]
0x18002c24d  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18002c251  mov     [rbp+1F0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002c255  mov     [rsp+2F0h+SecurityAttributes.nLength], 18h
0x18002c25d  mov     [rbp+1F0h+SecurityAttributes.bInheritHandle], edi
0x18002c260  call    cs:__imp_GetLocalTime
0x18002c266  xor     ebx, ebx
0x18002c268  movzx   r11d, [rbp+1F0h+SystemTime.wYear]
0x18002c26d  mov     eax, 51EB851Fh
0x18002c272  movzx   r8d, [rbp+1F0h+SystemTime.wSecond]
0x18002c277  movzx   r9d, [rbp+1F0h+SystemTime.wMinute]
0x18002c27c  movzx   ecx, [rbp+1F0h+SystemTime.wMonth]
0x18002c280  movzx   r10d, [rbp+1F0h+SystemTime.wHour]
0x18002c285  mov     [rsp+2F0h+var_290], r15
0x18002c28a  mov     dword ptr [rsp+2F0h+var_298], ebx
0x18002c28e  mul     r11d
0x18002c291  mov     dword ptr [rsp+2F0h+var_2A0], r12d
0x18002c296  mov     dword ptr [rsp+2F0h+var_2A8], r8d
0x18002c29b  lea     r8, aIumS22d22d22d2; "IUM-%s-%2.2d%2.2d%2.2d-%2.2d%2.2d%2.2d-"...
0x18002c2a2  mov     dword ptr [rsp+2F0h+var_2B0], r9d
0x18002c2a7  mov     r9, r14
0x18002c2aa  mov     dword ptr [rsp+2F0h+var_2B8], r10d
0x18002c2af  shr     edx, 5
0x18002c2b2  imul    eax, edx, 64h ; 'd'
0x18002c2b5  mov     edx, 105h; cbDest
0x18002c2ba  sub     r11d, eax
0x18002c2bd  movzx   eax, [rbp+1F0h+SystemTime.wDay]
0x18002c2c1  mov     dword ptr [rsp+2F0h+hTemplateFile], r11d
0x18002c2c6  mov     dword ptr [rsp+2F0h+dwFlagsAndAttributes], eax
0x18002c2ca  mov     dword ptr [rsp+2F0h+dwCreationDisposition], ecx
0x18002c2ce  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x18002c2d2  call    StringCbPrintfW
0x18002c2d7  test    eax, eax
0x18002c2d9  js      short loc_18002C32C
0x18002c2db  xor     eax, eax
0x18002c2dd  lea     r9, [rsp+2F0h+SecurityAttributes]; lpSecurityAttributes
0x18002c2e2  mov     [rsp+2F0h+hTemplateFile], rax; hTemplateFile
0x18002c2e7  lea     rcx, [rbp+1F0h+pszDest]; lpFileName
0x18002c2eb  mov     [rbp+1F0h+var_48], ax
0x18002c2f2  mov     edx, 40040000h; dwDesiredAccess
0x18002c2f7  mov     eax, 1
0x18002c2fc  mov     dword ptr [rsp+2F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002c304  mov     r8d, eax; dwShareMode
0x18002c307  mov     dword ptr [rsp+2F0h+dwCreationDisposition], eax; dwCreationDisposition
0x18002c30b  call    cs:__imp_CreateFileW
0x18002c311  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c315  jnz     short loc_18002C324
0x18002c317  inc     ebx
0x18002c319  cmp     ebx, 4
0x18002c31c  jb      loc_18002C268
0x18002c322  jmp     short loc_18002C32C
0x18002c324  mov     [rsi], rax
0x18002c327  mov     edi, 1
0x18002c32c  mov     rcx, [rsp+2F0h+SecurityDescriptor]; hMem
0x18002c331  test    rcx, rcx
0x18002c334  jz      short loc_18002C33C
0x18002c336  call    cs:__imp_LocalFree
0x18002c33c  mov     eax, edi
0x18002c33e  mov     rcx, [rbp+1F0h+var_40]
0x18002c345  xor     rcx, rsp; StackCookie
0x18002c348  call    __security_check_cookie
0x18002c34d  add     rsp, 2C0h
0x18002c354  pop     r15
0x18002c356  pop     r14
0x18002c358  pop     r12
0x18002c35a  pop     rdi
0x18002c35b  pop     rsi
0x18002c35c  pop     rbx
0x18002c35d  pop     rbp
0x18002c35e  retn
```
