# CUMRDPService::Handler(ulong,ulong,void *)

- ea: `0x180001a20`
- end: `0x18000215c`
- name: `?Handler@CUMRDPService@@AEAAKKKPEAX@Z`
- size: `1852`
- prototype: `unsigned int __fastcall(CUMRDPService *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180001a00`

## callees

- `0x180001a20`
- `0x180002920`
- `0x180005280`
- `0x18000a5cc`
- `0x18000e574`
- `0x18000e5c0`
- `0x180047ebe`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001a58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001a58`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000200c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000200c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001c95`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001c95`
- `WINSTA!WinStationQueryInformationW` at `0x180001e5d`
- `WINSTA!WinStationQueryInformationW` at `0x180001e5d`
- `WINSTA!WinStationIsSessionRemoteable` at `0x180001bae`
- `WINSTA!WinStationIsSessionRemoteable` at `0x180001bae`

## pseudocode

```c
__int64 __fastcall CUMRDPService::Handler(CUMRDPService *this, unsigned int a2, unsigned int a3, _DWORD *a4)
{
  __int64 v8; // rdx
  unsigned int *v9; // r8
  int v10; // r14d
  unsigned int v11; // ebp
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int *v16; // kr00_8
  unsigned int v17; // eax
  unsigned int v18; // r12d
  __int64 v19; // rcx
  int v20; // r12d
  __int64 v21; // rcx
  __int128 v22; // xmm1
  __int64 v23; // rcx
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  void *v30; // rcx
  unsigned int v31; // [rsp+20h] [rbp-558h]
  _BYTE v32[4]; // [rsp+30h] [rbp-548h] BYREF
  int v33; // [rsp+34h] [rbp-544h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-540h] BYREF
  _DWORD v35[304]; // [rsp+60h] [rbp-518h] BYREF

  WaitForSingleObject(*((HANDLE *)this + 34), 0xFFFFFFFF);
  if ( *((int *)this + 70) < 0 )
    return 120;
  v9 = &_ImageBase;
  v10 = 0;
  v11 = 0;
  if ( a2 != 11 )
  {
    v8 = *((unsigned int *)this + 8);
    switch ( a2 )
    {
      case 1u:
        goto LABEL_14;
      case 2u:
      case 3u:
        LODWORD(v8) = (unsigned int)v8 >> 1;
        goto LABEL_14;
      case 4u:
        goto LABEL_24;
      case 5u:
        LODWORD(v8) = (unsigned int)v8 >> 2;
        goto LABEL_14;
      case 6u:
        LODWORD(v8) = (unsigned int)v8 >> 3;
        goto LABEL_14;
      case 7u:
      case 8u:
      case 9u:
      case 0xAu:
        LODWORD(v8) = (unsigned int)v8 >> 4;
        goto LABEL_14;
      case 0xCu:
        LODWORD(v8) = (unsigned int)v8 >> 5;
        goto LABEL_14;
      case 0xDu:
        LODWORD(v8) = (unsigned int)v8 >> 6;
        goto LABEL_14;
      case 0xEu:
        LODWORD(v8) = (unsigned int)v8 >> 7;
        goto LABEL_14;
      case 0xFu:
        LODWORD(v8) = (unsigned int)v8 >> 8;
        goto LABEL_14;
      case 0x10u:
        LODWORD(v8) = (unsigned int)v8 >> 9;
        goto LABEL_14;
      case 0x20u:
        LODWORD(v8) = (unsigned int)v8 >> 10;
LABEL_14:
        v8 &= 1u;
        if ( (_DWORD)v8 )
        {
          switch ( a2 )
          {
            case 0xEu:
              v18 = a4[1];
              v32[0] = 0;
              if ( !(unsigned __int8)WinStationIsSessionRemoteable(0, v18, v32) )
              {
                GetLastError();
                v32[0] = 0;
              }
              switch ( a3 )
              {
                case 1u:
                  if ( !v32[0] )
                    goto LABEL_67;
                  goto LABEL_65;
                case 2u:
                case 4u:
                  goto LABEL_66;
                case 3u:
                  goto LABEL_65;
                case 5u:
                  CUMRDPService::OnLogon(this, v18, v32[0]);
                  goto LABEL_67;
                case 6u:
                  CUMRDPService::OnLogoff(this, v18);
                  goto LABEL_20;
                case 9u:
                  memset_0(v35, 0, sizeof(v35));
                  v33 = 0;
                  if ( (unsigned __int8)WinStationQueryInformationW(0, v18, 8, v35, 1216, &v33) )
                  {
                    if ( v35[0] == 3 )
                    {
LABEL_66:
                      CUMRDPService::OnDisconnect(this, v18);
                    }
                    else if ( !v35[0] )
                    {
LABEL_65:
                      CUMRDPService::OnReconnect(this, v18);
                    }
                  }
                  else
                  {
                    GetLastError();
                  }
                  goto LABEL_67;
                default:
                  if ( a3 == 6 )
                  {
LABEL_20:
                    v19 = *((_QWORD *)this + 8);
                    if ( v19 )
                      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 64LL))(v19, v18);
                  }
                  else
                  {
LABEL_67:
                    switch ( a3 )
                    {
                      case 1u:
                        v24 = (__int64 *)*((_QWORD *)this + 8);
                        if ( v24 )
                        {
                          v25 = *v24;
                          if ( v32[0] )
                            (*(void (__fastcall **)(__int64 *, _QWORD))(v25 + 48))(v24, v18);
                          else
                            (*(void (__fastcall **)(__int64 *, _QWORD))(v25 + 40))(v24, v18);
                        }
                        break;
                      case 2u:
                        v26 = *((_QWORD *)this + 8);
                        if ( v26 )
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 72LL))(v26, v18);
                        break;
                      case 3u:
                      case 9u:
                        v27 = *((_QWORD *)this + 8);
                        if ( v27 )
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 48LL))(v27, v18);
                        break;
                      case 4u:
                        v28 = *((_QWORD *)this + 8);
                        if ( v28 )
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 80LL))(v28, v18);
                        break;
                      case 5u:
                        v29 = *((_QWORD *)this + 8);
                        if ( v29 )
                          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 56LL))(v29, v18);
                        break;
                      default:
                        goto LABEL_3;
                    }
                  }
                  break;
              }
              break;
            case 1u:
              if ( *((_DWORD *)this + 7) == 4 )
              {
                CUMRDPService::UpdateStatus(this, 3u, (unsigned int)&_ImageBase, 0x12Au, v31);
                v10 = 1;
              }
              break;
            case 4u:
