# CSdController::_LogBackupStatus(CSxFunctionTracer *,_SD_BACKUP_RESULT,int,long,ushort const *)

- ea: `0x180012408`
- end: `0x1800127c9`
- name: `?_LogBackupStatus@CSdController@@AEAAJPEAVCSxFunctionTracer@@W4_SD_BACKUP_RESULT@@HJPEBG@Z`
- size: `961`
- prototype: `__int64 __fastcall(__int64, struct CSxFunctionTracer *, int, int, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180011b84`
- `0x1800122b8`
- `0x180012408`
- `0x1800151b4`
- `0x1800152c0`
- `0x1800153b8`
- `0x1800154d0`
- `0x180015598`
- `0x18001563c`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012493`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012493`

## pseudocode

```c
__int64 __fastcall CSdController::_LogBackupStatus(
        __int64 a1,
        struct CSxFunctionTracer *a2,
        int a3,
        int a4,
        int a5,
        unsigned __int16 *a6)
{
  __int16 v9; // ax
  HRESULT IsStaleBitSet; // ebx
  unsigned int v11; // edx
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  unsigned int v16; // esi
  CSdController *v17; // rcx
  __int64 (__fastcall *v18)(LPVOID, __int64); // rax
  bool v19; // sf
  int v20; // edi
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24; // edi
  __int16 v25; // di
  unsigned __int16 *v26; // rdi
  int v27; // r15d
  CSdController *v28; // rcx
  int v30; // [rsp+30h] [rbp-40h] BYREF
  __int16 v31; // [rsp+34h] [rbp-3Ch]
  __int16 v32; // [rsp+36h] [rbp-3Ah]
  __int64 v33; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+38h] BYREF

  v33 = a1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v30, "CSdController::_LogBackupStatus", 1383, 0);
  v9 = 1389;
  ppv = 0;
  LODWORD(v33) = 0;
  if ( !a2 )
    goto LABEL_2;
  v31 = 1389;
  v30 = 0;
  IsStaleBitSet = CoCreateInstance(&CLSID_CSdWhcNotifier, 0, 1u, &IID_ISdWhcNotifier, &ppv);
  v30 = IsStaleBitSet;
  v9 = 1395;
  if ( IsStaleBitSet < 0 )
    goto LABEL_3;
  v31 = 1395;
  if ( a3 <= 6 )
  {
    if ( a3 == 6 )
      goto LABEL_13;
    if ( !a3 )
    {
      IsStaleBitSet = Log_SD_INFO_BACKUP_SUCCEEDED(a2, v11);
      v30 = IsStaleBitSet;
      v9 = 1400;
      if ( IsStaleBitSet < 0 )
        goto LABEL_3;
      v31 = 1400;
      IsStaleBitSet = CSdController::_IsStaleBitSet(v17, (int *)&v33);
      v30 = IsStaleBitSet;
      v9 = 1402;
      if ( IsStaleBitSet < 0 )
        goto LABEL_3;
      v31 = 1402;
      v18 = *(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL);
      if ( (_DWORD)v33 )
      {
        IsStaleBitSet = v18(ppv, 15);
        v30 = IsStaleBitSet;
        v19 = IsStaleBitSet < 0;
        v9 = 1405;
      }
      else
      {
        IsStaleBitSet = v18(ppv, 5);
        v30 = IsStaleBitSet;
        v19 = IsStaleBitSet < 0;
        v9 = 1413;
      }
      if ( v19 )
        goto LABEL_3;
      v31 = v9;
      v16 = a4 != 0 ? 4 : 0;
LABEL_58:
      if ( !v16 )
        goto LABEL_61;
      goto LABEL_59;
    }
    v12 = a3 - 1;
    if ( !v12 )
      goto LABEL_61;
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
        goto LABEL_61;
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
          goto LABEL_61;
LABEL_13:
        if ( ((a5 + 2130706426) & 0xFFFFFFFD) != 0 )
        {
          if ( a5 == -2130706389 )
          {
            v16 = 18;
          }
          else
          {
            v16 = 3;
            if ( a5 == -2130706387 )
              v16 = 19;
          }
        }
        else
        {
          v16 = 9;
        }
        v25 = 1506;
        v30 = Log_SD_ERROR_BACKUP_FAILED(a2, 0x5E2u, a5);
        IsStaleBitSet = v30;
        if ( v30 >= 0 )
        {
          v31 = 1506;
          goto LABEL_58;
        }
LABEL_36:
        v32 = v25;
        goto LABEL_61;
      }
      IsStaleBitSet = Log_SD_WARNING_BACKUP_CANCELLED(a2, v11);
      v30 = IsStaleBitSet;
      v9 = 1427;
      if ( IsStaleBitSet < 0 )
        goto LABEL_3;
      v16 = 12;
    }
    else
    {
      IsStaleBitSet = Log_SD_INFO_BACKUP_STARTED(a2, v11, a6);
      v30 = IsStaleBitSet;
      v9 = 1464;
      if ( IsStaleBitSet < 0 )
        goto LABEL_3;
      v16 = 11;
    }
    goto LABEL_18;
  }
  v16 = 7;
  v20 = a3 - 7;
  if ( !v20 )
    goto LABEL_13;
  v21 = v20 - 1;
  if ( !v21 )
    goto LABEL_13;
  v22 = v21 - 1;
  if ( !v22 )
  {
    IsStaleBitSet = Log_SD_ERROR_SNAPSHOT_FAILED(a2, v11, a5);
    v30 = IsStaleBitSet;
    v9 = 1432;
    if ( IsStaleBitSet < 0 )
      goto LABEL_3;
    v16 = 3;
LABEL_18:
    v31 = v9;
    goto LABEL_59;
  }
  v23 = v22 - 1;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( v24 )
    {
      if ( v24 != 1 )
        goto LABEL_13;
      v16 = 17;
    }
    else
    {
      v25 = 1482;
      v30 = Log_SD_ERROR_BACKUP_FAILED(a2, 0x5CAu, a5);
      IsStaleBitSet = v30;
      if ( v30 < 0 )
        goto LABEL_36;
      v31 = 1482;
    }
  }
  else
  {
    v26 = a6;
    if ( !a6 || !*a6 )
    {
      v9 = 1436;
LABEL_2:
      IsStaleBitSet = -2147024809;
      v30 = -2147024809;
LABEL_3:
      v32 = v9;
      goto LABEL_61;
    }
    v27 = a5;
    v31 = 1436;
    v30 = 0;
    IsStaleBitSet = Log_SD_ERROR_TARGET_FAILED(a2, v11, a6, a5);
    v30 = IsStaleBitSet;
    v9 = 1437;
    if ( IsStaleBitSet < 0 )
      goto LABEL_3;
    v31 = 1437;
    IsStaleBitSet = CSdController::_FailureIsCredentialsError(v28, v26, v27);
    v30 = IsStaleBitSet;
    v9 = 1442;
    if ( IsStaleBitSet < 0 )
      goto LABEL_3;
    v31 = 1442;
    if ( IsStaleBitSet )
    {
      if ( ((v27 + 2130706426) & 0xFFFFFFFD) != 0 )
      {
        v16 = 3;
        if ( v27 == -2130706389 )
          v16 = 18;
      }
      else
      {
        v16 = 9;
      }
    }
    else
    {
      v16 = 1;
    }
  }
LABEL_59:
  IsStaleBitSet = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, v16);
  v30 = IsStaleBitSet;
  v9 = 1513;
  if ( IsStaleBitSet < 0 )
    goto LABEL_3;
  v31 = 1513;
LABEL_61:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v30);
  return (unsigned int)IsStaleBitSet;
}

```

