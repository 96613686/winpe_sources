# AcquirePortReservationWithFlags

- ea: `0x14005c93c`
- end: `0x14005cc81`
- name: `AcquirePortReservationWithFlags`
- size: `837`
- prototype: `__int64 __usercall@<rax>(PERESOURCE Resource@<rcx>, PEPROCESS Process, __int64, __int16)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005b8a0`
- `0x14005bf60`
- `0x140159960`
- `0x140159ff0`
- `0x14015a500`

## callees

- `0x14005bd10`
- `0x14005c93c`
- `0x14005cc88`
- `0x14005e360`
- `0x14005ec78`
- `0x14014f600`
- `0x14015a7c0`
- `0x14015a860`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x14005cc5d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14005cc5d`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005cbd1`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005cbd1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ca55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005cb84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ca55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005cb84`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca49`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cb78`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca49`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005cb78`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ca0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005cb4e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ca0d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005cb4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c9fc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005cb3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c9fc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005cb3d`
- `ntoskrnl!PsGetProcessId` at `0x14005cbe3`
- `ntoskrnl!PsGetProcessId` at `0x14005cc6f`
- `ntoskrnl!PsGetProcessId` at `0x14005cbe3`
- `ntoskrnl!PsGetProcessId` at `0x14005cc6f`

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
      if ( SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
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
  if ( LOBYTE(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) && v12 < 0 && !v11 )
    TraceVailGuestPortFailure(
      (_DWORD)Process,
      Resource[1].SystemResourcesList.Flink,
      Exclusion,
      (unsigned __int16)v9,
      v12,
      1);
  if ( SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
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
      (unsigned int)&TCP_GLOBAL_PORT_RESERVATION_V1,
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER,
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
0x14005c93c  push    rbp
0x14005c93e  push    rbx
0x14005c93f  push    rsi
0x14005c940  push    rdi
0x14005c941  push    r12
0x14005c943  push    r13
0x14005c945  push    r14
0x14005c947  push    r15
0x14005c949  lea     rbp, [rsp-7]
0x14005c94e  sub     rsp, 0A8h
0x14005c955  mov     rax, cs:__security_cookie
0x14005c95c  xor     rax, rsp
0x14005c95f  mov     [rbp+3Fh+var_50], rax
0x14005c963  movzx   esi, word ptr [rdx]
0x14005c966  or      r13, 0FFFFFFFFFFFFFFFFh
0x14005c96a  mov     rax, [rbp+3Fh+arg_28]
0x14005c96e  mov     r15, rcx
0x14005c971  mov     r14, [rbp+3Fh+Process]
0x14005c975  movzx   r12d, r8w
0x14005c979  xor     r8d, r8d
0x14005c97c  ror     si, 8
0x14005c980  mov     [rbp+3Fh+var_68], rdx
0x14005c984  mov     [rbp+3Fh+var_70], r9
0x14005c988  mov     [rbp+3Fh+var_78], rax
0x14005c98c  lea     edx, [r8+1]
0x14005c990  mov     [rbp+3Fh+var_88], r8
0x14005c994  test    r12w, r12w
0x14005c998  jnz     short loc_14005C9DF
0x14005c99a  mov     dil, r8b
0x14005c99d  mov     ebx, 0C000000Dh
0x14005c9a2  cmp     byte ptr cs:WPP_MAIN_CB.Queue+8, r8b
0x14005c9a9  jnz     loc_14005CC1C
0x14005c9af  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r8b
0x14005c9b6  jl      loc_14005CC51
0x14005c9bc  mov     eax, ebx
0x14005c9be  mov     rcx, [rbp+3Fh+var_50]
0x14005c9c2  xor     rcx, rsp; StackCookie
0x14005c9c5  call    __security_check_cookie
0x14005c9ca  add     rsp, 0A8h
0x14005c9d1  pop     r15
0x14005c9d3  pop     r14
0x14005c9d5  pop     r13
0x14005c9d7  pop     r12
0x14005c9d9  pop     rdi
0x14005c9da  pop     rsi
0x14005c9db  pop     rbx
0x14005c9dc  pop     rbp
0x14005c9dd  retn
0x14005c9df  movzx   eax, si
0x14005c9e2  add     eax, r12d
0x14005c9e5  cmp     eax, 10000h
0x14005c9ea  ja      short loc_14005C99A
0x14005c9ec  test    si, si
0x14005c9ef  mov     [rbp+3Fh+var_8C], edx
0x14005c9f2  movzx   r13d, si
0x14005c9f6  mov     ebx, edx
0x14005c9f8  setz    dil
0x14005c9fc  call    cs:__imp_KeEnterCriticalRegion
0x14005ca03  nop     dword ptr [rax+rax+00h]
0x14005ca08  mov     dl, 1; Wait
0x14005ca0a  mov     rcx, r15; Resource
0x14005ca0d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005ca14  nop     dword ptr [rax+rax+00h]
0x14005ca19  mov     rax, [rbp+3Fh+var_78]
0x14005ca1d  mov     r9d, r12d
0x14005ca20  movzx   edx, [rbp+3Fh+arg_30]
0x14005ca24  mov     rcx, r15
0x14005ca27  mov     [rsp+0E0h+var_B0], rax
0x14005ca2c  mov     rax, [rbp+3Fh+var_70]
0x14005ca30  movzx   r8d, si
0x14005ca34  mov     [rsp+0E0h+var_B8], r14
0x14005ca39  mov     [rsp+0E0h+var_C0], rax
0x14005ca3e  call    CreateExclusion
0x14005ca43  mov     rcx, r15; Resource
0x14005ca46  movzx   esi, ax
0x14005ca49  call    cs:__imp_ExReleaseResourceLite
0x14005ca50  nop     dword ptr [rax+rax+00h]
0x14005ca55  call    cs:__imp_KeLeaveCriticalRegion
0x14005ca5c  nop     dword ptr [rax+rax+00h]
0x14005ca61  xor     r8d, r8d
0x14005ca64  test    si, si
0x14005ca67  jz      loc_14005CBB1
0x14005ca6d  cmp     cs:PortTrackerEnabled, r8b
0x14005ca74  jz      loc_14005CB93
0x14005ca7a  lea     eax, [r12-1]
0x14005ca7f  mov     [rbp+3Fh+var_90], r8w
0x14005ca84  add     ax, si
0x14005ca87  mov     [rbp+3Fh+var_60], si
0x14005ca8b  mov     [rbp+3Fh+var_5E], ax
0x14005ca8f  lea     r8, [rbp+3Fh+var_90]
0x14005ca93  mov     eax, [r15+68h]
0x14005ca97  lea     rdx, [rbp+3Fh+var_88]
0x14005ca9b  mov     [rbp+3Fh+var_5C], eax
0x14005ca9e  lea     rcx, [rbp+3Fh+var_60]
0x14005caa2  mov     al, byte ptr [rbp+3Fh+arg_30]
0x14005caa5  and     al, 10h
0x14005caa7  neg     al
0x14005caa9  sbb     eax, eax
0x14005caab  add     eax, 2
0x14005caae  mov     [rbp+3Fh+var_58], eax
0x14005cab1  call    PtClientReservePortRange
0x14005cab6  xor     r8d, r8d
0x14005cab9  mov     [rbp+3Fh+var_80], eax
0x14005cabc  test    eax, eax
0x14005cabe  jz      short loc_14005CB3D
0x14005cac0  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r8b
0x14005cac7  jl      loc_14005CBC5
0x14005cacd  mov     rax, [rbp+3Fh+var_78]
0x14005cad1  lea     rcx, [r15+88h]
0x14005cad8  mov     [rbp+3Fh+var_88], r8
0x14005cadc  mov     rax, [rax]
0x14005cadf  mov     rdx, [rcx]
0x14005cae2  test    rdx, rdx
0x14005cae5  jz      short loc_14005CB12
0x14005cae7  cmp     eax, [rdx+0Ch]
0x14005caea  jnz     loc_14005CBF7
0x14005caf0  test    r14, r14
0x14005caf3  jnz     loc_14005CBFF
0x14005caf9  mov     rax, [rdx]
0x14005cafc  mov     [rcx], rax
0x14005caff  mov     rcx, r15
0x14005cb02  mov     rax, [rdx+20h]
0x14005cb06  mov     [rbp+3Fh+var_88], rax
0x14005cb0a  call    DeleteExclusion
0x14005cb0f  xor     r8d, r8d
0x14005cb12  test    r13w, r13w
0x14005cb16  jnz     loc_14005CC15
0x14005cb1c  cmp     [rbp+3Fh+var_90], r8w
0x14005cb21  jz      loc_14005CC0E
0x14005cb27  cmp     ebx, 3
0x14005cb2a  jz      loc_14005CC0E
0x14005cb30  inc     ebx
0x14005cb32  mov     esi, r8d
0x14005cb35  mov     [rbp+3Fh+var_8C], ebx
0x14005cb38  jmp     loc_14005C9FC
0x14005cb3d  call    cs:__imp_KeEnterCriticalRegion
0x14005cb44  nop     dword ptr [rax+rax+00h]
0x14005cb49  mov     dl, 1; Wait
0x14005cb4b  mov     rcx, r15; Resource
0x14005cb4e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005cb55  nop     dword ptr [rax+rax+00h]
0x14005cb5a  mov     rax, [rbp+3Fh+var_78]
0x14005cb5e  mov     rcx, [r15+88h]
0x14005cb65  mov     rdx, [rax]
0x14005cb68  call    FindExclusion
0x14005cb6d  mov     rcx, [rbp+3Fh+var_88]
0x14005cb71  mov     [rax+20h], rcx
0x14005cb75  mov     rcx, r15; Resource
0x14005cb78  call    cs:__imp_ExReleaseResourceLite
0x14005cb7f  nop     dword ptr [rax+rax+00h]
0x14005cb84  call    cs:__imp_KeLeaveCriticalRegion
0x14005cb8b  nop     dword ptr [rax+rax+00h]
0x14005cb90  xor     r8d, r8d
0x14005cb93  mov     rcx, [rbp+3Fh+var_68]
0x14005cb97  movzx   eax, si
0x14005cb9a  ror     ax, 8
0x14005cb9e  mov     ebx, r8d
0x14005cba1  mov     [rcx], ax
0x14005cba4  or      r13, 0FFFFFFFFFFFFFFFFh
0x14005cba8  lea     edx, [r13+2]
0x14005cbac  jmp     loc_14005C9A2
0x14005cbb1  neg     r13w
0x14005cbb5  mov     ebx, 0C0000209h
0x14005cbba  sbb     eax, eax
0x14005cbbc  and     eax, 0FFFFFE3Ah
0x14005cbc1  add     ebx, eax
0x14005cbc3  jmp     short loc_14005CBA4
0x14005cbc5  test    r14, r14
0x14005cbc8  jz      loc_1401C50C6
0x14005cbce  mov     rcx, r14
0x14005cbd1  call    cs:__imp_PsGetProcessSequenceNumber
0x14005cbd8  nop     dword ptr [rax+rax+00h]
0x14005cbdd  mov     rcx, r14; Process
0x14005cbe0  mov     rbx, rax
0x14005cbe3  call    cs:__imp_PsGetProcessId
0x14005cbea  nop     dword ptr [rax+rax+00h]
0x14005cbef  mov     r9, rax
0x14005cbf2  jmp     loc_1401C50CE
0x14005cbf7  mov     rcx, rdx
0x14005cbfa  jmp     loc_14005CADF
0x14005cbff  cmp     r14, [rdx+28h]
0x14005cc03  jnz     loc_14005CB12
0x14005cc09  jmp     loc_14005CAF9
0x14005cc0e  mov     ebx, 0C0000209h
0x14005cc13  jmp     short loc_14005CBA4
0x14005cc15  mov     ebx, 0C0000043h
0x14005cc1a  jmp     short loc_14005CBA4
0x14005cc1c  test    ebx, ebx
0x14005cc1e  jns     loc_14005C9AF
0x14005cc24  test    dil, dil
0x14005cc27  jnz     loc_14005C9AF
0x14005cc2d  mov     byte ptr [rsp+0E0h+var_B8], dl
0x14005cc31  movzx   r9d, r12w
0x14005cc35  mov     edx, [r15+68h]
0x14005cc39  movzx   r8d, si
0x14005cc3d  mov     rcx, r14
0x14005cc40  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14005cc44  call    TraceVailGuestPortFailure
0x14005cc49  xor     r8d, r8d
0x14005cc4c  jmp     loc_14005C9AF
0x14005cc51  test    r14, r14
0x14005cc54  jz      loc_1401C5104
0x14005cc5a  mov     rcx, r14
0x14005cc5d  call    cs:__imp_PsGetProcessStartKey
0x14005cc64  nop     dword ptr [rax+rax+00h]
0x14005cc69  mov     rcx, r14; Process
0x14005cc6c  mov     r13, rax
0x14005cc6f  call    cs:__imp_PsGetProcessId
0x14005cc76  nop     dword ptr [rax+rax+00h]
0x14005cc7b  nop
0x14005cc7c  jmp     loc_1401C5107
0x1401c50c6  or      r9d, 0FFFFFFFFh
0x1401c50ca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1401c50ce  mov     eax, [r15+68h]
0x1401c50d2  mov     [rsp+0E0h+var_98], rbx
0x1401c50d7  mov     [rsp+0E0h+var_A0], r12w
0x1401c50dd  mov     word ptr [rsp+0E0h+var_A8], si
0x1401c50e2  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1401c50e6  mov     eax, [rbp+3Fh+var_58]
0x1401c50e9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1401c50ed  mov     eax, [rbp+3Fh+var_80]
0x1401c50f0  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1401c50f4  call    McTemplateK0qqqqhhx_EtwWriteTransfer
0x1401c50f9  mov     ebx, [rbp+3Fh+var_8C]
0x1401c50fc  xor     r8d, r8d
0x1401c50ff  jmp     loc_14005CACD
0x1401c5104  or      eax, 0FFFFFFFFh
0x1401c5107  mov     [rsp+0E0h+var_A8], r13
0x1401c510c  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401c5113  mov     word ptr [rsp+0E0h+var_B0], r12w
0x1401c5119  lea     rdx, TCP_GLOBAL_PORT_RESERVATION_V1
0x1401c5120  mov     word ptr [rsp+0E0h+var_B8], si
0x1401c5125  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c512c  mov     r9d, eax
0x1401c512f  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1401c5133  call    McTemplateK0qqhhx_EtwWriteTransfer
0x1401c5138  nop
0x1401c5139  jmp     loc_14005C9BC
```
