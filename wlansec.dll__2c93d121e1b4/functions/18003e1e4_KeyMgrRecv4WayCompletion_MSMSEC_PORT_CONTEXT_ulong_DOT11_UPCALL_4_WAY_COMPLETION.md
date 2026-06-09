# KeyMgrRecv4WayCompletion(MSMSEC_PORT_CONTEXT *,ulong,DOT11_UPCALL_4_WAY_COMPLETION *)

- ea: `0x18003e1e4`
- end: `0x18003e4be`
- name: `?KeyMgrRecv4WayCompletion@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAUDOT11_UPCALL_4_WAY_COMPLETION@@@Z`
- size: `730`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, unsigned int, struct DOT11_UPCALL_4_WAY_COMPLETION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014b64`

## callees

- `0x18000892c`
- `0x18000895c`
- `0x180008998`
- `0x1800164e4`
- `0x1800169c0`
- `0x18002d138`
- `0x18002ddd4`
- `0x1800337c8`
- `0x18003e1e4`
- `0x18005c738`
- `0x180066244`
- `0x18006b788`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003e440`
- `ntdll!RtlNtStatusToDosError` at `0x18003e440`
- `MobileNetworking!ReleaseWriteLock` at `0x18003e425`
- `MobileNetworking!ReleaseWriteLock` at `0x18003e425`
- `MobileNetworking!AcquireWriteLock` at `0x18003e339`
- `MobileNetworking!AcquireWriteLock` at `0x18003e339`

## string_xrefs

- `0x18003e325`: `KeyMgrRecv4WayCompletion`
- `0x18003e411`: `KeyMgrRecv4WayCompletion`

## pseudocode

```c
__int64 __fastcall KeyMgrRecv4WayCompletion(
        struct MSMSEC_PORT_CONTEXT *a1,
        unsigned int a2,
        struct DOT11_UPCALL_4_WAY_COMPLETION *a3)
{
  unsigned int CanRecvOffloadedIndication; // eax
  unsigned int v6; // edi
  PVOID *v7; // rcx
  __int64 v8; // rdx
  BOOL v9; // eax
  const char *v10; // r9
  NTSTATUS v11; // ecx
  __int64 v12; // rsi
  ULONG v13; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 218, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
  CanRecvOffloadedIndication = KeyMgrCanRecvOffloadedIndication(a1, a2, a3);
  v6 = CanRecvOffloadedIndication;
  if ( !CanRecvOffloadedIndication )
  {
    v9 = *((_DWORD *)a1 + 297) && *((_DWORD *)a1 + 298) && *((_DWORD *)a1 + 299);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      v10 = "Secured";
      if ( !v9 )
        v10 = "Not secured";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 220, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v10);
    }
    v11 = *((_DWORD *)a3 + 3);
    if ( v11 )
    {
      if ( !*((_DWORD *)a3 + 4) )
        *((_DWORD *)a3 + 4) = 65537;
      v13 = RtlNtStatusToDosError(v11);
      CanRecvOffloadedIndication = KeyMgrOffloadedHandshakeFailure(a1, *((_DWORD *)a3 + 4), v13);
      v6 = CanRecvOffloadedIndication;
      if ( !CanRecvOffloadedIndication )
        goto LABEL_39;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_40;
      v8 = 223;
    }
    else
    {
      CanRecvOffloadedIndication = KeyMgrOffloadedHandshakeSuccess(a1);
      v6 = CanRecvOffloadedIndication;
      if ( !CanRecvOffloadedIndication )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_58508574>::GetImpl'::`2'::impl) )
        {
          TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
          AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "KeyMgrRecv4WayCompletion", 2809);
          v12 = *((_QWORD *)a1 + 3);
          if ( (unsigned int)SecMgrProfileValidForFastRoam(a1)
            && *(_BYTE *)(v12 + 3012)
            && !(unsigned int)IsPMKCacheValid((struct MSMSEC_PMKCACHE_CONTEXT *)(v12 + 3000)) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 222, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
            PmkCacheValidate(
              (struct MSMSEC_PMKCACHE_CONTEXT *)(*((_QWORD *)a1 + 3) + 3000LL),
              (struct MSMSEC_NW_DESC *)(*((_QWORD *)a1 + 3) + 2728LL),
              *(struct DOT11_MSMSEC_CONNECTION_PROFILE **)(*((_QWORD *)a1 + 3) + 2784LL),
              *((_DWORD *)a1 + 164),
              *((void **)a1 + 83),
              (unsigned __int8 (*)[6])((char *)a1 + 302),
              (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 512),
              (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 640),
              1);
          }
          TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
          ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "KeyMgrRecv4WayCompletion", 2829);
        }
        goto LABEL_39;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_40;
      v8 = 221;
    }
LABEL_38:
    WPP_SF_d(v7[7], v8, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, CanRecvOffloadedIndication);
LABEL_39:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_40;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v8 = 219;
    goto LABEL_38;
  }
