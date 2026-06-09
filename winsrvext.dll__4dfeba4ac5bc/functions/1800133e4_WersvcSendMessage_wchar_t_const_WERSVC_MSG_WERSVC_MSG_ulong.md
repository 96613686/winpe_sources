# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x1800133e4`
- end: `0x1800137d6`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `1010`
- prototype: `__int64 __fastcall(const wchar_t *, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180012ef8`

## callees

- `0x1800133e4`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x1800136e7`
- `ntdll!NtAlpcConnectPort` at `0x1800136e7`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180013750`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180013750`
- `ntdll!NtOpenEvent` at `0x180013577`
- `ntdll!NtOpenEvent` at `0x180013577`
- `ntdll!NtQuerySystemInformation` at `0x180013512`
- `ntdll!NtQuerySystemInformation` at `0x180013512`
- `ntdll!NtWaitForSingleObject` at `0x1800135b6`
- `ntdll!NtWaitForSingleObject` at `0x1800135b6`
- `ntdll!RtlFreeSid` at `0x18001378b`
- `ntdll!RtlFreeSid` at `0x18001378b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180013628`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180013628`
- `ntdll!RtlInitUnicodeString` at `0x180013663`
- `ntdll!RtlInitUnicodeString` at `0x180013663`
- `ntdll!NtClose` at `0x1800135c9`
- `ntdll!NtClose` at `0x1800137a0`
- `ntdll!NtClose` at `0x1800135c9`
- `ntdll!NtClose` at `0x1800137a0`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x180013488`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x180013488`
- `ntdll!ZwUpdateWnfStateData` at `0x1800134bd`
- `ntdll!ZwUpdateWnfStateData` at `0x1800134bd`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800134e6`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800134e6`

## string_xrefs

