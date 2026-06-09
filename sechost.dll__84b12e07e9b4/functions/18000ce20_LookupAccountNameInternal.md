# LookupAccountNameInternal

- ea: `0x18000ce20`
- end: `0x18000d1c0`
- name: `LookupAccountNameInternal`
- size: `928`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PSID DestinationSid@<rdx>, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cdf0`
- `0x180018940`

## callees

- `0x18000ce20`
- `0x18000d1d0`
- `0x18000dbb0`
- `0x18000dc40`
- `0x18000de70`
- `0x18000de94`
- `0x180020234`
- `0x180020314`
- `0x180020adc`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000cea1`
- `ntdll!RtlInitUnicodeString` at `0x18000cea1`
- `ntdll!RtlCopySid` at `0x18000d047`
- `ntdll!RtlCopySid` at `0x18000d047`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d0c1`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18000d0c1`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfba`
- `ntdll!RtlNtStatusToDosError` at `0x18000d01e`
- `ntdll!RtlNtStatusToDosError` at `0x18000cfba`
- `ntdll!RtlNtStatusToDosError` at `0x18000d01e`
- `ntdll!RtlLengthSid` at `0x18000cf94`
- `ntdll!RtlLengthSid` at `0x18000cf94`
- `ntdll!RtlCopyUnicodeString` at `0x18000d089`
- `ntdll!RtlCopyUnicodeString` at `0x18000d089`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d026`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d176`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d162`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d176`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1b5`

## pseudocode

