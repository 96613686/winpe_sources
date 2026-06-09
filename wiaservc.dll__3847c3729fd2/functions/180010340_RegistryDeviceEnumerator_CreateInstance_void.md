# RegistryDeviceEnumerator::CreateInstance(void)

- ea: `0x180010340`
- end: `0x18001072a`
- name: `?CreateInstance@RegistryDeviceEnumerator@@SAXXZ`
- size: `1002`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000f4fc`
- `0x18000fcfc`
- `0x180010340`
- `0x180013728`
- `0x18002044c`
- `0x18002e900`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x180048dbc`
- `0x180078010`

## string_xrefs

- `0x180010570`: `ServiceComponentHolder::Get`
- `0x1800105a2`: `ServiceComponentHolder::Get`
- `0x1800105ce`: `ServiceComponentHolder::Get`
- `0x180010604`: `ServiceComponentHolder::Get`
- `0x18001055b`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18001058b`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x1800105ba`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x1800105ec`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x180010485`: `RegistryDeviceEnumerator::CreateInstance`
- `0x1800104b6`: `RegistryDeviceEnumerator::CreateInstance`
- `0x180010627`: `RegistryDeviceEnumerator::CreateInstance`
- `0x180010658`: `RegistryDeviceEnumerator::CreateInstance`
- `0x1800106eb`: `RegistryDeviceEnumerator::CreateInstance`
- `0x180010719`: `RegistryDeviceEnumerator::CreateInstance`
- `0x180010473`: `CreateInstance failed to create a RegistryDeviceEnumerator due to lack of memory`
- `0x18001049c`: `CreateInstance failed to create a RegistryDeviceEnumerator due to lack of memory`
- `0x180010615`: `CreateInstance for the RegistryDeviceEnumerator failed to find the DeviceListManager`
- `0x18001063e`: `CreateInstance for the RegistryDeviceEnumerator failed to find the DeviceListManager`
- `0x1800106d9`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher`
- `0x180010702`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher`

## pseudocode

```c
void RegistryDeviceEnumerator::CreateInstance(void)
{
  __int64 v0; // rdi
  unsigned __int64 v1; // rdx
  Dispatcher *v2; // r14
  unsigned __int64 v3; // rdx
  DeviceListManager *v4; // rsi
  void *v5; // rax
  char *v6; // rbx
  void *v7; // rdx
  void **lpMem; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  char *v11; // rcx
  unsigned __int64 v12; // rdx
  char *v13; // rcx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  struct DeviceEnumerator *v30; // rax
  struct DeviceEnumerator *v31; // rbx
  char *v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h]
  const unsigned __int64 *v40; // [rsp+40h] [rbp-C0h] BYREF
  char v41; // [rsp+48h] [rbp-B8h] BYREF
  void *v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+150h] [rbp+50h]
  const unsigned __int64 *v44; // [rsp+170h] [rbp+70h] BYREF
  char v45; // [rsp+178h] [rbp+78h] BYREF
  void *v46; // [rsp+278h] [rbp+178h]
  __int64 v47; // [rsp+280h] [rbp+180h]
  const unsigned __int64 *v48; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v49; // [rsp+2A8h] [rbp+1A8h] BYREF
  void *v50; // [rsp+3A8h] [rbp+2A8h]

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v38);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v40, L"Dispatcher");
  v0 = v39;
  if ( v39 )
  {
    v2 = (Dispatcher *)CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<Dispatcher>(v39, &v40);
  }
  else
  {
    v2 = 0;
    v15 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                    v42);
    WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                     v42);
    WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"ServiceComponentHolder::Get", 2, v17);
  }
  v40 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v42 && v42 != &v41 )
    operator delete(v42, v1);
  v42 = 0;
  v43 = 0;
  if ( v2 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v44, L"DeviceListManager");
    if ( v0 )
    {
      v4 = (DeviceListManager *)CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<DeviceListManager>(v0, &v44);
    }
    else
    {
      v4 = 0;
      v20 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                      v46);
      WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v22 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                       v46);
      WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"ServiceComponentHolder::Get", 2, v22);
    }
    v44 = &CSimpleStringBase<unsigned short>::`vftable';
    if ( v46 && v46 != &v45 )
      operator delete(v46, v3);
    v46 = 0;
    v47 = 0;
    if ( v4 )
    {
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
        &v48,
        L"SYSTEM\\CurrentControlSet\\Control\\StillImage\\FakeDevices");
      v5 = operator new(0x1B0u);
      if ( v5
        && (v30 = (struct DeviceEnumerator *)RegistryDeviceEnumerator::RegistryDeviceEnumerator(v5, &v48),
            (v31 = v30) != 0) )
      {
        DeviceListManager::AddDeviceEnumerator(v4, v30);
        Dispatcher::AddEventHandler(v2, (struct DeviceEnumerator *)((char *)v31 + 16));
        v32 = (char *)v31 + *(int *)(*((_QWORD *)v31 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
      }
      else
      {
        v6 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "CreateInstance failed to create a RegistryDeviceEnumerator due to lack of memory");
        WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateInstance", v6);
        WiaTrcLib::Free((WiaTrcLib *)v6, v7);
        lpMem = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "CreateInstance failed to create a RegistryDeviceEnumerator due to lack of memory");
        WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"RegistryDeviceEnumerator::CreateInstance", 2, lpMem);
      }
      v11 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
      v48 = &CSimpleStringBase<unsigned short>::`vftable';
      if ( v50 && v50 != &v49 )
        operator delete(v50, v12);
    }
    else
    {
      v25 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "CreateInstance for the RegistryDeviceEnumerator failed to find the DeviceListManager");
      WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateInstance", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      v27 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "CreateInstance for the RegistryDeviceEnumerator failed to find the DeviceListManager");
      WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"RegistryDeviceEnumerator::CreateInstance", 2, v27);
    }
    v13 = (char *)v2 + *(int *)(*((_QWORD *)v2 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  else
  {
    v33 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher");
    WriteDbgTraceWarningWI("RegistryDeviceEnumerator::CreateInstance", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"RegistryDeviceEnumerator::CreateInstance", 2, v35);
  }
  if ( v0 )
  {
    v14 = v0 + *(int *)(*(_QWORD *)v0 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
}

```