LABEL_24:
              if ( *((_QWORD *)this + 2) )
              {
                v20 = *((_DWORD *)this + 7);
                *((_DWORD *)this + 8) = 132;
                if ( v20 == 4 )
                  *((_DWORD *)this + 8) = 133;
                v21 = *((_QWORD *)this + 36);
                *(_QWORD *)((char *)this + 36) = 0;
                *(_QWORD *)((char *)this + 44) = 0;
                v22 = *(_OWORD *)((char *)this + 36);
                *(_OWORD *)&ServiceStatus.dwServiceType = *(_OWORD *)((char *)this + 24);
                *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v22;
                if ( v21 )
                  ServiceStatus.dwControlsAccepted = ServiceStatus.dwControlsAccepted & 0xFFFFFFF8
                                                   | (LOBYTE(ServiceStatus.dwControlsAccepted) | 0xFFFFFFF8)
                                                   & (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v21 + 8LL))(
                                                       v21,
                                                       v8,
                                                       &_ImageBase);
                v23 = *((_QWORD *)this + 39);
                if ( v23 )
                  ServiceStatus.dwControlsAccepted |= (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v23 + 8LL))(
                                                        v23,
                                                        v8,
                                                        v9);
                SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 2), &ServiceStatus);
                if ( v20 == 1 )
                  *((_QWORD *)this + 2) = 0;
              }
              break;
            case 5u:
              CUMRDPService::UpdateStatus(this, 1u, (unsigned int)&_ImageBase, 0, v31);
              break;
            default:
              v11 = 120;
              break;
          }
        }
        break;
      default:
        break;
    }
  }
