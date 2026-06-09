# CWerService::IsAppContainerHangValid(void *,ulong *)

- ea: `0x1800157b4`
- end: `0x180015aa0`
- name: `?IsAppContainerHangValid@CWerService@@AEAA_NPEAXPEAK@Z`
- size: `748`
- prototype: `bool __fastcall(CWerService *this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180019fc8`

## callees

- `0x1800029f4`
- `0x180011ef8`
- `0x1800157b4`
- `0x18001e57c`
- `0x18002fbb0`
- `0x18002fda8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800158b5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800158b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015954`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015a4b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015890`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015890`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall CWerService::IsAppContainerHangValid(CWerService *this, void *a2, unsigned int *a3)
{
  unsigned int v5; // ebx
  int ProcessPackageFullName; // eax
  __int64 v7; // r15
  DWORD v8; // r14d
  HANDLE v9; // rax
  void *v10; // rdi
  int IsPackagedApplication; // eax
  void *v12; // rcx
  int v13; // eax
  __int16 *v14; // r8
  bool v15; // bl
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  signed int LastError; // eax
  signed int v21; // eax
  __int64 v22; // r8
  __int16 v23; // [rsp+40h] [rbp-30h] BYREF
  LPCWCH lpString1; // [rsp+50h] [rbp-20h]
  _WORD *v25; // [rsp+58h] [rbp-18h]
  _WORD v26[8]; // [rsp+60h] [rbp-10h] BYREF
  CWerService *ExitCode; // [rsp+A0h] [rbp+30h] BYREF

  ExitCode = this;
  lpString1 = v26;
  v25 = v26;
  v26[0] = 0;
  v23 = 0;
  if ( !a3 || !(unsigned int)PackageUtility::IsPackagedApplication(a2) )
  {
    v5 = -2147024809;
    goto LABEL_22;
  }
  ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(a2);
  v5 = ProcessPackageFullName;
  if ( ProcessPackageFullName < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        179,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)ProcessPackageFullName);
    goto LABEL_22;
  }
  v7 = 0;
  while ( 1 )
  {
    v8 = a3[v7];
    if ( !v8 )
      goto LABEL_20;
    v9 = OpenProcess(0x1000u, 0, v8);
    v10 = v9;
    if ( (unsigned __int64)v9 + 1 <= 1 )
      break;
    LODWORD(ExitCode) = 0;
    if ( !GetExitCodeProcess(v9, (LPDWORD)&ExitCode) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v18 = 181;
LABEL_37:
      v19 = v5;
LABEL_38:
      WPP_SF_dD(v17[2], v18, v14, v19, v8);
      goto LABEL_39;
    }
    if ( (_DWORD)ExitCode == 259 )
    {
      IsPackagedApplication = PackageUtility::IsPackagedApplication(v10);
      v12 = v10;
      if ( !IsPackagedApplication )
      {
        v5 = -2147024809;
        goto LABEL_40;
      }
      v13 = PackageUtility::GetProcessPackageFullName(v10);
      v5 = v13;
      if ( v13 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_39;
        v18 = 183;
        v19 = (unsigned int)v13;
        goto LABEL_38;
      }
      v14 = &v23;
      if ( v25 - lpString1 )
      {
        v5 = -2147024809;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v18 = 184;
          goto LABEL_37;
        }
LABEL_39:
        v12 = v10;
LABEL_40:
        CloseHandle(v12);
        goto LABEL_22;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v8);
    }
    CloseHandle(v10);
LABEL_20:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= 0x10 )
    {
      v5 = 0;
      goto LABEL_22;
    }
  }
  v21 = GetLastError();
  v5 = v21;
  if ( v21 > 0 )
    v5 = (unsigned __int16)v21 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, v22, v5, v8);
LABEL_22:
  v15 = (v5 & 0x80000000) == 0;
  if ( lpString1 != v26 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  return v15;
}

