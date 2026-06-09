# AcquirePortReservationWithFlags

- ea: `0x14005c69c`
- end: `0x14005c9e1`
- name: `AcquirePortReservationWithFlags`
- size: `837`
- prototype: `__int64 __usercall@<rax>(PERESOURCE Resource@<rcx>, PEPROCESS Process, __int64, __int16)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14005b600`
- `0x14005bcc0`
- `0x140159820`
- `0x140159eb0`
- `0x14015a3c0`

## callees

- `0x14005ba70`
- `0x14005c69c`
- `0x14005c9e8`
- `0x14005e0c0`
- `0x14005e9d8`
- `0x14014f4c0`
- `0x14015a680`
- `0x14015a720`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!PsGetProcessStartKey` at `0x14005c9bd`
- `ntoskrnl!PsGetProcessStartKey` at `0x14005c9bd`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c931`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c931`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c7b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c8e4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c7b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c8e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c7a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c8d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c7a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c8d8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c76d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c8ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c76d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c8ae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c75c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c89d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c75c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c89d`
- `ntoskrnl!PsGetProcessId` at `0x14005c943`
- `ntoskrnl!PsGetProcessId` at `0x14005c9cf`
- `ntoskrnl!PsGetProcessId` at `0x14005c943`
- `ntoskrnl!PsGetProcessId` at `0x14005c9cf`

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
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) && v12 < 0 && !v11 )
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
0x14005c69c  push    rbp
0x14005c69e  push    rbx
0x14005c69f  push    rsi
0x14005c6a0  push    rdi
0x14005c6a1  push    r12
0x14005c6a3  push    r13
0x14005c6a5  push    r14
0x14005c6a7  push    r15
0x14005c6a9  lea     rbp, [rsp-7]
0x14005c6ae  sub     rsp, 0A8h
0x14005c6b5  mov     rax, cs:__security_cookie
0x14005c6bc  xor     rax, rsp
0x14005c6bf  mov     [rbp+3Fh+var_50], rax
0x14005c6c3  movzx   esi, word ptr [rdx]
0x14005c6c6  or      r13, 0FFFFFFFFFFFFFFFFh
0x14005c6ca  mov     rax, [rbp+3Fh+arg_28]
0x14005c6ce  mov     r15, rcx
0x14005c6d1  mov     r14, [rbp+3Fh+Process]
0x14005c6d5  movzx   r12d, r8w
0x14005c6d9  xor     r8d, r8d
0x14005c6dc  ror     si, 8
0x14005c6e0  mov     [rbp+3Fh+var_68], rdx
0x14005c6e4  mov     [rbp+3Fh+var_70], r9
0x14005c6e8  mov     [rbp+3Fh+var_78], rax
0x14005c6ec  lea     edx, [r8+1]
0x14005c6f0  mov     [rbp+3Fh+var_88], r8
0x14005c6f4  test    r12w, r12w
0x14005c6f8  jnz     short loc_14005C73F
0x14005c6fa  mov     dil, r8b
0x14005c6fd  mov     ebx, 0C000000Dh
0x14005c702  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, r8b
0x14005c709  jnz     loc_14005C97C
0x14005c70f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r8b
0x14005c716  jl      loc_14005C9B1
0x14005c71c  mov     eax, ebx
0x14005c71e  mov     rcx, [rbp+3Fh+var_50]
0x14005c722  xor     rcx, rsp; StackCookie
0x14005c725  call    __security_check_cookie
0x14005c72a  add     rsp, 0A8h
0x14005c731  pop     r15
0x14005c733  pop     r14
0x14005c735  pop     r13
0x14005c737  pop     r12
0x14005c739  pop     rdi
0x14005c73a  pop     rsi
0x14005c73b  pop     rbx
0x14005c73c  pop     rbp
0x14005c73d  retn
0x14005c73f  movzx   eax, si
0x14005c742  add     eax, r12d
0x14005c745  cmp     eax, 10000h
0x14005c74a  ja      short loc_14005C6FA
0x14005c74c  test    si, si
0x14005c74f  mov     [rbp+3Fh+var_8C], edx
0x14005c752  movzx   r13d, si
0x14005c756  mov     ebx, edx
0x14005c758  setz    dil
0x14005c75c  call    cs:__imp_KeEnterCriticalRegion
0x14005c763  nop     dword ptr [rax+rax+00h]
0x14005c768  mov     dl, 1; Wait
0x14005c76a  mov     rcx, r15; Resource
0x14005c76d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005c774  nop     dword ptr [rax+rax+00h]
0x14005c779  mov     rax, [rbp+3Fh+var_78]
0x14005c77d  mov     r9d, r12d
0x14005c780  movzx   edx, [rbp+3Fh+arg_30]
0x14005c784  mov     rcx, r15
0x14005c787  mov     [rsp+0E0h+var_B0], rax
0x14005c78c  mov     rax, [rbp+3Fh+var_70]
0x14005c790  movzx   r8d, si
0x14005c794  mov     [rsp+0E0h+var_B8], r14
0x14005c799  mov     [rsp+0E0h+var_C0], rax
0x14005c79e  call    CreateExclusion
0x14005c7a3  mov     rcx, r15; Resource
0x14005c7a6  movzx   esi, ax
0x14005c7a9  call    cs:__imp_ExReleaseResourceLite
0x14005c7b0  nop     dword ptr [rax+rax+00h]
0x14005c7b5  call    cs:__imp_KeLeaveCriticalRegion
0x14005c7bc  nop     dword ptr [rax+rax+00h]
0x14005c7c1  xor     r8d, r8d
0x14005c7c4  test    si, si
0x14005c7c7  jz      loc_14005C911
0x14005c7cd  cmp     cs:PortTrackerEnabled, r8b
0x14005c7d4  jz      loc_14005C8F3
0x14005c7da  lea     eax, [r12-1]
0x14005c7df  mov     [rbp+3Fh+var_90], r8w
0x14005c7e4  add     ax, si
0x14005c7e7  mov     [rbp+3Fh+var_60], si
0x14005c7eb  mov     [rbp+3Fh+var_5E], ax
0x14005c7ef  lea     r8, [rbp+3Fh+var_90]
0x14005c7f3  mov     eax, [r15+68h]
0x14005c7f7  lea     rdx, [rbp+3Fh+var_88]
0x14005c7fb  mov     [rbp+3Fh+var_5C], eax
0x14005c7fe  lea     rcx, [rbp+3Fh+var_60]
0x14005c802  mov     al, byte ptr [rbp+3Fh+arg_30]
0x14005c805  and     al, 10h
0x14005c807  neg     al
0x14005c809  sbb     eax, eax
0x14005c80b  add     eax, 2
0x14005c80e  mov     [rbp+3Fh+var_58], eax
0x14005c811  call    PtClientReservePortRange
0x14005c816  xor     r8d, r8d
0x14005c819  mov     [rbp+3Fh+var_80], eax
0x14005c81c  test    eax, eax
0x14005c81e  jz      short loc_14005C89D
0x14005c820  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r8b
0x14005c827  jl      loc_14005C925
0x14005c82d  mov     rax, [rbp+3Fh+var_78]
0x14005c831  lea     rcx, [r15+88h]
0x14005c838  mov     [rbp+3Fh+var_88], r8
0x14005c83c  mov     rax, [rax]
0x14005c83f  mov     rdx, [rcx]
0x14005c842  test    rdx, rdx
0x14005c845  jz      short loc_14005C872
0x14005c847  cmp     eax, [rdx+0Ch]
0x14005c84a  jnz     loc_14005C957
0x14005c850  test    r14, r14
0x14005c853  jnz     loc_14005C95F
0x14005c859  mov     rax, [rdx]
0x14005c85c  mov     [rcx], rax
0x14005c85f  mov     rcx, r15
0x14005c862  mov     rax, [rdx+20h]
0x14005c866  mov     [rbp+3Fh+var_88], rax
0x14005c86a  call    DeleteExclusion
0x14005c86f  xor     r8d, r8d
0x14005c872  test    r13w, r13w
0x14005c876  jnz     loc_14005C975
0x14005c87c  cmp     [rbp+3Fh+var_90], r8w
0x14005c881  jz      loc_14005C96E
0x14005c887  cmp     ebx, 3
0x14005c88a  jz      loc_14005C96E
0x14005c890  inc     ebx
0x14005c892  mov     esi, r8d
0x14005c895  mov     [rbp+3Fh+var_8C], ebx
0x14005c898  jmp     loc_14005C75C
0x14005c89d  call    cs:__imp_KeEnterCriticalRegion
0x14005c8a4  nop     dword ptr [rax+rax+00h]
0x14005c8a9  mov     dl, 1; Wait
0x14005c8ab  mov     rcx, r15; Resource
0x14005c8ae  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005c8b5  nop     dword ptr [rax+rax+00h]
0x14005c8ba  mov     rax, [rbp+3Fh+var_78]
0x14005c8be  mov     rcx, [r15+88h]
0x14005c8c5  mov     rdx, [rax]
0x14005c8c8  call    FindExclusion
0x14005c8cd  mov     rcx, [rbp+3Fh+var_88]
0x14005c8d1  mov     [rax+20h], rcx
0x14005c8d5  mov     rcx, r15; Resource
0x14005c8d8  call    cs:__imp_ExReleaseResourceLite
0x14005c8df  nop     dword ptr [rax+rax+00h]
0x14005c8e4  call    cs:__imp_KeLeaveCriticalRegion
0x14005c8eb  nop     dword ptr [rax+rax+00h]
0x14005c8f0  xor     r8d, r8d
0x14005c8f3  mov     rcx, [rbp+3Fh+var_68]
0x14005c8f7  movzx   eax, si
0x14005c8fa  ror     ax, 8
0x14005c8fe  mov     ebx, r8d
0x14005c901  mov     [rcx], ax
0x14005c904  or      r13, 0FFFFFFFFFFFFFFFFh
0x14005c908  lea     edx, [r13+2]
0x14005c90c  jmp     loc_14005C702
0x14005c911  neg     r13w
0x14005c915  mov     ebx, 0C0000209h
0x14005c91a  sbb     eax, eax
0x14005c91c  and     eax, 0FFFFFE3Ah
0x14005c921  add     ebx, eax
0x14005c923  jmp     short loc_14005C904
0x14005c925  test    r14, r14
0x14005c928  jz      loc_1401C4F86
0x14005c92e  mov     rcx, r14
0x14005c931  call    cs:__imp_PsGetProcessSequenceNumber
0x14005c938  nop     dword ptr [rax+rax+00h]
0x14005c93d  mov     rcx, r14; Process
0x14005c940  mov     rbx, rax
0x14005c943  call    cs:__imp_PsGetProcessId
0x14005c94a  nop     dword ptr [rax+rax+00h]
0x14005c94f  mov     r9, rax
0x14005c952  jmp     loc_1401C4F8E
0x14005c957  mov     rcx, rdx
0x14005c95a  jmp     loc_14005C83F
0x14005c95f  cmp     r14, [rdx+28h]
0x14005c963  jnz     loc_14005C872
0x14005c969  jmp     loc_14005C859
0x14005c96e  mov     ebx, 0C0000209h
0x14005c973  jmp     short loc_14005C904
0x14005c975  mov     ebx, 0C0000043h
0x14005c97a  jmp     short loc_14005C904
0x14005c97c  test    ebx, ebx
0x14005c97e  jns     loc_14005C70F
0x14005c984  test    dil, dil
0x14005c987  jnz     loc_14005C70F
0x14005c98d  mov     byte ptr [rsp+0E0h+var_B8], dl
0x14005c991  movzx   r9d, r12w
0x14005c995  mov     edx, [r15+68h]
0x14005c999  movzx   r8d, si
0x14005c99d  mov     rcx, r14
0x14005c9a0  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14005c9a4  call    TraceVailGuestPortFailure
0x14005c9a9  xor     r8d, r8d
0x14005c9ac  jmp     loc_14005C70F
0x14005c9b1  test    r14, r14
0x14005c9b4  jz      loc_1401C4FC4
0x14005c9ba  mov     rcx, r14
0x14005c9bd  call    cs:__imp_PsGetProcessStartKey
0x14005c9c4  nop     dword ptr [rax+rax+00h]
0x14005c9c9  mov     rcx, r14; Process
0x14005c9cc  mov     r13, rax
0x14005c9cf  call    cs:__imp_PsGetProcessId
0x14005c9d6  nop     dword ptr [rax+rax+00h]
0x14005c9db  nop
0x14005c9dc  jmp     loc_1401C4FC7
0x1401c4f86  or      r9d, 0FFFFFFFFh
0x1401c4f8a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1401c4f8e  mov     eax, [r15+68h]
0x1401c4f92  mov     [rsp+0E0h+var_98], rbx
0x1401c4f97  mov     [rsp+0E0h+var_A0], r12w
0x1401c4f9d  mov     word ptr [rsp+0E0h+var_A8], si
0x1401c4fa2  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1401c4fa6  mov     eax, [rbp+3Fh+var_58]
0x1401c4fa9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1401c4fad  mov     eax, [rbp+3Fh+var_80]
0x1401c4fb0  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1401c4fb4  call    McTemplateK0qqqqhhx_EtwWriteTransfer
0x1401c4fb9  mov     ebx, [rbp+3Fh+var_8C]
0x1401c4fbc  xor     r8d, r8d
0x1401c4fbf  jmp     loc_14005C82D
0x1401c4fc4  or      eax, 0FFFFFFFFh
0x1401c4fc7  mov     [rsp+0E0h+var_A8], r13
0x1401c4fcc  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401c4fd3  mov     word ptr [rsp+0E0h+var_B0], r12w
0x1401c4fd9  lea     rdx, TCP_GLOBAL_PORT_RESERVATION_V1
0x1401c4fe0  mov     word ptr [rsp+0E0h+var_B8], si
0x1401c4fe5  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c4fec  mov     r9d, eax
0x1401c4fef  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1401c4ff3  call    McTemplateK0qqhhx_EtwWriteTransfer
0x1401c4ff8  nop
0x1401c4ff9  jmp     loc_14005C71C
```
