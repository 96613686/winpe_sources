# _SetSecurityOnFileOrFolder(ushort const *,ushort const *,SYSTEM_DATA_FOLDER_USER_ACCESS,SYSTEM_DATA_FOLDER_FLAGS)

- ea: `0x180006490`
- end: `0x18000678e`
- name: `?_SetSecurityOnFileOrFolder@@YAJPEBG0W4SYSTEM_DATA_FOLDER_USER_ACCESS@@W4SYSTEM_DATA_FOLDER_FLAGS@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(const WCHAR *, const wchar_t *, int, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004b78`
- `0x1800053a0`

## callees

- `0x180006490`
- `0x180006794`
- `0x18000da00`
- `0x18003d244`
- `0x180054130`
- `0x180054ad4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006629`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000671b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006629`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000671b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006556`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006674`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006556`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006674`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800065ca`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800065ca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000660e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000660e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800066bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800065a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800065a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800066a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800066a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _SetSecurityOnFileOrFolder(const WCHAR *a1, const wchar_t *a2, int a3, char a4)
{
  const wchar_t *v5; // rdx
  WCHAR *v6; // r8
  __int64 v7; // rax
  __int64 v8; // r10
  WCHAR *v9; // rcx
  unsigned int Error; // ebx
  __int64 result; // rax
  void *v12; // rax
  void *v13; // rdi
  bool v14; // si
  size_t v15; // rax
  bool v16; // zf
  const wchar_t *v17; // r9
  DWORD nLengthNeeded[2]; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR v19; // [rsp+38h] [rbp-260h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-258h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+60h] [rbp-238h] BYREF

  if ( a3 )
  {
    v16 = (a4 & 1) == 0;
    v17 = L"BU";
    if ( v16 )
      v17 = a2;
    Error = StringCchPrintfW(StringSecurityDescriptor, 0x104u, (&off_1800EE010)[3 * a3], v17);
  }
  else
  {
    v5 = L"O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;FA;;;SY)";
    v6 = StringSecurityDescriptor;
    v7 = 2147483646;
    v8 = 260;
    do
    {
      if ( !v7 )
        break;
      if ( !*v5 )
        break;
      *v6++ = *v5++;
      --v7;
      --v8;
    }
    while ( v8 );
    v9 = v6 - 1;
    Error = -2147024774;
    if ( v8 )
    {
      v9 = v6;
      Error = 0;
    }
    *v9 = 0;
  }
  if ( (Error & 0x80000000) != 0 )
    return Error;
  nLengthNeeded[0] = 0;
  if ( !GetFileSecurityW(a1, 7u, 0, 0, nLengthNeeded) && (unsigned int)ResultFromKnownLastError() == -2147024774 )
  {
    v12 = CoTaskMemAlloc(nLengthNeeded[0]);
    v13 = v12;
    if ( v12 )
    {
      v14 = 0;
      v15 = CTCoAllocPolicy::_CoTaskMemSize(v12);
      memset_0(v13, 0, v15);
      if ( GetFileSecurityW(a1, 7u, v13, nLengthNeeded[0], nLengthNeeded) )
      {
        v19 = 0;
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v13, 1u, 7u, &v19, 0) )
        {
          v14 = CompareStringOrdinal(v19, -1, StringSecurityDescriptor, -1, 1) == 2;
          LocalFree(v19);
        }
      }
      CoTaskMemFree(v13);
      if ( v14 )
        return Error;
    }
  }
  *(_QWORD *)nLengthNeeded = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         (PSECURITY_DESCRIPTOR *)nLengthNeeded,
         0)
    || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    if ( SetFileSecurityW(a1, 7u, *(PSECURITY_DESCRIPTOR *)nLengthNeeded) )
      goto LABEL_18;
    Error = ResultFromKnownLastError();
    if ( Error != -2147024894 )
    {
      if ( Error == -2147024891 )
        Error = 0;
      goto LABEL_19;
    }
    SecurityAttributes.lpSecurityDescriptor = *(LPVOID *)nLengthNeeded;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    if ( CreateDirectoryW(a1, &SecurityAttributes) )
LABEL_18:
      Error = 0;
    else
      Error = ResultFromKnownLastError();
LABEL_19:
    LocalFree(*(HLOCAL *)nLengthNeeded);
    return Error;
  }
  return result;
}