```

## disassembly

```asm
0x1800157b4  mov     [rsp-28h+arg_8], rbx
0x1800157b9  mov     [rsp-28h+arg_10], rsi
0x1800157be  mov     [rsp-28h+ExitCode], rcx
0x1800157c3  push    rbp
0x1800157c4  push    rdi
0x1800157c5  push    r12
0x1800157c7  push    r14
0x1800157c9  push    r15
0x1800157cb  mov     rbp, rsp
0x1800157ce  sub     rsp, 70h
0x1800157d2  lea     rax, [rbp+var_10]
0x1800157d6  mov     r12, r8
0x1800157d9  mov     [rbp+lpString1], rax
0x1800157dd  mov     rbx, rdx
0x1800157e0  lea     rax, [rbp+var_10]
0x1800157e4  mov     [rbp+var_18], rax
0x1800157e8  xor     eax, eax
0x1800157ea  mov     [rbp+var_10], ax
0x1800157ee  lea     rax, [rbp+var_30]
0x1800157f2  mov     [rbp+lpString2], rax
0x1800157f6  lea     rax, [rbp+var_30]
0x1800157fa  mov     [rbp+var_38], rax
0x1800157fe  xor     eax, eax
0x180015800  mov     [rbp+var_30], ax
0x180015804  test    r8, r8
0x180015807  jnz     short loc_180015813
0x180015809  mov     ebx, 80070057h
0x18001580e  jmp     loc_180015977
0x180015813  mov     rcx, rbx; hProcess
0x180015816  call    ?IsPackagedApplication@PackageUtility@@SAHPEAX@Z; PackageUtility::IsPackagedApplication(void *)
0x18001581b  test    eax, eax
0x18001581d  jz      short loc_180015809
0x18001581f  lea     rdx, [rbp+lpString1]
0x180015823  mov     rcx, rbx; hProcess
0x180015826  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001582b  mov     ebx, eax
0x18001582d  test    eax, eax
0x18001582f  jns     short loc_18001586F
0x180015831  mov     rcx, cs:WPP_GLOBAL_Control
0x180015838  lea     rsi, WPP_GLOBAL_Control
0x18001583f  cmp     rcx, rsi
0x180015842  jz      loc_180015977
0x180015848  test    byte ptr [rcx+1Ch], 2
0x18001584c  jz      loc_180015977
0x180015852  mov     rcx, [rcx+10h]
0x180015856  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001585d  mov     edx, 0B3h
0x180015862  mov     r9d, eax
0x180015865  call    WPP_SF_d
0x18001586a  jmp     loc_180015977
0x18001586f  xor     r15d, r15d
0x180015872  lea     rsi, WPP_GLOBAL_Control
0x180015879  mov     r14d, [r12+r15*4]
0x18001587d  test    r14d, r14d
0x180015880  jz      loc_180015968
0x180015886  mov     r8d, r14d; dwProcessId
0x180015889  xor     edx, edx; bInheritHandle
0x18001588b  mov     ecx, 1000h; dwDesiredAccess
0x180015890  call    cs:__imp_OpenProcess
0x180015896  mov     rdi, rax
0x180015899  lea     rcx, [rax+1]
0x18001589d  cmp     rcx, 1
0x1800158a1  jbe     loc_180015A56
0x1800158a7  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800158ab  mov     dword ptr [rbp+ExitCode], 0
0x1800158b2  mov     rcx, rax; hProcess
0x1800158b5  call    cs:__imp_GetExitCodeProcess
0x1800158bb  test    eax, eax
0x1800158bd  jz      loc_180015A0B
0x1800158c3  cmp     dword ptr [rbp+ExitCode], 103h
0x1800158ca  jz      short loc_1800158FC
0x1800158cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158d3  cmp     rcx, rsi
0x1800158d6  jz      loc_18001595F
0x1800158dc  test    byte ptr [rcx+1Ch], 2
0x1800158e0  jz      short loc_18001595F
0x1800158e2  mov     rcx, [rcx+10h]
0x1800158e6  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800158ed  mov     edx, 0B6h
0x1800158f2  mov     r9d, r14d
0x1800158f5  call    WPP_SF_d
0x1800158fa  jmp     short loc_18001595F
0x1800158fc  mov     rcx, rdi; hProcess
0x1800158ff  call    ?IsPackagedApplication@PackageUtility@@SAHPEAX@Z; PackageUtility::IsPackagedApplication(void *)
0x180015904  mov     rcx, rdi; hProcess
0x180015907  test    eax, eax
0x180015909  jz      loc_180015A04
0x18001590f  lea     rdx, [rbp+lpString2]
0x180015913  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180015918  mov     ebx, eax
0x18001591a  test    eax, eax
0x18001591c  js      loc_1800159E8
0x180015922  mov     r8, [rbp+lpString2]; lpString2
0x180015926  mov     r9, [rbp+var_38]
0x18001592a  mov     rcx, [rbp+lpString1]; lpString1
0x18001592e  sub     r9, r8
0x180015931  mov     rdx, [rbp+var_18]
0x180015935  sub     rdx, rcx
0x180015938  sar     r9, 1; cchCount2
0x18001593b  sar     rdx, 1; cchCount1
0x18001593e  cmp     rdx, r9
0x180015941  jnz     loc_1800159CA
0x180015947  test    rdx, rdx
0x18001594a  jz      short loc_18001595F
0x18001594c  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180015954  call    cs:__imp_CompareStringOrdinal
0x18001595a  cmp     eax, 2
0x18001595d  jnz     short loc_1800159CA
0x18001595f  mov     rcx, rdi; hObject
0x180015962  call    cs:__imp_CloseHandle
0x180015968  inc     r15d
0x18001596b  cmp     r15d, 10h
0x18001596f  jb      loc_180015879
0x180015975  xor     ebx, ebx
0x180015977  mov     rcx, [rbp+lpString2]; void *
0x18001597b  lea     rax, [rbp+var_30]
0x18001597f  shr     ebx, 1Fh
0x180015982  xor     bl, 1
0x180015985  cmp     rcx, rax
0x180015988  jz      short loc_180015996
0x18001598a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015991  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015996  mov     rcx, [rbp+lpString1]; void *
0x18001599a  lea     rax, [rbp+var_10]
0x18001599e  cmp     rcx, rax
0x1800159a1  jz      short loc_1800159AF
0x1800159a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800159aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800159af  lea     r11, [rsp+70h+var_s0]
0x1800159b4  mov     al, bl
0x1800159b6  mov     rbx, [r11+38h]
0x1800159ba  mov     rsi, [r11+40h]
0x1800159be  mov     rsp, r11
0x1800159c1  pop     r15
0x1800159c3  pop     r14
0x1800159c5  pop     r12
0x1800159c7  pop     rdi
0x1800159c8  pop     rbp
0x1800159c9  retn
0x1800159ca  mov     ebx, 80070057h
0x1800159cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159d6  cmp     rcx, rsi
0x1800159d9  jz      short loc_180015A48
0x1800159db  test    byte ptr [rcx+1Ch], 2
0x1800159df  jz      short loc_180015A48
0x1800159e1  mov     edx, 0B8h
0x1800159e6  jmp     short loc_180015A37
0x1800159e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159ef  cmp     rcx, rsi
0x1800159f2  jz      short loc_180015A48
0x1800159f4  test    byte ptr [rcx+1Ch], 2
0x1800159f8  jz      short loc_180015A48
0x1800159fa  mov     edx, 0B7h
0x1800159ff  mov     r9d, eax
0x180015a02  jmp     short loc_180015A3A
0x180015a04  mov     ebx, 80070057h
0x180015a09  jmp     short loc_180015A4B
0x180015a0b  call    cs:__imp_GetLastError
0x180015a11  mov     ebx, eax
0x180015a13  test    eax, eax
0x180015a15  jle     short loc_180015A20
0x180015a17  movzx   ebx, ax
0x180015a1a  or      ebx, 80070000h
0x180015a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a27  cmp     rcx, rsi
0x180015a2a  jz      short loc_180015A48
0x180015a2c  test    byte ptr [rcx+1Ch], 2
0x180015a30  jz      short loc_180015A48
0x180015a32  mov     edx, 0B5h
0x180015a37  mov     r9d, ebx
0x180015a3a  mov     rcx, [rcx+10h]
0x180015a3e  mov     [rsp+70h+bIgnoreCase], r14d
0x180015a43  call    WPP_SF_dD
0x180015a48  mov     rcx, rdi; hObject
0x180015a4b  call    cs:__imp_CloseHandle
0x180015a51  jmp     loc_180015977
0x180015a56  call    cs:__imp_GetLastError
0x180015a5c  mov     ebx, eax
0x180015a5e  test    eax, eax
0x180015a60  jle     short loc_180015A6B
0x180015a62  movzx   ebx, ax
0x180015a65  or      ebx, 80070000h
0x180015a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a72  cmp     rcx, rsi
0x180015a75  jz      loc_180015977
0x180015a7b  test    byte ptr [rcx+1Ch], 2
0x180015a7f  jz      loc_180015977
0x180015a85  mov     rcx, [rcx+10h]
0x180015a89  mov     edx, 0B4h
0x180015a8e  mov     r9d, ebx
0x180015a91  mov     [rsp+70h+bIgnoreCase], r14d
0x180015a96  call    WPP_SF_dD
0x180015a9b  jmp     loc_180015977
```
