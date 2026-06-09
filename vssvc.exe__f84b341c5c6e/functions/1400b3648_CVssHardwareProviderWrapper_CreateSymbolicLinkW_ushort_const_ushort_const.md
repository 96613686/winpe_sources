# CVssHardwareProviderWrapper::CreateSymbolicLinkW(ushort const *,ushort const *)

- ea: `0x1400b3648`
- end: `0x1400b38da`
- name: `?CreateSymbolicLinkW@CVssHardwareProviderWrapper@@AEAA_NPEBG0@Z`
- size: `658`
- prototype: `bool(CVssHardwareProviderWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140063f60`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x14002d6d4`
- `0x14002d7b0`
- `0x140035280`
- `0x14003a8f0`
- `0x14003c7f0`
- `0x1400921dc`
- `0x1400b3648`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400b3703`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400b3723`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400b3703`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400b3723`
- `ntdll!RtlInitUnicodeString` at `0x1400b37b5`
- `ntdll!RtlInitUnicodeString` at `0x1400b37c2`
- `ntdll!RtlInitUnicodeString` at `0x1400b37b5`
- `ntdll!RtlInitUnicodeString` at `0x1400b37c2`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400b3810`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400b3810`
- `ntdll!NtClose` at `0x1400b3883`
- `ntdll!NtClose` at `0x1400b3883`

## string_xrefs

- `0x1400b366f`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b3864`: `NtCreateSymbolicLinkObject failed with status %d`
- `0x1400b367a`: `CVssHardwareProviderWrapper::CreateSymbolicLinkW`
- `0x1400b3820`: `CVssHardwareProviderWrapper::CreateSymbolicLinkW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall CVssHardwareProviderWrapper::CreateSymbolicLinkW(
        CVssHardwareProviderWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v5; // rdi
  const WCHAR *v6; // rbx
  NTSTATUS v7; // ebx
  bool v8; // dl
  bool v9; // bl
  void **v11; // [rsp+28h] [rbp-E0h] BYREF
  void *v12; // [rsp+30h] [rbp-D8h]
  void **v13; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v14[40]; // [rsp+40h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+68h] [rbp-A0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING Name; // [rsp+A8h] [rbp-60h] BYREF
  const unsigned __int16 *v18; // [rsp+B8h] [rbp-50h] BYREF
  const wchar_t *v19; // [rsp+C0h] [rbp-48h]
  const unsigned __int16 *v20; // [rsp+C8h] [rbp-40h]
  int v21; // [rsp+D0h] [rbp-38h]
  int v22; // [rsp+D4h] [rbp-34h]
  int v23; // [rsp+D8h] [rbp-30h]
  _BYTE v24[120]; // [rsp+E0h] [rbp-28h] BYREF
  int v25; // [rsp+158h] [rbp+50h]
  LPVOID v26[14]; // [rsp+168h] [rbp+60h] BYREF
  void *SymbolicLinkHandle; // [rsp+1F8h] [rbp+F0h] BYREF

  SymbolicLinkHandle = this;
  v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v19 = L"CVssHardwareProviderWrapper::CreateSymbolicLinkW";
  v20 = L"CORHDELC";
  v21 = 3065;
  v22 = 1;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v26, (__int64)&v18, 0);
  DestinationString = 0;
  Name = 0;
  memset(&ObjectAttributes_8, 0, sizeof(ObjectAttributes_8));
  SymbolicLinkHandle = 0;
  v5 = a2 + 14;
  if ( (unsigned int)_o__wcsnicmp(a2, L"\\\\?\\GLOBALROOT", 14) )
    v5 = a2;
  v6 = a3 + 14;
  if ( (unsigned int)_o__wcsnicmp(a3, L"\\\\?\\GLOBALROOT", 14) )
    v6 = a3;
  *(_QWORD *)v14 = 0;
  v13 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  CAutoSid::CreateBasicSid((CAutoSid *)&v13, WinWorldSid);
  v12 = 0;
  v11 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  CAutoSid::CreateBasicSid((CAutoSid *)&v11, WinNtAuthoritySid);
  memset(&v14[8], 0, 32);
  CVssSecurityDescriptor::Initialize((CVssSecurityDescriptor *)&v14[8]);
  CVssSecurityDescriptor::Allow((CVssSecurityDescriptor *)&v14[8], *(void **)v14);
  CVssSecurityDescriptor::Allow((CVssSecurityDescriptor *)&v14[8], v12);
  RtlInitUnicodeString(&DestinationString, v5);
  RtlInitUnicodeString(&Name, v6);
  ObjectAttributes_8.Length = 48;
  ObjectAttributes_8.RootDirectory = 0;
  ObjectAttributes_8.Attributes = 80;
  ObjectAttributes_8.ObjectName = &DestinationString;
  ObjectAttributes_8.SecurityDescriptor = *(PVOID *)&v14[8];
  ObjectAttributes_8.SecurityQualityOfService = 0;
  v7 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes_8, &Name);
  if ( v7 >= 0 )
  {
    NtClose(SymbolicLinkHandle);
    v8 = 1;
  }
  else
  {
    v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v19 = L"CVssHardwareProviderWrapper::CreateSymbolicLinkW";
    v20 = L"CORHDELC";
    v21 = 3113;
    v22 = 1;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::Trace(v26, &v18, L"NtCreateSymbolicLinkObject failed with status %d", (unsigned int)v7);
    v8 = 0;
  }
  v9 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v26, v8);
  CVssSecurityDescriptor::~CVssSecurityDescriptor((CVssSecurityDescriptor *)&v14[8]);
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v11);
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v13);
  CVssFunctionTracer::~CVssFunctionTracer(v26);
  return v9;
}

```

