# VaultIsDominantCaller(int *)

- ea: `0x180021d80`
- end: `0x180022185`
- name: `?VaultIsDominantCaller@@YAKPEAH@Z`
- size: `1029`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021b70`
- `0x1800493d4`

## callees

- `0x180003140`
- `0x180021d80`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021db3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021f3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022160`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022160`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800220cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022141`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800220cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180022141`
- `ntdll!RtlInitializeSid` at `0x180021e19`
- `ntdll!RtlInitializeSid` at `0x180021e19`
- `ntdll!RtlSubAuthoritySid` at `0x180021e25`
- `ntdll!RtlSubAuthoritySid` at `0x180021e25`
- `ntdll!RtlSidDominates` at `0x180022043`
- `ntdll!RtlSidDominates` at `0x180022043`
- `ntdll!NtQueryInformationToken` at `0x180021ec4`
- `ntdll!NtQueryInformationToken` at `0x180021fc3`
- `ntdll!NtQueryInformationToken` at `0x180021ec4`
- `ntdll!NtQueryInformationToken` at `0x180021fc3`
- `ntdll!NtOpenThreadToken` at `0x180021e45`
- `ntdll!NtOpenThreadToken` at `0x180021e45`
- `ntdll!RtlNtStatusToDosError` at `0x180021e81`
- `ntdll!RtlNtStatusToDosError` at `0x180021f0e`
- `ntdll!RtlNtStatusToDosError` at `0x180021f82`
- `ntdll!RtlNtStatusToDosError` at `0x180022002`
- `ntdll!RtlNtStatusToDosError` at `0x180022082`
- `ntdll!RtlNtStatusToDosError` at `0x1800220b7`
- `ntdll!RtlNtStatusToDosError` at `0x180021e81`
- `ntdll!RtlNtStatusToDosError` at `0x180021f0e`
- `ntdll!RtlNtStatusToDosError` at `0x180021f82`
- `ntdll!RtlNtStatusToDosError` at `0x180022002`
- `ntdll!RtlNtStatusToDosError` at `0x180022082`
- `ntdll!RtlNtStatusToDosError` at `0x1800220b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VaultIsDominantCaller(int *a1)
{
  HLOCAL v2; // rbx
  int v3; // edi
  ULONG v4; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  ULONG v8; // ebx
  ULONG v9; // ebx
  NTSTATUS v10; // eax
  HLOCAL v11; // rsi
  _QWORD *v12; // rdx
  NTSTATUS v13; // eax
  NTSTATUS v14; // edi
  ULONG v15; // ebx
  ULONG v16; // edi
  SIZE_T v17; // rax
  _BYTE *v18; // rdx
  _BYTE *v19; // rbx
  __int64 v20; // rax
  SIZE_T v21; // rax
  _BYTE *v22; // rcx
  char v23[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  BOOL (__stdcall *v25)(HANDLE); // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _OWORD TokenInformation[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Sid[80]; // [rsp+F0h] [rbp-10h] BYREF

  TokenHandle = 0;
  v27 = 0;
  v25 = CloseHandle;
  v2 = 0;
  v29 = 0;
  v30 = 0;
  v28 = 0;
  TokenInformationLength = 128;
  v23[0] = 1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(Sid, 0) = 4096;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
    v4 = RtlNtStatusToDosError(v3);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    return v4;
  }
  v6 = NtQueryInformationToken(
         TokenHandle,
         TokenIntegrityLevel,
         TokenInformation,
         TokenInformationLength,
         &TokenInformationLength);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v11 = 0;
    v12 = TokenInformation;
  }
  else
  {
    if ( v6 != -1073741789 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
          (unsigned int)v6);
LABEL_11:
      v8 = RtlNtStatusToDosError(v7);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
      return v8;
    }
    v2 = LocalAlloc(0x40u, TokenInformationLength);
    v29 = v2;
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
      v9 = RtlNtStatusToDosError(-1073741670);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
      return v9;
    }
    v10 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, v2, TokenInformationLength, &TokenInformationLength);
    v7 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
          (unsigned int)v10);
      goto LABEL_11;
    }
    v11 = v2;
    v12 = v2;
  }
  v13 = RtlSidDominates(Sid, *v12, v23);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *a1 = v23[0] == 0;
    v16 = RtlNtStatusToDosError(v13);
    if ( v11 && v2 )
    {
      v17 = LocalSize(v2);
      if ( v17 )
      {
        v18 = v2;
        do
        {
          *v18++ = 0;
          --v17;
        }
        while ( v17 );
      }
      LocalFree(v2);
    }
    v19 = TokenHandle;
    if ( TokenHandle )
    {
      v20 = v27;
      if ( v27 )
      {
        do
        {
          *v19++ = 0;
          --v20;
        }
        while ( v20 );
        v19 = TokenHandle;
      }
      if ( v25 )
      {
        ((void (__fastcall *)(_BYTE *))v25)(v19);
      }
      else if ( v19 )
      {
        v21 = LocalSize(v19);
        if ( v21 )
        {
          v22 = v19;
          do
          {
            *v22++ = 0;
            --v21;
          }
          while ( v21 );
        }
        LocalFree(v19);
      }
    }
    return v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
        (unsigned int)v13);
    v15 = RtlNtStatusToDosError(v14);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v28);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v25);
    return v15;
  }
}

