# CSdController::_VerifyDeviceWithCreds(ushort const *,void *,_SID *,_SD_STORAGE_DEVICE_PROP *,ulong *)

- ea: `0x18001445c`
- end: `0x1800147f4`
- name: `?_VerifyDeviceWithCreds@CSdController@@CAJPEBGPEAXPEAU_SID@@PEAU_SD_STORAGE_DEVICE_PROP@@PEAK@Z`
- size: `920`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HANDLE hToken, struct _SID *, struct _SD_STORAGE_DEVICE_PROP *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800101c0`
- `0x180011760`

## callees

- `0x18001445c`
- `0x1800148dc`
- `0x1800150f4`
- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x18001c58c`
- `0x18002170a`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014550`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014546`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014546`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014792`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180014792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001452e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001452e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800147aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001477b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001477b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001457f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001457f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800145ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800145ce`

## string_xrefs

- `0x18001463b`: `spCommon->QueryStorageDevice( pwszDevice, &StorageDeviceProp )`

## pseudocode

```c
__int64 __fastcall CSdController::_VerifyDeviceWithCreds(
        const unsigned __int16 *a1,
        HANDLE hToken,
        struct _SID *a3,
        struct _SD_STORAGE_DEVICE_PROP *a4,
        unsigned int *a5)
{
  int v9; // r12d
  __int64 v10; // rcx
  struct _SD_STORAGE_DEVICE_PROP *v11; // rax
  __int16 v12; // ax
  unsigned int *v13; // r15
  HANDLE CurrentThread; // rax
  int v15; // eax
  __int16 v16; // cx
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  unsigned int v25; // ebx
  HRESULT LastFailureAsHRESULT; // [rsp+30h] [rbp-B1h] BYREF
  __int16 v28; // [rsp+34h] [rbp-ADh]
  __int16 v29; // [rsp+36h] [rbp-ABh]
  LPVOID ppv; // [rsp+68h] [rbp-79h] BYREF
  _OWORD v31[3]; // [rsp+70h] [rbp-71h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-41h]
  __int128 v33; // [rsp+B0h] [rbp-31h]
  __int128 v34; // [rsp+C0h] [rbp-21h]
  __int128 v35; // [rsp+D0h] [rbp-11h]
  __int128 v36; // [rsp+E0h] [rbp-1h]
  __int128 v37; // [rsp+F0h] [rbp+Fh]
  unsigned int v38; // [rsp+140h] [rbp+5Fh] BYREF
  void *TokenHandle; // [rsp+158h] [rbp+77h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdController::_VerifyDeviceWithCreds",
    0xC3u,
    1u);
  ppv = 0;
  TokenHandle = 0;
  v9 = 0;
  memset_0(v31, 0, 0x90u);
  v38 = 0;
  if ( a4 )
  {
    v10 = 144;
    v11 = a4;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (struct _SD_STORAGE_DEVICE_PROP *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
  }
  v12 = 205;
  if ( !a1 )
    goto LABEL_5;
  v28 = 205;
  v12 = 206;
  if ( !a4 )
    goto LABEL_5;
  v13 = a5;
  v28 = 206;
  v12 = 207;
  if ( !a5 )
    goto LABEL_5;
  LastFailureAsHRESULT = 0;
  v28 = 207;
  if ( hToken )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) && GetLastError() != 1008 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v12 = 213;
      goto LABEL_6;
    }
    LastFailureAsHRESULT = 0;
    v28 = 213;
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v12 = 216;
      goto LABEL_6;
    }
    LastFailureAsHRESULT = 0;
    v28 = 216;
    v9 = 1;
  }
  LastFailureAsHRESULT = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdCommon2, &ppv);
  v12 = 221;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v28 = 221;
  v15 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _OWORD *))(*(_QWORD *)ppv + 104LL))(ppv, a1, v31);
  LastFailureAsHRESULT = v15;
  if ( v15 >= 0 )
  {
    v28 = 224;
    v16 = 227;
    if ( !DWORD2(v32)
      || (v28 = 227, v16 = 228, DWORD2(v32) == 1)
      || (v28 = 228, v16 = 229, DWORD2(v32) == 4)
      || (v28 = 229, v16 = 230, DWORD2(v32) == 5) )
    {
      LastFailureAsHRESULT = -2147024809;
      v29 = v16;
      goto LABEL_33;
    }
    v28 = 230;
    if ( DWORD2(v32) == 7 )
    {
      v12 = 234;
      if ( hToken )
      {
        LastFailureAsHRESULT = 0;
        v28 = 234;
        LastFailureAsHRESULT = CSdController::_VerifyUncDeviceAccess(a1, a3, &v38);
        v12 = 238;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_6;
        goto LABEL_32;
      }
    }
    else
    {
      v12 = 243;
      if ( !hToken )
      {
        LastFailureAsHRESULT = 0;
LABEL_32:
        v17 = v31[1];
        *(_OWORD *)a4 = v31[0];
        v28 = v12;
        v18 = v31[2];
        *v13 |= v38;
        *((_OWORD *)a4 + 1) = v17;
        v19 = v32;
        *((_OWORD *)a4 + 2) = v18;
        v20 = v33;
        *((_OWORD *)a4 + 3) = v19;
        v21 = v34;
        *((_OWORD *)a4 + 4) = v20;
        v22 = v35;
        *((_OWORD *)a4 + 5) = v21;
        v23 = v36;
        *((_OWORD *)a4 + 6) = v22;
        v24 = v37;
        *((_OWORD *)a4 + 7) = v23;
        *((_OWORD *)a4 + 8) = v24;
        memset_0(v31, 0, 0x90u);
        goto LABEL_33;
      }
    }
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
LABEL_6:
    v29 = v12;
    goto LABEL_33;
  }
  v29 = 224;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids,
      (unsigned int)"spCommon->QueryStorageDevice( pwszDevice, &StorageDeviceProp )",
      (__int64)a1,
      v15);
