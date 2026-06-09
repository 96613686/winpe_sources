# LookupAccountSidInternal

- ea: `0x18000d710`
- end: `0x18000dba3`
- name: `LookupAccountSidInternal`
- size: `1171`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d4e0`
- `0x18000d6e0`
- `0x180020adc`

## callees

- `0x18000d710`
- `0x18000dbb0`
- `0x18000dc40`
- `0x18000dcc0`
- `0x18000de70`
- `0x18001ffd4`
- `0x180020234`
- `0x1800202b8`
- `0x180020d40`
- `0x18004f902`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d96d`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d993`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d96d`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d993`
- `ntdll!RtlNtStatusToDosError` at `0x18000d8f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000d952`
- `ntdll!RtlNtStatusToDosError` at `0x18000d8f8`
- `ntdll!RtlNtStatusToDosError` at `0x18000d952`
- `ntdll!RtlCopyUnicodeString` at `0x18000da37`
- `ntdll!RtlCopyUnicodeString` at `0x18000da89`
- `ntdll!RtlCopyUnicodeString` at `0x18000da37`
- `ntdll!RtlCopyUnicodeString` at `0x18000da89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d900`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d95a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d900`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d95a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d84a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d84a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db44`

## pseudocode

```c
__int64 __fastcall LookupAccountSidInternal(
        __int64 a1,
        WCHAR *a2,
        unsigned int *a3,
        WCHAR *a4,
        ULONG *a5,
        _DWORD *a6,
        int a7)
{
  _DWORD *v7; // r12
  char *v8; // rdi
  WCHAR *v9; // r15
  WCHAR *v11; // rbx
  unsigned int v12; // esi
  int v13; // eax
  PVOID v14; // rbx
  int v15; // eax
  unsigned __int16 *v16; // r15
  int v17; // r12d
  char *v18; // rax
  __int64 v19; // rcx
  ULONG v20; // r8d
  ULONG v21; // r8d
  ULONG v22; // ecx
  unsigned int v23; // edx
  ULONG v24; // r8d
  DWORD v25; // eax
  DWORD v27; // eax
  int v28; // [rsp+28h] [rbp-C9h]
  char v29[8]; // [rsp+40h] [rbp-B1h] BYREF
  HLOCAL v30; // [rsp+48h] [rbp-A9h] BYREF
  ULONG v31; // [rsp+50h] [rbp-A1h] BYREF
  ULONG BytesInMultiByteString; // [rsp+54h] [rbp-9Dh] BYREF
  int v33; // [rsp+58h] [rbp-99h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-91h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-89h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-79h] BYREF
  __int64 v37; // [rsp+80h] [rbp-71h] BYREF
  size_t Size; // [rsp+88h] [rbp-69h] BYREF
  WCHAR *v39; // [rsp+90h] [rbp-61h]
  WCHAR *v40; // [rsp+98h] [rbp-59h]
  __int64 v41; // [rsp+A0h] [rbp-51h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-19h] BYREF
  int v44; // [rsp+E0h] [rbp-11h]

  v7 = a6;
  v8 = 0;
  v9 = a4;
  v40 = a4;
  v39 = a2;
  v11 = a2;
  v37 = a1;
  v41 = (__int64)a6;
  v12 = 1;
  hMem = 0;
  memset(&ObjectAttributes, 0, 44);
  PolicyHandle = 0;
  v30 = 0;
  v31 = 0;
  BytesInMultiByteString = 0;
  v43 = 0;
  v44 = 0;
  DestinationString = 0;
  v29[0] = 0;
  Size = 0;
  v33 = 0;
  if ( LsaLookupClientSidCacheEnabled
    && (int)LsaLookupClientFindTranslationsBySidInCache(
              a1,
              (unsigned int)&v37,
              (unsigned int)&v30,
              (unsigned int)&hMem,
              (__int64)&Size,
              (__int64)&v33,
              (__int64)v29) >= 0 )
  {
    v8 = (char *)hMem;
    goto LABEL_13;
  }
  v43 = 0x20000000CLL;
  ObjectAttributes.SecurityQualityOfService = &v43;
  LOWORD(v44) = 1;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v13 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v13 < 0 )
  {
    v27 = RtlNtStatusToDosError(v13);
    SetLastError(v27);
    return 0;
  }
  v14 = PolicyHandle;
  v33 = 0;
  hMem = 0;
  v15 = LsaInternalClientLookupSids(
          (_DWORD)PolicyHandle,
          1,
          (unsigned int)&v37,
          (unsigned int)&v30,
          (__int64)&hMem,
          v28,
          (__int64)&v33);
  v16 = (unsigned __int16 *)hMem;
  v17 = v15;
  if ( hMem )
  {
    Size = *((unsigned __int16 *)hMem + 5) + 32LL;
    v18 = (char *)LocalAlloc(0x40u, Size);
    v8 = v18;
    if ( v18 )
    {
      memset_0(v18, 0, Size);
      *(_DWORD *)v8 = *(_DWORD *)v16;
      *((_DWORD *)v8 + 6) = *((_DWORD *)v16 + 6);
      *((_WORD *)v8 + 4) = v16[4];
      *((_WORD *)v8 + 5) = v16[5];
      memcpy_0(v8 + 32, *((const void **)v16 + 2), v16[4]);
      *((_QWORD *)v8 + 2) = v8 + 32;
      v14 = PolicyHandle;
    }
    else
    {
      if ( v30 )
      {
        LocalFree(v30);
        v30 = 0;
      }
      v17 = -1073741670;
    }
    LocalFree(v16);
  }
  hMem = v8;
  LsaLookupClose(v14);
  if ( v17 >= 0 )
  {
    if ( LsaLookupClientSidCacheEnabled )
      LsaLookupClientUpdateCacheUsingSids(v19, &v37, v30, v8);
    v7 = (_DWORD *)v41;
    v9 = v40;
    v11 = v39;
LABEL_13:
    v20 = *((unsigned __int16 *)v8 + 4);
    if ( a7 )
    {
      v21 = v20 >> 1;
      BytesInMultiByteString = v21;
      v22 = *(unsigned __int16 *)(*((_QWORD *)v30 + 1) + 24LL * *((int *)v8 + 6)) >> 1;
      v31 = v22;
    }
    else
    {
      RtlUnicodeToMultiByteSize(&BytesInMultiByteString, *((PWCH *)v8 + 2), v20);
      RtlUnicodeToMultiByteSize(
        &v31,
        *(PWCH *)(*((_QWORD *)v30 + 1) + 24LL * *((int *)v8 + 6) + 8),
        *(unsigned __int16 *)(*((_QWORD *)v30 + 1) + 24LL * *((int *)v8 + 6)));
      v22 = v31;
      v21 = BytesInMultiByteString;
    }
    v23 = *a3;
    v24 = v21 + 1;
    if ( v24 > *a3 || v22 + 1 > *a5 )
    {
      *a5 = v22 + 1;
      *a3 = v24;
      v25 = RtlNtStatusToDosError(-1073741789);
      SetLastError(v25);
      v12 = 0;
      goto LABEL_17;
    }
    DestinationString.Buffer = v11;
    DestinationString.Length = 0;
    if ( v23 > 0x7FFF )
    {
      DestinationString.MaximumLength = -2;
    }
    else
    {
      DestinationString.MaximumLength = 2 * v23;
      if ( !v23 )
      {
LABEL_28:
        DestinationString.Buffer = v9;
        DestinationString.Length = 0;
        if ( *a5 > 0x7FFF )
          DestinationString.MaximumLength = -2;
        else
          DestinationString.MaximumLength = 2 * *a5;
        RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(*((_QWORD *)v30 + 1) + 24LL * *((int *)v8 + 6)));
        DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
        *a5 = v31;
        *a3 = BytesInMultiByteString;
        *v7 = *(_DWORD *)v8;
LABEL_17:
        if ( LsaLookupClientSidCacheEnabled && v29[0] )
        {
          if ( v30 )
          {
            LsaLookupClientFreeTranslatedNames(*(unsigned int *)v30, &hMem);
            LsaLookupClientFreeReferencedDomains(&v30);
          }
        }
        else
        {
          LocalFree(v8);
          if ( v30 )
            LocalFree(v30);
        }
        return v12;
      }
    }
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v8 + 8));
    DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
    goto LABEL_28;
  }
  if ( v17 == -1073741709 )
  {
    if ( v30 )
      LocalFree(v30);
    if ( v8 )
      LocalFree(v8);
  }
  BaseSetLastNTError((unsigned int)v17);
  return 0;
}

