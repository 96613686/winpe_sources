# LogonIdFromWinStationNameW

- ea: `0x180020380`
- end: `0x18002068f`
- name: `LogonIdFromWinStationNameW`
- size: `783`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180009ba4`
- `0x180009c10`
- `0x180009c94`
- `0x18000e880`
- `0x180020380`
- `0x18002bdd8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800204c7`
- `msvcrt!_wcsicmp` at `0x1800205c9`
- `msvcrt!_wcsicmp` at `0x1800204c7`
- `msvcrt!_wcsicmp` at `0x1800205c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002062d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020655`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002062d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800205ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020665`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800205ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020665`

## string_xrefs

- `0x1800203d8`: `Failed to open binding`
- `0x180020434`: `Enum->Open failed: 0x%x in %s`

## pseudocode

```c
char __fastcall LogonIdFromWinStationNameW(CPublicBinding *this, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned __int16 *v4; // rsi
  void *v6; // rax
  int EnumResult; // edi
  DWORD v8; // eax
  unsigned int i; // r15d
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r15
  DWORD v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v16; // [rsp+24h] [rbp-74h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-70h] BYREF
  int v18; // [rsp+30h] [rbp-68h]
  HLOCAL v19; // [rsp+38h] [rbp-60h] BYREF
  int v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 v22[8]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int16 v23[28]; // [rsp+60h] [rbp-38h] BYREF
  int v25; // [rsp+B8h] [rbp+20h]

  v4 = a2;
  v19 = 0;
  v15 = 0;
  v21 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v23, this, 0);
  if ( !CSmartPublicBinding::operator void *(v23) )
  {
    LOBYTE(v4) = 0;
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_30;
  }
  v6 = (void *)CSmartPublicBinding::operator void *(v23);
  EnumResult = CEnum::Open((CEnum *)&v21, v6);
  if ( EnumResult == -2147023174 )
  {
    LOBYTE(v4) = Legacy_LogonIdFromWinStationNameW(this, v4, a3);
    if ( !(_BYTE)v4 )
      GetLastError();
    goto LABEL_30;
  }
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", (unsigned int)EnumResult, "LogonIdFromWinStationNameW");
LABEL_8:
    v8 = ConvertHRESULT2WIN32(EnumResult);
    SetLastError(v8);
    LOBYTE(v4) = 0;
    goto LABEL_30;
  }
  EnumResult = CEnum::GetEnumResult((CEnum *)&v21, 1, (struct _SESSIONENUM **)&v19, &v15);
  v25 = EnumResult;
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "GetEnumResult failed: 0x%x in %s", (unsigned int)EnumResult, "LogonIdFromWinStationNameW");
    goto LABEL_8;
  }
  LODWORD(v4) = 0;
  v18 = 0;
  for ( i = 0; i < v15; ++i )
  {
    hMem = (HLOCAL)(104LL * i);
    if ( !_wcsicmp(a2, (const wchar_t *)((char *)v19 + (_QWORD)hMem + 12)) )
    {
      LODWORD(v4) = 1;
      v18 = 1;
      *a3 = *(_DWORD *)((char *)v19 + (_QWORD)hMem + 4);
    }
  }
  if ( !(_DWORD)v4 )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, this, 1);
    hMem = 0;
    v16 = 0;
    if ( CSmartPublicBinding::operator void *(v22) )
    {
      v10 = CSmartPublicBinding::operator void *(v22);
      EnumResult = RpcGetAllListeners(v10, &hMem, v11, &v16);
      v25 = EnumResult;
      v20 = EnumResult;
    }
    if ( EnumResult >= 0 )
    {
      v12 = 0;
      if ( v16 )
      {
        do
        {
          if ( !_wcsicmp(a2, (const wchar_t *)hMem + 40 * v12 + 6) )
          {
            LODWORD(v4) = 1;
            *a3 = *((_DWORD *)hMem + 20 * v12 + 1);
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < v16 );
        EnumResult = v25;
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( EnumResult >= 0 )
    {
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
      if ( !(_DWORD)v4 )
        SetLastError(0x1B6Eu);
    }
    else
    {
      _DbgPrintMessage(8, "RpcGetAllListeners failed: 0x%x in %s", EnumResult, "LogonIdFromWinStationNameW");
      v13 = ConvertHRESULT2WIN32(EnumResult);
      SetLastError(v13);
      LOBYTE(v4) = 0;
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
    }
  }
LABEL_30:
  if ( v19 )
    LocalFree(v19);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v23);
  CEnum::~CEnum((CEnum *)&v21);
  return (char)v4;
}

