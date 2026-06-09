# ServiceEventHandler::CreateInstance(void)

- ea: `0x18004bc70`
- end: `0x18004bee5`
- name: `?CreateInstance@ServiceEventHandler@@SAXXZ`
- size: `629`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800138a8`
- `0x1800174c4`
- `0x18002044c`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033884`
- `0x180033cc0`
- `0x18004bc70`
- `0x180078010`

## string_xrefs

- `0x18004bd97`: `ServiceEventHandler::CreateInstance`
- `0x18004bdca`: `ServiceEventHandler::CreateInstance`
- `0x18004be07`: `ServiceEventHandler::CreateInstance`
- `0x18004be3a`: `ServiceEventHandler::CreateInstance`
- `0x18004be77`: `ServiceEventHandler::CreateInstance`
- `0x18004beaa`: `ServiceEventHandler::CreateInstance`
- `0x18004bd83`: `CreateInstance failed to successfully Initialize a ServiceEventHandler object`
- `0x18004bdae`: `CreateInstance failed to successfully Initialize a ServiceEventHandler object`
- `0x18004be63`: `CreateInstance for the ServiceEventHandler failed to find the Dispatcher`
- `0x18004be8e`: `CreateInstance for the ServiceEventHandler failed to find the Dispatcher`
- `0x18004bdf3`: `CreateInstance failed to create a ServiceEventHandler due to lack of memory`
- `0x18004be1e`: `CreateInstance failed to create a ServiceEventHandler due to lack of memory`

## pseudocode

