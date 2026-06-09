# SharedAccessSvcMgr::Start(ulong,ulong,bool)

- ea: `0x18000d584`
- end: `0x18000d734`
- name: `?Start@SharedAccessSvcMgr@@QEAAJKK_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(SharedAccessSvcMgr *this, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001e4a4`

## callees

- `0x18000bf74`
- `0x18000d134`
- `0x18000d3ac`
- `0x18000d584`
- `0x18000d73c`
- `0x18000d8e4`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18000d679`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18000d679`
- `HNetCfgClient!HNetCfgStartSharing` at `0x18000d62d`
- `HNetCfgClient!HNetCfgStartSharing` at `0x18000d62d`

## pseudocode

```c
__int64 __fastcall SharedAccessSvcMgr::Start(SharedAccessSvcMgr *this, unsigned int a2, unsigned int a3, char a4)
{
  const WCHAR *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  _DWORD *v11; // rsi
  _DWORD *v12; // r14
  int started; // eax
  TetheringServiceTelemetry *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax

  v8 = (const WCHAR *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
  }
  v9 = SharedAccessSvcMgr::SetPrivateAddress(v8, a4);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids,
        (unsigned int)v9);
    }
    v11 = (_DWORD *)((char *)this + 28);
    v12 = (_DWORD *)((char *)this + 32);
    goto LABEL_27;
  }
  v11 = (_DWORD *)((char *)this + 28);
  v12 = (_DWORD *)((char *)this + 32);
  *((_DWORD *)this + 7) = a2;
  *((_DWORD *)this + 8) = a3;
  started = HNetCfgStartSharing(a2, a3);
  v10 = started;
  if ( started < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_27;
    }
    v15 = 19;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, (unsigned int)started);
LABEL_27:
    SharedAccessSvcMgr::Stop(this);
    *v11 = 0;
    *v12 = 0;
    goto LABEL_18;
  }
  v16 = SubscribeServiceChangeNotifications(
          *((_QWORD *)this + 1),
          2,
          SharedAccessSvcMgr::ScmEventsCallback,
          this,
          (char *)this + 16);
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v16);
    }
  }
  else
  {
    started = SharedAccessSvcMgr::NotifyUpdatePortMapping(this);
    v10 = started;
    if ( started < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_27;
      }
      v15 = 21;
      goto LABEL_26;
    }
  }
  *((_BYTE *)this + 24) = 1;
LABEL_18:
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000d584  push    rbx
0x18000d586  push    rbp
0x18000d587  push    rsi
0x18000d588  push    rdi
0x18000d589  push    r12
0x18000d58b  push    r13
0x18000d58d  push    r14
0x18000d58f  push    r15
0x18000d591  sub     rsp, 38h
0x18000d595  mov     bl, r9b
0x18000d598  mov     ebp, r8d
0x18000d59b  mov     r15d, edx
0x18000d59e  mov     rdi, rcx
0x18000d5a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5a8  lea     r12, WPP_GLOBAL_Control
0x18000d5af  lea     r13, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d5b6  cmp     rcx, r12
0x18000d5b9  jz      short loc_18000D5DA
0x18000d5bb  test    byte ptr [rcx+1Ch], 8
0x18000d5bf  jz      short loc_18000D5DA
0x18000d5c1  mov     rcx, [rcx+10h]
0x18000d5c5  mov     edx, 11h
0x18000d5ca  mov     dword ptr [rsp+78h+var_58], r8d
0x18000d5cf  mov     r9d, r15d
0x18000d5d2  mov     r8, r13
0x18000d5d5  call    WPP_SF_dd
0x18000d5da  mov     dl, bl; bool
0x18000d5dc  call    ?SetPrivateAddress@SharedAccessSvcMgr@@AEAAJ_N@Z; SharedAccessSvcMgr::SetPrivateAddress(bool)
0x18000d5e1  mov     ebx, eax
0x18000d5e3  test    eax, eax
0x18000d5e5  jns     short loc_18000D61A
0x18000d5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5ee  cmp     rcx, r12
0x18000d5f1  jz      short loc_18000D60D
0x18000d5f3  test    byte ptr [rcx+1Ch], 1
0x18000d5f7  jz      short loc_18000D60D
0x18000d5f9  mov     rcx, [rcx+10h]
0x18000d5fd  mov     edx, 12h
0x18000d602  mov     r9d, eax
0x18000d605  mov     r8, r13
0x18000d608  call    WPP_SF_d
0x18000d60d  lea     rsi, [rdi+1Ch]
0x18000d611  lea     r14, [rdi+20h]
0x18000d615  jmp     loc_18000D71A
0x18000d61a  lea     rsi, [rdi+1Ch]
0x18000d61e  mov     edx, ebp
0x18000d620  lea     r14, [rdi+20h]
0x18000d624  mov     [rsi], r15d
0x18000d627  mov     ecx, r15d
0x18000d62a  mov     [r14], ebp
0x18000d62d  call    cs:__imp_HNetCfgStartSharing
0x18000d633  mov     ebx, eax
0x18000d635  test    eax, eax
0x18000d637  jns     short loc_18000D65D
0x18000d639  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d640  cmp     rcx, r12
0x18000d643  jz      loc_18000D71A
0x18000d649  test    byte ptr [rcx+1Ch], 1
0x18000d64d  jz      loc_18000D71A
0x18000d653  mov     edx, 13h
0x18000d658  jmp     loc_18000D70B
0x18000d65d  mov     rcx, [rdi+8]
0x18000d661  lea     rax, [rdi+10h]
0x18000d665  mov     r9, rdi
0x18000d668  mov     [rsp+78h+var_58], rax
0x18000d66d  lea     r8, ?ScmEventsCallback@SharedAccessSvcMgr@@CAXKPEAX@Z; SharedAccessSvcMgr::ScmEventsCallback(ulong,void *)
0x18000d674  mov     edx, 2
0x18000d679  call    cs:__imp_SubscribeServiceChangeNotifications
0x18000d67f  test    eax, eax
0x18000d681  jz      short loc_18000D6E6
0x18000d683  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d68a  cmp     rcx, r12
0x18000d68d  jz      short loc_18000D6A9
0x18000d68f  test    byte ptr [rcx+1Ch], 1
0x18000d693  jz      short loc_18000D6A9
0x18000d695  mov     rcx, [rcx+10h]
0x18000d699  mov     edx, 14h
0x18000d69e  mov     r9d, eax
0x18000d6a1  mov     r8, r13
0x18000d6a4  call    WPP_SF_d
0x18000d6a9  mov     byte ptr [rdi+18h], 1
0x18000d6ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6b4  cmp     rcx, r12
0x18000d6b7  jz      short loc_18000D6D3
0x18000d6b9  test    byte ptr [rcx+1Ch], 8
0x18000d6bd  jz      short loc_18000D6D3
0x18000d6bf  mov     rcx, [rcx+10h]
0x18000d6c3  mov     edx, 16h
0x18000d6c8  mov     r9d, ebx
0x18000d6cb  mov     r8, r13
0x18000d6ce  call    WPP_SF_d
0x18000d6d3  mov     eax, ebx
0x18000d6d5  add     rsp, 38h
0x18000d6d9  pop     r15
0x18000d6db  pop     r14
0x18000d6dd  pop     r13
0x18000d6df  pop     r12
0x18000d6e1  pop     rdi
0x18000d6e2  pop     rsi
0x18000d6e3  pop     rbp
0x18000d6e4  pop     rbx
0x18000d6e5  retn
0x18000d6e6  mov     rcx, rdi; this
0x18000d6e9  call    ?NotifyUpdatePortMapping@SharedAccessSvcMgr@@AEAAJXZ; SharedAccessSvcMgr::NotifyUpdatePortMapping(void)
0x18000d6ee  mov     ebx, eax
0x18000d6f0  test    eax, eax
0x18000d6f2  jns     short loc_18000D6A9
0x18000d6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6fb  cmp     rcx, r12
0x18000d6fe  jz      short loc_18000D71A
0x18000d700  test    byte ptr [rcx+1Ch], 1
0x18000d704  jz      short loc_18000D71A
0x18000d706  mov     edx, 15h
0x18000d70b  mov     rcx, [rcx+10h]
0x18000d70f  mov     r9d, eax
0x18000d712  mov     r8, r13
0x18000d715  call    WPP_SF_d
0x18000d71a  mov     rcx, rdi; this
0x18000d71d  call    ?Stop@SharedAccessSvcMgr@@QEAAJXZ; SharedAccessSvcMgr::Stop(void)
0x18000d722  mov     dword ptr [rsi], 0
0x18000d728  mov     dword ptr [r14], 0
0x18000d72f  jmp     loc_18000D6AD
```
