# WctGetCOMInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong,_WAITCHAIN_NODE_INFO *,ulong *,ulong *,_WCT_LOCK_CONTEXT *)

- ea: `0x180050a48`
- end: `0x180050d55`
- name: `?WctGetCOMInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@KPEAU_WAITCHAIN_NODE_INFO@@PEAK3PEAU_WCT_LOCK_CONTEXT@@@Z`
- size: `781`
- prototype: `unsigned int __usercall@<eax>(struct _WCT_CLIENT_HANDLE *@<rcx>, struct _SYSTEM_PROCESS_INFORMATION *@<rdx>, unsigned int@<r8d>, struct _WAITCHAIN_NODE_INFO *@<r9>, unsigned int *, unsigned int *, struct _WCT_LOCK_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x180020680`
- `0x180050a48`
- `0x180053300`
- `0x18005dd11`
- `0x18005f4b0`
- `0x1800614f4`
- `0x1800616b8`
- `0x1800af094`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180050b17`
- `ntdll!NtQueryInformationThread` at `0x180050b17`
- `ntdll!RtlStringFromGUID` at `0x180050c29`
- `ntdll!RtlStringFromGUID` at `0x180050c29`
- `ntdll!RtlFreeUnicodeString` at `0x180050c6f`
- `ntdll!RtlFreeUnicodeString` at `0x180050c6f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050b57`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050b93`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050bf3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050b57`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050b93`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180050bf3`

## pseudocode

```c
__int64 __fastcall WctGetCOMInfo(
        HANDLE *a1,
        struct _SYSTEM_PROCESS_INFORMATION *a2,
        char a3,
        struct _WAITCHAIN_NODE_INFO *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _WCT_LOCK_CONTEXT *a7)
{
  unsigned int v10; // eax
  unsigned __int64 Length; // rbx
  int v12; // ebx
  GUID v13; // xmm0
  unsigned int v14; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-71h] BYREF
  __int64 v17; // [rsp+38h] [rbp-69h] BYREF
  __int64 Buffer; // [rsp+40h] [rbp-61h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-59h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+58h] [rbp-49h] BYREF
  struct _SYSTEM_PROCESS_INFORMATION *v21; // [rsp+60h] [rbp-41h]
  _OWORD ThreadInformation[3]; // [rsp+68h] [rbp-39h] BYREF
  __int128 Buf1; // [rsp+98h] [rbp-9h] BYREF

  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  Buffer = 0;
  v17 = 0;
  Buf1 = 0;
  v21 = a2;
  GuidString = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( dword_1800DECA0
    && !(unsigned int)WctIsWow64(a1[1])
    && NtQueryInformationThread(*a1, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength) >= 0
    && ReturnLength == 48
    && ReadProcessMemory(
         a1[1],
         (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + 5976LL),
         &Buffer,
         8u,
         &NumberOfBytesRead)
    && NumberOfBytesRead == 8
    && ReadProcessMemory(a1[1], (LPCVOID)(Buffer + (unsigned int)dword_1800DECA0), &v17, 8u, 0)
    && HIDWORD(v17) != -1 )
  {
    v10 = dword_1800DEC88;
    a4->ObjectType = WctComType;
    a4->ObjectStatus = WctStatusOwned;
    Buf1 = xmmword_1800BA710;
    if ( v10 )
    {
      if ( ReadProcessMemory(a1[1], (LPCVOID)(Buffer + v10), &Buf1, 0x10u, 0) )
      {
        if ( memcmp_0(&Buf1, &xmmword_1800BA710, 0x10u) )
        {
          GuidString.Buffer = 0;
          if ( RtlStringFromGUID((const GUID *const)&Buf1, &GuidString) >= 0 )
          {
            if ( GuidString.Length < 0x100u )
            {
              Length = GuidString.Length;
              memcpy_0(&a4->LockObject, GuidString.Buffer, GuidString.Length);
              a4->LockObject.ObjectName[Length >> 1] = 0;
            }
            if ( GuidString.Buffer )
              RtlFreeUnicodeString(&GuidString);
          }
        }
      }
    }
    *a5 = HIDWORD(v17);
    if ( (_DWORD)v17 )
    {
      *a6 = v17;
    }
    else
    {
      *a6 = 0;
      *a5 = 0;
    }
    v12 = *a6;
    if ( *a6 != *((_DWORD *)a1 + 4) )
    {
      if ( !memcmp_0(&Buf1, &xmmword_1800BA710, 0x10u) || !(unsigned int)WctIsRpcssPid(v12) )
      {
        if ( !*a5 && (a3 & 2) != 0 )
          WctGetCOMServerInfo((struct _WCT_CLIENT_HANDLE *)a1, v21, a5, a6);
      }
      else
      {
        v13 = (GUID)Buf1;
        *(_DWORD *)a7 = 9;
        *(GUID *)((char *)a7 + 4) = v13;
      }
    }
    v14 = 0;
  }
  else
  {
    v14 = 1168;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180050a48  mov     [rsp-8+arg_10], rbx
0x180050a4d  push    rbp
0x180050a4e  push    rsi
0x180050a4f  push    rdi
0x180050a50  push    r12
0x180050a52  push    r13
0x180050a54  push    r14
0x180050a56  push    r15
0x180050a58  lea     rbp, [rsp-0Fh]
0x180050a5d  sub     rsp, 0B0h
0x180050a64  mov     rax, cs:__security_cookie
0x180050a6b  xor     rax, rsp
0x180050a6e  mov     [rbp+3Fh+var_38], rax
0x180050a72  mov     r12, [rbp+3Fh+arg_30]
0x180050a76  xorps   xmm0, xmm0
0x180050a79  mov     rsi, [rbp+3Fh+arg_20]
0x180050a7d  xor     ebx, ebx
0x180050a7f  mov     r14, [rbp+3Fh+arg_28]
0x180050a83  xorps   xmm1, xmm1
0x180050a86  movups  [rbp+3Fh+ThreadInformation], xmm0
0x180050a8a  mov     [rbp+3Fh+NumberOfBytesRead], rbx
0x180050a8e  mov     r15, r9
0x180050a91  movups  [rbp+3Fh+var_68], xmm0
0x180050a95  mov     [rbp+3Fh+var_B0], ebx
0x180050a98  mov     r13d, r8d
0x180050a9b  movups  [rbp+3Fh+var_58], xmm0
0x180050a9f  mov     [rbp+3Fh+Buffer], rbx
0x180050aa3  mov     rdi, rcx
0x180050aa6  mov     [rbp+3Fh+var_A8], rbx
0x180050aaa  movups  [rbp+3Fh+Buf1], xmm0
0x180050aae  mov     [rbp+3Fh+var_80], rdx
0x180050ab2  movups  xmmword ptr [rbp+3Fh+GuidString.Length], xmm1
0x180050ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180050abd  lea     rax, WPP_GLOBAL_Control
0x180050ac4  cmp     rcx, rax
0x180050ac7  jz      short loc_180050AE2
0x180050ac9  test    byte ptr [rcx+1Ch], 4
0x180050acd  jz      short loc_180050AE2
0x180050acf  mov     rcx, [rcx+10h]
0x180050ad3  lea     edx, [rbx+26h]
0x180050ad6  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180050add  call    WPP_SF_
0x180050ae2  cmp     cs:dword_1800DECA0, ebx
0x180050ae8  jz      loc_180050CF5
0x180050aee  mov     rcx, [rdi+8]; void *
0x180050af2  call    ?WctIsWow64@@YAHPEAX@Z; WctIsWow64(void *)
0x180050af7  test    eax, eax
0x180050af9  jnz     loc_180050CF5
0x180050aff  mov     rcx, [rdi]; ThreadHandle
0x180050b02  lea     rax, [rbp+3Fh+var_B0]
0x180050b06  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180050b0c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180050b11  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x180050b15  xor     edx, edx; ThreadInformationClass
0x180050b17  call    cs:__imp_NtQueryInformationThread
0x180050b1e  nop     dword ptr [rax+rax+00h]
0x180050b23  test    eax, eax
0x180050b25  js      loc_180050CF5
0x180050b2b  cmp     [rbp+3Fh+var_B0], 30h ; '0'
0x180050b2f  jnz     loc_180050CF5
0x180050b35  mov     rdx, qword ptr [rbp+3Fh+ThreadInformation+8]
0x180050b39  lea     rax, [rbp+3Fh+NumberOfBytesRead]
0x180050b3d  mov     rcx, [rdi+8]; hProcess
0x180050b41  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x180050b45  add     rdx, 1758h; lpBaseAddress
0x180050b4c  mov     [rsp+0E0h+ReturnLength], rax; lpNumberOfBytesRead
0x180050b51  mov     r9d, 8; nSize
0x180050b57  call    cs:__imp_ReadProcessMemory
0x180050b5e  nop     dword ptr [rax+rax+00h]
0x180050b63  test    eax, eax
0x180050b65  jz      loc_180050CF5
0x180050b6b  cmp     [rbp+3Fh+NumberOfBytesRead], 8
0x180050b70  jnz     loc_180050CF5
0x180050b76  mov     edx, cs:dword_1800DECA0
0x180050b7c  lea     r8, [rbp+3Fh+var_A8]; lpBuffer
0x180050b80  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x180050b84  mov     r9d, 8; nSize
0x180050b8a  mov     rcx, [rdi+8]; hProcess
0x180050b8e  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x180050b93  call    cs:__imp_ReadProcessMemory
0x180050b9a  nop     dword ptr [rax+rax+00h]
0x180050b9f  test    eax, eax
0x180050ba1  jz      loc_180050CF5
0x180050ba7  cmp     dword ptr [rbp+3Fh+var_A8+4], 0FFFFFFFFh
0x180050bab  jz      loc_180050CF5
0x180050bb1  mov     eax, cs:dword_1800DEC88
0x180050bb7  mov     dword ptr [r15], 5
0x180050bbe  mov     dword ptr [r15+4], 6
0x180050bc6  movups  xmm0, cs:xmmword_1800BA710
0x180050bcd  movdqu  [rbp+3Fh+Buf1], xmm0
0x180050bd2  test    eax, eax
0x180050bd4  jz      loc_180050C7B
0x180050bda  mov     rcx, [rdi+8]; hProcess
0x180050bde  lea     r8, [rbp+3Fh+Buf1]; lpBuffer
0x180050be2  mov     edx, eax
0x180050be4  mov     [rsp+0E0h+ReturnLength], rbx; lpNumberOfBytesRead
0x180050be9  add     rdx, [rbp+3Fh+Buffer]; lpBaseAddress
0x180050bed  mov     r9d, 10h; nSize
0x180050bf3  call    cs:__imp_ReadProcessMemory
0x180050bfa  nop     dword ptr [rax+rax+00h]
0x180050bff  test    eax, eax
0x180050c01  jz      short loc_180050C7B
0x180050c03  mov     r8d, 10h; Size
0x180050c09  lea     rdx, xmmword_1800BA710; Buf2
0x180050c10  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x180050c14  call    memcmp_0
0x180050c19  test    eax, eax
0x180050c1b  jz      short loc_180050C7B
0x180050c1d  lea     rdx, [rbp+3Fh+GuidString]; GuidString
0x180050c21  mov     [rbp+3Fh+GuidString.Buffer], rbx
0x180050c25  lea     rcx, [rbp+3Fh+Buf1]; Guid
0x180050c29  call    cs:__imp_RtlStringFromGUID
0x180050c30  nop     dword ptr [rax+rax+00h]
0x180050c35  test    eax, eax
0x180050c37  js      short loc_180050C7B
0x180050c39  mov     eax, 100h
0x180050c3e  cmp     [rbp+3Fh+GuidString.Length], ax
0x180050c42  jnb     short loc_180050C65
0x180050c44  movzx   ebx, [rbp+3Fh+GuidString.Length]
0x180050c48  lea     rcx, [r15+8]; void *
0x180050c4c  mov     rdx, [rbp+3Fh+GuidString.Buffer]; Src
0x180050c50  mov     r8d, ebx; Size
0x180050c53  call    memcpy_0
0x180050c58  shr     rbx, 1
0x180050c5b  xor     eax, eax
0x180050c5d  mov     [r15+rbx*2+8], ax
0x180050c63  xor     ebx, ebx
0x180050c65  cmp     [rbp+3Fh+GuidString.Buffer], rbx
0x180050c69  jz      short loc_180050C7B
0x180050c6b  lea     rcx, [rbp+3Fh+GuidString]; UnicodeString
0x180050c6f  call    cs:__imp_RtlFreeUnicodeString
0x180050c76  nop     dword ptr [rax+rax+00h]
0x180050c7b  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x180050c7e  mov     [rsi], eax
0x180050c80  mov     rax, [rbp+3Fh+var_A8]
0x180050c84  test    eax, eax
0x180050c86  jnz     short loc_180050C8F
0x180050c88  mov     [r14], ebx
0x180050c8b  mov     [rsi], ebx
0x180050c8d  jmp     short loc_180050C92
0x180050c8f  mov     [r14], eax
0x180050c92  mov     ebx, [r14]
0x180050c95  cmp     ebx, [rdi+10h]
0x180050c98  jz      short loc_180050CF1
0x180050c9a  mov     r8d, 10h; Size
0x180050ca0  lea     rdx, xmmword_1800BA710; Buf2
0x180050ca7  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x180050cab  call    memcmp_0
0x180050cb0  test    eax, eax
0x180050cb2  jz      short loc_180050CD4
0x180050cb4  mov     ecx, ebx; unsigned int
0x180050cb6  call    ?WctIsRpcssPid@@YAHK@Z; WctIsRpcssPid(ulong)
0x180050cbb  test    eax, eax
0x180050cbd  jz      short loc_180050CD4
0x180050cbf  movups  xmm0, [rbp+3Fh+Buf1]
0x180050cc3  mov     dword ptr [r12], 9
0x180050ccb  movdqu  xmmword ptr [r12+4], xmm0
0x180050cd2  jmp     short loc_180050CF1
0x180050cd4  cmp     dword ptr [rsi], 0
0x180050cd7  jnz     short loc_180050CF1
0x180050cd9  test    r13b, 2
0x180050cdd  jz      short loc_180050CF1
0x180050cdf  mov     rdx, [rbp+3Fh+var_80]; struct _SYSTEM_PROCESS_INFORMATION *
0x180050ce3  mov     r9, r14; unsigned int *
0x180050ce6  mov     r8, rsi; unsigned int *
0x180050ce9  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x180050cec  call    ?WctGetCOMServerInfo@@YAXPEAU_WCT_CLIENT_HANDLE@@PEAU_SYSTEM_PROCESS_INFORMATION@@PEAK2@Z; WctGetCOMServerInfo(_WCT_CLIENT_HANDLE *,_SYSTEM_PROCESS_INFORMATION *,ulong *,ulong *)
0x180050cf1  xor     ebx, ebx
0x180050cf3  jmp     short loc_180050CFA
0x180050cf5  mov     ebx, 490h
0x180050cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d01  lea     rax, WPP_GLOBAL_Control
0x180050d08  cmp     rcx, rax
0x180050d0b  jz      short loc_180050D2B
0x180050d0d  test    byte ptr [rcx+1Ch], 4
0x180050d11  jz      short loc_180050D2B
0x180050d13  mov     rcx, [rcx+10h]
0x180050d17  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180050d1e  mov     edx, 27h ; '''
0x180050d23  mov     r9d, ebx
0x180050d26  call    WPP_SF_d
0x180050d2b  mov     eax, ebx
0x180050d2d  mov     rcx, [rbp+3Fh+var_38]
0x180050d31  xor     rcx, rsp; StackCookie
0x180050d34  call    __security_check_cookie
0x180050d39  mov     rbx, [rsp+0E0h+arg_10]
0x180050d41  add     rsp, 0B0h
0x180050d48  pop     r15
0x180050d4a  pop     r14
0x180050d4c  pop     r13
0x180050d4e  pop     r12
0x180050d50  pop     rdi
0x180050d51  pop     rsi
0x180050d52  pop     rbp
0x180050d53  retn
```
