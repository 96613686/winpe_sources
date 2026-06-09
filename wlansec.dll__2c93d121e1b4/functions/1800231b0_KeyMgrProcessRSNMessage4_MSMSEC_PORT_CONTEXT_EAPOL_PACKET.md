# KeyMgrProcessRSNMessage4(MSMSEC_PORT_CONTEXT *,EAPOL_PACKET *)

- ea: `0x1800231b0`
- end: `0x18002354e`
- name: `?KeyMgrProcessRSNMessage4@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUEAPOL_PACKET@@@Z`
- size: `926`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, struct EAPOL_PACKET *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180066c80`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18000c19c`
- `0x18000e620`
- `0x1800169c0`
- `0x180019a64`
- `0x18001a23c`
- `0x18001c968`
- `0x1800231b0`
- `0x180023554`
- `0x180023800`
- `0x1800239c0`
- `0x180024ca4`
- `0x1800423d4`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800234ba`
- `MobileNetworking!ReleaseWriteLock` at `0x1800234ba`
- `MobileNetworking!AcquireWriteLock` at `0x180023478`
- `MobileNetworking!AcquireWriteLock` at `0x180023478`

## pseudocode

```c
__int64 __fastcall KeyMgrProcessRSNMessage4(struct MSMSEC_PORT_CONTEXT *a1, struct EAPOL_PACKET *a2)
{
  PVOID *v4; // r10
  unsigned int v5; // eax
  unsigned int v6; // edx
  __int64 v7; // r14
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  int v13; // ebp
  struct MSMSEC_INTF_CONTEXT **v14; // rsi
  _OWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF

  v16[0] = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 228, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 2) != 0 )
    WPP_SF_LLL(
      v4[7],
      229,
      &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids,
      0,
      (*((unsigned __int8 *)a2 + 5) >> 4) & 1,
      *((unsigned __int8 *)a2 + 6) >> 7);
  v5 = DecryptKeyMaterial(*((unsigned int *)a1 + 484), *((_QWORD *)a1 + 243), v16);
  v7 = *((_QWORD *)&v16[0] + 1);
  v8 = v5;
  if ( v5 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_31;
    v10 = 230;
    goto LABEL_11;
  }
  if ( LODWORD(v16[0]) != 68 )
  {
    v8 = 13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        231,
        &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids,
        LODWORD(v16[0]),
        68);
    goto LABEL_31;
  }
  v5 = VerifyMIC((unsigned __int8 *)(*((_QWORD *)&v16[0] + 1) + 4LL), v6, a2);
  v8 = v5;
  if ( v5 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_31;
    v10 = 232;
    goto LABEL_11;
  }
  v12 = *((unsigned __int8 *)a2 + 5);
  if ( (v12 & 0x10) != 0 )
  {
    v8 = 13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 233, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids);
    goto LABEL_31;
  }
  if ( (v12 & 2) == 0 )
  {
    v13 = *((_DWORD *)a1 + 488);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 234, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids);
    v8 = 13;
    if ( v13 )
      KeyMgrNotifyKeyExchangeStatus(a1, 1, v13 != 0 ? 0x4800E : 0);
    goto LABEL_31;
  }
  if ( *((_QWORD *)a1 + 247) && *((_DWORD *)a1 + 496) )
  {
    FreeMSMSecMemory((char *)a1 + 1976);
    *((_DWORD *)a1 + 496) = 0;
  }
  ++*((_QWORD *)a1 + 237);
  v14 = (struct MSMSEC_INTF_CONTEXT **)((char *)a1 + 24);
  if ( (unsigned int)LocalMacIsHigher(a1) || (unsigned int)IntfIsInAPMode(*v14) )
  {
    v5 = InstallPairwiseKey(
           a1,
           (unsigned __int8 (*)[6])((char *)a1 + 302),
           (unsigned __int8 *)(v7 + 36),
           *(_DWORD *)v7,
           1,
           *((unsigned int (**)(void *, struct DOT11_CIPHER_KEY_MAPPING_KEY_VALUE *))a1 + 20));
    v8 = v5;
    if ( v5 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_31;
      v10 = 235;
LABEL_11:
      v11 = v5;
LABEL_12:
      WPP_SF_d(v9[7], v10, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids, v11);
LABEL_31:
      ++*((_DWORD *)a1 + 188);
      goto LABEL_46;
    }
  }
  TraceAdapterId(*((_DWORD *)*v14 + 624), ">>> Locking >>>");
  AcquireWriteLock(*v14, (char *)*v14 + 2512, "KeyMgrProcessRSNMessage4", 2897);
  v8 = InstallGroupKey(*v14);
  TraceAdapterId(*((_DWORD *)*v14 + 624), "<<< Unlocking <<<");
  ReleaseWriteLock(*v14, (char *)*v14 + 2512, "KeyMgrProcessRSNMessage4", 2899);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_31;
    v10 = 236;
    v11 = v8;
    goto LABEL_12;
  }
  *((_DWORD *)a1 + 488) = 1;
  ++*((_DWORD *)a1 + 187);
