# WldpIsAllowedEntryPoint

- ea: `0x18001a7a0`
- end: `0x18001ab82`
- name: `WldpIsAllowedEntryPoint`
- size: `994`
- prototype: `__int64 __fastcall(int, __int64, __int64, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001a3f4`
- `0x18001a7a0`
- `0x18001ab88`
- `0x1800206f4`
- `0x18002084c`
- `0x180021ec0`
- `0x180029730`
- `0x180029830`
- `0x180029968`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a963`
- `ntdll!RtlInitUnicodeString` at `0x18001a9a9`
- `ntdll!RtlInitUnicodeString` at `0x18001a9bd`
- `ntdll!RtlInitUnicodeString` at `0x18001a9a9`
- `ntdll!RtlInitUnicodeString` at `0x18001a9bd`
- `ntdll!NtQuerySystemInformation` at `0x18001a928`
- `ntdll!NtQuerySystemInformation` at `0x18001a928`
- `ntdll!NtQuerySecurityPolicy` at `0x18001a9e5`
- `ntdll!NtQuerySecurityPolicy` at `0x18001a9e5`

## string_xrefs

- `0x18001a939`: `onecore\base\ngscb\wldp\dll\hostlockdown.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsAllowedEntryPoint(int a1, __int64 a2, __int64 a3, int *a4)
{
  __int64 v5; // r13
  WCHAR *v6; // rdi
  void *v7; // rbx
  const WCHAR *v8; // r14
  int v9; // edx
  int OriginalFileNameFromResource; // ebx
  const wchar_t *v11; // rax
  int v12; // esi
  const wchar_t *v13; // rax
  __int64 v14; // r13
  NTSTATUS v15; // eax
  int v16; // ecx
  unsigned int v17; // esi
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // r13d
  __int64 v23; // rdi
  int v24; // r13d
  int v25; // [rsp+20h] [rbp-99h]
  __int64 v26; // [rsp+28h] [rbp-91h]
  void *v27; // [rsp+40h] [rbp-79h] BYREF
  const WCHAR *v28; // [rsp+48h] [rbp-71h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-69h]
  __int64 v30; // [rsp+58h] [rbp-61h]
  int v31; // [rsp+60h] [rbp-59h] BYREF
  int v32; // [rsp+64h] [rbp-55h] BYREF
  int v33; // [rsp+68h] [rbp-51h] BYREF
  int *v34; // [rsp+70h] [rbp-49h]
  __int64 *v35; // [rsp+78h] [rbp-41h]
  struct _UNICODE_STRING v36; // [rsp+80h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-29h] BYREF
  _OWORD SystemInformation[2]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v34 = a4;
  v5 = a1;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  *a4 = 0;
  v8 = L"*";
  SourceString = L"*";
  if ( a2 )
  {
    v27 = 0;
    v28 = 0;
    OriginalFileNameFromResource = FindOriginalFileNameFromResource(a2, &v28, &v27);
    if ( OriginalFileNameFromResource < 0 )
    {
      if ( OriginalFileNameFromResource != -2147023083 )
      {
        if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 8) != 0 )
        {
          v11 = L"*";
          if ( a3 )
            v11 = (const wchar_t *)a3;
          McTemplateU0zzzd_EventWriteTransfer(
            a1,
            v9,
            qword_180043100[2 * v5 + 1],
            (_DWORD)v27,
            (__int64)v11,
            OriginalFileNameFromResource);
        }
        WldpTraceLogging(
          1,
          (unsigned int)&qword_180043100[2 * v5],
          (_DWORD)v27,
          (unsigned int)L"*",
          a3,
          OriginalFileNameFromResource);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        goto LABEL_38;
      }
      v6 = (WCHAR *)v28;
    }
    else
    {
      v6 = (WCHAR *)v28;
      SourceString = v28;
    }
    v7 = v27;
  }
  v12 = 1;
  if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
  {
    v13 = L"*";
    if ( a3 )
      v13 = (const wchar_t *)a3;
    McTemplateU0zzzz_EventWriteTransfer(
      a1,
      (unsigned int)HostLockdownCheckEvent,
      qword_180043100[2 * v5 + 1],
      (_DWORD)v7,
      (__int64)v13,
      (__int64)v6);
  }
  v14 = 2 * v5;
  v30 = v14 * 8;
  v35 = &qword_180043100[v14];
  WldpTraceLogging(0, (unsigned int)&qword_180043100[v14], (_DWORD)v7, (_DWORD)SourceString, a3, 0);
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v15 = NtQuerySystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u, 0);
  if ( v15 >= 0 )
  {
    if ( (SystemInformation[0] & 0x51) == 0x51 )
    {
      v36 = 0;
      DestinationString = 0;
      v32 = 0;
      v31 = 4;
      v33 = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      if ( a3 )
        v8 = (const WCHAR *)a3;
      RtlInitUnicodeString(&v36, v8);
      v19 = NtQuerySecurityPolicy(v35, &DestinationString, &v36, &v33, &v32, &v31);
      v22 = v19;
      if ( v19 == -1073741275 )
      {
        if ( (SystemInformation[0] & 2) != 0 )
        {
          if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
            McTemplateU0zzzz_EventWriteTransfer(
              v21,
              (unsigned int)HostLockdownCheckAuditAllowedEvent,
              *(__int64 *)((char *)&qword_180043100[1] + v30),
              (_DWORD)v7,
              (__int64)v8,
              (__int64)v6);
        }
        else
        {
          if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 8) != 0 )
            McTemplateU0zzzz_EventWriteTransfer(
              v21,
              (unsigned int)HostLockdownCheckBlockedEvent,
              *(__int64 *)((char *)&qword_180043100[1] + v30),
              (_DWORD)v7,
              (__int64)v8,
              (__int64)v6);
          WldpTraceLogging(2, (_DWORD)v35, (_DWORD)v7, (_DWORD)SourceString, a3, 0);
          v12 = 0;
        }
        *v34 = v12;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        OriginalFileNameFromResource = 0;
        goto LABEL_38;
      }
      if ( v19 < 0 )
      {
        if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 8) != 0 )
        {
          v26 = (__int64)v6;
          v23 = v30;
          McTemplateU0zzzzd_EventWriteTransfer(
            v21,
            v20,
            *(__int64 *)((char *)&qword_180043100[1] + v30),
            (_DWORD)v7,
            (__int64)v8,
            v26,
            v19);
        }
        else
        {
          v23 = v30;
        }
        v24 = v22 | 0x10000000;
        WldpTraceLogging(3, (unsigned int)qword_180043100 + v23, (_DWORD)v7, (_DWORD)SourceString, a3, v24);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        OriginalFileNameFromResource = v24;
