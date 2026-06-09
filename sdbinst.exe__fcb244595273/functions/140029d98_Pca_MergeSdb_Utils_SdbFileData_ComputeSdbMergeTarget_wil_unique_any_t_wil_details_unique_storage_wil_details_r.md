# Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,_GUID const &,ushort const *)

- ea: `0x140029d98`
- end: `0x14002a03b`
- name: `?ComputeSdbMergeTarget@SdbFileData@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEBG@Z`
- size: `675`
- prototype: `__int64 __fastcall(LPVOID *, _QWORD *, char *, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002b138`

## callees

- `0x140006f60`
- `0x14000fb80`
- `0x14001008c`
- `0x140020f9c`
- `0x140029d98`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140029dcf`
- `KERNEL32!GetLastError` at `0x140029fc3`
- `KERNEL32!GetLastError` at `0x140029dcf`
- `KERNEL32!GetLastError` at `0x140029fc3`
- `KERNEL32!GetProcessHeap` at `0x140029dd7`
- `KERNEL32!GetProcessHeap` at `0x140029fcb`
- `KERNEL32!GetProcessHeap` at `0x140029ff7`
- `KERNEL32!GetProcessHeap` at `0x140029dd7`
- `KERNEL32!GetProcessHeap` at `0x140029fcb`
- `KERNEL32!GetProcessHeap` at `0x140029ff7`
- `KERNEL32!SetLastError` at `0x140029ded`
- `KERNEL32!SetLastError` at `0x140029fe1`
- `KERNEL32!SetLastError` at `0x140029ded`
- `KERNEL32!SetLastError` at `0x140029fe1`
- `KERNEL32!HeapFree` at `0x140029de5`
- `KERNEL32!HeapFree` at `0x140029fd9`
- `KERNEL32!HeapFree` at `0x14002a005`
- `KERNEL32!HeapFree` at `0x140029de5`
- `KERNEL32!HeapFree` at `0x140029fd9`
- `KERNEL32!HeapFree` at `0x14002a005`
- `ntdll!RtlNtStatusToDosError` at `0x140029f1b`
- `ntdll!RtlNtStatusToDosError` at `0x140029f1b`

## string_xrefs

- `0x140029ea7`: `msimain.sdb`
- `0x140029f77`: `Failed to append file extension to ID for merge target (%d)`
- `0x140029f38`: `Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget`
- `0x140029f88`: `Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget(
        LPVOID *a1,
        _QWORD *a2,
        char *a3,
        const char *a4)
{
  void *v4; // r15
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v10; // r14
  void *v11; // rbx
  NTSTATUS v12; // ebx
  ULONG v13; // eax
  ULONG v14; // esi
  int v16; // eax
  const char *v17; // r9
  unsigned int v18; // ebx
  void *v19; // rsi
  DWORD v20; // ebx
  HANDLE v21; // rax
  HANDLE v22; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-69h] BYREF
  void *v24; // [rsp+38h] [rbp-61h] BYREF
  void *v25; // [rsp+40h] [rbp-59h] BYREF
  void *v26; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 v28[48]; // [rsp+60h] [rbp-39h] BYREF

  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    SetLastError(LastError);
  }
  *a1 = 0;
  if ( *a2 == 0x1111111111111111LL && a2[1] == 0x1111111111111111LL )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpMem,
      (char *)L"sysmain.sdb",
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    if ( a1 != &lpMem )
    {
      v10 = lpMem;
LABEL_30:
      v19 = *a1;
      if ( *a1 )
      {
        v20 = GetLastError();
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v19);
        SetLastError(v20);
      }
      *a1 = v10;
      v11 = 0;
      goto LABEL_34;
    }
    v11 = lpMem;
    goto LABEL_34;
  }
  if ( *a2 == 0x4A733312F9AB2228LL && a2[1] == 0xEF12E1706D93F9B6uLL )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v24,
      (char *)L"drvmain.sdb",
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    if ( a1 != &v24 )
    {
      v10 = v24;
      goto LABEL_30;
    }
    v11 = v24;
LABEL_34:
    if ( v11 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
    return *a1 == 0 ? 0xE : 0;
  }
  if ( *a2 == 0x468A6A3AD8FF6D16LL && a2[1] == 0xEA49DC4D7101448BuLL )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v25,
      (char *)L"msimain.sdb",
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    if ( a1 != &v25 )
    {
      v10 = v25;
      goto LABEL_30;
    }
    v11 = v25;
    goto LABEL_34;
  }
  if ( a3 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v26,
      a3,
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    if ( a1 != &v26 )
    {
      v10 = v26;
      goto LABEL_30;
    }
    v11 = v26;
    goto LABEL_34;
  }
  v12 = AslGuidToString(v28, 43, a2);
  v13 = RtlNtStatusToDosError(v12);
  v14 = v13;
  if ( v12 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget",
      2327,
      "AslGuidToString failed to format GUID as string (%d)",
      v13);
    return v14;
  }
  v16 = StringCchCatW(v28, 0x2Bu, L".sdb");
  v18 = v16;
  if ( v16 >= 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v27,
      (char *)v28,
      0xFFFFFFFFFFFFFFFFuLL,
      v17);
    if ( a1 != v27 )
    {
      v10 = (LPVOID)v27[0];
      goto LABEL_30;
    }
    v11 = (void *)v27[0];
    goto LABEL_34;
  }
  if ( (v16 & 0x1FFF0000) == 0x70000 )
    v18 = (unsigned __int16)v16;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget",
    2332,
    "Failed to append file extension to ID for merge target (%d)",
    v18);
  return v18;
}

