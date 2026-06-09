# OpenPrivateNamespaceW(void * *)

- ea: `0x14001a608`
- end: `0x14001a8b5`
- name: `?OpenPrivateNamespaceW@@YAJPEAPEAX@Z`
- size: `685`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x14001aaa4`

## callees

- `0x140003224`
- `0x14000e318`
- `0x14000e340`
- `0x14001a5ac`
- `0x14001a608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83f`
- `ntdll!RtlInitUnicodeString` at `0x14001a682`
- `ntdll!RtlInitUnicodeString` at `0x14001a6e6`
- `ntdll!RtlInitUnicodeString` at `0x14001a682`
- `ntdll!RtlInitUnicodeString` at `0x14001a6e6`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x14001a68e`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x14001a68e`
- `ntdll!RtlCreateServiceSid` at `0x14001a6f6`
- `ntdll!RtlCreateServiceSid` at `0x14001a7b1`
- `ntdll!RtlCreateServiceSid` at `0x14001a6f6`
- `ntdll!RtlCreateServiceSid` at `0x14001a7b1`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x14001a7f3`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x14001a7f3`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x14001a88b`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x14001a88b`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x14001a831`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x14001a831`

## pseudocode

```c
__int64 __fastcall OpenPrivateNamespaceW(void **a1)
{
  void *v3; // rbx
  const struct std::nothrow_t *v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // edi
  NTSTATUS v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  void **v11; // rax
  NTSTATUS v12; // edi
  int v13; // edi
  HANDLE v14; // rax
  signed int LastError; // eax
  struct _UNICODE_STRING ServiceName; // [rsp+20h] [rbp-20h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG ServiceSidLength; // [rsp+60h] [rbp+20h] BYREF
  LPVOID lpBoundaryDescriptor; // [rsp+68h] [rbp+28h] BYREF
  void *v20; // [rsp+70h] [rbp+30h] BYREF

  lpBoundaryDescriptor = 0;
  ServiceSidLength = 0;
  DestinationString = 0;
  ServiceName = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    return 2147942487LL;
  }
  v3 = 0;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, L"WerSvcNameSpaceBoundary");
  lpBoundaryDescriptor = (LPVOID)RtlCreateBoundaryDescriptor(&DestinationString, 0);
  if ( !lpBoundaryDescriptor )
  {
    v7 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    goto LABEL_39;
  }
  RtlInitUnicodeString(&ServiceName, L"WerSvc");
  v8 = RtlCreateServiceSid(&ServiceName, 0, &ServiceSidLength);
  if ( v8 == -1073741789 )
  {
    v11 = (void **)utl::make_unique<unsigned char [0],0>(&v20, ServiceSidLength);
    v3 = *v11;
    *v11 = 0;
    if ( v20 )
      operator delete(v20, v4);
    if ( !v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
      v7 = -2147024882;
      goto LABEL_39;
    }
    v12 = RtlCreateServiceSid(&ServiceName, v3, &ServiceSidLength);
    if ( v12 >= 0 )
    {
      v13 = RtlAddSIDToBoundaryDescriptor(&lpBoundaryDescriptor, v3);
      if ( v13 >= 0 )
      {
        v14 = OpenPrivateNamespaceW(lpBoundaryDescriptor, L"WerSvc");
        *a1 = v14;
        if ( v14 )
        {
          v7 = 0;
          goto LABEL_39;
        }
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        v7 = LastError;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v10 = 52;
      }
      else
      {
        v7 = v13 | 0x10000000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v10 = 51;
      }
    }
    else
    {
      v7 = v12 | 0x10000000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v10 = 50;
    }
  }
  else
  {
    v7 = v8 | 0x10000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v10 = 48;
  }
  WPP_SF_d(v9[2], v10, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v7);
LABEL_39:
  if ( lpBoundaryDescriptor )
  {
    RtlDeleteBoundaryDescriptor(lpBoundaryDescriptor, v4, v5, v6);
    lpBoundaryDescriptor = 0;
  }
  if ( v3 )
    operator delete(v3, v4);
  return v7;
}

