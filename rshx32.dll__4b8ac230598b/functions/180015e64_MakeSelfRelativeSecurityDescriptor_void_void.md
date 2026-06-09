# MakeSelfRelativeSecurityDescriptor(void *,void * *)

- ea: `0x180015e64`
- end: `0x180015f86`
- name: `?MakeSelfRelativeSecurityDescriptor@@YAJPEAXPEAPEAX@Z`
- size: `290`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005b00`
- `0x18000ac00`

## callees

- `0x180015e64`
- `0x18001d322`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015f6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015f6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f35`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180015eaa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180015eaa`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180015f20`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180015f4e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180015f20`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180015f4e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015ee1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015ee1`

## pseudocode

```c
__int64 __fastcall MakeSelfRelativeSecurityDescriptor(void *Src, void **a2)
{
  void *v4; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  HLOCAL v7; // rax
  HLOCAL v8; // rax
  WORD pControl; // [rsp+40h] [rbp+8h] BYREF
  size_t Size; // [rsp+50h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+58h] [rbp+20h] BYREF

  dwRevision = 0;
  LODWORD(Size) = 0;
  pControl = 0;
  if ( !Src || !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 0;
  if ( !GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
    goto LABEL_4;
  if ( (pControl & 0x8000u) == 0 )
  {
    MakeSelfRelativeSD(Src, 0, (LPDWORD)&Size);
    if ( !(_DWORD)Size )
      goto LABEL_4;
    v8 = LocalAlloc(0x40u, (unsigned int)Size);
    v4 = v8;
    if ( !v8 )
      goto LABEL_8;
    if ( !MakeSelfRelativeSD(Src, v8, (LPDWORD)&Size) )
    {
LABEL_4:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_14;
    }
LABEL_13:
    v6 = 0;
    *a2 = v4;
    goto LABEL_14;
  }
  LODWORD(Size) = GetSecurityDescriptorLength(Src);
  v7 = LocalAlloc(0x40u, (unsigned int)Size);
  v4 = v7;
  if ( v7 )
  {
    memcpy_0(v7, Src, (unsigned int)Size);
    goto LABEL_13;
  }
LABEL_8:
  v6 = -2147024882;
LABEL_14:
  if ( !*a2 )
  {
    if ( v4 )
      LocalFree(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x180015e64  push    rbx
0x180015e66  push    rsi
0x180015e67  push    rdi
0x180015e68  sub     rsp, 20h
0x180015e6c  xor     eax, eax
0x180015e6e  mov     [rsp+38h+dwRevision], 0
0x180015e76  mov     dword ptr [rsp+38h+Size], 0
0x180015e7e  mov     rsi, rdx
0x180015e81  mov     [rsp+38h+pControl], ax
0x180015e86  mov     rbx, rcx
0x180015e89  test    rcx, rcx
0x180015e8c  jz      loc_180015F79
0x180015e92  test    rdx, rdx
0x180015e95  jz      loc_180015F79
0x180015e9b  mov     [rdx], rax
0x180015e9e  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x180015ea3  lea     rdx, [rsp+38h+pControl]; pControl
0x180015ea8  xor     edi, edi
0x180015eaa  call    cs:__imp_GetSecurityDescriptorControl
0x180015eb0  test    eax, eax
0x180015eb2  jnz     short loc_180015ED2
0x180015eb4  call    cs:__imp_GetLastError
0x180015eba  mov     ebx, eax
0x180015ebc  test    eax, eax
0x180015ebe  jle     loc_180015F61
0x180015ec4  movzx   ebx, ax
0x180015ec7  or      ebx, 80070000h
0x180015ecd  jmp     loc_180015F61
0x180015ed2  mov     eax, 8000h
0x180015ed7  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180015eda  test    [rsp+38h+pControl], ax
0x180015edf  jz      short loc_180015F19
0x180015ee1  call    cs:__imp_GetSecurityDescriptorLength
0x180015ee7  mov     edx, eax; uBytes
0x180015ee9  mov     ecx, 40h ; '@'; uFlags
0x180015eee  mov     dword ptr [rsp+38h+Size], edx
0x180015ef2  call    cs:__imp_LocalAlloc
0x180015ef8  mov     rdi, rax
0x180015efb  test    rax, rax
0x180015efe  jnz     short loc_180015F07
0x180015f00  mov     ebx, 8007000Eh
0x180015f05  jmp     short loc_180015F61
0x180015f07  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180015f0c  mov     rdx, rbx; Src
0x180015f0f  mov     rcx, rax; void *
0x180015f12  call    memcpy_0
0x180015f17  jmp     short loc_180015F5C
0x180015f19  lea     r8, [rsp+38h+Size]; lpdwBufferLength
0x180015f1e  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180015f20  call    cs:__imp_MakeSelfRelativeSD
0x180015f26  mov     eax, dword ptr [rsp+38h+Size]
0x180015f2a  test    eax, eax
0x180015f2c  jz      short loc_180015EB4
0x180015f2e  mov     edx, eax; uBytes
0x180015f30  mov     ecx, 40h ; '@'; uFlags
0x180015f35  call    cs:__imp_LocalAlloc
0x180015f3b  mov     rdi, rax
0x180015f3e  test    rax, rax
0x180015f41  jz      short loc_180015F00
0x180015f43  lea     r8, [rsp+38h+Size]; lpdwBufferLength
0x180015f48  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180015f4b  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180015f4e  call    cs:__imp_MakeSelfRelativeSD
0x180015f54  test    eax, eax
0x180015f56  jz      loc_180015EB4
0x180015f5c  xor     ebx, ebx
0x180015f5e  mov     [rsi], rdi
0x180015f61  cmp     qword ptr [rsi], 0
0x180015f65  jnz     short loc_180015F75
0x180015f67  test    rdi, rdi
0x180015f6a  jz      short loc_180015F75
0x180015f6c  mov     rcx, rdi; hMem
0x180015f6f  call    cs:__imp_LocalFree
0x180015f75  mov     eax, ebx
0x180015f77  jmp     short loc_180015F7E
0x180015f79  mov     eax, 80004003h
0x180015f7e  add     rsp, 20h
0x180015f82  pop     rdi
0x180015f83  pop     rsi
0x180015f84  pop     rbx
0x180015f85  retn
```
