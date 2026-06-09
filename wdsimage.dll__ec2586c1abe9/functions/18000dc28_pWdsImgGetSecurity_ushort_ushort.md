# pWdsImgGetSecurity(ushort *,ushort * *)

- ea: `0x18000dc28`
- end: `0x18000de8a`
- name: `?pWdsImgGetSecurity@@YAJPEAGPEAPEAG@Z`
- size: `610`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006470`
- `0x18000ba2c`
- `0x18000dfdc`

## callees

- `0x18000dc28`
- `0x18000e8a8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000dc91`
- `ntdll!RtlNtStatusToDosError` at `0x18000dca6`
- `ntdll!RtlNtStatusToDosError` at `0x18000dc91`
- `ntdll!RtlNtStatusToDosError` at `0x18000dca6`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ddd4`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ddd4`
- `ADVAPI32!GetFileSecurityW` at `0x18000dce5`
- `ADVAPI32!GetFileSecurityW` at `0x18000dd21`
- `ADVAPI32!GetFileSecurityW` at `0x18000ddaf`
- `ADVAPI32!GetFileSecurityW` at `0x18000dce5`
- `ADVAPI32!GetFileSecurityW` at `0x18000dd21`
- `ADVAPI32!GetFileSecurityW` at `0x18000ddaf`
- `KERNEL32!LocalFree` at `0x18000ddf8`
- `KERNEL32!LocalFree` at `0x18000ddf8`
- `KERNEL32!CloseHandle` at `0x18000de64`
- `KERNEL32!CloseHandle` at `0x18000de64`
- `KERNEL32!HeapAlloc` at `0x18000dd81`
- `KERNEL32!HeapAlloc` at `0x18000dd81`
- `KERNEL32!GetProcessHeap` at `0x18000dd6a`
- `KERNEL32!GetProcessHeap` at `0x18000de2a`
- `KERNEL32!GetProcessHeap` at `0x18000dd6a`
- `KERNEL32!GetProcessHeap` at `0x18000de2a`
- `KERNEL32!HeapFree` at `0x18000de3e`
- `KERNEL32!HeapFree` at `0x18000de3e`
- `KERNEL32!GetLastError` at `0x18000dcf5`
- `KERNEL32!GetLastError` at `0x18000dd2d`
- `KERNEL32!GetLastError` at `0x18000dd3e`
- `KERNEL32!GetLastError` at `0x18000de0f`
- `KERNEL32!GetLastError` at `0x18000dcf5`
- `KERNEL32!GetLastError` at `0x18000dd2d`
- `KERNEL32!GetLastError` at `0x18000dd3e`
- `KERNEL32!GetLastError` at `0x18000de0f`
- `WdsCommonLib!?WdsRestoreThreadPrivileges@@YAJPEAX@Z` at `0x18000de4e`
- `WdsCommonLib!?WdsRestoreThreadPrivileges@@YAJPEAX@Z` at `0x18000de4e`
- `WdsCommonLib!?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z` at `0x18000dc77`
- `WdsCommonLib!?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z` at `0x18000dc77`

## string_xrefs

- `0x18000dc45`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall pWdsImgGetSecurity(LPCWSTR lpFileName, unsigned __int16 **a2)
{
  SECURITY_INFORMATION v4; // r14d
  signed int v5; // eax
  unsigned int v6; // edi
  bool v7; // zf
  signed int v8; // eax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  void *v11; // rsi
  unsigned __int16 *v12; // rax
  LPWSTR v13; // rcx
  unsigned __int16 *v14; // rbx
  signed int LastError; // eax
  HANDLE v16; // rax
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  nLengthNeeded = 0;
  StringSecurityDescriptor = 0;
  hObject = (HANDLE)-1LL;
  v19 = L"SeSecurityPrivilege";
  v4 = 15;
  v5 = WdsSetThreadPrivileges(&v19, 1u, 1, &hObject);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (v5 & 0x10000000) != 0 )
    {
      if ( RtlNtStatusToDosError(v5) != 317 )
      {
        v5 = RtlNtStatusToDosError(v6);
        goto LABEL_7;
      }
    }
    else
    {
      v7 = (v5 & 0x1FFF0000) == 458752;
      v5 = (unsigned __int16)v5;
      if ( v7 )
        goto LABEL_7;
    }
    v5 = v6;
LABEL_7:
    if ( v5 != 1300 )
      goto LABEL_21;
  }
  if ( !GetFileSecurityW(lpFileName, 0xFu, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    v4 = 7;
    GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded);
  }
  if ( GetLastError() == 122 )
  {
    v9 = nLengthNeeded;
    v6 = -2147024882;
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, v9);
    if ( v11 )
    {
      if ( GetFileSecurityW(lpFileName, v4, v11, nLengthNeeded, &nLengthNeeded)
        && ConvertSecurityDescriptorToStringSecurityDescriptorW(v11, 1u, v4, &StringSecurityDescriptor, 0) )
      {
        v12 = (unsigned __int16 *)StrDupe(StringSecurityDescriptor);
        v13 = StringSecurityDescriptor;
        v14 = v12;
        *a2 = v12;
        LocalFree(v13);
        v6 = v14 == 0 ? 0x8007000E : 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v11);
    }
  }
  else
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
  }
LABEL_21:
  WdsRestoreThreadPrivileges(hObject);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v6;
}

```