```c
__int64 __fastcall LookupAccountNameInternal(
        PCWSTR SourceString,
        PSID DestinationSid,
        ULONG *a3,
        WCHAR *a4,
        ULONG *a5,
        _DWORD *a6,
        int a7)
{
  int v10; // ecx
  unsigned int v11; // esi
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  int v14; // ecx
  PSID *v15; // rbx
  __int64 v16; // rcx
  ULONG v17; // eax
  ULONG v18; // r8d
  DWORD v19; // eax
  DWORD v21; // eax
  USHORT v22; // ax
  int v23; // [rsp+30h] [rbp-D0h]
  _BYTE v24[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v25; // [rsp+48h] [rbp-B8h] BYREF
  ULONG BytesInMultiByteString; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v29; // [rsp+68h] [rbp-98h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v32; // [rsp+A0h] [rbp-60h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-20h] BYREF
  int v35; // [rsp+E8h] [rbp-18h]

  PolicyHandle = 0;
  v34 = 0;
  v35 = 0;
  v25 = 0;
  hMem = 0;
  *(_QWORD *)&v32.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  BytesInMultiByteString = 0;
  DestinationString = 0;
  v28 = 0;
  v29 = 0;
  v24[0] = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v11 = 1;
  if ( LsaLookupClientSidCacheEnabled
    && (int)LsaLookupClientFindTranslationsByNameInCache(
              v10,
              (unsigned int)&DestinationString,
              (unsigned int)&v25,
              (unsigned int)&hMem,
              (__int64)&v32,
              (__int64)&v28,
              (__int64)v24) >= 0 )
  {
    goto LABEL_5;
  }
  v34 = 0x20000000CLL;
  ObjectAttributes.SecurityQualityOfService = &v34;
  LOWORD(v35) = 1;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v12 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v12 < 0 )
  {
    BaseSetLastNTError((unsigned int)v12);
    return 0;
  }
  v28 = 0;
  v25 = 0;
  hMem = 0;
  v13 = LsaInternalClientLookupNames(
          (_DWORD)PolicyHandle,
          0,
          1,
          (unsigned int)&DestinationString,
          (__int64)&v25,
          (__int64)&hMem,
          v23,
          (__int64)&v28);
  LsaLookupClose(PolicyHandle);
  if ( LsaLookupClientSidCacheEnabled )
  {
    if ( v13 >= 0 )
    {
      v15 = (PSID *)hMem;
      v32 = DestinationString;
      LsaLookupClientUpdateCacheUsingNames(v14, a7, (unsigned int)&v32, (_DWORD)hMem, (__int64)v25);
      goto LABEL_6;
    }
  }
  else if ( v13 >= 0 )
  {
LABEL_5:
    v15 = (PSID *)hMem;
LABEL_6:
    v16 = *((_QWORD *)v25 + 1);
    if ( a7 )
      BytesInMultiByteString = *(unsigned __int16 *)(v16 + 24LL * *((int *)v15 + 4)) >> 1;
    else
      RtlUnicodeToMultiByteSize(
        &BytesInMultiByteString,
        *(PWCH *)(v16 + 24LL * *((int *)v15 + 4) + 8),
        *(unsigned __int16 *)(v16 + 24LL * *((int *)v15 + 4)));
    v17 = RtlLengthSid(v15[1]);
    v18 = BytesInMultiByteString;
    if ( v17 > *a3 || BytesInMultiByteString + 1 > *a5 )
    {
      *a3 = v17;
      *a5 = v18 + 1;
      v19 = RtlNtStatusToDosError(-1073741789);
      SetLastError(v19);
      v11 = 0;
    }
    else
    {
      RtlCopySid(*a3, DestinationSid, v15[1]);
      v29.Buffer = a4;
      v29.Length = 0;
      if ( *a5 >= 0x7FFF )
        v22 = -2;
      else
        v22 = 2 * *a5;
      v29.MaximumLength = v22;
      RtlCopyUnicodeString(&v29, (PCUNICODE_STRING)(*((_QWORD *)v25 + 1) + 24LL * *((int *)v15 + 4)));
      v29.Buffer[(unsigned __int64)v29.Length >> 1] = 0;
      *a6 = *(_DWORD *)v15;
      *a5 = BytesInMultiByteString;
    }
    if ( LsaLookupClientSidCacheEnabled && v24[0] )
    {
      if ( v25 )
      {
        LsaLookupClientFreeTranslatedSids(*(unsigned int *)v25, &hMem);
        LsaLookupClientFreeReferencedDomains(&v25);
      }
    }
    else
    {
      if ( v25 )
        LocalFree(v25);
      LocalFree(v15);
    }
    return v11;
  }
  if ( v13 == -1073741709 )
  {
    if ( v25 )
      LocalFree(v25);
    if ( hMem )
      LocalFree(hMem);
  }
  v21 = RtlNtStatusToDosError(v13);
  SetLastError(v21);
  return 0;
}

```

## disassembly

