# KeyMgrInactiveExitAction(PORT_EVENT *,ulong *)

- ea: `0x180031d50`
- end: `0x18003200b`
- name: `?KeyMgrInactiveExitAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `699`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x180019a64`
- `0x180031d50`
- `0x180032014`
- `0x180032324`
- `0x180040f84`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180031e6b`
- `MobileNetworking!ReleaseWriteLock` at `0x180031e6b`
- `MobileNetworking!AcquireWriteLock` at `0x180031e1d`
- `MobileNetworking!AcquireWriteLock` at `0x180031e1d`

## pseudocode

```c
__int64 __fastcall KeyMgrInactiveExitAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  PVOID *v3; // rcx
  __int64 v4; // r13
  __int64 v5; // r9
  unsigned int RsnGroupKeys; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int RSNMessage1; // eax
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  unsigned int v14; // [rsp+D0h] [rbp+8h]

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = *((_QWORD *)a1 + 3);
  v5 = *(unsigned int *)(v4 + 1012);
  if ( (((_DWORD)v5 - 4) & 0xFFFFFFFB) != 0 )
  {
    v14 = 50;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 1) != 0 )
      WPP_SF_d(v3[7], 21, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v5);
    goto LABEL_17;
  }
  TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "KeyMgrInactiveExitAction", 253);
  RsnGroupKeys = GenerateRsnGroupKeys(*(struct MSMSEC_INTF_CONTEXT **)(v4 + 24), 0);
  v14 = RsnGroupKeys;
  TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "KeyMgrInactiveExitAction", 255);
  if ( RsnGroupKeys )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_17;
    v8 = 22;
    v9 = RsnGroupKeys;
LABEL_16:
    WPP_SF_d(v7[7], v8, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v9);
LABEL_17:
    KeyMgrNotifyKeyExchangeStatus((struct MSMSEC_PORT_CONTEXT *)v4, 1, 0x48005u);
LABEL_21:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  *(_DWORD *)(v4 + 1988) = 1;
  *(_DWORD *)(v4 + 1968) = 0;
  RSNMessage1 = KeyMgrGenerateRSNMessage1((struct MSMSEC_PORT_CONTEXT *)v4);
  v14 = RSNMessage1;
  v11 = RSNMessage1;
  if ( RSNMessage1 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_17;
    v8 = 23;
    v9 = RSNMessage1;
    goto LABEL_16;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
  {
    WPP_SF_DDDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      24,
      (unsigned int)&WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids,
      *(unsigned __int8 *)(v4 + 296),
      *(_BYTE *)(v4 + 297),
      *(_BYTE *)(v4 + 298),
      *(_BYTE *)(v4 + 299),
      *(_BYTE *)(v4 + 300),
      *(_BYTE *)(v4 + 301),
      *(_BYTE *)(v4 + 302),
      *(_BYTE *)(v4 + 303),
      *(_BYTE *)(v4 + 304),
      *(_BYTE *)(v4 + 305),
      *(_BYTE *)(v4 + 306),
      *(_BYTE *)(v4 + 307));
    goto LABEL_21;
  }
LABEL_22:
  v11 = v14;
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 25, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v14);
  return v11;
}