## disassembly

```asm
0x1400b3648  mov     rax, rsp
0x1400b364b  mov     [rax+10h], rbx
0x1400b364f  mov     [rax+18h], rsi
0x1400b3653  mov     [rax+8], rcx
0x1400b3657  push    rbp
0x1400b3658  push    rdi
0x1400b3659  push    r13
0x1400b365b  lea     rbp, [rax-0E8h]
0x1400b3662  sub     rsp, 1D0h
0x1400b3669  mov     rsi, r8
0x1400b366c  mov     rbx, rdx
0x1400b366f  lea     r13, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b3676  mov     [rbp+0E0h+var_130], r13
0x1400b367a  lea     rax, aCvsshardwarepr_131; "CVssHardwareProviderWrapper::CreateSymb"...
0x1400b3681  mov     [rbp+0E0h+var_128], rax
0x1400b3685  lea     rax, aCorhdelc; "CORHDELC"
0x1400b368c  mov     [rbp+0E0h+var_120], rax
0x1400b3690  mov     [rbp+0E0h+var_118], 0BF9h
0x1400b3697  mov     [rbp+0E0h+var_114], 1
0x1400b369e  mov     [rbp+0E0h+var_110], 0FFh
0x1400b36a5  mov     [rbp+0E0h+var_90], 1000000h
0x1400b36ac  xor     edx, edx; Val
0x1400b36ae  lea     r8d, [rdx+78h]; Size
0x1400b36b2  lea     rcx, [rbp+0E0h+var_108]; void *
0x1400b36b6  call    memset_0
0x1400b36bb  xor     r8d, r8d
0x1400b36be  lea     rdx, [rbp+0E0h+var_130]
0x1400b36c2  lea     rcx, [rbp+0E0h+var_80]
0x1400b36c6  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400b36cb  nop
0x1400b36cc  xorps   xmm0, xmm0
0x1400b36cf  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x1400b36d3  xorps   xmm1, xmm1
0x1400b36d6  movups  xmmword ptr [rbp+0E0h+Name.Length], xmm1
0x1400b36da  movups  xmmword ptr [rsp+1E0h+ObjectAttributes+8], xmm0
0x1400b36df  movups  xmmword ptr [rsp+1E0h+ObjectAttributes+18h], xmm0
0x1400b36e4  movups  xmmword ptr [rbp+0E0h+ObjectAttributes+28h], xmm0
0x1400b36e8  mov     [rbp+0E0h+SymbolicLinkHandle], 0
0x1400b36f3  mov     r8d, 0Eh
0x1400b36f9  lea     rdx, aGlobalroot_2; "\\\\?\\GLOBALROOT"
0x1400b3700  mov     rcx, rbx
0x1400b3703  call    cs:__imp__o__wcsnicmp
0x1400b3709  lea     rdi, [rbx+1Ch]
0x1400b370d  test    eax, eax
0x1400b370f  cmovnz  rdi, rbx
0x1400b3713  mov     r8d, 0Eh
0x1400b3719  lea     rdx, aGlobalroot_2; "\\\\?\\GLOBALROOT"
0x1400b3720  mov     rcx, rsi
0x1400b3723  call    cs:__imp__o__wcsnicmp
0x1400b3729  lea     rbx, [rsi+1Ch]
0x1400b372d  test    eax, eax
0x1400b372f  cmovnz  rbx, rsi
0x1400b3733  mov     [rsp+1E0h+var_1A8], 0
0x1400b373c  lea     rsi, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x1400b3743  mov     [rsp+1E0h+var_1B0], rsi
0x1400b3748  mov     edx, 1; enum WELL_KNOWN_SID_TYPE
0x1400b374d  lea     rcx, [rsp+1E0h+var_1B0]; this
0x1400b3752  call    ?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z; CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)
0x1400b3757  mov     [rsp+1E0h+var_1B8], 0
0x1400b3760  mov     [rsp+1E0h+var_1C0], rsi
0x1400b3765  mov     edx, 7; enum WELL_KNOWN_SID_TYPE
0x1400b376a  lea     rcx, [rsp+1E0h+var_1C0]; this
0x1400b376f  call    ?CreateBasicSid@CAutoSid@@QEAAXW4WELL_KNOWN_SID_TYPE@@@Z; CAutoSid::CreateBasicSid(WELL_KNOWN_SID_TYPE)
0x1400b3774  xorps   xmm0, xmm0
0x1400b3777  movdqu  xmmword ptr [rsp+1E0h+var_1A8+8], xmm0
0x1400b377d  xorps   xmm1, xmm1
0x1400b3780  movdqu  [rsp+1E0h+var_198+8], xmm1
0x1400b3786  lea     rcx, [rsp+1E0h+var_1A8+8]; this
0x1400b378b  call    ?Initialize@CVssSecurityDescriptor@@QEAAJXZ; CVssSecurityDescriptor::Initialize(void)
0x1400b3790  mov     rdx, [rsp+1E0h+var_1A8]; void *
0x1400b3795  lea     rcx, [rsp+1E0h+var_1A8+8]; this
0x1400b379a  call    ?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Allow(void *,ulong,ulong)
0x1400b379f  mov     rdx, [rsp+1E0h+var_1B8]; void *
0x1400b37a4  lea     rcx, [rsp+1E0h+var_1A8+8]; this
0x1400b37a9  call    ?Allow@CVssSecurityDescriptor@@QEAAJPEAXKK@Z; CVssSecurityDescriptor::Allow(void *,ulong,ulong)
0x1400b37ae  mov     rdx, rdi; SourceString
0x1400b37b1  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x1400b37b5  call    cs:__imp_RtlInitUnicodeString
0x1400b37bb  mov     rdx, rbx; SourceString
0x1400b37be  lea     rcx, [rbp+0E0h+Name]; DestinationString
0x1400b37c2  call    cs:__imp_RtlInitUnicodeString
0x1400b37c8  mov     dword ptr [rsp+1E0h+ObjectAttributes+8], 30h ; '0'
0x1400b37d0  mov     qword ptr [rsp+1E0h+ObjectAttributes+10h], 0
0x1400b37d9  mov     dword ptr [rsp+1E0h+ObjectAttributes+20h], 50h ; 'P'
0x1400b37e1  lea     rax, [rbp+0E0h+DestinationString]
0x1400b37e5  mov     qword ptr [rsp+1E0h+ObjectAttributes+18h], rax
0x1400b37ea  mov     rax, [rsp+1E0h+var_1A8+8]
0x1400b37ef  mov     qword ptr [rbp+0E0h+ObjectAttributes+28h], rax
0x1400b37f3  mov     qword ptr [rbp+0E0h+ObjectAttributes+30h], 0
0x1400b37fb  lea     r9, [rbp+0E0h+Name]; Name
0x1400b37ff  lea     r8, [rsp+1E0h+ObjectAttributes+8]; ObjectAttributes
0x1400b3804  mov     edx, 0F0001h; DesiredAccess
0x1400b3809  lea     rcx, [rbp+0E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1400b3810  call    cs:__imp_NtCreateSymbolicLinkObject
0x1400b3816  mov     ebx, eax
0x1400b3818  test    eax, eax
0x1400b381a  jns     short loc_1400B387C
0x1400b381c  mov     [rbp+0E0h+var_130], r13
0x1400b3820  lea     rax, aCvsshardwarepr_131; "CVssHardwareProviderWrapper::CreateSymb"...
0x1400b3827  mov     [rbp+0E0h+var_128], rax
0x1400b382b  lea     rax, aCorhdelc; "CORHDELC"
0x1400b3832  mov     [rbp+0E0h+var_120], rax
0x1400b3836  mov     [rbp+0E0h+var_118], 0C29h
0x1400b383d  mov     [rbp+0E0h+var_114], 1
0x1400b3844  mov     [rbp+0E0h+var_110], 0FFh
0x1400b384b  mov     [rbp+0E0h+var_90], 1000000h
0x1400b3852  xor     edx, edx; Val
0x1400b3854  lea     r8d, [rdx+78h]; Size
0x1400b3858  lea     rcx, [rbp+0E0h+var_108]; void *
0x1400b385c  call    memset_0
0x1400b3861  mov     r9d, ebx
0x1400b3864  lea     r8, aNtcreatesymbol; "NtCreateSymbolicLinkObject failed with "...
0x1400b386b  lea     rdx, [rbp+0E0h+var_130]
0x1400b386f  lea     rcx, [rbp+0E0h+var_80]
0x1400b3873  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b3878  xor     edx, edx
0x1400b387a  jmp     short loc_1400B388B
0x1400b387c  mov     rcx, [rbp+0E0h+SymbolicLinkHandle]; Handle
0x1400b3883  call    cs:__imp_NtClose
0x1400b3889  mov     dl, 1; bool
0x1400b388b  lea     rcx, [rbp+0E0h+var_80]; this
0x1400b388f  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x1400b3894  mov     bl, al
0x1400b3896  lea     rcx, [rsp+1E0h+var_1A8+8]; this
0x1400b389b  call    ??1CVssSecurityDescriptor@@QEAA@XZ; CVssSecurityDescriptor::~CVssSecurityDescriptor(void)
0x1400b38a0  nop
0x1400b38a1  lea     rcx, [rsp+1E0h+var_1C0]
0x1400b38a6  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x1400b38ab  nop
0x1400b38ac  lea     rcx, [rsp+1E0h+var_1B0]
0x1400b38b1  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x1400b38b6  nop
0x1400b38b7  lea     rcx, [rbp+0E0h+var_80]; this
0x1400b38bb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400b38c0  mov     al, bl
0x1400b38c2  lea     r11, [rsp+1E0h+var_10]
0x1400b38ca  mov     rbx, [r11+28h]
0x1400b38ce  mov     rsi, [r11+30h]
0x1400b38d2  mov     rsp, r11
0x1400b38d5  pop     r13
0x1400b38d7  pop     rdi
0x1400b38d8  pop     rbp
0x1400b38d9  retn
```
