# AcquirePortReservationWithFlags

- ea: `0x1400b25dc`
- end: `0x1400b2921`
- name: `AcquirePortReservationWithFlags`
- size: `837`
- prototype: `__int64 __usercall@<rax>(PERESOURCE Resource@<rcx>, PEPROCESS Process, __int64, __int16)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b1540`
- `0x1400b1c00`
- `0x14015b6f0`
- `0x14015bd80`
- `0x14015c290`

## callees

- `0x1400b19b0`
- `0x1400b25dc`
- `0x1400b2928`
- `0x1400b3fb0`
- `0x1400b48c8`
- `0x140151200`
- `0x14015c550`
- `0x14015c5f0`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x1400b28fd`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400b28fd`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b2871`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b2871`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b26f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2824`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b26f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2824`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400b26e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400b2818`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400b26e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400b2818`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400b26ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400b27ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400b26ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400b27ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b269c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b27dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b269c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b27dd`
- `ntoskrnl!PsGetProcessId` at `0x1400b2883`
- `ntoskrnl!PsGetProcessId` at `0x1400b290f`
- `ntoskrnl!PsGetProcessId` at `0x1400b2883`
- `ntoskrnl!PsGetProcessId` at `0x1400b290f`

## pseudocode

```c
__int64 __fastcall AcquirePortReservationWithFlags(
        PERESOURCE Resource,
        _WORD *a2,
        unsigned __int16 a3,
        __int64 a4,
        PEPROCESS Process,
        _QWORD *a6,
        unsigned __int16 a7)
{
  char ProcessStartKey; // r13
  unsigned int v9; // r12d
  unsigned __int16 Exclusion; // si
  bool v11; // di
  int v12; // ebx
  unsigned __int16 v14; // r13
  int v15; // ebx
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  PVOID *p_SharedWaiters; // rcx
  PVOID *v21; // rdx
  __int64 v22; // rax
  char ProcessSequenceNumber; // bl
  unsigned int ProcessId; // r9d
  unsigned int v25; // eax
  __int16 v26[2]; // [rsp+50h] [rbp-51h] BYREF
  int v27; // [rsp+54h] [rbp-4Dh]
  PVOID v28; // [rsp+58h] [rbp-49h] BYREF
  int v29; // [rsp+60h] [rbp-41h]
  _QWORD *v30; // [rsp+68h] [rbp-39h]
  __int64 v31; // [rsp+70h] [rbp-31h]
  _WORD *v32; // [rsp+78h] [rbp-29h]
  _WORD v33[2]; // [rsp+80h] [rbp-21h] BYREF
  int Flink; // [rsp+84h] [rbp-1Dh]
  int v35; // [rsp+88h] [rbp-19h]

  ProcessStartKey = -1;
  v9 = a3;
  Exclusion = __ROR2__(*a2, 8);
  v32 = a2;
  v31 = a4;
  v30 = a6;
  v28 = 0;
  if ( a3 && a3 + (unsigned int)Exclusion <= 0x10000 )
  {
    v27 = 1;
    v14 = Exclusion;
    v15 = 1;
    v11 = Exclusion == 0;
    while ( 1 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(Resource, 1u);
      Exclusion = CreateExclusion(Resource, a7, Exclusion, v9, v31, Process, v30);
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
      if ( !Exclusion )
      {
        v12 = v14 != 0 ? -1073741757 : -1073741303;
        goto LABEL_23;
      }
      if ( !PortTrackerEnabled )
        goto LABEL_22;
      v26[0] = 0;
      v33[0] = Exclusion;
      v33[1] = Exclusion + v9 - 1;
      Flink = (int)Resource[1].SystemResourcesList.Flink;
      v35 = 2 - ((a7 & 0x10) != 0);
      v16 = PtClientReservePortRange(v33, &v28, v26);
      v19 = 0;
      v29 = v16;
      if ( !v16 )
      {
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(Resource, 1u);
        v22 = FindExclusion(Resource[1].SharedWaiters, *v30);
        *(_QWORD *)(v22 + 32) = v28;
        ExReleaseResourceLite(Resource);
        KeLeaveCriticalRegion();
LABEL_22:
        v12 = 0;
        *v32 = __ROR2__(Exclusion, 8);
        goto LABEL_23;
      }
      if ( SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        if ( Process )
        {
          ProcessSequenceNumber = PsGetProcessSequenceNumber(Process);
          ProcessId = (unsigned int)PsGetProcessId(Process);
        }
        else
        {
          ProcessId = -1;
          ProcessSequenceNumber = -1;
        }
        McTemplateK0qqqqhhx_EtwWriteTransfer(
          v18,
          v17,
          v19,
          ProcessId,
          v29,
          v35,
          (char)Resource[1].SystemResourcesList.Flink,
          Exclusion,
          v9,
          ProcessSequenceNumber);
        v15 = v27;
      }
      p_SharedWaiters = &Resource[1].SharedWaiters;
      v28 = 0;
      while ( 1 )
      {
        v21 = (PVOID *)*p_SharedWaiters;
        if ( !*p_SharedWaiters )
          break;
        if ( (unsigned int)*v30 == *((_DWORD *)v21 + 3) )
        {
          if ( !Process || Process == v21[5] )
          {
            *p_SharedWaiters = *v21;
            v28 = v21[4];
            DeleteExclusion(Resource, v21);
          }
          break;
        }
        p_SharedWaiters = (PVOID *)*p_SharedWaiters;
      }
      if ( v14 )
        break;
      if ( !v26[0] || v15 == 3 )
      {
        v12 = -1073741303;
        goto LABEL_23;
      }
      ++v15;
      Exclusion = 0;
      v27 = v15;
    }
    v12 = -1073741757;
LABEL_23:
    ProcessStartKey = -1;
  }
  else
  {
    v11 = 0;
    v12 = -1073741811;
  }
  if ( LOBYTE(WPP_MAIN_CB.DeviceType) && v12 < 0 && !v11 )
    TraceVailGuestPortFailure(
      (_DWORD)Process,
      Resource[1].SystemResourcesList.Flink,
      Exclusion,
      (unsigned __int16)v9,
      v12,
      1);
  if ( SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
  {
    if ( Process )
    {
      ProcessStartKey = PsGetProcessStartKey(Process);
      v25 = (unsigned int)PsGetProcessId(Process);
    }
    else
    {
      v25 = -1;
    }
    McTemplateK0qqhhx_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCP_GLOBAL_PORT_RESERVATION_V1,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v25,
      v12,
      Exclusion,
      v9,
      ProcessStartKey);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400b25dc  push    rbp
0x1400b25de  push    rbx
0x1400b25df  push    rsi
0x1400b25e0  push    rdi
0x1400b25e1  push    r12
0x1400b25e3  push    r13
0x1400b25e5  push    r14
0x1400b25e7  push    r15
0x1400b25e9  lea     rbp, [rsp-7]
0x1400b25ee  sub     rsp, 0A8h
0x1400b25f5  mov     rax, cs:__security_cookie
0x1400b25fc  xor     rax, rsp
0x1400b25ff  mov     [rbp+3Fh+var_50], rax
0x1400b2603  movzx   esi, word ptr [rdx]
0x1400b2606  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400b260a  mov     rax, [rbp+3Fh+arg_28]
0x1400b260e  mov     r15, rcx
0x1400b2611  mov     r14, [rbp+3Fh+Process]
0x1400b2615  movzx   r12d, r8w
0x1400b2619  xor     r8d, r8d
0x1400b261c  ror     si, 8
0x1400b2620  mov     [rbp+3Fh+var_68], rdx
0x1400b2624  mov     [rbp+3Fh+var_70], r9
0x1400b2628  mov     [rbp+3Fh+var_78], rax
0x1400b262c  lea     edx, [r8+1]
0x1400b2630  mov     [rbp+3Fh+var_88], r8
0x1400b2634  test    r12w, r12w
0x1400b2638  jnz     short loc_1400B267F
0x1400b263a  mov     dil, r8b
0x1400b263d  mov     ebx, 0C000000Dh
0x1400b2642  cmp     byte ptr cs:WPP_MAIN_CB.DeviceType, r8b
0x1400b2649  jnz     loc_1400B28BC
0x1400b264f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, r8b
0x1400b2656  jl      loc_1400B28F1
0x1400b265c  mov     eax, ebx
0x1400b265e  mov     rcx, [rbp+3Fh+var_50]
0x1400b2662  xor     rcx, rsp; StackCookie
0x1400b2665  call    __security_check_cookie
0x1400b266a  add     rsp, 0A8h
0x1400b2671  pop     r15
0x1400b2673  pop     r14
0x1400b2675  pop     r13
0x1400b2677  pop     r12
0x1400b2679  pop     rdi
0x1400b267a  pop     rsi
0x1400b267b  pop     rbx
0x1400b267c  pop     rbp
0x1400b267d  retn
0x1400b267f  movzx   eax, si
0x1400b2682  add     eax, r12d
0x1400b2685  cmp     eax, 10000h
0x1400b268a  ja      short loc_1400B263A
0x1400b268c  test    si, si
0x1400b268f  mov     [rbp+3Fh+var_8C], edx
0x1400b2692  movzx   r13d, si
0x1400b2696  mov     ebx, edx
0x1400b2698  setz    dil
0x1400b269c  call    cs:__imp_KeEnterCriticalRegion
0x1400b26a3  nop     dword ptr [rax+rax+00h]
0x1400b26a8  mov     dl, 1; Wait
0x1400b26aa  mov     rcx, r15; Resource
0x1400b26ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400b26b4  nop     dword ptr [rax+rax+00h]
0x1400b26b9  mov     rax, [rbp+3Fh+var_78]
0x1400b26bd  mov     r9d, r12d
0x1400b26c0  movzx   edx, [rbp+3Fh+arg_30]
0x1400b26c4  mov     rcx, r15
0x1400b26c7  mov     [rsp+0E0h+var_B0], rax
0x1400b26cc  mov     rax, [rbp+3Fh+var_70]
0x1400b26d0  movzx   r8d, si
0x1400b26d4  mov     [rsp+0E0h+var_B8], r14
0x1400b26d9  mov     [rsp+0E0h+var_C0], rax
0x1400b26de  call    CreateExclusion
0x1400b26e3  mov     rcx, r15; Resource
0x1400b26e6  movzx   esi, ax
0x1400b26e9  call    cs:__imp_ExReleaseResourceLite
0x1400b26f0  nop     dword ptr [rax+rax+00h]
0x1400b26f5  call    cs:__imp_KeLeaveCriticalRegion
0x1400b26fc  nop     dword ptr [rax+rax+00h]
0x1400b2701  xor     r8d, r8d
0x1400b2704  test    si, si
0x1400b2707  jz      loc_1400B2851
0x1400b270d  cmp     cs:PortTrackerEnabled, r8b
0x1400b2714  jz      loc_1400B2833
0x1400b271a  lea     eax, [r12-1]
0x1400b271f  mov     [rbp+3Fh+var_90], r8w
0x1400b2724  add     ax, si
0x1400b2727  mov     [rbp+3Fh+var_60], si
0x1400b272b  mov     [rbp+3Fh+var_5E], ax
0x1400b272f  lea     r8, [rbp+3Fh+var_90]
0x1400b2733  mov     eax, [r15+68h]
0x1400b2737  lea     rdx, [rbp+3Fh+var_88]
0x1400b273b  mov     [rbp+3Fh+var_5C], eax
0x1400b273e  lea     rcx, [rbp+3Fh+var_60]
0x1400b2742  mov     al, byte ptr [rbp+3Fh+arg_30]
0x1400b2745  and     al, 10h
0x1400b2747  neg     al
0x1400b2749  sbb     eax, eax
0x1400b274b  add     eax, 2
0x1400b274e  mov     [rbp+3Fh+var_58], eax
0x1400b2751  call    PtClientReservePortRange
0x1400b2756  xor     r8d, r8d
0x1400b2759  mov     [rbp+3Fh+var_80], eax
0x1400b275c  test    eax, eax
0x1400b275e  jz      short loc_1400B27DD
0x1400b2760  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, r8b
0x1400b2767  jl      loc_1400B2865
0x1400b276d  mov     rax, [rbp+3Fh+var_78]
0x1400b2771  lea     rcx, [r15+88h]
0x1400b2778  mov     [rbp+3Fh+var_88], r8
0x1400b277c  mov     rax, [rax]
0x1400b277f  mov     rdx, [rcx]
0x1400b2782  test    rdx, rdx
0x1400b2785  jz      short loc_1400B27B2
0x1400b2787  cmp     eax, [rdx+0Ch]
0x1400b278a  jnz     loc_1400B2897
0x1400b2790  test    r14, r14
0x1400b2793  jnz     loc_1400B289F
0x1400b2799  mov     rax, [rdx]
0x1400b279c  mov     [rcx], rax
0x1400b279f  mov     rcx, r15
0x1400b27a2  mov     rax, [rdx+20h]
0x1400b27a6  mov     [rbp+3Fh+var_88], rax
0x1400b27aa  call    DeleteExclusion
0x1400b27af  xor     r8d, r8d
0x1400b27b2  test    r13w, r13w
0x1400b27b6  jnz     loc_1400B28B5
0x1400b27bc  cmp     [rbp+3Fh+var_90], r8w
0x1400b27c1  jz      loc_1400B28AE
0x1400b27c7  cmp     ebx, 3
0x1400b27ca  jz      loc_1400B28AE
0x1400b27d0  inc     ebx
0x1400b27d2  mov     esi, r8d
0x1400b27d5  mov     [rbp+3Fh+var_8C], ebx
0x1400b27d8  jmp     loc_1400B269C
0x1400b27dd  call    cs:__imp_KeEnterCriticalRegion
0x1400b27e4  nop     dword ptr [rax+rax+00h]
0x1400b27e9  mov     dl, 1; Wait
0x1400b27eb  mov     rcx, r15; Resource
0x1400b27ee  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400b27f5  nop     dword ptr [rax+rax+00h]
0x1400b27fa  mov     rax, [rbp+3Fh+var_78]
0x1400b27fe  mov     rcx, [r15+88h]
0x1400b2805  mov     rdx, [rax]
0x1400b2808  call    FindExclusion
0x1400b280d  mov     rcx, [rbp+3Fh+var_88]
0x1400b2811  mov     [rax+20h], rcx
0x1400b2815  mov     rcx, r15; Resource
0x1400b2818  call    cs:__imp_ExReleaseResourceLite
0x1400b281f  nop     dword ptr [rax+rax+00h]
0x1400b2824  call    cs:__imp_KeLeaveCriticalRegion
0x1400b282b  nop     dword ptr [rax+rax+00h]
0x1400b2830  xor     r8d, r8d
0x1400b2833  mov     rcx, [rbp+3Fh+var_68]
0x1400b2837  movzx   eax, si
0x1400b283a  ror     ax, 8
0x1400b283e  mov     ebx, r8d
0x1400b2841  mov     [rcx], ax
0x1400b2844  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400b2848  lea     edx, [r13+2]
0x1400b284c  jmp     loc_1400B2642
0x1400b2851  neg     r13w
0x1400b2855  mov     ebx, 0C0000209h
0x1400b285a  sbb     eax, eax
0x1400b285c  and     eax, 0FFFFFE3Ah
0x1400b2861  add     ebx, eax
0x1400b2863  jmp     short loc_1400B2844
0x1400b2865  test    r14, r14
0x1400b2868  jz      loc_1401CEE62
0x1400b286e  mov     rcx, r14
0x1400b2871  call    cs:__imp_PsGetProcessSequenceNumber
0x1400b2878  nop     dword ptr [rax+rax+00h]
0x1400b287d  mov     rcx, r14; Process
0x1400b2880  mov     rbx, rax
0x1400b2883  call    cs:__imp_PsGetProcessId
0x1400b288a  nop     dword ptr [rax+rax+00h]
0x1400b288f  mov     r9, rax
0x1400b2892  jmp     loc_1401CEE6A
0x1400b2897  mov     rcx, rdx
0x1400b289a  jmp     loc_1400B277F
0x1400b289f  cmp     r14, [rdx+28h]
0x1400b28a3  jnz     loc_1400B27B2
0x1400b28a9  jmp     loc_1400B2799
0x1400b28ae  mov     ebx, 0C0000209h
0x1400b28b3  jmp     short loc_1400B2844
0x1400b28b5  mov     ebx, 0C0000043h
0x1400b28ba  jmp     short loc_1400B2844
0x1400b28bc  test    ebx, ebx
0x1400b28be  jns     loc_1400B264F
0x1400b28c4  test    dil, dil
0x1400b28c7  jnz     loc_1400B264F
0x1400b28cd  mov     byte ptr [rsp+0E0h+var_B8], dl
0x1400b28d1  movzx   r9d, r12w
0x1400b28d5  mov     edx, [r15+68h]
0x1400b28d9  movzx   r8d, si
0x1400b28dd  mov     rcx, r14
0x1400b28e0  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1400b28e4  call    TraceVailGuestPortFailure
0x1400b28e9  xor     r8d, r8d
0x1400b28ec  jmp     loc_1400B264F
0x1400b28f1  test    r14, r14
0x1400b28f4  jz      loc_1401CEEA0
0x1400b28fa  mov     rcx, r14
0x1400b28fd  call    cs:__imp_PsGetProcessStartKey
0x1400b2904  nop     dword ptr [rax+rax+00h]
0x1400b2909  mov     rcx, r14; Process
0x1400b290c  mov     r13, rax
0x1400b290f  call    cs:__imp_PsGetProcessId
0x1400b2916  nop     dword ptr [rax+rax+00h]
0x1400b291b  nop
0x1400b291c  jmp     loc_1401CEEA3
0x1401cee62  or      r9d, 0FFFFFFFFh
0x1401cee66  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1401cee6a  mov     eax, [r15+68h]
0x1401cee6e  mov     [rsp+0E0h+var_98], rbx
0x1401cee73  mov     [rsp+0E0h+var_A0], r12w
0x1401cee79  mov     word ptr [rsp+0E0h+var_A8], si
0x1401cee7e  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1401cee82  mov     eax, [rbp+3Fh+var_58]
0x1401cee85  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1401cee89  mov     eax, [rbp+3Fh+var_80]
0x1401cee8c  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1401cee90  call    McTemplateK0qqqqhhx_EtwWriteTransfer
0x1401cee95  mov     ebx, [rbp+3Fh+var_8C]
0x1401cee98  xor     r8d, r8d
0x1401cee9b  jmp     loc_1400B276D
0x1401ceea0  or      eax, 0FFFFFFFFh
0x1401ceea3  mov     [rsp+0E0h+var_A8], r13
0x1401ceea8  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401ceeaf  mov     word ptr [rsp+0E0h+var_B0], r12w
0x1401ceeb5  lea     rdx, TCP_GLOBAL_PORT_RESERVATION_V1
0x1401ceebc  mov     word ptr [rsp+0E0h+var_B8], si
0x1401ceec1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401ceec8  mov     r9d, eax
0x1401ceecb  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1401ceecf  call    McTemplateK0qqhhx_EtwWriteTransfer
0x1401ceed4  nop
0x1401ceed5  jmp     loc_1400B265C
```
