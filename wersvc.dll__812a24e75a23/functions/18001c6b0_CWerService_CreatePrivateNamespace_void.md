# CWerService::_CreatePrivateNamespace(void)

- ea: `0x18001c6b0`
- end: `0x18001c9f2`
- name: `?_CreatePrivateNamespace@CWerService@@AEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(CWerService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d9e8`

## callees

- `0x1800029f4`
- `0x180006a80`
- `0x180011ef8`
- `0x180013ef8`
- `0x180013f54`
- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c976`
- `ntdll!RtlInitUnicodeString` at `0x18001c6f9`
- `ntdll!RtlInitUnicodeString` at `0x18001c75d`
- `ntdll!RtlInitUnicodeString` at `0x18001c6f9`
- `ntdll!RtlInitUnicodeString` at `0x18001c75d`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18001c705`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18001c705`
- `ntdll!RtlCreateServiceSid` at `0x18001c76d`
- `ntdll!RtlCreateServiceSid` at `0x18001c7fc`
- `ntdll!RtlCreateServiceSid` at `0x18001c76d`
- `ntdll!RtlCreateServiceSid` at `0x18001c7fc`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x18001c83e`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x18001c83e`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18001c9bb`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18001c9bb`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x18001c935`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x18001c935`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x18001c95f`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x18001c95f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9df`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c8c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c8c1`

## pseudocode