```asm
0x18000ce20  push    rbp
0x18000ce22  push    rbx
0x18000ce23  push    rsi
0x18000ce24  push    rdi
0x18000ce25  push    r12
0x18000ce27  push    r13
0x18000ce29  push    r14
0x18000ce2b  push    r15
0x18000ce2d  lea     rbp, [rsp-8]
0x18000ce32  sub     rsp, 108h
0x18000ce39  mov     rax, cs:__security_cookie
0x18000ce40  xor     rax, rsp
0x18000ce43  mov     [rbp+40h+var_50], rax
0x18000ce47  mov     r15, [rbp+40h+arg_20]
0x18000ce4b  xorps   xmm0, xmm0
0x18000ce4e  mov     rdi, [rbp+40h+arg_28]
0x18000ce52  xor     ebx, ebx
0x18000ce54  xor     eax, eax
0x18000ce56  mov     [rsp+140h+PolicyHandle], rbx
0x18000ce5b  mov     r12, rdx
0x18000ce5e  mov     [rbp+40h+var_60], rax
0x18000ce62  mov     rdx, rcx; SourceString
0x18000ce65  mov     [rbp+40h+var_58], eax
0x18000ce68  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18000ce6c  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x18000ce70  mov     [rsp+140h+var_F8], rbx
0x18000ce75  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x18000ce79  mov     r13, r9
0x18000ce7c  mov     [rsp+140h+hMem], rbx
0x18000ce81  mov     r14, r8
0x18000ce84  mov     qword ptr [rbp+40h+var_A0], rbx
0x18000ce88  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18000ce8c  mov     [rsp+140h+BytesInMultiByteString], ebx
0x18000ce90  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x18000ce94  mov     [rsp+140h+var_E0], ebx
0x18000ce98  movups  xmmword ptr [rsp+140h+var_D8.Length], xmm0
0x18000ce9d  mov     [rsp+140h+var_100], al
0x18000cea1  call    cs:__imp_RtlInitUnicodeString
0x18000cea7  cmp     cs:LsaLookupClientSidCacheEnabled, bl
0x18000cead  mov     esi, 1
0x18000ceb2  jnz     loc_18000D0CC
0x18000ceb8  lea     rax, [rbp+40h+var_60]
0x18000cebc  mov     dword ptr [rbp+40h+var_60], 0Ch
0x18000cec3  lea     r8, [rsp+140h+PolicyHandle]; PolicyHandle
0x18000cec8  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x18000cecc  mov     edx, 800h; AccessMask
0x18000ced1  mov     dword ptr [rbp+40h+var_60+4], 2
0x18000ced8  lea     rcx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18000cedc  mov     word ptr [rbp+40h+var_58], si
0x18000cee0  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18000cee7  mov     [rbp+40h+ObjectAttributes.RootDirectory], rbx
0x18000ceeb  mov     [rbp+40h+ObjectAttributes.Attributes], ebx
0x18000ceee  mov     [rbp+40h+ObjectAttributes.ObjectName], rbx
0x18000cef2  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rbx
0x18000cef6  call    LsaLookupOpenLocalPolicy
0x18000cefb  test    eax, eax
0x18000cefd  js      loc_18000D113
0x18000cf03  mov     rcx, [rsp+140h+PolicyHandle]
0x18000cf08  lea     rax, [rsp+140h+var_E0]
0x18000cf0d  mov     [rsp+140h+var_108], rax
0x18000cf12  lea     r9, [rbp+40h+DestinationString]
0x18000cf16  lea     rax, [rsp+140h+hMem]
0x18000cf1b  mov     [rsp+140h+var_E0], ebx
0x18000cf1f  mov     [rsp+140h+var_118], rax
0x18000cf24  mov     r8d, esi
0x18000cf27  lea     rax, [rsp+140h+var_F8]
0x18000cf2c  mov     [rsp+140h+var_F8], rbx
0x18000cf31  xor     edx, edx
0x18000cf33  mov     [rsp+140h+var_120], rax
0x18000cf38  mov     [rsp+140h+hMem], rbx
0x18000cf3d  call    LsaInternalClientLookupNames
0x18000cf42  mov     rcx, [rsp+140h+PolicyHandle]; ObjectHandle
0x18000cf47  mov     ebx, eax
0x18000cf49  call    LsaLookupClose
0x18000cf4e  cmp     cs:LsaLookupClientSidCacheEnabled, 0
0x18000cf55  jnz     loc_18000D121
0x18000cf5b  test    ebx, ebx
0x18000cf5d  js      loc_18000D010
0x18000cf63  mov     rbx, [rsp+140h+hMem]
0x18000cf68  cmp     [rbp+40h+arg_30], 0
0x18000cf6f  movsxd  rax, dword ptr [rbx+10h]
0x18000cf73  lea     rdx, [rax+rax*2]
0x18000cf77  mov     rax, [rsp+140h+var_F8]
0x18000cf7c  mov     rcx, [rax+8]
0x18000cf80  jz      loc_18000D0B2
0x18000cf86  movzx   eax, word ptr [rcx+rdx*8]
0x18000cf8a  shr     eax, 1
0x18000cf8c  mov     [rsp+140h+BytesInMultiByteString], eax
0x18000cf90  mov     rcx, [rbx+8]; Sid
0x18000cf94  call    cs:__imp_RtlLengthSid
0x18000cf9a  mov     r9d, [r14]
0x18000cf9d  mov     r8d, [rsp+140h+BytesInMultiByteString]
0x18000cfa2  cmp     eax, r9d
0x18000cfa5  jbe     loc_18000D030
0x18000cfab  mov     [r14], eax
0x18000cfae  mov     ecx, 0C0000023h; Status
0x18000cfb3  lea     eax, [r8+1]
0x18000cfb7  mov     [r15], eax
0x18000cfba  call    cs:__imp_RtlNtStatusToDosError
0x18000cfc0  mov     ecx, eax; dwErrCode
0x18000cfc2  call    cs:__imp_SetLastError
0x18000cfc8  xor     esi, esi
0x18000cfca  cmp     cs:LsaLookupClientSidCacheEnabled, 0
0x18000cfd1  jnz     loc_18000D181
0x18000cfd7  mov     rcx, [rsp+140h+var_F8]; hMem
0x18000cfdc  test    rcx, rcx
0x18000cfdf  jnz     loc_18000D1B5
0x18000cfe5  mov     rcx, rbx; hMem
0x18000cfe8  call    cs:__imp_LocalFree
0x18000cfee  mov     eax, esi
0x18000cff0  mov     rcx, [rbp+40h+var_50]
0x18000cff4  xor     rcx, rsp; StackCookie
0x18000cff7  call    __security_check_cookie
0x18000cffc  add     rsp, 108h
0x18000d003  pop     r15
0x18000d005  pop     r14
0x18000d007  pop     r13
0x18000d009  pop     r12
0x18000d00b  pop     rdi
0x18000d00c  pop     rsi
0x18000d00d  pop     rbx
0x18000d00e  pop     rbp
0x18000d00f  retn
0x18000d010  cmp     ebx, 0C0000073h
0x18000d016  jz      loc_18000D158
0x18000d01c  mov     ecx, ebx; Status
0x18000d01e  call    cs:__imp_RtlNtStatusToDosError
0x18000d024  mov     ecx, eax; dwErrCode
0x18000d026  call    cs:__imp_SetLastError
0x18000d02c  xor     eax, eax
0x18000d02e  jmp     short loc_18000CFF0
0x18000d030  lea     ecx, [r8+1]
0x18000d034  cmp     ecx, [r15]
0x18000d037  ja      loc_18000CFAB
0x18000d03d  mov     r8, [rbx+8]; SourceSid
0x18000d041  mov     rdx, r12; DestinationSid
0x18000d044  mov     ecx, r9d; DestinationSidLength
0x18000d047  call    cs:__imp_RtlCopySid
0x18000d04d  xor     eax, eax
0x18000d04f  mov     [rsp+140h+var_D8.Buffer], r13
0x18000d054  mov     [rsp+140h+var_D8.Length], ax
0x18000d059  mov     eax, [r15]
0x18000d05c  cmp     eax, 7FFFh
0x18000d061  jnb     loc_18000D109
0x18000d067  add     ax, ax
0x18000d06a  mov     [rsp+140h+var_D8.MaximumLength], ax
0x18000d06f  movsxd  rax, dword ptr [rbx+10h]
0x18000d073  lea     rdx, [rax+rax*2]
0x18000d077  mov     rax, [rsp+140h+var_F8]
0x18000d07c  mov     rcx, [rax+8]
0x18000d080  lea     rdx, [rcx+rdx*8]; SourceString
0x18000d084  lea     rcx, [rsp+140h+var_D8]; DestinationString
0x18000d089  call    cs:__imp_RtlCopyUnicodeString
0x18000d08f  movzx   edx, [rsp+140h+var_D8.Length]
0x18000d094  mov     rax, [rsp+140h+var_D8.Buffer]
0x18000d099  shr     rdx, 1
0x18000d09c  xor     ecx, ecx
0x18000d09e  mov     [rax+rdx*2], cx
0x18000d0a2  mov     eax, [rbx]
0x18000d0a4  mov     [rdi], eax
0x18000d0a6  mov     eax, [rsp+140h+BytesInMultiByteString]
0x18000d0aa  mov     [r15], eax
0x18000d0ad  jmp     loc_18000CFCA
0x18000d0b2  movzx   r8d, word ptr [rcx+rdx*8]; BytesInUnicodeString
0x18000d0b7  mov     rdx, [rcx+rdx*8+8]; UnicodeString
0x18000d0bc  lea     rcx, [rsp+140h+BytesInMultiByteString]; BytesInMultiByteString
0x18000d0c1  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18000d0c7  jmp     loc_18000CF90
0x18000d0cc  lea     rax, [rsp+140h+var_100]
0x18000d0d1  mov     [rsp+140h+var_110], rax
0x18000d0d6  lea     r9, [rsp+140h+hMem]
0x18000d0db  lea     rax, [rsp+140h+var_E0]
0x18000d0e0  mov     [rsp+140h+var_118], rax
0x18000d0e5  lea     r8, [rsp+140h+var_F8]
0x18000d0ea  lea     rax, [rbp+40h+var_A0]
0x18000d0ee  lea     rdx, [rbp+40h+DestinationString]
0x18000d0f2  mov     [rsp+140h+var_120], rax
0x18000d0f7  call    LsaLookupClientFindTranslationsByNameInCache
0x18000d0fc  test    eax, eax
0x18000d0fe  js      loc_18000CEB8
0x18000d104  jmp     loc_18000CF63
0x18000d109  mov     eax, 0FFFEh
0x18000d10e  jmp     loc_18000D06A
0x18000d113  mov     ecx, eax
0x18000d115  call    BaseSetLastNTError
0x18000d11a  xor     eax, eax
0x18000d11c  jmp     loc_18000CFF0
0x18000d121  test    ebx, ebx
0x18000d123  js      loc_18000D010
0x18000d129  movaps  xmm0, xmmword ptr [rbp+40h+DestinationString.Length]
0x18000d12d  lea     r8, [rbp+40h+var_A0]
0x18000d131  mov     rax, [rsp+140h+var_F8]
0x18000d136  mov     rbx, [rsp+140h+hMem]
0x18000d13b  mov     edx, [rbp+40h+arg_30]
0x18000d141  mov     r9, rbx
0x18000d144  movdqa  [rbp+40h+var_A0], xmm0
0x18000d149  mov     [rsp+140h+var_120], rax
0x18000d14e  call    LsaLookupClientUpdateCacheUsingNames
0x18000d153  jmp     loc_18000CF68
0x18000d158  mov     rcx, [rsp+140h+var_F8]; hMem
0x18000d15d  test    rcx, rcx
0x18000d160  jz      short loc_18000D168
0x18000d162  call    cs:__imp_LocalFree
0x18000d168  mov     rcx, [rsp+140h+hMem]; hMem
0x18000d16d  test    rcx, rcx
0x18000d170  jz      loc_18000D01C
0x18000d176  call    cs:__imp_LocalFree
0x18000d17c  jmp     loc_18000D01C
0x18000d181  cmp     [rsp+140h+var_100], 0
0x18000d186  jz      loc_18000CFD7
0x18000d18c  mov     rcx, [rsp+140h+var_F8]
0x18000d191  test    rcx, rcx
0x18000d194  jz      loc_18000CFEE
0x18000d19a  mov     ecx, [rcx]
0x18000d19c  lea     rdx, [rsp+140h+hMem]
0x18000d1a1  call    LsaLookupClientFreeTranslatedSids
0x18000d1a6  lea     rcx, [rsp+140h+var_F8]
0x18000d1ab  call    LsaLookupClientFreeReferencedDomains
0x18000d1b0  jmp     loc_18000CFEE
0x18000d1b5  call    cs:__imp_LocalFree
0x18000d1bb  jmp     loc_18000CFE5
```