LABEL_3:
  v12 = *((_QWORD *)this + 36);
  if ( v12 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v12 + 8LL))(v12, v8, v9);
    if ( a2 != 11 )
    {
      v16 = v9;
      v9 = &_ImageBase;
      switch ( a2 )
      {
        case 1u:
          goto LABEL_40;
        case 2u:
        case 3u:
          v13 >>= 1;
          goto LABEL_40;
        case 4u:
          goto LABEL_41;
        case 5u:
          v13 >>= 2;
          goto LABEL_40;
        case 6u:
          v13 >>= 3;
          goto LABEL_40;
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
          v13 >>= 4;
          goto LABEL_40;
        case 0xCu:
          v13 >>= 5;
          goto LABEL_40;
        case 0xDu:
          v13 >>= 6;
          goto LABEL_40;
        case 0xEu:
          v13 >>= 7;
          goto LABEL_40;
        case 0xFu:
          v13 >>= 8;
          goto LABEL_40;
        case 0x10u:
          v13 >>= 9;
          goto LABEL_40;
        case 0x20u:
          v13 >>= 10;
LABEL_40:
          if ( (v13 & 1) != 0 )
            goto LABEL_41;
          goto LABEL_6;
        default:
          v9 = v16;
          goto LABEL_6;
      }
    }
    if ( *((_DWORD *)this + 71) )
    {
LABEL_41:
      (***((void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _DWORD *))this + 36))(*((_QWORD *)this + 36), a2, a3, a4);
      v11 = 0;
    }
  }
LABEL_6:
  v14 = *((_QWORD *)this + 39);
  if ( v14 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v14 + 8LL))(v14, v8, v9);
    if ( a2 != 11 )
    {
      switch ( a2 )
      {
        case 1u:
          goto LABEL_37;
        case 2u:
        case 3u:
          v17 >>= 1;
          goto LABEL_37;
        case 4u:
          goto LABEL_38;
        case 5u:
          v17 >>= 2;
          goto LABEL_37;
        case 6u:
          v17 >>= 3;
          goto LABEL_37;
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
          v17 >>= 4;
          goto LABEL_37;
        case 0xCu:
          v17 >>= 5;
          goto LABEL_37;
        case 0xDu:
          v17 >>= 6;
          goto LABEL_37;
        case 0xEu:
          v17 >>= 7;
          goto LABEL_37;
        case 0xFu:
          v17 >>= 8;
          goto LABEL_37;
        case 0x10u:
          v17 >>= 9;
          goto LABEL_37;
        case 0x20u:
          v17 >>= 10;
LABEL_37:
          if ( (v17 & 1) != 0 )
          {
LABEL_38:
            (***((void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _DWORD *))this + 39))(
              *((_QWORD *)this + 39),
              a2,
              a3,
              a4);
            v11 = 0;
          }
          break;
        default:
          break;
      }
    }
  }
  if ( v10 )
  {
    v30 = (void *)*((_QWORD *)this + 11);
    if ( v30 )
      SetEvent(v30);
  }
  return v11;
}

