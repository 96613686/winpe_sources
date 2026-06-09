# SecMgrMarkDeletedAndDerefAllPorts(MSMSEC_INTF_CONTEXT *,int)

- ea: `0x180005e80`
- end: `0x18000633e`
- name: `?SecMgrMarkDeletedAndDerefAllPorts@@YAKPEAUMSMSEC_INTF_CONTEXT@@H@Z`
- size: `1214`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1800058b8`
- `0x1800115c0`
- `0x180013bc0`

## callees

- `0x180005e80`
- `0x1800063b0`
- `0x180006d98`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x180018dd8`
- `0x180055a38`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000630e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000630e`
- `MobileNetworking!ReleaseWriteLock` at `0x180005fd1`
- `MobileNetworking!ReleaseWriteLock` at `0x180006059`
- `MobileNetworking!ReleaseWriteLock` at `0x1800060d0`
- `MobileNetworking!ReleaseWriteLock` at `0x180006188`
- `MobileNetworking!ReleaseWriteLock` at `0x180005fd1`
- `MobileNetworking!ReleaseWriteLock` at `0x180006059`
- `MobileNetworking!ReleaseWriteLock` at `0x1800060d0`
- `MobileNetworking!ReleaseWriteLock` at `0x180006188`
- `MobileNetworking!AcquireWriteLock` at `0x180005edf`
- `MobileNetworking!AcquireWriteLock` at `0x18000600f`
- `MobileNetworking!AcquireWriteLock` at `0x18000610a`
- `MobileNetworking!AcquireWriteLock` at `0x1800061cb`
- `MobileNetworking!AcquireWriteLock` at `0x180005edf`
- `MobileNetworking!AcquireWriteLock` at `0x18000600f`
- `MobileNetworking!AcquireWriteLock` at `0x18000610a`
- `MobileNetworking!AcquireWriteLock` at `0x1800061cb`

## string_xrefs

- `0x180005ecf`: `SecMgrMarkDeletedAndDerefAllPorts`
- `0x180005fc4`: `SecMgrMarkDeletedAndDerefAllPorts`
- `0x180006002`: `SecMgrMarkDeletedAndDerefAllPorts`
- `0x18000604c`: `SecMgrMarkDeletedAndDerefAllPorts`
- `0x1800060c3`: `SecMgrMarkDeletedAndDerefAllPorts`
- `0x1800060fd`: `SecMgrMarkDeletedAndDerefAllPorts`

## pseudocode

```c
__int64 __fastcall SecMgrMarkDeletedAndDerefAllPorts(struct MSMSEC_INTF_CONTEXT *a1, int a2, int a3)
{
  PVOID *v5; // rcx
  PVOID *v6; // rcx
  struct MSMSEC_INTF_CONTEXT *v7; // rdi
  struct MSMSEC_PORT_CONTEXT **v8; // rsi
  struct MSMSEC_PORT_CONTEXT *v9; // rdi
  __int64 v10; // rax
  struct MSMSEC_INTF_CONTEXT **v11; // rcx
  int v12; // r14d
  struct MSMSEC_INTF_CONTEXT **v13; // rcx
  int v14; // r8d
  PVOID *v15; // rcx
  int v16; // r8d
  _QWORD *v18; // rdi
  _QWORD *v19; // rsi
  unsigned int v20; // eax
  unsigned int v21; // eax

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 113, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v5[7], 11, a3, *((_DWORD *)a1 + 624), (__int64)">>> Locking >>>");
  }
  AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1473);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 114, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, a1);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = (struct MSMSEC_INTF_CONTEXT *)*((_QWORD *)a1 + 333);
  if ( v7 )
  {
    *((_QWORD *)a1 + 333) = 0;
    v13 = (struct MSMSEC_INTF_CONTEXT **)*((_QWORD *)a1 + 337);
    if ( *v13 != (struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2688) )
LABEL_13:
      __fastfail(3u);
    *(_QWORD *)v7 = (char *)a1 + 2688;
    *((_QWORD *)v7 + 1) = v13;
    *v13 = v7;
    *((_QWORD *)a1 + 337) = v7;
    TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1486);
    SecMgrPreDestroyInfraPort(v7);
    v20 = SecMgrDestroyPort(v7, 0);
    if ( v20 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 115, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v20);
    TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
    AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1496);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = (struct MSMSEC_PORT_CONTEXT **)((char *)a1 + 2672);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == (struct MSMSEC_PORT_CONTEXT *)v8 )
    {
      v9 = 0;
      v12 = 1;
    }
    else
    {
      if ( *((struct MSMSEC_PORT_CONTEXT ***)v9 + 1) != v8 )
        goto LABEL_13;
      v10 = *(_QWORD *)v9;
      if ( *(struct MSMSEC_PORT_CONTEXT **)(*(_QWORD *)v9 + 8LL) != v9 )
        goto LABEL_13;
      *v8 = (struct MSMSEC_PORT_CONTEXT *)v10;
      *(_QWORD *)(v10 + 8) = v8;
      v11 = (struct MSMSEC_INTF_CONTEXT **)*((_QWORD *)a1 + 337);
      if ( *v11 != (struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2688) )
        goto LABEL_13;
      *(_QWORD *)v9 = (char *)a1 + 2688;
      v12 = 0;
      *((_QWORD *)v9 + 1) = v11;
      *v11 = v9;
      *((_QWORD *)a1 + 337) = v9;
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x100) != 0 )
      WPP_SF_Ls(
        (unsigned int)v6[7],
        11,
        (unsigned int)"<<< Unlocking <<<",
        *((_DWORD *)a1 + 624),
        (__int64)"<<< Unlocking <<<");
    ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1514);
    if ( !v9 )
      goto LABEL_19;
    SecMgrPreDestroyInfraPort(v9);
    v21 = SecMgrDestroyPort(v9, 0);
    if ( !v21 )
      goto LABEL_19;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_23;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 116, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v21);
