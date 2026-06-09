# PowerEventHandler::CreateInstance(void)

- ea: `0x180047b80`
- end: `0x180047e00`
- name: `?CreateInstance@PowerEventHandler@@SAXXZ`
- size: `640`
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
- `0x180047b80`
- `0x180078010`

## string_xrefs

- `0x180047c9e`: `CreateInstance failed to successfully Initialize a PowerEventHandler object`
- `0x180047cc9`: `CreateInstance failed to successfully Initialize a PowerEventHandler object`
- `0x180047cb2`: `PowerEventHandler::CreateInstance`
- `0x180047ce5`: `PowerEventHandler::CreateInstance`
- `0x180047d22`: `PowerEventHandler::CreateInstance`
- `0x180047d55`: `PowerEventHandler::CreateInstance`
- `0x180047d92`: `PowerEventHandler::CreateInstance`
- `0x180047dc5`: `PowerEventHandler::CreateInstance`
- `0x180047d0e`: `CreateInstance failed to create a PowerEventHandler due to lack of memory`
- `0x180047d39`: `CreateInstance failed to create a PowerEventHandler due to lack of memory`
- `0x180047d7e`: `CreateInstance for the PowerEventHandler failed to find the Dispatcher`
- `0x180047da9`: `CreateInstance for the PowerEventHandler failed to find the Dispatcher`

## pseudocode

```c
void PowerEventHandler::CreateInstance(void)
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
    v1 = (struct SystemEventHandler *)operator new(0x30u);
    v2 = v1;
    if ( v1 )
    {
      *((_QWORD *)v1 + 1) = &PowerEventHandler::`vbtable';
      *((_QWORD *)v1 + 4) = &CSimpleRefCount::`vftable';
      *((_DWORD *)v1 + 10) = 1;
      v3 = *((_QWORD *)v1 + 1);
      *(_QWORD *)v1 = &SystemEventHandler::`vftable'{for `SystemEventHandler'};
      *(_QWORD *)((char *)v1 + *(int *)(v3 + 4) + 8) = &SystemEventHandler::`vftable'{for `CSimpleRefCount'};
      *(_QWORD *)v1 = &PowerEventHandler::`vftable'{for `SystemEventHandler'};
      *((_QWORD *)v1 + 2) = &PowerEventHandler::`vftable'{for `EnumDeviceInterface'};
      *(_QWORD *)((char *)v1 + *(int *)(*((_QWORD *)v1 + 1) + 4LL) + 8) = &PowerEventHandler::`vftable'{for `CSimpleRefCount'};
      *((_DWORD *)v1 + 6) = 1430812229;
      if ( (**(int (__fastcall ***)(struct SystemEventHandler *, _QWORD))v1)(v1, 0) < 0 )
      {
        v4 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "CreateInstance failed to successfully Initialize a PowerEventHandler object");
        WriteDbgTraceWarningWI("PowerEventHandler::CreateInstance", v4);
        WiaTrcLib::Free((WiaTrcLib *)v4, v5);
        lpMem = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "CreateInstance failed to successfully Initialize a PowerEventHandler object");
        WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"PowerEventHandler::CreateInstance", 2, lpMem);
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
                      "CreateInstance failed to create a PowerEventHandler due to lack of memory");
      WriteDbgTraceWarningWI("PowerEventHandler::CreateInstance", v10);
      WiaTrcLib::Free((WiaTrcLib *)v10, v11);
      v12 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "CreateInstance failed to create a PowerEventHandler due to lack of memory");
      WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"PowerEventHandler::CreateInstance", 2, v12);
    }
    v15 = (char *)v0 + *(int *)(*((_QWORD *)v0 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  else
  {
    v16 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "CreateInstance for the PowerEventHandler failed to find the Dispatcher");
    WriteDbgTraceWarningWI("PowerEventHandler::CreateInstance", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "CreateInstance for the PowerEventHandler failed to find the Dispatcher");
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"PowerEventHandler::CreateInstance", 2, v18);
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v21);
}

