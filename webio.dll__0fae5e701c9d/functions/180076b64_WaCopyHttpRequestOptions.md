# WaCopyHttpRequestOptions

- ea: `0x180076b64`
- end: `0x1800770ad`
- name: `WaCopyHttpRequestOptions`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180081d08`

## callees

- `0x18002e460`
- `0x180060954`
- `0x18006af94`
- `0x1800722f0`
- `0x180076b64`
- `0x18008c250`
- `0x18008c294`
- `0x1800923bc`
- `0x180092500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076d48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076d39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180076d48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076bb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077079`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180076d79`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180076d79`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180076e51`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180076e51`

## pseudocode

```c
__int64 __fastcall WaCopyHttpRequestOptions(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  SECURITY_STATUS UserCredentials; // eax
  bool v6; // zf
  SECURITY_STATUS v7; // eax
  bool v8; // zf
  void *v9; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  __int64 v12; // rcx
  unsigned int LastError; // eax
  __int64 v14; // rax
  const CERT_CONTEXT *v15; // rcx
  PCCERT_CONTEXT v16; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h]

  v20 = 0;
  TargetHandle = 0;
  v19 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  *(_QWORD *)(a2 + 4048) = *(_QWORD *)(a1 + 4048);
  *(_BYTE *)(a2 + 4056) = *(_BYTE *)(a1 + 4056);
  *(_DWORD *)(a2 + 4032) = *(_DWORD *)(a1 + 4032);
  *(_BYTE *)(a2 + 4545) = *(_BYTE *)(a1 + 4545);
  *(_BYTE *)(a2 + 4544) = *(_BYTE *)(a1 + 4544);
  *(_OWORD *)(a2 + 4548) = *(_OWORD *)(a1 + 4548);
  *(_QWORD *)(a2 + 4564) = *(_QWORD *)(a1 + 4564);
  v4 = WapCaptureAuthSpnUsage(a1 + 4360, a2 + 4360);
  if ( !v4 )
  {
    v4 = WapCaptureAuthSpnUsage(a1 + 4424, a2 + 4424);
    if ( !v4 )
    {
      *(_DWORD *)(a2 + 4352) = *(_DWORD *)(a1 + 4352);
      *(_DWORD *)(a2 + 4416) = *(_DWORD *)(a1 + 4416);
      *(_OWORD *)(a2 + 4448) = *(_OWORD *)(a1 + 4448);
      *(_QWORD *)(a2 + 4464) = *(_QWORD *)(a1 + 4464);
      *(_BYTE *)(a2 + 4472) = *(_BYTE *)(a1 + 4472);
      UserCredentials = WaAuthQueryUserCredentials((_DWORD **)(a1 + 4320), (__int64)&v19);
      v4 = UserCredentials;
      if ( UserCredentials )
      {
        v6 = UserCredentials == 1168;
      }
      else
      {
        v4 = WaAuthSetCredentials((__int64 *)(a2 + 4320), (__int64)&v19);
        WaAuthFreeUserCredentials(&v19);
        v6 = v4 == 0;
      }
      if ( v6 )
      {
        v7 = WaAuthQueryUserCredentials((_DWORD **)(a1 + 4384), (__int64)&v19);
        v4 = v7;
        if ( v7 )
        {
          v8 = v7 == 1168;
        }
        else
        {
          v4 = WaAuthSetCredentials((__int64 *)(a2 + 4384), (__int64)&v19);
          WaAuthFreeUserCredentials(&v19);
          v8 = v4 == 0;
        }
        if ( v8 )
        {
          if ( *(_QWORD *)(a1 + 4512) )
          {
            v9 = *(void **)(a1 + 4512);
            CurrentProcess = GetCurrentProcess();
            v11 = GetCurrentProcess();
            if ( !DuplicateHandle(v11, v9, CurrentProcess, &TargetHandle, 0, 0, 2u) )
            {
              LastError = WaGetLastError(v12);
              v4 = LastError;
              if ( (xmmword_1800AD710 & 2) != 0 )
                WPP_SF_qD(513, 18, WPP_08f0ab51ccfe379c381e122b33fc5841_Traceguids, *(_QWORD *)(a1 + 4512), LastError);
              goto LABEL_25;
            }
            if ( (xmmword_1800AD720 & 2) != 0 )
              WPP_SF_qq(
                1025,
                19,
                (unsigned int)WPP_08f0ab51ccfe379c381e122b33fc5841_Traceguids,
                *(_QWORD *)(a1 + 4512),
                (__int64)TargetHandle);
            *(_QWORD *)(a2 + 4512) = TargetHandle;
            TargetHandle = 0;
          }
          v14 = *(_QWORD *)(a1 + 4504);
          v4 = 0;
          *(_QWORD *)(a2 + 4504) = v14;
          if ( v14 )
            _InterlockedIncrement((volatile signed __int32 *)(v14 + 4));
          *(_DWORD *)(a2 + 4072) = *(_DWORD *)(a1 + 4072);
          *(_BYTE *)(a2 + 4068) = *(_BYTE *)(a1 + 4068);
          *(_DWORD *)(a2 + 4076) = *(_DWORD *)(a1 + 4076);
          v15 = *(const CERT_CONTEXT **)(a1 + 4088);
          if ( v15 )
            v16 = CertDuplicateCertificateContext(v15);
          else
            v16 = 0;
          *(_QWORD *)(a2 + 4088) = v16;
          v6 = WaKirDnsResolution == 0;
          *(_BYTE *)(a2 + 4096) = *(_BYTE *)(a1 + 4096);
          *(_BYTE *)(a2 + 4097) = *(_BYTE *)(a1 + 4097);
          *(_BYTE *)(a2 + 4098) = *(_BYTE *)(a1 + 4098);
          *(_DWORD *)(a2 + 4120) = *(_DWORD *)(a1 + 4120);
          *(_BYTE *)(a2 + 4125) = *(_BYTE *)(a1 + 4125);
          *(_DWORD *)(a2 + 4128) = *(_DWORD *)(a1 + 4128);
          *(_DWORD *)(a2 + 4132) = *(_DWORD *)(a1 + 4132);
          *(_BYTE *)(a2 + 4164) = *(_BYTE *)(a1 + 4164);
          *(_BYTE *)(a2 + 4680) = *(_BYTE *)(a1 + 4680);
          *(_DWORD *)(a2 + 4592) = *(_DWORD *)(a1 + 4592);
          *(_BYTE *)(a2 + 4601) = *(_BYTE *)(a1 + 4601);
          *(_DWORD *)(a2 + 4608) = *(_DWORD *)(a1 + 4608);
          *(_DWORD *)(a2 + 4612) = *(_DWORD *)(a1 + 4612);
          *(_DWORD *)(a2 + 4616) = *(_DWORD *)(a1 + 4616);
          *(_DWORD *)(a2 + 4620) = *(_DWORD *)(a1 + 4620);
          *(_BYTE *)(a2 + 4624) = *(_BYTE *)(a1 + 4624);
          *(_DWORD *)(a2 + 4628) = *(_DWORD *)(a1 + 4628);
          *(_QWORD *)(a2 + 4168) = *(_QWORD *)(a1 + 4168);
          *(_DWORD *)(a2 + 4176) = *(_DWORD *)(a1 + 4176);
          *(_OWORD *)(a2 + 4184) = *(_OWORD *)(a1 + 4184);
          *(_OWORD *)(a2 + 4200) = *(_OWORD *)(a1 + 4200);
          *(_OWORD *)(a2 + 4216) = *(_OWORD *)(a1 + 4216);
          *(_OWORD *)(a2 + 4232) = *(_OWORD *)(a1 + 4232);
          *(_OWORD *)(a2 + 4248) = *(_OWORD *)(a1 + 4248);
          *(_OWORD *)(a2 + 4264) = *(_OWORD *)(a1 + 4264);
          *(_OWORD *)(a2 + 4280) = *(_OWORD *)(a1 + 4280);
          *(_OWORD *)(a2 + 4296) = *(_OWORD *)(a1 + 4296);
          *(_BYTE *)(a2 + 4816) = *(_BYTE *)(a1 + 4816);
          *(_DWORD *)(a2 + 4820) = *(_DWORD *)(a1 + 4820);
          *(_DWORD *)(a2 + 4828) = *(_DWORD *)(a1 + 4828);
          *(_DWORD *)(a2 + 4832) = *(_DWORD *)(a1 + 4832);
          *(_DWORD *)(a2 + 4836) = *(_DWORD *)(a1 + 4836);
          *(_DWORD *)(a2 + 4840) = *(_DWORD *)(a1 + 4840);
          *(_DWORD *)(a2 + 4844) = *(_DWORD *)(a1 + 4844);
          *(_BYTE *)(a2 + 4852) = *(_BYTE *)(a1 + 4852);
          *(_DWORD *)(a2 + 4848) = *(_DWORD *)(a1 + 4848);
          if ( !v6 )
            *(_BYTE *)(a2 + 4127) = *(_BYTE *)(a1 + 4127);
        }
      }
    }
  }
