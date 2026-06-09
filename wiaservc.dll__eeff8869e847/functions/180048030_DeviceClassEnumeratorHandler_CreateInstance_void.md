# DeviceClassEnumeratorHandler::CreateInstance(void)

- ea: `0x180048030`
- end: `0x180048296`
- name: `?CreateInstance@DeviceClassEnumeratorHandler@@SAXXZ`
- size: `614`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000f4fc`
- `0x18000fc60`
- `0x180011a94`
- `0x1800138a8`
- `0x1800174c4`
- `0x18002044c`
- `0x18002e900`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033884`
- `0x180033cc0`
- `0x180047e20`
- `0x180048030`
- `0x180078010`

## string_xrefs

- `0x18004813e`: `CreateInstance failed to create a DeviceClassEnumeratorHandler due to lack of memory`
- `0x180048169`: `CreateInstance failed to create a DeviceClassEnumeratorHandler due to lack of memory`
- `0x180048152`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x180048185`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x1800481c2`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x1800481f5`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x180048232`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x180048265`: `DeviceClassEnumeratorHandler::CreateInstance`
- `0x1800481ae`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the DeviceListManager`
- `0x1800481d9`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the DeviceListManager`
- `0x18004821e`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher`
- `0x180048249`: `CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher`

## pseudocode

```c
void DeviceClassEnumeratorHandler::CreateInstance(void)
{
  Dispatcher *v0; // rsi
  __int64 v1; // rax
  DeviceListManager *v2; // rdi
  DeviceClassEnumeratorHandler *v3; // rax
  struct DeviceEnumerator *v4; // rax
  struct DeviceEnumerator *v5; // rbx
  char *v6; // rcx
  char *v7; // rbx
  void *v8; // rdx
  void **lpMem; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  char *v12; // rcx
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rcx
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  _BYTE v24[16]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v25[38]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[38]; // [rsp+170h] [rbp+70h] BYREF

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v24);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v25, L"Dispatcher");
  v0 = (Dispatcher *)ServiceComponentHolder::Get<Dispatcher>((__int64)v24, (__int64)v25);
  v25[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v25);
  v25[34] = 0;
  if ( v0 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v26, L"DeviceListManager");
    v1 = ServiceComponentHolder::Get<DeviceListManager>((__int64)v24, (__int64)v26);
    v26[0] = &CSimpleStringBase<unsigned short>::`vftable';
    v2 = (DeviceListManager *)v1;
    CSimpleStringBase<unsigned short>::DeleteStorage(v26);
    v26[34] = 0;
    if ( v2 )
    {
      v3 = (DeviceClassEnumeratorHandler *)operator new(0x70u);
      if ( v3 && (v4 = DeviceClassEnumeratorHandler::DeviceClassEnumeratorHandler(v3), (v5 = v4) != 0) )
      {
        DeviceListManager::AddDeviceEnumerator(v2, v4);
        Dispatcher::AddEventHandler(v0, (struct DeviceEnumerator *)((char *)v5 + 16));
        v6 = (char *)v5 + *(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      }
      else
      {
        v7 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "CreateInstance failed to create a DeviceClassEnumeratorHandler due to lack of memory");
        WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateInstance", v7);
        WiaTrcLib::Free((WiaTrcLib *)v7, v8);
        lpMem = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "CreateInstance failed to create a DeviceClassEnumeratorHandler due to lack of memory");
        WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"DeviceClassEnumeratorHandler::CreateInstance", 2, lpMem);
      }
      v12 = (char *)v2 + *(int *)(*((_QWORD *)v2 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    else
    {
      v13 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "CreateInstance for the DeviceClassEnumeratorHandler failed to find the DeviceListManager");
      WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateInstance", v13);
      WiaTrcLib::Free((WiaTrcLib *)v13, v14);
      v15 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "CreateInstance for the DeviceClassEnumeratorHandler failed to find the DeviceListManager");
      WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"DeviceClassEnumeratorHandler::CreateInstance", 2, v15);
    }
    v18 = (char *)v0 + *(int *)(*((_QWORD *)v0 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  else
  {
    v19 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher");
    WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::CreateInstance", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "CreateInstance for the DeviceClassEnumeratorHandler failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"DeviceClassEnumeratorHandler::CreateInstance", 2, v21);
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v24);
}

