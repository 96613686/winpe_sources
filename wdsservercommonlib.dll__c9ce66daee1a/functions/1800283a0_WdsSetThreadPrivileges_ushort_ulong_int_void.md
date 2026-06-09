# WdsSetThreadPrivileges(ushort * *,ulong,int,void * *)

- ea: `0x1800283a0`
- end: `0x1800287c4`
- name: `?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z`
- size: `1060`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int, int, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000179c`
- `0x1800283a0`
- `0x1800287cc`
- `0x1800288c0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028503`
- `KERNEL32!GetLastError` at `0x180028543`
- `KERNEL32!GetLastError` at `0x18002858d`
- `KERNEL32!GetLastError` at `0x1800285e1`
- `KERNEL32!GetLastError` at `0x180028649`
- `KERNEL32!GetLastError` at `0x1800286ba`
- `KERNEL32!GetLastError` at `0x1800286f0`
- `KERNEL32!GetLastError` at `0x18002872d`
- `KERNEL32!GetLastError` at `0x180028503`
- `KERNEL32!GetLastError` at `0x180028543`
- `KERNEL32!GetLastError` at `0x18002858d`
- `KERNEL32!GetLastError` at `0x1800285e1`
- `KERNEL32!GetLastError` at `0x180028649`
- `KERNEL32!GetLastError` at `0x1800286ba`
- `KERNEL32!GetLastError` at `0x1800286f0`
- `KERNEL32!GetLastError` at `0x18002872d`
- `KERNEL32!CloseHandle` at `0x180028766`
- `KERNEL32!CloseHandle` at `0x18002877f`
- `KERNEL32!CloseHandle` at `0x180028766`
- `KERNEL32!CloseHandle` at `0x18002877f`
- `KERNEL32!GetCurrentThread` at `0x180028486`
- `KERNEL32!GetCurrentThread` at `0x180028486`
- `KERNEL32!GetCurrentProcess` at `0x180028558`
- `KERNEL32!GetCurrentProcess` at `0x180028558`
- `ADVAPI32!OpenThreadToken` at `0x1800284a1`
- `ADVAPI32!OpenThreadToken` at `0x1800284a1`
- `ADVAPI32!SetThreadToken` at `0x18002871d`
- `ADVAPI32!SetThreadToken` at `0x18002871d`
- `ADVAPI32!DuplicateTokenEx` at `0x1800286aa`
- `ADVAPI32!DuplicateTokenEx` at `0x1800286aa`
- `ADVAPI32!GetKernelObjectSecurity` at `0x1800284d3`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180028639`
- `ADVAPI32!GetKernelObjectSecurity` at `0x1800284d3`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180028639`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800286e4`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1800286e4`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180028453`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180028453`
- `ADVAPI32!OpenProcessToken` at `0x180028570`
- `ADVAPI32!OpenProcessToken` at `0x180028570`

## pseudocode

```c
__int64 __fastcall WdsSetThreadPrivileges(LPCWSTR *a1, unsigned int a2, int a3, void **a4)
{
  signed int v4; // ebx
  __int64 v5; // r14
  unsigned __int64 v6; // rsi
  struct _TOKEN_PRIVILEGES *v7; // r12
  void **v8; // r15
  LPCWSTR *v10; // r13
  unsigned int *v11; // rax
  _DWORD *v12; // r15
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  DWORD v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // edi
  HANDLE CurrentProcess; // rax
  DWORD v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  DWORD v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  DWORD v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  void *TokenHandle[2]; // [rsp+30h] [rbp-30h] BYREF
  HANDLE Token; // [rsp+40h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+48h] [rbp-18h] BYREF
  DWORD nLengthNeeded; // [rsp+A0h] [rbp+40h] BYREF
  int v42; // [rsp+B0h] [rbp+50h]
  void **v43; // [rsp+B8h] [rbp+58h]

  v43 = a4;
  v42 = a3;
  v4 = 0;
  TokenHandle[0] = (void *)-1LL;
  v5 = -1;
  Token = (HANDLE)-1LL;
  v6 = 0;
  v7 = 0;
  nLengthNeeded = 0;
  v8 = a4;
  v10 = a1;
  memset(&TokenAttributes, 0, sizeof(TokenAttributes));
  if ( !a1 || !a2 || !a4 )
  {
    v4 = -2147024809;
    goto LABEL_48;
  }
  nLengthNeeded = 12 * a2 + 4;
  v11 = (unsigned int *)operator new[](nLengthNeeded, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (struct _TOKEN_PRIVILEGES *)v11;
  if ( !v11 )
  {
LABEL_5:
    v4 = -2147024882;
    goto LABEL_48;
  }
  *v11 = a2;
  if ( a2 )
  {
    v12 = v11 + 3;
    while ( LookupPrivilegeValueW(0, *v10, (PLUID)((char *)&v7->Privileges[0].Luid + 8 * v6 + 4 * (unsigned int)v6)) )
    {
      v6 = (unsigned int)(v6 + 1);
      ++v10;
      *v12 = v42 != 0 ? 2 : 0;
      v12 += 3;
      if ( (unsigned int)v6 >= a2 )
      {
        v8 = v43;
        goto LABEL_11;
      }
    }
    LastError = GetLastError();
    v17 = ElValidateWin32_19(LastError, v15, v16, 236);
    goto LABEL_17;
  }
LABEL_11:
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20006u, 0, TokenHandle) )
  {
    v5 = (__int64)TokenHandle[0];
  }
  else
  {
    v18 = GetLastError();
    v21 = v18;
    if ( v18 == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0x20002u, TokenHandle) )
      {
        TokenHandle[0] = (void *)-1LL;
        v23 = GetLastError();
        v17 = ElValidateWin32_19(v23, v24, v25, 286);
LABEL_17:
        v4 = v17;
        if ( v17 > 0 )
          v4 = (unsigned __int16)v17 | 0x80070000;
        v6 = 0;
        goto LABEL_20;
      }
      v5 = 0;
    }
    else
    {
      TokenHandle[0] = (void *)-1LL;
      if ( (unsigned int)ElValidateWin32_19(v18, v19, v20, 300) )
        goto LABEL_27;
    }
  }
  if ( !GetKernelObjectSecurity(TokenHandle[0], 4u, 0, 0, &nLengthNeeded) )
  {
    v26 = GetLastError();
    v21 = v26;
    if ( v26 == 122 || !(unsigned int)ElValidateWin32_19(v26, v27, v28, 337) )
      goto LABEL_33;
LABEL_27:
    v6 = 0;
    goto LABEL_28;
  }
  v4 = -2147024883;
  if ( (int)ElValidateHr_10(2147942413LL) < 0 )
  {
    v6 = 0;
    goto LABEL_48;
  }
