# WFDPmIntStartDAS(_WFD_PROFILE_MANAGER *)

- ea: `0x1800d8688`
- end: `0x1800d8ab6`
- name: `?WFDPmIntStartDAS@@YAKPEAU_WFD_PROFILE_MANAGER@@@Z`
- size: `1070`
- prototype: `unsigned int __fastcall(struct _WFD_PROFILE_MANAGER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180096b98`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800d8688`
- `0x180106340`
- `0x180148674`
- `0x180148b6c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d8917`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800d8917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d86db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d87ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d88a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d89c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d86db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d87ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d88a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d89c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d88da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d8954`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d897f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d88da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d8954`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800d897f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800d8a86`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800d8a8f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800d8a86`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800d8a8f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800d86cd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800d86cd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800d873a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800d873a`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800d879f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800d879f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800d8898`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800d8935`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800d8898`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800d8935`

## string_xrefs

- `0x1800d8730`: `DeviceAssociationService`

## pseudocode

```c
__int64 __fastcall WFDPmIntStartDAS(struct _WFD_PROFILE_MANAGER *a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // r13
  DWORD v3; // eax
  DWORD v4; // edi
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  DWORD v7; // eax
  DWORD v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD TickCount; // eax
  unsigned int v12; // r15d
  DWORD v13; // r12d
  DWORD v14; // edx
  DWORD v15; // eax
  DWORD LastError; // eax
  PVOID *v17; // rcx
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v21; // [rsp+58h] [rbp-28h]
  int v22; // [rsp+68h] [rbp-18h]

  pcbBytesNeeded = 0;
  v22 = 0;
  *(_OWORD *)Buffer = 0;
  v21 = 0;
  v1 = OpenSCManagerW(0, 0, 0xF003Fu);
  v2 = v1;
  if ( v1 )
  {
    v5 = OpenServiceW(v1, L"DeviceAssociationService", 0xF01FFu);
    v6 = v5;
    if ( v5 )
    {
      if ( StartServiceW(v5, 0, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_31e54d649409365576704d3c1f2892b5_Traceguids);
        }
        if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        {
          v4 = 0;
LABEL_33:
          TickCount = GetTickCount();
          v12 = DWORD1(v21);
          v13 = TickCount;
          while ( *(_DWORD *)&Buffer[4] == 2 )
          {
            v14 = DWORD2(v21) / 0xA;
            if ( DWORD2(v21) / 0xA >= 0x3E8 )
            {
              if ( v14 > 0x2710 )
                v14 = 10000;
            }
            else
            {
              v14 = 1000;
            }
            Sleep(v14);
            if ( !QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
            {
              LastError = GetLastError();
              v4 = LastError;
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  33,
                  WPP_31e54d649409365576704d3c1f2892b5_Traceguids,
                  LastError);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v4 )
              {
LABEL_65:
                CloseServiceHandle(v6);
                goto LABEL_66;
              }
LABEL_55:
              if ( *(_DWORD *)&Buffer[4] == 4 )
              {
                if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 105) >= 3u && (*((_BYTE *)v17 + 108) & 1) != 0 )
                  WPP_SF_(v17[12], 35, WPP_31e54d649409365576704d3c1f2892b5_Traceguids);
              }
              else
              {
                if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 105) && (*((_BYTE *)v17 + 108) & 1) != 0 )
                  WPP_SF_dddd(
                    v17[12],
                    36,
                    WPP_31e54d649409365576704d3c1f2892b5_Traceguids,
                    *(unsigned int *)&Buffer[4],
                    *(_DWORD *)&Buffer[12],
                    DWORD1(v21),
                    DWORD2(v21));
                v4 = 1062;
              }
              goto LABEL_65;
            }
            if ( DWORD1(v21) > v12 )
              goto LABEL_33;
            if ( *(_DWORD *)&Buffer[4] != 4 && GetTickCount() - v13 > DWORD2(v21) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 105)
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                v15 = GetTickCount();
                WPP_SF_ddDDD(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  34,
                  WPP_31e54d649409365576704d3c1f2892b5_Traceguids,
                  v12,
                  DWORD1(v21),
                  v13,
                  v15,
                  DWORD2(v21));
              }
              v4 = 1053;
              goto LABEL_65;
            }
          }
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_55;
        }
        v8 = GetLastError();
        v4 = v8;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_65;
        }
        v10 = 32;
      }
      else
      {
        v4 = GetLastError();
        if ( v4 == 1056 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_31e54d649409365576704d3c1f2892b5_Traceguids);
          }
          v4 = 0;
          goto LABEL_65;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_65;
        }
        v8 = GetLastError();
        v9 = WPP_GLOBAL_Control;
        v10 = 30;
      }
      WPP_SF_d(v9[12], v10, WPP_31e54d649409365576704d3c1f2892b5_Traceguids, v8);
      goto LABEL_65;
    }
    v7 = GetLastError();
    v4 = v7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_31e54d649409365576704d3c1f2892b5_Traceguids, v7);
    }
LABEL_66:
    CloseServiceHandle(v2);
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_31e54d649409365576704d3c1f2892b5_Traceguids, v3);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800d8688  push    rbp
0x1800d868a  push    rsi
0x1800d868b  push    rdi
0x1800d868c  push    r12
0x1800d868e  push    r13
0x1800d8690  push    r14
0x1800d8692  push    r15
0x1800d8694  mov     rbp, rsp
0x1800d8697  sub     rsp, 80h
0x1800d869e  mov     rax, cs:__security_cookie
0x1800d86a5  xor     rax, rsp
0x1800d86a8  mov     [rbp+var_10], rax
0x1800d86ac  xorps   xmm0, xmm0
0x1800d86af  mov     [rbp+var_40], 0
0x1800d86b6  xor     eax, eax
0x1800d86b8  xor     edx, edx; lpDatabaseName
0x1800d86ba  xor     ecx, ecx; lpMachineName
0x1800d86bc  mov     [rbp+var_18], eax
0x1800d86bf  mov     r8d, 0F003Fh; dwDesiredAccess
0x1800d86c5  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800d86c9  movups  [rbp+var_28], xmm0
0x1800d86cd  call    cs:__imp_OpenSCManagerW
0x1800d86d3  mov     r13, rax
0x1800d86d6  test    rax, rax
0x1800d86d9  jnz     short loc_1800D872A
0x1800d86db  call    cs:__imp_GetLastError
0x1800d86e1  mov     edi, eax
0x1800d86e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d86ea  lea     rsi, WPP_GLOBAL_Control
0x1800d86f1  cmp     rcx, rsi
0x1800d86f4  jz      loc_1800D8A95
0x1800d86fa  cmp     byte ptr [rcx+69h], 1
0x1800d86fe  jb      loc_1800D8A95
0x1800d8704  test    byte ptr [rcx+6Ch], 1
0x1800d8708  jz      loc_1800D8A95
0x1800d870e  mov     rcx, [rcx+60h]
0x1800d8712  lea     edx, [r13+1Bh]
0x1800d8716  mov     r9d, eax
0x1800d8719  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d8720  call    WPP_SF_d
0x1800d8725  jmp     loc_1800D8A95
0x1800d872a  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800d8730  lea     rdx, aDeviceassociat_0; "DeviceAssociationService"
0x1800d8737  mov     rcx, r13; hSCManager
0x1800d873a  call    cs:__imp_OpenServiceW
0x1800d8740  mov     r14, rax
0x1800d8743  test    rax, rax
0x1800d8746  jnz     short loc_1800D8797
0x1800d8748  call    cs:__imp_GetLastError
0x1800d874e  mov     edi, eax
0x1800d8750  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8757  lea     rsi, WPP_GLOBAL_Control
0x1800d875e  cmp     rcx, rsi
0x1800d8761  jz      loc_1800D8A8C
0x1800d8767  cmp     byte ptr [rcx+69h], 1
0x1800d876b  jb      loc_1800D8A8C
0x1800d8771  test    byte ptr [rcx+6Ch], 1
0x1800d8775  jz      loc_1800D8A8C
0x1800d877b  mov     rcx, [rcx+60h]
0x1800d877f  lea     edx, [r14+1Ch]
0x1800d8783  mov     r9d, eax
0x1800d8786  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d878d  call    WPP_SF_d
0x1800d8792  jmp     loc_1800D8A8C
0x1800d8797  xor     r8d, r8d; lpServiceArgVectors
0x1800d879a  xor     edx, edx; dwNumServiceArgs
0x1800d879c  mov     rcx, r14; hService
0x1800d879f  call    cs:__imp_StartServiceW
0x1800d87a5  test    eax, eax
0x1800d87a7  jnz     loc_1800D884C
0x1800d87ad  call    cs:__imp_GetLastError
0x1800d87b3  mov     edi, eax
0x1800d87b5  cmp     eax, 420h
0x1800d87ba  jnz     short loc_1800D87F7
0x1800d87bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d87c3  lea     rsi, WPP_GLOBAL_Control
0x1800d87ca  cmp     rcx, rsi
0x1800d87cd  jz      short loc_1800D87F0
0x1800d87cf  cmp     byte ptr [rcx+69h], 3
0x1800d87d3  jb      short loc_1800D87F0
0x1800d87d5  test    byte ptr [rcx+6Ch], 1
0x1800d87d9  jz      short loc_1800D87F0
0x1800d87db  mov     rcx, [rcx+60h]
0x1800d87df  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d87e6  mov     edx, 1Dh
0x1800d87eb  call    WPP_SF_
0x1800d87f0  xor     edi, edi
0x1800d87f2  jmp     loc_1800D8A83
0x1800d87f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800d87fe  lea     rsi, WPP_GLOBAL_Control
0x1800d8805  cmp     rax, rsi
0x1800d8808  jz      loc_1800D8A83
0x1800d880e  cmp     byte ptr [rax+69h], 1
0x1800d8812  jb      loc_1800D8A83
0x1800d8818  test    byte ptr [rax+6Ch], 1
0x1800d881c  jz      loc_1800D8A83
0x1800d8822  call    cs:__imp_GetLastError
0x1800d8828  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d882f  mov     edx, 1Eh
0x1800d8834  mov     rcx, [rcx+60h]
0x1800d8838  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d883f  mov     r9d, eax
0x1800d8842  call    WPP_SF_d
0x1800d8847  jmp     loc_1800D8A83
0x1800d884c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8853  lea     rsi, WPP_GLOBAL_Control
0x1800d885a  cmp     rcx, rsi
0x1800d885d  jz      short loc_1800D8880
0x1800d885f  cmp     byte ptr [rcx+69h], 3
0x1800d8863  jb      short loc_1800D8880
0x1800d8865  test    byte ptr [rcx+6Ch], 1
0x1800d8869  jz      short loc_1800D8880
0x1800d886b  mov     rcx, [rcx+60h]
0x1800d886f  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d8876  mov     edx, 1Fh
0x1800d887b  call    WPP_SF_
0x1800d8880  lea     rax, [rbp+var_40]
0x1800d8884  mov     r9d, 24h ; '$'; cbBufSize
0x1800d888a  lea     r8, [rbp+Buffer]; lpBuffer
0x1800d888e  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800d8893  xor     edx, edx; InfoLevel
0x1800d8895  mov     rcx, r14; hService
0x1800d8898  call    cs:__imp_QueryServiceStatusEx
0x1800d889e  test    eax, eax
0x1800d88a0  jnz     short loc_1800D88D8
0x1800d88a2  call    cs:__imp_GetLastError
0x1800d88a8  mov     edi, eax
0x1800d88aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d88b1  cmp     rcx, rsi
0x1800d88b4  jz      loc_1800D8A83
0x1800d88ba  cmp     byte ptr [rcx+69h], 1
0x1800d88be  jb      loc_1800D8A83
0x1800d88c4  test    byte ptr [rcx+6Ch], 1
0x1800d88c8  jz      loc_1800D8A83
0x1800d88ce  mov     edx, 20h ; ' '
0x1800d88d3  jmp     loc_1800D8834
0x1800d88d8  xor     edi, edi
0x1800d88da  call    cs:__imp_GetTickCount
0x1800d88e0  mov     r15d, dword ptr [rbp+var_28+4]
0x1800d88e4  mov     ecx, 2710h
0x1800d88e9  mov     r12d, eax
0x1800d88ec  cmp     dword ptr [rbp+Buffer+4], 2
0x1800d88f0  jnz     loc_1800D8A0A
0x1800d88f6  mov     eax, 0CCCCCCCDh
0x1800d88fb  mul     dword ptr [rbp+var_28+8]
0x1800d88fe  shr     edx, 3
0x1800d8901  cmp     edx, 3E8h
0x1800d8907  jnb     short loc_1800D8910
0x1800d8909  mov     edx, 3E8h
0x1800d890e  jmp     short loc_1800D8915
0x1800d8910  cmp     edx, ecx
0x1800d8912  cmova   edx, ecx
0x1800d8915  mov     ecx, edx; dwMilliseconds
0x1800d8917  call    cs:__imp_Sleep
0x1800d891d  lea     rax, [rbp+var_40]
0x1800d8921  mov     r9d, 24h ; '$'; cbBufSize
0x1800d8927  lea     r8, [rbp+Buffer]; lpBuffer
0x1800d892b  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800d8930  xor     edx, edx; InfoLevel
0x1800d8932  mov     rcx, r14; hService
0x1800d8935  call    cs:__imp_QueryServiceStatusEx
0x1800d893b  test    eax, eax
0x1800d893d  jz      loc_1800D89C5
0x1800d8943  cmp     dword ptr [rbp+var_28+4], r15d
0x1800d8947  ja      short loc_1800D88DA
0x1800d8949  cmp     dword ptr [rbp+Buffer+4], 4
0x1800d894d  mov     ecx, 2710h
0x1800d8952  jz      short loc_1800D88EC
0x1800d8954  call    cs:__imp_GetTickCount
0x1800d895a  sub     eax, r12d
0x1800d895d  mov     ecx, 2710h
0x1800d8962  cmp     eax, dword ptr [rbp+var_28+8]
0x1800d8965  jbe     short loc_1800D88EC
0x1800d8967  mov     rax, cs:WPP_GLOBAL_Control
0x1800d896e  cmp     rax, rsi
0x1800d8971  jz      short loc_1800D89BB
0x1800d8973  cmp     byte ptr [rax+69h], 1
0x1800d8977  jb      short loc_1800D89BB
0x1800d8979  test    byte ptr [rax+6Ch], 1
0x1800d897d  jz      short loc_1800D89BB
0x1800d897f  call    cs:__imp_GetTickCount
0x1800d8985  mov     ecx, dword ptr [rbp+var_28+8]
0x1800d8988  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d898f  mov     [rsp+80h+var_48], ecx
0x1800d8993  mov     edx, 22h ; '"'
0x1800d8998  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d899f  mov     r9d, r15d
0x1800d89a2  mov     [rsp+80h+var_50], eax
0x1800d89a6  mov     eax, dword ptr [rbp+var_28+4]
0x1800d89a9  mov     [rsp+80h+var_58], r12d
0x1800d89ae  mov     rcx, [rcx+60h]
0x1800d89b2  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x1800d89b6  call    WPP_SF_ddDDD
0x1800d89bb  mov     edi, 41Dh
0x1800d89c0  jmp     loc_1800D8A83
0x1800d89c5  call    cs:__imp_GetLastError
0x1800d89cb  mov     edi, eax
0x1800d89cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d89d4  cmp     rcx, rsi
0x1800d89d7  jz      short loc_1800D8A04
0x1800d89d9  cmp     byte ptr [rcx+69h], 1
0x1800d89dd  jb      short loc_1800D8A04
0x1800d89df  test    byte ptr [rcx+6Ch], 1
0x1800d89e3  jz      short loc_1800D8A04
0x1800d89e5  mov     rcx, [rcx+60h]
0x1800d89e9  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d89f0  mov     edx, 21h ; '!'
0x1800d89f5  mov     r9d, eax
0x1800d89f8  call    WPP_SF_d
0x1800d89fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8a04  test    edi, edi
0x1800d8a06  jz      short loc_1800D8A11
0x1800d8a08  jmp     short loc_1800D8A83
0x1800d8a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8a11  cmp     dword ptr [rbp+Buffer+4], 4
0x1800d8a15  jnz     short loc_1800D8A3F
0x1800d8a17  cmp     rcx, rsi
0x1800d8a1a  jz      short loc_1800D8A83
0x1800d8a1c  cmp     byte ptr [rcx+69h], 3
0x1800d8a20  jb      short loc_1800D8A83
0x1800d8a22  test    byte ptr [rcx+6Ch], 1
0x1800d8a26  jz      short loc_1800D8A83
0x1800d8a28  mov     rcx, [rcx+60h]
0x1800d8a2c  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d8a33  mov     edx, 23h ; '#'
0x1800d8a38  call    WPP_SF_
0x1800d8a3d  jmp     short loc_1800D8A83
0x1800d8a3f  cmp     rcx, rsi
0x1800d8a42  jz      short loc_1800D8A7E
0x1800d8a44  cmp     byte ptr [rcx+69h], 1
0x1800d8a48  jb      short loc_1800D8A7E
0x1800d8a4a  test    byte ptr [rcx+6Ch], 1
0x1800d8a4e  jz      short loc_1800D8A7E
0x1800d8a50  mov     eax, dword ptr [rbp+var_28+8]
0x1800d8a53  lea     r8, WPP_31e54d649409365576704d3c1f2892b5_Traceguids
0x1800d8a5a  mov     r9d, dword ptr [rbp+Buffer+4]
0x1800d8a5e  mov     edx, 24h ; '$'
0x1800d8a63  mov     rcx, [rcx+60h]
0x1800d8a67  mov     [rsp+80h+var_50], eax
0x1800d8a6b  mov     eax, dword ptr [rbp+var_28+4]
0x1800d8a6e  mov     [rsp+80h+var_58], eax
0x1800d8a72  mov     eax, dword ptr [rbp+Buffer+0Ch]
0x1800d8a75  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x1800d8a79  call    WPP_SF_dddd
0x1800d8a7e  mov     edi, 426h
0x1800d8a83  mov     rcx, r14; hSCObject
0x1800d8a86  call    cs:__imp_CloseServiceHandle
0x1800d8a8c  mov     rcx, r13; hSCObject
0x1800d8a8f  call    cs:__imp_CloseServiceHandle
0x1800d8a95  mov     eax, edi
0x1800d8a97  mov     rcx, [rbp+var_10]
0x1800d8a9b  xor     rcx, rsp; StackCookie
0x1800d8a9e  call    __security_check_cookie
0x1800d8aa3  add     rsp, 80h
0x1800d8aaa  pop     r15
0x1800d8aac  pop     r14
0x1800d8aae  pop     r13
0x1800d8ab0  pop     r12
0x1800d8ab2  pop     rdi
0x1800d8ab3  pop     rsi
0x1800d8ab4  pop     rbp
0x1800d8ab5  retn
```
