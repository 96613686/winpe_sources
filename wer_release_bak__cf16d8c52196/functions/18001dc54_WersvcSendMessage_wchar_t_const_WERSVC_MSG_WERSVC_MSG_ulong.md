# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18001dc54`
- end: `0x18001ded5`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `641`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001dad8`
- `0x18001dc24`
- `0x180036a28`
- `0x18003cd98`
- `0x180049588`

## callees

- `0x18001dc54`
- `0x18001dedc`
- `0x180029810`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18001dcf0`
- `ntdll!NtQuerySystemInformation` at `0x18001dcf0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001dd5d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001dd5d`
- `ntdll!NtAlpcConnectPort` at `0x18001de12`
- `ntdll!NtAlpcConnectPort` at `0x18001de12`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001de70`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001de70`
- `ntdll!RtlFreeSid` at `0x18001de9d`
- `ntdll!RtlFreeSid` at `0x18001de9d`
- `ntdll!RtlInitUnicodeString` at `0x18001dd91`
- `ntdll!RtlInitUnicodeString` at `0x18001dd91`
- `ntdll!NtClose` at `0x18001dead`
- `ntdll!NtClose` at `0x18001dead`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(PCWSTR SourceString, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3, int a4)
{
  NTSTATUS started; // ebx
  int v9; // eax
  char v10; // si
  __int64 *v11; // rdi
  int v12; // eax
  HANDLE v13; // rcx
  int v14; // eax
  __int64 SystemInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-58h]
  __int128 v24; // [rsp+B8h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v26[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-20h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v26, 0, 0x48u);
  v20 = 0;
  DestinationString = 0;
  Handle = 0;
  Sid = 0;
  v17 = 0;
  SystemInformation = 0;
  started = SignalStartWerSvc();
  if ( started >= 0 )
  {
    started = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( started >= 0 )
    {
      v9 = WaitForWerSvc(SystemInformation);
      started = v9;
      if ( v9 >= 0 )
      {
        if ( v9 == 258 )
        {
LABEL_5:
          started = -1073740973;
          goto LABEL_18;
        }
        v10 = 1;
        started = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
        if ( started >= 0 )
        {
          if ( !a4 )
            a4 = HIDWORD(SystemInformation);
          if ( a4 != -1 )
          {
            v10 = 0;
            v20 = -10000LL * a4;
          }
          RtlInitUnicodeString(&DestinationString, SourceString);
          LODWORD(v22) = 48;
          *((_QWORD *)&v22 + 1) = 0;
          DWORD2(v23) = 0;
          *(_QWORD *)&v23 = 0;
          v24 = 0;
          memset_0(v26, 0, 0x48u);
          v11 = &v20;
          if ( v10 )
            v11 = 0;
          v27 = 1400;
          v12 = NtAlpcConnectPort(&Handle, &DestinationString, &v22, v26, 0x20000, Sid, 0, 0, 0, 0, v11);
          started = v12;
          if ( v12 >= 0 )
          {
            if ( v12 == 258 )
              goto LABEL_5;
            memset_0((char *)a3 + 4, 0, 0x574u);
            v13 = Handle;
            *(_DWORD *)a3 = 91751760;
            v17 = 1400;
            v14 = NtAlpcSendWaitReceivePort(v13, 0x20000, a2, 0, a3, &v17, 0, v11);
            started = v14;
            if ( v14 >= 0 && v14 != 258 )
              started = v17 != 1400 ? 0xC000021F : 0;
          }
        }
      }
    }
  }