LABEL_40:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_d(v7[7], 224, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18003e1e4  push    rbx
0x18003e1e6  push    rsi
0x18003e1e7  push    rdi
0x18003e1e8  push    r14
0x18003e1ea  push    r15
0x18003e1ec  sub     rsp, 50h
0x18003e1f0  mov     rsi, r8
0x18003e1f3  mov     rbx, rcx
0x18003e1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e1fd  lea     r14, WPP_GLOBAL_Control
0x18003e204  lea     r15, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x18003e20b  cmp     rcx, r14
0x18003e20e  jz      short loc_18003E22A
0x18003e210  test    dword ptr [rcx+44h], 100h
0x18003e217  jz      short loc_18003E22A
0x18003e219  mov     rcx, [rcx+38h]
0x18003e21d  mov     edx, 0DAh
0x18003e222  mov     r8, r15
0x18003e225  call    WPP_SF_
0x18003e22a  mov     r8, rsi; void *
0x18003e22d  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18003e230  call    ?KeyMgrCanRecvOffloadedIndication@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAX@Z; KeyMgrCanRecvOffloadedIndication(MSMSEC_PORT_CONTEXT *,ulong,void *)
0x18003e235  mov     edi, eax
0x18003e237  test    eax, eax
0x18003e239  jz      short loc_18003E25F
0x18003e23b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e242  cmp     rcx, r14
0x18003e245  jz      loc_18003E4AF
0x18003e24b  test    byte ptr [rcx+44h], 1
0x18003e24f  jz      loc_18003E48D
0x18003e255  mov     edx, 0DBh
0x18003e25a  jmp     loc_18003E477
0x18003e25f  cmp     dword ptr [rbx+4A4h], 0
0x18003e266  jz      short loc_18003E281
0x18003e268  cmp     dword ptr [rbx+4A8h], 0
0x18003e26f  jz      short loc_18003E281
0x18003e271  cmp     dword ptr [rbx+4ACh], 0
0x18003e278  jz      short loc_18003E281
0x18003e27a  mov     eax, 1
0x18003e27f  jmp     short loc_18003E283
0x18003e281  xor     eax, eax
0x18003e283  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e28a  cmp     rcx, r14
0x18003e28d  jz      short loc_18003E2BA
0x18003e28f  test    byte ptr [rcx+44h], 2
0x18003e293  jz      short loc_18003E2BA
0x18003e295  mov     rcx, [rcx+38h]
0x18003e299  lea     rdx, aNotSecured; "Not secured"
0x18003e2a0  test    eax, eax
0x18003e2a2  lea     r9, aSecured; "Secured"
0x18003e2a9  mov     r8, r15
0x18003e2ac  cmovz   r9, rdx
0x18003e2b0  mov     edx, 0DCh
0x18003e2b5  call    WPP_SF_s
0x18003e2ba  mov     ecx, [rsi+0Ch]; Status
0x18003e2bd  test    ecx, ecx
0x18003e2bf  jnz     loc_18003E433
0x18003e2c5  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18003e2c8  call    ?KeyMgrOffloadedHandshakeSuccess@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; KeyMgrOffloadedHandshakeSuccess(MSMSEC_PORT_CONTEXT *)
0x18003e2cd  mov     edi, eax
0x18003e2cf  test    eax, eax
0x18003e2d1  jz      short loc_18003E2F7
0x18003e2d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2da  cmp     rcx, r14
0x18003e2dd  jz      loc_18003E4AF
0x18003e2e3  test    byte ptr [rcx+44h], 1
0x18003e2e7  jz      loc_18003E48D
0x18003e2ed  mov     edx, 0DDh
0x18003e2f2  jmp     loc_18003E477
0x18003e2f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_58508574@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58508574@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_58508574>::GetImpl(void)'::`2'::impl
0x18003e2fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58508574@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574>::__private_IsEnabled(void)
0x18003e303  test    al, al
0x18003e305  jz      loc_18003E486
0x18003e30b  mov     rcx, [rbx+18h]
0x18003e30f  lea     rdx, aLocking; ">>> Locking >>>"
0x18003e316  mov     ecx, [rcx+9C0h]; unsigned int
0x18003e31c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003e321  mov     rcx, [rbx+18h]
0x18003e325  lea     r8, aKeymgrrecv4way; "KeyMgrRecv4WayCompletion"
0x18003e32c  mov     r9d, 0AF9h
0x18003e332  lea     rdx, [rcx+9D0h]
0x18003e339  call    cs:__imp_AcquireWriteLock
0x18003e340  nop     dword ptr [rax+rax+00h]
0x18003e345  mov     rsi, [rbx+18h]
0x18003e349  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18003e34c  call    ?SecMgrProfileValidForFastRoam@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrProfileValidForFastRoam(MSMSEC_PORT_CONTEXT *)
0x18003e351  test    eax, eax
0x18003e353  jz      loc_18003E3F7
0x18003e359  lea     rcx, [rsi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e360  cmp     byte ptr [rcx+0Ch], 0
0x18003e364  jz      loc_18003E3F7
0x18003e36a  call    ?IsPMKCacheValid@@YAHPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; IsPMKCacheValid(MSMSEC_PMKCACHE_CONTEXT *)
0x18003e36f  test    eax, eax
0x18003e371  jnz     loc_18003E3F7
0x18003e377  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e37e  cmp     rcx, r14
0x18003e381  jz      short loc_18003E39A
0x18003e383  test    byte ptr [rcx+44h], 2
0x18003e387  jz      short loc_18003E39A
0x18003e389  mov     rcx, [rcx+38h]
0x18003e38d  mov     edx, 0DEh
0x18003e392  mov     r8, r15
0x18003e395  call    WPP_SF_
0x18003e39a  mov     r8, [rbx+18h]
0x18003e39e  lea     r9, [rbx+200h]
0x18003e3a5  mov     [rsp+78h+var_38], 1; int
0x18003e3ad  lea     rax, [rbx+280h]
0x18003e3b4  mov     [rsp+78h+var_40], rax; struct MSMSEC_RAW_DATA *
0x18003e3b9  lea     r10, [rbx+12Eh]
0x18003e3c0  mov     rax, [rbx+298h]
0x18003e3c7  mov     [rsp+78h+var_48], r9; struct MSMSEC_RAW_DATA *
0x18003e3cc  lea     rdx, [r8+0AA8h]; struct MSMSEC_NW_DESC *
0x18003e3d3  mov     r9d, [rbx+290h]; unsigned int
0x18003e3da  lea     rcx, [r8+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x18003e3e1  mov     r8, [r8+0AE0h]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18003e3e8  mov     [rsp+78h+var_50], r10; unsigned __int8 (*)[6]
0x18003e3ed  mov     [rsp+78h+var_58], rax; void *
0x18003e3f2  call    ?PmkCacheValidate@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAUMSMSEC_NW_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@KPEAXPEAY05EPEAUMSMSEC_RAW_DATA@@5H@Z; PmkCacheValidate(MSMSEC_PMKCACHE_CONTEXT *,MSMSEC_NW_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong,void *,uchar (*)[6],MSMSEC_RAW_DATA *,MSMSEC_RAW_DATA *,int)
0x18003e3f7  mov     rcx, [rbx+18h]
0x18003e3fb  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003e402  mov     ecx, [rcx+9C0h]; unsigned int
0x18003e408  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003e40d  mov     rcx, [rbx+18h]
0x18003e411  lea     r8, aKeymgrrecv4way; "KeyMgrRecv4WayCompletion"
0x18003e418  mov     r9d, 0B0Dh
0x18003e41e  lea     rdx, [rcx+9D0h]
0x18003e425  call    cs:__imp_ReleaseWriteLock
0x18003e42c  nop     dword ptr [rax+rax+00h]
0x18003e431  jmp     short loc_18003E486
0x18003e433  cmp     dword ptr [rsi+10h], 0
0x18003e437  jnz     short loc_18003E440
0x18003e439  mov     dword ptr [rsi+10h], 10001h
0x18003e440  call    cs:__imp_RtlNtStatusToDosError
0x18003e447  nop     dword ptr [rax+rax+00h]
0x18003e44c  mov     edx, [rsi+10h]; unsigned int
0x18003e44f  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18003e452  mov     r8d, eax; unsigned int
0x18003e455  call    ?KeyMgrOffloadedHandshakeFailure@@YAKPEAUMSMSEC_PORT_CONTEXT@@KK@Z; KeyMgrOffloadedHandshakeFailure(MSMSEC_PORT_CONTEXT *,ulong,ulong)
0x18003e45a  mov     edi, eax
0x18003e45c  test    eax, eax
0x18003e45e  jz      short loc_18003E486
0x18003e460  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e467  cmp     rcx, r14
0x18003e46a  jz      short loc_18003E4AF
0x18003e46c  test    byte ptr [rcx+44h], 1
0x18003e470  jz      short loc_18003E48D
0x18003e472  mov     edx, 0DFh
0x18003e477  mov     rcx, [rcx+38h]
0x18003e47b  mov     r9d, eax
0x18003e47e  mov     r8, r15
0x18003e481  call    WPP_SF_d
0x18003e486  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e48d  cmp     rcx, r14
0x18003e490  jz      short loc_18003E4AF
0x18003e492  test    dword ptr [rcx+44h], 100h
0x18003e499  jz      short loc_18003E4AF
0x18003e49b  mov     rcx, [rcx+38h]
0x18003e49f  mov     edx, 0E0h
0x18003e4a4  mov     r9d, edi
0x18003e4a7  mov     r8, r15
0x18003e4aa  call    WPP_SF_d
0x18003e4af  mov     eax, edi
0x18003e4b1  add     rsp, 50h
0x18003e4b5  pop     r15
0x18003e4b7  pop     r14
0x18003e4b9  pop     rdi
0x18003e4ba  pop     rsi
0x18003e4bb  pop     rbx
0x18003e4bc  retn
```