LABEL_33:
  v6 = (unsigned __int64)operator new[](nLengthNeeded, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
    goto LABEL_5;
  if ( !GetKernelObjectSecurity(TokenHandle[0], 4u, (PSECURITY_DESCRIPTOR)v6, nLengthNeeded, &nLengthNeeded) )
  {
    v29 = GetLastError();
    v32 = 354;
    goto LABEL_36;
  }
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_QWORD *)&TokenAttributes.bInheritHandle = 0;
  TokenAttributes.lpSecurityDescriptor = (LPVOID)v6;
  if ( !DuplicateTokenEx(TokenHandle[0], 0x2Cu, &TokenAttributes, SecurityImpersonation, TokenImpersonation, &Token) )
  {
    v29 = GetLastError();
    v32 = 373;
    goto LABEL_36;
  }
  AdjustTokenPrivileges(Token, 0, v7, 0, 0, 0);
  v34 = GetLastError();
  v21 = v34;
  if ( v34 && (unsigned int)ElValidateWin32_19(v34, v35, v36, 410) )
  {
LABEL_28:
    if ( v21 > 0 )
      v4 = (unsigned __int16)v21 | 0x80070000;
    else
      v4 = v21;
    goto LABEL_48;
  }
  if ( !SetThreadToken(0, Token) )
  {
    v29 = GetLastError();
    v32 = 418;
LABEL_36:
    v33 = ElValidateWin32_19(v29, v30, v31, v32);
    v4 = v33;
    if ( v33 > 0 )
      v4 = (unsigned __int16)v33 | 0x80070000;
LABEL_20:
    if ( v4 >= 0 )
      v4 = -2147467259;
    goto LABEL_48;
  }
  if ( TokenHandle[0] == (void *)v5 )
    TokenHandle[0] = (void *)-1LL;
  *v8 = (void *)v5;