## disassembly

```asm
0x180012408  mov     [rsp-28h+arg_10], rbx
0x18001240d  mov     [rsp-28h+arg_18], rsi
0x180012412  mov     [rsp-28h+arg_0], rcx
0x180012417  push    rbp
0x180012418  push    rdi
0x180012419  push    r12
0x18001241b  push    r14
0x18001241d  push    r15
0x18001241f  mov     rbp, rsp
0x180012422  sub     rsp, 70h
0x180012426  mov     esi, r9d
0x180012429  lea     rcx, [rbp+var_40]; this
0x18001242d  mov     edi, r8d
0x180012430  mov     r14, rdx
0x180012433  xor     r9d, r9d; unsigned __int16
0x180012436  lea     rdx, aCsdcontrollerL; "CSdController::_LogBackupStatus"
0x18001243d  mov     r8d, 567h; unsigned __int16
0x180012443  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180012448  xor     r12d, r12d
0x18001244b  mov     eax, 56Dh
0x180012450  mov     [rbp+arg_8], r12
0x180012454  mov     dword ptr [rbp+arg_0], r12d
0x180012458  test    r14, r14
0x18001245b  jnz     short loc_18001246E
0x18001245d  mov     ebx, 80070057h
0x180012462  mov     [rbp+var_40], ebx
0x180012465  mov     [rbp+var_3A], ax
0x180012469  jmp     loc_180012790
0x18001246e  xor     edx, edx; pUnkOuter
0x180012470  mov     [rbp+var_3C], ax
0x180012474  lea     rax, [rbp+arg_8]
0x180012478  mov     [rbp+var_40], r12d
0x18001247c  lea     r9, IID_ISdWhcNotifier; riid
0x180012483  mov     [rsp+70h+ppv], rax; ppv
0x180012488  lea     rcx, CLSID_CSdWhcNotifier; rclsid
0x18001248f  lea     r8d, [rdx+1]; dwClsContext
0x180012493  call    cs:__imp_CoCreateInstance
0x180012499  mov     ebx, eax
0x18001249b  mov     [rbp+var_40], eax
0x18001249e  test    eax, eax
0x1800124a0  mov     eax, 573h
0x1800124a5  js      short loc_180012465
0x1800124a7  mov     [rbp+var_3C], ax
0x1800124ab  cmp     edi, 6
0x1800124ae  jg      loc_1800125EF
0x1800124b4  jz      short loc_1800124E3
0x1800124b6  test    edi, edi
0x1800124b8  jz      loc_18001255D
0x1800124be  sub     edi, 1
0x1800124c1  jz      loc_180012790
0x1800124c7  sub     edi, 1
0x1800124ca  jz      short loc_180012538
0x1800124cc  sub     edi, 1
0x1800124cf  jz      loc_180012790
0x1800124d5  sub     edi, 1
0x1800124d8  jz      short loc_180012510
0x1800124da  cmp     edi, 1
0x1800124dd  jz      loc_180012790
0x1800124e3  mov     r8d, [rbp+arg_20]; int
0x1800124e7  lea     eax, [r8+7EFFFFFAh]
0x1800124ee  test    eax, 0FFFFFFFDh
0x1800124f3  jz      loc_18001273F
0x1800124f9  cmp     r8d, 8100002Bh
0x180012500  jnz     loc_18001272B
0x180012506  mov     esi, 12h
0x18001250b  jmp     loc_180012744
0x180012510  mov     rcx, r14; this
0x180012513  call    ?Log_SD_WARNING_BACKUP_CANCELLED@@YAJPEAVCSxFunctionTracer@@K@Z; Log_SD_WARNING_BACKUP_CANCELLED(CSxFunctionTracer *,ulong)
0x180012518  mov     ebx, eax
0x18001251a  mov     [rbp+var_40], eax
0x18001251d  test    eax, eax
0x18001251f  mov     eax, 593h
0x180012524  js      loc_180012465
0x18001252a  mov     esi, 0Ch
0x18001252f  mov     [rbp+var_3C], ax
0x180012533  jmp     loc_180012768
0x180012538  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x18001253c  mov     rcx, r14; this
0x18001253f  call    ?Log_SD_INFO_BACKUP_STARTED@@YAJPEAVCSxFunctionTracer@@KPEBG@Z; Log_SD_INFO_BACKUP_STARTED(CSxFunctionTracer *,ulong,ushort const *)
0x180012544  mov     ebx, eax
0x180012546  mov     [rbp+var_40], eax
0x180012549  test    eax, eax
0x18001254b  mov     eax, 5B8h
0x180012550  js      loc_180012465
0x180012556  mov     esi, 0Bh
0x18001255b  jmp     short loc_18001252F
0x18001255d  mov     rcx, r14; this
0x180012560  call    ?Log_SD_INFO_BACKUP_SUCCEEDED@@YAJPEAVCSxFunctionTracer@@K@Z; Log_SD_INFO_BACKUP_SUCCEEDED(CSxFunctionTracer *,ulong)
0x180012565  mov     ebx, eax
0x180012567  mov     [rbp+var_40], eax
0x18001256a  test    eax, eax
0x18001256c  mov     eax, 578h
0x180012571  js      loc_180012465
0x180012577  lea     rdx, [rbp+arg_0]; int *
0x18001257b  mov     [rbp+var_3C], ax
0x18001257f  call    ?_IsStaleBitSet@CSdController@@AEAAJPEAH@Z; CSdController::_IsStaleBitSet(int *)
0x180012584  mov     ebx, eax
0x180012586  mov     [rbp+var_40], eax
0x180012589  test    eax, eax
0x18001258b  mov     eax, 57Ah
0x180012590  js      loc_180012465
0x180012596  mov     rcx, [rbp+arg_8]
0x18001259a  mov     [rbp+var_3C], ax
0x18001259e  mov     rax, [rcx]
0x1800125a1  mov     rax, [rax+18h]
0x1800125a5  cmp     dword ptr [rbp+arg_0], r12d
0x1800125a9  jz      short loc_1800125D7
0x1800125ab  mov     edx, 0Fh
0x1800125b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b5  mov     ebx, eax
0x1800125b7  mov     [rbp+var_40], eax
0x1800125ba  test    eax, eax
0x1800125bc  mov     eax, 57Dh
0x1800125c1  js      loc_180012465
0x1800125c7  neg     esi
0x1800125c9  mov     [rbp+var_3C], ax
0x1800125cd  sbb     esi, esi
0x1800125cf  and     esi, 4
0x1800125d2  jmp     loc_180012764
0x1800125d7  mov     edx, 5
0x1800125dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125e1  mov     ebx, eax
0x1800125e3  mov     [rbp+var_40], eax
0x1800125e6  test    eax, eax
0x1800125e8  mov     eax, 585h
0x1800125ed  jmp     short loc_1800125C1
0x1800125ef  mov     esi, 7
0x1800125f4  sub     edi, esi
0x1800125f6  jz      loc_1800124E3
0x1800125fc  sub     edi, 1
0x1800125ff  jz      loc_1800124E3
0x180012605  sub     edi, 1
0x180012608  jz      loc_180012703
0x18001260e  sub     edi, 1
0x180012611  jz      short loc_180012657
0x180012613  sub     edi, 1
0x180012616  jz      short loc_180012629
0x180012618  cmp     edi, 1
0x18001261b  jnz     loc_1800124E3
0x180012621  lea     esi, [rdi+10h]
0x180012624  jmp     loc_180012768
0x180012629  mov     r8d, [rbp+arg_20]; int
0x18001262d  mov     edi, 5CAh
0x180012632  mov     edx, edi; unsigned int
0x180012634  mov     rcx, r14; this
0x180012637  call    ?Log_SD_ERROR_BACKUP_FAILED@@YAJPEAVCSxFunctionTracer@@KJ@Z; Log_SD_ERROR_BACKUP_FAILED(CSxFunctionTracer *,ulong,long)
0x18001263c  mov     [rbp+var_40], eax
0x18001263f  mov     ebx, eax
0x180012641  test    eax, eax
0x180012643  jns     short loc_18001264E
0x180012645  mov     [rbp+var_3A], di
0x180012649  jmp     loc_180012790
0x18001264e  mov     [rbp+var_3C], di
0x180012652  jmp     loc_180012768
0x180012657  mov     rdi, [rbp+arg_28]
0x18001265b  test    rdi, rdi
0x18001265e  jz      loc_1800126F9
0x180012664  cmp     [rdi], r12w
0x180012668  jz      loc_1800126F9
0x18001266e  mov     r15d, [rbp+arg_20]
0x180012672  mov     eax, 59Ch
0x180012677  mov     r9d, r15d; int
0x18001267a  mov     [rbp+var_3C], ax
0x18001267e  mov     r8, rdi; unsigned __int16 *
0x180012681  mov     [rbp+var_40], r12d
0x180012685  mov     rcx, r14; this
0x180012688  call    ?Log_SD_ERROR_TARGET_FAILED@@YAJPEAVCSxFunctionTracer@@KPEBGJ@Z; Log_SD_ERROR_TARGET_FAILED(CSxFunctionTracer *,ulong,ushort const *,long)
0x18001268d  mov     ebx, eax
0x18001268f  mov     [rbp+var_40], eax
0x180012692  test    eax, eax
0x180012694  mov     eax, 59Dh
0x180012699  js      loc_180012465
0x18001269f  mov     r8d, r15d; int
0x1800126a2  mov     [rbp+var_3C], ax
0x1800126a6  mov     rdx, rdi; unsigned __int16 *
0x1800126a9  call    ?_FailureIsCredentialsError@CSdController@@AEAAJPEBGJ@Z; CSdController::_FailureIsCredentialsError(ushort const *,long)
0x1800126ae  mov     ebx, eax
0x1800126b0  mov     [rbp+var_40], eax
0x1800126b3  test    eax, eax
0x1800126b5  mov     eax, 5A2h
0x1800126ba  js      loc_180012465
0x1800126c0  mov     [rbp+var_3C], ax
0x1800126c4  test    ebx, ebx
0x1800126c6  jnz     short loc_1800126D0
0x1800126c8  lea     esi, [rbx+1]
0x1800126cb  jmp     loc_180012768
0x1800126d0  lea     eax, [r15+7EFFFFFAh]
0x1800126d7  test    eax, 0FFFFFFFDh
0x1800126dc  jz      short loc_1800126F2
0x1800126de  mov     esi, 3
0x1800126e3  cmp     r15d, 8100002Bh
0x1800126ea  lea     eax, [rsi+0Fh]
0x1800126ed  cmovz   esi, eax
0x1800126f0  jmp     short loc_180012768
0x1800126f2  mov     esi, 9
0x1800126f7  jmp     short loc_180012768
0x1800126f9  mov     eax, 59Ch
0x1800126fe  jmp     loc_18001245D
0x180012703  mov     r8d, [rbp+arg_20]; int
0x180012707  mov     rcx, r14; this
0x18001270a  call    ?Log_SD_ERROR_SNAPSHOT_FAILED@@YAJPEAVCSxFunctionTracer@@KJ@Z; Log_SD_ERROR_SNAPSHOT_FAILED(CSxFunctionTracer *,ulong,long)
0x18001270f  mov     ebx, eax
0x180012711  mov     [rbp+var_40], eax
0x180012714  test    eax, eax
0x180012716  mov     eax, 598h
0x18001271b  js      loc_180012465
0x180012721  mov     esi, 3
0x180012726  jmp     loc_18001252F
0x18001272b  mov     esi, 3
0x180012730  cmp     r8d, 8100002Dh
0x180012737  lea     eax, [rsi+10h]
0x18001273a  cmovz   esi, eax
0x18001273d  jmp     short loc_180012744
0x18001273f  mov     esi, 9
0x180012744  mov     edi, 5E2h
0x180012749  mov     rcx, r14; this
0x18001274c  mov     edx, edi; unsigned int
0x18001274e  call    ?Log_SD_ERROR_BACKUP_FAILED@@YAJPEAVCSxFunctionTracer@@KJ@Z; Log_SD_ERROR_BACKUP_FAILED(CSxFunctionTracer *,ulong,long)
0x180012753  mov     [rbp+var_40], eax
0x180012756  mov     ebx, eax
0x180012758  test    eax, eax
0x18001275a  js      loc_180012645
0x180012760  mov     [rbp+var_3C], di
0x180012764  test    esi, esi
0x180012766  jz      short loc_180012790
0x180012768  mov     rcx, [rbp+arg_8]
0x18001276c  mov     edx, esi
0x18001276e  mov     rax, [rcx]
0x180012771  mov     rax, [rax+18h]
0x180012775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001277a  mov     ebx, eax
0x18001277c  mov     [rbp+var_40], eax
0x18001277f  test    eax, eax
0x180012781  mov     eax, 5E9h
0x180012786  js      loc_180012465
0x18001278c  mov     [rbp+var_3C], ax
0x180012790  mov     rcx, [rbp+arg_8]
0x180012794  test    rcx, rcx
0x180012797  jz      short loc_1800127A5
0x180012799  mov     rdx, [rcx]
0x18001279c  mov     rax, [rdx+10h]
0x1800127a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a5  lea     rcx, [rbp+var_40]; this
0x1800127a9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800127ae  lea     r11, [rsp+70h+var_s0]
0x1800127b3  mov     eax, ebx
0x1800127b5  mov     rbx, [r11+40h]
0x1800127b9  mov     rsi, [r11+48h]
0x1800127bd  mov     rsp, r11
0x1800127c0  pop     r15
0x1800127c2  pop     r14
0x1800127c4  pop     r12
0x1800127c6  pop     rdi
0x1800127c7  pop     rbp
0x1800127c8  retn
```
