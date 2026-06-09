# CUmRdpPrn::RegisterSerialPort(ushort const *,ushort const *)

- ea: `0x180016af8`
- end: `0x180016e6a`
- name: `?RegisterSerialPort@CUmRdpPrn@@AEAAHPEBG0@Z`
- size: `882`
- prototype: `__int64 __fastcall(HANDLE *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015164`

## callees

- `0x1800090b0`
- `0x180009fa8`
- `0x1800134cc`
- `0x180016af8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016df0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016de7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016de7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016bb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016cc7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016dce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016bb3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016cc7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016dce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016b6d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180016b6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e25`
- `ntdll!RtlNtStatusToDosError` at `0x180016ddf`
- `ntdll!RtlNtStatusToDosError` at `0x180016ddf`
- `ntdll!NtMakePermanentObject` at `0x180016e49`
- `ntdll!NtMakePermanentObject` at `0x180016e49`
- `ntdll!NtMakeTemporaryObject` at `0x180016d96`
- `ntdll!NtMakeTemporaryObject` at `0x180016d96`
- `ntdll!NtClose` at `0x180016cb6`
- `ntdll!NtClose` at `0x180016da2`
- `ntdll!NtClose` at `0x180016e55`
- `ntdll!NtClose` at `0x180016cb6`
- `ntdll!NtClose` at `0x180016da2`
- `ntdll!NtClose` at `0x180016e55`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180016c82`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180016d46`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180016c82`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180016d46`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180016c4b`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180016c4b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180016c2b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180016dc1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180016c2b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x180016dc1`
- `ntdll!RtlInitUnicodeString` at `0x180016be2`
- `ntdll!RtlInitUnicodeString` at `0x180016bef`
- `ntdll!RtlInitUnicodeString` at `0x180016be2`
- `ntdll!RtlInitUnicodeString` at `0x180016bef`
- `ntdll!NtQueryInformationProcess` at `0x180016b57`
- `ntdll!NtQueryInformationProcess` at `0x180016b57`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::RegisterSerialPort(HANDLE *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  WCHAR *v3; // rsi
  __int64 v7; // rbx
  BOOL v8; // r14d
  __int64 v10; // rax
  unsigned __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r12
  int TemporaryObject; // edi
  ULONG v15; // eax
  unsigned int v16; // edi
  unsigned __int16 *v17; // rax
  ULONG v18; // eax
  unsigned __int64 v19; // rcx
  DWORD v20; // eax
  unsigned int v21; // ebx
  int ProcessInformation; // [rsp+30h] [rbp-59h] BYREF
  void *SymbolicLinkHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING Name; // [rsp+60h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  ULONG DataWritten; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = 0;
  SymbolicLinkHandle = 0;
  ProcessInformation = 0;
  v7 = -1;
  DestinationString = 0;
  v8 = 0;
  Name = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessLUIDDeviceMapsEnabled, &ProcessInformation, 4u, 0) >= 0 )
  {
    if ( ProcessInformation )
    {
      v8 = ImpersonateLoggedOnUser(this[23]);
      if ( !v8 )
      {
        GetLastError();
        return 0;
      }
    }
  }
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = v10 + 5;
  v12 = (unsigned __int16 *)ALLOCMEM((unsigned int)(2 * (v10 + 5)));
  v13 = v12;
  if ( !v12 )
  {
    GetLastError();
    if ( v8 )
      RevertToSelf();
    return 0;
  }
  StringCchCopyW(v12, v11, L"\\??\\");
  StringCchCatW(v13, v11, a2);
  RtlInitUnicodeString(&DestinationString, v13);
  RtlInitUnicodeString(&Name, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  TemporaryObject = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, &Name);
  if ( TemporaryObject == -1073741771 )
  {
    TemporaryObject = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x10001u, &ObjectAttributes);
    if ( TemporaryObject >= 0 )
    {
      *(_DWORD *)(&LinkTarget.MaximumLength + 1) = 0;
      do
        ++v7;
      while ( a3[v7] );
      LinkTarget.Buffer = 0;
      *(_DWORD *)&LinkTarget.Length = 0;
      DataWritten = 0;
      if ( NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten) == -1073741789 )
      {
        v15 = DataWritten;
      }
      else
      {
        v15 = 0;
        DataWritten = 0;
      }
      v16 = v15 + 4 + 2 * v7;
      v17 = (unsigned __int16 *)ALLOCMEM(v16);
      v3 = v17;
      if ( !v17 )
      {
        NtClose(SymbolicLinkHandle);
        GetLastError();
        if ( v8 )
          RevertToSelf();
        HeapFree(NtCurrentPeb()->ProcessHeap, 0, v13);
        return 0;
      }
      StringCchCopyW(v17, (unsigned __int64)v16 >> 1, a3);
      v3[(unsigned int)v7] = 0;
      LOWORD(v18) = DataWritten;
      if ( !DataWritten )
        goto LABEL_29;
      LinkTarget.Buffer = &v3[(unsigned int)v7 + 1];
      *LinkTarget.Buffer = 0;
      LinkTarget.MaximumLength = v16 - 2 * v7 - 2;
      LinkTarget.Length = 0;
      DataWritten = 0;
      if ( NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten) )
      {
        v18 = 0;
      }
      else
      {
        LOWORD(v18) = DataWritten;
        if ( DataWritten <= 2 || (v19 = (unsigned __int64)DataWritten >> 1, !LinkTarget.Buffer[v19 - 2]) )
        {
LABEL_29:
          LinkTarget.Length = 2 * v7;
          LinkTarget.Buffer = v3;
          LinkTarget.MaximumLength = v18 + 2 * v7 + 2;
          TemporaryObject = NtMakeTemporaryObject(SymbolicLinkHandle);
          NtClose(SymbolicLinkHandle);
          SymbolicLinkHandle = 0;
          if ( TemporaryObject >= 0 )
            TemporaryObject = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, &LinkTarget);
          goto LABEL_31;
        }
        LinkTarget.Buffer[v19] = 0;
        v18 = DataWritten + 2;
      }
      DataWritten = v18;
      goto LABEL_29;
    }
  }
