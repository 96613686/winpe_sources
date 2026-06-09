# UtilStopWerSvc(ulong)

- ea: `0x1400186bc`
- end: `0x1400189bb`
- name: `?UtilStopWerSvc@@YAJK@Z`
- size: `767`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000cfa8`

## callees

- `0x140003200`
- `0x14000e340`
- `0x1400186bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400186de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140018915`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400186de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140018915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400187fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400187fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018953`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400188e7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400188e7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400186f4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400186f4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140018765`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140018765`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001898a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018998`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001898a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018998`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400187f1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140018905`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1400187f1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140018905`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14001884f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14001884f`

## pseudocode

```c
__int64 __fastcall UtilStopWerSvc(unsigned int a1)
{
  ULONGLONG v1; // rbx
  ULONGLONG TickCount64; // r15
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  signed int LastError; // eax
  unsigned int v6; // ebx
  SC_HANDLE v7; // rsi
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  DWORD v13; // ecx
  signed int v14; // eax
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-38h] BYREF
  DWORD dwMilliseconds[4]; // [rsp+48h] [rbp-28h]
  int v19; // [rsp+58h] [rbp-18h]

  v1 = a1;
  TickCount64 = GetTickCount64();
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    return v6;
  }
  v7 = OpenServiceW(v3, L"WerSvc", 0x24u);
  if ( !v7 )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v10 = 155;
    goto LABEL_13;
  }
  v19 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  *(_OWORD *)dwMilliseconds = 0;
  if ( !QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_47;
    v10 = 156;
    goto LABEL_13;
  }
  if ( *(_DWORD *)&Buffer[4] == 4 )
  {
    if ( ControlService(v7, 1u, (LPSERVICE_STATUS)Buffer) )
    {
      if ( *(_DWORD *)&Buffer[4] == 1 )
      {
LABEL_37:
        v6 = 0;
      }
      else
      {
        while ( 1 )
        {
          v13 = dwMilliseconds[2];
          if ( dwMilliseconds[2] < 0x32 )
            v13 = 50;
          dwMilliseconds[2] = v13;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v13);
            v13 = dwMilliseconds[2];
          }
          Sleep(v13);
          if ( !QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            break;
          if ( *(_DWORD *)&Buffer[4] == 1 )
            goto LABEL_37;
          if ( GetTickCount64() - TickCount64 > v1 )
          {
            v6 = -2147023436;
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 160;
              goto LABEL_13;
            }
            goto LABEL_47;
          }
          if ( *(_DWORD *)&Buffer[4] == 1 )
            goto LABEL_37;
        }
        v14 = GetLastError();
        v6 = v14;
        if ( v14 > 0 )
          v6 = (unsigned __int16)v14 | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 159;
          goto LABEL_13;
        }
      }
      goto LABEL_47;
    }
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 157;
LABEL_13:
      WPP_SF_d(v9[2], v10, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    }
  }
  else
  {
    v6 = 1;
  }
LABEL_47:
  CloseServiceHandle(v4);
  if ( v7 )
    CloseServiceHandle(v7);
  return v6;
}

