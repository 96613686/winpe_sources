# SecMgrDestroyAdapter(MSMSEC_INTF_CONTEXT * *)

- ea: `0x180038368`
- end: `0x180038511`
- name: `?SecMgrDestroyAdapter@@YAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `425`
- prototype: `void __fastcall(struct MSMSEC_INTF_CONTEXT **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800115c0`
- `0x180013bc0`

## callees

- `0x180004518`
- `0x180005bf0`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x1800184ec`
- `0x180038368`
- `0x180058118`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800384b2`
- `MobileNetworking!ReleaseWriteLock` at `0x1800384b2`
- `MobileNetworking!AcquireWriteLock` at `0x1800383d1`
- `MobileNetworking!AcquireWriteLock` at `0x1800383d1`

## pseudocode

```c
void __fastcall SecMgrDestroyAdapter(struct MSMSEC_INTF_CONTEXT **a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  TraceAdapterId(*((_DWORD *)*a1 + 624), ">>> Locking >>>");
  AcquireWriteLock(*a1, (char *)*a1 + 2512, "SecMgrDestroyAdapter", 957);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_qDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      66,
      *((unsigned __int8 *)*a1 + 2364),
      *a1,
      *((unsigned __int8 *)*a1 + 2360),
      *((unsigned __int8 *)*a1 + 2361),
      *((unsigned __int8 *)*a1 + 2362),
      *((unsigned __int8 *)*a1 + 2363),
      *((unsigned __int8 *)*a1 + 2364),
      *((unsigned __int8 *)*a1 + 2365));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)*a1 + 681) != 1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 1) != 0 )
      WPP_SF_(v2[7], 67, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    SecMgrResetIntfOnStopSecurity(*a1);
  }
  TraceAdapterId(*((_DWORD *)*a1 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(*a1, (char *)*a1 + 2512, "SecMgrDestroyAdapter", 980);
  SecMgrDeinitializeAdapter(*a1);
  if ( *a1 )
    MSMSEC_INTF_CONTEXT::`scalar deleting destructor'(*a1, v3);
  *a1 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, 0);
}

```

## disassembly

```asm
0x180038368  push    rbx
0x18003836a  push    rbp
0x18003836b  push    rsi
0x18003836c  push    rdi
0x18003836d  sub     rsp, 58h
0x180038371  mov     rsi, rcx
0x180038374  mov     rcx, cs:WPP_GLOBAL_Control
0x18003837b  lea     rbp, WPP_GLOBAL_Control
0x180038382  cmp     rcx, rbp
0x180038385  jz      short loc_1800383A5
0x180038387  test    dword ptr [rcx+44h], 100h
0x18003838e  jz      short loc_1800383A5
0x180038390  mov     rcx, [rcx+38h]
0x180038394  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18003839b  mov     edx, 41h ; 'A'
0x1800383a0  call    WPP_SF_
0x1800383a5  mov     rcx, [rsi]
0x1800383a8  lea     rdx, aLocking; ">>> Locking >>>"
0x1800383af  mov     ecx, [rcx+9C0h]; unsigned int
0x1800383b5  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800383ba  mov     rcx, [rsi]
0x1800383bd  lea     r8, aSecmgrdestroya; "SecMgrDestroyAdapter"
0x1800383c4  mov     r9d, 3BDh
0x1800383ca  lea     rdx, [rcx+9D0h]
0x1800383d1  call    cs:__imp_AcquireWriteLock
0x1800383d8  nop     dword ptr [rax+rax+00h]
0x1800383dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383e4  cmp     rcx, rbp
0x1800383e7  jz      short loc_180038452
0x1800383e9  test    byte ptr [rcx+44h], 2
0x1800383ed  jz      short loc_180038452
0x1800383ef  mov     r9, [rsi]
0x1800383f2  mov     edx, 42h ; 'B'
0x1800383f7  mov     rcx, [rcx+38h]
0x1800383fb  movzx   eax, byte ptr [r9+93Dh]
0x180038403  movzx   r8d, byte ptr [r9+93Ch]
0x18003840b  movzx   r10d, byte ptr [r9+93Bh]
0x180038413  movzx   r11d, byte ptr [r9+93Ah]
0x18003841b  movzx   ebx, byte ptr [r9+939h]
0x180038423  movzx   edi, byte ptr [r9+938h]
0x18003842b  mov     [rsp+78h+var_30], eax
0x18003842f  mov     [rsp+78h+var_38], r8d
0x180038434  mov     [rsp+78h+var_40], r10d
0x180038439  mov     [rsp+78h+var_48], r11d
0x18003843e  mov     [rsp+78h+var_50], ebx
0x180038442  mov     [rsp+78h+var_58], edi
0x180038446  call    WPP_SF_qDDDDDD
0x18003844b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038452  mov     rax, [rsi]
0x180038455  cmp     dword ptr [rax+0AA4h], 1
0x18003845c  jz      short loc_180038486
0x18003845e  cmp     rcx, rbp
0x180038461  jz      short loc_18003847E
0x180038463  test    byte ptr [rcx+44h], 1
0x180038467  jz      short loc_18003847E
0x180038469  mov     rcx, [rcx+38h]
0x18003846d  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180038474  mov     edx, 43h ; 'C'
0x180038479  call    WPP_SF_
0x18003847e  mov     rcx, [rsi]; struct MSMSEC_INTF_CONTEXT *
0x180038481  call    ?SecMgrResetIntfOnStopSecurity@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrResetIntfOnStopSecurity(MSMSEC_INTF_CONTEXT *)
0x180038486  mov     rcx, [rsi]
0x180038489  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180038490  mov     ecx, [rcx+9C0h]; unsigned int
0x180038496  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003849b  mov     rcx, [rsi]
0x18003849e  lea     r8, aSecmgrdestroya; "SecMgrDestroyAdapter"
0x1800384a5  mov     r9d, 3D4h
0x1800384ab  lea     rdx, [rcx+9D0h]
0x1800384b2  call    cs:__imp_ReleaseWriteLock
0x1800384b9  nop     dword ptr [rax+rax+00h]
0x1800384be  mov     rcx, [rsi]; struct MSMSEC_INTF_CONTEXT *
0x1800384c1  call    ?SecMgrDeinitializeAdapter@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrDeinitializeAdapter(MSMSEC_INTF_CONTEXT *)
0x1800384c6  mov     rcx, [rsi]; this
0x1800384c9  test    rcx, rcx
0x1800384cc  jz      short loc_1800384D3
0x1800384ce  call    ??_GMSMSEC_INTF_CONTEXT@@QEAAPEAXI@Z; MSMSEC_INTF_CONTEXT::`scalar deleting destructor'(uint)
0x1800384d3  mov     qword ptr [rsi], 0
0x1800384da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384e1  cmp     rcx, rbp
0x1800384e4  jz      short loc_180038507
0x1800384e6  test    dword ptr [rcx+44h], 100h
0x1800384ed  jz      short loc_180038507
0x1800384ef  mov     rcx, [rcx+38h]
0x1800384f3  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800384fa  mov     edx, 44h ; 'D'
0x1800384ff  xor     r9d, r9d
0x180038502  call    WPP_SF_d
0x180038507  add     rsp, 58h
0x18003850b  pop     rdi
0x18003850c  pop     rsi
0x18003850d  pop     rbp
0x18003850e  pop     rbx
0x18003850f  retn
```