LABEL_48:
  if ( TokenHandle[0] != (void *)-1LL )
  {
    CloseHandle(TokenHandle[0]);
    TokenHandle[0] = (void *)-1LL;
  }
  if ( Token != (HANDLE)-1LL )
  {
    CloseHandle(Token);
    Token = (HANDLE)-1LL;
  }
  if ( v7 )
    operator delete(v7);
  if ( v6 )
    operator delete((void *)v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800283a0  mov     [rsp-38h+arg_8], rbx
0x1800283a5  mov     [rsp-38h+arg_18], r9
0x1800283aa  mov     [rsp-38h+arg_10], r8d
0x1800283af  push    rbp
0x1800283b0  push    rsi
0x1800283b1  push    rdi
0x1800283b2  push    r12
0x1800283b4  push    r13
0x1800283b6  push    r14
0x1800283b8  push    r15
0x1800283ba  mov     rbp, rsp
0x1800283bd  sub     rsp, 60h
0x1800283c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800283c5  xor     ebx, ebx
0x1800283c7  mov     [rbp+TokenHandle], rax
0x1800283cb  mov     r14, rax
0x1800283ce  mov     [rbp+Token], rax
0x1800283d2  xor     esi, esi
0x1800283d4  xor     eax, eax
0x1800283d6  xor     r12d, r12d
0x1800283d9  and     [rbp+nLengthNeeded], eax
0x1800283dc  xorps   xmm0, xmm0
0x1800283df  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], rax
0x1800283e3  mov     r15, r9
0x1800283e6  mov     edi, edx
0x1800283e8  mov     r13, rcx
0x1800283eb  movups  xmmword ptr [rbp+TokenAttributes.nLength], xmm0
0x1800283ef  test    rcx, rcx
0x1800283f2  jz      loc_180028754
0x1800283f8  test    edx, edx
0x1800283fa  jz      loc_180028754
0x180028400  test    r9, r9
0x180028403  jz      loc_180028754
0x180028409  lea     eax, [rdx+rdx*2]
0x18002840c  lea     eax, ds:4[rax*4]
0x180028413  mov     ecx, eax; unsigned __int64
0x180028415  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002841c  mov     [rbp+nLengthNeeded], eax
0x18002841f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028424  mov     r12, rax
0x180028427  test    rax, rax
0x18002842a  jnz     short loc_180028436
0x18002842c  mov     ebx, 8007000Eh
0x180028431  jmp     loc_180028759
0x180028436  mov     [rax], edi
0x180028438  test    edi, edi
0x18002843a  jz      short loc_180028486
0x18002843c  lea     r15, [rax+0Ch]
0x180028440  mov     rdx, [r13+0]; lpName
0x180028444  mov     ecx, esi
0x180028446  inc     rcx
0x180028449  lea     rcx, [rcx+rsi*2]
0x18002844d  lea     r8, [r12+rcx*4]; lpLuid
0x180028451  xor     ecx, ecx; lpSystemName
0x180028453  call    cs:__imp_LookupPrivilegeValueW
0x18002845a  nop     dword ptr [rax+rax+00h]
0x18002845f  test    eax, eax
0x180028461  jz      loc_180028503
0x180028467  mov     eax, [rbp+arg_10]
0x18002846a  neg     eax
0x18002846c  sbb     ecx, ecx
0x18002846e  inc     esi
0x180028470  and     ecx, 2
0x180028473  add     r13, 8
0x180028477  mov     [r15], ecx
0x18002847a  add     r15, 0Ch
0x18002847e  cmp     esi, edi
0x180028480  jb      short loc_180028440
0x180028482  mov     r15, [rbp+arg_18]
0x180028486  call    cs:__imp_GetCurrentThread
0x18002848d  nop     dword ptr [rax+rax+00h]
0x180028492  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180028496  xor     r8d, r8d; OpenAsSelf
0x180028499  mov     rcx, rax; ThreadHandle
0x18002849c  mov     edx, 20006h; DesiredAccess
0x1800284a1  call    cs:__imp_OpenThreadToken
0x1800284a8  nop     dword ptr [rax+rax+00h]
0x1800284ad  xor     r13d, r13d
0x1800284b0  test    eax, eax
0x1800284b2  jz      loc_180028543
0x1800284b8  mov     r14, [rbp+TokenHandle]
0x1800284bc  mov     rcx, [rbp+TokenHandle]; Handle
0x1800284c0  lea     rax, [rbp+nLengthNeeded]
0x1800284c4  xor     r9d, r9d; nLength
0x1800284c7  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800284cc  xor     r8d, r8d; pSecurityDescriptor
0x1800284cf  lea     edx, [r9+4]; RequestedInformation
0x1800284d3  call    cs:__imp_GetKernelObjectSecurity
0x1800284da  nop     dword ptr [rax+rax+00h]
0x1800284df  test    eax, eax
0x1800284e1  jz      loc_1800285E1
0x1800284e7  mov     ebx, 8007000Dh
0x1800284ec  mov     ecx, ebx
0x1800284ee  call    ElValidateHr_10
0x1800284f3  test    eax, eax
0x1800284f5  jns     loc_180028605
0x1800284fb  mov     rsi, r13
0x1800284fe  jmp     loc_180028759
0x180028503  call    cs:__imp_GetLastError
0x18002850a  nop     dword ptr [rax+rax+00h]
0x18002850f  mov     ecx, eax
0x180028511  mov     r9d, 0ECh
0x180028517  call    ElValidateWin32_19
0x18002851c  xor     r13d, r13d
0x18002851f  mov     ebx, eax
0x180028521  test    eax, eax
0x180028523  jle     short loc_18002852E
0x180028525  movzx   ebx, ax
0x180028528  or      ebx, 80070000h
0x18002852e  mov     rsi, r13
0x180028531  test    ebx, ebx
0x180028533  js      loc_180028759
0x180028539  mov     ebx, 80004005h
0x18002853e  jmp     loc_180028759
0x180028543  call    cs:__imp_GetLastError
0x18002854a  nop     dword ptr [rax+rax+00h]
0x18002854f  mov     edi, eax
0x180028551  cmp     eax, 3F0h
0x180028556  jnz     short loc_1800285AB
0x180028558  call    cs:__imp_GetCurrentProcess
0x18002855f  nop     dword ptr [rax+rax+00h]
0x180028564  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180028568  mov     edx, 20002h; DesiredAccess
0x18002856d  mov     rcx, rax; ProcessHandle
0x180028570  call    cs:__imp_OpenProcessToken
0x180028577  nop     dword ptr [rax+rax+00h]
0x18002857c  test    eax, eax
0x18002857e  jz      short loc_180028588
0x180028580  mov     r14, r13
0x180028583  jmp     loc_1800284BC
0x180028588  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002858d  call    cs:__imp_GetLastError
0x180028594  nop     dword ptr [rax+rax+00h]
0x180028599  mov     ecx, eax
0x18002859b  mov     r9d, 11Eh
0x1800285a1  call    ElValidateWin32_19
0x1800285a6  jmp     loc_18002851F
0x1800285ab  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800285b0  mov     r9d, 12Ch
0x1800285b6  mov     ecx, edi
0x1800285b8  call    ElValidateWin32_19
0x1800285bd  test    eax, eax
0x1800285bf  jz      loc_1800284BC
0x1800285c5  mov     rsi, r13
0x1800285c8  test    edi, edi
0x1800285ca  jg      short loc_1800285D3
0x1800285cc  mov     ebx, edi
0x1800285ce  jmp     loc_180028759
0x1800285d3  movzx   ebx, di
0x1800285d6  or      ebx, 80070000h
0x1800285dc  jmp     loc_180028759
0x1800285e1  call    cs:__imp_GetLastError
0x1800285e8  nop     dword ptr [rax+rax+00h]
0x1800285ed  mov     edi, eax
0x1800285ef  cmp     eax, 7Ah ; 'z'
0x1800285f2  jz      short loc_180028605
0x1800285f4  mov     r9d, 151h
0x1800285fa  mov     ecx, eax
0x1800285fc  call    ElValidateWin32_19
0x180028601  test    eax, eax
0x180028603  jnz     short loc_1800285C5
0x180028605  mov     ecx, [rbp+nLengthNeeded]; unsigned __int64
0x180028608  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002860f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028614  mov     rsi, rax
0x180028617  test    rax, rax
0x18002861a  jz      loc_18002842C
0x180028620  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180028624  lea     rax, [rbp+nLengthNeeded]
0x180028628  mov     rcx, [rbp+TokenHandle]; Handle
0x18002862c  mov     r8, rsi; pSecurityDescriptor
0x18002862f  mov     edx, 4; RequestedInformation
0x180028634  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180028639  call    cs:__imp_GetKernelObjectSecurity
0x180028640  nop     dword ptr [rax+rax+00h]
0x180028645  test    eax, eax
0x180028647  jnz     short loc_18002867A
0x180028649  call    cs:__imp_GetLastError
0x180028650  nop     dword ptr [rax+rax+00h]
0x180028655  mov     r9d, 162h
0x18002865b  mov     ecx, eax
0x18002865d  call    ElValidateWin32_19
0x180028662  mov     ebx, eax
0x180028664  test    eax, eax
0x180028666  jle     loc_180028531
0x18002866c  movzx   ebx, ax
0x18002866f  or      ebx, 80070000h
0x180028675  jmp     loc_180028531
0x18002867a  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18002867e  lea     rax, [rbp+Token]
0x180028682  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180028687  lea     r8, [rbp+TokenAttributes]; lpTokenAttributes
0x18002868b  mov     eax, 2
0x180028690  mov     qword ptr [rbp+TokenAttributes.nLength], 18h
0x180028698  mov     r9d, eax; ImpersonationLevel
0x18002869b  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], r13
0x18002869f  mov     [rbp+TokenAttributes.lpSecurityDescriptor], rsi
0x1800286a3  mov     dword ptr [rsp+60h+lpnLengthNeeded], eax; TokenType
0x1800286a7  lea     edx, [rax+2Ah]; dwDesiredAccess
0x1800286aa  call    cs:__imp_DuplicateTokenEx
0x1800286b1  nop     dword ptr [rax+rax+00h]
0x1800286b6  test    eax, eax
0x1800286b8  jnz     short loc_1800286CE
0x1800286ba  call    cs:__imp_GetLastError
0x1800286c1  nop     dword ptr [rax+rax+00h]
0x1800286c6  mov     r9d, 175h
0x1800286cc  jmp     short loc_18002865B
0x1800286ce  mov     rcx, [rbp+Token]; TokenHandle
0x1800286d2  xor     r9d, r9d; BufferLength
0x1800286d5  mov     [rsp+60h+phNewToken], r13; ReturnLength
0x1800286da  mov     r8, r12; NewState
0x1800286dd  xor     edx, edx; DisableAllPrivileges
0x1800286df  mov     [rsp+60h+lpnLengthNeeded], r13; PreviousState
0x1800286e4  call    cs:__imp_AdjustTokenPrivileges
0x1800286eb  nop     dword ptr [rax+rax+00h]
0x1800286f0  call    cs:__imp_GetLastError
0x1800286f7  nop     dword ptr [rax+rax+00h]
0x1800286fc  mov     edi, eax
0x1800286fe  test    eax, eax
0x180028700  jz      short loc_180028717
0x180028702  mov     r9d, 19Ah
0x180028708  mov     ecx, eax
0x18002870a  call    ElValidateWin32_19
0x18002870f  test    eax, eax
0x180028711  jnz     loc_1800285C8
0x180028717  mov     rdx, [rbp+Token]; Token
0x18002871b  xor     ecx, ecx; Thread
0x18002871d  call    cs:__imp_SetThreadToken
0x180028724  nop     dword ptr [rax+rax+00h]
0x180028729  test    eax, eax
0x18002872b  jnz     short loc_180028744
0x18002872d  call    cs:__imp_GetLastError
0x180028734  nop     dword ptr [rax+rax+00h]
0x180028739  mov     r9d, 1A2h
0x18002873f  jmp     loc_18002865B
0x180028744  cmp     [rbp+TokenHandle], r14
0x180028748  jnz     short loc_18002874F
0x18002874a  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18002874f  mov     [r15], r14
0x180028752  jmp     short loc_180028759
0x180028754  mov     ebx, 80070057h
0x180028759  mov     rcx, [rbp+TokenHandle]; hObject
0x18002875d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028761  cmp     rcx, rdi
0x180028764  jz      short loc_180028776
0x180028766  call    cs:__imp_CloseHandle
0x18002876d  nop     dword ptr [rax+rax+00h]
0x180028772  mov     [rbp+TokenHandle], rdi
0x180028776  mov     rcx, [rbp+Token]; hObject
0x18002877a  cmp     rcx, rdi
0x18002877d  jz      short loc_18002878F
0x18002877f  call    cs:__imp_CloseHandle
0x180028786  nop     dword ptr [rax+rax+00h]
0x18002878b  mov     [rbp+Token], rdi
0x18002878f  test    r12, r12
0x180028792  jz      short loc_18002879C
0x180028794  mov     rcx, r12; lpMem
0x180028797  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002879c  test    rsi, rsi
0x18002879f  jz      short loc_1800287A9
0x1800287a1  mov     rcx, rsi; lpMem
0x1800287a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800287a9  mov     eax, ebx
0x1800287ab  mov     rbx, [rsp+60h+arg_8]
0x1800287b3  add     rsp, 60h
0x1800287b7  pop     r15
0x1800287b9  pop     r14
0x1800287bb  pop     r13
0x1800287bd  pop     r12
0x1800287bf  pop     rdi
0x1800287c0  pop     rsi
0x1800287c1  pop     rbp
0x1800287c2  retn
```
