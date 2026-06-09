# LsaImpersonateSecurityContext(_SecHandle *)

- ea: `0x1800145d0`
- end: `0x18001471f`
- name: `?LsaImpersonateSecurityContext@@YAJPEAU_SecHandle@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct _SecHandle *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003ee0`
- `0x180005cc0`
- `0x1800145d0`
- `0x18001b14c`
- `0x18001c948`
- `0x180023010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800146ed`
- `ntdll!RtlNtStatusToDosError` at `0x1800146ed`
- `ntdll!NtSetInformationThread` at `0x1800146b6`
- `ntdll!NtSetInformationThread` at `0x1800146b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800146f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800146f5`

## pseudocode

```c
__int64 __fastcall LsaImpersonateSecurityContext(struct _SecHandle *a1)
{
  ULONG_PTR dwLower; // rcx
  NTSTATUS v3; // ebx
  __int64 v5; // rsi
  __int64 v6; // rax
  NTSTATUS v7; // eax
  __int64 v8; // r8
  ULONG v9; // eax
  __int64 ThreadInformation; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  dwLower = a1->dwLower;
  ThreadInformation = 0;
  v3 = SecLocatePackageById(dwLower, &v11);
  if ( v3 >= 0 )
  {
    if ( LsaPackageShutdown )
    {
      SetLastError(0x45Bu);
      return 2148074245LL;
    }
    v5 = v11;
    v6 = *(_QWORD *)(v11 + 184);
    if ( !v6 )
      return 2148074242LL;
    v3 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64 *))(v6 + 48))(a1->dwUpper, &ThreadInformation);
    if ( v3 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SPP(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_4226b4628aa73746ed122932f46ebf9e_Traceguids,
          *(_QWORD *)(v5 + 104),
          a1->dwUpper,
          a1->dwLower);
      v7 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      v3 = v7;
      if ( v7 >= 0 )
        return SspNtStatusToSecStatus((unsigned int)v3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v8, ThreadInformation, v7);
    }
  }
  v9 = RtlNtStatusToDosError(v3);
  SetLastError(v9);
  if ( v3 == -1073741727 )
    return 2148074251LL;
  return SspNtStatusToSecStatus((unsigned int)v3);
}

```

## disassembly

```asm
0x1800145d0  mov     rax, rsp
0x1800145d3  mov     [rax+18h], rbx
0x1800145d7  push    rsi
0x1800145d8  push    rdi
0x1800145d9  push    r14
0x1800145db  sub     rsp, 30h
0x1800145df  mov     rdi, rcx
0x1800145e2  mov     qword ptr [rax+10h], 0
0x1800145ea  mov     rcx, [rcx]
0x1800145ed  lea     rdx, [rax+10h]
0x1800145f1  mov     qword ptr [rax+8], 0
0x1800145f9  call    SecLocatePackageById
0x1800145fe  mov     ebx, eax
0x180014600  test    eax, eax
0x180014602  js      loc_1800146EB
0x180014608  cmp     cs:?LsaPackageShutdown@@3HA, 0; int LsaPackageShutdown
0x18001460f  jz      short loc_180014626
0x180014611  mov     ecx, 45Bh; dwErrCode
0x180014616  call    cs:__imp_SetLastError
0x18001461c  mov     eax, 80090305h
0x180014621  jmp     loc_180014711
0x180014626  mov     rsi, [rsp+48h+arg_8]
0x18001462b  mov     rax, [rsi+0B8h]
0x180014632  test    rax, rax
0x180014635  jnz     short loc_180014641
0x180014637  mov     eax, 80090302h
0x18001463c  jmp     loc_180014711
0x180014641  mov     rcx, [rdi+8]
0x180014645  lea     rdx, [rsp+48h+ThreadInformation]
0x18001464a  mov     rax, [rax+30h]
0x18001464e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014653  mov     ebx, eax
0x180014655  test    eax, eax
0x180014657  js      loc_1800146EB
0x18001465d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014664  lea     r14, WPP_GLOBAL_Control
0x18001466b  cmp     rcx, r14
0x18001466e  jz      short loc_1800146A0
0x180014670  test    byte ptr [rcx+1Ch], 4
0x180014674  jz      short loc_1800146A0
0x180014676  mov     rax, [rdi]
0x180014679  lea     r8, WPP_4226b4628aa73746ed122932f46ebf9e_Traceguids
0x180014680  mov     r9, [rsi+68h]
0x180014684  mov     edx, 0Eh
0x180014689  mov     rcx, [rcx+10h]
0x18001468d  mov     [rsp+48h+var_20], rax
0x180014692  mov     rax, [rdi+8]
0x180014696  mov     [rsp+48h+var_28], rax
0x18001469b  call    WPP_SF_SPP
0x1800146a0  mov     r9d, 8; ThreadInformationLength
0x1800146a6  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x1800146ab  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800146b2  lea     edx, [r9-3]; ThreadInformationClass
0x1800146b6  call    cs:__imp_NtSetInformationThread
0x1800146bc  mov     ebx, eax
0x1800146be  test    eax, eax
0x1800146c0  jns     short loc_18001470A
0x1800146c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c9  cmp     rcx, r14
0x1800146cc  jz      short loc_1800146EB
0x1800146ce  test    byte ptr [rcx+1Ch], 1
0x1800146d2  jz      short loc_1800146EB
0x1800146d4  mov     r9, [rsp+48h+ThreadInformation]
0x1800146d9  mov     edx, 0Fh
0x1800146de  mov     rcx, [rcx+10h]
0x1800146e2  mov     dword ptr [rsp+48h+var_28], eax
0x1800146e6  call    WPP_SF_qD
0x1800146eb  mov     ecx, ebx; Status
0x1800146ed  call    cs:__imp_RtlNtStatusToDosError
0x1800146f3  mov     ecx, eax; dwErrCode
0x1800146f5  call    cs:__imp_SetLastError
0x1800146fb  cmp     ebx, 0C0000061h
0x180014701  jnz     short loc_18001470A
0x180014703  mov     eax, 8009030Bh
0x180014708  jmp     short loc_180014711
0x18001470a  mov     ecx, ebx
0x18001470c  call    SspNtStatusToSecStatus
0x180014711  mov     rbx, [rsp+48h+arg_10]
0x180014716  add     rsp, 30h
0x18001471a  pop     r14
0x18001471c  pop     rdi
0x18001471d  pop     rsi
0x18001471e  retn
```