```

## disassembly

```asm
0x18000d710  push    rbp
0x18000d712  push    rbx
0x18000d713  push    rsi
0x18000d714  push    rdi
0x18000d715  push    r12
0x18000d717  push    r13
0x18000d719  push    r14
0x18000d71b  push    r15
0x18000d71d  lea     rbp, [rsp-7]
0x18000d722  sub     rsp, 0F8h
0x18000d729  mov     rax, cs:__security_cookie
0x18000d730  xor     rax, rsp
0x18000d733  mov     [rbp+3Fh+var_48], rax
0x18000d737  mov     r12, [rbp+3Fh+arg_28]
0x18000d73b  xor     edi, edi
0x18000d73d  mov     r13, [rbp+3Fh+arg_20]
0x18000d741  xor     eax, eax
0x18000d743  cmp     cs:LsaLookupClientSidCacheEnabled, al
0x18000d749  xorps   xmm0, xmm0
0x18000d74c  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x18000d750  mov     r15, r9
0x18000d753  mov     [rbp+3Fh+var_98], r9
0x18000d757  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x18000d75b  mov     r14, r8
0x18000d75e  mov     [rbp+3Fh+var_A0], rdx
0x18000d762  mov     rbx, rdx
0x18000d765  mov     [rbp+3Fh+var_B0], rcx
0x18000d769  mov     [rbp+3Fh+var_90], r12
0x18000d76d  mov     esi, 1
0x18000d772  mov     [rsp+130h+hMem], rdi
0x18000d777  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x18000d77b  mov     [rbp+3Fh+PolicyHandle], rdi
0x18000d77f  mov     [rsp+130h+var_E8], rdi
0x18000d784  mov     [rsp+130h+var_E0], edi
0x18000d788  mov     [rsp+130h+BytesInMultiByteString], edi
0x18000d78c  mov     [rbp+3Fh+var_58], rax
0x18000d790  mov     [rbp+3Fh+var_50], eax
0x18000d793  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x18000d798  mov     [rsp+130h+var_F0], al
0x18000d79c  mov     [rbp+3Fh+Size], rdi
0x18000d7a0  mov     [rsp+130h+var_D8], edi
0x18000d7a4  jnz     loc_18000DACD
0x18000d7aa  lea     rax, [rbp+3Fh+var_58]
0x18000d7ae  mov     dword ptr [rbp+3Fh+var_58], 0Ch
0x18000d7b5  lea     r8, [rbp+3Fh+PolicyHandle]; PolicyHandle
0x18000d7b9  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], rax
0x18000d7bd  mov     edx, 800h; AccessMask
0x18000d7c2  mov     dword ptr [rbp+3Fh+var_58+4], 2
0x18000d7c9  lea     rcx, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18000d7cd  mov     word ptr [rbp+3Fh+var_50], si
0x18000d7d1  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18000d7d8  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rdi
0x18000d7dc  mov     [rbp+3Fh+ObjectAttributes.Attributes], edi
0x18000d7df  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rdi
0x18000d7e3  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rdi
0x18000d7e7  call    LsaLookupOpenLocalPolicy
0x18000d7ec  test    eax, eax
0x18000d7ee  js      loc_18000D950
0x18000d7f4  mov     rbx, [rbp+3Fh+PolicyHandle]
0x18000d7f8  lea     rax, [rsp+130h+var_D8]
0x18000d7fd  mov     [rsp+130h+var_100], rax
0x18000d802  lea     r9, [rsp+130h+var_E8]
0x18000d807  lea     rax, [rsp+130h+hMem]
0x18000d80c  mov     [rsp+130h+var_D8], edi
0x18000d810  lea     r8, [rbp+3Fh+var_B0]
0x18000d814  mov     [rsp+130h+var_110], rax
0x18000d819  mov     edx, esi
0x18000d81b  mov     [rsp+130h+hMem], rdi
0x18000d820  mov     rcx, rbx
0x18000d823  call    LsaInternalClientLookupSids
0x18000d828  mov     r15, [rsp+130h+hMem]
0x18000d82d  mov     r12d, eax
0x18000d830  test    r15, r15
0x18000d833  jz      short loc_18000D879
0x18000d835  movzx   eax, word ptr [r15+0Ah]
0x18000d83a  mov     ecx, 40h ; '@'; uFlags
0x18000d83f  add     rax, 20h ; ' '
0x18000d843  mov     rdx, rax; uBytes
0x18000d846  mov     [rbp+3Fh+Size], rax
0x18000d84a  call    cs:__imp_LocalAlloc
0x18000d850  mov     rdi, rax
0x18000d853  test    rax, rax
0x18000d856  jnz     loc_18000D9A7
0x18000d85c  mov     rcx, [rsp+130h+var_E8]; hMem
0x18000d861  test    rcx, rcx
0x18000d864  jnz     loc_18000DB0F
0x18000d86a  mov     r12d, 0C000009Ah
0x18000d870  mov     rcx, r15; hMem
0x18000d873  call    cs:__imp_LocalFree
0x18000d879  mov     rcx, rbx; ObjectHandle
0x18000d87c  mov     [rsp+130h+hMem], rdi
0x18000d881  call    LsaLookupClose
0x18000d886  test    r12d, r12d
0x18000d889  js      loc_18000DB23
0x18000d88f  cmp     cs:LsaLookupClientSidCacheEnabled, 0
0x18000d896  jnz     loc_18000DB59
0x18000d89c  mov     r12, [rbp+3Fh+var_90]
0x18000d8a0  mov     r15, [rbp+3Fh+var_98]
0x18000d8a4  mov     rbx, [rbp+3Fh+var_A0]
0x18000d8a8  cmp     [rbp+3Fh+arg_30], 0
0x18000d8ac  movzx   r8d, word ptr [rdi+8]; BytesInUnicodeString
0x18000d8b1  jz      loc_18000D964
0x18000d8b7  shr     r8d, 1
0x18000d8ba  mov     [rsp+130h+BytesInMultiByteString], r8d
0x18000d8bf  movsxd  rax, dword ptr [rdi+18h]
0x18000d8c3  lea     rdx, [rax+rax*2]
0x18000d8c7  mov     rax, [rsp+130h+var_E8]
0x18000d8cc  mov     rcx, [rax+8]
0x18000d8d0  movzx   ecx, word ptr [rcx+rdx*8]
0x18000d8d4  shr     ecx, 1
0x18000d8d6  mov     [rsp+130h+var_E0], ecx
0x18000d8da  mov     edx, [r14]
0x18000d8dd  inc     r8d
0x18000d8e0  cmp     r8d, edx
0x18000d8e3  jbe     loc_18000D9F5
0x18000d8e9  lea     eax, [rcx+1]
0x18000d8ec  mov     ecx, 0C0000023h; Status
0x18000d8f1  mov     [r13+0], eax
0x18000d8f5  mov     [r14], r8d
0x18000d8f8  call    cs:__imp_RtlNtStatusToDosError
0x18000d8fe  mov     ecx, eax; dwErrCode
0x18000d900  call    cs:__imp_SetLastError
0x18000d906  xor     esi, esi
0x18000d908  cmp     cs:LsaLookupClientSidCacheEnabled, 0
0x18000d90f  jnz     loc_18000DB6F
0x18000d915  mov     rcx, rdi; hMem
0x18000d918  call    cs:__imp_LocalFree
0x18000d91e  mov     rcx, [rsp+130h+var_E8]; hMem
0x18000d923  test    rcx, rcx
0x18000d926  jz      short loc_18000D92E
0x18000d928  call    cs:__imp_LocalFree
0x18000d92e  mov     eax, esi
0x18000d930  mov     rcx, [rbp+3Fh+var_48]
0x18000d934  xor     rcx, rsp; StackCookie
0x18000d937  call    __security_check_cookie
0x18000d93c  add     rsp, 0F8h
0x18000d943  pop     r15
0x18000d945  pop     r14
0x18000d947  pop     r13
0x18000d949  pop     r12
0x18000d94b  pop     rdi
0x18000d94c  pop     rsi
0x18000d94d  pop     rbx
0x18000d94e  pop     rbp
0x18000d94f  retn
0x18000d950  mov     ecx, eax; Status
0x18000d952  call    cs:__imp_RtlNtStatusToDosError
0x18000d958  mov     ecx, eax; dwErrCode
0x18000d95a  call    cs:__imp_SetLastError
0x18000d960  xor     eax, eax
0x18000d962  jmp     short loc_18000D930
0x18000d964  mov     rdx, [rdi+10h]; UnicodeString
0x18000d968  lea     rcx, [rsp+130h+BytesInMultiByteString]; BytesInMultiByteString
0x18000d96d  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18000d973  movsxd  rax, dword ptr [rdi+18h]
0x18000d977  lea     rdx, [rax+rax*2]
0x18000d97b  mov     rax, [rsp+130h+var_E8]
0x18000d980  mov     rcx, [rax+8]
0x18000d984  movzx   r8d, word ptr [rcx+rdx*8]; BytesInUnicodeString
0x18000d989  mov     rdx, [rcx+rdx*8+8]; UnicodeString
0x18000d98e  lea     rcx, [rsp+130h+var_E0]; BytesInMultiByteString
0x18000d993  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18000d999  mov     ecx, [rsp+130h+var_E0]
0x18000d99d  mov     r8d, [rsp+130h+BytesInMultiByteString]
0x18000d9a2  jmp     loc_18000D8DA
0x18000d9a7  mov     r8, [rbp+3Fh+Size]; Size
0x18000d9ab  xor     edx, edx; Val
0x18000d9ad  mov     rcx, rdi; void *
0x18000d9b0  call    memset_0
0x18000d9b5  mov     eax, [r15]
0x18000d9b8  lea     rbx, [rdi+20h]
0x18000d9bc  mov     [rdi], eax
0x18000d9be  mov     rcx, rbx; void *
0x18000d9c1  mov     eax, [r15+18h]
0x18000d9c5  mov     [rdi+18h], eax
0x18000d9c8  movzx   eax, word ptr [r15+8]
0x18000d9cd  mov     [rdi+8], ax
0x18000d9d1  movzx   eax, word ptr [r15+0Ah]
0x18000d9d6  mov     [rdi+0Ah], ax
0x18000d9da  movzx   r8d, word ptr [r15+8]; Size
0x18000d9df  mov     rdx, [r15+10h]; Src
0x18000d9e3  call    memcpy_0
0x18000d9e8  mov     [rdi+10h], rbx
0x18000d9ec  mov     rbx, [rbp+3Fh+PolicyHandle]
0x18000d9f0  jmp     loc_18000D870
0x18000d9f5  lea     eax, [rcx+1]
0x18000d9f8  cmp     eax, [r13+0]
0x18000d9fc  ja      loc_18000D8E9
0x18000da02  xor     eax, eax
0x18000da04  mov     [rsp+130h+DestinationString.Buffer], rbx
0x18000da09  mov     [rsp+130h+DestinationString.Length], ax
0x18000da0e  mov     ebx, 0FFFEh
0x18000da13  cmp     edx, 7FFFh
0x18000da19  ja      loc_18000DAC3
0x18000da1f  movzx   eax, dx
0x18000da22  add     ax, ax
0x18000da25  mov     [rsp+130h+DestinationString.MaximumLength], ax
0x18000da2a  test    edx, edx
0x18000da2c  jz      short loc_18000DA50
0x18000da2e  lea     rdx, [rdi+8]; SourceString
0x18000da32  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18000da37  call    cs:__imp_RtlCopyUnicodeString
0x18000da3d  movzx   edx, [rsp+130h+DestinationString.Length]
0x18000da42  mov     rax, [rsp+130h+DestinationString.Buffer]
0x18000da47  shr     rdx, 1
0x18000da4a  xor     ecx, ecx
0x18000da4c  mov     [rax+rdx*2], cx
0x18000da50  xor     eax, eax
0x18000da52  mov     [rsp+130h+DestinationString.Buffer], r15
0x18000da57  mov     [rsp+130h+DestinationString.Length], ax
0x18000da5c  mov     eax, [r13+0]
0x18000da60  cmp     eax, 7FFFh
0x18000da65  ja      short loc_18000DABC
0x18000da67  add     ax, ax
0x18000da6a  mov     [rsp+130h+DestinationString.MaximumLength], ax
0x18000da6f  movsxd  rax, dword ptr [rdi+18h]
0x18000da73  lea     rdx, [rax+rax*2]
0x18000da77  mov     rax, [rsp+130h+var_E8]
0x18000da7c  mov     rcx, [rax+8]
0x18000da80  lea     rdx, [rcx+rdx*8]; SourceString
0x18000da84  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18000da89  call    cs:__imp_RtlCopyUnicodeString
0x18000da8f  movzx   edx, [rsp+130h+DestinationString.Length]
0x18000da94  mov     rax, [rsp+130h+DestinationString.Buffer]
0x18000da99  shr     rdx, 1
0x18000da9c  xor     ecx, ecx
0x18000da9e  mov     [rax+rdx*2], cx
0x18000daa2  mov     eax, [rsp+130h+var_E0]
0x18000daa6  mov     [r13+0], eax
0x18000daaa  mov     eax, [rsp+130h+BytesInMultiByteString]
0x18000daae  mov     [r14], eax
0x18000dab1  mov     eax, [rdi]
0x18000dab3  mov     [r12], eax
0x18000dab7  jmp     loc_18000D908
0x18000dabc  mov     [rsp+130h+DestinationString.MaximumLength], bx
0x18000dac1  jmp     short loc_18000DA6F
0x18000dac3  mov     [rsp+130h+DestinationString.MaximumLength], bx
0x18000dac8  jmp     loc_18000DA2E
0x18000dacd  lea     rax, [rsp+130h+var_F0]
0x18000dad2  mov     [rsp+130h+var_100], rax
0x18000dad7  lea     r9, [rsp+130h+hMem]
0x18000dadc  lea     rax, [rsp+130h+var_D8]
0x18000dae1  mov     [rsp+130h+var_108], rax
0x18000dae6  lea     r8, [rsp+130h+var_E8]
0x18000daeb  lea     rax, [rbp+3Fh+Size]
0x18000daef  lea     rdx, [rbp+3Fh+var_B0]
0x18000daf3  mov     [rsp+130h+var_110], rax
0x18000daf8  call    LsaLookupClientFindTranslationsBySidInCache
0x18000dafd  test    eax, eax
0x18000daff  js      loc_18000D7AA
0x18000db05  mov     rdi, [rsp+130h+hMem]
0x18000db0a  jmp     loc_18000D8A8
0x18000db0f  call    cs:__imp_LocalFree
0x18000db15  mov     [rsp+130h+var_E8], 0
0x18000db1e  jmp     loc_18000D86A
0x18000db23  cmp     r12d, 0C0000073h
0x18000db2a  jnz     short loc_18000DB4A
0x18000db2c  mov     rcx, [rsp+130h+var_E8]; hMem
0x18000db31  test    rcx, rcx
0x18000db34  jz      short loc_18000DB3C
0x18000db36  call    cs:__imp_LocalFree
0x18000db3c  test    rdi, rdi
0x18000db3f  jz      short loc_18000DB4A
0x18000db41  mov     rcx, rdi; hMem
0x18000db44  call    cs:__imp_LocalFree
0x18000db4a  mov     ecx, r12d
0x18000db4d  call    BaseSetLastNTError
0x18000db52  xor     eax, eax
0x18000db54  jmp     loc_18000D930
0x18000db59  mov     r8, [rsp+130h+var_E8]
0x18000db5e  lea     rdx, [rbp+3Fh+var_B0]
0x18000db62  mov     r9, rdi
0x18000db65  call    LsaLookupClientUpdateCacheUsingSids
0x18000db6a  jmp     loc_18000D89C
0x18000db6f  cmp     [rsp+130h+var_F0], 0
0x18000db74  jz      loc_18000D915
0x18000db7a  mov     rcx, [rsp+130h+var_E8]
0x18000db7f  test    rcx, rcx
0x18000db82  jz      loc_18000D92E
0x18000db88  mov     ecx, [rcx]
0x18000db8a  lea     rdx, [rsp+130h+hMem]
0x18000db8f  call    LsaLookupClientFreeTranslatedNames
0x18000db94  lea     rcx, [rsp+130h+var_E8]
0x18000db99  call    LsaLookupClientFreeReferencedDomains
0x18000db9e  jmp     loc_18000D92E
```