- `0x180013658`: `\WindowsErrorReportingServicePort`
- `0x18001352d`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(const wchar_t *a1, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  char v5; // di
  BOOL v6; // ebx
  int v7; // eax
  int v8; // ecx
  NTSTATUS v9; // ebx
  __int64 v10; // rsi
  char v11; // dl
  union _LARGE_INTEGER *v12; // r8
  __int64 *v13; // rsi
  int v14; // eax
  HANDLE v15; // rcx
  int v16; // eax
  void *EventHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v26; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v27; // [rsp+B8h] [rbp-48h]
  __int128 v28; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+108h] [rbp+8h] BYREF
  __int128 v31; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v32[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v33; // [rsp+130h] [rbp+30h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v32, 0, 0x48u);
  v24 = 0;
  v5 = 1;
  Handle = 0;
  Sid = 0;
  v20 = 0;
  SystemInformation = 0;
  LODWORD(EventHandle) = 0;
  DestinationString = 0;
  v6 = 0;
  v31 = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v6 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  v31 = 0;
  v7 = EtwEventWriteNoRegistration(&`SignalStartWerSvc'::`2'::WerSvcTriggerGuid, &v31, 0, 0);
  v8 = v6 + 1;
  if ( v7 )
    v8 = v6;
  if ( v8 )
  {
    v9 = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( v9 >= 0 )
    {
      v10 = (int)SystemInformation;
      *((_QWORD *)&v31 + 1) = L"\\KernelObjects\\SystemErrorPortReady";
      *(_QWORD *)&v31 = 4718662;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.Attributes, 0, 24);
      EventHandle = 0;
      v23 = 0;
      ObjectAttributes.RootDirectory = 0;
      v9 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
      if ( v9 >= 0 )
      {
        if ( (_DWORD)v10 == -1 )
        {
          v11 = 1;
        }
        else
        {
          v11 = 0;
          v23 = -10000 * v10;
        }
        v12 = (union _LARGE_INTEGER *)&v23;
        if ( v11 )
          v12 = 0;
        v9 = NtWaitForSingleObject(EventHandle, 0, v12);
        NtClose(EventHandle);
        if ( v9 >= 0 )
        {
          if ( v9 == 258 )
          {
LABEL_16:
            v9 = -1073740973;
            goto LABEL_28;
          }
          v9 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
          if ( v9 >= 0 )
          {
            if ( HIDWORD(SystemInformation) != -1 )
            {
              v5 = 0;
              v24 = -10000LL * SHIDWORD(SystemInformation);
            }
            RtlInitUnicodeString(&DestinationString, L"\\WindowsErrorReportingServicePort");
            LODWORD(v26) = 48;
            *((_QWORD *)&v26 + 1) = 0;
            DWORD2(v27) = 0;
            *(_QWORD *)&v27 = 0;
            v28 = 0;
            memset_0(v32, 0, 0x48u);
            v13 = &v24;
            v33 = 1400;
            if ( v5 )
              v13 = 0;
            v14 = NtAlpcConnectPort(&Handle, &DestinationString, &v26, v32, 0x20000, Sid, 0, 0, 0, 0, v13);
            v9 = v14;
            if ( v14 >= 0 )
            {
              if ( v14 == 258 )
                goto LABEL_16;
              memset_0((char *)a3 + 4, 0, 0x574u);
              v15 = Handle;
              *(_DWORD *)a3 = 91751760;
              v20 = 1400;
              v16 = NtAlpcSendWaitReceivePort(v15, 0x20000, a2, 0, a3, &v20, 0, v13);
              v9 = v16;
              if ( v16 >= 0 && v16 != 258 )
                v9 = v20 != 1400 ? 0xC000021F : 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v9 = -1073741696;
  }
LABEL_28:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800133e4  mov     [rsp-8+arg_0], rbx
0x1800133e9  push    rbp
0x1800133ea  push    rsi
0x1800133eb  push    rdi
0x1800133ec  push    r12
0x1800133ee  push    r13
0x1800133f0  push    r14
0x1800133f2  push    r15
0x1800133f4  lea     rbp, [rsp-80h]
0x1800133f9  sub     rsp, 180h
0x180013400  mov     rax, cs:__security_cookie
0x180013407  xor     rax, rsp
0x18001340a  mov     [rbp+0B0h+var_40], rax
0x18001340e  xorps   xmm0, xmm0
0x180013411  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x180013417  xor     r12d, r12d
0x18001341a  lea     rcx, [rbp+0B0h+var_90]; void *
0x18001341e  mov     r14, r8
0x180013421  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r12d
0x180013425  mov     r15, rdx
0x180013428  xor     edx, edx; Val
0x18001342a  movups  [rbp+0B0h+var_108], xmm0
0x18001342e  lea     r8d, [r12+48h]; Size
0x180013433  movups  [rbp+0B0h+var_F8], xmm0
0x180013437  movups  [rbp+0B0h+var_E8], xmm0
0x18001343b  call    memset_0
0x180013440  xorps   xmm0, xmm0
0x180013443  mov     [rbp+0B0h+var_120], r12
0x180013447  lea     edi, [r12+1]
0x18001344c  mov     [rbp+0B0h+Handle], r12
0x180013450  mov     edx, edi
0x180013452  mov     [rsp+1B0h+var_138], r12
0x180013457  lea     r9, [rsp+1B0h+EventHandle]
0x18001345c  mov     [rsp+1B0h+var_140], r12
0x180013461  xor     r8d, r8d
0x180013464  mov     [rsp+1B0h+SystemInformation], r12
0x180013469  lea     rcx, WNF_WER_SERVICE_START
0x180013470  mov     dword ptr [rsp+1B0h+EventHandle], r12d
0x180013475  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180013479  mov     ebx, r12d
0x18001347c  mov     [rsp+1B0h+SubAuthority2], 4
0x180013484  movups  [rbp+0B0h+var_A0], xmm0
0x180013488  call    cs:__imp_ZwQueryWnfStateNameInformation
0x18001348f  nop     dword ptr [rax+rax+00h]
0x180013494  test    eax, eax
0x180013496  js      short loc_1800134CE
0x180013498  cmp     dword ptr [rsp+1B0h+EventHandle], r12d
0x18001349d  jz      short loc_1800134CE
0x18001349f  mov     [rsp+1B0h+SubAuthority4], r12d
0x1800134a4  lea     rcx, WNF_WER_SERVICE_START
0x1800134ab  mov     [rsp+1B0h+SubAuthority3], r12d
0x1800134b0  xor     r9d, r9d
0x1800134b3  xor     r8d, r8d
0x1800134b6  mov     qword ptr [rsp+1B0h+SubAuthority2], r12
0x1800134bb  xor     edx, edx
0x1800134bd  call    cs:__imp_ZwUpdateWnfStateData
0x1800134c4  nop     dword ptr [rax+rax+00h]
0x1800134c9  test    eax, eax
0x1800134cb  cmovns  ebx, edi
0x1800134ce  xorps   xmm0, xmm0
0x1800134d1  lea     rdx, [rbp+0B0h+var_A0]
0x1800134d5  xor     r9d, r9d
0x1800134d8  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x1800134df  xor     r8d, r8d
0x1800134e2  movups  [rbp+0B0h+var_A0], xmm0
0x1800134e6  call    cs:__imp_EtwEventWriteNoRegistration
0x1800134ed  nop     dword ptr [rax+rax+00h]
0x1800134f2  test    eax, eax
0x1800134f4  lea     ecx, [rbx+1]
0x1800134f7  cmovnz  ecx, ebx
0x1800134fa  test    ecx, ecx
0x1800134fc  jz      loc_18001377C
0x180013502  xor     r9d, r9d; ReturnLength
0x180013505  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x18001350a  lea     r8d, [r9+8]; SystemInformationLength
0x18001350e  lea     ecx, [r9+73h]; SystemInformationClass
0x180013512  call    cs:__imp_NtQuerySystemInformation
0x180013519  nop     dword ptr [rax+rax+00h]
0x18001351e  mov     ebx, eax
0x180013520  test    eax, eax
0x180013522  js      loc_180013781
0x180013528  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x18001352d  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x180013534  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x180013538  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x18001353c  lea     rax, [rbp+0B0h+var_A0]
0x180013540  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x180013548  xorps   xmm0, xmm0
0x18001354b  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x18001354f  mov     edx, 100001h; DesiredAccess
0x180013554  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x18001355c  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x180013561  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r12
0x180013565  mov     [rsp+1B0h+EventHandle], r12
0x18001356a  mov     [rbp+0B0h+var_128], r12
0x18001356e  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x180013572  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013577  call    cs:__imp_NtOpenEvent
0x18001357e  nop     dword ptr [rax+rax+00h]
0x180013583  mov     ebx, eax
0x180013585  test    eax, eax
0x180013587  js      loc_180013781
0x18001358d  cmp     esi, 0FFFFFFFFh
0x180013590  jnz     short loc_180013597
0x180013592  mov     dl, dil
0x180013595  jmp     short loc_1800135A5
0x180013597  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x18001359e  mov     dl, r12b
0x1800135a1  mov     [rbp+0B0h+var_128], rcx
0x1800135a5  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x1800135aa  lea     r8, [rbp+0B0h+var_128]
0x1800135ae  test    dl, dl
0x1800135b0  cmovnz  r8, r12; Timeout
0x1800135b4  xor     edx, edx; Alertable
0x1800135b6  call    cs:__imp_NtWaitForSingleObject
0x1800135bd  nop     dword ptr [rax+rax+00h]
0x1800135c2  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x1800135c7  mov     ebx, eax
0x1800135c9  call    cs:__imp_NtClose
0x1800135d0  nop     dword ptr [rax+rax+00h]
0x1800135d5  test    ebx, ebx
0x1800135d7  js      loc_180013781
0x1800135dd  mov     r13d, 102h
0x1800135e3  cmp     ebx, r13d
0x1800135e6  jnz     short loc_1800135F2
0x1800135e8  mov     ebx, 0C0000353h
0x1800135ed  jmp     loc_180013781
0x1800135f2  lea     rax, [rsp+1B0h+var_138]
0x1800135f7  xor     r9d, r9d; SubAuthority1
0x1800135fa  mov     [rsp+1B0h+Sid], rax; Sid
0x1800135ff  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x180013603  mov     [rsp+1B0h+SubAuthority7], r12d; SubAuthority7
0x180013608  mov     dl, dil; SubAuthorityCount
0x18001360b  mov     [rsp+1B0h+SubAuthority6], r12d; SubAuthority6
0x180013610  mov     [rsp+1B0h+SubAuthority5], r12d; SubAuthority5
0x180013615  lea     r8d, [r9+12h]; SubAuthority0
0x180013619  mov     [rsp+1B0h+SubAuthority4], r12d; SubAuthority4
0x18001361e  mov     [rsp+1B0h+SubAuthority3], r12d; SubAuthority3
0x180013623  mov     [rsp+1B0h+SubAuthority2], r12d; SubAuthority2
0x180013628  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001362f  nop     dword ptr [rax+rax+00h]
0x180013634  mov     ebx, eax
0x180013636  test    eax, eax
0x180013638  js      loc_180013781
0x18001363e  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x180013643  jz      short loc_180013658
0x180013645  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x18001364a  mov     dil, r12b
0x18001364d  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180013654  mov     [rbp+0B0h+var_120], rcx
0x180013658  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18001365f  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180013663  call    cs:__imp_RtlInitUnicodeString
0x18001366a  nop     dword ptr [rax+rax+00h]
0x18001366f  xor     edx, edx; Val
0x180013671  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x180013678  xorps   xmm0, xmm0
0x18001367b  mov     qword ptr [rbp+0B0h+var_108+8], r12
0x18001367f  lea     rcx, [rbp+0B0h+var_90]; void *
0x180013683  mov     dword ptr [rbp+0B0h+var_F8+8], r12d
0x180013687  mov     qword ptr [rbp+0B0h+var_F8], r12
0x18001368b  lea     r8d, [rdx+48h]; Size
0x18001368f  movdqu  [rbp+0B0h+var_E8], xmm0
0x180013694  call    memset_0
0x180013699  mov     rax, [rsp+1B0h+var_138]
0x18001369e  lea     rsi, [rbp+0B0h+var_120]
0x1800136a2  test    dil, dil
0x1800136a5  mov     [rbp+0B0h+var_80], 578h
0x1800136ad  lea     r9, [rbp+0B0h+var_90]
0x1800136b1  cmovnz  rsi, r12
0x1800136b5  lea     r8, [rbp+0B0h+var_108]
0x1800136b9  mov     [rsp+1B0h+Sid], rsi
0x1800136be  lea     rdx, [rbp+0B0h+DestinationString]
0x1800136c2  mov     qword ptr [rsp+1B0h+SubAuthority7], r12
0x1800136c7  lea     rcx, [rbp+0B0h+Handle]
0x1800136cb  mov     qword ptr [rsp+1B0h+SubAuthority6], r12
0x1800136d0  mov     qword ptr [rsp+1B0h+SubAuthority5], r12
0x1800136d5  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x1800136da  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x1800136df  mov     [rsp+1B0h+SubAuthority2], 20000h
0x1800136e7  call    cs:__imp_NtAlpcConnectPort
0x1800136ee  nop     dword ptr [rax+rax+00h]
0x1800136f3  mov     ebx, eax
0x1800136f5  test    eax, eax
0x1800136f7  js      loc_180013781
0x1800136fd  cmp     eax, r13d
0x180013700  jz      loc_1800135E8
0x180013706  lea     rcx, [r14+4]; void *
0x18001370a  xor     edx, edx; Val
0x18001370c  mov     r8d, 574h; Size
0x180013712  call    memset_0
0x180013717  mov     rcx, [rbp+0B0h+Handle]
0x18001371b  lea     rax, [rsp+1B0h+var_140]
0x180013720  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x180013725  mov     edi, 578h
0x18001372a  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x18001372f  xor     r9d, r9d
0x180013732  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x180013737  mov     r8, r15
0x18001373a  mov     edx, 20000h
0x18001373f  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x180013744  mov     dword ptr [r14], 5780550h
0x18001374b  mov     [rsp+1B0h+var_140], rdi
0x180013750  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180013757  nop     dword ptr [rax+rax+00h]
0x18001375c  mov     ebx, eax
0x18001375e  test    eax, eax
0x180013760  js      short loc_180013781
0x180013762  cmp     eax, r13d
0x180013765  jz      short loc_180013781
0x180013767  mov     rax, [rsp+1B0h+var_140]
0x18001376c  sub     rax, rdi
0x18001376f  neg     rax
0x180013772  sbb     ebx, ebx
0x180013774  and     ebx, 0C000021Fh
0x18001377a  jmp     short loc_180013781
0x18001377c  mov     ebx, 0C0000080h
0x180013781  mov     rcx, [rsp+1B0h+var_138]; Sid
0x180013786  test    rcx, rcx
0x180013789  jz      short loc_180013797
0x18001378b  call    cs:__imp_RtlFreeSid
0x180013792  nop     dword ptr [rax+rax+00h]
0x180013797  mov     rcx, [rbp+0B0h+Handle]; Handle
0x18001379b  test    rcx, rcx
0x18001379e  jz      short loc_1800137AC
0x1800137a0  call    cs:__imp_NtClose
0x1800137a7  nop     dword ptr [rax+rax+00h]
0x1800137ac  mov     eax, ebx
0x1800137ae  mov     rcx, [rbp+0B0h+var_40]
0x1800137b2  xor     rcx, rsp; StackCookie
0x1800137b5  call    __security_check_cookie
0x1800137ba  mov     rbx, [rsp+1B0h+arg_0]
0x1800137c2  add     rsp, 180h
0x1800137c9  pop     r15
0x1800137cb  pop     r14
0x1800137cd  pop     r13
0x1800137cf  pop     r12
0x1800137d1  pop     rdi
0x1800137d2  pop     rsi
0x1800137d3  pop     rbp
0x1800137d4  retn
```
