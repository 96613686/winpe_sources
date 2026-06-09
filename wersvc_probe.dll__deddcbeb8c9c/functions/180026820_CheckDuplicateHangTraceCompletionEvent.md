# CheckDuplicateHangTraceCompletionEvent

- ea: `0x180026820`
- end: `0x180026a87`
- name: `CheckDuplicateHangTraceCompletionEvent`
- size: `615`
- prototype: `__int64 __fastcall(HANDLE hTargetProcessHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180027460`

## callees

- `0x1800029d0`
- `0x180006a80`
- `0x180011ef8`
- `0x180026820`
- `0x180027364`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800269dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800269dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026a2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026908`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026908`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002687c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180026945`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002687c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180026945`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002685e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002685e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026a5e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026a0a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026a0a`

## string_xrefs

- `0x18002693a`: `Global\HealthAndExperienceHangTraceCompletion`

## pseudocode

```c
int __fastcall CheckDuplicateHangTraceCompletionEvent(HANDLE hTargetProcessHandle, __int64 a2)
{
  HANDLE *v4; // rax
  HANDLE v5; // rax
  void *v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD cbSid[4]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-78h] BYREF

  cbSid[0] = 68;
  LODWORD(v4) = CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid);
  if ( !(_DWORD)v4 )
    return (int)v4;
  v5 = OpenEventW(0x120000u, 0, L"Global\\HealthAndExperienceHangTraceAvailable");
  v6 = v5;
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    if ( (unsigned int)IsOwnedBySid(v5, pSid) )
    {
      if ( WaitForSingleObject(v6, 0) )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_28;
        v8 = 50;
      }
      else
      {
        v9 = OpenEventW(0x120000u, 0, L"Global\\HealthAndExperienceHangTraceCompletion");
        v10 = v9;
        if ( (unsigned __int64)v9 + 1 > 1 )
        {
          if ( (unsigned int)IsOwnedBySid(v9, pSid) )
          {
            CurrentProcess = GetCurrentProcess();
            if ( !DuplicateHandle(CurrentProcess, v10, hTargetProcessHandle, (LPHANDLE)(a2 + 1768), 0x100000u, 0, 0)
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
                LastError);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids);
          }
          CloseHandle(v10);
          goto LABEL_28;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_28:
          LODWORD(v4) = CloseHandle(v6);
          return (int)v4;
        }
        v8 = 51;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_28;
      v8 = 49;
    }
    WPP_SF_(v7[2], v8, &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids);
    goto LABEL_28;
  }
  v4 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    LODWORD(v4) = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids);
  return (int)v4;
}