LABEL_38:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        return (unsigned int)OriginalFileNameFromResource;
      }
      *v34 = 1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    }
    else
    {
      *v34 = 1;
      if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 1) != 0 )
      {
        if ( a3 )
          v8 = (const WCHAR *)a3;
        McTemplateU0zzzz_EventWriteTransfer(
          v16,
          (unsigned int)HostLockdownCheckAllowedEvent,
          qword_180043100[v14 + 1],
          (_DWORD)v7,
          (__int64)v8,
          (__int64)v6);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    return 0;
  }
  v17 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\hostlockdown.cpp",
          (const char *)(unsigned int)v15,
          v25);
  if ( v7 )
    LocalFree(v7);
  if ( v6 )
    LocalFree(v6);
  return v17;
}

```

## disassembly

```asm
0x18001a7a0  push    rbp
0x18001a7a2  push    rbx
0x18001a7a3  push    rsi
0x18001a7a4  push    rdi
0x18001a7a5  push    r12
0x18001a7a7  push    r13
0x18001a7a9  push    r14
0x18001a7ab  push    r15
0x18001a7ad  lea     rbp, [rsp-1Fh]
0x18001a7b2  sub     rsp, 0D8h
0x18001a7b9  mov     rax, cs:__security_cookie
0x18001a7c0  xor     rax, rsp
0x18001a7c3  mov     [rbp+57h+var_50], rax
0x18001a7c7  mov     rax, r9
0x18001a7ca  mov     [rbp+57h+var_A0], rax
0x18001a7ce  mov     r12, r8
0x18001a7d1  mov     r9, rdx
0x18001a7d4  movsxd  r13, ecx
0x18001a7d7  xor     edi, edi
0x18001a7d9  mov     [rbp+57h+var_C8], rdi
0x18001a7dd  xor     ebx, ebx
0x18001a7df  mov     [rbp+57h+var_D0], rbx
0x18001a7e3  mov     [rax], ebx
0x18001a7e5  lea     r14, asc_180047E5C; "*"
0x18001a7ec  mov     [rbp+57h+SourceString], r14
0x18001a7f0  test    rdx, rdx
0x18001a7f3  jz      loc_18001A89C
0x18001a7f9  mov     [rbp+57h+var_D0], rbx
0x18001a7fd  mov     [rbp+57h+var_C8], rbx
0x18001a801  lea     r8, [rbp+57h+var_D0]
0x18001a805  lea     rdx, [rbp+57h+var_C8]
0x18001a809  mov     rcx, r9
0x18001a80c  call    FindOriginalFileNameFromResource
0x18001a811  mov     ebx, eax
0x18001a813  test    eax, eax
0x18001a815  js      short loc_18001A821
0x18001a817  mov     rdi, [rbp+57h+var_C8]
0x18001a81b  mov     [rbp+57h+SourceString], rdi
0x18001a81f  jmp     short loc_18001A898
0x18001a821  cmp     ebx, 80070715h
0x18001a827  jz      short loc_18001A894
0x18001a829  lea     r15, qword_180043100
0x18001a830  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 8
0x18001a837  jz      short loc_18001A860
0x18001a839  mov     rax, r14
0x18001a83c  test    r12, r12
0x18001a83f  cmovnz  rax, r12
0x18001a843  mov     r8, r13
0x18001a846  add     r8, r8
0x18001a849  mov     dword ptr [rsp+110h+var_E8], ebx
0x18001a84d  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a852  mov     r9, [rbp+57h+var_D0]
0x18001a856  mov     r8, [r15+r8*8+8]
0x18001a85b  call    McTemplateU0zzzd_EventWriteTransfer
0x18001a860  mov     rdx, r13
0x18001a863  shl     rdx, 4
0x18001a867  add     rdx, r15
0x18001a86a  mov     dword ptr [rsp+110h+var_E8], ebx
0x18001a86e  mov     qword ptr [rsp+110h+var_F0], r12
0x18001a873  mov     r9, r14
0x18001a876  mov     r8, [rbp+57h+var_D0]
0x18001a87a  mov     ecx, 1
0x18001a87f  call    WldpTraceLogging
0x18001a884  nop
0x18001a885  lea     rcx, [rbp+57h+var_D0]
0x18001a889  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a88e  nop
0x18001a88f  jmp     loc_18001AAF9
0x18001a894  mov     rdi, [rbp+57h+var_C8]
0x18001a898  mov     rbx, [rbp+57h+var_D0]
0x18001a89c  lea     r15, qword_180043100
0x18001a8a3  mov     esi, 1
0x18001a8a8  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, sil
0x18001a8af  jz      short loc_18001A8DF
0x18001a8b1  mov     rax, r14
0x18001a8b4  test    r12, r12
0x18001a8b7  cmovnz  rax, r12
0x18001a8bb  mov     r8, r13
0x18001a8be  add     r8, r8
0x18001a8c1  mov     [rsp+110h+var_E8], rdi
0x18001a8c6  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a8cb  mov     r9, rbx
0x18001a8ce  mov     r8, [r15+r8*8+8]
0x18001a8d3  lea     rdx, HostLockdownCheckEvent
0x18001a8da  call    McTemplateU0zzzz_EventWriteTransfer
0x18001a8df  shl     r13, 4
0x18001a8e3  mov     [rbp+57h+var_B8], r13
0x18001a8e7  lea     rax, [r15+r13]
0x18001a8eb  mov     [rbp+57h+var_98], rax
0x18001a8ef  mov     dword ptr [rsp+110h+var_E8], 0
0x18001a8f7  mov     qword ptr [rsp+110h+var_F0], r12; int
0x18001a8fc  mov     r9, [rbp+57h+SourceString]
0x18001a900  mov     r8, rbx
0x18001a903  mov     rdx, rax
0x18001a906  xor     ecx, ecx
0x18001a908  call    WldpTraceLogging
0x18001a90d  xorps   xmm0, xmm0
0x18001a910  movups  [rbp+57h+SystemInformation], xmm0
0x18001a914  movups  [rbp+57h+var_60], xmm0
0x18001a918  xor     r9d, r9d; ReturnLength
0x18001a91b  lea     r8d, [r9+20h]; SystemInformationLength
0x18001a91f  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18001a923  mov     ecx, 0A4h; SystemInformationClass
0x18001a928  call    cs:__imp_NtQuerySystemInformation
0x18001a92e  test    eax, eax
0x18001a930  jns     short loc_18001A970
0x18001a932  mov     rcx, [rbp+5Fh]; this
0x18001a936  mov     r9d, eax; char *
0x18001a939  lea     r8, aOnecoreBaseNgs; "onecore\\base\\ngscb\\wldp\\dll\\hostlo"...
0x18001a940  mov     edx, 8Fh; void *
0x18001a945  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a94a  mov     esi, eax
0x18001a94c  test    rbx, rbx
0x18001a94f  jz      short loc_18001A95B
0x18001a951  mov     rcx, rbx; hMem
0x18001a954  call    cs:__imp_LocalFree
0x18001a95a  nop
0x18001a95b  test    rdi, rdi
0x18001a95e  jz      short loc_18001A969
0x18001a960  mov     rcx, rdi; hMem
0x18001a963  call    cs:__imp_LocalFree
0x18001a969  mov     eax, esi
0x18001a96b  jmp     loc_18001AB62
0x18001a970  mov     eax, dword ptr [rbp+57h+SystemInformation]
0x18001a973  and     eax, 51h
0x18001a976  cmp     al, 51h ; 'Q'
0x18001a978  jnz     loc_18001AB18
0x18001a97e  xorps   xmm0, xmm0
0x18001a981  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x18001a985  xorps   xmm1, xmm1
0x18001a988  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18001a98c  mov     [rbp+57h+var_AC], 0
0x18001a993  mov     [rbp+57h+var_B0], 4
0x18001a99a  mov     [rbp+57h+var_A8], 0
0x18001a9a1  mov     rdx, [rbp+57h+SourceString]; SourceString
0x18001a9a5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001a9a9  call    cs:__imp_RtlInitUnicodeString
0x18001a9af  test    r12, r12
0x18001a9b2  cmovnz  r14, r12
0x18001a9b6  mov     rdx, r14; SourceString
0x18001a9b9  lea     rcx, [rbp+57h+var_90]; DestinationString
0x18001a9bd  call    cs:__imp_RtlInitUnicodeString
0x18001a9c3  lea     rax, [rbp+57h+var_B0]
0x18001a9c7  mov     [rsp+110h+var_E8], rax
0x18001a9cc  lea     rax, [rbp+57h+var_AC]
0x18001a9d0  mov     qword ptr [rsp+110h+var_F0], rax
0x18001a9d5  lea     r9, [rbp+57h+var_A8]
0x18001a9d9  lea     r8, [rbp+57h+var_90]
0x18001a9dd  lea     rdx, [rbp+57h+DestinationString]
0x18001a9e1  mov     rcx, [rbp+57h+var_98]
0x18001a9e5  call    cs:__imp_NtQuerySecurityPolicy
0x18001a9eb  mov     r13d, eax
0x18001a9ee  cmp     eax, 0C0000225h
0x18001a9f3  jnz     loc_18001AA8F
0x18001a9f9  test    byte ptr [rbp+57h+SystemInformation], 2
0x18001a9fd  jz      short loc_18001AA2C
0x18001a9ff  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, sil
0x18001aa06  jz      short loc_18001AA7B
0x18001aa08  mov     [rsp+110h+var_E8], rdi
0x18001aa0d  mov     qword ptr [rsp+110h+var_F0], r14
0x18001aa12  mov     r9, rbx
0x18001aa15  mov     rdi, [rbp+57h+var_B8]
0x18001aa19  mov     r8, [rdi+r15+8]
0x18001aa1e  lea     rdx, HostLockdownCheckAuditAllowedEvent
0x18001aa25  call    McTemplateU0zzzz_EventWriteTransfer
0x18001aa2a  jmp     short loc_18001AA7B
0x18001aa2c  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 8
0x18001aa33  jz      short loc_18001AA57
0x18001aa35  mov     [rsp+110h+var_E8], rdi
0x18001aa3a  mov     qword ptr [rsp+110h+var_F0], r14
0x18001aa3f  mov     r9, rbx
0x18001aa42  mov     rdi, [rbp+57h+var_B8]
0x18001aa46  mov     r8, [rdi+r15+8]
0x18001aa4b  lea     rdx, HostLockdownCheckBlockedEvent
0x18001aa52  call    McTemplateU0zzzz_EventWriteTransfer
0x18001aa57  mov     dword ptr [rsp+110h+var_E8], 0
0x18001aa5f  mov     qword ptr [rsp+110h+var_F0], r12
0x18001aa64  mov     r9, [rbp+57h+SourceString]
0x18001aa68  mov     r8, rbx
0x18001aa6b  mov     rdx, [rbp+57h+var_98]
0x18001aa6f  mov     ecx, 2
0x18001aa74  call    WldpTraceLogging
0x18001aa79  xor     esi, esi
0x18001aa7b  mov     rax, [rbp+57h+var_A0]
0x18001aa7f  mov     [rax], esi
0x18001aa81  lea     rcx, [rbp+57h+var_D0]
0x18001aa85  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001aa8a  nop
0x18001aa8b  xor     ebx, ebx
0x18001aa8d  jmp     short loc_18001AAF9
0x18001aa8f  test    r13d, r13d
0x18001aa92  jns     short loc_18001AB06
0x18001aa94  mov     esi, 10000000h
0x18001aa99  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 8
0x18001aaa0  jz      short loc_18001AAC5
0x18001aaa2  or      eax, esi
0x18001aaa4  mov     [rsp+110h+var_E0], eax
0x18001aaa8  mov     [rsp+110h+var_E8], rdi
0x18001aaad  mov     qword ptr [rsp+110h+var_F0], r14
0x18001aab2  mov     r9, rbx
0x18001aab5  mov     rdi, [rbp+57h+var_B8]
0x18001aab9  mov     r8, [rdi+r15+8]
0x18001aabe  call    McTemplateU0zzzzd_EventWriteTransfer
0x18001aac3  jmp     short loc_18001AAC9
0x18001aac5  mov     rdi, [rbp+57h+var_B8]
0x18001aac9  or      r13d, esi
0x18001aacc  lea     rdx, [rdi+r15]
0x18001aad0  mov     dword ptr [rsp+110h+var_E8], r13d
0x18001aad5  mov     qword ptr [rsp+110h+var_F0], r12
0x18001aada  mov     r9, [rbp+57h+SourceString]
0x18001aade  mov     r8, rbx
0x18001aae1  mov     ecx, 3
0x18001aae6  call    WldpTraceLogging
0x18001aaeb  nop
0x18001aaec  lea     rcx, [rbp+57h+var_D0]
0x18001aaf0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001aaf5  nop
0x18001aaf6  mov     ebx, r13d
0x18001aaf9  lea     rcx, [rbp+57h+var_C8]
0x18001aafd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ab02  mov     eax, ebx
0x18001ab04  jmp     short loc_18001AB62
0x18001ab06  mov     rax, [rbp+57h+var_A0]
0x18001ab0a  mov     [rax], esi
0x18001ab0c  lea     rcx, [rbp+57h+var_D0]
0x18001ab10  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ab15  nop
0x18001ab16  jmp     short loc_18001AB57
0x18001ab18  mov     rax, [rbp+57h+var_A0]
0x18001ab1c  mov     [rax], esi
0x18001ab1e  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, sil
0x18001ab25  jz      short loc_18001AB4D
0x18001ab27  test    r12, r12
0x18001ab2a  cmovnz  r14, r12
0x18001ab2e  mov     [rsp+110h+var_E8], rdi
0x18001ab33  mov     qword ptr [rsp+110h+var_F0], r14
0x18001ab38  mov     r9, rbx
0x18001ab3b  mov     r8, [r15+r13+8]
0x18001ab40  lea     rdx, HostLockdownCheckAllowedEvent
0x18001ab47  call    McTemplateU0zzzz_EventWriteTransfer
0x18001ab4c  nop
0x18001ab4d  lea     rcx, [rbp+57h+var_D0]
0x18001ab51  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ab56  nop
0x18001ab57  lea     rcx, [rbp+57h+var_C8]
0x18001ab5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ab60  xor     eax, eax
0x18001ab62  mov     rcx, [rbp+57h+var_50]
0x18001ab66  xor     rcx, rsp; StackCookie
0x18001ab69  call    __security_check_cookie
0x18001ab6e  add     rsp, 0D8h
0x18001ab75  pop     r15
0x18001ab77  pop     r14
0x18001ab79  pop     r13
0x18001ab7b  pop     r12
0x18001ab7d  pop     rdi
0x18001ab7e  pop     rsi
0x18001ab7f  pop     rbx
0x18001ab80  pop     rbp
0x18001ab81  retn
```
