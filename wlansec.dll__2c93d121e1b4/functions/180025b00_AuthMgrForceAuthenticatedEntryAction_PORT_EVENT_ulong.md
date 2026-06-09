# AuthMgrForceAuthenticatedEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180025b00`
- end: `0x180025e17`
- name: `?AuthMgrForceAuthenticatedEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `791`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c444`
- `0x180013bc0`
- `0x1800169c0`
- `0x18001f2dc`
- `0x180025b00`
- `0x180025fd0`
- `0x1800262ac`

## import_xrefs

- `OneX!OneXForceAuthenticatedState` at `0x180025d4f`
- `OneX!OneXForceAuthenticatedState` at `0x180025d4f`
- `OneX!OneXSetAuthParams` at `0x180025c93`
- `OneX!OneXSetAuthParams` at `0x180025c93`
- `MobileNetworking!ReleaseWriteLock` at `0x180025c32`
- `MobileNetworking!ReleaseWriteLock` at `0x180025c68`
- `MobileNetworking!ReleaseWriteLock` at `0x180025c32`
- `MobileNetworking!ReleaseWriteLock` at `0x180025c68`
- `MobileNetworking!AcquireWriteLock` at `0x180025b7a`
- `MobileNetworking!AcquireWriteLock` at `0x180025b7a`

## pseudocode