```

## disassembly

```asm
0x180001a20  push    rbx
0x180001a22  push    rbp
0x180001a23  push    rsi
0x180001a24  push    r13
0x180001a26  push    r15
0x180001a28  sub     rsp, 550h
0x180001a2f  mov     rax, cs:__security_cookie
0x180001a36  xor     rax, rsp
0x180001a39  mov     [rsp+578h+var_58], rax
0x180001a41  mov     esi, edx
0x180001a43  mov     rbx, rcx
0x180001a46  mov     rcx, [rcx+110h]; hHandle
0x180001a4d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180001a52  mov     r13, r9
0x180001a55  mov     r15d, r8d
0x180001a58  call    cs:__imp_WaitForSingleObject
0x180001a5e  cmp     dword ptr [rbx+118h], 0
0x180001a65  jl      loc_180001CC4
0x180001a6b  mov     [rsp+578h+var_40], r14
0x180001a73  lea     r8, __ImageBase; unsigned int
0x180001a7a  xor     r14d, r14d
0x180001a7d  xor     ebp, ebp
0x180001a7f  cmp     esi, 0Bh
0x180001a82  jnz     short loc_180001AF4
0x180001a84  mov     rcx, [rbx+120h]; jumptable 0000000180001B23 default case
0x180001a8b  test    rcx, rcx
0x180001a8e  jz      short def_180001B48; jumptable 0000000180001B48 default case, cases 11,17-31
0x180001a90  mov     rax, [rcx]
0x180001a93  mov     rax, [rax+8]
0x180001a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a9c  cmp     esi, 0Bh
0x180001a9f  jnz     loc_180001B25
0x180001aa5  cmp     dword ptr [rbx+11Ch], 0
0x180001aac  jnz     loc_180001D0B; jumptable 0000000180001B48 case 4
0x180001ab2  mov     rcx, [rbx+138h]; jumptable 0000000180001B48 default case, cases 11,17-31
0x180001ab9  test    rcx, rcx
0x180001abc  jnz     loc_180001B4A
0x180001ac2  test    r14d, r14d; jumptable 0000000180001B86 default case, cases 11,17-31
0x180001ac5  mov     r14, [rsp+578h+var_40]
0x180001acd  jnz     loc_180001FFF
0x180001ad3  mov     eax, ebp
0x180001ad5  mov     rcx, [rsp+578h+var_58]
0x180001add  xor     rcx, rsp; StackCookie
0x180001ae0  call    __security_check_cookie
0x180001ae5  add     rsp, 550h
0x180001aec  pop     r15
0x180001aee  pop     r13
0x180001af0  pop     rsi
0x180001af1  pop     rbp
0x180001af2  pop     rbx
0x180001af3  retn
0x180001af4  lea     eax, [rsi-1]; switch 32 cases
0x180001af7  cmp     eax, 1Fh
0x180001afa  ja      short def_180001B23; jumptable 0000000180001B23 default case
0x180001afc  mov     edx, [rbx+20h]
0x180001aff  mov     [rsp+578h+var_30], rdi
0x180001b07  mov     [rsp+578h+var_38], r12
0x180001b0f  movzx   eax, ds:(byte_18000204C - 180000000h)[r8+rax]
0x180001b18  mov     ecx, ds:(jpt_180001B23 - 180000000h)[r8+rax*4]
0x180001b20  add     rcx, r8
0x180001b23  jmp     rcx; switch jump
0x180001b25  lea     ecx, [rsi-1]; switch 32 cases
0x180001b28  cmp     ecx, 1Fh
0x180001b2b  ja      short def_180001B48; jumptable 0000000180001B48 default case, cases 11,17-31
0x180001b2d  lea     r8, __ImageBase
0x180001b34  movzx   ecx, ds:(byte_1800020A0 - 180000000h)[r8+rcx]
0x180001b3d  mov     edx, ds:(jpt_180001B48 - 180000000h)[r8+rcx*4]
0x180001b45  add     rdx, r8
0x180001b48  jmp     rdx; switch jump
0x180001b4a  mov     rax, [rcx]
0x180001b4d  mov     rax, [rax+8]
0x180001b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b56  cmp     esi, 0Bh
0x180001b59  jz      def_180001B86; jumptable 0000000180001B86 default case, cases 11,17-31
0x180001b5f  lea     ecx, [rsi-1]; switch 32 cases
0x180001b62  cmp     ecx, 1Fh
0x180001b65  ja      def_180001B86; jumptable 0000000180001B86 default case, cases 11,17-31
0x180001b6b  lea     r8, __ImageBase
0x180001b72  movzx   ecx, ds:(byte_1800020F4 - 180000000h)[r8+rcx]
0x180001b7b  mov     edx, ds:(jpt_180001B86 - 180000000h)[r8+rcx*4]
0x180001b83  add     rdx, r8
0x180001b86  jmp     rdx; switch jump
0x180001b88  shr     edx, 7; jumptable 0000000180001B23 case 14
0x180001b8b  and     edx, 1; jumptable 0000000180001B23 case 1
0x180001b8e  test    edx, edx
0x180001b90  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001b96  cmp     esi, 0Eh
0x180001b99  jnz     short loc_180001BF4
0x180001b9b  mov     r12d, [r13+4]
0x180001b9f  lea     r8, [rsp+578h+var_548]
0x180001ba4  mov     edx, r12d
0x180001ba7  mov     [rsp+578h+var_548], bpl
0x180001bac  xor     ecx, ecx
0x180001bae  call    cs:__imp_WinStationIsSessionRemoteable
0x180001bb4  test    al, al
0x180001bb6  jz      loc_180001DC8
0x180001bbc  lea     edi, [r15-1]; switch 9 cases
0x180001bc0  cmp     edi, 8
0x180001bc3  jbe     loc_180001DD8
0x180001bc9  cmp     r15d, 6; jumptable 0000000180001DE9 default case, cases 7,8
0x180001bcd  jnz     loc_180001CBA
0x180001bd3  mov     rcx, [rbx+40h]
0x180001bd7  test    rcx, rcx
0x180001bda  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001be0  mov     rax, [rcx]
0x180001be3  mov     edx, r12d
0x180001be6  mov     rax, [rax+40h]
0x180001bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bef  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001bf4  mov     eax, esi
0x180001bf6  sub     eax, 1
0x180001bf9  jz      loc_180001DA0
0x180001bff  sub     eax, 3
0x180001c02  jnz     loc_180001D73
0x180001c08  cmp     [rbx+10h], rbp; jumptable 0000000180001B23 case 4
0x180001c0c  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001c12  mov     r12d, [rbx+1Ch]
0x180001c16  mov     dword ptr [rbx+20h], 84h
0x180001c1d  cmp     r12d, 4
0x180001c21  jnz     short loc_180001C2A
0x180001c23  mov     dword ptr [rbx+20h], 85h
0x180001c2a  mov     rcx, [rbx+120h]
0x180001c31  mov     [rbx+24h], rbp
0x180001c35  mov     [rbx+2Ch], rbp
0x180001c39  movups  xmm0, xmmword ptr [rbx+18h]
0x180001c3d  movups  xmm1, xmmword ptr [rbx+24h]
0x180001c41  movups  xmmword ptr [rsp+578h+ServiceStatus.dwServiceType], xmm0
0x180001c46  movups  xmmword ptr [rsp+578h+ServiceStatus.dwWin32ExitCode], xmm1
0x180001c4b  test    rcx, rcx
0x180001c4e  jz      short loc_180001C70
0x180001c50  mov     rax, [rcx]
0x180001c53  mov     edi, [rsp+578h+ServiceStatus.dwControlsAccepted]
0x180001c57  mov     rax, [rax+8]
0x180001c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c60  mov     ecx, edi
0x180001c62  and     edi, 0FFFFFFF8h
0x180001c65  or      ecx, 0FFFFFFF8h
0x180001c68  and     eax, ecx
0x180001c6a  or      eax, edi
0x180001c6c  mov     [rsp+578h+ServiceStatus.dwControlsAccepted], eax
0x180001c70  mov     rcx, [rbx+138h]
0x180001c77  test    rcx, rcx
0x180001c7a  jz      short loc_180001C8C
0x180001c7c  mov     rax, [rcx]
0x180001c7f  mov     rax, [rax+8]
0x180001c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c88  or      [rsp+578h+ServiceStatus.dwControlsAccepted], eax
0x180001c8c  mov     rcx, [rbx+10h]; hServiceStatus
0x180001c90  lea     rdx, [rsp+578h+ServiceStatus]; lpServiceStatus
0x180001c95  call    cs:__imp_SetServiceStatus
0x180001c9b  cmp     r12d, 1
0x180001c9f  jz      loc_180001F68
0x180001ca5  mov     rdi, [rsp+578h+var_30]; jumptable 0000000180001B23 cases 11,17-31
0x180001cad  mov     r12, [rsp+578h+var_38]
0x180001cb5  jmp     def_180001B23; jumptable 0000000180001B23 default case
0x180001cba  cmp     edi, 8; switch 9 cases
0x180001cbd  ja      short def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001cbf  jmp     loc_180001E94
0x180001cc4  mov     eax, 78h ; 'x'
0x180001cc9  jmp     loc_180001AD5
0x180001cce  shr     eax, 7; jumptable 0000000180001B86 case 14
0x180001cd1  and     eax, 1; jumptable 0000000180001B86 case 1
0x180001cd4  test    eax, eax
0x180001cd6  jz      def_180001B86; jumptable 0000000180001B86 default case, cases 11,17-31
0x180001cdc  mov     rcx, [rbx+138h]; jumptable 0000000180001B86 case 4
0x180001ce3  mov     r9, r13
0x180001ce6  mov     r8d, r15d
0x180001ce9  mov     edx, esi
0x180001ceb  mov     rax, [rcx]
0x180001cee  mov     rax, [rax]
0x180001cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cf6  xor     ebp, ebp
0x180001cf8  jmp     def_180001B86; jumptable 0000000180001B86 default case, cases 11,17-31
0x180001cfd  shr     eax, 7; jumptable 0000000180001B48 case 14
0x180001d00  and     eax, 1; jumptable 0000000180001B48 case 1
0x180001d03  test    eax, eax
0x180001d05  jz      def_180001B48; jumptable 0000000180001B48 default case, cases 11,17-31
0x180001d0b  mov     rcx, [rbx+120h]; jumptable 0000000180001B48 case 4
0x180001d12  mov     r9, r13
0x180001d15  mov     r8d, r15d
0x180001d18  mov     edx, esi
0x180001d1a  mov     rax, [rcx]
0x180001d1d  mov     rax, [rax]
0x180001d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d25  xor     ebp, ebp
0x180001d27  jmp     def_180001B48; jumptable 0000000180001B48 default case, cases 11,17-31
0x180001d2c  shr     edx, 1; jumptable 0000000180001B23 cases 2,3
0x180001d2e  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d33  shr     edx, 2; jumptable 0000000180001B23 case 5
0x180001d36  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d3b  shr     edx, 3; jumptable 0000000180001B23 case 6
0x180001d3e  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d43  shr     edx, 4; jumptable 0000000180001B23 cases 7-10
0x180001d46  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d4b  shr     edx, 5; jumptable 0000000180001B23 case 12
0x180001d4e  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d53  shr     edx, 6; jumptable 0000000180001B23 case 13
0x180001d56  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d5b  shr     edx, 8; jumptable 0000000180001B23 case 15
0x180001d5e  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d63  shr     edx, 9; jumptable 0000000180001B23 case 16
0x180001d66  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d6b  shr     edx, 0Ah; jumptable 0000000180001B23 case 32
0x180001d6e  jmp     loc_180001B8B; jumptable 0000000180001B23 case 1
0x180001d73  sub     eax, 1
0x180001d76  jz      short loc_180001D8B
0x180001d78  cmp     eax, 6
0x180001d7b  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001d81  mov     ebp, 78h ; 'x'
0x180001d86  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001d8b  xor     r9d, r9d; unsigned int
0x180001d8e  mov     edx, 1; unsigned int
0x180001d93  mov     rcx, rbx; this
0x180001d96  call    ?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z; CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)
0x180001d9b  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001da0  cmp     dword ptr [rbx+1Ch], 4
0x180001da4  jnz     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001daa  mov     edx, 3; unsigned int
0x180001daf  mov     r9d, 12Ah; unsigned int
0x180001db5  mov     rcx, rbx; this
0x180001db8  call    ?UpdateStatus@CUMRDPService@@AEAAHKKKK@Z; CUMRDPService::UpdateStatus(ulong,ulong,ulong,ulong)
0x180001dbd  mov     r14d, 1
0x180001dc3  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001dc8  call    cs:__imp_GetLastError
0x180001dce  mov     [rsp+578h+var_548], bpl
0x180001dd3  jmp     loc_180001BBC
0x180001dd8  lea     rcx, __ImageBase
0x180001ddf  mov     eax, ds:(jpt_180001DE9 - 180000000h)[rcx+rdi*4]
0x180001de6  add     rax, rcx
0x180001de9  jmp     rax; switch jump
0x180001deb  movzx   r8d, [rsp+578h+var_548]; jumptable 0000000180001DE9 case 5
0x180001df1  mov     edx, r12d; unsigned int
0x180001df4  mov     rcx, rbx; this
0x180001df7  call    ?OnLogon@CUMRDPService@@AEAAKKH@Z; CUMRDPService::OnLogon(ulong,int)
0x180001dfc  jmp     loc_180001E94
0x180001e01  mov     edx, r12d; jumptable 0000000180001DE9 case 6
0x180001e04  mov     rcx, rbx; this
0x180001e07  call    ?OnLogoff@CUMRDPService@@AEAAKK@Z; CUMRDPService::OnLogoff(ulong)
0x180001e0c  jmp     loc_180001BD3
0x180001e11  cmp     [rsp+578h+var_548], bpl; jumptable 0000000180001DE9 case 1
0x180001e16  jz      short loc_180001E94
0x180001e18  mov     edx, r12d; jumptable 0000000180001DE9 case 3
0x180001e1b  mov     rcx, rbx; this
0x180001e1e  call    ?OnReconnect@CUMRDPService@@AEAAKK@Z; CUMRDPService::OnReconnect(ulong)
0x180001e23  jmp     short loc_180001E94
0x180001e25  xor     edx, edx; jumptable 0000000180001DE9 case 9
0x180001e27  lea     rcx, [rsp+578h+var_518]; void *
0x180001e2c  mov     r8d, 4C0h; Size
0x180001e32  call    memset_0
0x180001e37  lea     rax, [rsp+578h+var_544]
0x180001e3c  mov     [rsp+578h+var_544], ebp
0x180001e40  mov     [rsp+578h+var_550], rax
0x180001e45  lea     r9, [rsp+578h+var_518]
0x180001e4a  mov     r8d, 8
0x180001e50  mov     [rsp+578h+var_558], 4C0h
0x180001e58  mov     edx, r12d
0x180001e5b  xor     ecx, ecx
0x180001e5d  call    cs:__imp_WinStationQueryInformationW
0x180001e63  test    al, al
0x180001e65  jnz     short loc_180001E6F
0x180001e67  call    cs:__imp_GetLastError
0x180001e6d  jmp     short loc_180001E94
0x180001e6f  mov     eax, [rsp+578h+var_518]
0x180001e73  cmp     eax, 3
0x180001e76  jz      short loc_180001E89; jumptable 0000000180001DE9 cases 2,4
0x180001e78  test    eax, eax
0x180001e7a  jnz     short loc_180001E94
0x180001e7c  mov     edx, r12d; unsigned int
0x180001e7f  mov     rcx, rbx; this
0x180001e82  call    ?OnReconnect@CUMRDPService@@AEAAKK@Z; CUMRDPService::OnReconnect(ulong)
0x180001e87  jmp     short loc_180001E94
0x180001e89  mov     edx, r12d; jumptable 0000000180001DE9 cases 2,4
0x180001e8c  mov     rcx, rbx; this
0x180001e8f  call    ?OnDisconnect@CUMRDPService@@AEAAKK@Z; CUMRDPService::OnDisconnect(ulong)
0x180001e94  lea     rax, __ImageBase
0x180001e9b  mov     eax, ds:(jpt_180001EAC - 180000000h)[rax+rdi*4]
0x180001ea2  lea     rcx, __ImageBase
0x180001ea9  add     rax, rcx
0x180001eac  jmp     rax; switch jump
0x180001eae  mov     rcx, [rbx+40h]; jumptable 0000000180001EAC case 0
0x180001eb2  test    rcx, rcx
0x180001eb5  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001ebb  mov     edx, r12d
0x180001ebe  mov     rax, [rcx]
0x180001ec1  cmp     [rsp+578h+var_548], bpl
0x180001ec6  jz      short loc_180001ED6
0x180001ec8  mov     rax, [rax+30h]
0x180001ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed1  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001ed6  mov     rax, [rax+28h]
0x180001eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001edf  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001ee4  mov     rcx, [rbx+40h]; jumptable 0000000180001EAC case 1
0x180001ee8  test    rcx, rcx
0x180001eeb  jz      def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
0x180001ef1  mov     rax, [rcx]
0x180001ef4  mov     edx, r12d
0x180001ef7  mov     rax, [rax+48h]
0x180001efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f00  jmp     def_180001EAC; jumptable 0000000180001B23 cases 11,17-31
  ... truncated ...
```