LABEL_19:
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v15[7], 11, v14, *((_DWORD *)a1 + 624), (__int64)">>> Locking >>>");
LABEL_23:
    AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1527);
    if ( v12 )
      break;
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v18 = (_QWORD *)((char *)a1 + 2688);
    do
    {
      v19 = (_QWORD *)*v18;
      TraceAdapterId(*((_DWORD *)a1 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1539);
      if ( v19 != v18 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 117, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
        Sleep(0x64u);
      }
      TraceAdapterId(*((_DWORD *)a1 + 624), ">>> Locking >>>");
      AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1549);
    }
    while ( v19 != v18 );
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v16, *((_DWORD *)a1 + 624), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrMarkDeletedAndDerefAllPorts", 1560);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 118, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180005e80  push    rbx
0x180005e82  push    rbp
0x180005e83  push    rsi
0x180005e84  push    rdi
0x180005e85  push    r12
0x180005e87  push    r13
0x180005e89  push    r14
0x180005e8b  push    r15
0x180005e8d  sub     rsp, 38h
0x180005e91  mov     r15d, edx
0x180005e94  mov     rbx, rcx
0x180005e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e9e  lea     r12, WPP_GLOBAL_Control
0x180005ea5  lea     rax, aLocking; ">>> Locking >>>"
0x180005eac  mov     r13d, 100h
0x180005eb2  lea     r14, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180005eb9  cmp     rcx, r12
0x180005ebc  jnz     loc_180006121
0x180005ec2  lea     rbp, [rbx+9D0h]
0x180005ec9  mov     r9d, 5C1h
0x180005ecf  lea     rsi, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x180005ed6  mov     rdx, rbp
0x180005ed9  mov     r8, rsi
0x180005edc  mov     rcx, rbx
0x180005edf  call    cs:__imp_AcquireWriteLock
0x180005ee6  nop     dword ptr [rax+rax+00h]
0x180005eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ef2  cmp     rcx, r12
0x180005ef5  jnz     short loc_180005F5D
0x180005ef7  mov     rdi, [rbx+0A68h]
0x180005efe  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x180005f05  test    rdi, rdi
0x180005f08  jnz     short loc_180005F83
0x180005f0a  lea     rsi, [rbx+0A70h]
0x180005f11  mov     rdi, [rsi]
0x180005f14  cmp     rdi, rsi
0x180005f17  jz      loc_180005FA9
0x180005f1d  cmp     [rdi+8], rsi
0x180005f21  jnz     short loc_180005FA2
0x180005f23  mov     rax, [rdi]
0x180005f26  cmp     [rax+8], rdi
0x180005f2a  jnz     short loc_180005FA2
0x180005f2c  mov     [rsi], rax
0x180005f2f  mov     [rax+8], rsi
0x180005f33  lea     rax, [rbx+0A80h]
0x180005f3a  mov     rcx, [rax+8]
0x180005f3e  cmp     [rcx], rax
0x180005f41  jnz     short loc_180005FA2
0x180005f43  mov     [rdi], rax
0x180005f46  xor     r14d, r14d
0x180005f49  mov     [rdi+8], rcx
0x180005f4d  mov     [rcx], rdi
0x180005f50  mov     [rax+8], rdi
0x180005f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f5b  jmp     short loc_180005FAF
0x180005f5d  test    byte ptr [rcx+44h], 2
0x180005f61  jz      short loc_180005EF7
0x180005f63  mov     rcx, [rcx+38h]
0x180005f67  mov     edx, 72h ; 'r'
0x180005f6c  mov     r9, rbx
0x180005f6f  mov     r8, r14
0x180005f72  call    WPP_SF_q
0x180005f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f7e  jmp     loc_180005EF7
0x180005f83  lea     rax, [rbx+0A80h]
0x180005f8a  mov     qword ptr [rbx+0A68h], 0
0x180005f95  mov     rcx, [rax+8]
0x180005f99  cmp     [rcx], rax
0x180005f9c  jz      loc_18000615D
0x180005fa2  mov     ecx, 3
0x180005fa7  int     29h; Win8: RtlFailFast(ecx)
0x180005fa9  xor     edi, edi
0x180005fab  lea     r14d, [rdi+1]
0x180005faf  cmp     rcx, r12
0x180005fb2  jz      short loc_180005FBE
0x180005fb4  test    [rcx+44h], r13d
0x180005fb8  jnz     loc_180006239
0x180005fbe  mov     r9d, 5EAh
0x180005fc4  lea     r8, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x180005fcb  mov     rdx, rbp
0x180005fce  mov     rcx, rbx
0x180005fd1  call    cs:__imp_ReleaseWriteLock
0x180005fd8  nop     dword ptr [rax+rax+00h]
0x180005fdd  test    rdi, rdi
0x180005fe0  jnz     loc_180006258
0x180005fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fed  cmp     rcx, r12
0x180005ff0  jz      short loc_180005FFC
0x180005ff2  test    [rcx+44h], r13d
0x180005ff6  jnz     loc_1800062A9
0x180005ffc  mov     r9d, 5F7h
0x180006002  lea     r8, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x180006009  mov     rdx, rbp
0x18000600c  mov     rcx, rbx
0x18000600f  call    cs:__imp_AcquireWriteLock
0x180006016  nop     dword ptr [rax+rax+00h]
0x18000601b  test    r14d, r14d
0x18000601e  jz      loc_1800062CF
0x180006024  lea     r14, aUnlocking; "<<< Unlocking <<<"
0x18000602b  test    r15d, r15d
0x18000602e  jnz     short loc_1800060A5
0x180006030  mov     rcx, cs:WPP_GLOBAL_Control
0x180006037  cmp     rcx, r12
0x18000603a  jz      short loc_180006046
0x18000603c  test    [rcx+44h], r13d
0x180006040  jnz     loc_18000631F
0x180006046  mov     r9d, 618h
0x18000604c  lea     r8, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x180006053  mov     rdx, rbp
0x180006056  mov     rcx, rbx
0x180006059  call    cs:__imp_ReleaseWriteLock
0x180006060  nop     dword ptr [rax+rax+00h]
0x180006065  mov     rcx, cs:WPP_GLOBAL_Control
0x18000606c  cmp     rcx, r12
0x18000606f  jnz     short loc_180006085
0x180006071  xor     eax, eax
0x180006073  add     rsp, 38h
0x180006077  pop     r15
0x180006079  pop     r14
0x18000607b  pop     r13
0x18000607d  pop     r12
0x18000607f  pop     rdi
0x180006080  pop     rsi
0x180006081  pop     rbp
0x180006082  pop     rbx
0x180006083  retn
0x180006085  test    [rcx+44h], r13d
0x180006089  jz      short loc_180006071
0x18000608b  mov     rcx, [rcx+38h]
0x18000608f  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180006096  mov     edx, 76h ; 'v'
0x18000609b  xor     r9d, r9d
0x18000609e  call    WPP_SF_d
0x1800060a3  jmp     short loc_180006071
0x1800060a5  lea     rdi, [rbx+0A80h]
0x1800060ac  mov     ecx, [rbx+9C0h]; unsigned int
0x1800060b2  mov     rdx, r14; char *
0x1800060b5  mov     rsi, [rdi]
0x1800060b8  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800060bd  mov     r9d, 603h
0x1800060c3  lea     r8, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x1800060ca  mov     rdx, rbp
0x1800060cd  mov     rcx, rbx
0x1800060d0  call    cs:__imp_ReleaseWriteLock
0x1800060d7  nop     dword ptr [rax+rax+00h]
0x1800060dc  cmp     rsi, rdi
0x1800060df  jnz     loc_1800062E2
0x1800060e5  mov     ecx, [rbx+9C0h]; unsigned int
0x1800060eb  lea     rdx, aLocking; ">>> Locking >>>"
0x1800060f2  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800060f7  mov     r9d, 60Dh
0x1800060fd  lea     r8, aSecmgrmarkdele_0; "SecMgrMarkDeletedAndDerefAllPorts"
0x180006104  mov     rdx, rbp
0x180006107  mov     rcx, rbx
0x18000610a  call    cs:__imp_AcquireWriteLock
0x180006111  nop     dword ptr [rax+rax+00h]
0x180006116  cmp     rsi, rdi
0x180006119  jz      loc_180006030
0x18000611f  jmp     short loc_1800060AC
0x180006121  test    [rcx+44h], r13d
0x180006125  jnz     loc_1800061EA
0x18000612b  cmp     rcx, r12
0x18000612e  jz      loc_180005EC2
0x180006134  test    [rcx+44h], r13d
0x180006138  jz      loc_180005EC2
0x18000613e  mov     r9d, [rbx+9C0h]
0x180006145  mov     edx, 0Bh
0x18000614a  mov     rcx, [rcx+38h]
0x18000614e  mov     [rsp+78h+var_58], rax
0x180006153  call    WPP_SF_Ls
0x180006158  jmp     loc_180005EC2
0x18000615d  mov     [rdi], rax
0x180006160  mov     rdx, r8; char *
0x180006163  mov     [rdi+8], rcx
0x180006167  mov     [rcx], rdi
0x18000616a  mov     [rax+8], rdi
0x18000616e  mov     ecx, [rbx+9C0h]; unsigned int
0x180006174  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180006179  mov     r9d, 5CEh
0x18000617f  mov     r8, rsi
0x180006182  mov     rdx, rbp
0x180006185  mov     rcx, rbx
0x180006188  call    cs:__imp_ReleaseWriteLock
0x18000618f  nop     dword ptr [rax+rax+00h]
0x180006194  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180006197  call    ?SecMgrPreDestroyInfraPort@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrPreDestroyInfraPort(MSMSEC_PORT_CONTEXT *)
0x18000619c  xor     edx, edx; unsigned int *
0x18000619e  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x1800061a1  call    ?SecMgrDestroyPort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAK@Z; SecMgrDestroyPort(MSMSEC_PORT_CONTEXT *,ulong *)
0x1800061a6  test    eax, eax
0x1800061a8  jnz     short loc_18000620E
0x1800061aa  mov     ecx, [rbx+9C0h]; unsigned int
0x1800061b0  lea     rdx, aLocking; ">>> Locking >>>"
0x1800061b7  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800061bc  mov     r9d, 5D8h
0x1800061c2  mov     r8, rsi
0x1800061c5  mov     rdx, rbp
0x1800061c8  mov     rcx, rbx
0x1800061cb  call    cs:__imp_AcquireWriteLock
0x1800061d2  nop     dword ptr [rax+rax+00h]
0x1800061d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061de  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x1800061e5  jmp     loc_180005F0A
0x1800061ea  mov     rcx, [rcx+38h]
0x1800061ee  mov     edx, 71h ; 'q'
0x1800061f3  mov     r8, r14
0x1800061f6  call    WPP_SF_
0x1800061fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006202  lea     rax, aLocking; ">>> Locking >>>"
0x180006209  jmp     loc_18000612B
0x18000620e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006215  cmp     rcx, r12
0x180006218  jz      short loc_1800061AA
0x18000621a  test    byte ptr [rcx+44h], 1
0x18000621e  jz      short loc_1800061AA
0x180006220  mov     rcx, [rcx+38h]
0x180006224  mov     edx, 73h ; 's'
0x180006229  mov     r9d, eax
0x18000622c  mov     r8, r14
0x18000622f  call    WPP_SF_d
0x180006234  jmp     loc_1800061AA
0x180006239  mov     r9d, [rbx+9C0h]
0x180006240  mov     edx, 0Bh
0x180006245  mov     rcx, [rcx+38h]
0x180006249  mov     [rsp+78h+var_58], r8
0x18000624e  call    WPP_SF_Ls
0x180006253  jmp     loc_180005FBE
0x180006258  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18000625b  call    ?SecMgrPreDestroyInfraPort@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrPreDestroyInfraPort(MSMSEC_PORT_CONTEXT *)
0x180006260  xor     edx, edx; unsigned int *
0x180006262  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180006265  call    ?SecMgrDestroyPort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAK@Z; SecMgrDestroyPort(MSMSEC_PORT_CONTEXT *,ulong *)
0x18000626a  test    eax, eax
0x18000626c  jz      loc_180005FE6
0x180006272  mov     rcx, cs:WPP_GLOBAL_Control
0x180006279  cmp     rcx, r12
0x18000627c  jz      loc_180005FFC
0x180006282  test    byte ptr [rcx+44h], 1
0x180006286  jz      loc_180005FED
0x18000628c  mov     rcx, [rcx+38h]
0x180006290  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180006297  mov     edx, 74h ; 't'
0x18000629c  mov     r9d, eax
0x18000629f  call    WPP_SF_d
0x1800062a4  jmp     loc_180005FE6
0x1800062a9  mov     r9d, [rbx+9C0h]
0x1800062b0  lea     rax, aLocking; ">>> Locking >>>"
0x1800062b7  mov     rcx, [rcx+38h]
0x1800062bb  mov     edx, 0Bh
0x1800062c0  mov     [rsp+78h+var_58], rax
0x1800062c5  call    WPP_SF_Ls
0x1800062ca  jmp     loc_180005FFC
0x1800062cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062d6  lea     r8, aUnlocking; "<<< Unlocking <<<"
0x1800062dd  jmp     loc_180005F11
0x1800062e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062e9  cmp     rcx, r12
0x1800062ec  jz      short loc_180006309
0x1800062ee  test    byte ptr [rcx+44h], 2
0x1800062f2  jz      short loc_180006309
0x1800062f4  mov     rcx, [rcx+38h]
0x1800062f8  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x1800062ff  mov     edx, 75h ; 'u'
0x180006304  call    WPP_SF_
0x180006309  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000630e  call    cs:__imp_Sleep
0x180006315  nop     dword ptr [rax+rax+00h]
0x18000631a  jmp     loc_1800060E5
0x18000631f  mov     r9d, [rbx+9C0h]
0x180006326  mov     edx, 0Bh
0x18000632b  mov     rcx, [rcx+38h]
0x18000632f  mov     [rsp+78h+var_58], r14
0x180006334  call    WPP_SF_Ls
0x180006339  jmp     loc_180006046
```