LABEL_46:
  if ( v7 )
    ScrubAndFreeKeyMaterial((char *)v16 + 8, v16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 237, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800231b0  push    rbx
0x1800231b2  push    rbp
0x1800231b3  push    rsi
0x1800231b4  push    rdi
0x1800231b5  push    r12
0x1800231b7  push    r14
0x1800231b9  push    r15
0x1800231bb  sub     rsp, 40h
0x1800231bf  xorps   xmm0, xmm0
0x1800231c2  mov     rsi, rdx
0x1800231c5  movups  [rsp+78h+var_48], xmm0
0x1800231ca  mov     rdi, rcx
0x1800231cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800231d4  lea     r12, WPP_GLOBAL_Control
0x1800231db  lea     rbp, WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids
0x1800231e2  cmp     r10, r12
0x1800231e5  jz      short loc_180023209
0x1800231e7  test    dword ptr [r10+44h], 100h
0x1800231ef  jz      short loc_180023209
0x1800231f1  mov     rcx, [r10+38h]
0x1800231f5  mov     edx, 0E4h
0x1800231fa  mov     r8, rbp
0x1800231fd  call    WPP_SF_
0x180023202  mov     r10, cs:WPP_GLOBAL_Control
0x180023209  mov     r15d, 1
0x18002320f  cmp     r10, r12
0x180023212  jz      short loc_180023248
0x180023214  test    byte ptr [r10+44h], 2
0x180023219  jz      short loc_180023248
0x18002321b  movzx   ecx, byte ptr [rsi+6]
0x18002321f  mov     edx, 0E5h
0x180023224  movzx   eax, byte ptr [rsi+5]
0x180023228  xor     r9d, r9d
0x18002322b  shr     ecx, 7
0x18002322e  mov     r8, rbp
0x180023231  mov     dword ptr [rsp+78h+var_50], ecx
0x180023235  mov     rcx, [r10+38h]
0x180023239  shr     eax, 4
0x18002323c  and     eax, r15d
0x18002323f  mov     [rsp+78h+var_58], eax
0x180023243  call    WPP_SF_LLL
0x180023248  mov     rdx, [rdi+798h]
0x18002324f  lea     r8, [rsp+78h+var_48]
0x180023254  mov     ecx, [rdi+790h]
0x18002325a  call    DecryptKeyMaterial
0x18002325f  mov     r14, qword ptr [rsp+78h+var_48+8]
0x180023264  mov     ebx, eax
0x180023266  test    eax, eax
0x180023268  jz      short loc_18002329D
0x18002326a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023271  cmp     rcx, r12
0x180023274  jz      loc_1800233A7
0x18002327a  test    [rcx+44h], r15b
0x18002327e  jz      loc_1800233A7
0x180023284  mov     edx, 0E6h
0x180023289  mov     r9d, eax
0x18002328c  mov     rcx, [rcx+38h]
0x180023290  mov     r8, rbp
0x180023293  call    WPP_SF_d
0x180023298  jmp     loc_1800233A7
0x18002329d  mov     r9d, dword ptr [rsp+78h+var_48]
0x1800232a2  cmp     r9d, 44h ; 'D'
0x1800232a6  jz      short loc_1800232E5
0x1800232a8  mov     ebx, 0Dh
0x1800232ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232b4  cmp     rcx, r12
0x1800232b7  jz      loc_1800233A7
0x1800232bd  test    [rcx+44h], r15b
0x1800232c1  jz      loc_1800233A7
0x1800232c7  mov     rcx, [rcx+38h]
0x1800232cb  mov     edx, 0E7h
0x1800232d0  mov     r8, rbp
0x1800232d3  mov     [rsp+78h+var_58], 44h ; 'D'
0x1800232db  call    WPP_SF_dd
0x1800232e0  jmp     loc_1800233A7
0x1800232e5  lea     rcx, [r14+4]; unsigned __int8 *
0x1800232e9  mov     r8, rsi; struct EAPOL_PACKET *
0x1800232ec  call    ?VerifyMIC@@YAKPEAEKPEBUEAPOL_PACKET@@@Z; VerifyMIC(uchar *,ulong,EAPOL_PACKET const *)
0x1800232f1  mov     ebx, eax
0x1800232f3  test    eax, eax
0x1800232f5  jz      short loc_18002331B
0x1800232f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232fe  cmp     rcx, r12
0x180023301  jz      loc_1800233A7
0x180023307  test    [rcx+44h], r15b
0x18002330b  jz      loc_1800233A7
0x180023311  mov     edx, 0E8h
0x180023316  jmp     loc_180023289
0x18002331b  mov     al, [rsi+5]
0x18002331e  test    al, 10h
0x180023320  jz      short loc_18002334C
0x180023322  mov     ebx, 0Dh
0x180023327  mov     rcx, cs:WPP_GLOBAL_Control
0x18002332e  cmp     rcx, r12
0x180023331  jz      short loc_1800233A7
0x180023333  test    [rcx+44h], r15b
0x180023337  jz      short loc_1800233A7
0x180023339  mov     rcx, [rcx+38h]
0x18002333d  mov     edx, 0E9h
0x180023342  mov     r8, rbp
0x180023345  call    WPP_SF_
0x18002334a  jmp     short loc_1800233A7
0x18002334c  test    al, 2
0x18002334e  jnz     short loc_1800233B3
0x180023350  mov     ebp, [rdi+7A0h]
0x180023356  mov     eax, ebp
0x180023358  neg     eax
0x18002335a  sbb     esi, esi
0x18002335c  and     esi, 4800Eh
0x180023362  mov     rcx, cs:WPP_GLOBAL_Control
0x180023369  cmp     rcx, r12
0x18002336c  jz      short loc_180023389
0x18002336e  test    [rcx+44h], r15b
0x180023372  jz      short loc_180023389
0x180023374  mov     rcx, [rcx+38h]
0x180023378  lea     r8, WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids
0x18002337f  mov     edx, 0EAh
0x180023384  call    WPP_SF_
0x180023389  mov     ebx, 0Dh
0x18002338e  test    ebp, ebp
0x180023390  jz      short loc_1800233A0
0x180023392  mov     r8d, esi; unsigned int
0x180023395  mov     edx, r15d; int
0x180023398  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18002339b  call    ?KeyMgrNotifyKeyExchangeStatus@@YAKPEAUMSMSEC_PORT_CONTEXT@@HK@Z; KeyMgrNotifyKeyExchangeStatus(MSMSEC_PORT_CONTEXT *,int,ulong)
0x1800233a0  lea     rbp, WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids
0x1800233a7  add     [rdi+2F0h], r15d
0x1800233ae  jmp     loc_1800234FF
0x1800233b3  lea     rcx, [rdi+7B8h]
0x1800233ba  cmp     qword ptr [rcx], 0
0x1800233be  jz      short loc_1800233D8
0x1800233c0  cmp     dword ptr [rdi+7C0h], 0
0x1800233c7  jz      short loc_1800233D8
0x1800233c9  call    FreeMSMSecMemory
0x1800233ce  mov     dword ptr [rdi+7C0h], 0
0x1800233d8  add     [rdi+768h], r15
0x1800233df  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800233e2  call    ?LocalMacIsHigher@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z; LocalMacIsHigher(MSMSEC_PORT_CONTEXT *)
0x1800233e7  lea     rsi, [rdi+18h]
0x1800233eb  test    eax, eax
0x1800233ed  jnz     short loc_1800233FB
0x1800233ef  mov     rcx, [rsi]; struct MSMSEC_INTF_CONTEXT *
0x1800233f2  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x1800233f7  test    eax, eax
0x1800233f9  jz      short loc_18002344C
0x1800233fb  mov     rax, [rdi+0A0h]
0x180023402  lea     r8, [r14+24h]; unsigned __int8 *
0x180023406  mov     r9d, [r14]; unsigned int
0x180023409  lea     rdx, [rdi+12Eh]; unsigned __int8 (*)[6]
0x180023410  mov     [rsp+78h+var_50], rax; unsigned int (*)(void *, struct DOT11_CIPHER_KEY_MAPPING_KEY_VALUE *)
0x180023415  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180023418  mov     [rsp+78h+var_58], r15d; int
0x18002341d  call    ?InstallPairwiseKey@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAY05EPEAEKHP6AKPEAXPEAUDOT11_CIPHER_KEY_MAPPING_KEY_VALUE@@@Z@Z; InstallPairwiseKey(MSMSEC_PORT_CONTEXT *,uchar (*)[6],uchar *,ulong,int,ulong (*)(void *,DOT11_CIPHER_KEY_MAPPING_KEY_VALUE *))
0x180023422  mov     ebx, eax
0x180023424  test    eax, eax
0x180023426  jz      short loc_18002344C
0x180023428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002342f  cmp     rcx, r12
0x180023432  jz      loc_1800233A7
0x180023438  test    [rcx+44h], r15b
0x18002343c  jz      loc_1800233A7
0x180023442  mov     edx, 0EBh
0x180023447  jmp     loc_180023289
0x18002344c  mov     rcx, [rsi]
0x18002344f  lea     rdx, aLocking; ">>> Locking >>>"
0x180023456  mov     ecx, [rcx+9C0h]; unsigned int
0x18002345c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180023461  mov     rcx, [rsi]
0x180023464  lea     r8, aKeymgrprocessr; "KeyMgrProcessRSNMessage4"
0x18002346b  mov     r9d, 0B51h
0x180023471  lea     rdx, [rcx+9D0h]
0x180023478  call    cs:__imp_AcquireWriteLock
0x18002347f  nop     dword ptr [rax+rax+00h]
0x180023484  mov     rcx, [rsi]; struct MSMSEC_INTF_CONTEXT *
0x180023487  call    ?InstallGroupKey@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z; InstallGroupKey(MSMSEC_INTF_CONTEXT *)
0x18002348c  mov     rcx, [rsi]
0x18002348f  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180023496  mov     ebx, eax
0x180023498  mov     ecx, [rcx+9C0h]; unsigned int
0x18002349e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800234a3  mov     rcx, [rsi]
0x1800234a6  lea     r8, aKeymgrprocessr; "KeyMgrProcessRSNMessage4"
0x1800234ad  mov     r9d, 0B53h
0x1800234b3  lea     rdx, [rcx+9D0h]
0x1800234ba  call    cs:__imp_ReleaseWriteLock
0x1800234c1  nop     dword ptr [rax+rax+00h]
0x1800234c6  test    ebx, ebx
0x1800234c8  jz      short loc_1800234F1
0x1800234ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234d1  cmp     rcx, r12
0x1800234d4  jz      loc_1800233A7
0x1800234da  test    [rcx+44h], r15b
0x1800234de  jz      loc_1800233A7
0x1800234e4  mov     edx, 0ECh
0x1800234e9  mov     r9d, ebx
0x1800234ec  jmp     loc_18002328C
0x1800234f1  mov     [rdi+7A0h], r15d
0x1800234f8  add     [rdi+2ECh], r15d
0x1800234ff  test    r14, r14
0x180023502  jz      short loc_180023513
0x180023504  lea     rdx, [rsp+78h+var_48]
0x180023509  lea     rcx, [rsp+78h+var_48+8]
0x18002350e  call    ScrubAndFreeKeyMaterial
0x180023513  mov     rcx, cs:WPP_GLOBAL_Control
0x18002351a  cmp     rcx, r12
0x18002351d  jz      short loc_18002353C
0x18002351f  test    dword ptr [rcx+44h], 100h
0x180023526  jz      short loc_18002353C
0x180023528  mov     rcx, [rcx+38h]
0x18002352c  mov     edx, 0EDh
0x180023531  mov     r9d, ebx
0x180023534  mov     r8, rbp
0x180023537  call    WPP_SF_d
0x18002353c  mov     eax, ebx
0x18002353e  add     rsp, 40h
0x180023542  pop     r15
0x180023544  pop     r14
0x180023546  pop     r12
0x180023548  pop     rdi
0x180023549  pop     rsi
0x18002354a  pop     rbp
0x18002354b  pop     rbx
0x18002354c  retn
```
