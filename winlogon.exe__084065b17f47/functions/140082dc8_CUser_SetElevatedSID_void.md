# CUser::SetElevatedSID(void)

- ea: `0x140082dc8`
- end: `0x14008302c`
- name: `?SetElevatedSID@CUser@@AEAAKXZ`
- size: `612`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140081d40`

## callees

- `0x1400057f4`
- `0x14000fd40`
- `0x140082dc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140082f33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140082f33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140083011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140083011`
- `ntdll!NtQueryInformationToken` at `0x140082e0d`
- `ntdll!NtQueryInformationToken` at `0x140082e79`
- `ntdll!NtQueryInformationToken` at `0x140082ece`
- `ntdll!NtQueryInformationToken` at `0x140082f8d`
- `ntdll!NtQueryInformationToken` at `0x140082e0d`
- `ntdll!NtQueryInformationToken` at `0x140082e79`
- `ntdll!NtQueryInformationToken` at `0x140082ece`
- `ntdll!NtQueryInformationToken` at `0x140082f8d`
- `ntdll!RtlNtStatusToDosError` at `0x140083019`
- `ntdll!RtlNtStatusToDosError` at `0x140083019`
- `ntdll!NtClose` at `0x140082ff5`
- `ntdll!NtClose` at `0x140082ff5`

## pseudocode

```c
ULONG __fastcall CUser::SetElevatedSID(CUser *this)
{
  PSID *v1; // rdi
  void *v3; // rcx
  int v4; // ebx
  CUser *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rax
  ULONG TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  TokenInformation = 0;
  v3 = (void *)*((_QWORD *)this + 17);
  TokenHandle = 0;
  v4 = NtQueryInformationToken(v3, TokenElevationType, &TokenInformation, 4u, &TokenInformationLength);
  if ( v4 >= 0 )
  {
    if ( TokenInformation != 3 )
      goto LABEL_33;
    v4 = NtQueryInformationToken(*((HANDLE *)this + 17), TokenLinkedToken, &TokenHandle, 8u, &TokenInformationLength);
    if ( v4 >= 0 )
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
      if ( v4 == -1073741789 )
      {
        v1 = (PSID *)HeapAlloc(*((HANDLE *)this + 1), 8u, TokenInformationLength);
        if ( v1 )
        {
          v4 = NtQueryInformationToken(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength);
          if ( v4 < 0 )
            goto LABEL_33;
          v8 = DuplicateSID(*v1);
          *((_QWORD *)this + 21) = v8;
          if ( v8 )
            goto LABEL_33;
          v4 = -1073741801;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_33;
          }
          v6 = 252;
        }
        else
        {
          v4 = -1073741801;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_33;
          }
          v6 = 251;
        }
        v7 = 3221225495LL;
        goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          250,
          WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
          (unsigned int)v4);
      }
      if ( v4 >= 0 )
        v4 = -1073741306;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 249;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 248;
LABEL_6:
      v7 = (unsigned int)v4;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v7);
    }
  }
