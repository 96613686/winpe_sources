# ComputeService::ContainerUtilities::RemoveMappedDirectory(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1400da39c`
- end: `0x1400da6e2`
- name: `?RemoveMappedDirectory@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1_N@Z`
- size: `838`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14008b7f0`
- `0x1400a0cdc`
- `0x1400a0ed0`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x14002dd18`
- `0x140042b50`
- `0x14004346c`
- `0x1400438dc`
- `0x140043c2c`
- `0x140044adc`
- `0x1400d4de0`
- `0x1400da178`
- `0x1400da39c`
- `0x1400eb68c`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x1400da602`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400da602`
- `ntdll!NtMakeTemporaryObject` at `0x1400da618`
- `ntdll!NtMakeTemporaryObject` at `0x1400da618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400da638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400da638`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400da583`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400da583`

## string_xrefs

- `0x1400da694`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da6a6`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da6bb`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da6d0`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::ContainerUtilities::RemoveMappedDirectory(
        __int64 a1,
        __int64 a2,
        struct _GUID *a3,
        char a4)
{
  struct _GUID *v5; // rbx
  ComputeService::Storage *v7; // rcx
  __int64 v8; // rax
  struct _GUID *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rcx
  const char *v15; // r9
  __int128 *p_Src; // rax
  NTSTATUS v17; // eax
  NTSTATUS TemporaryObject; // eax
  __int64 v19; // rdx
  LPCWSTR *v20; // r8
  int v21; // eax
  int v22[8]; // [rsp+20h] [rbp-A9h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-89h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-69h] BYREF
  void *SymbolicLinkHandle[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 Src; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-19h]
  unsigned __int64 v28; // [rsp+B8h] [rbp-11h]
  LPCWSTR lpPathName[2]; // [rsp+C0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+D0h] [rbp+7h]
  __int128 v31; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v5 = a3;
  *(_OWORD *)lpPathName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpPathName[0]) = 0;
  if ( *(_QWORD *)a3[1].Data4 <= 7u )
    v7 = (ComputeService::Storage *)a3;
  else
    v7 = *(ComputeService::Storage **)&a3->Data1;
  if ( ComputeService::Storage::IsDriveLetter(v7, 0, (char *)a3) )
  {
    Src = 0;
    v27 = 0;
    v28 = 7;
    LOWORD(Src) = 0;
    if ( a4 )
    {
      if ( *(_QWORD *)v5[1].Data4 <= 7u )
        v9 = v5;
      else
        v9 = *(struct _GUID **)&v5->Data1;
      v10 = ComputeService::Storage::ResolveDirectoryPath(v22, v9);
      std::wstring::operator=(lpPathName, v10);
      std::wstring::~wstring(v22);
      v11 = Vml::FormatString(v22, (wchar_t *)L"\\GLOBAL??\\%s");
      std::wstring::operator=(&Src, v11);
    }
    else
    {
      ComputeService::ContainerUtilities::_anonymous_namespace_::GetHashPath(v23, v5);
      v12 = ComputeService::Storage::ConvertContainerPathToHostPath(v22);
      std::wstring::operator=(lpPathName, v12);
      std::wstring::~wstring(v22);
      std::wstring::~wstring(v23);
      ComputeService::ContainerUtilities::QueryContainerNamespacePath(v22);
      v13 = Vml::FormatString(v23, (wchar_t *)L"%s\\GLOBAL??\\%s");
      std::wstring::operator=(&Src, v13);
      std::wstring::~wstring(v23);
    }
    std::wstring::~wstring(v22);
    v14 = (const WCHAR *)lpPathName;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = lpPathName[0];
    if ( !RemoveDirectoryW(v14) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        v15);
    p_Src = &Src;
    if ( v28 > 7 )
      p_Src = (__int128 *)Src;
    HIWORD(SymbolicLinkHandle[0]) = 0;
    SymbolicLinkHandle[1] = p_Src;
    LOWORD(SymbolicLinkHandle[0]) = 2 * v27;
    *(_DWORD *)((char *)SymbolicLinkHandle + 2) = (unsigned __int16)(2 * v27);
    v31 = *(_OWORD *)SymbolicLinkHandle;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 16;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    SymbolicLinkHandle[0] = 0;
    v17 = NtOpenSymbolicLinkObject(SymbolicLinkHandle, 0x10000000u, &ObjectAttributes);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)v17,
        v22[0]);
    TemporaryObject = NtMakeTemporaryObject(SymbolicLinkHandle[0]);
    if ( TemporaryObject < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)TemporaryObject,
        v22[0]);
    if ( (unsigned __int64)SymbolicLinkHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(SymbolicLinkHandle[0]);
  }
  else
  {
    if ( a4 )
    {
      if ( *(_QWORD *)v5[1].Data4 > 7u )
        v5 = *(struct _GUID **)&v5->Data1;
      v8 = ComputeService::Storage::ResolveDirectoryPath(&Src, v5);
    }
    else
    {
      v8 = ComputeService::Storage::ConvertContainerPathToHostPath(&Src);
    }
    std::wstring::operator=(lpPathName, v8);
  }
  std::wstring::~wstring(&Src);
  v20 = lpPathName;
  if ( si128.m128i_i64[1] > 7uLL )
    v20 = (LPCWSTR *)lpPathName[0];
  v21 = BfRemoveMappingInternal(a1, v19, v20);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)v21,
      v22[0]);
  std::wstring::~wstring(lpPathName);
}

```