LABEL_25:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v4;
}

```

## disassembly

```asm
0x180076b64  mov     [rsp-28h+arg_10], rbx
0x180076b69  mov     [rsp-28h+arg_18], rsi
0x180076b6e  push    rbp
0x180076b6f  push    rdi
0x180076b70  push    r12
0x180076b72  push    r14
0x180076b74  push    r15
0x180076b76  mov     rbp, rsp
0x180076b79  sub     rsp, 70h
0x180076b7d  mov     rax, cs:__security_cookie
0x180076b84  xor     rax, rsp
0x180076b87  mov     [rbp+var_10], rax
0x180076b8b  xor     eax, eax
0x180076b8d  mov     rsi, rcx
0x180076b90  xorps   xmm0, xmm0
0x180076b93  mov     [rbp+var_18], rax
0x180076b97  add     rcx, 8; lpCriticalSection
0x180076b9b  mov     [rbp+TargetHandle], rax
0x180076b9f  movups  [rbp+var_28], xmm0
0x180076ba3  mov     r14, rdx
0x180076ba6  call    cs:__imp_EnterCriticalSection
0x180076bad  nop     dword ptr [rax+rax+00h]
0x180076bb2  lea     rcx, [r14+8]; lpCriticalSection
0x180076bb6  call    cs:__imp_EnterCriticalSection
0x180076bbd  nop     dword ptr [rax+rax+00h]
0x180076bc2  mov     rax, [rsi+0FD0h]
0x180076bc9  lea     rdx, [r14+1108h]
0x180076bd0  mov     [r14+0FD0h], rax
0x180076bd7  lea     rcx, [rsi+1108h]
0x180076bde  mov     al, [rsi+0FD8h]
0x180076be4  mov     [r14+0FD8h], al
0x180076beb  mov     eax, [rsi+0FC0h]
0x180076bf1  mov     [r14+0FC0h], eax
0x180076bf8  mov     al, [rsi+11C1h]
0x180076bfe  mov     [r14+11C1h], al
0x180076c05  mov     al, [rsi+11C0h]
0x180076c0b  mov     [r14+11C0h], al
0x180076c12  movups  xmm0, xmmword ptr [rsi+11C4h]
0x180076c19  movups  xmmword ptr [r14+11C4h], xmm0
0x180076c21  movsd   xmm1, qword ptr [rsi+11D4h]
0x180076c29  movsd   qword ptr [r14+11D4h], xmm1
0x180076c32  call    WapCaptureAuthSpnUsage
0x180076c37  mov     ebx, eax
0x180076c39  test    eax, eax
0x180076c3b  jnz     loc_180077065
0x180076c41  lea     rdx, [r14+1148h]
0x180076c48  lea     rcx, [rsi+1148h]
0x180076c4f  call    WapCaptureAuthSpnUsage
0x180076c54  mov     ebx, eax
0x180076c56  test    eax, eax
0x180076c58  jnz     loc_180077065
0x180076c5e  mov     eax, [rsi+1100h]
0x180076c64  lea     rcx, [rsi+10E0h]
0x180076c6b  mov     [r14+1100h], eax
0x180076c72  lea     rdx, [rbp+var_28]
0x180076c76  mov     eax, [rsi+1140h]
0x180076c7c  mov     [r14+1140h], eax
0x180076c83  movups  xmm0, xmmword ptr [rsi+1160h]
0x180076c8a  movups  xmmword ptr [r14+1160h], xmm0
0x180076c92  movsd   xmm1, qword ptr [rsi+1170h]
0x180076c9a  movsd   qword ptr [r14+1170h], xmm1
0x180076ca3  mov     al, [rsi+1178h]
0x180076ca9  mov     [r14+1178h], al
0x180076cb0  call    WaAuthQueryUserCredentials
0x180076cb5  mov     ebx, eax
0x180076cb7  mov     edi, 490h
0x180076cbc  test    eax, eax
0x180076cbe  jz      short loc_180076CC4
0x180076cc0  cmp     eax, edi
0x180076cc2  jmp     short loc_180076CE1
0x180076cc4  lea     rcx, [r14+10E0h]
0x180076ccb  lea     rdx, [rbp+var_28]
0x180076ccf  call    WaAuthSetCredentials
0x180076cd4  lea     rcx, [rbp+var_28]
0x180076cd8  mov     ebx, eax
0x180076cda  call    WaAuthFreeUserCredentials
0x180076cdf  test    ebx, ebx
0x180076ce1  jnz     loc_180077065
0x180076ce7  lea     rcx, [rsi+1120h]
0x180076cee  lea     rdx, [rbp+var_28]
0x180076cf2  call    WaAuthQueryUserCredentials
0x180076cf7  mov     ebx, eax
0x180076cf9  test    eax, eax
0x180076cfb  jz      short loc_180076D01
0x180076cfd  cmp     eax, edi
0x180076cff  jmp     short loc_180076D1E
0x180076d01  lea     rcx, [r14+1120h]
0x180076d08  lea     rdx, [rbp+var_28]
0x180076d0c  call    WaAuthSetCredentials
0x180076d11  lea     rcx, [rbp+var_28]
0x180076d15  mov     ebx, eax
0x180076d17  call    WaAuthFreeUserCredentials
0x180076d1c  test    ebx, ebx
0x180076d1e  jnz     loc_180077065
0x180076d24  cmp     qword ptr [rsi+11A0h], 0
0x180076d2c  jz      loc_180076E05
0x180076d32  mov     rdi, [rsi+11A0h]
0x180076d39  call    cs:__imp_GetCurrentProcess
0x180076d40  nop     dword ptr [rax+rax+00h]
0x180076d45  mov     rbx, rax
0x180076d48  call    cs:__imp_GetCurrentProcess
0x180076d4f  nop     dword ptr [rax+rax+00h]
0x180076d54  mov     [rsp+70h+dwOptions], 2; dwOptions
0x180076d5c  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x180076d60  mov     rcx, rax; hSourceProcessHandle
0x180076d63  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x180076d6b  mov     r8, rbx; hTargetProcessHandle
0x180076d6e  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x180076d76  mov     rdx, rdi; hSourceHandle
0x180076d79  call    cs:__imp_DuplicateHandle
0x180076d80  nop     dword ptr [rax+rax+00h]
0x180076d85  test    eax, eax
0x180076d87  jnz     short loc_180076DC3
0x180076d89  call    WaGetLastError
0x180076d8e  mov     ebx, eax
0x180076d90  test    byte ptr cs:xmmword_1800AD710, 2
0x180076d97  jz      loc_180077065
0x180076d9d  mov     r9, [rsi+11A0h]
0x180076da4  lea     r8, WPP_08f0ab51ccfe379c381e122b33fc5841_Traceguids
0x180076dab  mov     edx, 12h
0x180076db0  mov     [rsp+70h+dwDesiredAccess], eax
0x180076db4  mov     ecx, 201h
0x180076db9  call    WPP_SF_qD
0x180076dbe  jmp     loc_180077065
0x180076dc3  test    byte ptr cs:xmmword_1800AD720, 2
0x180076dca  jz      short loc_180076DF2
0x180076dcc  mov     rax, [rbp+TargetHandle]
0x180076dd0  lea     r8, WPP_08f0ab51ccfe379c381e122b33fc5841_Traceguids
0x180076dd7  mov     r9, [rsi+11A0h]
0x180076dde  mov     edx, 13h
0x180076de3  mov     ecx, 401h
0x180076de8  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x180076ded  call    WPP_SF_qq
0x180076df2  mov     rax, [rbp+TargetHandle]
0x180076df6  mov     [r14+11A0h], rax
0x180076dfd  mov     [rbp+TargetHandle], 0
0x180076e05  mov     rax, [rsi+1198h]
0x180076e0c  xor     ebx, ebx
0x180076e0e  mov     [r14+1198h], rax
0x180076e15  test    rax, rax
0x180076e18  jz      short loc_180076E1E
0x180076e1a  lock inc dword ptr [rax+4]
0x180076e1e  mov     eax, [rsi+0FE8h]
0x180076e24  mov     [r14+0FE8h], eax
0x180076e2b  mov     al, [rsi+0FE4h]
0x180076e31  mov     [r14+0FE4h], al
0x180076e38  mov     eax, [rsi+0FECh]
0x180076e3e  mov     [r14+0FECh], eax
0x180076e45  mov     rcx, [rsi+0FF8h]; pCertContext
0x180076e4c  test    rcx, rcx
0x180076e4f  jz      short loc_180076E5F
0x180076e51  call    cs:__imp_CertDuplicateCertificateContext
0x180076e58  nop     dword ptr [rax+rax+00h]
0x180076e5d  jmp     short loc_180076E61
0x180076e5f  xor     eax, eax
0x180076e61  mov     [r14+0FF8h], rax
0x180076e68  cmp     cs:WaKirDnsResolution, bl
0x180076e6e  mov     al, [rsi+1000h]
0x180076e74  mov     [r14+1000h], al
0x180076e7b  mov     al, [rsi+1001h]
0x180076e81  mov     [r14+1001h], al
0x180076e88  mov     al, [rsi+1002h]
0x180076e8e  mov     [r14+1002h], al
0x180076e95  mov     eax, [rsi+1018h]
0x180076e9b  mov     [r14+1018h], eax
0x180076ea2  mov     al, [rsi+101Dh]
0x180076ea8  mov     [r14+101Dh], al
0x180076eaf  mov     eax, [rsi+1020h]
0x180076eb5  mov     [r14+1020h], eax
0x180076ebc  mov     eax, [rsi+1024h]
0x180076ec2  mov     [r14+1024h], eax
0x180076ec9  mov     al, [rsi+1044h]
0x180076ecf  mov     [r14+1044h], al
0x180076ed6  mov     al, [rsi+1248h]
0x180076edc  mov     [r14+1248h], al
0x180076ee3  mov     eax, [rsi+11F0h]
0x180076ee9  mov     [r14+11F0h], eax
0x180076ef0  mov     al, [rsi+11F9h]
0x180076ef6  mov     [r14+11F9h], al
0x180076efd  mov     eax, [rsi+1200h]
0x180076f03  mov     [r14+1200h], eax
0x180076f0a  mov     eax, [rsi+1204h]
0x180076f10  mov     [r14+1204h], eax
0x180076f17  mov     eax, [rsi+1208h]
0x180076f1d  mov     [r14+1208h], eax
0x180076f24  mov     eax, [rsi+120Ch]
0x180076f2a  mov     [r14+120Ch], eax
0x180076f31  mov     al, [rsi+1210h]
0x180076f37  mov     [r14+1210h], al
0x180076f3e  mov     eax, [rsi+1214h]
0x180076f44  mov     [r14+1214h], eax
0x180076f4b  movsd   xmm0, qword ptr [rsi+1048h]
0x180076f53  movsd   qword ptr [r14+1048h], xmm0
0x180076f5c  mov     eax, [rsi+1050h]
0x180076f62  mov     [r14+1050h], eax
0x180076f69  movups  xmm0, xmmword ptr [rsi+1058h]
0x180076f70  movups  xmmword ptr [r14+1058h], xmm0
0x180076f78  movups  xmm1, xmmword ptr [rsi+1068h]
0x180076f7f  movups  xmmword ptr [r14+1068h], xmm1
0x180076f87  movups  xmm0, xmmword ptr [rsi+1078h]
0x180076f8e  movups  xmmword ptr [r14+1078h], xmm0
0x180076f96  movups  xmm1, xmmword ptr [rsi+1088h]
0x180076f9d  movups  xmmword ptr [r14+1088h], xmm1
0x180076fa5  movups  xmm0, xmmword ptr [rsi+1098h]
0x180076fac  movups  xmmword ptr [r14+1098h], xmm0
0x180076fb4  movups  xmm1, xmmword ptr [rsi+10A8h]
0x180076fbb  movups  xmmword ptr [r14+10A8h], xmm1
0x180076fc3  movups  xmm0, xmmword ptr [rsi+10B8h]
0x180076fca  movups  xmmword ptr [r14+10B8h], xmm0
0x180076fd2  movups  xmm1, xmmword ptr [rsi+10C8h]
0x180076fd9  movups  xmmword ptr [r14+10C8h], xmm1
0x180076fe1  mov     al, [rsi+12D0h]
0x180076fe7  mov     [r14+12D0h], al
0x180076fee  mov     eax, [rsi+12D4h]
0x180076ff4  mov     [r14+12D4h], eax
0x180076ffb  mov     eax, [rsi+12DCh]
0x180077001  mov     [r14+12DCh], eax
0x180077008  mov     eax, [rsi+12E0h]
0x18007700e  mov     [r14+12E0h], eax
0x180077015  mov     eax, [rsi+12E4h]
0x18007701b  mov     [r14+12E4h], eax
0x180077022  mov     eax, [rsi+12E8h]
0x180077028  mov     [r14+12E8h], eax
0x18007702f  mov     eax, [rsi+12ECh]
0x180077035  mov     [r14+12ECh], eax
0x18007703c  mov     al, [rsi+12F4h]
0x180077042  mov     [r14+12F4h], al
0x180077049  mov     eax, [rsi+12F0h]
0x18007704f  mov     [r14+12F0h], eax
0x180077056  jz      short loc_180077065
0x180077058  mov     al, [rsi+101Fh]
0x18007705e  mov     [r14+101Fh], al
0x180077065  lea     rcx, [r14+8]; lpCriticalSection
0x180077069  call    cs:__imp_LeaveCriticalSection
0x180077070  nop     dword ptr [rax+rax+00h]
0x180077075  lea     rcx, [rsi+8]; lpCriticalSection
0x180077079  call    cs:__imp_LeaveCriticalSection
0x180077080  nop     dword ptr [rax+rax+00h]
0x180077085  mov     eax, ebx
0x180077087  mov     rcx, [rbp+var_10]
0x18007708b  xor     rcx, rsp; StackCookie
0x18007708e  call    __security_check_cookie
0x180077093  lea     r11, [rsp+70h+var_s0]
0x180077098  mov     rbx, [r11+40h]
0x18007709c  mov     rsi, [r11+48h]
0x1800770a0  mov     rsp, r11
0x1800770a3  pop     r15
0x1800770a5  pop     r14
0x1800770a7  pop     r12
0x1800770a9  pop     rdi
0x1800770aa  pop     rbp
0x1800770ab  retn
```