```c
__int64 __fastcall AuthMgrForceAuthenticatedEntryAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned __int32 v13; // eax
  __int64 v14; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 83, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  v3 = *((_QWORD *)a1 + 3);
  v4 = *(_QWORD *)(v3 + 24);
  TraceAdapterId(*(_DWORD *)(v4 + 2496), ">>> Locking >>>");
  AcquireWriteLock(v4, v4 + 2512, "AuthMgrForceAuthenticatedEntryAction", 932);
  TraceAdapterId(*(_DWORD *)(v4 + 2496), ">>> Refing >>>");
  SecMgrRefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v4, "AuthMgrForceAuthenticatedEntryAction", 935);
  v5 = AuthMgrPreConnectConfigureOneX(
         *(void **)(v3 + 928),
         *(_DWORD *)(*(_QWORD *)(v4 + 2784) + 40LL),
         *(void **)(*(_QWORD *)(v4 + 2784) + 48LL),
         *(struct DOT11_MSMSEC_RUNTIME_STATE **)(v4 + 2904),
         **(_DWORD **)(*(_QWORD *)(v4 + 2784) + 24LL) == 8);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 84, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v5);
    TraceAdapterId(*(_DWORD *)(v4 + 2496), "<<< Unlocking <<<");
    ReleaseWriteLock(v4, v4 + 2512, "AuthMgrForceAuthenticatedEntryAction", 989);
    goto LABEL_28;
  }
  TraceAdapterId(*(_DWORD *)(v4 + 2496), "<<< Unlocking <<<");
  ReleaseWriteLock(v4, v4 + 2512, "AuthMgrForceAuthenticatedEntryAction", 953);
  v7 = OneXSetAuthParams(1, *(_QWORD *)(v3 + 928), *((unsigned int *)a1 + 11), *((_QWORD *)a1 + 6), 0);
  v8 = v7;
  if ( !v7 )
  {
    v13 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_1800AEFB0, 1u);
    v14 = *(_QWORD *)(v3 + 928);
    *(_DWORD *)(v3 + 936) = ++v13;
    v10 = OneXForceAuthenticatedState(1, v13, v14, 0);
    v6 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_28;
      v12 = 87;
    }
    else
    {
      v10 = CreateAndQueuePortEvent(v3, 48, 0);
      v6 = v10;
      if ( !v10 )
        goto LABEL_28;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_28;
      v12 = 88;
    }
LABEL_27:
    WPP_SF_d(v11[7], v12, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v10);
    goto LABEL_28;
  }
  v9 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 85, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v7);
  if ( (byte_1800AED45 & 4) != 0 )
    McTemplateU0qqq_EventWriteTransfer(v9, (unsigned int)MsmSecFastRoamVeto, v8, 965, *(_DWORD *)(v3 + 936));
  v10 = CreateAndQueuePortEvent(v3, 49, 0);
  v6 = v10;
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v12 = 86;
      goto LABEL_27;
    }
  }
LABEL_28:
  TraceAdapterId(*(_DWORD *)(v4 + 2496), "<<< Derefing <<<");
  SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v4, "AuthMgrForceAuthenticatedEntryAction", 993);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180025b00  push    rbx
0x180025b02  push    rbp
0x180025b03  push    rsi
0x180025b04  push    rdi
0x180025b05  push    r12
0x180025b07  push    r14
0x180025b09  push    r15
0x180025b0b  sub     rsp, 30h
0x180025b0f  mov     rdi, rcx
0x180025b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b19  lea     r15, WPP_GLOBAL_Control
0x180025b20  lea     r12, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180025b27  cmp     rcx, r15
0x180025b2a  jz      short loc_180025B46
0x180025b2c  test    dword ptr [rcx+44h], 100h
0x180025b33  jz      short loc_180025B46
0x180025b35  mov     rcx, [rcx+38h]
0x180025b39  mov     edx, 53h ; 'S'
0x180025b3e  mov     r8, r12
0x180025b41  call    WPP_SF_
0x180025b46  mov     rsi, [rdi+18h]
0x180025b4a  lea     rdx, aLocking; ">>> Locking >>>"
0x180025b51  mov     rbp, [rsi+18h]
0x180025b55  mov     ecx, [rbp+9C0h]; unsigned int
0x180025b5b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025b60  lea     r14, [rbp+9D0h]
0x180025b67  mov     r9d, 3A4h
0x180025b6d  mov     rdx, r14
0x180025b70  lea     r8, aAuthmgrforceau; "AuthMgrForceAuthenticatedEntryAction"
0x180025b77  mov     rcx, rbp
0x180025b7a  call    cs:__imp_AcquireWriteLock
0x180025b81  nop     dword ptr [rax+rax+00h]
0x180025b86  mov     ecx, [rbp+9C0h]; unsigned int
0x180025b8c  lea     rdx, aRefing; ">>> Refing >>>"
0x180025b93  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025b98  mov     r8d, 3A7h; int
0x180025b9e  lea     rdx, aAuthmgrforceau; "AuthMgrForceAuthenticatedEntryAction"
0x180025ba5  mov     rcx, rbp; struct MSMSEC_INTF_CONTEXT *
0x180025ba8  call    ?SecMgrRefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrRefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180025bad  mov     rdx, [rbp+0AE0h]
0x180025bb4  xor     ecx, ecx
0x180025bb6  mov     r9, [rbp+0B58h]; struct DOT11_MSMSEC_RUNTIME_STATE *
0x180025bbd  mov     rax, [rdx+18h]
0x180025bc1  mov     r8, [rdx+30h]; void *
0x180025bc5  mov     edx, [rdx+28h]; unsigned int
0x180025bc8  cmp     dword ptr [rax], 8
0x180025bcb  setz    cl
0x180025bce  mov     [rsp+68h+var_48], ecx; int
0x180025bd2  mov     rcx, [rsi+3A0h]; void *
0x180025bd9  call    ?AuthMgrPreConnectConfigureOneX@@YAKPEAXK0PEAUDOT11_MSMSEC_RUNTIME_STATE@@H@Z; AuthMgrPreConnectConfigureOneX(void *,ulong,void *,DOT11_MSMSEC_RUNTIME_STATE *,int)
0x180025bde  mov     ebx, eax
0x180025be0  test    eax, eax
0x180025be2  jz      short loc_180025C43
0x180025be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180025beb  cmp     rcx, r15
0x180025bee  jz      short loc_180025C0D
0x180025bf0  mov     edi, 1
0x180025bf5  test    [rcx+44h], dil
0x180025bf9  jz      short loc_180025C0D
0x180025bfb  mov     rcx, [rcx+38h]
0x180025bff  lea     edx, [rdi+53h]
0x180025c02  mov     r9d, eax
0x180025c05  mov     r8, r12
0x180025c08  call    WPP_SF_d
0x180025c0d  mov     ecx, [rbp+9C0h]; unsigned int
0x180025c13  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180025c1a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025c1f  mov     r9d, 3DDh
0x180025c25  lea     r8, aAuthmgrforceau; "AuthMgrForceAuthenticatedEntryAction"
0x180025c2c  mov     rdx, r14
0x180025c2f  mov     rcx, rbp
0x180025c32  call    cs:__imp_ReleaseWriteLock
0x180025c39  nop     dword ptr [rax+rax+00h]
0x180025c3e  jmp     loc_180025DB5
0x180025c43  mov     ecx, [rbp+9C0h]; unsigned int
0x180025c49  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180025c50  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025c55  mov     r9d, 3B9h
0x180025c5b  lea     r8, aAuthmgrforceau; "AuthMgrForceAuthenticatedEntryAction"
0x180025c62  mov     rdx, r14
0x180025c65  mov     rcx, rbp
0x180025c68  call    cs:__imp_ReleaseWriteLock
0x180025c6f  nop     dword ptr [rax+rax+00h]
0x180025c74  mov     r9, [rdi+30h]
0x180025c78  mov     r8d, [rdi+2Ch]
0x180025c7c  mov     edi, 1
0x180025c81  mov     rdx, [rsi+3A0h]
0x180025c88  mov     ecx, edi
0x180025c8a  mov     qword ptr [rsp+68h+var_48], 0
0x180025c93  call    cs:__imp_OneXSetAuthParams
0x180025c9a  nop     dword ptr [rax+rax+00h]
0x180025c9f  mov     ebx, eax
0x180025ca1  test    eax, eax
0x180025ca3  jz      loc_180025D2F
0x180025ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cb0  cmp     rcx, r15
0x180025cb3  jz      short loc_180025CCD
0x180025cb5  test    [rcx+44h], dil
0x180025cb9  jz      short loc_180025CCD
0x180025cbb  mov     rcx, [rcx+38h]
0x180025cbf  lea     edx, [rdi+54h]
0x180025cc2  mov     r9d, eax
0x180025cc5  mov     r8, r12
0x180025cc8  call    WPP_SF_d
0x180025ccd  test    cs:byte_1800AED45, 4
0x180025cd4  jz      short loc_180025CF5
0x180025cd6  mov     eax, [rsi+3A8h]
0x180025cdc  lea     rdx, MsmSecFastRoamVeto
0x180025ce3  mov     r9d, 3C5h
0x180025ce9  mov     [rsp+68h+var_48], eax
0x180025ced  mov     r8d, ebx
0x180025cf0  call    McTemplateU0qqq_EventWriteTransfer
0x180025cf5  xor     r8d, r8d
0x180025cf8  mov     rcx, rsi
0x180025cfb  lea     edx, [r8+31h]
0x180025cff  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x180025d04  mov     ebx, eax
0x180025d06  test    eax, eax
0x180025d08  jz      loc_180025DB5
0x180025d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d15  cmp     rcx, r15
0x180025d18  jz      loc_180025DB5
0x180025d1e  test    [rcx+44h], dil
0x180025d22  jz      loc_180025DB5
0x180025d28  mov     edx, 56h ; 'V'
0x180025d2d  jmp     short loc_180025DA6
0x180025d2f  mov     eax, edi
0x180025d31  lock xadd dword ptr cs:qword_1800AEFB0, eax
0x180025d39  mov     r8, [rsi+3A0h]
0x180025d40  add     eax, edi
0x180025d42  mov     edx, eax
0x180025d44  xor     r9d, r9d
0x180025d47  mov     ecx, edi
0x180025d49  mov     [rsi+3A8h], eax
0x180025d4f  call    cs:__imp_OneXForceAuthenticatedState
0x180025d56  nop     dword ptr [rax+rax+00h]
0x180025d5b  mov     ebx, eax
0x180025d5d  test    eax, eax
0x180025d5f  jz      short loc_180025D7A
0x180025d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d68  cmp     rcx, r15
0x180025d6b  jz      short loc_180025DB5
0x180025d6d  test    [rcx+44h], dil
0x180025d71  jz      short loc_180025DB5
0x180025d73  mov     edx, 57h ; 'W'
0x180025d78  jmp     short loc_180025DA6
0x180025d7a  xor     r8d, r8d
0x180025d7d  mov     rcx, rsi
0x180025d80  lea     edx, [r8+30h]
0x180025d84  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x180025d89  mov     ebx, eax
0x180025d8b  test    eax, eax
0x180025d8d  jz      short loc_180025DB5
0x180025d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d96  cmp     rcx, r15
0x180025d99  jz      short loc_180025DB5
0x180025d9b  test    [rcx+44h], dil
0x180025d9f  jz      short loc_180025DB5
0x180025da1  mov     edx, 58h ; 'X'
0x180025da6  mov     rcx, [rcx+38h]
0x180025daa  mov     r9d, eax
0x180025dad  mov     r8, r12
0x180025db0  call    WPP_SF_d
0x180025db5  mov     ecx, [rbp+9C0h]; unsigned int
0x180025dbb  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180025dc2  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180025dc7  mov     r8d, 3E1h; int
0x180025dcd  lea     rdx, aAuthmgrforceau; "AuthMgrForceAuthenticatedEntryAction"
0x180025dd4  mov     rcx, rbp; struct MSMSEC_INTF_CONTEXT *
0x180025dd7  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180025ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025de3  cmp     rcx, r15
0x180025de6  jz      short loc_180025E05
0x180025de8  test    dword ptr [rcx+44h], 100h
0x180025def  jz      short loc_180025E05
0x180025df1  mov     rcx, [rcx+38h]
0x180025df5  mov     edx, 59h ; 'Y'
0x180025dfa  mov     r9d, ebx
0x180025dfd  mov     r8, r12
0x180025e00  call    WPP_SF_d
0x180025e05  mov     eax, ebx
0x180025e07  add     rsp, 30h
0x180025e0b  pop     r15
0x180025e0d  pop     r14
0x180025e0f  pop     r12
0x180025e11  pop     rdi
0x180025e12  pop     rsi
0x180025e13  pop     rbp
0x180025e14  pop     rbx
0x180025e15  retn
```
