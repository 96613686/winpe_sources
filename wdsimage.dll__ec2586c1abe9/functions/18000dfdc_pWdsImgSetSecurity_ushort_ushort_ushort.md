# pWdsImgSetSecurity(ushort *,ushort *,ushort * *)

- ea: `0x18000dfdc`
- end: `0x18000e253`
- name: `?pWdsImgSetSecurity@@YAJPEAG0PEAPEAG@Z`
- size: `631`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR StringSecurityDescriptor, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006cb0`
- `0x18000bfcc`

## callees

- `0x18000dc28`
- `0x18000de90`
- `0x18000dfdc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e067`
- `ntdll!RtlNtStatusToDosError` at `0x18000e07c`
- `ntdll!RtlNtStatusToDosError` at `0x18000e067`
- `ntdll!RtlNtStatusToDosError` at `0x18000e07c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000e195`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000e195`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e0b3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e0b3`
- `KERNEL32!LocalFree` at `0x18000e1c6`
- `KERNEL32!LocalFree` at `0x18000e1c6`
- `KERNEL32!CloseHandle` at `0x18000e1f0`
- `KERNEL32!CloseHandle` at `0x18000e1f0`
- `KERNEL32!GetProcessHeap` at `0x18000e20f`
- `KERNEL32!GetProcessHeap` at `0x18000e20f`
- `KERNEL32!HeapFree` at `0x18000e223`
- `KERNEL32!HeapFree` at `0x18000e223`
- `KERNEL32!GetLastError` at `0x18000e0c3`
- `KERNEL32!GetLastError` at `0x18000e0c3`
- `WdsCommonLib!?WdsRestoreThreadPrivileges@@YAJPEAX@Z` at `0x18000e1da`
- `WdsCommonLib!?WdsRestoreThreadPrivileges@@YAJPEAX@Z` at `0x18000e1da`
- `WdsCommonLib!?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z` at `0x18000e04d`
- `WdsCommonLib!?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z` at `0x18000e04d`

## string_xrefs

- `0x18000e003`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall pWdsImgSetSecurity(WCHAR *lpFileName, LPCWSTR StringSecurityDescriptor, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rdi
  signed int v7; // eax
  NTSTATUS SecurityDescriptorComponents; // ebx
  bool v9; // zf
  signed int LastError; // eax
  bool v11; // cc
  SECURITY_INFORMATION v12; // r8d
  NTSTATUS Security; // eax
  HANDLE ProcessHeap; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-38h] BYREF
  PSID psidOwner; // [rsp+50h] [rbp-30h] BYREF
  PSID psidGroup; // [rsp+58h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+60h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v22; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int16 v24; // [rsp+C8h] [rbp+48h] BYREF

  hObject = (HANDLE)-1LL;
  v23 = L"SeSecurityPrivilege";
  SecurityDescriptor = 0;
  v24 = 0;
  psidOwner = 0;
  psidGroup = 0;
  pDacl = 0;
  pSacl = 0;
  v22 = 0;
  v6 = 0;
  v7 = WdsSetThreadPrivileges(&v23, 1u, 1, &hObject);
  SecurityDescriptorComponents = v7;
  if ( v7 >= 0 )
    goto LABEL_8;
  if ( (v7 & 0x10000000) != 0 )
  {
    if ( RtlNtStatusToDosError(v7) != 317 )
    {
      v7 = RtlNtStatusToDosError(SecurityDescriptorComponents);
      goto LABEL_7;
    }
  }
  else
  {
    v9 = (v7 & 0x1FFF0000) == 458752;
    v7 = (unsigned __int16)v7;
    if ( v9 )
      goto LABEL_7;
  }
  v7 = SecurityDescriptorComponents;
LABEL_7:
  if ( v7 != 1300 )
    goto LABEL_21;
LABEL_8:
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    SecurityDescriptorComponents = pWdsImgGetSecurityDescriptorComponents(
                                     SecurityDescriptor,
                                     &v24,
                                     &psidOwner,
                                     &psidGroup,
                                     &pDacl,
                                     &pSacl);
    if ( SecurityDescriptorComponents < 0 )
      goto LABEL_21;
    v12 = psidOwner != 0;
    if ( psidGroup )
      v12 |= 2u;
    if ( (v24 & 4) != 0 )
      v12 |= (v24 & 0x1000) != 0 ? -2147483644 : 536870916;
    if ( (v24 & 0x10) != 0 )
      v12 |= (v24 & 0x2000) != 0 ? 1073741832 : 268435464;
    LastError = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, v12, psidOwner, psidGroup, pDacl, pSacl);
    SecurityDescriptorComponents = LastError;
    v11 = LastError <= 0;
    if ( !LastError )
    {
      Security = pWdsImgGetSecurity(lpFileName, &v22);
      v6 = v22;
      SecurityDescriptorComponents = Security;
      goto LABEL_21;
    }
  }
  else
  {
    LastError = GetLastError();
    SecurityDescriptorComponents = LastError;
    v11 = LastError <= 0;
  }
  if ( !v11 )
    SecurityDescriptorComponents = (unsigned __int16)LastError | 0x80070000;
LABEL_21:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  WdsRestoreThreadPrivileges(hObject);
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  if ( SecurityDescriptorComponents < 0 )
  {
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
  }
  else
  {
    *a3 = v6;
  }
  return (unsigned int)SecurityDescriptorComponents;
}

```

