# Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,HKEY__ *)

- ea: `0x14002c15c`
- end: `0x14002c364`
- name: `?KeyPathFromHKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(void **, char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1400293cc`
- `0x14002d660`

## callees

- `0x1400025f8`
- `0x14001008c`
- `0x140020f9c`
- `0x14002c15c`
- `0x14002e3e2`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002c17c`
- `KERNEL32!GetLastError` at `0x14002c2d7`
- `KERNEL32!GetLastError` at `0x14002c17c`
- `KERNEL32!GetLastError` at `0x14002c2d7`
- `KERNEL32!GetProcessHeap` at `0x14002c184`
- `KERNEL32!GetProcessHeap` at `0x14002c2df`
- `KERNEL32!GetProcessHeap` at `0x14002c30c`
- `KERNEL32!GetProcessHeap` at `0x14002c184`
- `KERNEL32!GetProcessHeap` at `0x14002c2df`
- `KERNEL32!GetProcessHeap` at `0x14002c30c`
- `KERNEL32!SetLastError` at `0x14002c19a`
- `KERNEL32!SetLastError` at `0x14002c2f5`
- `KERNEL32!SetLastError` at `0x14002c19a`
- `KERNEL32!SetLastError` at `0x14002c2f5`
- `KERNEL32!HeapFree` at `0x14002c192`
- `KERNEL32!HeapFree` at `0x14002c2ed`
- `KERNEL32!HeapFree` at `0x14002c31a`
- `KERNEL32!HeapFree` at `0x14002c192`
- `KERNEL32!HeapFree` at `0x14002c2ed`
- `KERNEL32!HeapFree` at `0x14002c31a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002c335`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002c342`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002c335`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002c342`
- `ntdll!RtlNtStatusToDosError` at `0x14002c1de`
- `ntdll!RtlNtStatusToDosError` at `0x14002c279`
- `ntdll!RtlNtStatusToDosError` at `0x14002c1de`
- `ntdll!RtlNtStatusToDosError` at `0x14002c279`
- `ntdll!NtQueryKey` at `0x14002c1d4`
- `ntdll!NtQueryKey` at `0x14002c26f`
- `ntdll!NtQueryKey` at `0x14002c1d4`
- `ntdll!NtQueryKey` at `0x14002c26f`

## string_xrefs

- `0x14002c200`: `Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey`
- `0x14002c296`: `Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(void **a1, char *a2)
{
  void *v4; // rdi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  int v7; // ebx
  ULONG v8; // eax
  ULONG v9; // edi
  ULONG v11; // r14d
  char *v12; // rax
  char *v13; // rdi
  int v14; // ebx
  ULONG v15; // eax
  const char *v16; // r9
  unsigned int v17; // ebp
  void *v18; // r14
  void *v19; // rbp
  DWORD v20; // ebx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  _QWORD v24[5]; // [rsp+30h] [rbp-28h] BYREF
  ULONG Length; // [rsp+60h] [rbp+8h] BYREF
  char *v26; // [rsp+68h] [rbp+10h]

  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    SetLastError(LastError);
  }
  *a1 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 87;
  Length = 0;
  v7 = NtQueryKey(a2, KeyNameInformation, 0, 0, &Length);
  v8 = RtlNtStatusToDosError(v7);
  v9 = v8;
  if ( v7 < 0 && v8 != 122 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey",
      538,
      "NtQueryKey failed to query size for KeyNameInformation (%d)",
      v8);
    return v9;
  }
  v11 = Length;
  v12 = (char *)operator new[](Length, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
    memset_0(v12, 0, v11);
  else
    v13 = 0;
  v26 = v13;
  if ( !v13 )
    return 14;
  v14 = NtQueryKey(a2, KeyNameInformation, v13, v11, &Length);
  v15 = RtlNtStatusToDosError(v14);
  v17 = v15;
  if ( v14 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey",
      555,
      "NtQueryKey failed to query for KeyNameInformation (%d)",
      v15);
LABEL_23:
    operator delete[](v13);
    return v17;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v24,
    v13 + 4,
    (unsigned __int64)*(unsigned int *)v13 >> 1,
    v16);
  if ( a1 == v24 )
  {
    v22 = (void *)v24[0];
  }
  else
  {
    v18 = (void *)v24[0];
    v19 = *a1;
    if ( *a1 )
    {
      v20 = GetLastError();
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v19);
      SetLastError(v20);
    }
    *a1 = v18;
    v22 = 0;
  }
  if ( v22 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  if ( !*a1 )
  {
    *a1 = 0;
    v17 = 14;
    goto LABEL_23;
  }
  operator delete[](v13);
  return 0;
}

```