## disassembly

```asm
0x1400da39c  mov     [rsp-8+arg_18], rbx
0x1400da3a1  push    rbp
0x1400da3a2  push    rsi
0x1400da3a3  push    rdi
0x1400da3a4  push    r14
0x1400da3a6  push    r15
0x1400da3a8  lea     rbp, [rsp-37h]
0x1400da3ad  sub     rsp, 100h
0x1400da3b4  mov     rax, cs:__security_cookie
0x1400da3bb  xor     rax, rsp
0x1400da3be  mov     [rbp+57h+var_30], rax
0x1400da3c2  mov     sil, r9b
0x1400da3c5  mov     rbx, r8
0x1400da3c8  mov     rdi, rdx
0x1400da3cb  mov     r14, rcx
0x1400da3ce  xorps   xmm0, xmm0
0x1400da3d1  movups  xmmword ptr [rbp+57h+lpPathName], xmm0
0x1400da3d5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400da3dd  movdqu  [rbp+57h+var_50], xmm1
0x1400da3e2  xor     eax, eax
0x1400da3e4  mov     word ptr [rbp+57h+lpPathName], ax
0x1400da3e8  lea     r15d, [rax+7]
0x1400da3ec  cmp     [r8+18h], r15
0x1400da3f0  jbe     short loc_1400DA3F7
0x1400da3f2  mov     rcx, [r8]
0x1400da3f5  jmp     short loc_1400DA3FA
0x1400da3f7  mov     rcx, rbx; this
0x1400da3fa  xor     edx, edx; unsigned __int16 *
0x1400da3fc  call    ?IsDriveLetter@Storage@ComputeService@@YA_NPEBGPEAD@Z; ComputeService::Storage::IsDriveLetter(ushort const *,char *)
0x1400da401  test    al, al
0x1400da403  jnz     short loc_1400DA453
0x1400da405  test    sil, sil
0x1400da408  jz      short loc_1400DA430
0x1400da40a  cmp     [rbx+18h], r15
0x1400da40e  jbe     short loc_1400DA413
0x1400da410  mov     rbx, [rbx]
0x1400da413  mov     rdx, rbx
0x1400da416  lea     rcx, [rbp+57h+Src]
0x1400da41a  call    ?ResolveDirectoryPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveDirectoryPath(ushort const *)
0x1400da41f  mov     rdx, rax
0x1400da422  lea     rcx, [rbp+57h+lpPathName]
0x1400da426  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400da42b  jmp     loc_1400DA63F
0x1400da430  cmp     [rbx+18h], r15
0x1400da434  jbe     short loc_1400DA439
0x1400da436  mov     rbx, [rbx]
0x1400da439  cmp     [rdi+18h], r15
0x1400da43d  jbe     short loc_1400DA442
0x1400da43f  mov     rdi, [rdi]
0x1400da442  mov     r8, rbx
0x1400da445  mov     rdx, rdi
0x1400da448  lea     rcx, [rbp+57h+Src]; Src
0x1400da44c  call    ?ConvertContainerPathToHostPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; ComputeService::Storage::ConvertContainerPathToHostPath(ushort const *,ushort const *)
0x1400da451  jmp     short loc_1400DA41F
0x1400da453  xorps   xmm0, xmm0
0x1400da456  movups  [rbp+57h+Src], xmm0
0x1400da45a  mov     [rbp+57h+var_70], 0
0x1400da462  mov     [rbp+57h+var_68], r15
0x1400da466  xor     eax, eax
0x1400da468  mov     word ptr [rbp+57h+Src], ax
0x1400da46c  test    sil, sil
0x1400da46f  jz      short loc_1400DA4CD
0x1400da471  cmp     [rbx+18h], r15
0x1400da475  jbe     short loc_1400DA47C
0x1400da477  mov     rdx, [rbx]
0x1400da47a  jmp     short loc_1400DA47F
0x1400da47c  mov     rdx, rbx
0x1400da47f  lea     rcx, [rsp+120h+var_100]
0x1400da484  call    ?ResolveDirectoryPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveDirectoryPath(ushort const *)
0x1400da489  mov     rdx, rax
0x1400da48c  lea     rcx, [rbp+57h+lpPathName]
0x1400da490  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400da495  lea     rcx, [rsp+120h+var_100]; void *
0x1400da49a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da49f  cmp     [rbx+18h], r15
0x1400da4a3  jbe     short loc_1400DA4A8
0x1400da4a5  mov     rbx, [rbx]
0x1400da4a8  mov     r8, rbx
0x1400da4ab  lea     rdx, aGlobalS; "\\GLOBAL??\\%s"
0x1400da4b2  lea     rcx, [rsp+120h+var_100]; Src
0x1400da4b7  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400da4bc  mov     rdx, rax
0x1400da4bf  lea     rcx, [rbp+57h+Src]
0x1400da4c3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400da4c8  jmp     loc_1400DA56C
0x1400da4cd  mov     rdx, rbx; struct _GUID *
0x1400da4d0  lea     rcx, [rsp+120h+var_E0]; Src
0x1400da4d5  call    ComputeService__ContainerUtilities___anonymous_namespace___GetHashPath
0x1400da4da  nop
0x1400da4db  cmp     [rax+18h], r15
0x1400da4df  jbe     short loc_1400DA4E4
0x1400da4e1  mov     rax, [rax]
0x1400da4e4  cmp     [rdi+18h], r15
0x1400da4e8  jbe     short loc_1400DA4ED
0x1400da4ea  mov     rdi, [rdi]
0x1400da4ed  mov     r8, rax
0x1400da4f0  mov     rdx, rdi
0x1400da4f3  lea     rcx, [rsp+120h+var_100]; Src
0x1400da4f8  call    ?ConvertContainerPathToHostPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; ComputeService::Storage::ConvertContainerPathToHostPath(ushort const *,ushort const *)
0x1400da4fd  mov     rdx, rax
0x1400da500  lea     rcx, [rbp+57h+lpPathName]
0x1400da504  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400da509  lea     rcx, [rsp+120h+var_100]; void *
0x1400da50e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da513  nop
0x1400da514  lea     rcx, [rsp+120h+var_E0]; void *
0x1400da519  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da51e  cmp     [rbx+18h], r15
0x1400da522  jbe     short loc_1400DA527
0x1400da524  mov     rbx, [rbx]
0x1400da527  mov     rdx, r14
0x1400da52a  lea     rcx, [rsp+120h+var_100]; Src
0x1400da52f  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x1400da534  nop
0x1400da535  cmp     [rax+18h], r15
0x1400da539  jbe     short loc_1400DA53E
0x1400da53b  mov     rax, [rax]
0x1400da53e  mov     r9, rbx
0x1400da541  mov     r8, rax
0x1400da544  lea     rdx, aSGlobalS; "%s\\GLOBAL??\\%s"
0x1400da54b  lea     rcx, [rsp+120h+var_E0]; Src
0x1400da550  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400da555  mov     rdx, rax
0x1400da558  lea     rcx, [rbp+57h+Src]
0x1400da55c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400da561  lea     rcx, [rsp+120h+var_E0]; void *
0x1400da566  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da56b  nop
0x1400da56c  lea     rcx, [rsp+120h+var_100]; void *
0x1400da571  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da576  lea     rcx, [rbp+57h+lpPathName]
0x1400da57a  cmp     qword ptr [rbp+57h+var_50+8], r15
0x1400da57e  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x1400da583  call    cs:__imp_RemoveDirectoryW
0x1400da589  mov     rcx, [rbp+5Fh]; this
0x1400da58d  test    eax, eax
0x1400da58f  jz      loc_1400DA6A6
0x1400da595  lea     rax, [rbp+57h+Src]
0x1400da599  cmp     [rbp+57h+var_68], r15
0x1400da59d  cmova   rax, qword ptr [rbp+57h+Src]
0x1400da5a2  mov     rcx, [rbp+57h+var_70]
0x1400da5a6  mov     dword ptr [rbp+57h+SymbolicLinkHandle+4], 0
0x1400da5ad  mov     [rbp+57h+SymbolicLinkHandle+8], rax
0x1400da5b1  add     cx, cx
0x1400da5b4  mov     word ptr [rbp+57h+SymbolicLinkHandle], cx
0x1400da5b8  mov     word ptr [rbp+57h+SymbolicLinkHandle+2], cx
0x1400da5bc  movaps  xmm0, xmmword ptr [rbp+57h+SymbolicLinkHandle]
0x1400da5c0  movdqa  [rbp+57h+var_40], xmm0
0x1400da5c5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400da5cd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 10h
0x1400da5d5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400da5dd  lea     rax, [rbp+57h+var_40]
0x1400da5e1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400da5e5  xorps   xmm0, xmm0
0x1400da5e8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400da5ed  mov     [rbp+57h+SymbolicLinkHandle], 0
0x1400da5f5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400da5f9  mov     edx, 10000000h; DesiredAccess
0x1400da5fe  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1400da602  call    cs:__imp_NtOpenSymbolicLinkObject
0x1400da608  mov     rcx, [rbp+5Fh]; this
0x1400da60c  test    eax, eax
0x1400da60e  js      loc_1400DA6B8
0x1400da614  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x1400da618  call    cs:__imp_NtMakeTemporaryObject
0x1400da61e  mov     rcx, [rbp+5Fh]; this
0x1400da622  test    eax, eax
0x1400da624  js      loc_1400DA6CD
0x1400da62a  mov     rcx, [rbp+57h+SymbolicLinkHandle]; hObject
0x1400da62e  lea     rax, [rcx-1]
0x1400da632  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400da636  ja      short loc_1400DA63F
0x1400da638  call    cs:__imp_CloseHandle
0x1400da63e  nop
0x1400da63f  lea     rcx, [rbp+57h+Src]; void *
0x1400da643  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da648  lea     r8, [rbp+57h+lpPathName]
0x1400da64c  cmp     qword ptr [rbp+57h+var_50+8], r15
0x1400da650  cmova   r8, [rbp+57h+lpPathName]
0x1400da655  mov     rcx, r14
0x1400da658  call    BfRemoveMappingInternal
0x1400da65d  mov     rcx, [rbp+5Fh]; this
0x1400da661  test    eax, eax
0x1400da663  js      short loc_1400DA691
0x1400da665  lea     rcx, [rbp+57h+lpPathName]; void *
0x1400da669  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da66e  mov     rcx, [rbp+57h+var_30]
0x1400da672  xor     rcx, rsp; StackCookie
0x1400da675  call    __security_check_cookie
0x1400da67a  mov     rbx, [rsp+120h+arg_18]
0x1400da682  add     rsp, 100h
0x1400da689  pop     r15
0x1400da68b  pop     r14
0x1400da68d  pop     rdi
0x1400da68e  pop     rsi
0x1400da68f  pop     rbp
0x1400da690  retn
0x1400da691  mov     r9d, eax; char *
0x1400da694  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da69b  mov     edx, 1C5h; void *
0x1400da6a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400da6a6  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da6ad  mov     edx, 1BCh; void *
0x1400da6b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400da6b8  mov     r9d, eax; char *
0x1400da6bb  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da6c2  mov     edx, 1C1h; void *
0x1400da6c7  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400da6cd  mov     r9d, eax; char *
0x1400da6d0  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da6d7  mov     edx, 1C2h; void *
0x1400da6dc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