```

## disassembly

```asm
0x1400186bc  push    rbp
0x1400186be  push    rbx
0x1400186bf  push    rsi
0x1400186c0  push    rdi
0x1400186c1  push    r12
0x1400186c3  push    r14
0x1400186c5  push    r15
0x1400186c7  mov     rbp, rsp
0x1400186ca  sub     rsp, 70h
0x1400186ce  mov     rax, cs:__security_cookie
0x1400186d5  xor     rax, rsp
0x1400186d8  mov     [rbp+var_10], rax
0x1400186dc  mov     ebx, ecx
0x1400186de  call    cs:__imp_GetTickCount64
0x1400186e4  mov     r12d, 1
0x1400186ea  xor     edx, edx; lpDatabaseName
0x1400186ec  mov     r8d, r12d; dwDesiredAccess
0x1400186ef  xor     ecx, ecx; lpMachineName
0x1400186f1  mov     r15, rax
0x1400186f4  call    cs:__imp_OpenSCManagerW
0x1400186fa  mov     r14, rax
0x1400186fd  test    rax, rax
0x140018700  jnz     short loc_140018755
0x140018702  call    cs:__imp_GetLastError
0x140018708  mov     ebx, eax
0x14001870a  test    eax, eax
0x14001870c  jle     short loc_140018717
0x14001870e  movzx   ebx, ax
0x140018711  or      ebx, 80070000h
0x140018717  mov     rcx, cs:WPP_GLOBAL_Control
0x14001871e  lea     rdi, WPP_GLOBAL_Control
0x140018725  cmp     rcx, rdi
0x140018728  jz      loc_14001899E
0x14001872e  test    [rcx+1Ch], r12b
0x140018732  jz      loc_14001899E
0x140018738  mov     rcx, [rcx+10h]
0x14001873c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140018743  mov     edx, 9Ah
0x140018748  mov     r9d, ebx
0x14001874b  call    WPP_SF_d
0x140018750  jmp     loc_14001899E
0x140018755  mov     r8d, 24h ; '$'; dwDesiredAccess
0x14001875b  lea     rdx, AliasPrefix; "WerSvc"
0x140018762  mov     rcx, r14; hSCManager
0x140018765  call    cs:__imp_OpenServiceW
0x14001876b  mov     rsi, rax
0x14001876e  test    rax, rax
0x140018771  jnz     short loc_1400187C6
0x140018773  call    cs:__imp_GetLastError
0x140018779  mov     ebx, eax
0x14001877b  test    eax, eax
0x14001877d  jle     short loc_140018788
0x14001877f  movzx   ebx, ax
0x140018782  or      ebx, 80070000h
0x140018788  mov     rcx, cs:WPP_GLOBAL_Control
0x14001878f  lea     rdi, WPP_GLOBAL_Control
0x140018796  cmp     rcx, rdi
0x140018799  jz      loc_140018987
0x14001879f  test    [rcx+1Ch], r12b
0x1400187a3  jz      loc_140018987
0x1400187a9  mov     edx, 9Bh
0x1400187ae  mov     rcx, [rcx+10h]
0x1400187b2  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400187b9  mov     r9d, ebx
0x1400187bc  call    WPP_SF_d
0x1400187c1  jmp     loc_140018987
0x1400187c6  xor     eax, eax
0x1400187c8  lea     r8, [rbp+Buffer]; lpBuffer
0x1400187cc  xorps   xmm0, xmm0
0x1400187cf  mov     [rbp+var_18], eax
0x1400187d2  mov     [rbp+var_40], eax
0x1400187d5  mov     r9d, 24h ; '$'; cbBufSize
0x1400187db  lea     rax, [rbp+var_40]
0x1400187df  xor     edx, edx; InfoLevel
0x1400187e1  mov     rcx, rsi; hService
0x1400187e4  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1400187e9  movups  xmmword ptr [rbp+Buffer], xmm0
0x1400187ed  movups  xmmword ptr [rbp+dwMilliseconds], xmm0
0x1400187f1  call    cs:__imp_QueryServiceStatusEx
0x1400187f7  test    eax, eax
0x1400187f9  jnz     short loc_14001883B
0x1400187fb  call    cs:__imp_GetLastError
0x140018801  mov     ebx, eax
0x140018803  test    eax, eax
0x140018805  jle     short loc_140018810
0x140018807  movzx   ebx, ax
0x14001880a  or      ebx, 80070000h
0x140018810  mov     rcx, cs:WPP_GLOBAL_Control
0x140018817  lea     rdi, WPP_GLOBAL_Control
0x14001881e  cmp     rcx, rdi
0x140018821  jz      loc_140018987
0x140018827  test    [rcx+1Ch], r12b
0x14001882b  jz      loc_140018987
0x140018831  mov     edx, 9Ch
0x140018836  jmp     loc_1400187AE
0x14001883b  cmp     dword ptr [rbp+Buffer+4], 4
0x14001883f  jnz     loc_140018984
0x140018845  lea     r8, [rbp+Buffer]; lpServiceStatus
0x140018849  mov     edx, r12d; dwControl
0x14001884c  mov     rcx, rsi; hService
0x14001884f  call    cs:__imp_ControlService
0x140018855  test    eax, eax
0x140018857  jnz     short loc_140018899
0x140018859  call    cs:__imp_GetLastError
0x14001885f  mov     ebx, eax
0x140018861  test    eax, eax
0x140018863  jle     short loc_14001886E
0x140018865  movzx   ebx, ax
0x140018868  or      ebx, 80070000h
0x14001886e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018875  lea     rdi, WPP_GLOBAL_Control
0x14001887c  cmp     rcx, rdi
0x14001887f  jz      loc_140018987
0x140018885  test    [rcx+1Ch], r12b
0x140018889  jz      loc_140018987
0x14001888f  mov     edx, 9Dh
0x140018894  jmp     loc_1400187AE
0x140018899  cmp     dword ptr [rbp+Buffer+4], r12d
0x14001889d  jz      loc_14001892E
0x1400188a3  lea     rdi, WPP_GLOBAL_Control
0x1400188aa  mov     eax, 32h ; '2'
0x1400188af  mov     ecx, [rbp+dwMilliseconds+8]
0x1400188b2  cmp     ecx, eax
0x1400188b4  cmovb   ecx, eax
0x1400188b7  mov     [rbp+dwMilliseconds+8], ecx
0x1400188ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400188c1  cmp     rax, rdi
0x1400188c4  jz      short loc_1400188E7
0x1400188c6  test    byte ptr [rax+1Ch], 8
0x1400188ca  jz      short loc_1400188E7
0x1400188cc  mov     r9d, ecx
0x1400188cf  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400188d6  mov     rcx, [rax+10h]
0x1400188da  mov     edx, 9Eh
0x1400188df  call    WPP_SF_d
0x1400188e4  mov     ecx, [rbp+dwMilliseconds+8]; dwMilliseconds
0x1400188e7  call    cs:__imp_Sleep
0x1400188ed  lea     rax, [rbp+var_40]
0x1400188f1  mov     r9d, 24h ; '$'; cbBufSize
0x1400188f7  lea     r8, [rbp+Buffer]; lpBuffer
0x1400188fb  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140018900  xor     edx, edx; InfoLevel
0x140018902  mov     rcx, rsi; hService
0x140018905  call    cs:__imp_QueryServiceStatusEx
0x14001890b  test    eax, eax
0x14001890d  jz      short loc_140018953
0x14001890f  cmp     dword ptr [rbp+Buffer+4], r12d
0x140018913  jz      short loc_14001892E
0x140018915  call    cs:__imp_GetTickCount64
0x14001891b  sub     rax, r15
0x14001891e  cmp     rax, rbx
0x140018921  ja      short loc_140018932
0x140018923  mov     eax, 32h ; '2'
0x140018928  cmp     dword ptr [rbp+Buffer+4], r12d
0x14001892c  jnz     short loc_1400188AF
0x14001892e  xor     ebx, ebx
0x140018930  jmp     short loc_140018987
0x140018932  mov     ebx, 800705B4h
0x140018937  mov     rcx, cs:WPP_GLOBAL_Control
0x14001893e  cmp     rcx, rdi
0x140018941  jz      short loc_140018987
0x140018943  test    [rcx+1Ch], r12b
0x140018947  jz      short loc_140018987
0x140018949  mov     edx, 0A0h
0x14001894e  jmp     loc_1400187AE
0x140018953  call    cs:__imp_GetLastError
0x140018959  mov     ebx, eax
0x14001895b  test    eax, eax
0x14001895d  jle     short loc_140018968
0x14001895f  movzx   ebx, ax
0x140018962  or      ebx, 80070000h
0x140018968  mov     rcx, cs:WPP_GLOBAL_Control
0x14001896f  cmp     rcx, rdi
0x140018972  jz      short loc_140018987
0x140018974  test    [rcx+1Ch], r12b
0x140018978  jz      short loc_140018987
0x14001897a  mov     edx, 9Fh
0x14001897f  jmp     loc_1400187AE
0x140018984  mov     ebx, r12d
0x140018987  mov     rcx, r14; hSCObject
0x14001898a  call    cs:__imp_CloseServiceHandle
0x140018990  test    rsi, rsi
0x140018993  jz      short loc_14001899E
0x140018995  mov     rcx, rsi; hSCObject
0x140018998  call    cs:__imp_CloseServiceHandle
0x14001899e  mov     eax, ebx
0x1400189a0  mov     rcx, [rbp+var_10]
0x1400189a4  xor     rcx, rsp; StackCookie
0x1400189a7  call    __security_check_cookie
0x1400189ac  add     rsp, 70h
0x1400189b0  pop     r15
0x1400189b2  pop     r14
0x1400189b4  pop     r12
0x1400189b6  pop     rdi
0x1400189b7  pop     rsi
0x1400189b8  pop     rbx
0x1400189b9  pop     rbp
0x1400189ba  retn
```