```

## disassembly

```asm
0x180047b80  mov     [rsp+arg_0], rbx
0x180047b85  mov     [rsp+arg_8], rbp
0x180047b8a  push    rdi
0x180047b8b  sub     rsp, 190h
0x180047b92  mov     rax, cs:__security_cookie
0x180047b99  xor     rax, rsp
0x180047b9c  mov     [rsp+198h+var_18], rax
0x180047ba4  lea     rcx, [rsp+198h+var_160]; this
0x180047ba9  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180047bae  lea     rdx, aDispatcher; "Dispatcher"
0x180047bb5  lea     rcx, [rsp+198h+var_148]
0x180047bba  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180047bbf  lea     rdx, [rsp+198h+var_148]
0x180047bc4  lea     rcx, [rsp+198h+var_160]
0x180047bc9  call    ??$Get@VDispatcher@@@ServiceComponentHolder@@QEAAPEAVDispatcher@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<Dispatcher>(CSimpleStringBase<ushort> const &)
0x180047bce  mov     rbp, rax
0x180047bd1  lea     rcx, [rsp+198h+var_148]
0x180047bd6  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180047bdd  mov     [rsp+198h+var_148], rax
0x180047be2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180047be7  mov     [rsp+198h+var_38], 0
0x180047bf3  test    rbp, rbp
0x180047bf6  jz      loc_180047D7E
0x180047bfc  mov     ecx, 30h ; '0'; Size
0x180047c01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047c06  mov     rdi, rax
0x180047c09  test    rax, rax
0x180047c0c  jz      loc_180047D0E
0x180047c12  lea     rax, ??_8PowerEventHandler@@7B@; const PowerEventHandler::`vbtable'
0x180047c19  xor     edx, edx
0x180047c1b  mov     [rdi+8], rax
0x180047c1f  lea     rax, ??_7CSimpleRefCount@@6B@; const CSimpleRefCount::`vftable'
0x180047c26  mov     [rdi+20h], rax
0x180047c2a  lea     rax, ??_7SystemEventHandler@@6B0@@; const SystemEventHandler::`vftable'{for `SystemEventHandler'}
0x180047c31  mov     dword ptr [rdi+28h], 1
0x180047c38  mov     rcx, [rdi+8]
0x180047c3c  mov     [rdi], rax
0x180047c3f  movsxd  rax, dword ptr [rcx+4]
0x180047c43  lea     rcx, ??_7SystemEventHandler@@6BCSimpleRefCount@@@; const SystemEventHandler::`vftable'{for `CSimpleRefCount'}
0x180047c4a  mov     [rax+rdi+8], rcx
0x180047c4f  lea     rax, ??_7PowerEventHandler@@6BSystemEventHandler@@@; const PowerEventHandler::`vftable'{for `SystemEventHandler'}
0x180047c56  mov     [rdi], rax
0x180047c59  lea     rax, ??_7PowerEventHandler@@6BEnumDeviceInterface@@@; const PowerEventHandler::`vftable'{for `EnumDeviceInterface'}
0x180047c60  mov     [rdi+10h], rax
0x180047c64  mov     rax, [rdi+8]
0x180047c68  movsxd  rcx, dword ptr [rax+4]
0x180047c6c  lea     rax, ??_7PowerEventHandler@@6BCSimpleRefCount@@@; const PowerEventHandler::`vftable'{for `CSimpleRefCount'}
0x180047c73  mov     [rcx+rdi+8], rax
0x180047c78  mov     rcx, rdi
0x180047c7b  mov     dword ptr [rdi+18h], 55487645h
0x180047c82  mov     rax, [rdi]
0x180047c85  mov     rax, [rax]
0x180047c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c8d  test    eax, eax
0x180047c8f  js      short loc_180047C9E
0x180047c91  mov     rdx, rdi; struct SystemEventHandler *
0x180047c94  mov     rcx, rbp; this
0x180047c97  call    ?AddEventHandler@Dispatcher@@QEAAJPEAVSystemEventHandler@@@Z; Dispatcher::AddEventHandler(SystemEventHandler *)
0x180047c9c  jmp     short loc_180047CF1
0x180047c9e  lea     rdx, aCreateinstance_10; "CreateInstance failed to successfully I"...
0x180047ca5  mov     ecx, 1
0x180047caa  call    WiaTrace_TraceLogWithSubComp
0x180047caf  mov     rdx, rax; char *
0x180047cb2  lea     rcx, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047cb9  mov     rbx, rax
0x180047cbc  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180047cc1  mov     rcx, rbx; this
0x180047cc4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180047cc9  lea     rdx, aCreateinstance_10; "CreateInstance failed to successfully I"...
0x180047cd0  mov     ecx, 1
0x180047cd5  call    WiaTrace_TraceWithSubComp
0x180047cda  mov     r9d, 2; int
0x180047ce0  mov     [rsp+198h+lpMem], rax; lpMem
0x180047ce5  lea     r8, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047cec  call    WiaTrace_ProcessTrace_Ex
0x180047cf1  mov     rax, [rdi+8]
0x180047cf5  movsxd  rcx, dword ptr [rax+4]
0x180047cf9  add     rcx, 8
0x180047cfd  add     rcx, rdi
0x180047d00  mov     rax, [rcx]
0x180047d03  mov     rax, [rax+10h]
0x180047d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d0c  jmp     short loc_180047D61
0x180047d0e  lea     rdx, aCreateinstance_15; "CreateInstance failed to create a Power"...
0x180047d15  mov     ecx, 1
0x180047d1a  call    WiaTrace_TraceLogWithSubComp
0x180047d1f  mov     rdx, rax; char *
0x180047d22  lea     rcx, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047d29  mov     rbx, rax
0x180047d2c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180047d31  mov     rcx, rbx; this
0x180047d34  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180047d39  lea     rdx, aCreateinstance_15; "CreateInstance failed to create a Power"...
0x180047d40  mov     ecx, 1
0x180047d45  call    WiaTrace_TraceWithSubComp
0x180047d4a  mov     r9d, 2; int
0x180047d50  mov     [rsp+198h+lpMem], rax; lpMem
0x180047d55  lea     r8, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047d5c  call    WiaTrace_ProcessTrace_Ex
0x180047d61  mov     rax, [rbp+8]
0x180047d65  movsxd  rcx, dword ptr [rax+4]
0x180047d69  add     rcx, 8
0x180047d6d  add     rcx, rbp
0x180047d70  mov     rax, [rcx]
0x180047d73  mov     rax, [rax+10h]
0x180047d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d7c  jmp     short loc_180047DD1
0x180047d7e  lea     rdx, aCreateinstance_16; "CreateInstance for the PowerEventHandle"...
0x180047d85  mov     ecx, 1
0x180047d8a  call    WiaTrace_TraceLogWithSubComp
0x180047d8f  mov     rdx, rax; char *
0x180047d92  lea     rcx, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047d99  mov     rbx, rax
0x180047d9c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180047da1  mov     rcx, rbx; this
0x180047da4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180047da9  lea     rdx, aCreateinstance_16; "CreateInstance for the PowerEventHandle"...
0x180047db0  mov     ecx, 1
0x180047db5  call    WiaTrace_TraceWithSubComp
0x180047dba  mov     r9d, 2; int
0x180047dc0  mov     [rsp+198h+lpMem], rax; lpMem
0x180047dc5  lea     r8, aPowereventhand_2; "PowerEventHandler::CreateInstance"
0x180047dcc  call    WiaTrace_ProcessTrace_Ex
0x180047dd1  lea     rcx, [rsp+198h+var_160]; this
0x180047dd6  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x180047ddb  mov     rcx, [rsp+198h+var_18]
0x180047de3  xor     rcx, rsp; StackCookie
0x180047de6  call    __security_check_cookie
0x180047deb  lea     r11, [rsp+198h+var_8]
0x180047df3  mov     rbx, [r11+10h]
0x180047df7  mov     rbp, [r11+18h]
0x180047dfb  mov     rsp, r11
0x180047dfe  pop     rdi
0x180047dff  retn
```