## disassembly

```asm
0x180010340  push    rbp
0x180010342  push    rbx
0x180010343  push    rsi
0x180010344  push    rdi
0x180010345  push    r12
0x180010347  push    r13
0x180010349  push    r14
0x18001034b  lea     rbp, [rsp-2E0h]
0x180010353  sub     rsp, 3E0h
0x18001035a  mov     rax, cs:__security_cookie
0x180010361  xor     rax, rsp
0x180010364  mov     [rbp+310h+var_40], rax
0x18001036b  lea     rcx, [rsp+410h+var_3E0]; this
0x180010370  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180010375  lea     rdx, aDispatcher; "Dispatcher"
0x18001037c  lea     rcx, [rsp+410h+var_3D0]
0x180010381  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180010386  mov     rdi, [rsp+410h+var_3D8]
0x18001038b  mov     esi, 2
0x180010390  lea     r12d, [rsi-1]
0x180010394  test    rdi, rdi
0x180010397  jz      loc_180010557
0x18001039d  lea     rdx, [rsp+410h+var_3D0]
0x1800103a2  mov     rcx, rdi
0x1800103a5  call    ??$Get@VDispatcher@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x1800103aa  mov     r14, rax
0x1800103ad  mov     rcx, [rbp+310h+var_2C8]; void *
0x1800103b1  lea     r13, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800103b8  mov     [rsp+410h+var_3D0], r13
0x1800103bd  test    rcx, rcx
0x1800103c0  jz      short loc_1800103D0
0x1800103c2  lea     rax, [rsp+410h+var_3C8]
0x1800103c7  cmp     rcx, rax
0x1800103ca  jnz     loc_180010669
0x1800103d0  mov     [rbp+310h+var_2C8], 0
0x1800103d8  mov     [rbp+310h+var_2C0], 0
0x1800103e0  test    r14, r14
0x1800103e3  jz      loc_1800106D9
0x1800103e9  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x1800103f0  lea     rcx, [rbp+310h+var_2A0]
0x1800103f4  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800103f9  test    rdi, rdi
0x1800103fc  jz      loc_1800105B3
0x180010402  lea     rdx, [rbp+310h+var_2A0]
0x180010406  mov     rcx, rdi
0x180010409  call    ??$Get@VDeviceListManager@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18001040e  mov     rsi, rax
0x180010411  mov     rcx, [rbp+310h+var_198]; void *
0x180010418  mov     [rbp+310h+var_2A0], r13
0x18001041c  test    rcx, rcx
0x18001041f  jz      short loc_18001042E
0x180010421  lea     rax, [rbp+310h+var_298]
0x180010425  cmp     rcx, rax
0x180010428  jnz     loc_180010673
0x18001042e  mov     [rbp+310h+var_198], 0
0x180010439  mov     [rbp+310h+var_190], 0
0x180010444  test    rsi, rsi
0x180010447  jz      loc_180010615
0x18001044d  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Sti"...
0x180010454  lea     rcx, [rbp+310h+var_170]
0x18001045b  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180010460  mov     ecx, 1B0h; Size
0x180010465  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001046a  test    rax, rax
0x18001046d  jnz     loc_180010687
0x180010473  lea     rdx, aCreateinstance_7; "CreateInstance failed to create a Regis"...
0x18001047a  mov     ecx, r12d
0x18001047d  call    WiaTrace_TraceLogWithSubComp
0x180010482  mov     rdx, rax; char *
0x180010485  lea     rcx, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x18001048c  mov     rbx, rax
0x18001048f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180010494  mov     rcx, rbx; this
0x180010497  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001049c  lea     rdx, aCreateinstance_7; "CreateInstance failed to create a Regis"...
0x1800104a3  mov     ecx, r12d
0x1800104a6  call    WiaTrace_TraceWithSubComp
0x1800104ab  mov     r9d, 2; int
0x1800104b1  mov     [rsp+410h+lpMem], rax; lpMem
0x1800104b6  lea     r8, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x1800104bd  call    WiaTrace_ProcessTrace_Ex
0x1800104c2  mov     rax, [rsi+8]
0x1800104c6  movsxd  rcx, dword ptr [rax+4]
0x1800104ca  add     rcx, 8
0x1800104ce  add     rcx, rsi
0x1800104d1  mov     rax, [rcx]
0x1800104d4  mov     rax, [rax+10h]
0x1800104d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104dd  mov     rcx, [rbp+310h+var_68]; void *
0x1800104e4  mov     [rbp+310h+var_170], r13
0x1800104eb  test    rcx, rcx
0x1800104ee  jz      short loc_180010500
0x1800104f0  lea     rax, [rbp+310h+var_168]
0x1800104f7  cmp     rcx, rax
0x1800104fa  jnz     loc_18001067D
0x180010500  mov     rax, [r14+8]
0x180010504  movsxd  rcx, dword ptr [rax+4]
0x180010508  add     rcx, 8
0x18001050c  add     rcx, r14
0x18001050f  mov     rax, [rcx]
0x180010512  mov     rax, [rax+10h]
0x180010516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001051b  test    rdi, rdi
0x18001051e  jz      short loc_180010536
0x180010520  mov     rax, [rdi]
0x180010523  movsxd  rcx, dword ptr [rax+4]
0x180010527  add     rcx, rdi
0x18001052a  mov     rax, [rcx]
0x18001052d  mov     rax, [rax+10h]
0x180010531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010536  mov     rcx, [rbp+310h+var_40]
0x18001053d  xor     rcx, rsp; StackCookie
0x180010540  call    __security_check_cookie
0x180010545  add     rsp, 3E0h
0x18001054c  pop     r14
0x18001054e  pop     r13
0x180010550  pop     r12
0x180010552  pop     rdi
0x180010553  pop     rsi
0x180010554  pop     rbx
0x180010555  pop     rbp
0x180010556  retn
0x180010557  mov     r8, [rbp+310h+var_2C8]
0x18001055b  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x180010562  mov     ecx, r12d
0x180010565  xor     r14d, r14d
0x180010568  call    WiaTrace_TraceLogWithSubComp
0x18001056d  mov     rdx, rax; char *
0x180010570  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x180010577  mov     rbx, rax
0x18001057a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001057f  mov     rcx, rbx; this
0x180010582  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180010587  mov     r8, [rbp+310h+var_2C8]
0x18001058b  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x180010592  mov     ecx, r12d
0x180010595  call    WiaTrace_TraceWithSubComp
0x18001059a  mov     r9d, esi; int
0x18001059d  mov     [rsp+410h+lpMem], rax; lpMem
0x1800105a2  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x1800105a9  call    WiaTrace_ProcessTrace_Ex
0x1800105ae  jmp     loc_1800103AD
0x1800105b3  mov     r8, [rbp+310h+var_198]
0x1800105ba  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x1800105c1  mov     ecx, r12d
0x1800105c4  xor     esi, esi
0x1800105c6  call    WiaTrace_TraceLogWithSubComp
0x1800105cb  mov     rdx, rax; char *
0x1800105ce  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x1800105d5  mov     rbx, rax
0x1800105d8  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800105dd  mov     rcx, rbx; this
0x1800105e0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800105e5  mov     r8, [rbp+310h+var_198]
0x1800105ec  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x1800105f3  mov     ecx, r12d
0x1800105f6  call    WiaTrace_TraceWithSubComp
0x1800105fb  lea     r9d, [rsi+2]; int
0x1800105ff  mov     [rsp+410h+lpMem], rax; lpMem
0x180010604  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x18001060b  call    WiaTrace_ProcessTrace_Ex
0x180010610  jmp     loc_180010411
0x180010615  lea     rdx, aCreateinstance_19; "CreateInstance for the RegistryDeviceEn"...
0x18001061c  mov     ecx, r12d
0x18001061f  call    WiaTrace_TraceLogWithSubComp
0x180010624  mov     rdx, rax; char *
0x180010627  lea     rcx, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x18001062e  mov     rbx, rax
0x180010631  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180010636  mov     rcx, rbx; this
0x180010639  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001063e  lea     rdx, aCreateinstance_19; "CreateInstance for the RegistryDeviceEn"...
0x180010645  mov     ecx, r12d
0x180010648  call    WiaTrace_TraceWithSubComp
0x18001064d  mov     r9d, 2; int
0x180010653  mov     [rsp+410h+lpMem], rax; lpMem
0x180010658  lea     r8, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x18001065f  call    WiaTrace_ProcessTrace_Ex
0x180010664  jmp     loc_180010500
0x180010669  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001066e  jmp     loc_1800103D0
0x180010673  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010678  jmp     loc_18001042E
0x18001067d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010682  jmp     loc_180010500
0x180010687  lea     rdx, [rbp+310h+var_170]
0x18001068e  mov     rcx, rax
0x180010691  call    ??0RegistryDeviceEnumerator@@QEAA@AEAV?$CSimpleStringBase@G@@@Z; RegistryDeviceEnumerator::RegistryDeviceEnumerator(CSimpleStringBase<ushort> &)
0x180010696  mov     rbx, rax
0x180010699  test    rax, rax
0x18001069c  jz      loc_180010473
0x1800106a2  mov     rdx, rax; struct DeviceEnumerator *
0x1800106a5  mov     rcx, rsi; this
0x1800106a8  call    ?AddDeviceEnumerator@DeviceListManager@@QEAAJPEAVDeviceEnumerator@@@Z; DeviceListManager::AddDeviceEnumerator(DeviceEnumerator *)
0x1800106ad  lea     rdx, [rbx+10h]; struct SystemEventHandler *
0x1800106b1  mov     rcx, r14; this
0x1800106b4  call    ?AddEventHandler@Dispatcher@@QEAAJPEAVSystemEventHandler@@@Z; Dispatcher::AddEventHandler(SystemEventHandler *)
0x1800106b9  mov     rcx, [rbx+8]
0x1800106bd  movsxd  rcx, dword ptr [rcx+4]
0x1800106c1  add     rcx, 8
0x1800106c5  add     rcx, rbx
0x1800106c8  mov     rax, [rcx]
0x1800106cb  mov     rax, [rax+10h]
0x1800106cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d4  jmp     loc_1800104C2
0x1800106d9  lea     rdx, aCreateinstance_5; "CreateInstance for the DeviceClassEnume"...
0x1800106e0  mov     ecx, r12d
0x1800106e3  call    WiaTrace_TraceLogWithSubComp
0x1800106e8  mov     rdx, rax; char *
0x1800106eb  lea     rcx, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x1800106f2  mov     rbx, rax
0x1800106f5  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800106fa  mov     rcx, rbx; this
0x1800106fd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180010702  lea     rdx, aCreateinstance_5; "CreateInstance for the DeviceClassEnume"...
0x180010709  mov     ecx, r12d
0x18001070c  call    WiaTrace_TraceWithSubComp
0x180010711  mov     r9d, esi; int
0x180010714  mov     [rsp+410h+lpMem], rax; lpMem
0x180010719  lea     r8, aRegistrydevice; "RegistryDeviceEnumerator::CreateInstanc"...
0x180010720  call    WiaTrace_ProcessTrace_Ex
0x180010725  jmp     loc_18001051B
```