```

## disassembly

```asm
0x180006490  push    rbx
0x180006492  push    rbp
0x180006493  sub     rsp, 288h
0x18000649a  mov     rax, cs:__security_cookie
0x1800064a1  xor     rax, rsp
0x1800064a4  mov     [rsp+298h+var_28], rax
0x1800064ac  mov     rbp, rcx
0x1800064af  test    r8d, r8d
0x1800064b2  jnz     loc_180006729
0x1800064b8  mov     rdx, cs:off_1800EE010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x1800064bf  lea     r8, [rsp+298h+StringSecurityDescriptor]
0x1800064c4  mov     eax, 7FFFFFFEh
0x1800064c9  mov     r10d, 104h
0x1800064cf  nop
0x1800064d0  test    rax, rax
0x1800064d3  jz      short loc_1800064F2
0x1800064d5  movzx   ecx, word ptr [rdx]
0x1800064d8  test    cx, cx
0x1800064db  jz      short loc_1800064F2
0x1800064dd  mov     [r8], cx
0x1800064e1  add     rdx, 2
0x1800064e5  add     r8, 2
0x1800064e9  dec     rax
0x1800064ec  sub     r10, 1
0x1800064f0  jnz     short loc_1800064D0
0x1800064f2  test    r10, r10
0x1800064f5  lea     rcx, [r8-2]
0x1800064f9  mov     ebx, 8007007Ah
0x1800064fe  cmovnz  rcx, r8
0x180006502  xor     eax, eax
0x180006504  test    r10, r10
0x180006507  cmovnz  ebx, eax
0x18000650a  mov     [rcx], ax
0x18000650d  test    ebx, ebx
0x18000650f  jns     short loc_18000652E
0x180006511  mov     eax, ebx
0x180006513  mov     rcx, [rsp+298h+var_28]
0x18000651b  xor     rcx, rsp; StackCookie
0x18000651e  call    __security_check_cookie
0x180006523  add     rsp, 288h
0x18000652a  pop     rbp
0x18000652b  pop     rbx
0x18000652c  retn
0x18000652e  lea     rax, [rsp+298h+nLengthNeeded]
0x180006533  mov     [rsp+298h+var_18], rdi
0x18000653b  xor     r9d, r9d; nLength
0x18000653e  mov     [rsp+298h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180006543  xor     r8d, r8d; pSecurityDescriptor
0x180006546  mov     [rsp+298h+nLengthNeeded], 0
0x18000654e  mov     edx, 7; RequestedInformation
0x180006553  mov     rcx, rbp; lpFileName
0x180006556  call    cs:__imp_GetFileSecurityW
0x18000655d  nop     dword ptr [rax+rax+00h]
0x180006562  test    eax, eax
0x180006564  jnz     short loc_18000658E
0x180006566  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000656b  cmp     eax, 8007007Ah
0x180006570  jnz     short loc_18000658E
0x180006572  mov     ecx, [rsp+298h+nLengthNeeded]; cb
0x180006576  call    cs:__imp_CoTaskMemAlloc
0x18000657d  nop     dword ptr [rax+rax+00h]
0x180006582  mov     rdi, rax
0x180006585  test    rax, rax
0x180006588  jnz     loc_18000663A
0x18000658e  xor     r9d, r9d; SecurityDescriptorSize
0x180006591  mov     qword ptr [rsp+298h+nLengthNeeded], 0
0x18000659a  lea     r8, [rsp+298h+nLengthNeeded]; SecurityDescriptor
0x18000659f  mov     edx, 1; StringSDRevision
0x1800065a4  lea     rcx, [rsp+298h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800065a9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800065b0  nop     dword ptr [rax+rax+00h]
0x1800065b5  test    eax, eax
0x1800065b7  jz      loc_180006760
0x1800065bd  mov     r8, qword ptr [rsp+298h+nLengthNeeded]; pSecurityDescriptor
0x1800065c2  mov     edx, 7; SecurityInformation
0x1800065c7  mov     rcx, rbp; lpFileName
0x1800065ca  call    cs:__imp_SetFileSecurityW
0x1800065d1  nop     dword ptr [rax+rax+00h]
0x1800065d6  test    eax, eax
0x1800065d8  jnz     short loc_180006622
0x1800065da  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800065df  mov     ebx, eax
0x1800065e1  cmp     eax, 80070002h
0x1800065e6  jnz     loc_18000677E
0x1800065ec  mov     rax, qword ptr [rsp+298h+nLengthNeeded]
0x1800065f1  lea     rdx, [rsp+298h+SecurityAttributes]; lpSecurityAttributes
0x1800065f6  mov     [rsp+298h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800065fb  mov     rcx, rbp; lpPathName
0x1800065fe  xor     eax, eax
0x180006600  mov     qword ptr [rsp+298h+SecurityAttributes.nLength], 18h
0x180006609  mov     qword ptr [rsp+298h+SecurityAttributes.bInheritHandle], rax
0x18000660e  call    cs:__imp_CreateDirectoryW
0x180006615  nop     dword ptr [rax+rax+00h]
0x18000661a  test    eax, eax
0x18000661c  jz      loc_180006772
0x180006622  xor     ebx, ebx
0x180006624  mov     rcx, qword ptr [rsp+298h+nLengthNeeded]; hMem
0x180006629  call    cs:__imp_LocalFree
0x180006630  nop     dword ptr [rax+rax+00h]
0x180006635  jmp     loc_1800066D9
0x18000663a  mov     [rsp+298h+arg_10], rsi
0x180006642  mov     rcx, rdi; void *
0x180006645  xor     sil, sil
0x180006648  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000664d  mov     r8, rax; Size
0x180006650  xor     edx, edx; Val
0x180006652  mov     rcx, rdi; void *
0x180006655  call    memset_0
0x18000665a  mov     r9d, [rsp+298h+nLengthNeeded]; nLength
0x18000665f  lea     rax, [rsp+298h+nLengthNeeded]
0x180006664  mov     r8, rdi; pSecurityDescriptor
0x180006667  mov     [rsp+298h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000666c  mov     edx, 7; RequestedInformation
0x180006671  mov     rcx, rbp; lpFileName
0x180006674  call    cs:__imp_GetFileSecurityW
0x18000667b  nop     dword ptr [rax+rax+00h]
0x180006680  test    eax, eax
0x180006682  jz      short loc_1800066B9
0x180006684  lea     r9, [rsp+298h+var_260]; StringSecurityDescriptor
0x180006689  mov     [rsp+298h+var_260], 0
0x180006692  mov     edx, 1; RequestedStringSDRevision
0x180006697  mov     [rsp+298h+lpnLengthNeeded], 0; StringSecurityDescriptorLen
0x1800066a0  mov     r8d, 7; SecurityInformation
0x1800066a6  mov     rcx, rdi; SecurityDescriptor
0x1800066a9  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800066b0  nop     dword ptr [rax+rax+00h]
0x1800066b5  test    eax, eax
0x1800066b7  jnz     short loc_1800066E8
0x1800066b9  mov     rcx, rdi; pv
0x1800066bc  call    cs:__imp_CoTaskMemFree
0x1800066c3  nop     dword ptr [rax+rax+00h]
0x1800066c8  test    sil, sil
0x1800066cb  mov     rsi, [rsp+298h+arg_10]
0x1800066d3  jz      loc_18000658E
0x1800066d9  mov     eax, ebx
0x1800066db  mov     rdi, [rsp+298h+var_18]
0x1800066e3  jmp     loc_180006513
0x1800066e8  mov     rcx, [rsp+298h+var_260]; lpString1
0x1800066ed  lea     r8, [rsp+298h+StringSecurityDescriptor]; lpString2
0x1800066f2  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800066f8  mov     dword ptr [rsp+298h+lpnLengthNeeded], 1; bIgnoreCase
0x180006700  mov     edx, r9d; cchCount1
0x180006703  call    cs:__imp_CompareStringOrdinal
0x18000670a  nop     dword ptr [rax+rax+00h]
0x18000670f  mov     rcx, [rsp+298h+var_260]; hMem
0x180006714  cmp     eax, 2
0x180006717  setz    sil
0x18000671b  call    cs:__imp_LocalFree
0x180006722  nop     dword ptr [rax+rax+00h]
0x180006727  jmp     short loc_1800066B9
0x180006729  movsxd  rax, r8d
0x18000672c  lea     rcx, [rsp+298h+StringSecurityDescriptor]; unsigned __int16 *
0x180006731  test    r9b, 1
0x180006735  lea     r9, aBu; "BU"
0x18000673c  cmovz   r9, rdx
0x180006740  mov     edx, 104h; unsigned __int64
0x180006745  lea     r8, [rax+rax*2]
0x180006749  lea     rax, off_1800EE010; "O:SYG:SYD:P(A;;FA;;;S-1-5-80-956008885-"...
0x180006750  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180006754  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006759  mov     ebx, eax
0x18000675b  jmp     loc_18000650D
0x180006760  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006765  test    eax, eax
0x180006767  js      loc_1800066DB
0x18000676d  jmp     loc_1800065BD
0x180006772  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006777  mov     ebx, eax
0x180006779  jmp     loc_180006624
0x18000677e  xor     ecx, ecx
0x180006780  cmp     ebx, 80070005h
0x180006786  cmovz   ebx, ecx
0x180006789  jmp     loc_180006624
```
