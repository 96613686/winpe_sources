# UtilIsWriteRestrictedToken(void *)

- ea: `0x1800062d0`
- end: `0x180006473`
- name: `?UtilIsWriteRestrictedToken@@YA_NPEAX@Z`
- size: `419`
- prototype: `bool __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a370`
- `0x180070f3c`

## callees

- `0x180004bb4`
- `0x1800062d0`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006398`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006330`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180006330`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800063b2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800063b2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006408`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180006408`

## pseudocode

```c
bool __fastcall UtilIsWriteRestrictedToken(HANDLE ExistingTokenHandle)
{
  BOOL v2; // ebx
  DWORD v3; // eax
  DWORD LastError; // eax
  bool v6; // bl
  WINBOOL IsMember; // [rsp+20h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+30h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-21h] BYREF
  HANDLE *p_hObject; // [rsp+40h] [rbp-19h]
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  hObject = 0;
  IsMember = 0;
  p_hObject = &hObject;
  cbSid = 68;
  DuplicateTokenHandle = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(&hObject, 0);
  v2 = DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle);
  if ( DuplicateTokenHandle )
    tlx::unique_any<tlx::file_handle_traits>::reset(p_hObject, DuplicateTokenHandle);
  if ( v2 )
  {
    if ( CreateWellKnownSid(WinWriteRestrictedCodeSid, 0, pSid, &cbSid) )
    {
      if ( CheckTokenMembership(hObject, pSid, &IsMember) )
      {
        v6 = IsMember != 0;
        goto LABEL_20;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
    }
    v6 = 0;
LABEL_20:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hObject);
    return v6;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v3 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v3);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800062d0  mov     [rsp-8+arg_8], rbx
0x1800062d5  push    rbp
0x1800062d6  lea     rbp, [rsp-57h]
0x1800062db  sub     rsp, 0B0h
0x1800062e2  mov     rax, cs:__security_cookie
0x1800062e9  xor     rax, rsp
0x1800062ec  mov     [rbp+57h+var_10], rax
0x1800062f0  mov     rbx, rcx
0x1800062f3  mov     [rbp+57h+hObject], 0
0x1800062fb  lea     rax, [rbp+57h+hObject]
0x1800062ff  mov     [rbp+57h+IsMember], 0
0x180006306  lea     rcx, [rbp+57h+hObject]
0x18000630a  mov     [rbp+57h+var_70], rax
0x18000630e  xor     edx, edx
0x180006310  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180006317  mov     [rbp+57h+DuplicateTokenHandle], 0
0x18000631f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180006324  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180006328  mov     edx, 2; ImpersonationLevel
0x18000632d  mov     rcx, rbx; ExistingTokenHandle
0x180006330  call    cs:__imp_DuplicateToken
0x180006336  mov     rdx, [rbp+57h+DuplicateTokenHandle]
0x18000633a  mov     ebx, eax
0x18000633c  test    rdx, rdx
0x18000633f  jz      short loc_18000634A
0x180006341  mov     rcx, [rbp+57h+var_70]
0x180006345  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000634a  test    ebx, ebx
0x18000634c  jnz     short loc_1800063A5
0x18000634e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006355  lea     rax, WPP_GLOBAL_Control
0x18000635c  cmp     rcx, rax
0x18000635f  jz      short loc_18000638A
0x180006361  test    byte ptr [rcx+1Ch], 1
0x180006365  jz      short loc_18000638A
0x180006367  call    cs:__imp_GetLastError
0x18000636d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006374  lea     edx, [rbx+2Bh]
0x180006377  mov     r9d, eax
0x18000637a  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180006381  mov     rcx, [rcx+10h]
0x180006385  call    WPP_SF_d
0x18000638a  mov     rcx, [rbp+57h+hObject]; hObject
0x18000638e  lea     rax, [rcx+1]
0x180006392  cmp     rax, 1
0x180006396  jbe     short loc_18000639E
0x180006398  call    cs:__imp_CloseHandle
0x18000639e  xor     al, al
0x1800063a0  jmp     loc_180006456
0x1800063a5  xor     edx, edx; DomainSid
0x1800063a7  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800063ab  lea     r8, [rbp+57h+pSid]; pSid
0x1800063af  lea     ecx, [rdx+46h]; WellKnownSidType
0x1800063b2  call    cs:__imp_CreateWellKnownSid
0x1800063b8  test    eax, eax
0x1800063ba  jnz     short loc_1800063FC
0x1800063bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063c3  lea     rax, WPP_GLOBAL_Control
0x1800063ca  cmp     rcx, rax
0x1800063cd  jz      short loc_180006440
0x1800063cf  test    byte ptr [rcx+1Ch], 1
0x1800063d3  jz      short loc_180006440
0x1800063d5  call    cs:__imp_GetLastError
0x1800063db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063e2  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800063e9  mov     edx, 2Ch ; ','
0x1800063ee  mov     r9d, eax
0x1800063f1  mov     rcx, [rcx+10h]
0x1800063f5  call    WPP_SF_d
0x1800063fa  jmp     short loc_180006440
0x1800063fc  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x180006400  lea     r8, [rbp+57h+IsMember]; IsMember
0x180006404  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180006408  call    cs:__imp_CheckTokenMembership
0x18000640e  test    eax, eax
0x180006410  jnz     short loc_180006444
0x180006412  mov     rcx, cs:WPP_GLOBAL_Control
0x180006419  lea     rax, WPP_GLOBAL_Control
0x180006420  cmp     rcx, rax
0x180006423  jz      short loc_180006440
0x180006425  test    byte ptr [rcx+1Ch], 1
0x180006429  jz      short loc_180006440
0x18000642b  mov     rcx, [rcx+10h]
0x18000642f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180006436  mov     edx, 2Dh ; '-'
0x18000643b  call    WPP_SF_
0x180006440  xor     bl, bl
0x180006442  jmp     short loc_18000644B
0x180006444  cmp     [rbp+57h+IsMember], 0
0x180006448  setnz   bl
0x18000644b  lea     rcx, [rbp+57h+hObject]
0x18000644f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180006454  mov     al, bl
0x180006456  mov     rcx, [rbp+57h+var_10]
0x18000645a  xor     rcx, rsp; StackCookie
0x18000645d  call    __security_check_cookie
0x180006462  mov     rbx, [rsp+0B0h+arg_8]
0x18000646a  add     rsp, 0B0h
0x180006471  pop     rbp
0x180006472  retn
```