```c
void ServiceEventHandler::CreateInstance(void)
{
  Dispatcher *v0; // rbp
  struct SystemEventHandler *v1; // rax
  struct SystemEventHandler *v2; // rdi
  __int64 v3; // rcx
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  char *v9; // rcx
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  _BYTE v21[24]; // [rsp+38h] [rbp-160h] BYREF
  _QWORD v22[38]; // [rsp+50h] [rbp-148h] BYREF

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v21);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v22, L"Dispatcher");
  v0 = (Dispatcher *)ServiceComponentHolder::Get<Dispatcher>((__int64)v21, (__int64)v22);
  v22[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v22);
  v22[34] = 0;
  if ( v0 )
  {
    v1 = (struct SystemEventHandler *)operator new(0x28u);
    v2 = v1;
    if ( v1 )
    {
      *((_QWORD *)v1 + 1) = &ServiceEventHandler::`vbtable';
      *((_QWORD *)v1 + 3) = &CSimpleRefCount::`vftable';
      *((_DWORD *)v1 + 8) = 1;
      v3 = *((_QWORD *)v1 + 1);
      *(_QWORD *)v1 = &SystemEventHandler::`vftable'{for `SystemEventHandler'};
      *(_QWORD *)((char *)v1 + *(int *)(v3 + 4) + 8) = &SystemEventHandler::`vftable'{for `CSimpleRefCount'};
      *(_QWORD *)v1 = &ServiceEventHandler::`vftable'{for `SystemEventHandler'};
      *(_QWORD *)((char *)v1 + *(int *)(*((_QWORD *)v1 + 1) + 4LL) + 8) = &ServiceEventHandler::`vftable'{for `CSimpleRefCount'};
      *((_DWORD *)v1 + 4) = 1430812229;
      if ( (**(int (__fastcall ***)(struct SystemEventHandler *, _QWORD))v1)(v1, 0) < 0 )
      {
        v4 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "CreateInstance failed to successfully Initialize a ServiceEventHandler object");
        WriteDbgTraceWarningWI("ServiceEventHandler::CreateInstance", v4);
        WiaTrcLib::Free((WiaTrcLib *)v4, v5);
        lpMem = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "CreateInstance failed to successfully Initialize a ServiceEventHandler object");
        WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"ServiceEventHandler::CreateInstance", 2, lpMem);
      }
      else
      {
        Dispatcher::AddEventHandler(v0, v2);
      }
      v9 = (char *)v2 + *(int *)(*((_QWORD *)v2 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      v10 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "CreateInstance failed to create a ServiceEventHandler due to lack of memory");
      WriteDbgTraceWarningWI("ServiceEventHandler::CreateInstance", v10);
      WiaTrcLib::Free((WiaTrcLib *)v10, v11);
      v12 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "CreateInstance failed to create a ServiceEventHandler due to lack of memory");
      WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"ServiceEventHandler::CreateInstance", 2, v12);
    }
    v15 = (char *)v0 + *(int *)(*((_QWORD *)v0 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  else
  {
    v16 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "CreateInstance for the ServiceEventHandler failed to find the Dispatcher");
    WriteDbgTraceWarningWI("ServiceEventHandler::CreateInstance", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "CreateInstance for the ServiceEventHandler failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"ServiceEventHandler::CreateInstance", 2, v18);
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v21);
}

```

## disassembly

```asm
0x18004bc70  mov     [rsp+arg_0], rbx
0x18004bc75  mov     [rsp+arg_8], rbp
0x18004bc7a  push    rdi
0x18004bc7b  sub     rsp, 190h
0x18004bc82  mov     rax, cs:__security_cookie
0x18004bc89  xor     rax, rsp
0x18004bc8c  mov     [rsp+198h+var_18], rax
0x18004bc94  lea     rcx, [rsp+198h+var_160]; this
0x18004bc99  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18004bc9e  lea     rdx, aDispatcher; "Dispatcher"
0x18004bca5  lea     rcx, [rsp+198h+var_148]
0x18004bcaa  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004bcaf  lea     rdx, [rsp+198h+var_148]
0x18004bcb4  lea     rcx, [rsp+198h+var_160]
0x18004bcb9  call    ??$Get@VDispatcher@@@ServiceComponentHolder@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x18004bcbe  mov     rbp, rax
0x18004bcc1  lea     rcx, [rsp+198h+var_148]
0x18004bcc6  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18004bccd  mov     [rsp+198h+var_148], rax
0x18004bcd2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004bcd7  mov     [rsp+198h+var_38], 0
0x18004bce3  test    rbp, rbp
0x18004bce6  jz      loc_18004BE63
0x18004bcec  mov     ecx, 28h ; '('; Size
0x18004bcf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bcf6  mov     rdi, rax
0x18004bcf9  test    rax, rax
0x18004bcfc  jz      loc_18004BDF3
0x18004bd02  lea     rax, ??_8ServiceEventHandler@@7B@; const ServiceEventHandler::`vbtable'
0x18004bd09  xor     edx, edx
0x18004bd0b  mov     [rdi+8], rax
0x18004bd0f  lea     rax, ??_7CSimpleRefCount@@6B@; const CSimpleRefCount::`vftable'
0x18004bd16  mov     [rdi+18h], rax
0x18004bd1a  lea     rax, ??_7SystemEventHandler@@6B0@@; const SystemEventHandler::`vftable'{for `SystemEventHandler'}
0x18004bd21  mov     dword ptr [rdi+20h], 1
0x18004bd28  mov     rcx, [rdi+8]
0x18004bd2c  mov     [rdi], rax
0x18004bd2f  movsxd  rax, dword ptr [rcx+4]
0x18004bd33  lea     rcx, ??_7SystemEventHandler@@6BCSimpleRefCount@@@; const SystemEventHandler::`vftable'{for `CSimpleRefCount'}
0x18004bd3a  mov     [rax+rdi+8], rcx
0x18004bd3f  lea     rax, ??_7ServiceEventHandler@@6BSystemEventHandler@@@; const ServiceEventHandler::`vftable'{for `SystemEventHandler'}
0x18004bd46  mov     [rdi], rax
0x18004bd49  mov     rax, [rdi+8]
0x18004bd4d  movsxd  rcx, dword ptr [rax+4]
0x18004bd51  lea     rax, ??_7ServiceEventHandler@@6BCSimpleRefCount@@@; const ServiceEventHandler::`vftable'{for `CSimpleRefCount'}
0x18004bd58  mov     [rcx+rdi+8], rax
0x18004bd5d  mov     rcx, rdi
0x18004bd60  mov     dword ptr [rdi+10h], 55487645h
0x18004bd67  mov     rax, [rdi]
0x18004bd6a  mov     rax, [rax]
0x18004bd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd72  test    eax, eax
0x18004bd74  js      short loc_18004BD83
0x18004bd76  mov     rdx, rdi; struct SystemEventHandler *
0x18004bd79  mov     rcx, rbp; this
0x18004bd7c  call    ?AddEventHandler@Dispatcher@@QEAAJPEAVSystemEventHandler@@@Z; Dispatcher::AddEventHandler(SystemEventHandler *)
0x18004bd81  jmp     short loc_18004BDD6
0x18004bd83  lea     rdx, aCreateinstance_0; "CreateInstance failed to successfully I"...
0x18004bd8a  mov     ecx, 1
0x18004bd8f  call    WiaTrace_TraceLogWithSubComp
0x18004bd94  mov     rdx, rax; char *
0x18004bd97  lea     rcx, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004bd9e  mov     rbx, rax
0x18004bda1  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004bda6  mov     rcx, rbx; this
0x18004bda9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004bdae  lea     rdx, aCreateinstance_0; "CreateInstance failed to successfully I"...
0x18004bdb5  mov     ecx, 1
0x18004bdba  call    WiaTrace_TraceWithSubComp
0x18004bdbf  mov     r9d, 2; int
0x18004bdc5  mov     [rsp+198h+lpMem], rax; lpMem
0x18004bdca  lea     r8, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004bdd1  call    WiaTrace_ProcessTrace_Ex
0x18004bdd6  mov     rax, [rdi+8]
0x18004bdda  movsxd  rcx, dword ptr [rax+4]
0x18004bdde  add     rcx, 8
0x18004bde2  add     rcx, rdi
0x18004bde5  mov     rax, [rcx]
0x18004bde8  mov     rax, [rax+10h]
0x18004bdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdf1  jmp     short loc_18004BE46
0x18004bdf3  lea     rdx, aCreateinstance_6; "CreateInstance failed to create a Servi"...
0x18004bdfa  mov     ecx, 1
0x18004bdff  call    WiaTrace_TraceLogWithSubComp
0x18004be04  mov     rdx, rax; char *
0x18004be07  lea     rcx, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004be0e  mov     rbx, rax
0x18004be11  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004be16  mov     rcx, rbx; this
0x18004be19  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004be1e  lea     rdx, aCreateinstance_6; "CreateInstance failed to create a Servi"...
0x18004be25  mov     ecx, 1
0x18004be2a  call    WiaTrace_TraceWithSubComp
0x18004be2f  mov     r9d, 2; int
0x18004be35  mov     [rsp+198h+lpMem], rax; lpMem
0x18004be3a  lea     r8, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004be41  call    WiaTrace_ProcessTrace_Ex
0x18004be46  mov     rax, [rbp+8]
0x18004be4a  movsxd  rcx, dword ptr [rax+4]
0x18004be4e  add     rcx, 8
0x18004be52  add     rcx, rbp
0x18004be55  mov     rax, [rcx]
0x18004be58  mov     rax, [rax+10h]
0x18004be5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be61  jmp     short loc_18004BEB6
0x18004be63  lea     rdx, aCreateinstance_3; "CreateInstance for the ServiceEventHand"...
0x18004be6a  mov     ecx, 1
0x18004be6f  call    WiaTrace_TraceLogWithSubComp
0x18004be74  mov     rdx, rax; char *
0x18004be77  lea     rcx, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004be7e  mov     rbx, rax
0x18004be81  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004be86  mov     rcx, rbx; this
0x18004be89  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004be8e  lea     rdx, aCreateinstance_3; "CreateInstance for the ServiceEventHand"...
0x18004be95  mov     ecx, 1
0x18004be9a  call    WiaTrace_TraceWithSubComp
0x18004be9f  mov     r9d, 2; int
0x18004bea5  mov     [rsp+198h+lpMem], rax; lpMem
0x18004beaa  lea     r8, aServiceeventha; "ServiceEventHandler::CreateInstance"
0x18004beb1  call    WiaTrace_ProcessTrace_Ex
0x18004beb6  lea     rcx, [rsp+198h+var_160]; this
0x18004bebb  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x18004bec0  mov     rcx, [rsp+198h+var_18]
0x18004bec8  xor     rcx, rsp; StackCookie
0x18004becb  call    __security_check_cookie
0x18004bed0  lea     r11, [rsp+198h+var_8]
0x18004bed8  mov     rbx, [r11+10h]
0x18004bedc  mov     rbp, [r11+18h]
0x18004bee0  mov     rsp, r11
0x18004bee3  pop     rdi
0x18004bee4  retn
```