```

## disassembly

```asm
0x180031d50  push    rbx
0x180031d52  push    rbp
0x180031d53  push    rsi
0x180031d54  push    rdi
0x180031d55  push    r12
0x180031d57  push    r13
0x180031d59  push    r14
0x180031d5b  push    r15
0x180031d5d  sub     rsp, 88h
0x180031d64  mov     r13, rcx
0x180031d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d6e  lea     rdi, WPP_GLOBAL_Control
0x180031d75  lea     rbp, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180031d7c  cmp     rcx, rdi
0x180031d7f  jz      short loc_180031DA2
0x180031d81  test    dword ptr [rcx+44h], 100h
0x180031d88  jz      short loc_180031DA2
0x180031d8a  mov     rcx, [rcx+38h]
0x180031d8e  mov     edx, 14h
0x180031d93  mov     r8, rbp
0x180031d96  call    WPP_SF_
0x180031d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031da2  mov     r13, [r13+18h]
0x180031da6  mov     esi, 1
0x180031dab  mov     r9d, [r13+3F4h]
0x180031db2  lea     eax, [r9-4]
0x180031db6  test    eax, 0FFFFFFFBh
0x180031dbb  jz      short loc_180031DEF
0x180031dbd  mov     [rsp+0C8h+arg_0], 32h ; '2'
0x180031dc8  cmp     rcx, rdi
0x180031dcb  jz      loc_180031EE4
0x180031dd1  test    [rcx+44h], sil
0x180031dd5  jz      loc_180031EE4
0x180031ddb  mov     rcx, [rcx+38h]
0x180031ddf  lea     edx, [rsi+14h]
0x180031de2  mov     r8, rbp
0x180031de5  call    WPP_SF_d
0x180031dea  jmp     loc_180031EE4
0x180031def  mov     rcx, [r13+18h]
0x180031df3  lea     rdx, aLocking; ">>> Locking >>>"
0x180031dfa  mov     ecx, [rcx+9C0h]; unsigned int
0x180031e00  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180031e05  mov     rcx, [r13+18h]
0x180031e09  lea     r8, aKeymgrinactive; "KeyMgrInactiveExitAction"
0x180031e10  mov     r9d, 0FDh
0x180031e16  lea     rdx, [rcx+9D0h]
0x180031e1d  call    cs:__imp_AcquireWriteLock
0x180031e24  nop     dword ptr [rax+rax+00h]
0x180031e29  mov     rcx, [r13+18h]; struct MSMSEC_INTF_CONTEXT *
0x180031e2d  xor     edx, edx; bool
0x180031e2f  call    ?GenerateRsnGroupKeys@@YAKPEAUMSMSEC_INTF_CONTEXT@@_N@Z; GenerateRsnGroupKeys(MSMSEC_INTF_CONTEXT *,bool)
0x180031e34  mov     rcx, [r13+18h]
0x180031e38  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180031e3f  mov     ebx, eax
0x180031e41  mov     [rsp+0C8h+arg_0], eax
0x180031e48  mov     ecx, [rcx+9C0h]; unsigned int
0x180031e4e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180031e53  mov     rcx, [r13+18h]
0x180031e57  lea     r8, aKeymgrinactive; "KeyMgrInactiveExitAction"
0x180031e5e  mov     r9d, 0FFh
0x180031e64  lea     rdx, [rcx+9D0h]
0x180031e6b  call    cs:__imp_ReleaseWriteLock
0x180031e72  nop     dword ptr [rax+rax+00h]
0x180031e77  test    ebx, ebx
0x180031e79  jz      short loc_180031E97
0x180031e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e82  cmp     rcx, rdi
0x180031e85  jz      short loc_180031EE4
0x180031e87  test    [rcx+44h], sil
0x180031e8b  jz      short loc_180031EE4
0x180031e8d  mov     edx, 16h
0x180031e92  mov     r9d, ebx
0x180031e95  jmp     short loc_180031ED8
0x180031e97  mov     rcx, r13; struct MSMSEC_PORT_CONTEXT *
0x180031e9a  mov     [r13+7C4h], esi
0x180031ea1  mov     dword ptr [r13+7B0h], 0
0x180031eac  call    ?KeyMgrGenerateRSNMessage1@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; KeyMgrGenerateRSNMessage1(MSMSEC_PORT_CONTEXT *)
0x180031eb1  mov     [rsp+0C8h+arg_0], eax
0x180031eb8  mov     ebx, eax
0x180031eba  test    eax, eax
0x180031ebc  jz      short loc_180031EF9
0x180031ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ec5  cmp     rcx, rdi
0x180031ec8  jz      short loc_180031EE4
0x180031eca  test    [rcx+44h], sil
0x180031ece  jz      short loc_180031EE4
0x180031ed0  mov     edx, 17h
0x180031ed5  mov     r9d, eax
0x180031ed8  mov     rcx, [rcx+38h]
0x180031edc  mov     r8, rbp
0x180031edf  call    WPP_SF_d
0x180031ee4  mov     r8d, 48005h; unsigned int
0x180031eea  mov     edx, esi; int
0x180031eec  mov     rcx, r13; struct MSMSEC_PORT_CONTEXT *
0x180031eef  call    ?KeyMgrNotifyKeyExchangeStatus@@YAKPEAUMSMSEC_PORT_CONTEXT@@HK@Z; KeyMgrNotifyKeyExchangeStatus(MSMSEC_PORT_CONTEXT *,int,ulong)
0x180031ef4  jmp     loc_180031FC4
0x180031ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f00  cmp     rcx, rdi
0x180031f03  jz      loc_180031FF4
0x180031f09  test    byte ptr [rcx+44h], 10h
0x180031f0d  jz      loc_180031FCB
0x180031f13  movzx   r8d, byte ptr [r13+132h]
0x180031f1b  mov     edx, 18h
0x180031f20  movzx   ebp, byte ptr [r13+12Ch]
0x180031f28  movzx   eax, byte ptr [r13+133h]
0x180031f30  movzx   r10d, byte ptr [r13+131h]
0x180031f38  movzx   r11d, byte ptr [r13+130h]
0x180031f40  movzx   ebx, byte ptr [r13+12Fh]
0x180031f48  movzx   edi, byte ptr [r13+12Eh]
0x180031f50  movzx   esi, byte ptr [r13+12Dh]
0x180031f58  movzx   r14d, byte ptr [r13+12Bh]
0x180031f60  movzx   r15d, byte ptr [r13+12Ah]
0x180031f68  movzx   r12d, byte ptr [r13+129h]
0x180031f70  movzx   r9d, byte ptr [r13+128h]
0x180031f78  mov     rcx, [rcx+38h]
0x180031f7c  mov     [rsp+0C8h+var_58], eax
0x180031f80  mov     [rsp+0C8h+var_60], r8d
0x180031f85  mov     [rsp+0C8h+var_68], r10d
0x180031f8a  mov     [rsp+0C8h+var_70], r11d
0x180031f8f  mov     [rsp+0C8h+var_78], ebx
0x180031f93  mov     [rsp+0C8h+var_80], edi
0x180031f97  mov     [rsp+0C8h+var_88], esi
0x180031f9b  mov     [rsp+0C8h+var_90], ebp
0x180031f9f  lea     rbp, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180031fa6  mov     [rsp+0C8h+var_98], r14d
0x180031fab  mov     r8, rbp
0x180031fae  mov     [rsp+0C8h+var_A0], r15d
0x180031fb3  mov     [rsp+0C8h+var_A8], r12d
0x180031fb8  call    WPP_SF_DDDDDDDDDDDD
0x180031fbd  lea     rdi, WPP_GLOBAL_Control
0x180031fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fcb  mov     ebx, [rsp+0C8h+arg_0]
0x180031fd2  cmp     rcx, rdi
0x180031fd5  jz      short loc_180031FF4
0x180031fd7  test    dword ptr [rcx+44h], 100h
0x180031fde  jz      short loc_180031FF4
0x180031fe0  mov     rcx, [rcx+38h]
0x180031fe4  mov     edx, 19h
0x180031fe9  mov     r9d, ebx
0x180031fec  mov     r8, rbp
0x180031fef  call    WPP_SF_d
0x180031ff4  mov     eax, ebx
0x180031ff6  add     rsp, 88h
0x180031ffd  pop     r15
0x180031fff  pop     r14
0x180032001  pop     r13
0x180032003  pop     r12
0x180032005  pop     rdi
0x180032006  pop     rsi
0x180032007  pop     rbp
0x180032008  pop     rbx
0x180032009  retn
```