```

## disassembly

```asm
0x180021d80  push    rbp
0x180021d82  push    rbx
0x180021d83  push    rsi
0x180021d84  push    rdi
0x180021d85  push    r14
0x180021d87  push    r15
0x180021d89  lea     rbp, [rsp-58h]
0x180021d8e  sub     rsp, 158h
0x180021d95  mov     rax, cs:__security_cookie
0x180021d9c  xor     rax, rsp
0x180021d9f  mov     [rbp+80h+var_40], rax
0x180021da3  mov     r14, rcx
0x180021da6  xor     r15d, r15d
0x180021da9  mov     [rsp+180h+TokenHandle], r15
0x180021dae  mov     [rsp+180h+var_138], r15d
0x180021db3  mov     rax, cs:__imp_CloseHandle
0x180021dba  mov     [rsp+180h+var_148], rax
0x180021dbf  mov     ebx, r15d
0x180021dc2  mov     [rsp+180h+var_128], rbx
0x180021dc7  mov     [rsp+180h+var_120], r15d
0x180021dcc  mov     [rsp+180h+var_130], r15
0x180021dd1  mov     [rsp+180h+TokenInformationLength], 80h
0x180021dd9  mov     [rsp+180h+var_150], 1
0x180021dde  mov     dword ptr [rsp+180h+IdentifierAuthority.Value], ebx
0x180021de2  mov     word ptr [rsp+180h+IdentifierAuthority.Value+4], 1000h
0x180021de9  xorps   xmm0, xmm0
0x180021dec  movups  [rsp+180h+TokenInformation], xmm0
0x180021df1  movups  [rbp+80h+var_100], xmm0
0x180021df5  movups  [rbp+80h+var_F0], xmm0
0x180021df9  movups  [rbp+80h+var_E0], xmm0
0x180021dfd  movups  [rbp+80h+var_D0], xmm0
0x180021e01  movups  [rbp+80h+var_C0], xmm0
0x180021e05  movups  [rbp+80h+var_B0], xmm0
0x180021e09  movups  [rbp+80h+var_A0], xmm0
0x180021e0d  mov     r8b, 1; SubAuthorityCount
0x180021e10  lea     rdx, [rsp+180h+IdentifierAuthority]; IdentifierAuthority
0x180021e15  lea     rcx, [rbp+80h+Sid]; Sid
0x180021e19  call    cs:__imp_RtlInitializeSid
0x180021e1f  xor     edx, edx; SubAuthority
0x180021e21  lea     rcx, [rbp+80h+Sid]; Sid
0x180021e25  call    cs:__imp_RtlSubAuthoritySid
0x180021e2b  mov     dword ptr [rax], 1000h
0x180021e31  lea     r9, [rsp+180h+TokenHandle]; TokenHandle
0x180021e36  mov     r8b, 1; OpenAsSelf
0x180021e39  mov     edx, 8; DesiredAccess
0x180021e3e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180021e45  call    cs:__imp_NtOpenThreadToken
0x180021e4b  mov     edi, eax
0x180021e4d  test    eax, eax
0x180021e4f  jns     short loc_180021EA6
0x180021e51  lea     rdx, WPP_GLOBAL_Control
0x180021e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e5f  cmp     rcx, rdx
0x180021e62  jz      short loc_180021E7F
0x180021e64  test    byte ptr [rcx+1Ch], 2
0x180021e68  jz      short loc_180021E7F
0x180021e6a  mov     edx, 19h
0x180021e6f  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021e76  mov     rcx, [rcx+10h]
0x180021e7a  call    WPP_SF_
0x180021e7f  mov     ecx, edi; Status
0x180021e81  call    cs:__imp_RtlNtStatusToDosError
0x180021e87  mov     ebx, eax
0x180021e89  lea     rcx, [rsp+180h+var_130]
0x180021e8e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021e93  nop
0x180021e94  lea     rcx, [rsp+180h+var_148]
0x180021e99  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021e9e  nop
0x180021e9f  mov     eax, ebx
0x180021ea1  jmp     loc_180022169
0x180021ea6  lea     rax, [rsp+180h+TokenInformationLength]
0x180021eab  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x180021eb0  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x180021eb5  lea     r8, [rsp+180h+TokenInformation]; TokenInformation
0x180021eba  mov     edx, 19h; TokenInformationClass
0x180021ebf  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180021ec4  call    cs:__imp_NtQueryInformationToken
0x180021eca  mov     edi, eax
0x180021ecc  test    eax, eax
0x180021ece  jns     loc_18002202F
0x180021ed4  cmp     eax, 0C0000023h
0x180021ed9  jz      short loc_180021F33
0x180021edb  lea     rdx, WPP_GLOBAL_Control
0x180021ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ee9  cmp     rcx, rdx
0x180021eec  jz      short loc_180021F0C
0x180021eee  test    byte ptr [rcx+1Ch], 2
0x180021ef2  jz      short loc_180021F0C
0x180021ef4  mov     edx, 1Ah
0x180021ef9  mov     r9d, eax
0x180021efc  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021f03  mov     rcx, [rcx+10h]
0x180021f07  call    WPP_SF_d
0x180021f0c  mov     ecx, edi; Status
0x180021f0e  call    cs:__imp_RtlNtStatusToDosError
0x180021f14  mov     ebx, eax
0x180021f16  lea     rcx, [rsp+180h+var_130]
0x180021f1b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021f20  nop
0x180021f21  lea     rcx, [rsp+180h+var_148]
0x180021f26  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021f2b  nop
0x180021f2c  mov     eax, ebx
0x180021f2e  jmp     loc_180022169
0x180021f33  mov     edx, [rsp+180h+TokenInformationLength]; uBytes
0x180021f37  mov     ecx, 40h ; '@'; uFlags
0x180021f3c  call    cs:__imp_LocalAlloc
0x180021f42  mov     rbx, rax
0x180021f45  mov     [rsp+180h+var_128], rax
0x180021f4a  test    rax, rax
0x180021f4d  jnz     short loc_180021FA7
0x180021f4f  lea     rdx, WPP_GLOBAL_Control
0x180021f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f5d  cmp     rcx, rdx
0x180021f60  jz      short loc_180021F7D
0x180021f62  test    byte ptr [rcx+1Ch], 2
0x180021f66  jz      short loc_180021F7D
0x180021f68  mov     edx, 1Bh
0x180021f6d  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021f74  mov     rcx, [rcx+10h]
0x180021f78  call    WPP_SF_
0x180021f7d  mov     ecx, 0C000009Ah; Status
0x180021f82  call    cs:__imp_RtlNtStatusToDosError
0x180021f88  mov     ebx, eax
0x180021f8a  lea     rcx, [rsp+180h+var_130]
0x180021f8f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021f94  nop
0x180021f95  lea     rcx, [rsp+180h+var_148]
0x180021f9a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180021f9f  nop
0x180021fa0  mov     eax, ebx
0x180021fa2  jmp     loc_180022169
0x180021fa7  lea     rax, [rsp+180h+TokenInformationLength]
0x180021fac  mov     [rsp+180h+ReturnLength], rax; ReturnLength
0x180021fb1  mov     r9d, [rsp+180h+TokenInformationLength]; TokenInformationLength
0x180021fb6  mov     r8, rbx; TokenInformation
0x180021fb9  mov     edx, 19h; TokenInformationClass
0x180021fbe  mov     rcx, [rsp+180h+TokenHandle]; TokenHandle
0x180021fc3  call    cs:__imp_NtQueryInformationToken
0x180021fc9  mov     edi, eax
0x180021fcb  test    eax, eax
0x180021fcd  jns     short loc_180022027
0x180021fcf  lea     rdx, WPP_GLOBAL_Control
0x180021fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fdd  cmp     rcx, rdx
0x180021fe0  jz      short loc_180022000
0x180021fe2  test    byte ptr [rcx+1Ch], 2
0x180021fe6  jz      short loc_180022000
0x180021fe8  mov     edx, 1Ch
0x180021fed  mov     r9d, eax
0x180021ff0  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021ff7  mov     rcx, [rcx+10h]
0x180021ffb  call    WPP_SF_d
0x180022000  mov     ecx, edi; Status
0x180022002  call    cs:__imp_RtlNtStatusToDosError
0x180022008  mov     ebx, eax
0x18002200a  lea     rcx, [rsp+180h+var_130]
0x18002200f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180022014  nop
0x180022015  lea     rcx, [rsp+180h+var_148]
0x18002201a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002201f  nop
0x180022020  mov     eax, ebx
0x180022022  jmp     loc_180022169
0x180022027  mov     rsi, rbx
0x18002202a  mov     rdx, rbx
0x18002202d  jmp     short loc_180022037
0x18002202f  mov     rsi, r15
0x180022032  lea     rdx, [rsp+180h+TokenInformation]
0x180022037  lea     r8, [rsp+180h+var_150]
0x18002203c  mov     rdx, [rdx]
0x18002203f  lea     rcx, [rbp+80h+Sid]
0x180022043  call    cs:__imp_RtlSidDominates
0x180022049  mov     edi, eax
0x18002204b  test    eax, eax
0x18002204d  jns     short loc_1800220A7
0x18002204f  lea     rdx, WPP_GLOBAL_Control
0x180022056  mov     rcx, cs:WPP_GLOBAL_Control
0x18002205d  cmp     rcx, rdx
0x180022060  jz      short loc_180022080
0x180022062  test    byte ptr [rcx+1Ch], 2
0x180022066  jz      short loc_180022080
0x180022068  mov     edx, 1Dh
0x18002206d  mov     r9d, eax
0x180022070  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180022077  mov     rcx, [rcx+10h]
0x18002207b  call    WPP_SF_d
0x180022080  mov     ecx, edi; Status
0x180022082  call    cs:__imp_RtlNtStatusToDosError
0x180022088  mov     ebx, eax
0x18002208a  lea     rcx, [rsp+180h+var_130]
0x18002208f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180022094  nop
0x180022095  lea     rcx, [rsp+180h+var_148]
0x18002209a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002209f  nop
0x1800220a0  mov     eax, ebx
0x1800220a2  jmp     loc_180022169
0x1800220a7  mov     eax, r15d
0x1800220aa  cmp     [rsp+180h+var_150], r15b
0x1800220af  setz    al
0x1800220b2  mov     [r14], eax
0x1800220b5  mov     ecx, edi; Status
0x1800220b7  call    cs:__imp_RtlNtStatusToDosError
0x1800220bd  mov     edi, eax
0x1800220bf  test    rsi, rsi
0x1800220c2  jz      short loc_1800220F7
0x1800220c4  test    rbx, rbx
0x1800220c7  jz      short loc_1800220F7
0x1800220c9  mov     rcx, rbx; hMem
0x1800220cc  call    cs:__imp_LocalSize
0x1800220d2  test    rax, rax
0x1800220d5  jz      short loc_1800220ED
0x1800220d7  mov     rdx, rbx
0x1800220da  nop     word ptr [rax+rax+00h]
0x1800220e0  mov     byte ptr [rdx], 0
0x1800220e3  lea     rdx, [rdx+1]
0x1800220e7  sub     rax, 1
0x1800220eb  jnz     short loc_1800220E0
0x1800220ed  mov     rcx, rbx; hMem
0x1800220f0  call    cs:__imp_LocalFree
0x1800220f6  nop
0x1800220f7  mov     rbx, [rsp+180h+TokenHandle]
0x1800220fc  test    rbx, rbx
0x1800220ff  jz      short loc_180022167
0x180022101  mov     eax, [rsp+180h+var_138]
0x180022105  test    eax, eax
0x180022107  jz      short loc_180022125
0x180022109  test    rbx, rbx
0x18002210c  jz      short loc_180022125
0x18002210e  test    rax, rax
0x180022111  jz      short loc_180022125
0x180022113  mov     byte ptr [rbx], 0
0x180022116  lea     rbx, [rbx+1]
0x18002211a  sub     rax, 1
0x18002211e  jnz     short loc_180022113
0x180022120  mov     rbx, [rsp+180h+TokenHandle]
0x180022125  mov     rax, [rsp+180h+var_148]
0x18002212a  test    rax, rax
0x18002212d  jz      short loc_180022139
0x18002212f  mov     rcx, rbx
0x180022132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022137  jmp     short loc_180022167
0x180022139  test    rbx, rbx
0x18002213c  jz      short loc_180022167
0x18002213e  mov     rcx, rbx; hMem
0x180022141  call    cs:__imp_LocalSize
0x180022147  test    rax, rax
0x18002214a  jz      short loc_18002215D
0x18002214c  mov     rcx, rbx
0x18002214f  nop
0x180022150  mov     byte ptr [rcx], 0
0x180022153  lea     rcx, [rcx+1]
0x180022157  sub     rax, 1
0x18002215b  jnz     short loc_180022150
0x18002215d  mov     rcx, rbx; hMem
0x180022160  call    cs:__imp_LocalFree
0x180022166  nop
0x180022167  mov     eax, edi
0x180022169  mov     rcx, [rbp+80h+var_40]
0x18002216d  xor     rcx, rsp; StackCookie
0x180022170  call    __security_check_cookie
0x180022175  add     rsp, 158h
0x18002217c  pop     r15
0x18002217e  pop     r14
0x180022180  pop     rdi
0x180022181  pop     rsi
0x180022182  pop     rbx
0x180022183  pop     rbp
0x180022184  retn
```