```

## disassembly

```asm
0x180020380  mov     rax, rsp
0x180020383  mov     [rax+18h], r8
0x180020387  mov     [rax+10h], rdx
0x18002038b  push    rsi
0x18002038c  push    rdi
0x18002038d  push    r12
0x18002038f  push    r13
0x180020391  push    r15
0x180020393  sub     rsp, 70h
0x180020397  mov     r13, r8
0x18002039a  mov     rsi, rdx
0x18002039d  mov     r12, rcx
0x1800203a0  mov     qword ptr [rax-60h], 0
0x1800203a8  mov     dword ptr [rax-78h], 0
0x1800203af  mov     qword ptr [rax-50h], 0
0x1800203b7  xor     r8d, r8d; int
0x1800203ba  mov     rdx, rcx; void *
0x1800203bd  lea     rcx, [rax-38h]; this
0x1800203c1  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800203c6  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800203cb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800203d0  test    rax, rax
0x1800203d3  jnz     short loc_1800203EC
0x1800203d5  xor     sil, sil
0x1800203d8  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800203df  lea     ecx, [rax+8]; int
0x1800203e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800203e7  jmp     loc_18002065B
0x1800203ec  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800203f1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800203f6  mov     rdx, rax; void *
0x1800203f9  lea     rcx, [rsp+98h+var_50]; this
0x1800203fe  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x180020403  mov     edi, eax
0x180020405  cmp     eax, 800706BAh
0x18002040a  jnz     short loc_180020430
0x18002040c  mov     r8, r13; unsigned int *
0x18002040f  mov     rdx, rsi; unsigned __int16 *
0x180020412  mov     rcx, r12; this
0x180020415  call    ?Legacy_LogonIdFromWinStationNameW@@YAEPEAXPEAGPEAK@Z; Legacy_LogonIdFromWinStationNameW(void *,ushort *,ulong *)
0x18002041a  mov     sil, al
0x18002041d  test    al, al
0x18002041f  jnz     loc_18002065B
0x180020425  call    cs:__imp_GetLastError
0x18002042b  jmp     loc_18002065B
0x180020430  test    edi, edi
0x180020432  jns     short loc_180020466
0x180020434  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x18002043b  mov     r8d, edi
0x18002043e  lea     r9, aLogonidfromwin_2; "LogonIdFromWinStationNameW"
0x180020445  mov     ecx, 8; int
0x18002044a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002044f  mov     ecx, edi; int
0x180020451  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180020456  mov     ecx, eax; dwErrCode
0x180020458  call    cs:__imp_SetLastError
0x18002045e  xor     sil, sil
0x180020461  jmp     loc_18002065B
0x180020466  lea     r9, [rsp+98h+var_78]; unsigned int *
0x18002046b  lea     r8, [rsp+98h+var_60]; struct _SESSIONENUM **
0x180020470  mov     edx, 1; unsigned int
0x180020475  lea     rcx, [rsp+98h+var_50]; this
0x18002047a  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x18002047f  mov     edi, eax
0x180020481  mov     [rsp+98h+arg_18], eax
0x180020488  test    eax, eax
0x18002048a  jns     short loc_180020495
0x18002048c  lea     rdx, aGetenumresultF; "GetEnumResult failed: 0x%x in %s"
0x180020493  jmp     short loc_18002043B
0x180020495  xor     esi, esi
0x180020497  mov     [rsp+98h+var_68], esi
0x18002049b  xor     r15d, r15d
0x18002049e  cmp     [rsp+98h+var_78], esi
0x1800204a2  jbe     short loc_1800204FB
0x1800204a4  mov     rdi, [rsp+98h+String1]
0x1800204ac  mov     eax, r15d
0x1800204af  imul    rcx, rax, 68h ; 'h'
0x1800204b3  mov     [rsp+98h+hMem], rcx
0x1800204b8  mov     rdx, [rsp+98h+var_60]
0x1800204bd  add     rdx, 0Ch
0x1800204c1  add     rdx, rcx; String2
0x1800204c4  mov     rcx, rdi; String1
0x1800204c7  call    cs:__imp__wcsicmp
0x1800204cd  test    eax, eax
0x1800204cf  jnz     short loc_1800204EA
0x1800204d1  lea     esi, [rax+1]
0x1800204d4  mov     [rsp+98h+var_68], esi
0x1800204d8  mov     rax, [rsp+98h+var_60]
0x1800204dd  mov     rcx, [rsp+98h+hMem]
0x1800204e2  mov     ecx, [rcx+rax+4]
0x1800204e6  mov     [r13+0], ecx
0x1800204ea  inc     r15d
0x1800204ed  cmp     r15d, [rsp+98h+var_78]
0x1800204f2  jb      short loc_1800204AC
0x1800204f4  mov     edi, [rsp+98h+arg_18]
0x1800204fb  test    esi, esi
0x1800204fd  jnz     loc_18002065B
0x180020503  lea     r8d, [rsi+1]; int
0x180020507  mov     rdx, r12; void *
0x18002050a  lea     rcx, [rsp+98h+var_48]; this
0x18002050f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180020514  mov     [rsp+98h+hMem], 0
0x18002051d  mov     [rsp+98h+var_74], esi
0x180020521  lea     rcx, [rsp+98h+var_48]; unsigned __int16 *
0x180020526  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002052b  test    rax, rax
0x18002052e  jz      short loc_18002059C
0x180020530  lea     rcx, [rsp+98h+var_48]; unsigned __int16 *
0x180020535  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002053a  mov     rcx, rax
0x18002053d  lea     r9, [rsp+98h+var_74]
0x180020542  lea     rdx, [rsp+98h+hMem]
0x180020547  call    RpcGetAllListeners
0x18002054c  mov     edi, eax
0x18002054e  mov     [rsp+98h+arg_18], eax
0x180020555  mov     [rsp+98h+var_58], eax
0x180020559  jmp     short loc_18002059C
0x18002055b  mov     edi, eax
0x18002055d  mov     [rsp+98h+arg_18], eax
0x180020564  test    eax, eax
0x180020566  jle     short loc_180020578
0x180020568  movzx   edi, ax
0x18002056b  or      edi, 80070000h
0x180020571  mov     [rsp+98h+arg_18], edi
0x180020578  mov     [rsp+98h+var_58], edi
0x18002057c  mov     r8d, edi
0x18002057f  lea     rdx, aRpcgetallliste_0; "RpcGetAllListeners threw an exception: "...
0x180020586  mov     ecx, 8; int
0x18002058b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020590  mov     r13, [rsp+98h+arg_10]
0x180020598  mov     esi, [rsp+98h+var_68]
0x18002059c  test    edi, edi
0x18002059e  js      short loc_1800205F5
0x1800205a0  xor     r15d, r15d
0x1800205a3  cmp     [rsp+98h+var_74], r15d
0x1800205a8  jbe     short loc_1800205F5
0x1800205aa  mov     rdi, [rsp+98h+String1]
0x1800205b2  lea     r12, [r15+r15*4]
0x1800205b6  shl     r12, 4
0x1800205ba  mov     rdx, [rsp+98h+hMem]
0x1800205bf  add     rdx, 0Ch
0x1800205c3  add     rdx, r12; String2
0x1800205c6  mov     rcx, rdi; String1
0x1800205c9  call    cs:__imp__wcsicmp
0x1800205cf  test    eax, eax
0x1800205d1  jnz     short loc_1800205E4
0x1800205d3  lea     esi, [rax+1]
0x1800205d6  mov     rax, [rsp+98h+hMem]
0x1800205db  mov     ecx, [r12+rax+4]
0x1800205e0  mov     [r13+0], ecx
0x1800205e4  inc     r15d
0x1800205e7  cmp     r15d, [rsp+98h+var_74]
0x1800205ec  jb      short loc_1800205B2
0x1800205ee  mov     edi, [rsp+98h+arg_18]
0x1800205f5  mov     rcx, [rsp+98h+hMem]; hMem
0x1800205fa  test    rcx, rcx
0x1800205fd  jz      short loc_180020605
0x1800205ff  call    cs:__imp_LocalFree
0x180020605  test    edi, edi
0x180020607  jns     short loc_180020642
0x180020609  lea     r9, aLogonidfromwin_2; "LogonIdFromWinStationNameW"
0x180020610  mov     r8d, edi
0x180020613  lea     rdx, aRpcgetallliste; "RpcGetAllListeners failed: 0x%x in %s"
0x18002061a  mov     ecx, 8; int
0x18002061f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020624  mov     ecx, edi; int
0x180020626  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002062b  mov     ecx, eax; dwErrCode
0x18002062d  call    cs:__imp_SetLastError
0x180020633  xor     sil, sil
0x180020636  lea     rcx, [rsp+98h+var_48]; this
0x18002063b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180020640  jmp     short loc_18002065B
0x180020642  lea     rcx, [rsp+98h+var_48]; this
0x180020647  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002064c  test    esi, esi
0x18002064e  jnz     short loc_18002065B
0x180020650  mov     ecx, 1B6Eh; dwErrCode
0x180020655  call    cs:__imp_SetLastError
0x18002065b  mov     rcx, [rsp+98h+var_60]; hMem
0x180020660  test    rcx, rcx
0x180020663  jz      short loc_18002066B
0x180020665  call    cs:__imp_LocalFree
0x18002066b  lea     rcx, [rsp+98h+var_38]; this
0x180020670  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180020675  lea     rcx, [rsp+98h+var_50]; this
0x18002067a  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x18002067f  mov     al, sil
0x180020682  add     rsp, 70h
0x180020686  pop     r15
0x180020688  pop     r13
0x18002068a  pop     r12
0x18002068c  pop     rdi
0x18002068d  pop     rsi
0x18002068e  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```
