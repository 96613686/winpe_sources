# CSdFileCursor::_CheckFileRecordForAccess(ISdFileRecord *,int *)

- ea: `0x1800be478`
- end: `0x1800be750`
- name: `?_CheckFileRecordForAccess@CSdFileCursor@@AEAAJPEAUISdFileRecord@@PEAH@Z`
- size: `728`
- prototype: `__int64 __fastcall(CSdFileCursor *__hidden this, struct ISdFileRecord *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bdce0`
- `0x1800be1d0`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x18008d4e8`
- `0x1800935fc`
- `0x1800be478`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800be5dd`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800be5dd`
- `KERNEL32!CloseHandle` at `0x1800be63f`
- `KERNEL32!CloseHandle` at `0x1800be70c`
- `KERNEL32!CloseHandle` at `0x1800be63f`
- `KERNEL32!CloseHandle` at `0x1800be70c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800be6a7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800be6a7`
- `ole32!CoTaskMemFree` at `0x1800be6e7`
- `ole32!CoTaskMemFree` at `0x1800be6e7`

## string_xrefs

- `0x1800be4b5`: `CSdFileCursor::_CheckFileRecordForAccess`

## pseudocode

```c
__int64 __fastcall CSdFileCursor::_CheckFileRecordForAccess(CSdFileCursor *this, struct ISdFileRecord *a2, int *a3)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v8; // ax
  __int64 v9; // rcx
  HANDLE hObject; // [rsp+40h] [rbp-79h] BYREF
  ULONG SecurityDescriptorLength; // [rsp+48h] [rbp-71h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-6Dh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptorInput; // [rsp+50h] [rbp-69h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-61h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp-5Dh] BYREF
  int v17; // [rsp+60h] [rbp-59h] BYREF
  __int16 v18; // [rsp+64h] [rbp-55h]
  __int16 v19; // [rsp+66h] [rbp-53h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+A0h] [rbp-19h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v17,
    "CSdFileCursor::_CheckFileRecordForAccess",
    0x48Du,
    2u);
  hObject = 0;
  SecurityDescriptorLength = 0;
  SecurityDescriptorInput = 0;
  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSet.PrivilegeCount = 0;
  memset_0(&PrivilegeSet.Control, 0, 0x4Cu);
  PrivilegeSetLength = 80;
  if ( a3 )
    *a3 = 0;
  v6 = 1176;
  if ( a2 && (v18 = 1176, v6 = 1177, a3) )
  {
    LastFailureAsHRESULT = 0;
    v17 = 0;
    v18 = 1177;
    if ( !*((_DWORD *)this + 56) )
    {
      *a3 = 1;
      v18 = 1182;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, PSECURITY_DESCRIPTOR *, ULONG *))(*(_QWORD *)a2 + 136LL))(
                             a2,
                             &SecurityDescriptorInput,
                             &SecurityDescriptorLength);
    v17 = LastFailureAsHRESULT;
    v8 = 1185;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_10;
    v18 = 1185;
    v6 = 1186;
    if ( SecurityDescriptorLength < 0x7FFFFFFF )
    {
      LastFailureAsHRESULT = 0;
      v17 = 0;
      v18 = 1186;
      if ( !SecurityDescriptorInput && !SecurityDescriptorLength )
      {
        *a3 = 1;
        v18 = 1191;
        goto LABEL_30;
      }
      if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0xFu) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fe79a416f70f3748e10163690077993c_Traceguids);
        LastFailureAsHRESULT = 1;
        v18 = 1199;
        goto LABEL_27;
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      LastFailureAsHRESULT = OpenThreadAccessToken(&hObject);
      v17 = LastFailureAsHRESULT;
      v8 = 1202;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v18 = 1202;
        if ( AccessCheck(
               SecurityDescriptorInput,
               hObject,
               0x120089u,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus) )
        {
          LastFailureAsHRESULT = 0;
          v18 = 1204;
          *a3 = AccessStatus;
          goto LABEL_27;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v17 = LastFailureAsHRESULT;
        v8 = 1204;
      }
LABEL_10:
      v19 = v8;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = -2130706380;
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
  }
  v19 = v6;
LABEL_27:
  v17 = LastFailureAsHRESULT;
LABEL_28:
  if ( SecurityDescriptorInput )
  {
    CoTaskMemFree(SecurityDescriptorInput);
    SecurityDescriptorInput = 0;
    LastFailureAsHRESULT = v17;
  }