```

## disassembly

```asm
0x140029d98  mov     [rsp-8+arg_18], rbx
0x140029d9d  push    rbp
0x140029d9e  push    rsi
0x140029d9f  push    rdi
0x140029da0  push    r14
0x140029da2  push    r15
0x140029da4  lea     rbp, [rsp-37h]
0x140029da9  sub     rsp, 0D0h
0x140029db0  mov     rax, cs:__security_cookie
0x140029db7  xor     rax, rsp
0x140029dba  mov     [rbp+57h+var_30], rax
0x140029dbe  mov     r15, [rcx]
0x140029dc1  mov     r14, r8
0x140029dc4  mov     rsi, rdx
0x140029dc7  mov     rdi, rcx
0x140029dca  test    r15, r15
0x140029dcd  jz      short loc_140029DF3
0x140029dcf  call    cs:__imp_GetLastError
0x140029dd5  mov     ebx, eax
0x140029dd7  call    cs:__imp_GetProcessHeap
0x140029ddd  mov     r8, r15; lpMem
0x140029de0  xor     edx, edx; dwFlags
0x140029de2  mov     rcx, rax; hHeap
0x140029de5  call    cs:__imp_HeapFree
0x140029deb  mov     ecx, ebx; dwErrCode
0x140029ded  call    cs:__imp_SetLastError
0x140029df3  mov     qword ptr [rdi], 0
0x140029dfa  mov     rax, [rsi]
0x140029dfd  cmp     rax, cs:qword_14003BDD8
0x140029e04  jnz     short loc_140029E42
0x140029e06  mov     rax, [rsi+8]
0x140029e0a  cmp     rax, cs:qword_14003BDE0
0x140029e11  jnz     short loc_140029E42
0x140029e13  or      r8, 0FFFFFFFFFFFFFFFFh
0x140029e17  lea     rdx, aSysmainSdb_0; "sysmain.sdb"
0x140029e1e  lea     rcx, [rbp+57h+lpMem]
0x140029e22  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140029e27  lea     rax, [rbp+57h+lpMem]
0x140029e2b  cmp     rdi, rax
0x140029e2e  jz      short loc_140029E39
0x140029e30  mov     r14, [rbp+57h+lpMem]
0x140029e34  jmp     loc_140029FBB
0x140029e39  mov     rbx, [rbp+57h+lpMem]
0x140029e3d  jmp     loc_140029FF2
0x140029e42  mov     rax, [rsi]
0x140029e45  cmp     rax, cs:qword_14003BC70
0x140029e4c  jnz     short loc_140029E8A
0x140029e4e  mov     rax, [rsi+8]
0x140029e52  cmp     rax, cs:qword_14003BC78
0x140029e59  jnz     short loc_140029E8A
0x140029e5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x140029e5f  lea     rdx, aDrvmainSdb_0; "drvmain.sdb"
0x140029e66  lea     rcx, [rbp+57h+var_B8]
0x140029e6a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140029e6f  lea     rax, [rbp+57h+var_B8]
0x140029e73  cmp     rdi, rax
0x140029e76  jz      short loc_140029E81
0x140029e78  mov     r14, [rbp+57h+var_B8]
0x140029e7c  jmp     loc_140029FBB
0x140029e81  mov     rbx, [rbp+57h+var_B8]
0x140029e85  jmp     loc_140029FF2
0x140029e8a  mov     rax, [rsi]
0x140029e8d  cmp     rax, cs:qword_14003BDC8
0x140029e94  jnz     short loc_140029ED2
0x140029e96  mov     rax, [rsi+8]
0x140029e9a  cmp     rax, cs:qword_14003BDD0
0x140029ea1  jnz     short loc_140029ED2
0x140029ea3  or      r8, 0FFFFFFFFFFFFFFFFh
0x140029ea7  lea     rdx, aMsimainSdb_0; "msimain.sdb"
0x140029eae  lea     rcx, [rbp+57h+var_B0]
0x140029eb2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140029eb7  lea     rax, [rbp+57h+var_B0]
0x140029ebb  cmp     rdi, rax
0x140029ebe  jz      short loc_140029EC9
0x140029ec0  mov     r14, [rbp+57h+var_B0]
0x140029ec4  jmp     loc_140029FBB
0x140029ec9  mov     rbx, [rbp+57h+var_B0]
0x140029ecd  jmp     loc_140029FF2
0x140029ed2  test    r14, r14
0x140029ed5  jz      short loc_140029F02
0x140029ed7  or      r8, 0FFFFFFFFFFFFFFFFh
0x140029edb  lea     rcx, [rbp+57h+var_A8]
0x140029edf  mov     rdx, r14
0x140029ee2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140029ee7  lea     rax, [rbp+57h+var_A8]
0x140029eeb  cmp     rdi, rax
0x140029eee  jz      short loc_140029EF9
0x140029ef0  mov     r14, [rbp+57h+var_A8]
0x140029ef4  jmp     loc_140029FBB
0x140029ef9  mov     rbx, [rbp+57h+var_A8]
0x140029efd  jmp     loc_140029FF2
0x140029f02  mov     r14d, 2Bh ; '+'
0x140029f08  lea     rcx, [rbp+57h+var_90]
0x140029f0c  mov     edx, r14d
0x140029f0f  mov     r8, rsi
0x140029f12  call    AslGuidToString
0x140029f17  mov     ecx, eax; Status
0x140029f19  mov     ebx, eax
0x140029f1b  call    cs:__imp_RtlNtStatusToDosError
0x140029f21  mov     esi, eax
0x140029f23  test    ebx, ebx
0x140029f25  jns     short loc_140029F4F
0x140029f27  lea     r9, aAslguidtostrin_0; "AslGuidToString failed to format GUID a"...
0x140029f2e  mov     [rsp+0F0h+var_D0], eax
0x140029f32  mov     r8d, 917h
0x140029f38  lea     rdx, aPcaMergesdbUti_15; "Pca::MergeSdb::Utils::SdbFileData::Comp"...
0x140029f3f  lea     ecx, [r14-2Ah]
0x140029f43  call    AslLogCallPrintf
0x140029f48  mov     eax, esi
0x140029f4a  jmp     loc_14002A018
0x140029f4f  lea     r8, aSdb; ".sdb"
0x140029f56  mov     rdx, r14; unsigned __int64
0x140029f59  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x140029f5d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140029f62  mov     ebx, eax
0x140029f64  test    eax, eax
0x140029f66  jns     short loc_140029F9D
0x140029f68  and     eax, 1FFF0000h
0x140029f6d  cmp     eax, 70000h
0x140029f72  jnz     short loc_140029F77
0x140029f74  movzx   ebx, bx
0x140029f77  lea     r9, aFailedToAppend_4; "Failed to append file extension to ID f"...
0x140029f7e  mov     [rsp+0F0h+var_D0], ebx
0x140029f82  mov     r8d, 91Ch
0x140029f88  lea     rdx, aPcaMergesdbUti_15; "Pca::MergeSdb::Utils::SdbFileData::Comp"...
0x140029f8f  mov     ecx, 1
0x140029f94  call    AslLogCallPrintf
0x140029f99  mov     eax, ebx
0x140029f9b  jmp     short loc_14002A018
0x140029f9d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140029fa1  lea     rdx, [rbp+57h+var_90]
0x140029fa5  lea     rcx, [rbp+57h+var_A0]
0x140029fa9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140029fae  lea     rax, [rbp+57h+var_A0]
0x140029fb2  cmp     rdi, rax
0x140029fb5  jz      short loc_140029FEE
0x140029fb7  mov     r14, [rbp+57h+var_A0]
0x140029fbb  mov     rsi, [rdi]
0x140029fbe  test    rsi, rsi
0x140029fc1  jz      short loc_140029FE7
0x140029fc3  call    cs:__imp_GetLastError
0x140029fc9  mov     ebx, eax
0x140029fcb  call    cs:__imp_GetProcessHeap
0x140029fd1  mov     r8, rsi; lpMem
0x140029fd4  xor     edx, edx; dwFlags
0x140029fd6  mov     rcx, rax; hHeap
0x140029fd9  call    cs:__imp_HeapFree
0x140029fdf  mov     ecx, ebx; dwErrCode
0x140029fe1  call    cs:__imp_SetLastError
0x140029fe7  mov     [rdi], r14
0x140029fea  xor     ebx, ebx
0x140029fec  jmp     short loc_140029FF2
0x140029fee  mov     rbx, [rbp+57h+var_A0]
0x140029ff2  test    rbx, rbx
0x140029ff5  jz      short loc_14002A00B
0x140029ff7  call    cs:__imp_GetProcessHeap
0x140029ffd  mov     r8, rbx; lpMem
0x14002a000  xor     edx, edx; dwFlags
0x14002a002  mov     rcx, rax; hHeap
0x14002a005  call    cs:__imp_HeapFree
0x14002a00b  mov     rax, [rdi]
0x14002a00e  neg     rax
0x14002a011  sbb     eax, eax
0x14002a013  not     eax
0x14002a015  and     eax, 0Eh
0x14002a018  mov     rcx, [rbp+57h+var_30]
0x14002a01c  xor     rcx, rsp; StackCookie
0x14002a01f  call    __security_check_cookie
0x14002a024  mov     rbx, [rsp+0F0h+arg_18]
0x14002a02c  add     rsp, 0D0h
0x14002a033  pop     r15
0x14002a035  pop     r14
0x14002a037  pop     rdi
0x14002a038  pop     rsi
0x14002a039  pop     rbp
0x14002a03a  retn
```
