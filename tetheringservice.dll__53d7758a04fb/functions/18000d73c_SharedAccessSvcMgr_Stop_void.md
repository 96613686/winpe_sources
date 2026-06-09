# SharedAccessSvcMgr::Stop(void)

- ea: `0x18000d73c`
- end: `0x18000d85f`
- name: `?Stop@SharedAccessSvcMgr@@QEAAJXZ`
- size: `291`
- prototype: `__int64 __fastcall(SharedAccessSvcMgr *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000d584`
- `0x180015e30`
- `0x18001f740`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d73c`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18000d783`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18000d783`
- `HNetCfgClient!HNetCfgStopSharing` at `0x18000d7c9`
- `HNetCfgClient!HNetCfgStopSharing` at `0x18000d7c9`
- `HNetCfgClient!HNetCfgSetDhcpScopeAddress` at `0x18000d793`
- `HNetCfgClient!HNetCfgSetDhcpScopeAddress` at `0x18000d793`

## pseudocode

```c
__int64 __fastcall SharedAccessSvcMgr::Stop(SharedAccessSvcMgr *this)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // edi
  TetheringServiceTelemetry *v5; // rcx

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
  }
  if ( *((_QWORD *)this + 2) )
  {
    UnsubscribeServiceChangeNotifications();
    *((_QWORD *)this + 2) = 0;
  }
  v2 = HNetCfgSetDhcpScopeAddress(0);
  if ( v2 < 0
    && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids,
      (unsigned int)v2);
  }
  v3 = HNetCfgStopSharing(*((unsigned int *)this + 7), *((unsigned int *)this + 8));
  v4 = v3;
  if ( v3 >= 0 )
    goto LABEL_14;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids,
      (unsigned int)v3);
LABEL_14:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 28, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v4);
LABEL_18:
  *(_QWORD *)((char *)this + 28) = 0;
  *((_BYTE *)this + 24) = 0;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18000d73c  push    rbx
0x18000d73e  push    rbp
0x18000d73f  push    rdi
0x18000d740  push    r14
0x18000d742  sub     rsp, 28h
0x18000d746  mov     rbx, rcx
0x18000d749  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d750  lea     rbp, WPP_GLOBAL_Control
0x18000d757  lea     r14, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d75e  cmp     rcx, rbp
0x18000d761  jz      short loc_18000D77A
0x18000d763  test    byte ptr [rcx+1Ch], 8
0x18000d767  jz      short loc_18000D77A
0x18000d769  mov     rcx, [rcx+10h]
0x18000d76d  mov     edx, 19h
0x18000d772  mov     r8, r14
0x18000d775  call    WPP_SF_
0x18000d77a  mov     rcx, [rbx+10h]
0x18000d77e  test    rcx, rcx
0x18000d781  jz      short loc_18000D791
0x18000d783  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x18000d789  mov     qword ptr [rbx+10h], 0
0x18000d791  xor     ecx, ecx
0x18000d793  call    cs:__imp_HNetCfgSetDhcpScopeAddress
0x18000d799  test    eax, eax
0x18000d79b  jns     short loc_18000D7C3
0x18000d79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7a4  cmp     rcx, rbp
0x18000d7a7  jz      short loc_18000D7C3
0x18000d7a9  test    byte ptr [rcx+1Ch], 1
0x18000d7ad  jz      short loc_18000D7C3
0x18000d7af  mov     rcx, [rcx+10h]
0x18000d7b3  mov     edx, 1Ah
0x18000d7b8  mov     r9d, eax
0x18000d7bb  mov     r8, r14
0x18000d7be  call    WPP_SF_d
0x18000d7c3  mov     edx, [rbx+20h]
0x18000d7c6  mov     ecx, [rbx+1Ch]
0x18000d7c9  call    cs:__imp_HNetCfgStopSharing
0x18000d7cf  mov     edi, eax
0x18000d7d1  test    eax, eax
0x18000d7d3  jns     short loc_18000D7FB
0x18000d7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7dc  cmp     rcx, rbp
0x18000d7df  jz      short loc_18000D821
0x18000d7e1  test    byte ptr [rcx+1Ch], 1
0x18000d7e5  jz      short loc_18000D802
0x18000d7e7  mov     rcx, [rcx+10h]
0x18000d7eb  mov     edx, 1Bh
0x18000d7f0  mov     r9d, eax
0x18000d7f3  mov     r8, r14
0x18000d7f6  call    WPP_SF_d
0x18000d7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d802  cmp     rcx, rbp
0x18000d805  jz      short loc_18000D821
0x18000d807  test    byte ptr [rcx+1Ch], 4
0x18000d80b  jz      short loc_18000D821
0x18000d80d  mov     rcx, [rcx+10h]
0x18000d811  mov     edx, 1Ch
0x18000d816  mov     r9d, edi
0x18000d819  mov     r8, r14
0x18000d81c  call    WPP_SF_d
0x18000d821  mov     qword ptr [rbx+1Ch], 0
0x18000d829  mov     byte ptr [rbx+18h], 0
0x18000d82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d834  cmp     rcx, rbp
0x18000d837  jz      short loc_18000D853
0x18000d839  test    byte ptr [rcx+1Ch], 8
0x18000d83d  jz      short loc_18000D853
0x18000d83f  mov     rcx, [rcx+10h]
0x18000d843  mov     edx, 1Dh
0x18000d848  mov     r9d, edi
0x18000d84b  mov     r8, r14
0x18000d84e  call    WPP_SF_d
0x18000d853  mov     eax, edi
0x18000d855  add     rsp, 28h
0x18000d859  pop     r14
0x18000d85b  pop     rdi
0x18000d85c  pop     rbp
0x18000d85d  pop     rbx
0x18000d85e  retn
```
