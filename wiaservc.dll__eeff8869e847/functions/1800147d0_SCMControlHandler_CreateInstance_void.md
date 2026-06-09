# SCMControlHandler::CreateInstance(void)

- ea: `0x1800147d0`
- end: `0x180014a68`
- name: `?CreateInstance@SCMControlHandler@@SAXXZ`
- size: `664`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000f4fc`
- `0x1800138a8`
- `0x1800147d0`
- `0x180014a70`
- `0x180014b9c`
- `0x180014ef8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x180078010`

## string_xrefs

- `0x180014893`: `ServiceStatus`
- `0x1800148cb`: `Could not store (%ws) because the ServiceComponentHolder is NULL`
- `0x1800148fd`: `Could not store (%ws) because the ServiceComponentHolder is NULL`
- `0x1800148df`: `ServiceComponentHolder::Set`
- `0x180014919`: `ServiceComponentHolder::Set`
- `0x18001496b`: `CreateInstance failed to create a SCMControlHandler due to lack of memory`
- `0x180014996`: `CreateInstance failed to create a SCMControlHandler due to lack of memory`
- `0x18001497f`: `SCMControlHandler::CreateInstance`
- `0x1800149b2`: `SCMControlHandler::CreateInstance`
- `0x1800149ef`: `SCMControlHandler::CreateInstance`
- `0x180014a22`: `SCMControlHandler::CreateInstance`
- `0x1800149db`: `CreateInstance for the SCMControlHandler failed to find the Dispatcher`
- `0x180014a06`: `CreateInstance for the SCMControlHandler failed to find the Dispatcher`

## pseudocode

```c
void SCMControlHandler::CreateInstance(void)
{
  __int64 v0; // rax
  Dispatcher *v1; // r14
  __int64 v2; // rsi
  SCMControlHandler *v3; // rax
  SCMControlHandler *v4; // rdi
  __int64 v5; // rbx
  char *v6; // rbx
  void *v7; // rdx
  void **lpMem; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  char *v11; // rcx
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rcx
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  char v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  const unsigned __int64 *v26; // [rsp+40h] [rbp-C0h] BYREF
  char v27; // [rsp+48h] [rbp-B8h] BYREF
  void *v28; // [rsp+148h] [rbp+48h]
  __int64 v29; // [rsp+150h] [rbp+50h]
  const unsigned __int64 *v30; // [rsp+170h] [rbp+70h] BYREF
  char v31; // [rsp+178h] [rbp+78h] BYREF
  void *v32; // [rsp+278h] [rbp+178h]

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v24);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v26, L"Dispatcher");
  v0 = ServiceComponentHolder::Get<Dispatcher>((__int64)v24, (__int64)&v26);
  v26 = &CSimpleStringBase<unsigned short>::`vftable';
  v1 = (Dispatcher *)v0;
  if ( v28 && v28 != &v27 )
    operator delete(v28);
  v2 = v25;
  v28 = 0;
  v29 = 0;
  if ( v1 )
  {
    v3 = (SCMControlHandler *)operator new(0xF8u);
    if ( v3 )
      v4 = SCMControlHandler::SCMControlHandler(v3);
    else
      v4 = 0;
    if ( v4 )
    {
      v5 = *(int *)(*((_QWORD *)v4 + 1) + 4LL);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v30, L"ServiceStatus");
      if ( v2 )
      {
        CSimpleRefMap<CSimpleStringBase<unsigned short>>::Set(v2, &v30, (char *)v4 + v5 + 8, v4);
      }
      else
      {
        v6 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "Could not store (%ws) because the ServiceComponentHolder is NULL",
                       v32);
        WriteDbgTraceWarningWI("ServiceComponentHolder::Set", v6);
        WiaTrcLib::Free((WiaTrcLib *)v6, v7);
        lpMem = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "Could not store (%ws) because the ServiceComponentHolder is NULL",
                           v32);
        WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"ServiceComponentHolder::Set", 2, lpMem);
      }
      v30 = &CSimpleStringBase<unsigned short>::`vftable';
      if ( v32 && v32 != &v31 )
        operator delete(v32);
      Dispatcher::AddEventSource(v1, v4);
      v11 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    else
    {
      v12 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "CreateInstance failed to create a SCMControlHandler due to lack of memory");
      WriteDbgTraceWarningWI("SCMControlHandler::CreateInstance", v12);
      WiaTrcLib::Free((WiaTrcLib *)v12, v13);
      v14 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "CreateInstance failed to create a SCMControlHandler due to lack of memory");
      WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"SCMControlHandler::CreateInstance", 2, v14);
    }
    v17 = (char *)v1 + *(int *)(*((_QWORD *)v1 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  else
  {
    v18 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "CreateInstance for the SCMControlHandler failed to find the Dispatcher");
    WriteDbgTraceWarningWI("SCMControlHandler::CreateInstance", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v20 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "CreateInstance for the SCMControlHandler failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"SCMControlHandler::CreateInstance", 2, v20);
  }
  if ( v2 )
  {
    v23 = v2 + *(int *)(*(_QWORD *)v2 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
}

```

## disassembly

```asm
0x1800147d0  push    rbp
0x1800147d2  push    rbx
0x1800147d3  push    rsi
0x1800147d4  push    rdi
0x1800147d5  push    r12
0x1800147d7  push    r14
0x1800147d9  lea     rbp, [rsp-1B8h]
0x1800147e1  sub     rsp, 2B8h
0x1800147e8  mov     rax, cs:__security_cookie
0x1800147ef  xor     rax, rsp
0x1800147f2  mov     [rbp+1E0h+var_40], rax
0x1800147f9  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800147fe  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180014803  lea     rdx, aDispatcher; "Dispatcher"
0x18001480a  lea     rcx, [rsp+2E0h+var_2A0]
0x18001480f  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180014814  lea     rdx, [rsp+2E0h+var_2A0]
0x180014819  lea     rcx, [rsp+2E0h+var_2B0]
0x18001481e  call    ??$Get@VDispatcher@@@ServiceComponentHolder@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x180014823  mov     rcx, [rbp+1E0h+var_198]; void *
0x180014827  lea     r12, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18001482e  mov     [rsp+2E0h+var_2A0], r12
0x180014833  mov     r14, rax
0x180014836  test    rcx, rcx
0x180014839  jz      short loc_18001484A
0x18001483b  lea     rax, [rsp+2E0h+var_298]
0x180014840  cmp     rcx, rax
0x180014843  jz      short loc_18001484A
0x180014845  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001484a  mov     rsi, [rsp+2E0h+var_2A8]
0x18001484f  mov     [rbp+1E0h+var_198], 0
0x180014857  mov     [rbp+1E0h+var_190], 0
0x18001485f  test    r14, r14
0x180014862  jz      loc_1800149DB
0x180014868  mov     ecx, 0F8h; Size
0x18001486d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014872  test    rax, rax
0x180014875  jz      short loc_180014884
0x180014877  mov     rcx, rax; this
0x18001487a  call    ??0SCMControlHandler@@QEAA@XZ; SCMControlHandler::SCMControlHandler(void)
0x18001487f  mov     rdi, rax
0x180014882  jmp     short loc_180014886
0x180014884  xor     edi, edi
0x180014886  test    rdi, rdi
0x180014889  jz      loc_18001496B
0x18001488f  mov     rax, [rdi+8]
0x180014893  lea     rdx, aServicestatus; "ServiceStatus"
0x18001489a  lea     rcx, [rbp+1E0h+var_170]
0x18001489e  movsxd  rbx, dword ptr [rax+4]
0x1800148a2  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800148a7  test    rsi, rsi
0x1800148aa  jz      short loc_1800148C4
0x1800148ac  lea     r8, [rbx+8]
0x1800148b0  mov     r9, rdi
0x1800148b3  add     r8, rdi
0x1800148b6  lea     rdx, [rbp+1E0h+var_170]
0x1800148ba  mov     rcx, rsi
0x1800148bd  call    ?Set@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAA_NAEBV?$CSimpleStringBase@G@@PEAVCSimpleRefCount@@PEAX@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Set(CSimpleStringBase<ushort> const &,CSimpleRefCount *,void *)
0x1800148c2  jmp     short loc_180014925
0x1800148c4  mov     r8, [rbp+1E0h+var_68]
0x1800148cb  lea     rdx, aCouldNotStoreW; "Could not store (%ws) because the Servi"...
0x1800148d2  mov     ecx, 1
0x1800148d7  call    WiaTrace_TraceLogWithSubComp
0x1800148dc  mov     rdx, rax; char *
0x1800148df  lea     rcx, aServicecompone_0; "ServiceComponentHolder::Set"
0x1800148e6  mov     rbx, rax
0x1800148e9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800148ee  mov     rcx, rbx; this
0x1800148f1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800148f6  mov     r8, [rbp+1E0h+var_68]
0x1800148fd  lea     rdx, aCouldNotStoreW; "Could not store (%ws) because the Servi"...
0x180014904  mov     ecx, 1
0x180014909  call    WiaTrace_TraceWithSubComp
0x18001490e  mov     r9d, 2; int
0x180014914  mov     [rsp+2E0h+lpMem], rax; lpMem
0x180014919  lea     r8, aServicecompone_0; "ServiceComponentHolder::Set"
0x180014920  call    WiaTrace_ProcessTrace_Ex
0x180014925  mov     rcx, [rbp+1E0h+var_68]; void *
0x18001492c  mov     [rbp+1E0h+var_170], r12
0x180014930  test    rcx, rcx
0x180014933  jz      short loc_180014943
0x180014935  lea     rax, [rbp+1E0h+var_168]
0x180014939  cmp     rcx, rax
0x18001493c  jz      short loc_180014943
0x18001493e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014943  mov     rdx, rdi; struct SystemEventSource *
0x180014946  mov     rcx, r14; this
0x180014949  call    ?AddEventSource@Dispatcher@@QEAAJPEAVSystemEventSource@@@Z; Dispatcher::AddEventSource(SystemEventSource *)
0x18001494e  mov     rax, [rdi+8]
0x180014952  movsxd  rcx, dword ptr [rax+4]
0x180014956  add     rcx, 8
0x18001495a  add     rcx, rdi
0x18001495d  mov     rax, [rcx]
0x180014960  mov     rax, [rax+10h]
0x180014964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014969  jmp     short loc_1800149BE
0x18001496b  lea     rdx, aCreateinstance_2; "CreateInstance failed to create a SCMCo"...
0x180014972  mov     ecx, 1
0x180014977  call    WiaTrace_TraceLogWithSubComp
0x18001497c  mov     rdx, rax; char *
0x18001497f  lea     rcx, aScmcontrolhand; "SCMControlHandler::CreateInstance"
0x180014986  mov     rbx, rax
0x180014989  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001498e  mov     rcx, rbx; this
0x180014991  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014996  lea     rdx, aCreateinstance_2; "CreateInstance failed to create a SCMCo"...
0x18001499d  mov     ecx, 1
0x1800149a2  call    WiaTrace_TraceWithSubComp
0x1800149a7  mov     r9d, 2; int
0x1800149ad  mov     [rsp+2E0h+lpMem], rax; lpMem
0x1800149b2  lea     r8, aScmcontrolhand; "SCMControlHandler::CreateInstance"
0x1800149b9  call    WiaTrace_ProcessTrace_Ex
0x1800149be  mov     rax, [r14+8]
0x1800149c2  movsxd  rcx, dword ptr [rax+4]
0x1800149c6  add     rcx, 8
0x1800149ca  add     rcx, r14
0x1800149cd  mov     rax, [rcx]
0x1800149d0  mov     rax, [rax+10h]
0x1800149d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d9  jmp     short loc_180014A2E
0x1800149db  lea     rdx, aCreateinstance_13; "CreateInstance for the SCMControlHandle"...
0x1800149e2  mov     ecx, 1
0x1800149e7  call    WiaTrace_TraceLogWithSubComp
0x1800149ec  mov     rdx, rax; char *
0x1800149ef  lea     rcx, aScmcontrolhand; "SCMControlHandler::CreateInstance"
0x1800149f6  mov     rbx, rax
0x1800149f9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800149fe  mov     rcx, rbx; this
0x180014a01  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014a06  lea     rdx, aCreateinstance_13; "CreateInstance for the SCMControlHandle"...
0x180014a0d  mov     ecx, 1
0x180014a12  call    WiaTrace_TraceWithSubComp
0x180014a17  mov     r9d, 2; int
0x180014a1d  mov     [rsp+2E0h+lpMem], rax; lpMem
0x180014a22  lea     r8, aScmcontrolhand; "SCMControlHandler::CreateInstance"
0x180014a29  call    WiaTrace_ProcessTrace_Ex
0x180014a2e  test    rsi, rsi
0x180014a31  jz      short loc_180014A49
0x180014a33  mov     rax, [rsi]
0x180014a36  movsxd  rcx, dword ptr [rax+4]
0x180014a3a  add     rcx, rsi
0x180014a3d  mov     rax, [rcx]
0x180014a40  mov     rax, [rax+10h]
0x180014a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a49  mov     rcx, [rbp+1E0h+var_40]
0x180014a50  xor     rcx, rsp; StackCookie
0x180014a53  call    __security_check_cookie
0x180014a58  add     rsp, 2B8h
0x180014a5f  pop     r14
0x180014a61  pop     r12
0x180014a63  pop     rdi
0x180014a64  pop     rsi
0x180014a65  pop     rbx
0x180014a66  pop     rbp
0x180014a67  retn
```