```

## disassembly

```asm
0x180048030  push    rbp
0x180048032  push    rbx
0x180048033  push    rsi
0x180048034  push    rdi
0x180048035  lea     rbp, [rsp-1B8h]
0x18004803d  sub     rsp, 2B8h
0x180048044  mov     rax, cs:__security_cookie
0x18004804b  xor     rax, rsp
0x18004804e  mov     [rbp+1D0h+var_30], rax
0x180048055  lea     rcx, [rsp+2D0h+var_2A0]; this
0x18004805a  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18004805f  lea     rdx, aDispatcher; "Dispatcher"
0x180048066  lea     rcx, [rsp+2D0h+var_290]
0x18004806b  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180048070  lea     rdx, [rsp+2D0h+var_290]
0x180048075  lea     rcx, [rsp+2D0h+var_2A0]
0x18004807a  call    ??$Get@VDispatcher@@@ServiceComponentHolder@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x18004807f  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180048086  mov     rsi, rax
0x180048089  lea     rcx, [rsp+2D0h+var_290]
0x18004808e  mov     [rsp+2D0h+var_290], rbx
0x180048093  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180048098  mov     [rbp+1D0h+var_180], 0
0x1800480a0  test    rsi, rsi
0x1800480a3  jz      loc_18004821E
0x1800480a9  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x1800480b0  lea     rcx, [rbp+1D0h+var_160]
0x1800480b4  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800480b9  lea     rdx, [rbp+1D0h+var_160]
0x1800480bd  lea     rcx, [rsp+2D0h+var_2A0]
0x1800480c2  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x1800480c7  lea     rcx, [rbp+1D0h+var_160]
0x1800480cb  mov     [rbp+1D0h+var_160], rbx
0x1800480cf  mov     rdi, rax
0x1800480d2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800480d7  mov     [rbp+1D0h+var_50], 0
0x1800480e2  test    rdi, rdi
0x1800480e5  jz      loc_1800481AE
0x1800480eb  mov     ecx, 70h ; 'p'; Size
0x1800480f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800480f5  test    rax, rax
0x1800480f8  jz      short loc_18004813E
0x1800480fa  mov     rcx, rax; this
0x1800480fd  call    ??0DeviceClassEnumeratorHandler@@QEAA@XZ; DeviceClassEnumeratorHandler::DeviceClassEnumeratorHandler(void)
0x180048102  mov     rbx, rax
0x180048105  test    rax, rax
0x180048108  jz      short loc_18004813E
0x18004810a  mov     rdx, rax; struct DeviceEnumerator *
0x18004810d  mov     rcx, rdi; this
0x180048110  call    ?AddDeviceEnumerator@DeviceListManager@@QEAAJPEAVDeviceEnumerator@@@Z; DeviceListManager::AddDeviceEnumerator(DeviceEnumerator *)
0x180048115  lea     rdx, [rbx+10h]; struct SystemEventHandler *
0x180048119  mov     rcx, rsi; this
0x18004811c  call    ?AddEventHandler@Dispatcher@@QEAAJPEAVSystemEventHandler@@@Z; Dispatcher::AddEventHandler(SystemEventHandler *)
0x180048121  mov     rcx, [rbx+8]
0x180048125  movsxd  rcx, dword ptr [rcx+4]
0x180048129  add     rcx, 8
0x18004812d  add     rcx, rbx
0x180048130  mov     rax, [rcx]
0x180048133  mov     rax, [rax+10h]
0x180048137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004813c  jmp     short loc_180048191
0x18004813e  lea     rdx, aCreateinstance_12; "CreateInstance failed to create a Devic"...
0x180048145  mov     ecx, 1
0x18004814a  call    WiaTrace_TraceLogWithSubComp
0x18004814f  mov     rdx, rax; char *
0x180048152  lea     rcx, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x180048159  mov     rbx, rax
0x18004815c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180048161  mov     rcx, rbx; this
0x180048164  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180048169  lea     rdx, aCreateinstance_12; "CreateInstance failed to create a Devic"...
0x180048170  mov     ecx, 1
0x180048175  call    WiaTrace_TraceWithSubComp
0x18004817a  mov     r9d, 2; int
0x180048180  mov     [rsp+2D0h+lpMem], rax; lpMem
0x180048185  lea     r8, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x18004818c  call    WiaTrace_ProcessTrace_Ex
0x180048191  mov     rax, [rdi+8]
0x180048195  movsxd  rcx, dword ptr [rax+4]
0x180048199  add     rcx, 8
0x18004819d  add     rcx, rdi
0x1800481a0  mov     rax, [rcx]
0x1800481a3  mov     rax, [rax+10h]
0x1800481a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481ac  jmp     short loc_180048201
0x1800481ae  lea     rdx, aCreateinstance_18; "CreateInstance for the DeviceClassEnume"...
0x1800481b5  mov     ecx, 1
0x1800481ba  call    WiaTrace_TraceLogWithSubComp
0x1800481bf  mov     rdx, rax; char *
0x1800481c2  lea     rcx, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x1800481c9  mov     rbx, rax
0x1800481cc  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800481d1  mov     rcx, rbx; this
0x1800481d4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800481d9  lea     rdx, aCreateinstance_18; "CreateInstance for the DeviceClassEnume"...
0x1800481e0  mov     ecx, 1
0x1800481e5  call    WiaTrace_TraceWithSubComp
0x1800481ea  mov     r9d, 2; int
0x1800481f0  mov     [rsp+2D0h+lpMem], rax; lpMem
0x1800481f5  lea     r8, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x1800481fc  call    WiaTrace_ProcessTrace_Ex
0x180048201  mov     rax, [rsi+8]
0x180048205  movsxd  rcx, dword ptr [rax+4]
0x180048209  add     rcx, 8
0x18004820d  add     rcx, rsi
0x180048210  mov     rax, [rcx]
0x180048213  mov     rax, [rax+10h]
0x180048217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004821c  jmp     short loc_180048271
0x18004821e  lea     rdx, aCreateinstance_5; "CreateInstance for the DeviceClassEnume"...
0x180048225  mov     ecx, 1
0x18004822a  call    WiaTrace_TraceLogWithSubComp
0x18004822f  mov     rdx, rax; char *
0x180048232  lea     rcx, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x180048239  mov     rbx, rax
0x18004823c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180048241  mov     rcx, rbx; this
0x180048244  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180048249  lea     rdx, aCreateinstance_5; "CreateInstance for the DeviceClassEnume"...
0x180048250  mov     ecx, 1
0x180048255  call    WiaTrace_TraceWithSubComp
0x18004825a  mov     r9d, 2; int
0x180048260  mov     [rsp+2D0h+lpMem], rax; lpMem
0x180048265  lea     r8, aDeviceclassenu_0; "DeviceClassEnumeratorHandler::CreateIns"...
0x18004826c  call    WiaTrace_ProcessTrace_Ex
0x180048271  lea     rcx, [rsp+2D0h+var_2A0]; this
0x180048276  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x18004827b  mov     rcx, [rbp+1D0h+var_30]
0x180048282  xor     rcx, rsp; StackCookie
0x180048285  call    __security_check_cookie
0x18004828a  add     rsp, 2B8h
0x180048291  pop     rdi
0x180048292  pop     rsi
0x180048293  pop     rbx
0x180048294  pop     rbp
0x180048295  retn
```
