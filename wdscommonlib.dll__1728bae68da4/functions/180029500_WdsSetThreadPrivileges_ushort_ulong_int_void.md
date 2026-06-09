# WdsSetThreadPrivileges(ushort * *,ulong,int,void * *)

- ea: `0x180029500`
- end: `0x180029932`
- name: `?WdsSetThreadPrivileges@@YAJPEAPEAGKHPEAPEAX@Z`
- size: `1074`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int, int, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000214c`
- `0x180029500`
- `0x180029938`
- `0x180029a2c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800298f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002990b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800298f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002990b`
- `KERNEL32!GetLastError` at `0x180029663`
- `KERNEL32!GetLastError` at `0x1800296a3`
- `KERNEL32!GetLastError` at `0x1800296ed`
- `KERNEL32!GetLastError` at `0x180029741`
- `KERNEL32!GetLastError` at `0x1800297a9`
- `KERNEL32!GetLastError` at `0x18002981a`
- `KERNEL32!GetLastError` at `0x180029850`
- `KERNEL32!GetLastError` at `0x18002988d`
- `KERNEL32!GetLastError` at `0x180029663`
- `KERNEL32!GetLastError` at `0x1800296a3`
- `KERNEL32!GetLastError` at `0x1800296ed`
- `KERNEL32!GetLastError` at `0x180029741`
- `KERNEL32!GetLastError` at `0x1800297a9`
- `KERNEL32!GetLastError` at `0x18002981a`
- `KERNEL32!GetLastError` at `0x180029850`
- `KERNEL32!GetLastError` at `0x18002988d`
- `KERNEL32!CloseHandle` at `0x1800298c6`
- `KERNEL32!CloseHandle` at `0x1800298df`
- `KERNEL32!CloseHandle` at `0x1800298c6`
- `KERNEL32!CloseHandle` at `0x1800298df`
- `KERNEL32!GetCurrentThread` at `0x1800295e6`
- `KERNEL32!GetCurrentThread` at `0x1800295e6`
- `KERNEL32!GetCurrentProcess` at `0x1800296b8`
- `KERNEL32!GetCurrentProcess` at `0x1800296b8`
- `ADVAPI32!OpenProcessToken` at `0x1800296d0`
- `ADVAPI32!OpenProcessToken` at `0x1800296d0`
- `ADVAPI32!OpenThreadToken` at `0x180029601`
- `ADVAPI32!OpenThreadToken` at `0x180029601`
- `ADVAPI32!SetThreadToken` at `0x18002987d`
- `ADVAPI32!SetThreadToken` at `0x18002987d`
- `ADVAPI32!DuplicateTokenEx` at `0x18002980a`
- `ADVAPI32!DuplicateTokenEx` at `0x18002980a`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180029633`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180029799`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180029633`
- `ADVAPI32!GetKernelObjectSecurity` at `0x180029799`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029844`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029844`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800295b3`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800295b3`

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
0x180029500  mov     [rsp-38h+arg_8], rbx
0x180029505  mov     [rsp-38h+arg_18], r9
0x18002950a  mov     [rsp-38h+arg_10], r8d
0x18002950f  push    rbp
0x180029510  push    rsi
0x180029511  push    rdi
0x180029512  push    r12
0x180029514  push    r13
0x180029516  push    r14
0x180029518  push    r15
0x18002951a  mov     rbp, rsp
0x18002951d  sub     rsp, 60h
0x180029521  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029525  xor     ebx, ebx
0x180029527  mov     [rbp+TokenHandle], rax
0x18002952b  mov     r14, rax
0x18002952e  mov     [rbp+Token], rax
0x180029532  xor     esi, esi
0x180029534  xor     eax, eax
0x180029536  xor     r12d, r12d
0x180029539  and     [rbp+nLengthNeeded], eax
0x18002953c  xorps   xmm0, xmm0
0x18002953f  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], rax
0x180029543  mov     r15, r9
0x180029546  mov     edi, edx
0x180029548  mov     r13, rcx
0x18002954b  movups  xmmword ptr [rbp+TokenAttributes.nLength], xmm0
0x18002954f  test    rcx, rcx
0x180029552  jz      loc_1800298B4
0x180029558  test    edx, edx
0x18002955a  jz      loc_1800298B4
0x180029560  test    r9, r9
0x180029563  jz      loc_1800298B4
0x180029569  lea     eax, [rdx+rdx*2]
0x18002956c  lea     eax, ds:4[rax*4]
0x180029573  mov     ecx, eax; unsigned __int64
0x180029575  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002957c  mov     [rbp+nLengthNeeded], eax
0x18002957f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029584  mov     r12, rax
0x180029587  test    rax, rax
0x18002958a  jnz     short loc_180029596
0x18002958c  mov     ebx, 8007000Eh
0x180029591  jmp     loc_1800298B9
0x180029596  mov     [rax], edi
0x180029598  test    edi, edi
0x18002959a  jz      short loc_1800295E6
0x18002959c  lea     r15, [rax+0Ch]
0x1800295a0  mov     rdx, [r13+0]; lpName
0x1800295a4  mov     ecx, esi
0x1800295a6  inc     rcx
0x1800295a9  lea     rcx, [rcx+rsi*2]
0x1800295ad  lea     r8, [r12+rcx*4]; lpLuid
0x1800295b1  xor     ecx, ecx; lpSystemName
0x1800295b3  call    cs:__imp_LookupPrivilegeValueW
0x1800295ba  nop     dword ptr [rax+rax+00h]
0x1800295bf  test    eax, eax
0x1800295c1  jz      loc_180029663
0x1800295c7  mov     eax, [rbp+arg_10]
0x1800295ca  neg     eax
0x1800295cc  sbb     ecx, ecx
0x1800295ce  inc     esi
0x1800295d0  and     ecx, 2
0x1800295d3  add     r13, 8
0x1800295d7  mov     [r15], ecx
0x1800295da  add     r15, 0Ch
0x1800295de  cmp     esi, edi
0x1800295e0  jb      short loc_1800295A0
0x1800295e2  mov     r15, [rbp+arg_18]
0x1800295e6  call    cs:__imp_GetCurrentThread
0x1800295ed  nop     dword ptr [rax+rax+00h]
0x1800295f2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800295f6  xor     r8d, r8d; OpenAsSelf
0x1800295f9  mov     rcx, rax; ThreadHandle
0x1800295fc  mov     edx, 20006h; DesiredAccess
0x180029601  call    cs:__imp_OpenThreadToken
0x180029608  nop     dword ptr [rax+rax+00h]
0x18002960d  xor     r13d, r13d
0x180029610  test    eax, eax
0x180029612  jz      loc_1800296A3
0x180029618  mov     r14, [rbp+TokenHandle]
0x18002961c  mov     rcx, [rbp+TokenHandle]; Handle
0x180029620  lea     rax, [rbp+nLengthNeeded]
0x180029624  xor     r9d, r9d; nLength
0x180029627  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002962c  xor     r8d, r8d; pSecurityDescriptor
0x18002962f  lea     edx, [r9+4]; RequestedInformation
0x180029633  call    cs:__imp_GetKernelObjectSecurity
0x18002963a  nop     dword ptr [rax+rax+00h]
0x18002963f  test    eax, eax
0x180029641  jz      loc_180029741
0x180029647  mov     ebx, 8007000Dh
0x18002964c  mov     ecx, ebx
0x18002964e  call    ElValidateHr_10
0x180029653  test    eax, eax
0x180029655  jns     loc_180029765
0x18002965b  mov     rsi, r13
0x18002965e  jmp     loc_1800298B9
0x180029663  call    cs:__imp_GetLastError
0x18002966a  nop     dword ptr [rax+rax+00h]
0x18002966f  mov     ecx, eax
0x180029671  mov     r9d, 0ECh
0x180029677  call    ElValidateWin32_19
0x18002967c  xor     r13d, r13d
0x18002967f  mov     ebx, eax
0x180029681  test    eax, eax
0x180029683  jle     short loc_18002968E
0x180029685  movzx   ebx, ax
0x180029688  or      ebx, 80070000h
0x18002968e  mov     rsi, r13
0x180029691  test    ebx, ebx
0x180029693  js      loc_1800298B9
0x180029699  mov     ebx, 80004005h
0x18002969e  jmp     loc_1800298B9
0x1800296a3  call    cs:__imp_GetLastError
0x1800296aa  nop     dword ptr [rax+rax+00h]
0x1800296af  mov     edi, eax
0x1800296b1  cmp     eax, 3F0h
0x1800296b6  jnz     short loc_18002970B
0x1800296b8  call    cs:__imp_GetCurrentProcess
0x1800296bf  nop     dword ptr [rax+rax+00h]
0x1800296c4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800296c8  mov     edx, 20002h; DesiredAccess
0x1800296cd  mov     rcx, rax; ProcessHandle
0x1800296d0  call    cs:__imp_OpenProcessToken
0x1800296d7  nop     dword ptr [rax+rax+00h]
0x1800296dc  test    eax, eax
0x1800296de  jz      short loc_1800296E8
0x1800296e0  mov     r14, r13
0x1800296e3  jmp     loc_18002961C
0x1800296e8  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800296ed  call    cs:__imp_GetLastError
0x1800296f4  nop     dword ptr [rax+rax+00h]
0x1800296f9  mov     ecx, eax
0x1800296fb  mov     r9d, 11Eh
0x180029701  call    ElValidateWin32_19
0x180029706  jmp     loc_18002967F
0x18002970b  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180029710  mov     r9d, 12Ch
0x180029716  mov     ecx, edi
0x180029718  call    ElValidateWin32_19
0x18002971d  test    eax, eax
0x18002971f  jz      loc_18002961C
0x180029725  mov     rsi, r13
0x180029728  test    edi, edi
0x18002972a  jg      short loc_180029733
0x18002972c  mov     ebx, edi
0x18002972e  jmp     loc_1800298B9
0x180029733  movzx   ebx, di
0x180029736  or      ebx, 80070000h
0x18002973c  jmp     loc_1800298B9
0x180029741  call    cs:__imp_GetLastError
0x180029748  nop     dword ptr [rax+rax+00h]
0x18002974d  mov     edi, eax
0x18002974f  cmp     eax, 7Ah ; 'z'
0x180029752  jz      short loc_180029765
0x180029754  mov     r9d, 151h
0x18002975a  mov     ecx, eax
0x18002975c  call    ElValidateWin32_19
0x180029761  test    eax, eax
0x180029763  jnz     short loc_180029725
0x180029765  mov     ecx, [rbp+nLengthNeeded]; unsigned __int64
0x180029768  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002976f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029774  mov     rsi, rax
0x180029777  test    rax, rax
0x18002977a  jz      loc_18002958C
0x180029780  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180029784  lea     rax, [rbp+nLengthNeeded]
0x180029788  mov     rcx, [rbp+TokenHandle]; Handle
0x18002978c  mov     r8, rsi; pSecurityDescriptor
0x18002978f  mov     edx, 4; RequestedInformation
0x180029794  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180029799  call    cs:__imp_GetKernelObjectSecurity
0x1800297a0  nop     dword ptr [rax+rax+00h]
0x1800297a5  test    eax, eax
0x1800297a7  jnz     short loc_1800297DA
0x1800297a9  call    cs:__imp_GetLastError
0x1800297b0  nop     dword ptr [rax+rax+00h]
0x1800297b5  mov     r9d, 162h
0x1800297bb  mov     ecx, eax
0x1800297bd  call    ElValidateWin32_19
0x1800297c2  mov     ebx, eax
0x1800297c4  test    eax, eax
0x1800297c6  jle     loc_180029691
0x1800297cc  movzx   ebx, ax
0x1800297cf  or      ebx, 80070000h
0x1800297d5  jmp     loc_180029691
0x1800297da  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1800297de  lea     rax, [rbp+Token]
0x1800297e2  mov     [rsp+60h+phNewToken], rax; phNewToken
0x1800297e7  lea     r8, [rbp+TokenAttributes]; lpTokenAttributes
0x1800297eb  mov     eax, 2
0x1800297f0  mov     qword ptr [rbp+TokenAttributes.nLength], 18h
0x1800297f8  mov     r9d, eax; ImpersonationLevel
0x1800297fb  mov     qword ptr [rbp+TokenAttributes.bInheritHandle], r13
0x1800297ff  mov     [rbp+TokenAttributes.lpSecurityDescriptor], rsi
0x180029803  mov     dword ptr [rsp+60h+lpnLengthNeeded], eax; TokenType
0x180029807  lea     edx, [rax+2Ah]; dwDesiredAccess
0x18002980a  call    cs:__imp_DuplicateTokenEx
0x180029811  nop     dword ptr [rax+rax+00h]
0x180029816  test    eax, eax
0x180029818  jnz     short loc_18002982E
0x18002981a  call    cs:__imp_GetLastError
0x180029821  nop     dword ptr [rax+rax+00h]
0x180029826  mov     r9d, 175h
0x18002982c  jmp     short loc_1800297BB
0x18002982e  mov     rcx, [rbp+Token]; TokenHandle
0x180029832  xor     r9d, r9d; BufferLength
0x180029835  mov     [rsp+60h+phNewToken], r13; ReturnLength
0x18002983a  mov     r8, r12; NewState
0x18002983d  xor     edx, edx; DisableAllPrivileges
0x18002983f  mov     [rsp+60h+lpnLengthNeeded], r13; PreviousState
0x180029844  call    cs:__imp_AdjustTokenPrivileges
0x18002984b  nop     dword ptr [rax+rax+00h]
0x180029850  call    cs:__imp_GetLastError
0x180029857  nop     dword ptr [rax+rax+00h]
0x18002985c  mov     edi, eax
0x18002985e  test    eax, eax
0x180029860  jz      short loc_180029877
0x180029862  mov     r9d, 19Ah
0x180029868  mov     ecx, eax
0x18002986a  call    ElValidateWin32_19
0x18002986f  test    eax, eax
0x180029871  jnz     loc_180029728
0x180029877  mov     rdx, [rbp+Token]; Token
0x18002987b  xor     ecx, ecx; Thread
0x18002987d  call    cs:__imp_SetThreadToken
0x180029884  nop     dword ptr [rax+rax+00h]
0x180029889  test    eax, eax
0x18002988b  jnz     short loc_1800298A4
0x18002988d  call    cs:__imp_GetLastError
0x180029894  nop     dword ptr [rax+rax+00h]
0x180029899  mov     r9d, 1A2h
0x18002989f  jmp     loc_1800297BB
0x1800298a4  cmp     [rbp+TokenHandle], r14
0x1800298a8  jnz     short loc_1800298AF
0x1800298aa  or      [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800298af  mov     [r15], r14
0x1800298b2  jmp     short loc_1800298B9
0x1800298b4  mov     ebx, 80070057h
0x1800298b9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800298bd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800298c1  cmp     rcx, rdi
0x1800298c4  jz      short loc_1800298D6
0x1800298c6  call    cs:__imp_CloseHandle
0x1800298cd  nop     dword ptr [rax+rax+00h]
0x1800298d2  mov     [rbp+TokenHandle], rdi
0x1800298d6  mov     rcx, [rbp+Token]; hObject
0x1800298da  cmp     rcx, rdi
0x1800298dd  jz      short loc_1800298EF
0x1800298df  call    cs:__imp_CloseHandle
0x1800298e6  nop     dword ptr [rax+rax+00h]
0x1800298eb  mov     [rbp+Token], rdi
0x1800298ef  test    r12, r12
0x1800298f2  jz      short loc_180029903
0x1800298f4  mov     rcx, r12
0x1800298f7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800298fe  nop     dword ptr [rax+rax+00h]
0x180029903  test    rsi, rsi
0x180029906  jz      short loc_180029917
0x180029908  mov     rcx, rsi
0x18002990b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029912  nop     dword ptr [rax+rax+00h]
0x180029917  mov     eax, ebx
0x180029919  mov     rbx, [rsp+60h+arg_8]
0x180029921  add     rsp, 60h
0x180029925  pop     r15
0x180029927  pop     r14
0x180029929  pop     r13
0x18002992b  pop     r12
0x18002992d  pop     rdi
0x18002992e  pop     rsi
0x18002992f  pop     rbp
0x180029930  retn
```
