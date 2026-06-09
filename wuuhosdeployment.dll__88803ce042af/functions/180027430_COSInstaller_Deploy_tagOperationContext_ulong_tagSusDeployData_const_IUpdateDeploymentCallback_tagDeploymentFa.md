# COSInstaller::Deploy(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions)

- ea: `0x180027430`
- end: `0x1800276c8`
- name: `?Deploy@COSInstaller@@UEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@@Z`
- size: `664`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x180024660`
- `0x180026c58`
- `0x180027430`
- `0x1800276d0`
- `0x180027d78`
- `0x180028268`
- `0x18002db78`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800274e2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800274e2`

## string_xrefs

- `0x180027648`: `Install`
- `0x1800275a2`: `Commit`
- `0x180027605`: `Uninstall`
- `0x180027614`: `Deployment handler does not support uninstall`
- `0x180027478`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180027568`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
__int64 __fastcall COSInstaller::Deploy(
        COSInstaller *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        struct IUpdateDeploymentCallback *a5,
        int a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  int v14; // [rsp+20h] [rbp-E0h]
  _QWORD v15[5]; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v18; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  const char *v20; // [rsp+90h] [rbp-70h] BYREF
  void *v21; // [rsp+98h] [rbp-68h]
  void *lpMem; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+A8h] [rbp-58h]
  __int128 v24; // [rsp+B8h] [rbp-48h]
  __int128 v25; // [rsp+C8h] [rbp-38h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  _BYTE v27[8]; // [rsp+E0h] [rbp-20h] BYREF
  ULONGLONG UnbiasedTime[4]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v18 = a3;
  if ( !a3 )
  {
    v9 = -2145124316;
    v10 = 133;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v9,
      v14);
    return v9;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    v10 = 134;
    goto LABEL_3;
  }
  v17 = 0;
  v20 = 0;
  v21 = 0;
  lpMem = 0;
  v23 = 0;
  v26 = 0;
  v24 = 0;
  v19[0] = 0;
  v25 = 0;
  CWUPerfTimer::CWUPerfTimer((CWUPerfTimer *)v27);
  UnbiasedTime[2] = 0;
  QueryUnbiasedInterruptTime(UnbiasedTime);
  OSDeploymentEventSummary::GenerateCV((OSDeploymentEventSummary *)&v20);
  v15[0] = v27;
  v16 = 1;
  v15[1] = &v20;
  v15[2] = &v18;
  v15[3] = v19;
  v15[4] = &v17;
  v17 = (*(__int64 (__fastcall **)(COSInstaller *, _QWORD, __int64, _DWORD *))(*(_QWORD *)a1 + 48LL))(a1, v18, a4, v19);
  v9 = v17;
  if ( v17 >= 0 )
  {
    if ( v19[0] )
    {
      switch ( *(_DWORD *)(a4 + 288) )
      {
        case 1:
          v20 = "Install";
          v12 = COSInstaller::Install(a1, a2, v18, (struct tagSusDeployData *)a4, a5, a6, v21);
          break;
        case 2:
          v20 = "Uninstall";
          WUTrace(0, 0, 4096, 3);
          v9 = -2145116156;
          v17 = -2145116156;
          goto LABEL_20;
        case 4:
          v20 = "Revert";
          v12 = COSInstaller::Revert(a1, a2, v18, a4, a5, a6, v21);
          break;
        case 8:
          v20 = "Commit";
          v12 = COSInstaller::Commit((__int64)a1, v18, a4, (__int64)a5, a6, v21);
          break;
        default:
          goto LABEL_20;
      }
      v9 = v12;
      v17 = v12;
      goto LABEL_20;
    }
    v9 = -2145116156;
    v11 = 157;
    v17 = -2145116156;
  }
  else
  {
    v11 = 153;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)v9,
    v14);
LABEL_20:
  wil::details::lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___::_lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___(v15);
  if ( lpMem )
  {
    CSusBaseAllocTag<942762101>::operator delete(lpMem);
    lpMem = 0;
  }
  if ( v21 )
    CSusBaseAllocTag<942762101>::operator delete(v21);
  return v9;
}

```

## disassembly