LABEL_31:
  if ( !v8 || RevertToSelf() )
  {
    if ( TemporaryObject >= 0 )
    {
      TemporaryObject = NtMakePermanentObject(SymbolicLinkHandle);
      NtClose(SymbolicLinkHandle);
      if ( TemporaryObject >= 0 )
      {
        v21 = 1;
        goto LABEL_35;
      }
    }
  }
  else
  {
    TemporaryObject = -1073741823;
  }
  v20 = RtlNtStatusToDosError(TemporaryObject);
  SetLastError(v20);
  v21 = 0;
  GetLastError();
LABEL_35:
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, v13);
  if ( v3 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
  return v21;
}

```

## disassembly

```asm
0x180016af8  push    rbp
0x180016afa  push    rbx
0x180016afb  push    rsi
0x180016afc  push    rdi
0x180016afd  push    r12
0x180016aff  push    r13
0x180016b01  push    r14
0x180016b03  push    r15
0x180016b05  lea     rbp, [rsp-1Fh]
0x180016b0a  sub     rsp, 0A8h
0x180016b11  xor     esi, esi
0x180016b13  xorps   xmm0, xmm0
0x180016b16  mov     r13, r8
0x180016b19  mov     [rbp+57h+SymbolicLinkHandle], rsi
0x180016b1d  mov     r15, rdx
0x180016b20  mov     [rbp+57h+ProcessInformation], esi
0x180016b23  mov     rdi, rcx
0x180016b26  mov     [rsp+0E0h+ReturnLength], rsi; ReturnLength
0x180016b2b  xorps   xmm1, xmm1
0x180016b2e  lea     r9d, [rsi+4]; ProcessInformationLength
0x180016b32  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016b36  lea     edx, [rsi+1Ch]; ProcessInformationClass
0x180016b39  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180016b3d  mov     rcx, rbx; ProcessHandle
0x180016b40  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180016b44  mov     r14d, esi
0x180016b47  movups  xmmword ptr [rbp+57h+Name.Length], xmm1
0x180016b4b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180016b4f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180016b53  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016b57  call    cs:__imp_NtQueryInformationProcess
0x180016b5d  test    eax, eax
0x180016b5f  js      short loc_180016B87
0x180016b61  cmp     [rbp+57h+ProcessInformation], esi
0x180016b64  jz      short loc_180016B87
0x180016b66  mov     rcx, [rdi+0B8h]; hToken
0x180016b6d  call    cs:__imp_ImpersonateLoggedOnUser
0x180016b73  mov     r14d, eax
0x180016b76  test    eax, eax
0x180016b78  jnz     short loc_180016B87
0x180016b7a  call    cs:__imp_GetLastError
0x180016b80  xor     eax, eax
0x180016b82  jmp     loc_180016E2D
0x180016b87  mov     rax, rbx
0x180016b8a  inc     rax
0x180016b8d  cmp     [r15+rax*2], si
0x180016b92  jnz     short loc_180016B8A
0x180016b94  lea     rdi, [rax+5]
0x180016b98  lea     ecx, [rdi+rdi]; dwBytes
0x180016b9b  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180016ba0  mov     r12, rax
0x180016ba3  test    rax, rax
0x180016ba6  jnz     short loc_180016BBB
0x180016ba8  call    cs:__imp_GetLastError
0x180016bae  test    r14d, r14d
0x180016bb1  jz      short loc_180016B80
0x180016bb3  call    cs:__imp_RevertToSelf
0x180016bb9  jmp     short loc_180016B80
0x180016bbb  lea     r8, asc_18004E210; "\\??\\"
0x180016bc2  mov     rdx, rdi; unsigned __int64
0x180016bc5  mov     rcx, r12; unsigned __int16 *
0x180016bc8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016bcd  mov     r8, r15; unsigned __int16 *
0x180016bd0  mov     rdx, rdi; unsigned __int64
0x180016bd3  mov     rcx, r12; unsigned __int16 *
0x180016bd6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016bdb  mov     rdx, r12; SourceString
0x180016bde  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180016be2  call    cs:__imp_RtlInitUnicodeString
0x180016be8  mov     rdx, r13; SourceString
0x180016beb  lea     rcx, [rbp+57h+Name]; DestinationString
0x180016bef  call    cs:__imp_RtlInitUnicodeString
0x180016bf5  lea     rax, [rbp+57h+DestinationString]
0x180016bf9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180016c00  xorps   xmm0, xmm0
0x180016c03  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180016c07  xor     r15d, r15d
0x180016c0a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180016c11  lea     r9, [rbp+57h+Name]; Name
0x180016c15  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180016c19  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180016c1d  mov     edx, 0F0001h; DesiredAccess
0x180016c22  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180016c26  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180016c2b  call    cs:__imp_NtCreateSymbolicLinkObject
0x180016c31  mov     edi, eax
0x180016c33  cmp     eax, 0C0000035h
0x180016c38  jnz     loc_180016DC9
0x180016c3e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180016c42  mov     edx, 10001h; DesiredAccess
0x180016c47  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180016c4b  call    cs:__imp_NtOpenSymbolicLinkObject
0x180016c51  mov     edi, eax
0x180016c53  test    eax, eax
0x180016c55  js      loc_180016DC9
0x180016c5b  mov     dword ptr [rbp+57h+LinkTarget+4], r15d
0x180016c5f  inc     rbx
0x180016c62  cmp     [r13+rbx*2+0], r15w
0x180016c68  jnz     short loc_180016C5F
0x180016c6a  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x180016c6e  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x180016c72  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x180016c76  mov     [rbp+57h+LinkTarget.Buffer], r15
0x180016c7a  mov     dword ptr [rbp+57h+LinkTarget.Length], r15d
0x180016c7e  mov     [rbp+57h+DataWritten], r15d
0x180016c82  call    cs:__imp_NtQuerySymbolicLinkObject
0x180016c88  cmp     eax, 0C0000023h
0x180016c8d  jz      short loc_180016C97
0x180016c8f  mov     eax, r15d
0x180016c92  mov     [rbp+57h+DataWritten], eax
0x180016c95  jmp     short loc_180016C9A
0x180016c97  mov     eax, [rbp+57h+DataWritten]
0x180016c9a  lea     edi, [rax+4]
0x180016c9d  lea     edi, [rdi+rbx*2]
0x180016ca0  mov     ecx, edi; dwBytes
0x180016ca2  mov     r15d, edi
0x180016ca5  call    ?ALLOCMEM@@YAPEAX_K@Z; ALLOCMEM(unsigned __int64)
0x180016caa  mov     rsi, rax
0x180016cad  test    rax, rax
0x180016cb0  jnz     short loc_180016CEA
0x180016cb2  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180016cb6  call    cs:__imp_NtClose
0x180016cbc  call    cs:__imp_GetLastError
0x180016cc2  test    r14d, r14d
0x180016cc5  jz      short loc_180016CCD
0x180016cc7  call    cs:__imp_RevertToSelf
0x180016ccd  mov     rcx, gs:60h
0x180016cd6  mov     r8, r12; lpMem
0x180016cd9  xor     edx, edx; dwFlags
0x180016cdb  mov     rcx, [rcx+30h]; hHeap
0x180016cdf  call    cs:__imp_HeapFree
0x180016ce5  jmp     loc_180016B80
0x180016cea  shr     r15, 1
0x180016ced  mov     r8, r13; unsigned __int16 *
0x180016cf0  mov     rdx, r15; unsigned __int64
0x180016cf3  mov     rcx, rsi; unsigned __int16 *
0x180016cf6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016cfb  xor     r15d, r15d
0x180016cfe  mov     r11d, ebx
0x180016d01  mov     [rsi+r11*2], r15w
0x180016d06  lea     r13d, [r15+2]
0x180016d0a  mov     eax, [rbp+57h+DataWritten]
0x180016d0d  test    eax, eax
0x180016d0f  jz      short loc_180016D7C
0x180016d11  inc     r11
0x180016d14  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x180016d18  movzx   eax, bx
0x180016d1b  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x180016d1f  add     ax, ax
0x180016d22  sub     di, ax
0x180016d25  lea     rcx, [rsi+r11*2]
0x180016d29  sub     di, r13w
0x180016d2d  mov     [rbp+57h+LinkTarget.Buffer], rcx
0x180016d31  mov     [rcx], r15w
0x180016d35  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x180016d39  mov     [rbp+57h+LinkTarget.MaximumLength], di
0x180016d3d  mov     [rbp+57h+LinkTarget.Length], r15w
0x180016d42  mov     [rbp+57h+DataWritten], r15d
0x180016d46  call    cs:__imp_NtQuerySymbolicLinkObject
0x180016d4c  test    eax, eax
0x180016d4e  jnz     short loc_180016D76
0x180016d50  mov     eax, [rbp+57h+DataWritten]
0x180016d53  cmp     eax, r13d
0x180016d56  jbe     short loc_180016D7C
0x180016d58  mov     rdx, [rbp+57h+LinkTarget.Buffer]
0x180016d5c  mov     ecx, eax
0x180016d5e  shr     rcx, 1
0x180016d61  cmp     [rdx+rcx*2-4], r15w
0x180016d67  jz      short loc_180016D7C
0x180016d69  mov     [rdx+rcx*2], r15w
0x180016d6e  mov     eax, [rbp+57h+DataWritten]
0x180016d71  add     eax, r13d
0x180016d74  jmp     short loc_180016D79
0x180016d76  mov     eax, r15d
0x180016d79  mov     [rbp+57h+DataWritten], eax
0x180016d7c  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180016d80  add     bx, bx
0x180016d83  mov     [rbp+57h+LinkTarget.Length], bx
0x180016d87  add     bx, ax
0x180016d8a  add     bx, r13w
0x180016d8e  mov     [rbp+57h+LinkTarget.Buffer], rsi
0x180016d92  mov     [rbp+57h+LinkTarget.MaximumLength], bx
0x180016d96  call    cs:__imp_NtMakeTemporaryObject
0x180016d9c  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180016da0  mov     edi, eax
0x180016da2  call    cs:__imp_NtClose
0x180016da8  mov     [rbp+57h+SymbolicLinkHandle], r15
0x180016dac  test    edi, edi
0x180016dae  js      short loc_180016DC9
0x180016db0  lea     r9, [rbp+57h+LinkTarget]; Name
0x180016db4  mov     edx, 0F0001h; DesiredAccess
0x180016db9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180016dbd  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180016dc1  call    cs:__imp_NtCreateSymbolicLinkObject
0x180016dc7  mov     edi, eax
0x180016dc9  test    r14d, r14d
0x180016dcc  jz      short loc_180016E41
0x180016dce  call    cs:__imp_RevertToSelf
0x180016dd4  test    eax, eax
0x180016dd6  jnz     short loc_180016E41
0x180016dd8  mov     edi, 0C0000001h
0x180016ddd  mov     ecx, edi; Status
0x180016ddf  call    cs:__imp_RtlNtStatusToDosError
0x180016de5  mov     ecx, eax; dwErrCode
0x180016de7  call    cs:__imp_SetLastError
0x180016ded  mov     ebx, r15d
0x180016df0  call    cs:__imp_GetLastError
0x180016df6  mov     rcx, gs:60h
0x180016dff  mov     r8, r12; lpMem
0x180016e02  xor     edx, edx; dwFlags
0x180016e04  mov     rcx, [rcx+30h]; hHeap
0x180016e08  call    cs:__imp_HeapFree
0x180016e0e  test    rsi, rsi
0x180016e11  jz      short loc_180016E2B
0x180016e13  mov     rcx, gs:60h
0x180016e1c  mov     r8, rsi; lpMem
0x180016e1f  xor     edx, edx; dwFlags
0x180016e21  mov     rcx, [rcx+30h]; hHeap
0x180016e25  call    cs:__imp_HeapFree
0x180016e2b  mov     eax, ebx
0x180016e2d  add     rsp, 0A8h
0x180016e34  pop     r15
0x180016e36  pop     r14
0x180016e38  pop     r13
0x180016e3a  pop     r12
0x180016e3c  pop     rdi
0x180016e3d  pop     rsi
0x180016e3e  pop     rbx
0x180016e3f  pop     rbp
0x180016e40  retn
0x180016e41  test    edi, edi
0x180016e43  js      short loc_180016DDD
0x180016e45  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Object
0x180016e49  call    cs:__imp_NtMakePermanentObject
0x180016e4f  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180016e53  mov     edi, eax
0x180016e55  call    cs:__imp_NtClose
0x180016e5b  test    edi, edi
0x180016e5d  js      loc_180016DDD
0x180016e63  mov     ebx, 1
0x180016e68  jmp     short loc_180016DF6
```
