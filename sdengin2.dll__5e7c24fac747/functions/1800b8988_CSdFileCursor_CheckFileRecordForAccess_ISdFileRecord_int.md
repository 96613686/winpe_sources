# CSdFileCursor::_CheckFileRecordForAccess(ISdFileRecord *,int *)

- ea: `0x1800b8988`
- end: `0x1800b8c41`
- name: `?_CheckFileRecordForAccess@CSdFileCursor@@AEAAJPEAUISdFileRecord@@PEAH@Z`
- size: `697`
- prototype: `__int64 __fastcall(CSdFileCursor *__hidden this, struct ISdFileRecord *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b81f0`
- `0x1800b86e0`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180089968`
- `0x18008f5d0`
- `0x1800b8988`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800b8aed`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800b8aed`
- `KERNEL32!CloseHandle` at `0x1800b8b49`
- `KERNEL32!CloseHandle` at `0x1800b8c04`
- `KERNEL32!CloseHandle` at `0x1800b8b49`
- `KERNEL32!CloseHandle` at `0x1800b8c04`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800b8bab`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800b8bab`
- `ole32!CoTaskMemFree` at `0x1800b8be5`
- `ole32!CoTaskMemFree` at `0x1800b8be5`

## string_xrefs

- `0x1800b89c5`: `CSdFileCursor::_CheckFileRecordForAccess`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "CSdFileCursor::_CheckFileRecordForAccess", 1165, 2);
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
0x1800b8988  mov     [rsp-8+arg_0], rbx
0x1800b898d  mov     [rsp-8+arg_18], rsi
0x1800b8992  push    rbp
0x1800b8993  push    rdi
0x1800b8994  push    r14
0x1800b8996  lea     rbp, [rsp-47h]
0x1800b899b  sub     rsp, 100h
0x1800b89a2  mov     rax, cs:__security_cookie
0x1800b89a9  xor     rax, rsp
0x1800b89ac  mov     [rbp+57h+var_20], rax
0x1800b89b0  mov     rdi, r8
0x1800b89b3  mov     rsi, rdx
0x1800b89b6  mov     r14, rcx
0x1800b89b9  mov     r9d, 2; unsigned __int16
0x1800b89bf  mov     r8d, 48Dh; unsigned __int16
0x1800b89c5  lea     rdx, aCsdfilecursorC_2; "CSdFileCursor::_CheckFileRecordForAcces"...
0x1800b89cc  lea     rcx, [rbp+57h+var_B0]; this
0x1800b89d0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b89d5  mov     [rbp+57h+hObject], 0
0x1800b89dd  mov     [rbp+57h+SecurityDescriptorLength], 0
0x1800b89e4  mov     [rbp+57h+SecurityDescriptorInput], 0
0x1800b89ec  mov     [rbp+57h+var_C4], 0
0x1800b89f3  mov     [rbp+57h+var_B8], 0
0x1800b89fa  mov     [rbp+57h+var_70.PrivilegeCount], 0
0x1800b8a01  xor     edx, edx; Val
0x1800b8a03  lea     r8d, [rdx+4Ch]; Size
0x1800b8a07  lea     rcx, [rbp+57h+var_70.Control]; void *
0x1800b8a0b  call    memset_0
0x1800b8a10  mov     [rbp+57h+var_B4], 50h ; 'P'
0x1800b8a17  test    rdi, rdi
0x1800b8a1a  jz      short loc_1800B8A22
0x1800b8a1c  mov     dword ptr [rdi], 0
0x1800b8a22  mov     eax, 498h
0x1800b8a27  test    rsi, rsi
0x1800b8a2a  jnz     short loc_1800B8A3A
0x1800b8a2c  mov     ebx, 80070057h
0x1800b8a31  mov     [rbp+57h+var_AA], ax
0x1800b8a35  jmp     loc_1800B8BD9
0x1800b8a3a  mov     [rbp+57h+var_AC], ax
0x1800b8a3e  mov     eax, 499h
0x1800b8a43  test    rdi, rdi
0x1800b8a46  jz      short loc_1800B8A2C
0x1800b8a48  xor     ebx, ebx
0x1800b8a4a  mov     [rbp+57h+var_B0], ebx
0x1800b8a4d  mov     [rbp+57h+var_AC], ax
0x1800b8a51  cmp     [r14+0E0h], ebx
0x1800b8a58  jnz     short loc_1800B8A6E
0x1800b8a5a  mov     dword ptr [rdi], 1
0x1800b8a60  mov     eax, 49Eh
0x1800b8a65  mov     [rbp+57h+var_AC], ax
0x1800b8a69  jmp     loc_1800B8BDC
0x1800b8a6e  mov     rax, [rsi]
0x1800b8a71  lea     r8, [rbp+57h+SecurityDescriptorLength]
0x1800b8a75  lea     rdx, [rbp+57h+SecurityDescriptorInput]
0x1800b8a79  mov     rcx, rsi
0x1800b8a7c  mov     rax, [rax+88h]
0x1800b8a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8a88  mov     ebx, eax
0x1800b8a8a  mov     [rbp+57h+var_B0], eax
0x1800b8a8d  test    eax, eax
0x1800b8a8f  mov     eax, 4A1h
0x1800b8a94  jns     short loc_1800B8A9F
0x1800b8a96  mov     [rbp+57h+var_AA], ax
0x1800b8a9a  jmp     loc_1800B8BDC
0x1800b8a9f  mov     [rbp+57h+var_AC], ax
0x1800b8aa3  mov     edx, [rbp+57h+SecurityDescriptorLength]; SecurityDescriptorLength
0x1800b8aa6  mov     eax, 4A2h
0x1800b8aab  cmp     edx, 7FFFFFFFh
0x1800b8ab1  jb      short loc_1800B8ABD
0x1800b8ab3  mov     ebx, 81000034h
0x1800b8ab8  jmp     loc_1800B8A31
0x1800b8abd  xor     ebx, ebx
0x1800b8abf  mov     [rbp+57h+var_B0], ebx
0x1800b8ac2  mov     [rbp+57h+var_AC], ax
0x1800b8ac6  mov     rcx, [rbp+57h+SecurityDescriptorInput]; SecurityDescriptorInput
0x1800b8aca  test    rcx, rcx
0x1800b8acd  jnz     short loc_1800B8AE7
0x1800b8acf  test    edx, edx
0x1800b8ad1  jnz     short loc_1800B8AE7
0x1800b8ad3  mov     dword ptr [rdi], 1
0x1800b8ad9  mov     eax, 4A7h
0x1800b8ade  mov     [rbp+57h+var_AC], ax
0x1800b8ae2  jmp     loc_1800B8BF6
0x1800b8ae7  mov     r8d, 0Fh; RequiredInformation
0x1800b8aed  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800b8af3  test    al, al
0x1800b8af5  jnz     short loc_1800B8B3B
0x1800b8af7  lea     rax, WPP_GLOBAL_Control
0x1800b8afe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8b05  cmp     rcx, rax
0x1800b8b08  jz      short loc_1800B8B28
0x1800b8b0a  test    dword ptr [rcx+1Ch], 1000000h
0x1800b8b11  jz      short loc_1800B8B28
0x1800b8b13  mov     edx, 0Ah
0x1800b8b18  lea     r8, WPP_fe79a416f70f3748e10163690077993c_Traceguids
0x1800b8b1f  mov     rcx, [rcx+10h]
0x1800b8b23  call    WPP_SF_
0x1800b8b28  mov     ebx, 1
0x1800b8b2d  mov     eax, 4AFh
0x1800b8b32  mov     [rbp+57h+var_AC], ax
0x1800b8b36  jmp     loc_1800B8BD9
0x1800b8b3b  mov     rcx, [rbp+57h+hObject]; hObject
0x1800b8b3f  lea     rax, [rcx-1]
0x1800b8b43  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b8b47  ja      short loc_1800B8B53
0x1800b8b49  call    cs:__imp_CloseHandle
0x1800b8b4f  mov     [rbp+57h+hObject], rbx
0x1800b8b53  lea     rcx, [rbp+57h+hObject]; TokenHandle
0x1800b8b57  call    ?OpenThreadAccessToken@@YAJPEAPEAX@Z; OpenThreadAccessToken(void * *)
0x1800b8b5c  mov     ebx, eax
0x1800b8b5e  mov     [rbp+57h+var_B0], eax
0x1800b8b61  test    eax, eax
0x1800b8b63  mov     eax, 4B2h
0x1800b8b68  js      loc_1800B8A96
0x1800b8b6e  mov     [rbp+57h+var_AC], ax
0x1800b8b72  lea     rax, [rbp+57h+var_C4]
0x1800b8b76  mov     [rsp+110h+AccessStatus], rax; AccessStatus
0x1800b8b7b  lea     rax, [rbp+57h+var_B8]
0x1800b8b7f  mov     [rsp+110h+GrantedAccess], rax; GrantedAccess
0x1800b8b84  lea     rax, [rbp+57h+var_B4]
0x1800b8b88  mov     [rsp+110h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800b8b8d  lea     rax, [rbp+57h+var_70]
0x1800b8b91  mov     [rsp+110h+PrivilegeSet], rax; PrivilegeSet
0x1800b8b96  lea     r9, GenericMapping; GenericMapping
0x1800b8b9d  mov     r8d, 120089h; DesiredAccess
0x1800b8ba3  mov     rdx, [rbp+57h+hObject]; ClientToken
0x1800b8ba7  mov     rcx, [rbp+57h+SecurityDescriptorInput]; pSecurityDescriptor
0x1800b8bab  call    cs:__imp_AccessCheck
0x1800b8bb1  test    eax, eax
0x1800b8bb3  jnz     short loc_1800B8BC9
0x1800b8bb5  call    GetLastFailureAsHRESULT
0x1800b8bba  mov     ebx, eax
0x1800b8bbc  mov     [rbp+57h+var_B0], eax
0x1800b8bbf  mov     eax, 4B4h
0x1800b8bc4  jmp     loc_1800B8A96
0x1800b8bc9  xor     ebx, ebx
0x1800b8bcb  mov     eax, 4B4h
0x1800b8bd0  mov     [rbp+57h+var_AC], ax
0x1800b8bd4  mov     eax, [rbp+57h+var_C4]
0x1800b8bd7  mov     [rdi], eax
0x1800b8bd9  mov     [rbp+57h+var_B0], ebx
0x1800b8bdc  mov     rcx, [rbp+57h+SecurityDescriptorInput]; pv
0x1800b8be0  test    rcx, rcx
0x1800b8be3  jz      short loc_1800B8BF6
0x1800b8be5  call    cs:__imp_CoTaskMemFree
0x1800b8beb  mov     [rbp+57h+SecurityDescriptorInput], 0
0x1800b8bf3  mov     ebx, [rbp+57h+var_B0]
0x1800b8bf6  mov     rcx, [rbp+57h+hObject]; hObject
0x1800b8bfa  lea     rdx, [rcx-1]
0x1800b8bfe  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800b8c02  ja      short loc_1800B8C12
0x1800b8c04  call    cs:__imp_CloseHandle
0x1800b8c0a  mov     [rbp+57h+hObject], 0
0x1800b8c12  lea     rcx, [rbp+57h+var_B0]; this
0x1800b8c16  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800b8c1b  mov     eax, ebx
0x1800b8c1d  mov     rcx, [rbp+57h+var_20]
0x1800b8c21  xor     rcx, rsp; StackCookie
0x1800b8c24  call    __security_check_cookie
0x1800b8c29  lea     r11, [rsp+110h+var_10]
0x1800b8c31  mov     rbx, [r11+20h]
0x1800b8c35  mov     rsi, [r11+38h]
0x1800b8c39  mov     rsp, r11
0x1800b8c3c  pop     r14
0x1800b8c3e  pop     rdi
0x1800b8c3f  pop     rbp
0x1800b8c40  retn
```