## disassembly

```asm
0x18000dc28  mov     [rsp-28h+arg_0], rbx
0x18000dc2d  mov     [rsp-28h+arg_8], rsi
0x18000dc32  push    rbp
0x18000dc33  push    rdi
0x18000dc34  push    r12
0x18000dc36  push    r14
0x18000dc38  push    r15
0x18000dc3a  mov     rbp, rsp
0x18000dc3d  sub     rsp, 40h
0x18000dc41  and     [rbp+nLengthNeeded], 0
0x18000dc45  lea     rax, aSesecuritypriv; "SeSecurityPrivilege"
0x18000dc4c  and     [rbp+StringSecurityDescriptor], 0
0x18000dc51  lea     r9, [rbp+hObject]
0x18000dc55  or      [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18000dc5a  mov     r12, rdx
0x18000dc5d  mov     [rbp+var_8], rax
0x18000dc61  mov     r15, rcx
0x18000dc64  mov     r14d, 0Fh
0x18000dc6a  lea     rcx, [rbp+var_8]
0x18000dc6e  lea     eax, [r14-0Eh]
0x18000dc72  mov     r8d, eax
0x18000dc75  mov     edx, eax
0x18000dc77  call    cs:__imp_?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z; WdsSetThreadPrivileges(ushort * *,ulong,int,void * *)
0x18000dc7e  nop     dword ptr [rax+rax+00h]
0x18000dc83  mov     edi, eax
0x18000dc85  test    eax, eax
0x18000dc87  jns     short loc_18000DCD0
0x18000dc89  bt      eax, 1Ch
0x18000dc8d  jnb     short loc_18000DCB4
0x18000dc8f  mov     ecx, eax; Status
0x18000dc91  call    cs:__imp_RtlNtStatusToDosError
0x18000dc98  nop     dword ptr [rax+rax+00h]
0x18000dc9d  cmp     eax, 13Dh
0x18000dca2  jz      short loc_18000DCC3
0x18000dca4  mov     ecx, edi; Status
0x18000dca6  call    cs:__imp_RtlNtStatusToDosError
0x18000dcad  nop     dword ptr [rax+rax+00h]
0x18000dcb2  jmp     short loc_18000DCC5
0x18000dcb4  and     eax, 1FFF0000h
0x18000dcb9  cmp     eax, 70000h
0x18000dcbe  movzx   eax, di
0x18000dcc1  jz      short loc_18000DCC5
0x18000dcc3  mov     eax, edi
0x18000dcc5  cmp     eax, 514h
0x18000dcca  jnz     loc_18000DE4A
0x18000dcd0  lea     rax, [rbp+nLengthNeeded]
0x18000dcd4  xor     r9d, r9d; nLength
0x18000dcd7  xor     r8d, r8d; pSecurityDescriptor
0x18000dcda  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000dcdf  mov     edx, r14d; RequestedInformation
0x18000dce2  mov     rcx, r15; lpFileName
0x18000dce5  call    cs:__imp_GetFileSecurityW
0x18000dcec  nop     dword ptr [rax+rax+00h]
0x18000dcf1  test    eax, eax
0x18000dcf3  jnz     short loc_18000DD2D
0x18000dcf5  call    cs:__imp_GetLastError
0x18000dcfc  nop     dword ptr [rax+rax+00h]
0x18000dd01  cmp     eax, 7Ah ; 'z'
0x18000dd04  jz      short loc_18000DD2D
0x18000dd06  lea     rax, [rbp+nLengthNeeded]
0x18000dd0a  mov     r14d, 7
0x18000dd10  mov     edx, r14d; RequestedInformation
0x18000dd13  mov     [rsp+40h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000dd18  xor     r9d, r9d; nLength
0x18000dd1b  xor     r8d, r8d; pSecurityDescriptor
0x18000dd1e  mov     rcx, r15; lpFileName
0x18000dd21  call    cs:__imp_GetFileSecurityW
0x18000dd28  nop     dword ptr [rax+rax+00h]
0x18000dd2d  call    cs:__imp_GetLastError
0x18000dd34  nop     dword ptr [rax+rax+00h]
0x18000dd39  cmp     eax, 7Ah ; 'z'
0x18000dd3c  jz      short loc_18000DD62
0x18000dd3e  call    cs:__imp_GetLastError
0x18000dd45  nop     dword ptr [rax+rax+00h]
0x18000dd4a  mov     edi, eax
0x18000dd4c  test    eax, eax
0x18000dd4e  jle     loc_18000DE4A
0x18000dd54  movzx   edi, ax
0x18000dd57  or      edi, 80070000h
0x18000dd5d  jmp     loc_18000DE4A
0x18000dd62  mov     ebx, [rbp+nLengthNeeded]
0x18000dd65  mov     edi, 8007000Eh
0x18000dd6a  call    cs:__imp_GetProcessHeap
0x18000dd71  nop     dword ptr [rax+rax+00h]
0x18000dd76  mov     r8d, ebx; dwBytes
0x18000dd79  mov     edx, 8; dwFlags
0x18000dd7e  mov     rcx, rax; hHeap
0x18000dd81  call    cs:__imp_HeapAlloc
0x18000dd88  nop     dword ptr [rax+rax+00h]
0x18000dd8d  mov     rsi, rax
0x18000dd90  test    rax, rax
0x18000dd93  jz      loc_18000DE4A
0x18000dd99  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18000dd9d  lea     rax, [rbp+nLengthNeeded]
0x18000dda1  mov     r8, rsi; pSecurityDescriptor
0x18000dda4  mov     [rsp+40h+lpnLengthNeeded], rax; StringSecurityDescriptorLen
0x18000dda9  mov     edx, r14d; RequestedInformation
0x18000ddac  mov     rcx, r15; lpFileName
0x18000ddaf  call    cs:__imp_GetFileSecurityW
0x18000ddb6  nop     dword ptr [rax+rax+00h]
0x18000ddbb  test    eax, eax
0x18000ddbd  jz      short loc_18000DE0F
0x18000ddbf  and     [rsp+40h+lpnLengthNeeded], 0
0x18000ddc5  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000ddc9  mov     r8d, r14d; SecurityInformation
0x18000ddcc  mov     edx, 1; RequestedStringSDRevision
0x18000ddd1  mov     rcx, rsi; SecurityDescriptor
0x18000ddd4  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000dddb  nop     dword ptr [rax+rax+00h]
0x18000dde0  test    eax, eax
0x18000dde2  jz      short loc_18000DE0F
0x18000dde4  mov     rcx, [rbp+StringSecurityDescriptor]; pszSrc
0x18000dde8  call    StrDupe
0x18000dded  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18000ddf1  mov     rbx, rax
0x18000ddf4  mov     [r12], rax
0x18000ddf8  call    cs:__imp_LocalFree
0x18000ddff  nop     dword ptr [rax+rax+00h]
0x18000de04  neg     rbx
0x18000de07  sbb     eax, eax
0x18000de09  not     eax
0x18000de0b  and     edi, eax
0x18000de0d  jmp     short loc_18000DE2A
0x18000de0f  call    cs:__imp_GetLastError
0x18000de16  nop     dword ptr [rax+rax+00h]
0x18000de1b  mov     edi, eax
0x18000de1d  test    eax, eax
0x18000de1f  jle     short loc_18000DE2A
0x18000de21  movzx   edi, ax
0x18000de24  or      edi, 80070000h
0x18000de2a  call    cs:__imp_GetProcessHeap
0x18000de31  nop     dword ptr [rax+rax+00h]
0x18000de36  mov     r8, rsi; lpMem
0x18000de39  xor     edx, edx; dwFlags
0x18000de3b  mov     rcx, rax; hHeap
0x18000de3e  call    cs:__imp_HeapFree
0x18000de45  nop     dword ptr [rax+rax+00h]
0x18000de4a  mov     rcx, [rbp+hObject]
0x18000de4e  call    cs:__imp_?WdsRestoreThreadPrivileges@@YAJPEAX@Z; WdsRestoreThreadPrivileges(void *)
0x18000de55  nop     dword ptr [rax+rax+00h]
0x18000de5a  mov     rcx, [rbp+hObject]; hObject
0x18000de5e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000de62  jz      short loc_18000DE70
0x18000de64  call    cs:__imp_CloseHandle
0x18000de6b  nop     dword ptr [rax+rax+00h]
0x18000de70  mov     rbx, [rsp+40h+arg_0]
0x18000de75  mov     eax, edi
0x18000de77  mov     rsi, [rsp+40h+arg_8]
0x18000de7c  add     rsp, 40h
0x18000de80  pop     r15
0x18000de82  pop     r14
0x18000de84  pop     r12
0x18000de86  pop     rdi
0x18000de87  pop     rbp
0x18000de88  retn
```