## disassembly

```asm
0x14002c15c  mov     [rsp+arg_10], rbx
0x14002c161  mov     [rsp+arg_18], rbp
0x14002c166  push    rsi
0x14002c167  push    rdi
0x14002c168  push    r14
0x14002c16a  sub     rsp, 40h
0x14002c16e  mov     rbp, rdx
0x14002c171  mov     rsi, rcx
0x14002c174  mov     rdi, [rcx]
0x14002c177  test    rdi, rdi
0x14002c17a  jz      short loc_14002C1A0
0x14002c17c  call    cs:__imp_GetLastError
0x14002c182  mov     ebx, eax
0x14002c184  call    cs:__imp_GetProcessHeap
0x14002c18a  mov     rcx, rax; hHeap
0x14002c18d  mov     r8, rdi; lpMem
0x14002c190  xor     edx, edx; dwFlags
0x14002c192  call    cs:__imp_HeapFree
0x14002c198  mov     ecx, ebx; dwErrCode
0x14002c19a  call    cs:__imp_SetLastError
0x14002c1a0  mov     qword ptr [rsi], 0
0x14002c1a7  lea     rax, [rbp-1]
0x14002c1ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c1af  ja      loc_14002C34C
0x14002c1b5  mov     [rsp+58h+Length], 0
0x14002c1bd  lea     rax, [rsp+58h+Length]
0x14002c1c2  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14002c1c7  xor     r9d, r9d; Length
0x14002c1ca  xor     r8d, r8d; KeyInformation
0x14002c1cd  lea     edx, [r9+3]; KeyInformationClass
0x14002c1d1  mov     rcx, rbp; KeyHandle
0x14002c1d4  call    cs:__imp_NtQueryKey
0x14002c1da  mov     ebx, eax
0x14002c1dc  mov     ecx, eax; Status
0x14002c1de  call    cs:__imp_RtlNtStatusToDosError
0x14002c1e4  mov     edi, eax
0x14002c1e6  test    ebx, ebx
0x14002c1e8  jns     short loc_14002C218
0x14002c1ea  cmp     eax, 7Ah ; 'z'
0x14002c1ed  jz      short loc_14002C218
0x14002c1ef  mov     dword ptr [rsp+58h+ResultLength], eax
0x14002c1f3  lea     r9, aNtquerykeyFail_0; "NtQueryKey failed to query size for Key"...
0x14002c1fa  mov     r8d, 21Ah
0x14002c200  lea     rdx, aPcaMergesdbUti_13; "Pca::MergeSdb::Utils::RegUtil::KeyPathF"...
0x14002c207  mov     ecx, 1
0x14002c20c  call    AslLogCallPrintf
0x14002c211  mov     eax, edi
0x14002c213  jmp     loc_14002C351
0x14002c218  mov     r14d, [rsp+58h+Length]
0x14002c21d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002c224  mov     ecx, r14d; unsigned __int64
0x14002c227  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002c22c  mov     rdi, rax
0x14002c22f  test    rax, rax
0x14002c232  jz      short loc_14002C243
0x14002c234  mov     r8d, r14d; Size
0x14002c237  xor     edx, edx; Val
0x14002c239  mov     rcx, rax; void *
0x14002c23c  call    memset_0
0x14002c241  jmp     short loc_14002C245
0x14002c243  xor     edi, edi
0x14002c245  mov     [rsp+58h+arg_8], rdi
0x14002c24a  test    rdi, rdi
0x14002c24d  jnz     short loc_14002C257
0x14002c24f  lea     eax, [rdi+0Eh]
0x14002c252  jmp     loc_14002C351
0x14002c257  lea     rax, [rsp+58h+Length]
0x14002c25c  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14002c261  mov     r9d, r14d; Length
0x14002c264  mov     r8, rdi; KeyInformation
0x14002c267  mov     edx, 3; KeyInformationClass
0x14002c26c  mov     rcx, rbp; KeyHandle
0x14002c26f  call    cs:__imp_NtQueryKey
0x14002c275  mov     ebx, eax
0x14002c277  mov     ecx, eax; Status
0x14002c279  call    cs:__imp_RtlNtStatusToDosError
0x14002c27f  mov     ebp, eax
0x14002c281  test    ebx, ebx
0x14002c283  jns     short loc_14002C2AC
0x14002c285  mov     dword ptr [rsp+58h+ResultLength], eax
0x14002c289  lea     r9, aNtquerykeyFail; "NtQueryKey failed to query for KeyNameI"...
0x14002c290  mov     r8d, 22Bh
0x14002c296  lea     rdx, aPcaMergesdbUti_13; "Pca::MergeSdb::Utils::RegUtil::KeyPathF"...
0x14002c29d  mov     ecx, 1
0x14002c2a2  call    AslLogCallPrintf
0x14002c2a7  jmp     loc_14002C332
0x14002c2ac  mov     r8d, [rdi]
0x14002c2af  shr     r8, 1
0x14002c2b2  lea     rdx, [rdi+4]
0x14002c2b6  lea     rcx, [rsp+58h+var_28]
0x14002c2bb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002c2c0  lea     rax, [rsp+58h+var_28]
0x14002c2c5  cmp     rsi, rax
0x14002c2c8  jz      short loc_14002C302
0x14002c2ca  mov     r14, [rsp+58h+var_28]
0x14002c2cf  mov     rbp, [rsi]
0x14002c2d2  test    rbp, rbp
0x14002c2d5  jz      short loc_14002C2FB
0x14002c2d7  call    cs:__imp_GetLastError
0x14002c2dd  mov     ebx, eax
0x14002c2df  call    cs:__imp_GetProcessHeap
0x14002c2e5  mov     rcx, rax; hHeap
0x14002c2e8  mov     r8, rbp; lpMem
0x14002c2eb  xor     edx, edx; dwFlags
0x14002c2ed  call    cs:__imp_HeapFree
0x14002c2f3  mov     ecx, ebx; dwErrCode
0x14002c2f5  call    cs:__imp_SetLastError
0x14002c2fb  mov     [rsi], r14
0x14002c2fe  xor     ebx, ebx
0x14002c300  jmp     short loc_14002C307
0x14002c302  mov     rbx, [rsp+58h+var_28]
0x14002c307  test    rbx, rbx
0x14002c30a  jz      short loc_14002C320
0x14002c30c  call    cs:__imp_GetProcessHeap
0x14002c312  mov     rcx, rax; hHeap
0x14002c315  mov     r8, rbx; lpMem
0x14002c318  xor     edx, edx; dwFlags
0x14002c31a  call    cs:__imp_HeapFree
0x14002c320  cmp     qword ptr [rsi], 0
0x14002c324  jnz     short loc_14002C33F
0x14002c326  mov     qword ptr [rsi], 0
0x14002c32d  mov     ebp, 0Eh
0x14002c332  mov     rcx, rdi
0x14002c335  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002c33b  mov     eax, ebp
0x14002c33d  jmp     short loc_14002C351
0x14002c33f  mov     rcx, rdi
0x14002c342  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002c348  xor     eax, eax
0x14002c34a  jmp     short loc_14002C351
0x14002c34c  mov     eax, 57h ; 'W'
0x14002c351  mov     rbx, [rsp+58h+arg_10]
0x14002c356  mov     rbp, [rsp+58h+arg_18]
0x14002c35b  add     rsp, 40h
0x14002c35f  pop     r14
0x14002c361  pop     rdi
0x14002c362  pop     rsi
0x14002c363  retn
```
