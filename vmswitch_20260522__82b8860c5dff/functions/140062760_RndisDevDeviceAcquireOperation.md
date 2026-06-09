# RndisDevDeviceAcquireOperation

- ea: `0x140062760`
- end: `0x1400629d4`
- name: `RndisDevDeviceAcquireOperation`
- size: `628`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400637dc`
- `0x140092168`
- `0x1401ab1cc`
- `0x1401acbd0`

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x140062760`
- `0x1400629dc`
- `0x14008497c`
- `0x140089920`
- `0x1401a8508`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006288b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006288b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006284e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006284e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400627cc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400628cf`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400627cc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400628cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006299d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006299d`

## pseudocode

```c
__int64 __fastcall RndisDevDeviceAcquireOperation(__int64 a1, PSLIST_ENTRY *a2, unsigned __int16 a3)
{
  unsigned int v3; // r14d
  __int64 v4; // rsi
  char v6; // r13
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  __int64 v10; // rbx
  char v11; // r15
  PSLIST_ENTRY v12; // rax
  _QWORD *p_Next; // r8
  PSLIST_ENTRY v14; // rbx
  int v15; // edi
  __int64 v17; // rsi
  _QWORD *v18; // rdx
  int v19; // edx
  __int64 v20; // rdi
  PSLIST_ENTRY v21; // rax
  bool v22; // zf
  int v23; // edx
  int v24; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF
  PSLIST_ENTRY v26; // [rsp+B0h] [rbp+8h] BYREF

  v3 = a3;
  v4 = a1 - 4005040;
  *a2 = 0;
  v26 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v6 = a1;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(a1 - 4005040 + 4004768))(
          *(_QWORD *)(a1 - 4005040 + 4004784),
          a3) )
  {
    v15 = -1073741436;
    WPP_RECORDER_SF_Hd(v8, v7, v9, 30, (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids, v3, 132);
LABEL_23:
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v19, 20, 31, (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids, v6, v15);
    return (unsigned int)v15;
  }
  v10 = 16LL * v3;
  v11 = 0;
  v12 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v10 + v4 + 4002608));
  p_Next = &v12->Next;
  if ( v12 )
  {
    v14 = v12 - 58;
    *((_DWORD *)&v12[-1].Next + 2) = 1;
  }
  else
  {
    v20 = v10 + 4003632;
    while ( 1 )
    {
      v21 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v20 + v4));
      p_Next = &v21->Next;
      if ( !v21 )
        break;
      v22 = v21[2].Next == 0;
      v14 = v21 - 58;
      v26 = v21 - 58;
      if ( v22 )
        goto LABEL_19;
      v23 = *((_DWORD *)&v21[2].Next + 3);
      if ( v23 == *(_DWORD *)(v4 + 4LL * *((unsigned __int16 *)&v21[2].Next + 4) + 4005120) )
        goto LABEL_19;
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v23,
        19,
        29,
        (__int64)WPP_73b674cdc296383cdca7632fcc353cea_Traceguids,
        (__int64)"isOperationStale == FALSE");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v24 = RndisDevDeviceAllocateOperation(v4, &v26);
    v14 = v26;
    v15 = v24;
    if ( v24 < 0 )
      goto LABEL_20;
    v11 = 1;
    p_Next = &v26[58].Next;
LABEL_19:
    *((_DWORD *)&v14[57].Next + 2) = 3;
  }
  *p_Next = 0;
  v15 = RndisDevHostInitializeOpContext(v4, v14, (unsigned __int16)v3);
  if ( v15 < 0 )
  {
LABEL_20:
    (*(void (__fastcall **)(_QWORD, _QWORD))(v4 + 4004776))(*(_QWORD *)(v4 + 4004784), (unsigned __int16)v3);
    if ( v11 && v14 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 4004720));
      ExFreePoolWithTag(v14, 0);
    }
    goto LABEL_23;
  }
  if ( v11 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 4004728), &LockHandle);
    v17 = v4 + 4004736;
    v18 = *(_QWORD **)(v17 + 8);
    if ( *v18 != v17 )
      __fastfail(3u);
    v14[59].Next = (struct _SLIST_ENTRY *)v17;
    *((_QWORD *)&v14[59].Next + 1) = v18;
    *v18 = v14 + 59;
    *(_QWORD *)(v17 + 8) = v14 + 59;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  *((_BYTE *)&v14[60].Next + 10) = 1;
  v15 = 0;
  *a2 = v14;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140062760  mov     r11, rsp
0x140062763  push    rbx
0x140062764  push    rbp
0x140062765  push    rsi
0x140062766  push    rdi
0x140062767  push    r12
0x140062769  push    r13
0x14006276b  push    r14
0x14006276d  push    r15
0x14006276f  sub     rsp, 68h
0x140062773  xor     eax, eax
0x140062775  movzx   r14d, r8w
0x140062779  lea     rsi, [rcx-3D1CB0h]
0x140062780  mov     [rdx], rax
0x140062783  xorps   xmm0, xmm0
0x140062786  mov     [r11+8], rax
0x14006278a  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14006278f  mov     [r11-58h], rax
0x140062793  mov     r12, rdx
0x140062796  mov     rax, [rsi+3D1BA0h]
0x14006279d  mov     r13, rcx
0x1400627a0  mov     rcx, [rsi+3D1BB0h]
0x1400627a7  movzx   edx, r14w
0x1400627ab  call    _guard_dispatch_icall
0x1400627b0  test    al, al
0x1400627b2  jz      loc_140062899
0x1400627b8  mov     ebx, r14d
0x1400627bb  lea     rcx, [rsi+3D1330h]
0x1400627c2  shl     rbx, 4
0x1400627c6  xor     r15b, r15b
0x1400627c9  add     rcx, rbx; ListHead
0x1400627cc  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400627d3  nop     dword ptr [rax+rax+00h]
0x1400627d8  lea     rbp, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1400627df  mov     r8, rax
0x1400627e2  test    rax, rax
0x1400627e5  jz      loc_1400628C4
0x1400627eb  lea     rbx, [rax-3A0h]
0x1400627f2  mov     dword ptr [rbx+398h], 1
0x1400627fc  mov     qword ptr [r8], 0
0x140062803  mov     rdx, rbx
0x140062806  movzx   r8d, r14w
0x14006280a  mov     rcx, rsi
0x14006280d  call    RndisDevHostInitializeOpContext
0x140062812  mov     edi, eax
0x140062814  test    eax, eax
0x140062816  js      loc_140062970
0x14006281c  test    r15b, r15b
0x14006281f  jnz     short loc_140062842
0x140062821  mov     byte ptr [rbx+3CAh], 1
0x140062828  xor     edi, edi
0x14006282a  mov     [r12], rbx
0x14006282e  mov     eax, edi
0x140062830  add     rsp, 68h
0x140062834  pop     r15
0x140062836  pop     r14
0x140062838  pop     r13
0x14006283a  pop     r12
0x14006283c  pop     rdi
0x14006283d  pop     rsi
0x14006283e  pop     rbp
0x14006283f  pop     rbx
0x140062840  retn
0x140062842  lea     rcx, [rsi+3D1B78h]; SpinLock
0x140062849  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14006284e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140062855  nop     dword ptr [rax+rax+00h]
0x14006285a  add     rsi, 3D1B80h
0x140062861  mov     rdx, [rsi+8]
0x140062865  cmp     [rdx], rsi
0x140062868  jz      short loc_140062871
0x14006286a  mov     ecx, 3
0x14006286f  int     29h; Win8: RtlFailFast(ecx)
0x140062871  lea     rax, [rbx+3B0h]
0x140062878  mov     [rax], rsi
0x14006287b  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140062880  mov     [rax+8], rdx
0x140062884  mov     [rdx], rax
0x140062887  mov     [rsi+8], rax
0x14006288b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140062892  nop     dword ptr [rax+rax+00h]
0x140062897  jmp     short loc_140062821
0x140062899  mov     edi, 0C0000184h
0x14006289e  mov     [rsp+0A8h+var_78], edi
0x1400628a2  lea     rbp, WPP_73b674cdc296383cdca7632fcc353cea_Traceguids
0x1400628a9  mov     word ptr [rsp+0A8h+var_80], r14w
0x1400628af  mov     r9d, 1Eh
0x1400628b5  mov     [rsp+0A8h+var_88], rbp
0x1400628ba  call    WPP_RECORDER_SF_Hd
0x1400628bf  jmp     loc_1400629A9
0x1400628c4  lea     rdi, [rbx+3D1730h]
0x1400628cb  lea     rcx, [rdi+rsi]; ListHead
0x1400628cf  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400628d6  nop     dword ptr [rax+rax+00h]
0x1400628db  mov     r8, rax
0x1400628de  test    rax, rax
0x1400628e1  jz      short loc_140062939
0x1400628e3  cmp     qword ptr [rax+20h], 0
0x1400628e8  lea     rbx, [rax-3A0h]
0x1400628ef  mov     [rsp+0A8h+arg_0], rbx
0x1400628f7  jz      short loc_140062961
0x1400628f9  mov     edx, [rax+2Ch]
0x1400628fc  movzx   eax, word ptr [rax+28h]
0x140062900  mov     ecx, [rsi+rax*4+3D1D00h]
0x140062907  cmp     edx, ecx
0x140062909  jz      short loc_140062961
0x14006290b  mov     rcx, cs:VmsIfrLog
0x140062912  lea     rax, aIsoperationsta; "isOperationStale == FALSE"
0x140062919  mov     r9d, 1Dh
0x14006291f  mov     [rsp+0A8h+var_80], rax
0x140062924  mov     [rsp+0A8h+var_88], rbp
0x140062929  lea     r8d, [r9-0Ah]
0x14006292d  call    WPP_RECORDER_SF_s
0x140062932  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "isOperationStale == 0")
0x140062937  jmp     short loc_1400628CB
0x140062939  lea     rdx, [rsp+0A8h+arg_0]
0x140062941  mov     rcx, rsi
0x140062944  call    RndisDevDeviceAllocateOperation
0x140062949  mov     rbx, [rsp+0A8h+arg_0]
0x140062951  mov     edi, eax
0x140062953  test    eax, eax
0x140062955  js      short loc_140062970
0x140062957  mov     r15b, 1
0x14006295a  lea     r8, [rbx+3A0h]
0x140062961  mov     dword ptr [rbx+398h], 3
0x14006296b  jmp     loc_1400627FC
0x140062970  mov     rax, [rsi+3D1BA8h]
0x140062977  movzx   edx, r14w
0x14006297b  mov     rcx, [rsi+3D1BB0h]
0x140062982  call    _guard_dispatch_icall
0x140062987  test    r15b, r15b
0x14006298a  jz      short loc_1400629A9
0x14006298c  test    rbx, rbx
0x14006298f  jz      short loc_1400629A9
0x140062991  lock dec dword ptr [rsi+3D1B70h]
0x140062998  xor     edx, edx; Tag
0x14006299a  mov     rcx, rbx; P
0x14006299d  call    cs:__imp_ExFreePoolWithTag
0x1400629a4  nop     dword ptr [rax+rax+00h]
0x1400629a9  mov     rcx, cs:VmsIfrLog
0x1400629b0  mov     r9d, 1Fh
0x1400629b6  mov     [rsp+0A8h+var_78], edi
0x1400629ba  mov     dl, 2
0x1400629bc  mov     [rsp+0A8h+var_80], r13
0x1400629c1  mov     [rsp+0A8h+var_88], rbp
0x1400629c6  lea     r8d, [r9-0Bh]
0x1400629ca  call    WPP_RECORDER_SF_id
0x1400629cf  jmp     loc_14006282E
```
