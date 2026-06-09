# CUmRdpPrn::DeleteSymLink(ushort const *)

- ea: `0x180014d04`
- end: `0x180014e45`
- name: `?DeleteSymLink@CUmRdpPrn@@AEAAHPEBG@Z`
- size: `321`
- prototype: `int(CUmRdpPrn *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006480`

## callees

- `0x1800090b0`
- `0x180009fa8`
- `0x1800134cc`
- `0x180014d04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e12`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d7c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014e18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014d7c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014e18`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014d3e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014d3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014e30`
- `ntdll!RtlNtStatusToDosError` at `0x180014e0a`
- `ntdll!RtlNtStatusToDosError` at `0x180014e0a`
- `ntdll!NtMakeTemporaryObject` at `0x180014df1`
- `ntdll!NtMakeTemporaryObject` at `0x180014df1`
- `ntdll!NtClose` at `0x180014dfb`
- `ntdll!NtClose` at `0x180014dfb`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180014de3`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180014de3`
- `ntdll!RtlInitUnicodeString` at `0x180014dae`
- `ntdll!RtlInitUnicodeString` at `0x180014dae`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::DeleteSymLink(CUmRdpPrn *this, const unsigned __int16 *a2)
{
  void *v2; // rcx
  unsigned int v3; // edi
  __int64 v5; // rax
  unsigned int v6; // r14d
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  int v9; // eax
  DWORD v10; // eax
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *SymbolicLinkHandle; // [rsp+A0h] [rbp+38h] BYREF

  v2 = (void *)*((_QWORD *)this + 23);
  v3 = 0;
  SymbolicLinkHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( ImpersonateLoggedOnUser(v2) )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 13;
    v7 = (unsigned __int16 *)ALLOCMEM((unsigned int)(2 * (v5 + 13)));
    v8 = v7;
    if ( v7 )
    {
      StringCchCopyW(v7, v6, L"\\??\\");
      StringCchCatW(v8, v6, a2);
      RtlInitUnicodeString(&DestinationString, v8);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x10000u, &ObjectAttributes);
      if ( v9 < 0 )
      {
        v10 = RtlNtStatusToDosError(v9);
        SetLastError(v10);
      }
      else
      {
        NtMakeTemporaryObject(SymbolicLinkHandle);
        NtClose(SymbolicLinkHandle);
        v3 = 1;
      }
      RevertToSelf();
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    else
    {
      GetLastError();
      RevertToSelf();
    }
  }
  else
  {
    GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x180014d04  push    rbp
0x180014d06  push    rbx
0x180014d07  push    rsi
0x180014d08  push    rdi
0x180014d09  push    r14
0x180014d0b  push    r15
0x180014d0d  mov     rbp, rsp
0x180014d10  sub     rsp, 68h
0x180014d14  mov     rcx, [rcx+0B8h]; hToken
0x180014d1b  xorps   xmm1, xmm1
0x180014d1e  xor     r15d, r15d
0x180014d21  xorps   xmm0, xmm0
0x180014d24  mov     edi, r15d
0x180014d27  mov     [rbp+SymbolicLinkHandle], r15
0x180014d2b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180014d2f  mov     rsi, rdx
0x180014d32  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180014d36  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180014d3a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180014d3e  call    cs:__imp_ImpersonateLoggedOnUser
0x180014d44  test    eax, eax
0x180014d46  jnz     short loc_180014D53
0x180014d48  call    cs:__imp_GetLastError
0x180014d4e  jmp     loc_180014E36
0x180014d53  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014d57  inc     rax
0x180014d5a  cmp     [rsi+rax*2], r15w
0x180014d5f  jnz     short loc_180014D57
0x180014d61  lea     r14d, [rax+0Dh]
0x180014d65  lea     ecx, [r14+r14]; dwBytes
0x180014d69  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180014d6e  mov     rbx, rax
0x180014d71  test    rax, rax
0x180014d74  jnz     short loc_180014D87
0x180014d76  call    cs:__imp_GetLastError
0x180014d7c  call    cs:__imp_RevertToSelf
0x180014d82  jmp     loc_180014E36
0x180014d87  lea     r8, asc_18004E210; "\\??\\"
0x180014d8e  mov     edx, r14d; unsigned __int64
0x180014d91  mov     rcx, rbx; unsigned __int16 *
0x180014d94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014d99  mov     r8, rsi; unsigned __int16 *
0x180014d9c  mov     edx, r14d; unsigned __int64
0x180014d9f  mov     rcx, rbx; unsigned __int16 *
0x180014da2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014da7  mov     rdx, rbx; SourceString
0x180014daa  lea     rcx, [rbp+DestinationString]; DestinationString
0x180014dae  call    cs:__imp_RtlInitUnicodeString
0x180014db4  lea     rax, [rbp+DestinationString]
0x180014db8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180014dbf  xorps   xmm0, xmm0
0x180014dc2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180014dc6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180014dca  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180014dce  mov     edx, 10000h; DesiredAccess
0x180014dd3  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180014dda  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x180014dde  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180014de3  call    cs:__imp_NtOpenSymbolicLinkObject
0x180014de9  test    eax, eax
0x180014deb  js      short loc_180014E08
0x180014ded  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180014df1  call    cs:__imp_NtMakeTemporaryObject
0x180014df7  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x180014dfb  call    cs:__imp_NtClose
0x180014e01  mov     edi, 1
0x180014e06  jmp     short loc_180014E18
0x180014e08  mov     ecx, eax; Status
0x180014e0a  call    cs:__imp_RtlNtStatusToDosError
0x180014e10  mov     ecx, eax; dwErrCode
0x180014e12  call    cs:__imp_SetLastError
0x180014e18  call    cs:__imp_RevertToSelf
0x180014e1e  mov     rcx, gs:60h
0x180014e27  mov     r8, rbx; lpMem
0x180014e2a  xor     edx, edx; dwFlags
0x180014e2c  mov     rcx, [rcx+30h]; hHeap
0x180014e30  call    cs:__imp_HeapFree
0x180014e36  mov     eax, edi
0x180014e38  add     rsp, 68h
0x180014e3c  pop     r15
0x180014e3e  pop     r14
0x180014e40  pop     rdi
0x180014e41  pop     rsi
0x180014e42  pop     rbx
0x180014e43  pop     rbp
0x180014e44  retn
```
