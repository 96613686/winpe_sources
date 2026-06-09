# GSM::_ServiceMainHelper(ushort const *)

- ea: `0x1800074c0`
- end: `0x180007750`
- name: `?_ServiceMainHelper@GSM@@YAXPEBG@Z`
- size: `656`
- prototype: `void __fastcall(const WCHAR *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022050`

## callees

- `0x1800074c0`
- `0x180007760`
- `0x180007ad0`
- `0x180018a74`
- `0x180019148`
- `0x18001951c`
- `0x18001efc8`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800075a5`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800075a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800075e0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800075e0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000752b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000752b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007732`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007732`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007570`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007570`

## pseudocode

```c
void __fastcall GSM::_ServiceMainHelper(const WCHAR *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v4; // ebx
  int v5; // esi
  int v6; // ebp
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ecx
  __int64 v10; // rsi
  __int64 *v11; // rbx
  char v12; // bp
  HRESULT v13; // r14d
  SERVICE_STATUS_HANDLE v14; // rax
  struct GSM::SERVICEENTRY *v15; // rdx
  bool v16; // zf
  int v17; // edi
  int v18; // ecx
  int v19; // esi
  int v20; // r8d
  _BYTE v21[16]; // [rsp+30h] [rbp-48h] BYREF

  if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_HDSrv_Service_Start_Start,
      a3,
      1,
      (__int64)v21);
  v4 = 0;
  v5 = 0;
  v6 = -2147467259;
  while ( !v5 )
  {
    v7 = lstrcmpW(this, GSM::g_rgsubservice);
    v8 = 0;
    if ( v7 )
      v8 = v6;
    v6 = v8;
    v9 = 0;
    if ( v7 )
      v9 = v4;
    v5 = 1;
    v4 = v9;
    if ( v6 >= 0 )
    {
      v10 = 99LL * v9;
      v11 = &qword_18003E0B0[v10 + 1];
      v12 = 0;
      v13 = CoInitializeEx(0, 4u);
      if ( v13 >= 0 )
      {
        v12 = 1;
        v13 = GSM::SERVICEENTRY::Init(
                (GSM::SERVICEENTRY *)&qword_18003E0B0[v10 + 1],
                this,
                (const struct CFactoryData *)*(&GSM::g_rgsubservice + v10 + 9),
                (unsigned int)(&GSM::g_rgsubservice)[v10 + 5]);
      }
      v14 = RegisterServiceCtrlHandlerExW(this, GSM::_ServiceHandler, &qword_18003E0B0[v10 + 1]);
      v11[6] = (__int64)v14;
      if ( !v14 )
        goto LABEL_35;
      *((_DWORD *)v11 + 10) = 1;
      if ( v13 >= 0 )
      {
        v16 = GSM::g_loadedcontext == 1;
        v17 = 2;
        *((_DWORD *)v11 + 3) = 2;
        if ( v16 && !SetServiceStatus(v14, (LPSERVICE_STATUS)(v11 + 1)) )
          ResultFromKnownLastError();
        v19 = ((__int64 (__fastcall *)(__int64 *))(&GSM::g_rgsubservice)[v10 + 1])(v11 + 37);
        if ( v19 >= 0 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, bool, __int64))(*(_QWORD *)v11[37] + 8LL))(
                  v11[37],
                  GSM::g_loadedcontext == 1,
                  (__int64)v11 + 76);
          if ( v19 >= 0 )
          {
            if ( (*(_BYTE *)v11 & 2) == 0
              || (v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11[37] + 48LL))(v11[37], v11[38]),
                  v19 >= 0) )
            {
              if ( (*(_BYTE *)v11 & 1) == 0
                || (v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11[37] + 40LL))(v11[37], v11 + 5),
                    v19 >= 0) )
              {
                *((_DWORD *)v11 + 3) = 4;
                GSM::_SetServiceStatus((GSM *)v11, v15);
                v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11[37] + 16LL))(v11[37]);
              }
            }
          }
        }
        if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            v18,
            (unsigned int)ShellTraceId_HDSrv_Service_Start_Stop,
            v20,
            1,
            (__int64)v21);
        if ( v19 < 0 || (int)GSM::_RunService((GSM *)v11, v15) < 0 )
        {
          *((_DWORD *)v11 + 69) = 4;
        }
        else
        {
          if ( *((_DWORD *)v11 + 3) == 1 )
            GSM::_SetServiceStatus((GSM *)v11, v15);
          else
            v17 = 3;
          *((_DWORD *)v11 + 69) = v17;
          if ( (unsigned int)(v17 - 3) >= 2 )
            goto LABEL_35;
        }
      }
      *((_DWORD *)v11 + 3) = 1;
      GSM::_SetServiceStatus((GSM *)v11, v15);
LABEL_35:
      GSM::SERVICEENTRY::_Cleanup((GSM::SERVICEENTRY *)v11);
      if ( v12 )
        CoUninitialize();
      return;
    }
  }
}

