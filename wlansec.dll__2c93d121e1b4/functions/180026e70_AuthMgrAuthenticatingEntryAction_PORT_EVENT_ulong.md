# AuthMgrAuthenticatingEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180026e70`
- end: `0x180027050`
- name: `?AuthMgrAuthenticatingEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `480`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000b348`
- `0x1800169c0`
- `0x180026e70`
- `0x180027058`
- `0x180027388`
- `0x180027830`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002700b`
- `MobileNetworking!ReleaseWriteLock` at `0x18002700b`
- `MobileNetworking!AcquireWriteLock` at `0x180026f6b`
- `MobileNetworking!AcquireWriteLock` at `0x180026f6b`

## pseudocode

```c
__int64 __fastcall AuthMgrAuthenticatingEntryAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  PVOID *v3; // rcx
  __int64 v4; // rsi
  unsigned int v5; // edx
  unsigned int v6; // eax
  unsigned int v7; // edi
  PVOID *v8; // rcx
  __int64 v9; // rbx
  void *v10; // rcx
  unsigned __int8 *v12; // [rsp+28h] [rbp-50h]
  struct _EAP_METHOD_TYPE v13; // [rsp+40h] [rbp-38h] BYREF

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = *((_QWORD *)a1 + 3);
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 2) != 0 )
    WPP_SF_d(v3[7], 74, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, *(unsigned int *)(v4 + 312));
  v5 = *(_DWORD *)(v4 + 968);
  *(_DWORD *)(v4 + 964) = 0;
  AuthMgrSetTimers((struct MSMSEC_PORT_AUTH_CONTEXT *)(v4 + 920), v5);
  v6 = SecMgrNotifyAuthStart((struct MSMSEC_PORT_CONTEXT *)v4);
  v7 = v6;
  if ( !v6 )
  {
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), ">>> Locking >>>");
    AcquireWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "AuthMgrAuthenticatingEntryAction", 824);
    v9 = *(_QWORD *)(v4 + 24);
    v10 = *(void **)(v9 + 2632);
    v13 = *(struct _EAP_METHOD_TYPE *)(*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v9 + 2784) + 48LL) + 64LL)
                                     + *(_QWORD *)(*(_QWORD *)(v9 + 2784) + 48LL)
                                     + 4LL);
    SecMgrCorrelateToSession(v10);
    MSMSecLogOneXStart(
      (unsigned __int16 *)(*(_QWORD *)(v4 + 24) + 48LL),
      (struct _GUID *)(*(_QWORD *)(v4 + 24) + 32LL),
      (unsigned __int8 (*)[6])(v4 + 296),
      (struct _DOT11_SSID *)(*(_QWORD *)(v4 + 24) + 2728LL),
      *(enum _DOT11_BSS_TYPE *)(*(_QWORD *)(v4 + 24) + 2764LL),
      (unsigned __int8 (*)[6])v12,
      &v13,
      *(void **)(v9 + 2632));
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), "<<< Unlocking <<<");
    ReleaseWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "AuthMgrAuthenticatingEntryAction", 844);
    goto LABEL_12;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v6);