```c
__int64 __fastcall CWerService::_CreatePrivateNamespace(CWerService *this)
{
  void *v2; // rbx
  const struct std::nothrow_t *v3; // rdx
  unsigned int v4; // edi
  NTSTATUS v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  void **v9; // rax
  NTSTATUS v10; // edi
  int v11; // edi
  void **v12; // rax
  signed int LastError; // eax
  HANDLE v14; // rax
  void *v16; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING ServiceName; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+48h] [rbp-18h] BYREF
  ULONG ServiceSidLength; // [rsp+98h] [rbp+38h] BYREF
  LPVOID lpBoundaryDescriptor; // [rsp+A0h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+48h] BYREF

  hMem = 0;
  lpBoundaryDescriptor = 0;
  v2 = 0;
  DestinationString = 0;
  ServiceSidLength = 0;
  ServiceName = 0;
  memset(&PrivateNamespaceAttributes, 0, sizeof(PrivateNamespaceAttributes));
  RtlInitUnicodeString(&DestinationString, L"WerSvcNameSpaceBoundary");
  lpBoundaryDescriptor = (LPVOID)RtlCreateBoundaryDescriptor(&DestinationString, 0);
  if ( !lpBoundaryDescriptor )
  {
    v4 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    goto LABEL_47;
  }
  RtlInitUnicodeString(&ServiceName, L"WerSvc");
  v5 = RtlCreateServiceSid(&ServiceName, 0, &ServiceSidLength);
  if ( v5 != -1073741789 )
  {
    v4 = v5 | 0x10000000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v7 = 66;
LABEL_9:
    v8 = v4;
LABEL_10:
    WPP_SF_d(v6[2], v7, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
    goto LABEL_47;
  }
  v9 = (void **)utl::make_unique<unsigned char [0],0>(&v16, ServiceSidLength);
  v2 = *v9;
  *v9 = 0;
  if ( v16 )
    operator delete(v16, v3);
  if ( !v2 )
  {
    v4 = -2147024882;
    goto LABEL_47;
  }
  v10 = RtlCreateServiceSid(&ServiceName, v2, &ServiceSidLength);
  if ( v10 < 0 )
  {
    v4 = v10 | 0x10000000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v7 = 67;
    goto LABEL_9;
  }
  v11 = RtlAddSIDToBoundaryDescriptor(&lpBoundaryDescriptor, v2);
  if ( v11 < 0 )
  {
    v4 = v11 | 0x10000000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v7 = 68;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  v12 = ___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;GA;;;S-1-5-80-3299868208-4286319593-1091140620-3583751967-1732444380)(A;OICI;GR;;;AU)",
         1u,
         v12,
         0) )
  {
    PrivateNamespaceAttributes.lpSecurityDescriptor = hMem;
    PrivateNamespaceAttributes.nLength = 24;
    PrivateNamespaceAttributes.bInheritHandle = 0;
    v14 = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, lpBoundaryDescriptor, L"WerSvc");
    *((_QWORD *)this + 48) = v14;
    if ( !v14 && GetLastError() == 183 )
      *((_QWORD *)this + 48) = OpenPrivateNamespaceW(lpBoundaryDescriptor, L"WerSvc");
    if ( *((_QWORD *)this + 48) )
    {
      v4 = 0;
      goto LABEL_47;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v4 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 71;
      goto LABEL_34;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v4 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 70;
LABEL_34:
      v8 = (unsigned int)LastError;
      goto LABEL_10;
    }
  }
LABEL_47:
  if ( lpBoundaryDescriptor )
  {
    RtlDeleteBoundaryDescriptor();
    lpBoundaryDescriptor = 0;
  }
  if ( v2 )
    operator delete(v2, v3);
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x18001c6b0  push    rbp
0x18001c6b2  push    rbx
0x18001c6b3  push    rsi
0x18001c6b4  push    rdi
0x18001c6b5  push    r14
0x18001c6b7  mov     rbp, rsp
0x18001c6ba  sub     rsp, 60h
0x18001c6be  xorps   xmm0, xmm0
0x18001c6c1  mov     [rbp+hMem], 0
0x18001c6c9  mov     r14, rcx
0x18001c6cc  mov     [rbp+lpBoundaryDescriptor], 0
0x18001c6d4  xorps   xmm1, xmm1
0x18001c6d7  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001c6db  xor     eax, eax
0x18001c6dd  lea     rdx, aWersvcnamespac; "WerSvcNameSpaceBoundary"
0x18001c6e4  xor     ebx, ebx
0x18001c6e6  mov     qword ptr [rbp+PrivateNamespaceAttributes.bInheritHandle], rax
0x18001c6ea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001c6ee  mov     [rbp+ServiceSidLength], ebx
0x18001c6f1  movups  xmmword ptr [rbp+ServiceName.Length], xmm1
0x18001c6f5  movups  xmmword ptr [rbp+PrivateNamespaceAttributes.nLength], xmm0
0x18001c6f9  call    cs:__imp_RtlInitUnicodeString
0x18001c6ff  xor     edx, edx
0x18001c701  lea     rcx, [rbp+DestinationString]
0x18001c705  call    cs:__imp_RtlCreateBoundaryDescriptor
0x18001c70b  mov     [rbp+lpBoundaryDescriptor], rax
0x18001c70f  test    rax, rax
0x18001c712  jnz     short loc_18001C752
0x18001c714  mov     edi, 80004005h
0x18001c719  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c720  lea     rsi, WPP_GLOBAL_Control
0x18001c727  cmp     rcx, rsi
0x18001c72a  jz      loc_18001C9B2
0x18001c730  test    byte ptr [rcx+1Ch], 1
0x18001c734  jz      loc_18001C9B2
0x18001c73a  mov     rcx, [rcx+10h]
0x18001c73e  lea     edx, [rbx+41h]
0x18001c741  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c748  call    WPP_SF_
0x18001c74d  jmp     loc_18001C9B2
0x18001c752  lea     rdx, AliasPrefix; "WerSvc"
0x18001c759  lea     rcx, [rbp+ServiceName]; DestinationString
0x18001c75d  call    cs:__imp_RtlInitUnicodeString
0x18001c763  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x18001c767  xor     edx, edx; ServiceSid
0x18001c769  lea     rcx, [rbp+ServiceName]; ServiceName
0x18001c76d  call    cs:__imp_RtlCreateServiceSid
0x18001c773  mov     edi, eax
0x18001c775  cmp     eax, 0C0000023h
0x18001c77a  jz      short loc_18001C7BE
0x18001c77c  bts     edi, 1Ch
0x18001c780  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c787  lea     rsi, WPP_GLOBAL_Control
0x18001c78e  cmp     rcx, rsi
0x18001c791  jz      loc_18001C9B2
0x18001c797  test    byte ptr [rcx+1Ch], 1
0x18001c79b  jz      loc_18001C9B2
0x18001c7a1  mov     edx, 42h ; 'B'
0x18001c7a6  mov     r9d, edi
0x18001c7a9  mov     rcx, [rcx+10h]
0x18001c7ad  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c7b4  call    WPP_SF_d
0x18001c7b9  jmp     loc_18001C9B2
0x18001c7be  mov     edx, [rbp+ServiceSidLength]
0x18001c7c1  lea     rcx, [rbp+var_40]
0x18001c7c5  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18001c7ca  mov     rbx, [rax]
0x18001c7cd  mov     qword ptr [rax], 0
0x18001c7d4  mov     rcx, [rbp+var_40]; void *
0x18001c7d8  test    rcx, rcx
0x18001c7db  jz      short loc_18001C7E2
0x18001c7dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c7e2  test    rbx, rbx
0x18001c7e5  jnz     short loc_18001C7F1
0x18001c7e7  mov     edi, 8007000Eh
0x18001c7ec  jmp     loc_18001C9B2
0x18001c7f1  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x18001c7f5  mov     rdx, rbx; ServiceSid
0x18001c7f8  lea     rcx, [rbp+ServiceName]; ServiceName
0x18001c7fc  call    cs:__imp_RtlCreateServiceSid
0x18001c802  mov     edi, eax
0x18001c804  test    eax, eax
0x18001c806  jns     short loc_18001C837
0x18001c808  bts     edi, 1Ch
0x18001c80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c813  lea     rsi, WPP_GLOBAL_Control
0x18001c81a  cmp     rcx, rsi
0x18001c81d  jz      loc_18001C9B2
0x18001c823  test    byte ptr [rcx+1Ch], 1
0x18001c827  jz      loc_18001C9B2
0x18001c82d  mov     edx, 43h ; 'C'
0x18001c832  jmp     loc_18001C7A6
0x18001c837  mov     rdx, rbx
0x18001c83a  lea     rcx, [rbp+lpBoundaryDescriptor]
0x18001c83e  call    cs:__imp_RtlAddSIDToBoundaryDescriptor
0x18001c844  mov     edi, eax
0x18001c846  test    eax, eax
0x18001c848  jns     short loc_18001C879
0x18001c84a  bts     edi, 1Ch
0x18001c84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c855  lea     rsi, WPP_GLOBAL_Control
0x18001c85c  cmp     rcx, rsi
0x18001c85f  jz      loc_18001C9B2
0x18001c865  test    byte ptr [rcx+1Ch], 1
0x18001c869  jz      loc_18001C9B2
0x18001c86f  mov     edx, 44h ; 'D'
0x18001c874  jmp     loc_18001C7A6
0x18001c879  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c880  lea     rsi, WPP_GLOBAL_Control
0x18001c887  cmp     rcx, rsi
0x18001c88a  jz      short loc_18001C8A7
0x18001c88c  test    byte ptr [rcx+1Ch], 4
0x18001c890  jz      short loc_18001C8A7
0x18001c892  mov     rcx, [rcx+10h]
0x18001c896  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001c89d  mov     edx, 45h ; 'E'
0x18001c8a2  call    WPP_SF_
0x18001c8a7  lea     rcx, [rbp+hMem]
0x18001c8ab  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001c8b0  xor     r9d, r9d; SecurityDescriptorSize
0x18001c8b3  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GA;;;S-1-5-80-3299868208-4286"...
0x18001c8ba  mov     r8, rax; SecurityDescriptor
0x18001c8bd  lea     edx, [r9+1]; StringSDRevision
0x18001c8c1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c8c7  test    eax, eax
0x18001c8c9  jnz     short loc_18001C910
0x18001c8cb  call    cs:__imp_GetLastError
0x18001c8d1  test    eax, eax
0x18001c8d3  jle     short loc_18001C8DD
0x18001c8d5  movzx   eax, ax
0x18001c8d8  or      eax, 80070000h
0x18001c8dd  mov     edi, 80004005h
0x18001c8e2  test    eax, eax
0x18001c8e4  cmovns  eax, edi
0x18001c8e7  mov     edi, eax
0x18001c8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8f0  cmp     rcx, rsi
0x18001c8f3  jz      loc_18001C9B2
0x18001c8f9  test    byte ptr [rcx+1Ch], 1
0x18001c8fd  jz      loc_18001C9B2
0x18001c903  mov     edx, 46h ; 'F'
0x18001c908  mov     r9d, eax
0x18001c90b  jmp     loc_18001C7A9
0x18001c910  mov     rax, [rbp+hMem]
0x18001c914  lea     r8, AliasPrefix; "WerSvc"
0x18001c91b  mov     rdx, [rbp+lpBoundaryDescriptor]; lpBoundaryDescriptor
0x18001c91f  lea     rcx, [rbp+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x18001c923  mov     [rbp+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x18001c927  mov     [rbp+PrivateNamespaceAttributes.nLength], 18h
0x18001c92e  mov     [rbp+PrivateNamespaceAttributes.bInheritHandle], 0
0x18001c935  call    cs:__imp_CreatePrivateNamespaceW
0x18001c93b  mov     [r14+180h], rax
0x18001c942  test    rax, rax
0x18001c945  jnz     short loc_18001C96C
0x18001c947  call    cs:__imp_GetLastError
0x18001c94d  cmp     eax, 0B7h
0x18001c952  jnz     short loc_18001C96C
0x18001c954  mov     rcx, [rbp+lpBoundaryDescriptor]; lpBoundaryDescriptor
0x18001c958  lea     rdx, AliasPrefix; "WerSvc"
0x18001c95f  call    cs:__imp_OpenPrivateNamespaceW
0x18001c965  mov     [r14+180h], rax
0x18001c96c  cmp     qword ptr [r14+180h], 0
0x18001c974  jnz     short loc_18001C9B0
0x18001c976  call    cs:__imp_GetLastError
0x18001c97c  test    eax, eax
0x18001c97e  jle     short loc_18001C988
0x18001c980  movzx   eax, ax
0x18001c983  or      eax, 80070000h
0x18001c988  mov     edi, 80004005h
0x18001c98d  test    eax, eax
0x18001c98f  cmovns  eax, edi
0x18001c992  mov     edi, eax
0x18001c994  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c99b  cmp     rcx, rsi
0x18001c99e  jz      short loc_18001C9B2
0x18001c9a0  test    byte ptr [rcx+1Ch], 1
0x18001c9a4  jz      short loc_18001C9B2
0x18001c9a6  mov     edx, 47h ; 'G'
0x18001c9ab  jmp     loc_18001C908
0x18001c9b0  xor     edi, edi
0x18001c9b2  mov     rcx, [rbp+lpBoundaryDescriptor]
0x18001c9b6  test    rcx, rcx
0x18001c9b9  jz      short loc_18001C9C9
0x18001c9bb  call    cs:__imp_RtlDeleteBoundaryDescriptor
0x18001c9c1  mov     [rbp+lpBoundaryDescriptor], 0
0x18001c9c9  test    rbx, rbx
0x18001c9cc  jz      short loc_18001C9D6
0x18001c9ce  mov     rcx, rbx; void *
0x18001c9d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c9d6  mov     rcx, [rbp+hMem]; hMem
0x18001c9da  test    rcx, rcx
0x18001c9dd  jz      short loc_18001C9E5
0x18001c9df  call    cs:__imp_LocalFree
0x18001c9e5  mov     eax, edi
0x18001c9e7  add     rsp, 60h
0x18001c9eb  pop     r14
0x18001c9ed  pop     rdi
0x18001c9ee  pop     rsi
0x18001c9ef  pop     rbx
0x18001c9f0  pop     rbp
0x18001c9f1  retn
```