LABEL_18:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001dc54  push    rbp
0x18001dc56  push    rbx
0x18001dc57  push    rsi
0x18001dc58  push    rdi
0x18001dc59  push    r12
0x18001dc5b  push    r13
0x18001dc5d  push    r14
0x18001dc5f  push    r15
0x18001dc61  lea     rbp, [rsp-38h]
0x18001dc66  sub     rsp, 138h
0x18001dc6d  mov     rax, cs:__security_cookie
0x18001dc74  xor     rax, rsp
0x18001dc77  mov     [rbp+70h+var_50], rax
0x18001dc7b  xorps   xmm0, xmm0
0x18001dc7e  mov     word ptr [rbp+70h+IdentifierAuthority.Value+4], 500h
0x18001dc84  xor     r13d, r13d
0x18001dc87  mov     r14, r8
0x18001dc8a  mov     r15, rdx
0x18001dc8d  mov     dword ptr [rbp+70h+IdentifierAuthority.Value], r13d
0x18001dc91  mov     r12, rcx
0x18001dc94  xor     edx, edx; Val
0x18001dc96  lea     rcx, [rbp+70h+var_A0]; void *
0x18001dc9a  mov     edi, r9d
0x18001dc9d  lea     r8d, [r13+48h]; Size
0x18001dca1  movups  [rbp+70h+var_D8], xmm0
0x18001dca5  movups  [rbp+70h+var_C8], xmm0
0x18001dca9  movups  [rbp+70h+var_B8], xmm0
0x18001dcad  call    memset_0
0x18001dcb2  xorps   xmm0, xmm0
0x18001dcb5  mov     [rbp+70h+var_F0], r13
0x18001dcb9  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18001dcbd  mov     [rsp+170h+Handle], r13
0x18001dcc2  mov     [rsp+170h+var_100], r13
0x18001dcc7  mov     [rsp+170h+var_108], r13
0x18001dccc  mov     [rsp+170h+SystemInformation], r13
0x18001dcd1  call    ?SignalStartWerSvc@@YAJXZ; SignalStartWerSvc(void)
0x18001dcd6  mov     ebx, eax
0x18001dcd8  test    eax, eax
0x18001dcda  js      loc_18001DE93
0x18001dce0  xor     r9d, r9d; ReturnLength
0x18001dce3  lea     r8d, [r13+8]; SystemInformationLength
0x18001dce7  lea     rdx, [rsp+170h+SystemInformation]; SystemInformation
0x18001dcec  lea     ecx, [r13+73h]; SystemInformationClass
0x18001dcf0  call    cs:__imp_NtQuerySystemInformation
0x18001dcf6  mov     ebx, eax
0x18001dcf8  test    eax, eax
0x18001dcfa  js      loc_18001DE93
0x18001dd00  mov     ecx, dword ptr [rsp+170h+SystemInformation]; unsigned int
0x18001dd04  call    ?WaitForWerSvc@@YAJK@Z; WaitForWerSvc(ulong)
0x18001dd09  mov     ebx, eax
0x18001dd0b  test    eax, eax
0x18001dd0d  js      loc_18001DE93
0x18001dd13  cmp     eax, 102h
0x18001dd18  jnz     short loc_18001DD24
0x18001dd1a  mov     ebx, 0C0000353h
0x18001dd1f  jmp     loc_18001DE93
0x18001dd24  lea     rax, [rsp+170h+var_100]
0x18001dd29  xor     r9d, r9d; SubAuthority1
0x18001dd2c  mov     [rsp+170h+Sid], rax; Sid
0x18001dd31  lea     rcx, [rbp+70h+IdentifierAuthority]; IdentifierAuthority
0x18001dd35  mov     [rsp+170h+SubAuthority7], r13d; SubAuthority7
0x18001dd3a  mov     sil, 1
0x18001dd3d  mov     [rsp+170h+SubAuthority6], r13d; SubAuthority6
0x18001dd42  mov     dl, sil; SubAuthorityCount
0x18001dd45  mov     [rsp+170h+SubAuthority5], r13d; SubAuthority5
0x18001dd4a  lea     r8d, [r9+12h]; SubAuthority0
0x18001dd4e  mov     [rsp+170h+SubAuthority4], r13d; SubAuthority4
0x18001dd53  mov     [rsp+170h+SubAuthority3], r13d; SubAuthority3
0x18001dd58  mov     [rsp+170h+SubAuthority2], r13d; SubAuthority2
0x18001dd5d  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001dd63  mov     ebx, eax
0x18001dd65  test    eax, eax
0x18001dd67  js      loc_18001DE93
0x18001dd6d  test    edi, edi
0x18001dd6f  cmovz   edi, dword ptr [rsp+170h+SystemInformation+4]
0x18001dd74  cmp     edi, 0FFFFFFFFh
0x18001dd77  jz      short loc_18001DD8A
0x18001dd79  movsxd  rax, edi
0x18001dd7c  mov     sil, r13b
0x18001dd7f  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18001dd86  mov     [rbp+70h+var_F0], rcx
0x18001dd8a  mov     rdx, r12; SourceString
0x18001dd8d  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18001dd91  call    cs:__imp_RtlInitUnicodeString
0x18001dd97  xor     edx, edx; Val
0x18001dd99  mov     dword ptr [rbp+70h+var_D8], 30h ; '0'
0x18001dda0  xorps   xmm0, xmm0
0x18001dda3  mov     qword ptr [rbp+70h+var_D8+8], r13
0x18001dda7  lea     rcx, [rbp+70h+var_A0]; void *
0x18001ddab  mov     dword ptr [rbp+70h+var_C8+8], r13d
0x18001ddaf  mov     qword ptr [rbp+70h+var_C8], r13
0x18001ddb3  lea     r8d, [rdx+48h]; Size
0x18001ddb7  movdqu  [rbp+70h+var_B8], xmm0
0x18001ddbc  call    memset_0
0x18001ddc1  mov     rax, [rsp+170h+var_100]
0x18001ddc6  lea     rdi, [rbp+70h+var_F0]
0x18001ddca  test    sil, sil
0x18001ddcd  lea     r9, [rbp+70h+var_A0]
0x18001ddd1  mov     r12d, 578h
0x18001ddd7  lea     r8, [rbp+70h+var_D8]
0x18001dddb  cmovnz  rdi, r13
0x18001dddf  mov     [rbp+70h+var_90], r12
0x18001dde3  mov     [rsp+170h+Sid], rdi
0x18001dde8  lea     rdx, [rbp+70h+DestinationString]
0x18001ddec  mov     qword ptr [rsp+170h+SubAuthority7], r13
0x18001ddf1  lea     rcx, [rsp+170h+Handle]
0x18001ddf6  mov     qword ptr [rsp+170h+SubAuthority6], r13
0x18001ddfb  mov     qword ptr [rsp+170h+SubAuthority5], r13
0x18001de00  mov     qword ptr [rsp+170h+SubAuthority4], r13
0x18001de05  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x18001de0a  mov     [rsp+170h+SubAuthority2], 20000h
0x18001de12  call    cs:__imp_NtAlpcConnectPort
0x18001de18  mov     ebx, eax
0x18001de1a  test    eax, eax
0x18001de1c  js      short loc_18001DE93
0x18001de1e  mov     esi, 102h
0x18001de23  cmp     eax, esi
0x18001de25  jz      loc_18001DD1A
0x18001de2b  lea     rcx, [r14+4]; void *
0x18001de2f  xor     edx, edx; Val
0x18001de31  lea     r8d, [r12-4]; Size
0x18001de36  call    memset_0
0x18001de3b  mov     rcx, [rsp+170h+Handle]
0x18001de40  lea     rax, [rsp+170h+var_108]
0x18001de45  mov     qword ptr [rsp+170h+SubAuthority5], rdi
0x18001de4a  xor     r9d, r9d
0x18001de4d  mov     qword ptr [rsp+170h+SubAuthority4], r13
0x18001de52  mov     r8, r15
0x18001de55  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x18001de5a  mov     edx, 20000h
0x18001de5f  mov     qword ptr [rsp+170h+SubAuthority2], r14
0x18001de64  mov     dword ptr [r14], 5780550h
0x18001de6b  mov     [rsp+170h+var_108], r12
0x18001de70  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001de76  mov     ebx, eax
0x18001de78  test    eax, eax
0x18001de7a  js      short loc_18001DE93
0x18001de7c  cmp     eax, esi
0x18001de7e  jz      short loc_18001DE93
0x18001de80  mov     rax, [rsp+170h+var_108]
0x18001de85  sub     rax, r12
0x18001de88  neg     rax
0x18001de8b  sbb     ebx, ebx
0x18001de8d  and     ebx, 0C000021Fh
0x18001de93  mov     rcx, [rsp+170h+var_100]; Sid
0x18001de98  test    rcx, rcx
0x18001de9b  jz      short loc_18001DEA3
0x18001de9d  call    cs:__imp_RtlFreeSid
0x18001dea3  mov     rcx, [rsp+170h+Handle]; Handle
0x18001dea8  test    rcx, rcx
0x18001deab  jz      short loc_18001DEB3
0x18001dead  call    cs:__imp_NtClose
0x18001deb3  mov     eax, ebx
0x18001deb5  mov     rcx, [rbp+70h+var_50]
0x18001deb9  xor     rcx, rsp; StackCookie
0x18001debc  call    __security_check_cookie
0x18001dec1  add     rsp, 138h
0x18001dec8  pop     r15
0x18001deca  pop     r14
0x18001decc  pop     r13
0x18001dece  pop     r12
0x18001ded0  pop     rdi
0x18001ded1  pop     rsi
0x18001ded2  pop     rbx
0x18001ded3  pop     rbp
0x18001ded4  retn
```