```asm
0x180027430  push    rbp
0x180027432  push    rbx
0x180027433  push    rsi
0x180027434  push    rdi
0x180027435  push    r14
0x180027437  push    r15
0x180027439  lea     rbp, [rsp-18h]
0x18002743e  sub     rsp, 118h
0x180027445  mov     rax, cs:__security_cookie
0x18002744c  xor     rax, rsp
0x18002744f  mov     [rbp+40h+var_38], rax
0x180027453  mov     r14, [rbp+40h+arg_20]
0x180027457  mov     rdi, r9
0x18002745a  mov     [rsp+140h+var_C8], r8d
0x18002745f  mov     r15, rdx
0x180027462  mov     rsi, rcx
0x180027465  test    r8d, r8d
0x180027468  jnz     short loc_18002748C
0x18002746a  mov     ebx, 80240024h
0x18002746f  mov     edx, 85h; void *
0x180027474  mov     rcx, [rbp+48h]; this
0x180027478  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002747f  mov     r9d, ebx; char *
0x180027482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027487  jmp     loc_1800276AA
0x18002748c  test    rdi, rdi
0x18002748f  jnz     short loc_18002749D
0x180027491  mov     ebx, 80004003h
0x180027496  mov     edx, 86h
0x18002749b  jmp     short loc_180027474
0x18002749d  xor     eax, eax
0x18002749f  mov     [rsp+140h+var_D0], 0
0x1800274a7  xorps   xmm0, xmm0
0x1800274aa  mov     [rbp+40h+var_B0], rax
0x1800274ae  lea     rcx, [rbp+40h+var_60]; this
0x1800274b2  mov     [rbp+40h+var_A8], rax
0x1800274b6  mov     [rbp+40h+lpMem], rax
0x1800274ba  movups  [rbp+40h+var_98], xmm0
0x1800274be  mov     [rbp+40h+var_68], rax
0x1800274c2  movups  [rbp+40h+var_88], xmm0
0x1800274c6  mov     [rbp+40h+var_C0], 0
0x1800274cd  movups  [rbp+40h+var_78], xmm0
0x1800274d1  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x1800274d6  lea     rcx, [rbp+40h+UnbiasedTime]; UnbiasedTime
0x1800274da  mov     [rbp+40h+var_48], 0
0x1800274e2  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800274e8  lea     rcx, [rbp+40h+var_B0]; this
0x1800274ec  call    ?GenerateCV@OSDeploymentEventSummary@@QEAAXXZ; OSDeploymentEventSummary::GenerateCV(void)
0x1800274f1  mov     edx, [rsp+140h+var_C8]
0x1800274f5  lea     rax, [rbp+40h+var_60]
0x1800274f9  mov     [rsp+140h+var_100], rax
0x1800274fe  lea     r9, [rbp+40h+var_C0]
0x180027502  lea     rax, [rbp+40h+var_B0]
0x180027506  mov     [rsp+140h+var_D8], 1
0x18002750b  mov     [rsp+140h+var_F8], rax
0x180027510  mov     r8, rdi
0x180027513  lea     rax, [rsp+140h+var_C8]
0x180027518  mov     rcx, rsi
0x18002751b  mov     [rsp+140h+var_F0], rax
0x180027520  lea     rax, [rbp+40h+var_C0]
0x180027524  mov     [rsp+140h+var_E8], rax
0x180027529  lea     rax, [rsp+140h+var_D0]
0x18002752e  mov     [rsp+140h+var_E0], rax
0x180027533  mov     rax, [rsi]
0x180027536  mov     rax, [rax+30h]
0x18002753a  call    _guard_dispatch_icall
0x18002753f  mov     [rsp+140h+var_D0], eax
0x180027543  mov     ebx, eax
0x180027545  test    eax, eax
0x180027547  jns     short loc_180027550
0x180027549  mov     edx, 99h
0x18002754e  jmp     short loc_180027564
0x180027550  cmp     [rbp+40h+var_C0], 0
0x180027554  jnz     short loc_18002757C
0x180027556  mov     ebx, 80242004h
0x18002755b  mov     edx, 9Dh; void *
0x180027560  mov     [rsp+140h+var_D0], ebx
0x180027564  mov     rcx, [rbp+48h]; this
0x180027568  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002756f  mov     r9d, ebx; char *
0x180027572  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027577  jmp     loc_18002767C
0x18002757c  mov     edx, [rdi+120h]
0x180027582  sub     edx, 1
0x180027585  jz      loc_180027643
0x18002758b  sub     edx, 1
0x18002758e  jz      short loc_180027605
0x180027590  sub     edx, 2
0x180027593  jz      short loc_1800275D0
0x180027595  cmp     edx, 4
0x180027598  jnz     loc_18002767C
0x18002759e  mov     edx, [rsp+140h+var_C8]
0x1800275a2  lea     rax, aCommit_0; "Commit"
0x1800275a9  mov     [rbp+40h+var_B0], rax
0x1800275ad  mov     r9, r14
0x1800275b0  mov     rax, [rbp+40h+var_A8]
0x1800275b4  mov     r8, rdi
0x1800275b7  mov     [rsp+140h+var_118], rax
0x1800275bc  mov     rcx, rsi
0x1800275bf  mov     eax, [rbp+40h+arg_28]
0x1800275c2  mov     dword ptr [rsp+140h+var_120], eax
0x1800275c6  call    ?Commit@COSInstaller@@AEAAJKQEBUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Commit(ulong,tagSusDeployData const * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x1800275cb  jmp     loc_180027676
0x1800275d0  mov     r8d, [rsp+140h+var_C8]
0x1800275d5  lea     rax, aRevert; "Revert"
0x1800275dc  mov     [rbp+40h+var_B0], rax
0x1800275e0  mov     r9, rdi
0x1800275e3  mov     rax, [rbp+40h+var_A8]
0x1800275e7  mov     rdx, r15
0x1800275ea  mov     [rsp+140h+var_110], rax
0x1800275ef  mov     rcx, rsi
0x1800275f2  mov     eax, [rbp+40h+arg_28]
0x1800275f5  mov     dword ptr [rsp+140h+var_118], eax
0x1800275f9  mov     [rsp+140h+var_120], r14
0x1800275fe  call    ?Revert@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Revert(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x180027603  jmp     short loc_180027676
0x180027605  lea     rax, aUninstall; "Uninstall"
0x18002760c  xor     edx, edx
0x18002760e  mov     [rbp+40h+var_B0], rax
0x180027612  xor     ecx, ecx
0x180027614  lea     rax, aDeploymentHand; "Deployment handler does not support uni"...
0x18002761b  mov     r8d, 1000h
0x180027621  mov     [rsp+140h+var_118], rax
0x180027626  lea     r9d, [rdx+3]
0x18002762a  mov     [rsp+140h+var_120], 0
0x180027633  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180027638  mov     ebx, 80242004h
0x18002763d  mov     [rsp+140h+var_D0], ebx
0x180027641  jmp     short loc_18002767C
0x180027643  mov     r8d, [rsp+140h+var_C8]
0x180027648  lea     rax, aInstall_0; "Install"
0x18002764f  mov     [rbp+40h+var_B0], rax
0x180027653  mov     r9, rdi
0x180027656  mov     rax, [rbp+40h+var_A8]
0x18002765a  mov     rdx, r15
0x18002765d  mov     [rsp+140h+var_110], rax
0x180027662  mov     rcx, rsi
0x180027665  mov     eax, [rbp+40h+arg_28]
0x180027668  mov     dword ptr [rsp+140h+var_118], eax
0x18002766c  mov     [rsp+140h+var_120], r14
0x180027671  call    ?Install@COSInstaller@@AEAAJPEAUtagOperationContext@@KQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@W4tagDeploymentFailOptions@@PEBD@Z; COSInstaller::Install(tagOperationContext *,ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,tagDeploymentFailOptions,char const *)
0x180027676  mov     ebx, eax
0x180027678  mov     [rsp+140h+var_D0], eax
0x18002767c  lea     rcx, [rsp+140h+var_100]
0x180027681  call    wil__details__lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103______lambda_call__lambda_caf7dfe7fc8ad8db89b6973ff755b103___
0x180027686  mov     rcx, [rbp+40h+lpMem]; lpMem
0x18002768a  test    rcx, rcx
0x18002768d  jz      short loc_18002769C
0x18002768f  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180027694  mov     [rbp+40h+lpMem], 0
0x18002769c  mov     rcx, [rbp+40h+var_A8]; lpMem
0x1800276a0  test    rcx, rcx
0x1800276a3  jz      short loc_1800276AA
0x1800276a5  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800276aa  mov     eax, ebx
0x1800276ac  mov     rcx, [rbp+40h+var_38]
0x1800276b0  xor     rcx, rsp; StackCookie
0x1800276b3  call    __security_check_cookie
0x1800276b8  add     rsp, 118h
0x1800276bf  pop     r15
0x1800276c1  pop     r14
0x1800276c3  pop     rdi
0x1800276c4  pop     rsi
0x1800276c5  pop     rbx
0x1800276c6  pop     rbp
0x1800276c7  retn
```
