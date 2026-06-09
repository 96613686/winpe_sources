# WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18001e2c0`
- end: `0x18001e56c`
- name: `?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z`
- size: `684`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001e134`
- `0x18001e288`
- `0x180038a34`
- `0x18003ee38`
- `0x18004b858`

## callees

- `0x18001e2c0`
- `0x18001e574`
- `0x18002ac58`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18001e35c`
- `ntdll!NtQuerySystemInformation` at `0x18001e35c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e3cf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e3cf`
- `ntdll!NtAlpcConnectPort` at `0x18001e490`
- `ntdll!NtAlpcConnectPort` at `0x18001e490`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001e4f4`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001e4f4`
- `ntdll!RtlFreeSid` at `0x18001e527`
- `ntdll!RtlFreeSid` at `0x18001e527`
- `ntdll!RtlInitUnicodeString` at `0x18001e409`
- `ntdll!RtlInitUnicodeString` at `0x18001e409`
- `ntdll!NtClose` at `0x18001e53d`
- `ntdll!NtClose` at `0x18001e53d`

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
0x18001e2c0  push    rbp
0x18001e2c2  push    rbx
0x18001e2c3  push    rsi
0x18001e2c4  push    rdi
0x18001e2c5  push    r12
0x18001e2c7  push    r13
0x18001e2c9  push    r14
0x18001e2cb  push    r15
0x18001e2cd  lea     rbp, [rsp-38h]
0x18001e2d2  sub     rsp, 138h
0x18001e2d9  mov     rax, cs:__security_cookie
0x18001e2e0  xor     rax, rsp
0x18001e2e3  mov     [rbp+70h+var_50], rax
0x18001e2e7  xorps   xmm0, xmm0
0x18001e2ea  mov     word ptr [rbp+70h+IdentifierAuthority.Value+4], 500h
0x18001e2f0  xor     r13d, r13d
0x18001e2f3  mov     r14, r8
0x18001e2f6  mov     r15, rdx
0x18001e2f9  mov     dword ptr [rbp+70h+IdentifierAuthority.Value], r13d
0x18001e2fd  mov     r12, rcx
0x18001e300  xor     edx, edx; Val
0x18001e302  lea     rcx, [rbp+70h+var_A0]; void *
0x18001e306  mov     edi, r9d
0x18001e309  lea     r8d, [r13+48h]; Size
0x18001e30d  movups  [rbp+70h+var_D8], xmm0
0x18001e311  movups  [rbp+70h+var_C8], xmm0
0x18001e315  movups  [rbp+70h+var_B8], xmm0
0x18001e319  call    memset_0
0x18001e31e  xorps   xmm0, xmm0
0x18001e321  mov     [rbp+70h+var_F0], r13
0x18001e325  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18001e329  mov     [rsp+170h+Handle], r13
0x18001e32e  mov     [rsp+170h+var_100], r13
0x18001e333  mov     [rsp+170h+var_108], r13
0x18001e338  mov     [rsp+170h+SystemInformation], r13
0x18001e33d  call    ?SignalStartWerSvc@@YAJXZ; SignalStartWerSvc(void)
0x18001e342  mov     ebx, eax
0x18001e344  test    eax, eax
0x18001e346  js      loc_18001E51D
0x18001e34c  xor     r9d, r9d; ReturnLength
0x18001e34f  lea     r8d, [r13+8]; SystemInformationLength
0x18001e353  lea     rdx, [rsp+170h+SystemInformation]; SystemInformation
0x18001e358  lea     ecx, [r13+73h]; SystemInformationClass
0x18001e35c  call    cs:__imp_NtQuerySystemInformation
0x18001e363  nop     dword ptr [rax+rax+00h]
0x18001e368  mov     ebx, eax
0x18001e36a  test    eax, eax
0x18001e36c  js      loc_18001E51D
0x18001e372  mov     ecx, dword ptr [rsp+170h+SystemInformation]; unsigned int
0x18001e376  call    ?WaitForWerSvc@@YAJK@Z; WaitForWerSvc(ulong)
0x18001e37b  mov     ebx, eax
0x18001e37d  test    eax, eax
0x18001e37f  js      loc_18001E51D
0x18001e385  cmp     eax, 102h
0x18001e38a  jnz     short loc_18001E396
0x18001e38c  mov     ebx, 0C0000353h
0x18001e391  jmp     loc_18001E51D
0x18001e396  lea     rax, [rsp+170h+var_100]
0x18001e39b  xor     r9d, r9d; SubAuthority1
0x18001e39e  mov     [rsp+170h+Sid], rax; Sid
0x18001e3a3  lea     rcx, [rbp+70h+IdentifierAuthority]; IdentifierAuthority
0x18001e3a7  mov     [rsp+170h+SubAuthority7], r13d; SubAuthority7
0x18001e3ac  mov     sil, 1
0x18001e3af  mov     [rsp+170h+SubAuthority6], r13d; SubAuthority6
0x18001e3b4  mov     dl, sil; SubAuthorityCount
0x18001e3b7  mov     [rsp+170h+SubAuthority5], r13d; SubAuthority5
0x18001e3bc  lea     r8d, [r9+12h]; SubAuthority0
0x18001e3c0  mov     [rsp+170h+SubAuthority4], r13d; SubAuthority4
0x18001e3c5  mov     [rsp+170h+SubAuthority3], r13d; SubAuthority3
0x18001e3ca  mov     [rsp+170h+SubAuthority2], r13d; SubAuthority2
0x18001e3cf  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001e3d6  nop     dword ptr [rax+rax+00h]
0x18001e3db  mov     ebx, eax
0x18001e3dd  test    eax, eax
0x18001e3df  js      loc_18001E51D
0x18001e3e5  test    edi, edi
0x18001e3e7  cmovz   edi, dword ptr [rsp+170h+SystemInformation+4]
0x18001e3ec  cmp     edi, 0FFFFFFFFh
0x18001e3ef  jz      short loc_18001E402
0x18001e3f1  movsxd  rax, edi
0x18001e3f4  mov     sil, r13b
0x18001e3f7  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18001e3fe  mov     [rbp+70h+var_F0], rcx
0x18001e402  mov     rdx, r12; SourceString
0x18001e405  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18001e409  call    cs:__imp_RtlInitUnicodeString
0x18001e410  nop     dword ptr [rax+rax+00h]
0x18001e415  xor     edx, edx; Val
0x18001e417  mov     dword ptr [rbp+70h+var_D8], 30h ; '0'
0x18001e41e  xorps   xmm0, xmm0
0x18001e421  mov     qword ptr [rbp+70h+var_D8+8], r13
0x18001e425  lea     rcx, [rbp+70h+var_A0]; void *
0x18001e429  mov     dword ptr [rbp+70h+var_C8+8], r13d
0x18001e42d  mov     qword ptr [rbp+70h+var_C8], r13
0x18001e431  lea     r8d, [rdx+48h]; Size
0x18001e435  movdqu  [rbp+70h+var_B8], xmm0
0x18001e43a  call    memset_0
0x18001e43f  mov     rax, [rsp+170h+var_100]
0x18001e444  lea     rdi, [rbp+70h+var_F0]
0x18001e448  test    sil, sil
0x18001e44b  lea     r9, [rbp+70h+var_A0]
0x18001e44f  mov     r12d, 578h
0x18001e455  lea     r8, [rbp+70h+var_D8]
0x18001e459  cmovnz  rdi, r13
0x18001e45d  mov     [rbp+70h+var_90], r12
0x18001e461  mov     [rsp+170h+Sid], rdi
0x18001e466  lea     rdx, [rbp+70h+DestinationString]
0x18001e46a  mov     qword ptr [rsp+170h+SubAuthority7], r13
0x18001e46f  lea     rcx, [rsp+170h+Handle]
0x18001e474  mov     qword ptr [rsp+170h+SubAuthority6], r13
0x18001e479  mov     qword ptr [rsp+170h+SubAuthority5], r13
0x18001e47e  mov     qword ptr [rsp+170h+SubAuthority4], r13
0x18001e483  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x18001e488  mov     [rsp+170h+SubAuthority2], 20000h
0x18001e490  call    cs:__imp_NtAlpcConnectPort
0x18001e497  nop     dword ptr [rax+rax+00h]
0x18001e49c  mov     ebx, eax
0x18001e49e  test    eax, eax
0x18001e4a0  js      short loc_18001E51D
0x18001e4a2  mov     esi, 102h
0x18001e4a7  cmp     eax, esi
0x18001e4a9  jz      loc_18001E38C
0x18001e4af  lea     rcx, [r14+4]; void *
0x18001e4b3  xor     edx, edx; Val
0x18001e4b5  lea     r8d, [r12-4]; Size
0x18001e4ba  call    memset_0
0x18001e4bf  mov     rcx, [rsp+170h+Handle]
0x18001e4c4  lea     rax, [rsp+170h+var_108]
0x18001e4c9  mov     qword ptr [rsp+170h+SubAuthority5], rdi
0x18001e4ce  xor     r9d, r9d
0x18001e4d1  mov     qword ptr [rsp+170h+SubAuthority4], r13
0x18001e4d6  mov     r8, r15
0x18001e4d9  mov     qword ptr [rsp+170h+SubAuthority3], rax
0x18001e4de  mov     edx, 20000h
0x18001e4e3  mov     qword ptr [rsp+170h+SubAuthority2], r14
0x18001e4e8  mov     dword ptr [r14], 5780550h
0x18001e4ef  mov     [rsp+170h+var_108], r12
0x18001e4f4  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001e4fb  nop     dword ptr [rax+rax+00h]
0x18001e500  mov     ebx, eax
0x18001e502  test    eax, eax
0x18001e504  js      short loc_18001E51D
0x18001e506  cmp     eax, esi
0x18001e508  jz      short loc_18001E51D
0x18001e50a  mov     rax, [rsp+170h+var_108]
0x18001e50f  sub     rax, r12
0x18001e512  neg     rax
0x18001e515  sbb     ebx, ebx
0x18001e517  and     ebx, 0C000021Fh
0x18001e51d  mov     rcx, [rsp+170h+var_100]; Sid
0x18001e522  test    rcx, rcx
0x18001e525  jz      short loc_18001E533
0x18001e527  call    cs:__imp_RtlFreeSid
0x18001e52e  nop     dword ptr [rax+rax+00h]
0x18001e533  mov     rcx, [rsp+170h+Handle]; Handle
0x18001e538  test    rcx, rcx
0x18001e53b  jz      short loc_18001E549
0x18001e53d  call    cs:__imp_NtClose
0x18001e544  nop     dword ptr [rax+rax+00h]
0x18001e549  mov     eax, ebx
0x18001e54b  mov     rcx, [rbp+70h+var_50]
0x18001e54f  xor     rcx, rsp; StackCookie
0x18001e552  call    __security_check_cookie
0x18001e557  add     rsp, 138h
0x18001e55e  pop     r15
0x18001e560  pop     r14
0x18001e562  pop     r13
0x18001e564  pop     r12
0x18001e566  pop     rdi
0x18001e567  pop     rsi
0x18001e568  pop     rbx
0x18001e569  pop     rbp
0x18001e56a  retn
```