LABEL_30:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800be478  mov     [rsp-8+arg_0], rbx
0x1800be47d  mov     [rsp-8+arg_18], rsi
0x1800be482  push    rbp
0x1800be483  push    rdi
0x1800be484  push    r14
0x1800be486  lea     rbp, [rsp-47h]
0x1800be48b  sub     rsp, 100h
0x1800be492  mov     rax, cs:__security_cookie
0x1800be499  xor     rax, rsp
0x1800be49c  mov     [rbp+57h+var_20], rax
0x1800be4a0  mov     rdi, r8
0x1800be4a3  mov     rsi, rdx
0x1800be4a6  mov     r14, rcx
0x1800be4a9  mov     r9d, 2; unsigned __int16
0x1800be4af  mov     r8d, 48Dh; unsigned __int16
0x1800be4b5  lea     rdx, aCsdfilecursorC_2; "CSdFileCursor::_CheckFileRecordForAcces"...
0x1800be4bc  lea     rcx, [rbp+57h+var_B0]; this
0x1800be4c0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800be4c5  mov     [rbp+57h+hObject], 0
0x1800be4cd  mov     [rbp+57h+SecurityDescriptorLength], 0
0x1800be4d4  mov     [rbp+57h+SecurityDescriptorInput], 0
0x1800be4dc  mov     [rbp+57h+var_C4], 0
0x1800be4e3  mov     [rbp+57h+var_B8], 0
0x1800be4ea  mov     [rbp+57h+var_70.PrivilegeCount], 0
0x1800be4f1  xor     edx, edx; Val
0x1800be4f3  lea     r8d, [rdx+4Ch]; Size
0x1800be4f7  lea     rcx, [rbp+57h+var_70.Control]; void *
0x1800be4fb  call    memset_0
0x1800be500  mov     [rbp+57h+var_B4], 50h ; 'P'
0x1800be507  test    rdi, rdi
0x1800be50a  jz      short loc_1800BE512
0x1800be50c  mov     dword ptr [rdi], 0
0x1800be512  mov     eax, 498h
0x1800be517  test    rsi, rsi
0x1800be51a  jnz     short loc_1800BE52A
0x1800be51c  mov     ebx, 80070057h
0x1800be521  mov     [rbp+57h+var_AA], ax
0x1800be525  jmp     loc_1800BE6DB
0x1800be52a  mov     [rbp+57h+var_AC], ax
0x1800be52e  mov     eax, 499h
0x1800be533  test    rdi, rdi
0x1800be536  jz      short loc_1800BE51C
0x1800be538  xor     ebx, ebx
0x1800be53a  mov     [rbp+57h+var_B0], ebx
0x1800be53d  mov     [rbp+57h+var_AC], ax
0x1800be541  cmp     [r14+0E0h], ebx
0x1800be548  jnz     short loc_1800BE55E
0x1800be54a  mov     dword ptr [rdi], 1
0x1800be550  mov     eax, 49Eh
0x1800be555  mov     [rbp+57h+var_AC], ax
0x1800be559  jmp     loc_1800BE6DE
0x1800be55e  mov     rax, [rsi]
0x1800be561  lea     r8, [rbp+57h+SecurityDescriptorLength]
0x1800be565  lea     rdx, [rbp+57h+SecurityDescriptorInput]
0x1800be569  mov     rcx, rsi
0x1800be56c  mov     rax, [rax+88h]
0x1800be573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be578  mov     ebx, eax
0x1800be57a  mov     [rbp+57h+var_B0], eax
0x1800be57d  test    eax, eax
0x1800be57f  mov     eax, 4A1h
0x1800be584  jns     short loc_1800BE58F
0x1800be586  mov     [rbp+57h+var_AA], ax
0x1800be58a  jmp     loc_1800BE6DE
0x1800be58f  mov     [rbp+57h+var_AC], ax
0x1800be593  mov     edx, [rbp+57h+SecurityDescriptorLength]; SecurityDescriptorLength
0x1800be596  mov     eax, 4A2h
0x1800be59b  cmp     edx, 7FFFFFFFh
0x1800be5a1  jb      short loc_1800BE5AD
0x1800be5a3  mov     ebx, 81000034h
0x1800be5a8  jmp     loc_1800BE521
0x1800be5ad  xor     ebx, ebx
0x1800be5af  mov     [rbp+57h+var_B0], ebx
0x1800be5b2  mov     [rbp+57h+var_AC], ax
0x1800be5b6  mov     rcx, [rbp+57h+SecurityDescriptorInput]; SecurityDescriptorInput
0x1800be5ba  test    rcx, rcx
0x1800be5bd  jnz     short loc_1800BE5D7
0x1800be5bf  test    edx, edx
0x1800be5c1  jnz     short loc_1800BE5D7
0x1800be5c3  mov     dword ptr [rdi], 1
0x1800be5c9  mov     eax, 4A7h
0x1800be5ce  mov     [rbp+57h+var_AC], ax
0x1800be5d2  jmp     loc_1800BE6FE
0x1800be5d7  mov     r8d, 0Fh; RequiredInformation
0x1800be5dd  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800be5e4  nop     dword ptr [rax+rax+00h]
0x1800be5e9  test    al, al
0x1800be5eb  jnz     short loc_1800BE631
0x1800be5ed  lea     rax, WPP_GLOBAL_Control
0x1800be5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5fb  cmp     rcx, rax
0x1800be5fe  jz      short loc_1800BE61E
0x1800be600  test    dword ptr [rcx+1Ch], 1000000h
0x1800be607  jz      short loc_1800BE61E
0x1800be609  mov     edx, 0Ah
0x1800be60e  lea     r8, WPP_fe79a416f70f3748e10163690077993c_Traceguids
0x1800be615  mov     rcx, [rcx+10h]
0x1800be619  call    WPP_SF_
0x1800be61e  mov     ebx, 1
0x1800be623  mov     eax, 4AFh
0x1800be628  mov     [rbp+57h+var_AC], ax
0x1800be62c  jmp     loc_1800BE6DB
0x1800be631  mov     rcx, [rbp+57h+hObject]; hObject
0x1800be635  lea     rax, [rcx-1]
0x1800be639  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800be63d  ja      short loc_1800BE64F
0x1800be63f  call    cs:__imp_CloseHandle
0x1800be646  nop     dword ptr [rax+rax+00h]
0x1800be64b  mov     [rbp+57h+hObject], rbx
0x1800be64f  lea     rcx, [rbp+57h+hObject]; TokenHandle
0x1800be653  call    ?OpenThreadAccessToken@@YAJPEAPEAX@Z; OpenThreadAccessToken(void * *)
0x1800be658  mov     ebx, eax
0x1800be65a  mov     [rbp+57h+var_B0], eax
0x1800be65d  test    eax, eax
0x1800be65f  mov     eax, 4B2h
0x1800be664  js      loc_1800BE586
0x1800be66a  mov     [rbp+57h+var_AC], ax
0x1800be66e  lea     rax, [rbp+57h+var_C4]
0x1800be672  mov     [rsp+110h+AccessStatus], rax; AccessStatus
0x1800be677  lea     rax, [rbp+57h+var_B8]
0x1800be67b  mov     [rsp+110h+GrantedAccess], rax; GrantedAccess
0x1800be680  lea     rax, [rbp+57h+var_B4]
0x1800be684  mov     [rsp+110h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800be689  lea     rax, [rbp+57h+var_70]
0x1800be68d  mov     [rsp+110h+PrivilegeSet], rax; PrivilegeSet
0x1800be692  lea     r9, GenericMapping; GenericMapping
0x1800be699  mov     r8d, 120089h; DesiredAccess
0x1800be69f  mov     rdx, [rbp+57h+hObject]; ClientToken
0x1800be6a3  mov     rcx, [rbp+57h+SecurityDescriptorInput]; pSecurityDescriptor
0x1800be6a7  call    cs:__imp_AccessCheck
0x1800be6ae  nop     dword ptr [rax+rax+00h]
0x1800be6b3  test    eax, eax
0x1800be6b5  jnz     short loc_1800BE6CB
0x1800be6b7  call    GetLastFailureAsHRESULT
0x1800be6bc  mov     ebx, eax
0x1800be6be  mov     [rbp+57h+var_B0], eax
0x1800be6c1  mov     eax, 4B4h
0x1800be6c6  jmp     loc_1800BE586
0x1800be6cb  xor     ebx, ebx
0x1800be6cd  mov     eax, 4B4h
0x1800be6d2  mov     [rbp+57h+var_AC], ax
0x1800be6d6  mov     eax, [rbp+57h+var_C4]
0x1800be6d9  mov     [rdi], eax
0x1800be6db  mov     [rbp+57h+var_B0], ebx
0x1800be6de  mov     rcx, [rbp+57h+SecurityDescriptorInput]; pv
0x1800be6e2  test    rcx, rcx
0x1800be6e5  jz      short loc_1800BE6FE
0x1800be6e7  call    cs:__imp_CoTaskMemFree
0x1800be6ee  nop     dword ptr [rax+rax+00h]
0x1800be6f3  mov     [rbp+57h+SecurityDescriptorInput], 0
0x1800be6fb  mov     ebx, [rbp+57h+var_B0]
0x1800be6fe  mov     rcx, [rbp+57h+hObject]; hObject
0x1800be702  lea     rdx, [rcx-1]
0x1800be706  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800be70a  ja      short loc_1800BE720
0x1800be70c  call    cs:__imp_CloseHandle
0x1800be713  nop     dword ptr [rax+rax+00h]
0x1800be718  mov     [rbp+57h+hObject], 0
0x1800be720  lea     rcx, [rbp+57h+var_B0]; this
0x1800be724  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800be729  mov     eax, ebx
0x1800be72b  mov     rcx, [rbp+57h+var_20]
0x1800be72f  xor     rcx, rsp; StackCookie
0x1800be732  call    __security_check_cookie
0x1800be737  lea     r11, [rsp+110h+var_10]
0x1800be73f  mov     rbx, [r11+20h]
0x1800be743  mov     rsi, [r11+38h]
0x1800be747  mov     rsp, r11
0x1800be74a  pop     r14
0x1800be74c  pop     rdi
0x1800be74d  pop     rbp
0x1800be74e  retn
```