## disassembly

```asm
0x18000dfdc  mov     [rsp-28h+arg_0], rbx
0x18000dfe1  mov     [rsp-28h+arg_8], rsi
0x18000dfe6  mov     [rsp-28h+arg_10], rdi
0x18000dfeb  push    rbp
0x18000dfec  push    r12
0x18000dfee  push    r13
0x18000dff0  push    r14
0x18000dff2  push    r15
0x18000dff4  mov     rbp, rsp
0x18000dff7  sub     rsp, 80h
0x18000dffe  or      [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18000e003  lea     rax, aSesecuritypriv; "SeSecurityPrivilege"
0x18000e00a  xor     r12d, r12d
0x18000e00d  mov     [rbp+var_8], rax
0x18000e011  mov     r15, r8
0x18000e014  mov     [rbp+SecurityDescriptor], r12
0x18000e018  mov     rsi, rdx
0x18000e01b  mov     [rbp+arg_18], r12w
0x18000e020  mov     r14, rcx
0x18000e023  mov     [rbp+psidOwner], r12
0x18000e027  lea     r13d, [r12+1]
0x18000e02c  mov     [rbp+var_28], r12
0x18000e030  mov     r8d, r13d
0x18000e033  mov     [rbp+var_18], r12
0x18000e037  mov     edx, r13d
0x18000e03a  mov     [rbp+var_20], r12
0x18000e03e  lea     r9, [rbp+hObject]
0x18000e042  mov     [rbp+var_10], r12
0x18000e046  lea     rcx, [rbp+var_8]
0x18000e04a  mov     edi, r12d
0x18000e04d  call    cs:__imp_?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z; WdsSetThreadPrivileges(ushort * *,ulong,int,void * *)
0x18000e054  nop     dword ptr [rax+rax+00h]
0x18000e059  mov     ebx, eax
0x18000e05b  test    eax, eax
0x18000e05d  jns     short loc_18000E0A6
0x18000e05f  bt      eax, 1Ch
0x18000e063  jnb     short loc_18000E08A
0x18000e065  mov     ecx, eax; Status
0x18000e067  call    cs:__imp_RtlNtStatusToDosError
0x18000e06e  nop     dword ptr [rax+rax+00h]
0x18000e073  cmp     eax, 13Dh
0x18000e078  jz      short loc_18000E099
0x18000e07a  mov     ecx, ebx; Status
0x18000e07c  call    cs:__imp_RtlNtStatusToDosError
0x18000e083  nop     dword ptr [rax+rax+00h]
0x18000e088  jmp     short loc_18000E09B
0x18000e08a  and     eax, 1FFF0000h
0x18000e08f  cmp     eax, 70000h
0x18000e094  movzx   eax, bx
0x18000e097  jz      short loc_18000E09B
0x18000e099  mov     eax, ebx
0x18000e09b  cmp     eax, 514h
0x18000e0a0  jnz     loc_18000E1BD
0x18000e0a6  xor     r9d, r9d; SecurityDescriptorSize
0x18000e0a9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000e0ad  mov     edx, r13d; StringSDRevision
0x18000e0b0  mov     rcx, rsi; StringSecurityDescriptor
0x18000e0b3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000e0ba  nop     dword ptr [rax+rax+00h]
0x18000e0bf  test    eax, eax
0x18000e0c1  jnz     short loc_18000E0E7
0x18000e0c3  call    cs:__imp_GetLastError
0x18000e0ca  nop     dword ptr [rax+rax+00h]
0x18000e0cf  mov     ebx, eax
0x18000e0d1  test    eax, eax
0x18000e0d3  jle     loc_18000E1BD
0x18000e0d9  movzx   ebx, ax
0x18000e0dc  or      ebx, 80070000h
0x18000e0e2  jmp     loc_18000E1BD
0x18000e0e7  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18000e0eb  lea     rax, [rbp+var_20]
0x18000e0ef  mov     [rsp+80h+pDacl], rax; struct _ACL **
0x18000e0f4  lea     r9, [rbp+var_28]; void **
0x18000e0f8  lea     rax, [rbp+var_18]
0x18000e0fc  lea     r8, [rbp+psidOwner]; void **
0x18000e100  mov     [rsp+80h+psidGroup], rax; struct _ACL **
0x18000e105  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000e109  call    ?pWdsImgGetSecurityDescriptorComponents@@YAJPEAXPEAGPEAPEAX2PEAPEAU_ACL@@3@Z; pWdsImgGetSecurityDescriptorComponents(void *,ushort *,void * *,void * *,_ACL * *,_ACL * *)
0x18000e10e  mov     ebx, eax
0x18000e110  test    eax, eax
0x18000e112  js      loc_18000E1BD
0x18000e118  mov     r9, [rbp+psidOwner]; psidOwner
0x18000e11c  mov     r8d, r12d
0x18000e11f  mov     r10, [rbp+var_28]
0x18000e123  test    r9, r9
0x18000e126  cmovnz  r8d, r13d
0x18000e12a  test    r10, r10
0x18000e12d  jz      short loc_18000E133
0x18000e12f  or      r8d, 2
0x18000e133  movzx   ecx, [rbp+arg_18]
0x18000e137  test    cl, 4
0x18000e13a  jz      short loc_18000E159
0x18000e13c  movzx   eax, cx
0x18000e13f  mov     edx, 1000h
0x18000e144  and     ax, dx
0x18000e147  neg     ax
0x18000e14a  sbb     eax, eax
0x18000e14c  and     eax, 60000000h
0x18000e151  add     eax, 20000004h
0x18000e156  or      r8d, eax
0x18000e159  test    cl, 10h
0x18000e15c  jz      short loc_18000E178
0x18000e15e  mov     eax, 2000h
0x18000e163  and     cx, ax
0x18000e166  neg     cx
0x18000e169  sbb     eax, eax
0x18000e16b  and     eax, 30000000h
0x18000e170  add     eax, 10000008h
0x18000e175  or      r8d, eax; SecurityInfo
0x18000e178  mov     rax, [rbp+var_20]
0x18000e17c  mov     edx, r13d; ObjectType
0x18000e17f  mov     [rsp+80h+pSacl], rax; pSacl
0x18000e184  mov     rcx, r14; pObjectName
0x18000e187  mov     rax, [rbp+var_18]
0x18000e18b  mov     [rsp+80h+pDacl], rax; pDacl
0x18000e190  mov     [rsp+80h+psidGroup], r10; psidGroup
0x18000e195  call    cs:__imp_SetNamedSecurityInfoW
0x18000e19c  nop     dword ptr [rax+rax+00h]
0x18000e1a1  mov     ebx, eax
0x18000e1a3  test    eax, eax
0x18000e1a5  jnz     loc_18000E0D3
0x18000e1ab  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000e1af  mov     rcx, r14; lpFileName
0x18000e1b2  call    ?pWdsImgGetSecurity@@YAJPEAGPEAPEAG@Z; pWdsImgGetSecurity(ushort *,ushort * *)
0x18000e1b7  mov     rdi, [rbp+var_10]
0x18000e1bb  mov     ebx, eax
0x18000e1bd  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000e1c1  test    rcx, rcx
0x18000e1c4  jz      short loc_18000E1D6
0x18000e1c6  call    cs:__imp_LocalFree
0x18000e1cd  nop     dword ptr [rax+rax+00h]
0x18000e1d2  mov     [rbp+SecurityDescriptor], r12
0x18000e1d6  mov     rcx, [rbp+hObject]
0x18000e1da  call    cs:__imp_?WdsRestoreThreadPrivileges@@YAJPEAX@Z; WdsRestoreThreadPrivileges(void *)
0x18000e1e1  nop     dword ptr [rax+rax+00h]
0x18000e1e6  mov     rcx, [rbp+hObject]; hObject
0x18000e1ea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e1ee  jz      short loc_18000E201
0x18000e1f0  call    cs:__imp_CloseHandle
0x18000e1f7  nop     dword ptr [rax+rax+00h]
0x18000e1fc  or      [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18000e201  test    ebx, ebx
0x18000e203  js      short loc_18000E20A
0x18000e205  mov     [r15], rdi
0x18000e208  jmp     short loc_18000E22F
0x18000e20a  test    rdi, rdi
0x18000e20d  jz      short loc_18000E22F
0x18000e20f  call    cs:__imp_GetProcessHeap
0x18000e216  nop     dword ptr [rax+rax+00h]
0x18000e21b  mov     r8, rdi; lpMem
0x18000e21e  xor     edx, edx; dwFlags
0x18000e220  mov     rcx, rax; hHeap
0x18000e223  call    cs:__imp_HeapFree
0x18000e22a  nop     dword ptr [rax+rax+00h]
0x18000e22f  lea     r11, [rsp+80h+var_s0]
0x18000e237  mov     eax, ebx
0x18000e239  mov     rbx, [r11+30h]
0x18000e23d  mov     rsi, [r11+38h]
0x18000e241  mov     rdi, [r11+40h]
0x18000e245  mov     rsp, r11
0x18000e248  pop     r15
0x18000e24a  pop     r14
0x18000e24c  pop     r13
0x18000e24e  pop     r12
0x18000e250  pop     rbp
0x18000e251  retn
```