LABEL_33:
  CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)v31);
  if ( v9 )
    RevertToSelf();
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    v25 = LastFailureAsHRESULT;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
  }
  else
  {
    v25 = LastFailureAsHRESULT;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v25;
}

```

## disassembly

```asm
0x18001445c  mov     [rsp-8+arg_8], rbx
0x180014461  push    rbp
0x180014462  push    rsi
0x180014463  push    rdi
0x180014464  push    r12
0x180014466  push    r13
0x180014468  push    r14
0x18001446a  push    r15
0x18001446c  lea     rbp, [rsp-1Fh]
0x180014471  sub     rsp, 100h
0x180014478  mov     rdi, r9
0x18001447b  mov     r13, r8
0x18001447e  mov     rsi, rdx
0x180014481  mov     r14, rcx
0x180014484  mov     r9d, 1; unsigned __int16
0x18001448a  lea     rdx, aCsdcontrollerV_3; "CSdController::_VerifyDeviceWithCreds"
0x180014491  mov     r8d, 0C3h; unsigned __int16
0x180014497  lea     rcx, [rsp+130h+var_100]; this
0x18001449c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800144a1  xor     r15d, r15d
0x1800144a4  lea     rcx, [rbp+4Fh+var_C0]; void *
0x1800144a8  xor     edx, edx; Val
0x1800144aa  mov     [rbp+4Fh+var_C8], r15
0x1800144ae  mov     r8d, 90h; Size
0x1800144b4  mov     [rbp+4Fh+TokenHandle], r15
0x1800144b8  mov     r12d, r15d
0x1800144bb  call    memset_0
0x1800144c0  mov     [rbp+4Fh+arg_0], r15d
0x1800144c4  test    rdi, rdi
0x1800144c7  jz      short loc_1800144DD
0x1800144c9  mov     ecx, 90h
0x1800144ce  mov     rax, rdi
0x1800144d1  mov     [rax], r15b
0x1800144d4  inc     rax
0x1800144d7  sub     rcx, 1
0x1800144db  jnz     short loc_1800144D1
0x1800144dd  mov     eax, 0CDh
0x1800144e2  test    r14, r14
0x1800144e5  jnz     short loc_1800144F9
0x1800144e7  mov     [rsp+130h+var_100], 80070057h
0x1800144ef  mov     [rsp+130h+var_FA], ax
0x1800144f4  jmp     loc_18001476D
0x1800144f9  mov     [rsp+130h+var_FC], ax
0x1800144fe  mov     eax, 0CEh
0x180014503  test    rdi, rdi
0x180014506  jz      short loc_1800144E7
0x180014508  mov     r15, [rbp+4Fh+arg_20]
0x18001450c  mov     [rsp+130h+var_FC], ax
0x180014511  mov     eax, 0CFh
0x180014516  test    r15, r15
0x180014519  jz      short loc_1800144E7
0x18001451b  mov     [rsp+130h+var_100], r12d
0x180014520  mov     [rsp+130h+var_FC], ax
0x180014525  test    rsi, rsi
0x180014528  jz      loc_1800145B1
0x18001452e  call    cs:__imp_GetCurrentThread
0x180014534  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x180014538  mov     edx, 2000Ch; DesiredAccess
0x18001453d  mov     rcx, rax; ThreadHandle
0x180014540  mov     r8d, 1; OpenAsSelf
0x180014546  call    cs:__imp_OpenThreadToken
0x18001454c  test    eax, eax
0x18001454e  jnz     short loc_18001456D
0x180014550  call    cs:__imp_GetLastError
0x180014556  cmp     eax, 3F0h
0x18001455b  jz      short loc_18001456D
0x18001455d  call    GetLastFailureAsHRESULT
0x180014562  mov     [rsp+130h+var_100], eax
0x180014566  mov     eax, 0D5h
0x18001456b  jmp     short loc_1800144EF
0x18001456d  mov     eax, 0D5h
0x180014572  mov     [rsp+130h+var_100], r12d
0x180014577  mov     rcx, rsi; hToken
0x18001457a  mov     [rsp+130h+var_FC], ax
0x18001457f  call    cs:__imp_ImpersonateLoggedOnUser
0x180014585  test    eax, eax
0x180014587  jnz     short loc_18001459C
0x180014589  call    GetLastFailureAsHRESULT
0x18001458e  mov     [rsp+130h+var_100], eax
0x180014592  mov     eax, 0D8h
0x180014597  jmp     loc_1800144EF
0x18001459c  mov     eax, 0D8h
0x1800145a1  mov     [rsp+130h+var_100], r12d
0x1800145a6  mov     [rsp+130h+var_FC], ax
0x1800145ab  mov     r12d, 1
0x1800145b1  xor     edx, edx; pUnkOuter
0x1800145b3  lea     rax, [rbp+4Fh+var_C8]
0x1800145b7  lea     r9, IID_ISdCommon2; riid
0x1800145be  mov     [rsp+130h+ppv], rax; ppv
0x1800145c3  lea     rcx, CLSID_SdEngine2; rclsid
0x1800145ca  lea     r8d, [rdx+1]; dwClsContext
0x1800145ce  call    cs:__imp_CoCreateInstance
0x1800145d4  mov     [rsp+130h+var_100], eax
0x1800145d8  test    eax, eax
0x1800145da  mov     eax, 0DDh
0x1800145df  js      loc_1800144EF
0x1800145e5  mov     rcx, [rbp+4Fh+var_C8]
0x1800145e9  lea     r8, [rbp+4Fh+var_C0]
0x1800145ed  mov     [rsp+130h+var_FC], ax
0x1800145f2  mov     rdx, r14
0x1800145f5  mov     rax, [rcx]
0x1800145f8  mov     rax, [rax+68h]
0x1800145fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014601  mov     [rsp+130h+var_100], eax
0x180014605  mov     ecx, 0E0h
0x18001460a  test    eax, eax
0x18001460c  jns     short loc_180014661
0x18001460e  mov     [rsp+130h+var_FA], cx
0x180014613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461a  lea     rdx, WPP_GLOBAL_Control
0x180014621  cmp     rcx, rdx
0x180014624  jz      loc_18001476D
0x18001462a  test    dword ptr [rcx+1Ch], 2000000h
0x180014631  jz      loc_18001476D
0x180014637  mov     rcx, [rcx+10h]
0x18001463b  lea     r9, aSpcommonQuerys; "spCommon->QueryStorageDevice( pwszDevic"...
0x180014642  mov     [rsp+130h+var_108], eax
0x180014646  lea     r8, WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids
0x18001464d  mov     edx, 0Ah
0x180014652  mov     [rsp+130h+ppv], r14
0x180014657  call    WPP_SF_sSd
0x18001465c  jmp     loc_18001476D
0x180014661  mov     eax, [rbp+4Fh+var_88]
0x180014664  mov     [rsp+130h+var_FC], cx
0x180014669  mov     ecx, 0E3h
0x18001466e  test    eax, eax
0x180014670  jnz     short loc_180014684
0x180014672  mov     [rsp+130h+var_100], 80070057h
0x18001467a  mov     [rsp+130h+var_FA], cx
0x18001467f  jmp     loc_18001476D
0x180014684  mov     [rsp+130h+var_FC], cx
0x180014689  mov     ecx, 0E4h
0x18001468e  cmp     eax, 1
0x180014691  jz      short loc_180014672
0x180014693  mov     [rsp+130h+var_FC], cx
0x180014698  mov     ecx, 0E5h
0x18001469d  cmp     eax, 4
0x1800146a0  jz      short loc_180014672
0x1800146a2  mov     [rsp+130h+var_FC], cx
0x1800146a7  mov     ecx, 0E6h
0x1800146ac  cmp     eax, 5
0x1800146af  jz      short loc_180014672
0x1800146b1  mov     [rsp+130h+var_FC], cx
0x1800146b6  cmp     eax, 7
0x1800146b9  jnz     short loc_1800146F5
0x1800146bb  lea     eax, [rcx+4]
0x1800146be  test    rsi, rsi
0x1800146c1  jz      loc_1800144E7
0x1800146c7  lea     r8, [rbp+4Fh+arg_0]; unsigned int *
0x1800146cb  mov     [rsp+130h+var_100], 0
0x1800146d3  mov     rdx, r13; struct _SID *
0x1800146d6  mov     [rsp+130h+var_FC], ax
0x1800146db  mov     rcx, r14; unsigned __int16 *
0x1800146de  call    ?_VerifyUncDeviceAccess@CSdController@@CAJPEBGPEAU_SID@@PEAK@Z; CSdController::_VerifyUncDeviceAccess(ushort const *,_SID *,ulong *)
0x1800146e3  mov     [rsp+130h+var_100], eax
0x1800146e7  test    eax, eax
0x1800146e9  mov     eax, 0EEh
0x1800146ee  jns     short loc_180014707
0x1800146f0  jmp     loc_1800144EF
0x1800146f5  mov     eax, 0F3h
0x1800146fa  test    rsi, rsi
0x1800146fd  jnz     loc_1800144E7
0x180014703  mov     [rsp+130h+var_100], esi
0x180014707  movaps  xmm0, [rbp+4Fh+var_C0]
0x18001470b  lea     rcx, [rbp+4Fh+var_C0]; void *
0x18001470f  movaps  xmm1, [rbp+4Fh+var_B0]
0x180014713  xor     edx, edx; Val
0x180014715  movups  xmmword ptr [rdi], xmm0
0x180014718  mov     r8d, 90h; Size
0x18001471e  mov     [rsp+130h+var_FC], ax
0x180014723  movaps  xmm0, [rbp+4Fh+var_A0]
0x180014727  mov     eax, [rbp+4Fh+arg_0]
0x18001472a  or      [r15], eax
0x18001472d  movups  xmmword ptr [rdi+10h], xmm1
0x180014731  movaps  xmm1, xmmword ptr [rbp-41h]
0x180014735  movups  xmmword ptr [rdi+20h], xmm0
0x180014739  movaps  xmm0, [rbp+4Fh+var_80]
0x18001473d  movups  xmmword ptr [rdi+30h], xmm1
0x180014741  movaps  xmm1, [rbp+4Fh+var_70]
0x180014745  movups  xmmword ptr [rdi+40h], xmm0
0x180014749  movaps  xmm0, [rbp+4Fh+var_60]
0x18001474d  movups  xmmword ptr [rdi+50h], xmm1
0x180014751  movaps  xmm1, [rbp+4Fh+var_50]
0x180014755  movups  xmmword ptr [rdi+60h], xmm0
0x180014759  movaps  xmm0, [rbp+4Fh+var_40]
0x18001475d  movups  xmmword ptr [rdi+70h], xmm1
0x180014761  movups  xmmword ptr [rdi+80h], xmm0
0x180014768  call    memset_0
0x18001476d  lea     rcx, [rbp+4Fh+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x180014771  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180014776  test    r12d, r12d
0x180014779  jz      short loc_180014781
0x18001477b  call    cs:__imp_RevertToSelf
0x180014781  mov     rdx, [rbp+4Fh+TokenHandle]; Token
0x180014785  test    rdx, rdx
0x180014788  jnz     short loc_180014790
0x18001478a  mov     ebx, [rsp+130h+var_100]
0x18001478e  jmp     short loc_1800147B8
0x180014790  xor     ecx, ecx; Thread
0x180014792  call    cs:__imp_SetThreadToken
0x180014798  mov     rcx, [rbp+4Fh+TokenHandle]; hObject
0x18001479c  mov     ebx, [rsp+130h+var_100]
0x1800147a0  lea     rax, [rcx-1]
0x1800147a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800147a8  ja      short loc_1800147B8
0x1800147aa  call    cs:__imp_CloseHandle
0x1800147b0  mov     [rbp+4Fh+TokenHandle], 0
0x1800147b8  mov     rcx, [rbp+4Fh+var_C8]
0x1800147bc  test    rcx, rcx
0x1800147bf  jz      short loc_1800147CD
0x1800147c1  mov     rdx, [rcx]
0x1800147c4  mov     rax, [rdx+10h]
0x1800147c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147cd  lea     rcx, [rsp+130h+var_100]; this
0x1800147d2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800147d7  mov     eax, ebx
0x1800147d9  mov     rbx, [rsp+130h+arg_8]
0x1800147e1  add     rsp, 100h
0x1800147e8  pop     r15
0x1800147ea  pop     r14
0x1800147ec  pop     r13
0x1800147ee  pop     r12
0x1800147f0  pop     rdi
0x1800147f1  pop     rsi
0x1800147f2  pop     rbp
0x1800147f3  retn
```