```

## disassembly

```asm
0x14001a608  mov     [rsp-18h+arg_18], rbx
0x14001a60d  push    rbp
0x14001a60e  push    rsi
0x14001a60f  push    rdi
0x14001a610  mov     rbp, rsp
0x14001a613  sub     rsp, 40h
0x14001a617  mov     [rbp+lpBoundaryDescriptor], 0
0x14001a61f  xorps   xmm0, xmm0
0x14001a622  mov     [rbp+ServiceSidLength], 0
0x14001a629  xorps   xmm1, xmm1
0x14001a62c  mov     rsi, rcx
0x14001a62f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a633  movups  xmmword ptr [rbp+ServiceName.Length], xmm1
0x14001a637  test    rcx, rcx
0x14001a63a  jnz     short loc_14001A672
0x14001a63c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a643  lea     rax, WPP_GLOBAL_Control
0x14001a64a  cmp     rcx, rax
0x14001a64d  jz      short loc_14001A668
0x14001a64f  test    byte ptr [rcx+1Ch], 1
0x14001a653  jz      short loc_14001A668
0x14001a655  mov     rcx, [rcx+10h]
0x14001a659  lea     edx, [rsi+2Eh]
0x14001a65c  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001a663  call    WPP_SF_
0x14001a668  mov     eax, 80070057h
0x14001a66d  jmp     loc_14001A8A8
0x14001a672  xor     ebx, ebx
0x14001a674  lea     rdx, SourceString; "WerSvcNameSpaceBoundary"
0x14001a67b  mov     [rcx], rbx
0x14001a67e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a682  call    cs:__imp_RtlInitUnicodeString
0x14001a688  xor     edx, edx
0x14001a68a  lea     rcx, [rbp+DestinationString]
0x14001a68e  call    cs:__imp_RtlCreateBoundaryDescriptor
0x14001a694  mov     [rbp+lpBoundaryDescriptor], rax
0x14001a698  test    rax, rax
0x14001a69b  jnz     short loc_14001A6DB
0x14001a69d  mov     edi, 80004005h
0x14001a6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6a9  lea     rax, WPP_GLOBAL_Control
0x14001a6b0  cmp     rcx, rax
0x14001a6b3  jz      loc_14001A882
0x14001a6b9  test    byte ptr [rcx+1Ch], 1
0x14001a6bd  jz      loc_14001A882
0x14001a6c3  mov     rcx, [rcx+10h]
0x14001a6c7  lea     edx, [rbx+2Fh]
0x14001a6ca  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001a6d1  call    WPP_SF_
0x14001a6d6  jmp     loc_14001A882
0x14001a6db  lea     rdx, AliasPrefix; "WerSvc"
0x14001a6e2  lea     rcx, [rbp+ServiceName]; DestinationString
0x14001a6e6  call    cs:__imp_RtlInitUnicodeString
0x14001a6ec  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x14001a6f0  xor     edx, edx; ServiceSid
0x14001a6f2  lea     rcx, [rbp+ServiceName]; ServiceName
0x14001a6f6  call    cs:__imp_RtlCreateServiceSid
0x14001a6fc  mov     edi, eax
0x14001a6fe  cmp     eax, 0C0000023h
0x14001a703  jz      short loc_14001A747
0x14001a705  bts     edi, 1Ch
0x14001a709  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a710  lea     rax, WPP_GLOBAL_Control
0x14001a717  cmp     rcx, rax
0x14001a71a  jz      loc_14001A882
0x14001a720  test    byte ptr [rcx+1Ch], 1
0x14001a724  jz      loc_14001A882
0x14001a72a  mov     edx, 30h ; '0'
0x14001a72f  mov     rcx, [rcx+10h]
0x14001a733  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001a73a  mov     r9d, edi
0x14001a73d  call    WPP_SF_d
0x14001a742  jmp     loc_14001A882
0x14001a747  mov     edx, [rbp+ServiceSidLength]
0x14001a74a  lea     rcx, [rbp+arg_10]
0x14001a74e  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x14001a753  mov     rbx, [rax]
0x14001a756  mov     qword ptr [rax], 0
0x14001a75d  mov     rcx, [rbp+arg_10]; void *
0x14001a761  test    rcx, rcx
0x14001a764  jz      short loc_14001A76B
0x14001a766  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a76b  test    rbx, rbx
0x14001a76e  jnz     short loc_14001A7A6
0x14001a770  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a777  lea     rax, WPP_GLOBAL_Control
0x14001a77e  cmp     rcx, rax
0x14001a781  jz      short loc_14001A79C
0x14001a783  test    byte ptr [rcx+1Ch], 1
0x14001a787  jz      short loc_14001A79C
0x14001a789  mov     rcx, [rcx+10h]
0x14001a78d  lea     edx, [rbx+31h]
0x14001a790  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001a797  call    WPP_SF_
0x14001a79c  mov     edi, 8007000Eh
0x14001a7a1  jmp     loc_14001A882
0x14001a7a6  lea     r8, [rbp+ServiceSidLength]; ServiceSidLength
0x14001a7aa  mov     rdx, rbx; ServiceSid
0x14001a7ad  lea     rcx, [rbp+ServiceName]; ServiceName
0x14001a7b1  call    cs:__imp_RtlCreateServiceSid
0x14001a7b7  mov     edi, eax
0x14001a7b9  test    eax, eax
0x14001a7bb  jns     short loc_14001A7EC
0x14001a7bd  bts     edi, 1Ch
0x14001a7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7c8  lea     rax, WPP_GLOBAL_Control
0x14001a7cf  cmp     rcx, rax
0x14001a7d2  jz      loc_14001A882
0x14001a7d8  test    byte ptr [rcx+1Ch], 1
0x14001a7dc  jz      loc_14001A882
0x14001a7e2  mov     edx, 32h ; '2'
0x14001a7e7  jmp     loc_14001A72F
0x14001a7ec  mov     rdx, rbx
0x14001a7ef  lea     rcx, [rbp+lpBoundaryDescriptor]
0x14001a7f3  call    cs:__imp_RtlAddSIDToBoundaryDescriptor
0x14001a7f9  mov     edi, eax
0x14001a7fb  test    eax, eax
0x14001a7fd  jns     short loc_14001A826
0x14001a7ff  bts     edi, 1Ch
0x14001a803  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a80a  lea     rax, WPP_GLOBAL_Control
0x14001a811  cmp     rcx, rax
0x14001a814  jz      short loc_14001A882
0x14001a816  test    byte ptr [rcx+1Ch], 1
0x14001a81a  jz      short loc_14001A882
0x14001a81c  mov     edx, 33h ; '3'
0x14001a821  jmp     loc_14001A72F
0x14001a826  mov     rcx, [rbp+lpBoundaryDescriptor]; lpBoundaryDescriptor
0x14001a82a  lea     rdx, AliasPrefix; "WerSvc"
0x14001a831  call    cs:__imp_OpenPrivateNamespaceW
0x14001a837  mov     [rsi], rax
0x14001a83a  test    rax, rax
0x14001a83d  jnz     short loc_14001A880
0x14001a83f  call    cs:__imp_GetLastError
0x14001a845  test    eax, eax
0x14001a847  jle     short loc_14001A851
0x14001a849  movzx   eax, ax
0x14001a84c  or      eax, 80070000h
0x14001a851  mov     edi, 80004005h
0x14001a856  test    eax, eax
0x14001a858  cmovns  eax, edi
0x14001a85b  mov     edi, eax
0x14001a85d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a864  lea     rax, WPP_GLOBAL_Control
0x14001a86b  cmp     rcx, rax
0x14001a86e  jz      short loc_14001A882
0x14001a870  test    byte ptr [rcx+1Ch], 1
0x14001a874  jz      short loc_14001A882
0x14001a876  mov     edx, 34h ; '4'
0x14001a87b  jmp     loc_14001A72F
0x14001a880  xor     edi, edi
0x14001a882  mov     rcx, [rbp+lpBoundaryDescriptor]
0x14001a886  test    rcx, rcx
0x14001a889  jz      short loc_14001A899
0x14001a88b  call    cs:__imp_RtlDeleteBoundaryDescriptor
0x14001a891  mov     [rbp+lpBoundaryDescriptor], 0
0x14001a899  test    rbx, rbx
0x14001a89c  jz      short loc_14001A8A6
0x14001a89e  mov     rcx, rbx; void *
0x14001a8a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a8a6  mov     eax, edi
0x14001a8a8  mov     rbx, [rsp+40h+arg_18]
0x14001a8ad  add     rsp, 40h
0x14001a8b1  pop     rdi
0x14001a8b2  pop     rsi
0x14001a8b3  pop     rbp
0x14001a8b4  retn
```