LABEL_33:
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( v1 )
    HeapFree(*((HANDLE *)this + 1), 0, v1);
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x140082dc8  mov     [rsp-18h+arg_18], rbx
0x140082dcd  push    rbp
0x140082dce  push    rsi
0x140082dcf  push    rdi
0x140082dd0  mov     rbp, rsp
0x140082dd3  sub     rsp, 30h
0x140082dd7  xor     edi, edi
0x140082dd9  mov     [rbp+TokenInformationLength], 0
0x140082de0  mov     rsi, rcx
0x140082de3  mov     [rbp+TokenInformation], 0
0x140082dea  mov     rcx, [rcx+88h]; TokenHandle
0x140082df1  lea     rax, [rbp+TokenInformationLength]
0x140082df5  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140082df9  mov     [rbp+TokenHandle], 0
0x140082e01  lea     r9d, [rdi+4]; TokenInformationLength
0x140082e05  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140082e0a  lea     edx, [rdi+12h]; TokenInformationClass
0x140082e0d  call    cs:__imp_NtQueryInformationToken
0x140082e13  mov     ebx, eax
0x140082e15  test    eax, eax
0x140082e17  jns     short loc_140082E51
0x140082e19  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e20  lea     rax, WPP_GLOBAL_Control
0x140082e27  cmp     rcx, rax
0x140082e2a  jz      loc_140082FEC
0x140082e30  test    byte ptr [rcx+1Ch], 20h
0x140082e34  jz      loc_140082FEC
0x140082e3a  cmp     byte ptr [rcx+19h], 2
0x140082e3e  jb      loc_140082FEC
0x140082e44  mov     edx, 0F8h
0x140082e49  mov     r9d, ebx
0x140082e4c  jmp     loc_140082FDC
0x140082e51  cmp     [rbp+TokenInformation], 3
0x140082e55  jnz     loc_140082FEC
0x140082e5b  mov     rcx, [rsi+88h]; TokenHandle
0x140082e62  lea     rax, [rbp+TokenInformationLength]
0x140082e66  mov     r9d, 8; TokenInformationLength
0x140082e6c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140082e71  lea     r8, [rbp+TokenHandle]; TokenInformation
0x140082e75  lea     edx, [r9+0Bh]; TokenInformationClass
0x140082e79  call    cs:__imp_NtQueryInformationToken
0x140082e7f  mov     ebx, eax
0x140082e81  test    eax, eax
0x140082e83  jns     short loc_140082EB7
0x140082e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140082e8c  lea     rax, WPP_GLOBAL_Control
0x140082e93  cmp     rcx, rax
0x140082e96  jz      loc_140082FEC
0x140082e9c  test    byte ptr [rcx+1Ch], 20h
0x140082ea0  jz      loc_140082FEC
0x140082ea6  cmp     byte ptr [rcx+19h], 2
0x140082eaa  jb      loc_140082FEC
0x140082eb0  mov     edx, 0F9h
0x140082eb5  jmp     short loc_140082E49
0x140082eb7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140082ebb  lea     rax, [rbp+TokenInformationLength]
0x140082ebf  xor     r9d, r9d; TokenInformationLength
0x140082ec2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140082ec7  xor     r8d, r8d; TokenInformation
0x140082eca  lea     edx, [r9+1]; TokenInformationClass
0x140082ece  call    cs:__imp_NtQueryInformationToken
0x140082ed4  mov     ebx, eax
0x140082ed6  cmp     eax, 0C0000023h
0x140082edb  jz      short loc_140082F26
0x140082edd  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ee4  lea     rax, WPP_GLOBAL_Control
0x140082eeb  cmp     rcx, rax
0x140082eee  jz      short loc_140082F14
0x140082ef0  test    byte ptr [rcx+1Ch], 20h
0x140082ef4  jz      short loc_140082F14
0x140082ef6  cmp     byte ptr [rcx+19h], 2
0x140082efa  jb      short loc_140082F14
0x140082efc  mov     rcx, [rcx+10h]
0x140082f00  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140082f07  mov     edx, 0FAh
0x140082f0c  mov     r9d, ebx
0x140082f0f  call    WPP_SF_d
0x140082f14  test    ebx, ebx
0x140082f16  js      loc_140082FEC
0x140082f1c  mov     ebx, 0C0000206h
0x140082f21  jmp     loc_140082FEC
0x140082f26  mov     r8d, [rbp+TokenInformationLength]; dwBytes
0x140082f2a  mov     edx, 8; dwFlags
0x140082f2f  mov     rcx, [rsi+8]; hHeap
0x140082f33  call    cs:__imp_HeapAlloc
0x140082f39  mov     rdi, rax
0x140082f3c  test    rax, rax
0x140082f3f  jnz     short loc_140082F74
0x140082f41  mov     ebx, 0C0000017h
0x140082f46  mov     rcx, cs:WPP_GLOBAL_Control
0x140082f4d  lea     rax, WPP_GLOBAL_Control
0x140082f54  cmp     rcx, rax
0x140082f57  jz      loc_140082FEC
0x140082f5d  test    byte ptr [rcx+1Ch], 20h
0x140082f61  jz      loc_140082FEC
0x140082f67  cmp     byte ptr [rcx+19h], 2
0x140082f6b  jb      short loc_140082FEC
0x140082f6d  mov     edx, 0FBh
0x140082f72  jmp     short loc_140082FD6
0x140082f74  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140082f78  lea     rax, [rbp+TokenInformationLength]
0x140082f7c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140082f80  mov     r8, rdi; TokenInformation
0x140082f83  mov     edx, 1; TokenInformationClass
0x140082f88  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140082f8d  call    cs:__imp_NtQueryInformationToken
0x140082f93  mov     ebx, eax
0x140082f95  test    eax, eax
0x140082f97  js      short loc_140082FEC
0x140082f99  mov     rcx, [rdi]; SourceSid
0x140082f9c  call    DuplicateSID
0x140082fa1  mov     [rsi+0A8h], rax
0x140082fa8  test    rax, rax
0x140082fab  jnz     short loc_140082FEC
0x140082fad  mov     ebx, 0C0000017h
0x140082fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140082fb9  lea     rax, WPP_GLOBAL_Control
0x140082fc0  cmp     rcx, rax
0x140082fc3  jz      short loc_140082FEC
0x140082fc5  test    byte ptr [rcx+1Ch], 20h
0x140082fc9  jz      short loc_140082FEC
0x140082fcb  cmp     byte ptr [rcx+19h], 2
0x140082fcf  jb      short loc_140082FEC
0x140082fd1  mov     edx, 0FCh
0x140082fd6  mov     r9d, 0C0000017h
0x140082fdc  mov     rcx, [rcx+10h]
0x140082fe0  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140082fe7  call    WPP_SF_d
0x140082fec  mov     rcx, [rbp+TokenHandle]; Handle
0x140082ff0  test    rcx, rcx
0x140082ff3  jz      short loc_140083003
0x140082ff5  call    cs:__imp_NtClose
0x140082ffb  mov     [rbp+TokenHandle], 0
0x140083003  test    rdi, rdi
0x140083006  jz      short loc_140083017
0x140083008  mov     rcx, [rsi+8]; hHeap
0x14008300c  mov     r8, rdi; lpMem
0x14008300f  xor     edx, edx; dwFlags
0x140083011  call    cs:__imp_HeapFree
0x140083017  mov     ecx, ebx; Status
0x140083019  call    cs:__imp_RtlNtStatusToDosError
0x14008301f  mov     rbx, [rsp+30h+arg_18]
0x140083024  add     rsp, 30h
0x140083028  pop     rdi
0x140083029  pop     rsi
0x14008302a  pop     rbp
0x14008302b  retn
```
