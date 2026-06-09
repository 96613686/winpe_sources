# WersvcSendMessage(ushort const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)

- ea: `0x18000bb20`
- end: `0x18000bd9e`
- name: `?WersvcSendMessage@@YAJPEBGPEAU_WERSVC_MSG@@1K@Z`
- size: `638`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _WERSVC_MSG *, struct _WERSVC_MSG *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b334`

## callees

- `0x18000b0e4`
- `0x18000ba60`
- `0x18000bb20`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000bbba`
- `ntdll!NtQuerySystemInformation` at `0x18000bbba`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000bc27`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000bc27`
- `ntdll!NtAlpcConnectPort` at `0x18000bcd7`
- `ntdll!NtAlpcConnectPort` at `0x18000bcd7`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000bd38`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000bd38`
- `ntdll!RtlFreeSid` at `0x18000bd68`
- `ntdll!RtlFreeSid` at `0x18000bd68`
- `ntdll!NtClose` at `0x18000bd78`
- `ntdll!NtClose` at `0x18000bd78`
- `ntdll!RtlInitUnicodeString` at `0x18000bc58`
- `ntdll!RtlInitUnicodeString` at `0x18000bc58`

## pseudocode

```c
__int64 __fastcall WersvcSendMessage(PCWSTR SourceString, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  NTSTATUS started; // ebx
  int v7; // eax
  char v8; // di
  __int64 *v9; // r14
  int v10; // eax
  HANDLE v11; // rcx
  int v12; // eax
  __int64 SystemInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+98h] [rbp-68h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-58h]
  __int128 v22; // [rsp+B8h] [rbp-48h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v24[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-20h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset_0(v24, 0, 0x48u);
  v18 = 0;
  DestinationString = 0;
  Handle = 0;
  Sid = 0;
  v15 = 0;
  SystemInformation = 0;
  started = SignalStartWerSvc();
  if ( started >= 0 )
  {
    started = NtQuerySystemInformation(MaxSystemInfoClass|SystemObjectInformation, &SystemInformation, 8u, 0);
    if ( started >= 0 )
    {
      v7 = WaitForWerSvc(SystemInformation);
      started = v7;
      if ( v7 >= 0 )
      {
        if ( v7 == 258 )
        {
LABEL_5:
          started = -1073740973;
          goto LABEL_16;
        }
        v8 = 1;
        started = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
        if ( started >= 0 )
        {
          if ( HIDWORD(SystemInformation) != -1 )
          {
            v8 = 0;
            v18 = -10000LL * SHIDWORD(SystemInformation);
          }
          RtlInitUnicodeString(&DestinationString, SourceString);
          LODWORD(v20) = 48;
          *((_QWORD *)&v20 + 1) = 0;
          DWORD2(v21) = 0;
          *(_QWORD *)&v21 = 0;
          v22 = 0;
          memset_0(v24, 0, 0x48u);
          v9 = &v18;
          v25 = 1400;
          if ( v8 )
            v9 = 0;
          v10 = NtAlpcConnectPort(&Handle, &DestinationString, &v20, v24, 0x20000, Sid, 0, 0, 0, 0, v9);
          started = v10;
          if ( v10 >= 0 )
          {
            if ( v10 == 258 )
              goto LABEL_5;
            memset_0((char *)a3 + 4, 0, 0x574u);
            v11 = Handle;
            *(_DWORD *)a3 = 91751760;
            v15 = 1400;
            v12 = NtAlpcSendWaitReceivePort(v11, 0x20000, a2, 0, a3, &v15, 0, v9);
            started = v12;
            if ( v12 >= 0 && v12 != 258 )
              started = v15 != 1400 ? 0xC000021F : 0;
          }
        }
      }
    }
  }
LABEL_16:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000bb20  push    rbp
0x18000bb22  push    rbx
0x18000bb23  push    rsi
0x18000bb24  push    rdi
0x18000bb25  push    r12
0x18000bb27  push    r14
0x18000bb29  push    r15
0x18000bb2b  lea     rbp, [rsp-30h]
0x18000bb30  sub     rsp, 130h
0x18000bb37  mov     rax, cs:__security_cookie
0x18000bb3e  xor     rax, rsp
0x18000bb41  mov     [rbp+60h+var_40], rax
0x18000bb45  xorps   xmm0, xmm0
0x18000bb48  mov     word ptr [rbp+60h+IdentifierAuthority.Value+4], 500h
0x18000bb4e  xor     r12d, r12d
0x18000bb51  mov     rsi, r8
0x18000bb54  mov     r15, rdx
0x18000bb57  mov     dword ptr [rbp+60h+IdentifierAuthority.Value], r12d
0x18000bb5b  mov     r14, rcx
0x18000bb5e  xor     edx, edx; Val
0x18000bb60  lea     rcx, [rbp+60h+var_90]; void *
0x18000bb64  lea     r8d, [r12+48h]; Size
0x18000bb69  movups  [rbp+60h+var_C8], xmm0
0x18000bb6d  movups  [rbp+60h+var_B8], xmm0
0x18000bb71  movups  [rbp+60h+var_A8], xmm0
0x18000bb75  call    memset_0
0x18000bb7a  xorps   xmm0, xmm0
0x18000bb7d  mov     [rbp+60h+var_E0], r12
0x18000bb81  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18000bb85  mov     [rsp+160h+Handle], r12
0x18000bb8a  mov     [rsp+160h+var_F0], r12
0x18000bb8f  mov     [rsp+160h+var_F8], r12
0x18000bb94  mov     [rsp+160h+SystemInformation], r12
0x18000bb99  call    ?SignalStartWerSvc@@YAJXZ; SignalStartWerSvc(void)
0x18000bb9e  mov     ebx, eax
0x18000bba0  test    eax, eax
0x18000bba2  js      loc_18000BD5E
0x18000bba8  xor     r9d, r9d; ReturnLength
0x18000bbab  lea     r8d, [r12+8]; SystemInformationLength
0x18000bbb0  lea     rdx, [rsp+160h+SystemInformation]; SystemInformation
0x18000bbb5  lea     ecx, [r12+73h]; SystemInformationClass
0x18000bbba  call    cs:__imp_NtQuerySystemInformation
0x18000bbc0  mov     ebx, eax
0x18000bbc2  test    eax, eax
0x18000bbc4  js      loc_18000BD5E
0x18000bbca  mov     ecx, dword ptr [rsp+160h+SystemInformation]; unsigned int
0x18000bbce  call    ?WaitForWerSvc@@YAJK@Z; WaitForWerSvc(ulong)
0x18000bbd3  mov     ebx, eax
0x18000bbd5  test    eax, eax
0x18000bbd7  js      loc_18000BD5E
0x18000bbdd  cmp     eax, 102h
0x18000bbe2  jnz     short loc_18000BBEE
0x18000bbe4  mov     ebx, 0C0000353h
0x18000bbe9  jmp     loc_18000BD5E
0x18000bbee  lea     rax, [rsp+160h+var_F0]
0x18000bbf3  xor     r9d, r9d; SubAuthority1
0x18000bbf6  mov     [rsp+160h+Sid], rax; Sid
0x18000bbfb  lea     rcx, [rbp+60h+IdentifierAuthority]; IdentifierAuthority
0x18000bbff  mov     [rsp+160h+SubAuthority7], r12d; SubAuthority7
0x18000bc04  mov     dil, 1
0x18000bc07  mov     [rsp+160h+SubAuthority6], r12d; SubAuthority6
0x18000bc0c  mov     dl, dil; SubAuthorityCount
0x18000bc0f  mov     [rsp+160h+SubAuthority5], r12d; SubAuthority5
0x18000bc14  lea     r8d, [r9+12h]; SubAuthority0
0x18000bc18  mov     [rsp+160h+SubAuthority4], r12d; SubAuthority4
0x18000bc1d  mov     [rsp+160h+SubAuthority3], r12d; SubAuthority3
0x18000bc22  mov     [rsp+160h+SubAuthority2], r12d; SubAuthority2
0x18000bc27  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000bc2d  mov     ebx, eax
0x18000bc2f  test    eax, eax
0x18000bc31  js      loc_18000BD5E
0x18000bc37  cmp     dword ptr [rsp+160h+SystemInformation+4], 0FFFFFFFFh
0x18000bc3c  jz      short loc_18000BC51
0x18000bc3e  movsxd  rax, dword ptr [rsp+160h+SystemInformation+4]
0x18000bc43  mov     dil, r12b
0x18000bc46  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18000bc4d  mov     [rbp+60h+var_E0], rcx
0x18000bc51  mov     rdx, r14; SourceString
0x18000bc54  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18000bc58  call    cs:__imp_RtlInitUnicodeString
0x18000bc5e  xor     edx, edx; Val
0x18000bc60  mov     dword ptr [rbp+60h+var_C8], 30h ; '0'
0x18000bc67  xorps   xmm0, xmm0
0x18000bc6a  mov     qword ptr [rbp+60h+var_C8+8], r12
0x18000bc6e  lea     rcx, [rbp+60h+var_90]; void *
0x18000bc72  mov     dword ptr [rbp+60h+var_B8+8], r12d
0x18000bc76  mov     qword ptr [rbp+60h+var_B8], r12
0x18000bc7a  lea     r8d, [rdx+48h]; Size
0x18000bc7e  movdqu  [rbp+60h+var_A8], xmm0
0x18000bc83  call    memset_0
0x18000bc88  mov     rax, [rsp+160h+var_F0]
0x18000bc8d  lea     r14, [rbp+60h+var_E0]
0x18000bc91  test    dil, dil
0x18000bc94  mov     [rbp+60h+var_80], 578h
0x18000bc9c  lea     r9, [rbp+60h+var_90]
0x18000bca0  cmovnz  r14, r12
0x18000bca4  lea     r8, [rbp+60h+var_C8]
0x18000bca8  mov     [rsp+160h+Sid], r14
0x18000bcad  lea     rdx, [rbp+60h+DestinationString]
0x18000bcb1  mov     qword ptr [rsp+160h+SubAuthority7], r12
0x18000bcb6  lea     rcx, [rsp+160h+Handle]
0x18000bcbb  mov     qword ptr [rsp+160h+SubAuthority6], r12
0x18000bcc0  mov     qword ptr [rsp+160h+SubAuthority5], r12
0x18000bcc5  mov     qword ptr [rsp+160h+SubAuthority4], r12
0x18000bcca  mov     qword ptr [rsp+160h+SubAuthority3], rax
0x18000bccf  mov     [rsp+160h+SubAuthority2], 20000h
0x18000bcd7  call    cs:__imp_NtAlpcConnectPort
0x18000bcdd  mov     ebx, eax
0x18000bcdf  test    eax, eax
0x18000bce1  js      short loc_18000BD5E
0x18000bce3  cmp     eax, 102h
0x18000bce8  jz      loc_18000BBE4
0x18000bcee  lea     rcx, [rsi+4]; void *
0x18000bcf2  xor     edx, edx; Val
0x18000bcf4  mov     r8d, 574h; Size
0x18000bcfa  call    memset_0
0x18000bcff  mov     rcx, [rsp+160h+Handle]
0x18000bd04  lea     rax, [rsp+160h+var_F8]
0x18000bd09  mov     qword ptr [rsp+160h+SubAuthority5], r14
0x18000bd0e  mov     edi, 578h
0x18000bd13  mov     qword ptr [rsp+160h+SubAuthority4], r12
0x18000bd18  xor     r9d, r9d
0x18000bd1b  mov     qword ptr [rsp+160h+SubAuthority3], rax
0x18000bd20  mov     r8, r15
0x18000bd23  mov     edx, 20000h
0x18000bd28  mov     qword ptr [rsp+160h+SubAuthority2], rsi
0x18000bd2d  mov     dword ptr [rsi], 5780550h
0x18000bd33  mov     [rsp+160h+var_F8], rdi
0x18000bd38  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000bd3e  mov     ebx, eax
0x18000bd40  test    eax, eax
0x18000bd42  js      short loc_18000BD5E
0x18000bd44  cmp     eax, 102h
0x18000bd49  jz      short loc_18000BD5E
0x18000bd4b  mov     rax, [rsp+160h+var_F8]
0x18000bd50  sub     rax, rdi
0x18000bd53  neg     rax
0x18000bd56  sbb     ebx, ebx
0x18000bd58  and     ebx, 0C000021Fh
0x18000bd5e  mov     rcx, [rsp+160h+var_F0]; Sid
0x18000bd63  test    rcx, rcx
0x18000bd66  jz      short loc_18000BD6E
0x18000bd68  call    cs:__imp_RtlFreeSid
0x18000bd6e  mov     rcx, [rsp+160h+Handle]; Handle
0x18000bd73  test    rcx, rcx
0x18000bd76  jz      short loc_18000BD7E
0x18000bd78  call    cs:__imp_NtClose
0x18000bd7e  mov     eax, ebx
0x18000bd80  mov     rcx, [rbp+60h+var_40]
0x18000bd84  xor     rcx, rsp; StackCookie
0x18000bd87  call    __security_check_cookie
0x18000bd8c  add     rsp, 130h
0x18000bd93  pop     r15
0x18000bd95  pop     r14
0x18000bd97  pop     r12
0x18000bd99  pop     rdi
0x18000bd9a  pop     rsi
0x18000bd9b  pop     rbx
0x18000bd9c  pop     rbp
0x18000bd9d  retn
```