LABEL_12:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
    WPP_SF_d(v8[7], 76, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180026e70  push    rbx
0x180026e72  push    rbp
0x180026e73  push    rsi
0x180026e74  push    rdi
0x180026e75  sub     rsp, 58h
0x180026e79  mov     rsi, rcx
0x180026e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e83  lea     rbp, WPP_GLOBAL_Control
0x180026e8a  cmp     rcx, rbp
0x180026e8d  jz      short loc_180026EB4
0x180026e8f  test    dword ptr [rcx+44h], 100h
0x180026e96  jz      short loc_180026EB4
0x180026e98  mov     rcx, [rcx+38h]
0x180026e9c  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180026ea3  mov     edx, 49h ; 'I'
0x180026ea8  call    WPP_SF_
0x180026ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180026eb4  mov     rsi, [rsi+18h]
0x180026eb8  lea     rbx, [rsi+398h]
0x180026ebf  cmp     rcx, rbp
0x180026ec2  jz      short loc_180026EE6
0x180026ec4  test    byte ptr [rcx+44h], 2
0x180026ec8  jz      short loc_180026EE6
0x180026eca  mov     r9d, [rsi+138h]
0x180026ed1  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180026ed8  mov     rcx, [rcx+38h]
0x180026edc  mov     edx, 4Ah ; 'J'
0x180026ee1  call    WPP_SF_d
0x180026ee6  mov     edx, [rbx+30h]; unsigned int
0x180026ee9  mov     rcx, rbx; struct MSMSEC_PORT_AUTH_CONTEXT *
0x180026eec  mov     dword ptr [rbx+2Ch], 0
0x180026ef3  call    ?AuthMgrSetTimers@@YAXPEAUMSMSEC_PORT_AUTH_CONTEXT@@K@Z; AuthMgrSetTimers(MSMSEC_PORT_AUTH_CONTEXT *,ulong)
0x180026ef8  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180026efb  call    ?SecMgrNotifyAuthStart@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrNotifyAuthStart(MSMSEC_PORT_CONTEXT *)
0x180026f00  mov     edi, eax
0x180026f02  test    eax, eax
0x180026f04  jz      short loc_180026F3D
0x180026f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f0d  cmp     rcx, rbp
0x180026f10  jz      loc_180027044
0x180026f16  test    byte ptr [rcx+44h], 1
0x180026f1a  jz      loc_18002701E
0x180026f20  mov     rcx, [rcx+38h]
0x180026f24  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180026f2b  mov     edx, 4Bh ; 'K'
0x180026f30  mov     r9d, eax
0x180026f33  call    WPP_SF_d
0x180026f38  jmp     loc_180027017
0x180026f3d  mov     rcx, [rsi+18h]
0x180026f41  lea     rdx, aLocking; ">>> Locking >>>"
0x180026f48  mov     ecx, [rcx+9C0h]; unsigned int
0x180026f4e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180026f53  mov     rcx, [rsi+18h]
0x180026f57  lea     r8, aAuthmgrauthent; "AuthMgrAuthenticatingEntryAction"
0x180026f5e  mov     r9d, 338h
0x180026f64  lea     rdx, [rcx+9D0h]
0x180026f6b  call    cs:__imp_AcquireWriteLock
0x180026f72  nop     dword ptr [rax+rax+00h]
0x180026f77  mov     rbx, [rsi+18h]
0x180026f7b  mov     rax, [rbx+0AE0h]
0x180026f82  mov     rcx, [rax+30h]
0x180026f86  mov     eax, [rcx+40h]
0x180026f89  movups  xmm0, xmmword ptr [rax+rcx+4]
0x180026f8e  mov     rcx, [rbx+0A48h]; void *
0x180026f95  movdqu  xmmword ptr [rsp+78h+var_38.eapType.type], xmm0
0x180026f9b  call    ?SecMgrCorrelateToSession@@YAXPEAX@Z; SecMgrCorrelateToSession(void *)
0x180026fa0  mov     rcx, [rsi+18h]
0x180026fa4  lea     r8, [rsi+128h]; unsigned __int8 (*)[6]
0x180026fab  mov     rax, [rbx+0A48h]
0x180026fb2  mov     [rsp+78h+var_40], rax; void *
0x180026fb7  lea     rax, [rsp+78h+var_38]
0x180026fbc  mov     [rsp+78h+var_48], rax; struct _EAP_METHOD_TYPE *
0x180026fc1  lea     r9, [rcx+0AA8h]; struct _DOT11_SSID *
0x180026fc8  mov     eax, [r9+24h]
0x180026fcc  lea     rdx, [rcx+20h]; struct _GUID *
0x180026fd0  add     rcx, 30h ; '0'; unsigned __int16 *
0x180026fd4  mov     [rsp+78h+var_58], eax; enum _DOT11_BSS_TYPE
0x180026fd8  call    ?MSMSecLogOneXStart@@YAKPEAGPEAU_GUID@@PEAY05EPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@2PEAU_EAP_METHOD_TYPE@@PEAX@Z; MSMSecLogOneXStart(ushort *,_GUID *,uchar (*)[6],_DOT11_SSID *,_DOT11_BSS_TYPE,uchar (*)[6],_EAP_METHOD_TYPE *,void *)
0x180026fdd  mov     rcx, [rsi+18h]
0x180026fe1  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180026fe8  mov     ecx, [rcx+9C0h]; unsigned int
0x180026fee  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180026ff3  mov     rcx, [rsi+18h]
0x180026ff7  lea     r8, aAuthmgrauthent; "AuthMgrAuthenticatingEntryAction"
0x180026ffe  mov     r9d, 34Ch
0x180027004  lea     rdx, [rcx+9D0h]
0x18002700b  call    cs:__imp_ReleaseWriteLock
0x180027012  nop     dword ptr [rax+rax+00h]
0x180027017  mov     rcx, cs:WPP_GLOBAL_Control
0x18002701e  cmp     rcx, rbp
0x180027021  jz      short loc_180027044
0x180027023  test    dword ptr [rcx+44h], 100h
0x18002702a  jz      short loc_180027044
0x18002702c  mov     rcx, [rcx+38h]
0x180027030  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180027037  mov     edx, 4Ch ; 'L'
0x18002703c  mov     r9d, edi
0x18002703f  call    WPP_SF_d
0x180027044  mov     eax, edi
0x180027046  add     rsp, 58h
0x18002704a  pop     rdi
0x18002704b  pop     rsi
0x18002704c  pop     rbp
0x18002704d  pop     rbx
0x18002704e  retn
```