```

## disassembly

```asm
0x180026820  mov     [rsp+arg_10], rbx
0x180026825  push    rbp
0x180026826  push    rsi
0x180026827  push    rdi
0x180026828  sub     rsp, 0B0h
0x18002682f  mov     rax, cs:__security_cookie
0x180026836  xor     rax, rsp
0x180026839  mov     [rsp+0C8h+var_28], rax
0x180026841  mov     rbp, rdx
0x180026844  mov     [rsp+0C8h+cbSid], 44h ; 'D'
0x18002684c  xor     edx, edx; DomainSid
0x18002684e  lea     r9, [rsp+0C8h+cbSid]; cbSid
0x180026853  mov     rsi, rcx
0x180026856  lea     r8, [rsp+0C8h+pSid]; pSid
0x18002685b  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002685e  call    cs:__imp_CreateWellKnownSid
0x180026864  test    eax, eax
0x180026866  jz      loc_180026A64
0x18002686c  mov     edi, 120000h
0x180026871  lea     r8, aGlobalHealthan; "Global\\HealthAndExperienceHangTraceAva"...
0x180026878  mov     ecx, edi; dwDesiredAccess
0x18002687a  xor     edx, edx; bInheritHandle
0x18002687c  call    cs:__imp_OpenEventW
0x180026882  mov     rbx, rax
0x180026885  lea     rcx, [rax+1]
0x180026889  cmp     rcx, 1
0x18002688d  ja      short loc_1800268CA
0x18002688f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026896  lea     rax, WPP_GLOBAL_Control
0x18002689d  cmp     rcx, rax
0x1800268a0  jz      loc_180026A64
0x1800268a6  test    byte ptr [rcx+1Ch], 4
0x1800268aa  jz      loc_180026A64
0x1800268b0  mov     rcx, [rcx+10h]
0x1800268b4  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x1800268bb  mov     edx, 30h ; '0'
0x1800268c0  call    WPP_SF_
0x1800268c5  jmp     loc_180026A64
0x1800268ca  lea     rdx, [rsp+0C8h+pSid]; pSid2
0x1800268cf  mov     rcx, rbx; Handle
0x1800268d2  call    IsOwnedBySid
0x1800268d7  test    eax, eax
0x1800268d9  jnz     short loc_180026903
0x1800268db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268e2  lea     rax, WPP_GLOBAL_Control
0x1800268e9  cmp     rcx, rax
0x1800268ec  jz      loc_180026A5B
0x1800268f2  test    byte ptr [rcx+1Ch], 2
0x1800268f6  jz      loc_180026A5B
0x1800268fc  mov     edx, 31h ; '1'
0x180026901  jmp     short loc_18002697E
0x180026903  xor     edx, edx; dwMilliseconds
0x180026905  mov     rcx, rbx; hHandle
0x180026908  call    cs:__imp_WaitForSingleObject
0x18002690e  test    eax, eax
0x180026910  jz      short loc_18002693A
0x180026912  mov     rcx, cs:WPP_GLOBAL_Control
0x180026919  lea     rax, WPP_GLOBAL_Control
0x180026920  cmp     rcx, rax
0x180026923  jz      loc_180026A5B
0x180026929  test    byte ptr [rcx+1Ch], 4
0x18002692d  jz      loc_180026A5B
0x180026933  mov     edx, 32h ; '2'
0x180026938  jmp     short loc_18002697E
0x18002693a  lea     r8, aGlobalHealthan_0; "Global\\HealthAndExperienceHangTraceCom"...
0x180026941  xor     edx, edx; bInheritHandle
0x180026943  mov     ecx, edi; dwDesiredAccess
0x180026945  call    cs:__imp_OpenEventW
0x18002694b  mov     rdi, rax
0x18002694e  lea     rcx, [rax+1]
0x180026952  cmp     rcx, 1
0x180026956  ja      short loc_180026993
0x180026958  mov     rcx, cs:WPP_GLOBAL_Control
0x18002695f  lea     rax, WPP_GLOBAL_Control
0x180026966  cmp     rcx, rax
0x180026969  jz      loc_180026A5B
0x18002696f  test    byte ptr [rcx+1Ch], 2
0x180026973  jz      loc_180026A5B
0x180026979  mov     edx, 33h ; '3'
0x18002697e  mov     rcx, [rcx+10h]
0x180026982  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x180026989  call    WPP_SF_
0x18002698e  jmp     loc_180026A5B
0x180026993  lea     rdx, [rsp+0C8h+pSid]; pSid2
0x180026998  mov     rcx, rdi; Handle
0x18002699b  call    IsOwnedBySid
0x1800269a0  test    eax, eax
0x1800269a2  jnz     short loc_1800269DC
0x1800269a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ab  lea     rax, WPP_GLOBAL_Control
0x1800269b2  cmp     rcx, rax
0x1800269b5  jz      loc_180026A52
0x1800269bb  test    byte ptr [rcx+1Ch], 2
0x1800269bf  jz      loc_180026A52
0x1800269c5  mov     rcx, [rcx+10h]
0x1800269c9  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x1800269d0  mov     edx, 34h ; '4'
0x1800269d5  call    WPP_SF_
0x1800269da  jmp     short loc_180026A52
0x1800269dc  call    cs:__imp_GetCurrentProcess
0x1800269e2  mov     [rsp+0C8h+dwOptions], 0; dwOptions
0x1800269ea  lea     r9, [rbp+6E8h]; lpTargetHandle
0x1800269f1  mov     rcx, rax; hSourceProcessHandle
0x1800269f4  mov     [rsp+0C8h+bInheritHandle], 0; bInheritHandle
0x1800269fc  mov     r8, rsi; hTargetProcessHandle
0x1800269ff  mov     [rsp+0C8h+dwDesiredAccess], 100000h; dwDesiredAccess
0x180026a07  mov     rdx, rdi; hSourceHandle
0x180026a0a  call    cs:__imp_DuplicateHandle
0x180026a10  test    eax, eax
0x180026a12  jnz     short loc_180026A52
0x180026a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a1b  lea     rax, WPP_GLOBAL_Control
0x180026a22  cmp     rcx, rax
0x180026a25  jz      short loc_180026A52
0x180026a27  test    byte ptr [rcx+1Ch], 1
0x180026a2b  jz      short loc_180026A52
0x180026a2d  call    cs:__imp_GetLastError
0x180026a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a3a  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x180026a41  mov     edx, 35h ; '5'
0x180026a46  mov     r9d, eax
0x180026a49  mov     rcx, [rcx+10h]
0x180026a4d  call    WPP_SF_d
0x180026a52  mov     rcx, rdi; hObject
0x180026a55  call    cs:__imp_CloseHandle
0x180026a5b  mov     rcx, rbx; hObject
0x180026a5e  call    cs:__imp_CloseHandle
0x180026a64  mov     rcx, [rsp+0C8h+var_28]
0x180026a6c  xor     rcx, rsp; StackCookie
0x180026a6f  call    __security_check_cookie
0x180026a74  mov     rbx, [rsp+0C8h+arg_10]
0x180026a7c  add     rsp, 0B0h
0x180026a83  pop     rdi
0x180026a84  pop     rsi
0x180026a85  pop     rbp
0x180026a86  retn
```