```

## disassembly

```asm
0x1800074c0  push    rbx
0x1800074c2  push    rbp
0x1800074c3  push    rsi
0x1800074c4  push    rdi
0x1800074c5  push    r12
0x1800074c7  sub     rsp, 50h
0x1800074cb  mov     rax, cs:__security_cookie
0x1800074d2  xor     rax, rsp
0x1800074d5  mov     [rsp+78h+var_38], rax
0x1800074da  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x1800074e1  mov     rdi, rcx
0x1800074e4  jz      short loc_180007502
0x1800074e6  lea     rax, [rsp+78h+var_48]
0x1800074eb  mov     r9d, 1
0x1800074f1  lea     rdx, ShellTraceId_HDSrv_Service_Start_Start
0x1800074f8  mov     [rsp+78h+var_58], rax
0x1800074fd  call    McGenEventWrite_EtwEventWriteTransfer
0x180007502  xor     ebx, ebx
0x180007504  lea     r12, ?g_rgsubservice@GSM@@3PAUSUBSERVICE@1@A; GSM::SUBSERVICE near * GSM::g_rgsubservice
0x18000750b  xor     esi, esi
0x18000750d  mov     ebp, 80004005h
0x180007512  cmp     esi, 1
0x180007515  jnb     loc_180007738
0x18000751b  mov     eax, esi
0x18000751d  mov     rcx, rdi; lpString1
0x180007520  imul    rdx, rax, 318h
0x180007527  mov     rdx, [rdx+r12]; lpString2
0x18000752b  call    cs:__imp_lstrcmpW
0x180007531  xor     ecx, ecx
0x180007533  test    eax, eax
0x180007535  cmovnz  ecx, ebp
0x180007538  mov     ebp, ecx
0x18000753a  mov     ecx, esi
0x18000753c  cmovnz  ecx, ebx
0x18000753f  inc     esi
0x180007541  mov     ebx, ecx
0x180007543  test    ebp, ebp
0x180007545  js      short loc_180007512
0x180007547  imul    rsi, rbx, 318h
0x18000754e  lea     rbx, [r12+58h]
0x180007553  mov     [rsp+78h+arg_8], r14
0x18000755b  mov     edx, 4; dwCoInit
0x180007560  mov     [rsp+78h+arg_10], r15
0x180007568  xor     ecx, ecx; pvReserved
0x18000756a  add     rbx, rsi
0x18000756d  xor     bpl, bpl
0x180007570  call    cs:__imp_CoInitializeEx
0x180007576  mov     r14d, eax
0x180007579  test    eax, eax
0x18000757b  js      short loc_180007598
0x18000757d  mov     r9d, [rsi+r12+50h]; unsigned int
0x180007582  mov     rdx, rdi; unsigned __int16 *
0x180007585  mov     r8, [rsi+r12+48h]; struct CFactoryData *
0x18000758a  mov     rcx, rbx; this
0x18000758d  mov     bpl, 1
0x180007590  call    ?Init@SERVICEENTRY@GSM@@QEAAJPEBGPEBVCFactoryData@@K@Z; GSM::SERVICEENTRY::Init(ushort const *,CFactoryData const *,ulong)
0x180007595  mov     r14d, eax
0x180007598  mov     r8, rbx; lpContext
0x18000759b  lea     rdx, ?_ServiceHandler@GSM@@YAKKKPEAX0@Z; lpHandlerProc
0x1800075a2  mov     rcx, rdi; lpServiceName
0x1800075a5  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800075ab  mov     [rbx+30h], rax
0x1800075af  test    rax, rax
0x1800075b2  jz      loc_180007715
0x1800075b8  mov     dword ptr [rbx+28h], 1
0x1800075bf  test    r14d, r14d
0x1800075c2  js      loc_180007706
0x1800075c8  cmp     cs:?g_loadedcontext@GSM@@3W4LOADEDCONTEXT@1@A, 1; GSM::LOADEDCONTEXT GSM::g_loadedcontext
0x1800075cf  lea     rdx, [rbx+8]; lpServiceStatus
0x1800075d3  mov     edi, 2
0x1800075d8  mov     [rdx+4], edi
0x1800075db  jnz     short loc_1800075EF
0x1800075dd  mov     rcx, rax; hServiceStatus
0x1800075e0  call    cs:__imp_SetServiceStatus
0x1800075e6  test    eax, eax
0x1800075e8  jnz     short loc_1800075EF
0x1800075ea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800075ef  mov     rax, [rsi+r12+10h]
0x1800075f4  lea     rcx, [rbx+128h]
0x1800075fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007600  mov     esi, eax
0x180007602  test    eax, eax
0x180007604  js      loc_18000769E
0x18000760a  mov     rcx, [rbx+128h]
0x180007611  lea     r8, [rbx+4Ch]
0x180007615  xor     edx, edx
0x180007617  cmp     cs:?g_loadedcontext@GSM@@3W4LOADEDCONTEXT@1@A, 1; GSM::LOADEDCONTEXT GSM::g_loadedcontext
0x18000761e  mov     rax, [rcx]
0x180007621  setz    dl
0x180007624  mov     rax, [rax+8]
0x180007628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762d  mov     esi, eax
0x18000762f  test    eax, eax
0x180007631  js      short loc_18000769E
0x180007633  test    [rbx], dil
0x180007636  jz      short loc_180007658
0x180007638  mov     rcx, [rbx+128h]
0x18000763f  mov     rdx, [rbx+130h]
0x180007646  mov     rax, [rcx]
0x180007649  mov     rax, [rax+30h]
0x18000764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007652  mov     esi, eax
0x180007654  test    eax, eax
0x180007656  js      short loc_18000769E
0x180007658  test    byte ptr [rbx], 1
0x18000765b  jz      short loc_18000767A
0x18000765d  mov     rcx, [rbx+128h]
0x180007664  lea     rdx, [rbx+28h]
0x180007668  mov     rax, [rcx]
0x18000766b  mov     rax, [rax+28h]
0x18000766f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007674  mov     esi, eax
0x180007676  test    eax, eax
0x180007678  js      short loc_18000769E
0x18000767a  mov     rcx, rbx; this
0x18000767d  mov     dword ptr [rbx+0Ch], 4
0x180007684  call    ?_SetServiceStatus@GSM@@YAXPEAUSERVICEENTRY@1@@Z; GSM::_SetServiceStatus(GSM::SERVICEENTRY *)
0x180007689  mov     rcx, [rbx+128h]
0x180007690  mov     rax, [rcx]
0x180007693  mov     rax, [rax+10h]
0x180007697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769c  mov     esi, eax
0x18000769e  test    cs:Microsoft_Windows_ShsvcsEnableBits, 1
0x1800076a5  jz      short loc_1800076C3
0x1800076a7  lea     rax, [rsp+78h+var_48]
0x1800076ac  mov     r9d, 1
0x1800076b2  lea     rdx, ShellTraceId_HDSrv_Service_Start_Stop
0x1800076b9  mov     [rsp+78h+var_58], rax
0x1800076be  call    McGenEventWrite_EtwEventWriteTransfer
0x1800076c3  test    esi, esi
0x1800076c5  js      short loc_1800076FC
0x1800076c7  mov     rcx, rbx; this
0x1800076ca  call    ?_RunService@GSM@@YAJPEAUSERVICEENTRY@1@@Z; GSM::_RunService(GSM::SERVICEENTRY *)
0x1800076cf  mov     esi, eax
0x1800076d1  test    eax, eax
0x1800076d3  js      short loc_1800076FC
0x1800076d5  cmp     dword ptr [rbx+0Ch], 1
0x1800076d9  jnz     short loc_1800076E5
0x1800076db  mov     rcx, rbx; this
0x1800076de  call    ?_SetServiceStatus@GSM@@YAXPEAUSERVICEENTRY@1@@Z; GSM::_SetServiceStatus(GSM::SERVICEENTRY *)
0x1800076e3  jmp     short loc_1800076EA
0x1800076e5  mov     edi, 3
0x1800076ea  mov     [rbx+114h], edi
0x1800076f0  sub     edi, 3
0x1800076f3  jz      short loc_180007706
0x1800076f5  cmp     edi, 1
0x1800076f8  jz      short loc_180007706
0x1800076fa  jmp     short loc_180007715
0x1800076fc  mov     dword ptr [rbx+114h], 4
0x180007706  mov     rcx, rbx; this
0x180007709  mov     dword ptr [rbx+0Ch], 1
0x180007710  call    ?_SetServiceStatus@GSM@@YAXPEAUSERVICEENTRY@1@@Z; GSM::_SetServiceStatus(GSM::SERVICEENTRY *)
0x180007715  mov     rcx, rbx; this
0x180007718  call    ?_Cleanup@SERVICEENTRY@GSM@@QEAAXXZ; GSM::SERVICEENTRY::_Cleanup(void)
0x18000771d  mov     r15, [rsp+78h+arg_10]
0x180007725  mov     r14, [rsp+78h+arg_8]
0x18000772d  test    bpl, bpl
0x180007730  jz      short loc_180007738
0x180007732  call    cs:__imp_CoUninitialize
0x180007738  mov     rcx, [rsp+78h+var_38]
0x18000773d  xor     rcx, rsp; StackCookie
0x180007740  call    __security_check_cookie
0x180007745  add     rsp, 50h
0x180007749  pop     r12
0x18000774b  pop     rdi
0x18000774c  pop     rsi
0x18000774d  pop     rbp
0x18000774e  pop     rbx
0x18000774f  retn
```
