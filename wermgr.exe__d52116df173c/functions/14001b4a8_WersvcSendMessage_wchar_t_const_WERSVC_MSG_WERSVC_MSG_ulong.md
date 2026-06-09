# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x14001b4a8`
- end: `0x14001b847`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `927`
- prototype: `__int64 __fastcall(const wchar_t *, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x14001b130`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x14001b4a8`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x14001b623`
- `ntdll!NtOpenEvent` at `0x14001b623`
- `ntdll!RtlInitUnicodeString` at `0x14001b6f7`
- `ntdll!RtlInitUnicodeString` at `0x14001b6f7`
- `ntdll!NtClose` at `0x14001b669`
- `ntdll!NtClose` at `0x14001b818`
- `ntdll!NtClose` at `0x14001b669`
- `ntdll!NtClose` at `0x14001b818`
- `ntdll!NtQuerySystemInformation` at `0x14001b5c4`
- `ntdll!NtQuerySystemInformation` at `0x14001b5c4`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14001b54c`
- `ntdll!ZwQueryWnfStateNameInformation` at `0x14001b54c`
- `ntdll!ZwUpdateWnfStateData` at `0x14001b57b`
- `ntdll!ZwUpdateWnfStateData` at `0x14001b57b`
- `ntdll!EtwEventWriteNoRegistration` at `0x14001b59e`
- `ntdll!EtwEventWriteNoRegistration` at `0x14001b59e`
- `ntdll!NtWaitForSingleObject` at `0x14001b65c`
- `ntdll!NtWaitForSingleObject` at `0x14001b65c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001b6c2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14001b6c2`
- `ntdll!NtAlpcConnectPort` at `0x14001b775`
- `ntdll!NtAlpcConnectPort` at `0x14001b775`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14001b7d4`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x14001b7d4`
- `ntdll!RtlFreeSid` at `0x14001b809`
- `ntdll!RtlFreeSid` at `0x14001b809`

## string_xrefs

- `0x14001b5d9`: `\KernelObjects\SystemErrorPortReady`
- `0x14001b6ec`: `\WindowsErrorReportingServicePort`

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
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
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
  if ( (int)ZwQueryWnfStateNameInformation(WNF_WER_SERVICE_START, 1, 0, &EventHandle, 4) >= 0 && (_DWORD)EventHandle )
    v6 = (int)ZwUpdateWnfStateData(WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
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
0x14001b4a8  mov     [rsp-8+arg_0], rbx
0x14001b4ad  push    rbp
0x14001b4ae  push    rsi
0x14001b4af  push    rdi
0x14001b4b0  push    r12
0x14001b4b2  push    r13
0x14001b4b4  push    r14
0x14001b4b6  push    r15
0x14001b4b8  lea     rbp, [rsp-80h]
0x14001b4bd  sub     rsp, 180h
0x14001b4c4  mov     rax, cs:__security_cookie
0x14001b4cb  xor     rax, rsp
0x14001b4ce  mov     [rbp+0B0h+var_40], rax
0x14001b4d2  xorps   xmm0, xmm0
0x14001b4d5  mov     word ptr [rbp+0B0h+IdentifierAuthority.Value+4], 500h
0x14001b4db  xor     r12d, r12d
0x14001b4de  lea     rcx, [rbp+0B0h+var_90]; void *
0x14001b4e2  mov     r14, r8
0x14001b4e5  mov     dword ptr [rbp+0B0h+IdentifierAuthority.Value], r12d
0x14001b4e9  mov     r15, rdx
0x14001b4ec  xor     edx, edx; Val
0x14001b4ee  movups  [rbp+0B0h+var_108], xmm0
0x14001b4f2  lea     r8d, [r12+48h]; Size
0x14001b4f7  movups  [rbp+0B0h+var_F8], xmm0
0x14001b4fb  movups  [rbp+0B0h+var_E8], xmm0
0x14001b4ff  call    memset_0
0x14001b504  xorps   xmm0, xmm0
0x14001b507  mov     [rbp+0B0h+var_120], r12
0x14001b50b  lea     edi, [r12+1]
0x14001b510  mov     [rbp+0B0h+Handle], r12
0x14001b514  mov     edx, edi
0x14001b516  mov     [rsp+1B0h+var_138], r12
0x14001b51b  lea     r9, [rsp+1B0h+EventHandle]
0x14001b520  mov     [rsp+1B0h+var_140], r12
0x14001b525  xor     r8d, r8d
0x14001b528  mov     [rsp+1B0h+SystemInformation], r12
0x14001b52d  lea     rcx, WNF_WER_SERVICE_START
0x14001b534  mov     dword ptr [rsp+1B0h+EventHandle], r12d
0x14001b539  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x14001b53d  mov     ebx, r12d
0x14001b540  mov     [rsp+1B0h+SubAuthority2], 4
0x14001b548  movups  [rbp+0B0h+var_A0], xmm0
0x14001b54c  call    cs:__imp_ZwQueryWnfStateNameInformation
0x14001b552  test    eax, eax
0x14001b554  js      short loc_14001B586
0x14001b556  cmp     dword ptr [rsp+1B0h+EventHandle], r12d
0x14001b55b  jz      short loc_14001B586
0x14001b55d  mov     [rsp+1B0h+SubAuthority4], r12d
0x14001b562  lea     rcx, WNF_WER_SERVICE_START
0x14001b569  mov     [rsp+1B0h+SubAuthority3], r12d
0x14001b56e  xor     r9d, r9d
0x14001b571  xor     r8d, r8d
0x14001b574  mov     qword ptr [rsp+1B0h+SubAuthority2], r12
0x14001b579  xor     edx, edx
0x14001b57b  call    cs:__imp_ZwUpdateWnfStateData
0x14001b581  test    eax, eax
0x14001b583  cmovns  ebx, edi
0x14001b586  xorps   xmm0, xmm0
0x14001b589  lea     rdx, [rbp+0B0h+var_A0]
0x14001b58d  xor     r9d, r9d
0x14001b590  lea     rcx, ?WerSvcTriggerGuid@?1??SignalStartWerSvc@@YAJXZ@4U_GUID@@B; _GUID const `SignalStartWerSvc(void)'::`2'::WerSvcTriggerGuid
0x14001b597  xor     r8d, r8d
0x14001b59a  movups  [rbp+0B0h+var_A0], xmm0
0x14001b59e  call    cs:__imp_EtwEventWriteNoRegistration
0x14001b5a4  test    eax, eax
0x14001b5a6  lea     ecx, [rbx+1]
0x14001b5a9  cmovnz  ecx, ebx
0x14001b5ac  test    ecx, ecx
0x14001b5ae  jz      loc_14001B7FA
0x14001b5b4  xor     r9d, r9d; ReturnLength
0x14001b5b7  lea     rdx, [rsp+1B0h+SystemInformation]; SystemInformation
0x14001b5bc  lea     r8d, [r9+8]; SystemInformationLength
0x14001b5c0  lea     ecx, [r9+73h]; SystemInformationClass
0x14001b5c4  call    cs:__imp_NtQuerySystemInformation
0x14001b5ca  mov     ebx, eax
0x14001b5cc  test    eax, eax
0x14001b5ce  js      loc_14001B7FF
0x14001b5d4  movsxd  rsi, dword ptr [rsp+1B0h+SystemInformation]
0x14001b5d9  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x14001b5e0  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x14001b5e4  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x14001b5e8  lea     rax, [rbp+0B0h+var_A0]
0x14001b5ec  mov     qword ptr [rbp+0B0h+var_A0], 480046h
0x14001b5f4  xorps   xmm0, xmm0
0x14001b5f7  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14001b5fb  mov     edx, 100001h; DesiredAccess
0x14001b600  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x14001b608  lea     rcx, [rsp+1B0h+EventHandle]; EventHandle
0x14001b60d  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], r12
0x14001b611  mov     [rsp+1B0h+EventHandle], r12
0x14001b616  mov     [rbp+0B0h+var_128], r12
0x14001b61a  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x14001b61e  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001b623  call    cs:__imp_NtOpenEvent
0x14001b629  mov     ebx, eax
0x14001b62b  test    eax, eax
0x14001b62d  js      loc_14001B7FF
0x14001b633  cmp     esi, 0FFFFFFFFh
0x14001b636  jnz     short loc_14001B63D
0x14001b638  mov     dl, dil
0x14001b63b  jmp     short loc_14001B64B
0x14001b63d  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x14001b644  mov     dl, r12b
0x14001b647  mov     [rbp+0B0h+var_128], rcx
0x14001b64b  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14001b650  lea     r8, [rbp+0B0h+var_128]
0x14001b654  test    dl, dl
0x14001b656  cmovnz  r8, r12; Timeout
0x14001b65a  xor     edx, edx; Alertable
0x14001b65c  call    cs:__imp_NtWaitForSingleObject
0x14001b662  mov     rcx, [rsp+1B0h+EventHandle]; Handle
0x14001b667  mov     ebx, eax
0x14001b669  call    cs:__imp_NtClose
0x14001b66f  test    ebx, ebx
0x14001b671  js      loc_14001B7FF
0x14001b677  mov     r13d, 102h
0x14001b67d  cmp     ebx, r13d
0x14001b680  jnz     short loc_14001B68C
0x14001b682  mov     ebx, 0C0000353h
0x14001b687  jmp     loc_14001B7FF
0x14001b68c  lea     rax, [rsp+1B0h+var_138]
0x14001b691  xor     r9d, r9d; SubAuthority1
0x14001b694  mov     [rsp+1B0h+Sid], rax; Sid
0x14001b699  lea     rcx, [rbp+0B0h+IdentifierAuthority]; IdentifierAuthority
0x14001b69d  mov     [rsp+1B0h+SubAuthority7], r12d; SubAuthority7
0x14001b6a2  mov     dl, dil; SubAuthorityCount
0x14001b6a5  mov     [rsp+1B0h+SubAuthority6], r12d; SubAuthority6
0x14001b6aa  mov     [rsp+1B0h+SubAuthority5], r12d; SubAuthority5
0x14001b6af  lea     r8d, [r9+12h]; SubAuthority0
0x14001b6b3  mov     [rsp+1B0h+SubAuthority4], r12d; SubAuthority4
0x14001b6b8  mov     [rsp+1B0h+SubAuthority3], r12d; SubAuthority3
0x14001b6bd  mov     [rsp+1B0h+SubAuthority2], r12d; SubAuthority2
0x14001b6c2  call    cs:__imp_RtlAllocateAndInitializeSid
0x14001b6c8  mov     ebx, eax
0x14001b6ca  test    eax, eax
0x14001b6cc  js      loc_14001B7FF
0x14001b6d2  cmp     dword ptr [rsp+1B0h+SystemInformation+4], 0FFFFFFFFh
0x14001b6d7  jz      short loc_14001B6EC
0x14001b6d9  movsxd  rax, dword ptr [rsp+1B0h+SystemInformation+4]
0x14001b6de  mov     dil, r12b
0x14001b6e1  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x14001b6e8  mov     [rbp+0B0h+var_120], rcx
0x14001b6ec  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x14001b6f3  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x14001b6f7  call    cs:__imp_RtlInitUnicodeString
0x14001b6fd  xor     edx, edx; Val
0x14001b6ff  mov     dword ptr [rbp+0B0h+var_108], 30h ; '0'
0x14001b706  xorps   xmm0, xmm0
0x14001b709  mov     qword ptr [rbp+0B0h+var_108+8], r12
0x14001b70d  lea     rcx, [rbp+0B0h+var_90]; void *
0x14001b711  mov     dword ptr [rbp+0B0h+var_F8+8], r12d
0x14001b715  mov     qword ptr [rbp+0B0h+var_F8], r12
0x14001b719  lea     r8d, [rdx+48h]; Size
0x14001b71d  movdqu  [rbp+0B0h+var_E8], xmm0
0x14001b722  call    memset_0
0x14001b727  mov     rax, [rsp+1B0h+var_138]
0x14001b72c  lea     rsi, [rbp+0B0h+var_120]
0x14001b730  test    dil, dil
0x14001b733  mov     [rbp+0B0h+var_80], 578h
0x14001b73b  lea     r9, [rbp+0B0h+var_90]
0x14001b73f  cmovnz  rsi, r12
0x14001b743  lea     r8, [rbp+0B0h+var_108]
0x14001b747  mov     [rsp+1B0h+Sid], rsi
0x14001b74c  lea     rdx, [rbp+0B0h+DestinationString]
0x14001b750  mov     qword ptr [rsp+1B0h+SubAuthority7], r12
0x14001b755  lea     rcx, [rbp+0B0h+Handle]
0x14001b759  mov     qword ptr [rsp+1B0h+SubAuthority6], r12
0x14001b75e  mov     qword ptr [rsp+1B0h+SubAuthority5], r12
0x14001b763  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x14001b768  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14001b76d  mov     [rsp+1B0h+SubAuthority2], 20000h
0x14001b775  call    cs:__imp_NtAlpcConnectPort
0x14001b77b  mov     ebx, eax
0x14001b77d  test    eax, eax
0x14001b77f  js      short loc_14001B7FF
0x14001b781  cmp     eax, r13d
0x14001b784  jz      loc_14001B682
0x14001b78a  lea     rcx, [r14+4]; void *
0x14001b78e  xor     edx, edx; Val
0x14001b790  mov     r8d, 574h; Size
0x14001b796  call    memset_0
0x14001b79b  mov     rcx, [rbp+0B0h+Handle]
0x14001b79f  lea     rax, [rsp+1B0h+var_140]
0x14001b7a4  mov     qword ptr [rsp+1B0h+SubAuthority5], rsi
0x14001b7a9  mov     edi, 578h
0x14001b7ae  mov     qword ptr [rsp+1B0h+SubAuthority4], r12
0x14001b7b3  xor     r9d, r9d
0x14001b7b6  mov     qword ptr [rsp+1B0h+SubAuthority3], rax
0x14001b7bb  mov     r8, r15
0x14001b7be  mov     edx, 20000h
0x14001b7c3  mov     qword ptr [rsp+1B0h+SubAuthority2], r14
0x14001b7c8  mov     dword ptr [r14], 5780550h
0x14001b7cf  mov     [rsp+1B0h+var_140], rdi
0x14001b7d4  call    cs:__imp_NtAlpcSendWaitReceivePort
0x14001b7da  mov     ebx, eax
0x14001b7dc  test    eax, eax
0x14001b7de  js      short loc_14001B7FF
0x14001b7e0  cmp     eax, r13d
0x14001b7e3  jz      short loc_14001B7FF
0x14001b7e5  mov     rax, [rsp+1B0h+var_140]
0x14001b7ea  sub     rax, rdi
0x14001b7ed  neg     rax
0x14001b7f0  sbb     ebx, ebx
0x14001b7f2  and     ebx, 0C000021Fh
0x14001b7f8  jmp     short loc_14001B7FF
0x14001b7fa  mov     ebx, 0C0000080h
0x14001b7ff  mov     rcx, [rsp+1B0h+var_138]; Sid
0x14001b804  test    rcx, rcx
0x14001b807  jz      short loc_14001B80F
0x14001b809  call    cs:__imp_RtlFreeSid
0x14001b80f  mov     rcx, [rbp+0B0h+Handle]; Handle
0x14001b813  test    rcx, rcx
0x14001b816  jz      short loc_14001B81E
0x14001b818  call    cs:__imp_NtClose
0x14001b81e  mov     eax, ebx
0x14001b820  mov     rcx, [rbp+0B0h+var_40]
0x14001b824  xor     rcx, rsp; StackCookie
0x14001b827  call    __security_check_cookie
0x14001b82c  mov     rbx, [rsp+1B0h+arg_0]
0x14001b834  add     rsp, 180h
0x14001b83b  pop     r15
0x14001b83d  pop     r14
0x14001b83f  pop     r13
0x14001b841  pop     r12
0x14001b843  pop     rdi
0x14001b844  pop     rsi
0x14001b845  pop     rbp
0x14001b846  retn
```
