# MpRegInitialize

- ea: `0x140092410`
- end: `0x1400928f3`
- name: `MpRegInitialize`
- size: `1251`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14008f314`

## callees

- `0x1400026c0`
- `0x1400051bc`
- `0x1400118d0`
- `0x140091e3c`
- `0x140092410`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140092473`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400924fb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140092473`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400924fb`
- `ntoskrnl!CmRegisterCallbackEx` at `0x140092870`
- `ntoskrnl!CmRegisterCallbackEx` at `0x140092870`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092462`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400924ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092804`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092824`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092462`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400924ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092804`
- `ntoskrnl!RtlInitUnicodeString` at `0x140092824`
- `ntoskrnl!KeInitializeEvent` at `0x1400925e9`
- `ntoskrnl!KeInitializeEvent` at `0x140092621`
- `ntoskrnl!KeInitializeEvent` at `0x1400925e9`
- `ntoskrnl!KeInitializeEvent` at `0x140092621`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140092672`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400926ac`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400926df`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009270f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140092743`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009277b`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400927b3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400927e3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140092672`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400926ac`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400926df`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009270f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140092743`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009277b`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400927b3`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400927e3`
- `FLTMGR!FltInitializePushLock` at `0x1400925b1`
- `FLTMGR!FltInitializePushLock` at `0x1400925b1`

## string_xrefs

- `0x1400927f6`: `LoadAppInit_DLLs`

## pseudocode

```c
__int64 MpRegInitialize()
{
  unsigned int v0; // ebx
  PVOID SystemRoutineAddress; // rdi
  PVOID v2; // rsi
  __int64 v3; // rdx
  unsigned __int64 *PoolWithTag; // rax
  char *v5; // rcx
  struct _KEVENT *v6; // rcx
  char *v7; // rcx
  _QWORD *v8; // rax
  NTSTATUS v9; // r8d
  int Size; // [rsp+20h] [rbp-58h]
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF

  v0 = 0;
  SystemRoutineAddress = 0;
  SystemRoutineName = 0;
  v2 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 4) == 0 )
    goto LABEL_12;
  RtlInitUnicodeString(&SystemRoutineName, L"CmCallbackGetKeyObjectIDEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( !SystemRoutineAddress )
  {
    v0 = -1073741822;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v3 = 10;
LABEL_6:
      Size = -1073741822;
LABEL_7:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        Size);
      return v0;
    }
    return v0;
  }
  RtlInitUnicodeString(&SystemRoutineName, L"CmCallbackReleaseKeyObjectIDEx");
  v2 = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( v2 )
  {
LABEL_12:
    PoolWithTag = (unsigned __int64 *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 1280, 1148342349);
    MpRegData = PoolWithTag;
    if ( PoolWithTag )
    {
      *(_DWORD *)PoolWithTag = 83941897;
      PoolWithTag[4] = (unsigned __int64)SystemRoutineAddress;
      PoolWithTag[5] = (unsigned __int64)v2;
      *((_DWORD *)PoolWithTag + 64) = 0;
      FltInitializePushLock(PoolWithTag + 1);
      v5 = (char *)MpRegData;
      *((_DWORD *)MpRegData + 74) = 1;
      *((_QWORD *)v5 + 38) = 0;
      *((_DWORD *)v5 + 78) = 0;
      KeInitializeEvent((PRKEVENT)(v5 + 320), SynchronizationEvent, 0);
      v6 = (struct _KEVENT *)MpRegData;
      *((_DWORD *)MpRegData + 48) = 1;
      v6[8].Header.WaitListHead.Flink = 0;
      LODWORD(v6[8].Header.WaitListHead.Blink) = 0;
      KeInitializeEvent(v6 + 9, SynchronizationEvent, 0);
      v7 = (char *)MpRegData;
      v8 = (char *)MpRegData + 352;
      *((_QWORD *)MpRegData + 45) = (char *)MpRegData + 352;
      *v8 = v8;
      *((_QWORD *)v7 + 36) = v7 + 280;
      *((_QWORD *)v7 + 35) = v7 + 280;
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v7 + 64), 0, 0, 0, 0x78u, 0x4E72504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 3, 0, 0, 0, 0x40u, 0x5872504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 4, 0, 0, 0, 0x50u, 0x5872504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 5, 0, 0, 0, 0x50u, 0x5872504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 6, 0, 0, 0, 0x38u, 0x5872504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 7, 0, 0, 0, 0x28u, 0x5372504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 8, 0, 0, 0, 0x230u, 0x4B72504Du, 0);
      ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpRegData + 9, 0, 0, 0, 0x40u, 0x5872504Du, 0);
      RtlInitUnicodeString((PUNICODE_STRING)((char *)MpRegData + 264), L"LoadAppInit_DLLs");
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"328010");
      if ( (*(_DWORD *)(MpData + 864) & 8) == 0 )
      {
        v9 = CmRegisterCallbackEx(
               MpRegHardeningCallback,
               &DestinationString,
               *(PVOID *)(MpData + 8),
               0,
               (PLARGE_INTEGER)MpRegData + 31,
               0);
        if ( v9 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            v9);
        }
      }
      MpRegCreateHardeningList();
    }
    else
    {
      v0 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v3 = 12;
        Size = -1073741670;
        goto LABEL_7;
      }
    }
    return v0;
  }
  v0 = -1073741822;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v3 = 11;
    goto LABEL_6;
  }
  return v0;
}

```

## disassembly

```asm
0x140092410  mov     r11, rsp
0x140092413  mov     [r11+8], rbx
0x140092417  mov     [r11+10h], rbp
0x14009241b  mov     [r11+18h], rsi
0x14009241f  push    rdi
0x140092420  sub     rsp, 70h
0x140092424  mov     rax, cs:__security_cookie
0x14009242b  xor     rax, rsp
0x14009242e  mov     [rsp+78h+var_18], rax
0x140092433  mov     rax, cs:MpData
0x14009243a  xor     ebx, ebx
0x14009243c  xorps   xmm0, xmm0
0x14009243f  mov     edi, ebx
0x140092441  movups  xmmword ptr [rsp+78h+SystemRoutineName.Length], xmm0
0x140092446  mov     esi, ebx
0x140092448  mov     ecx, [rax+360h]
0x14009244e  test    cl, 4
0x140092451  jz      loc_14009253E
0x140092457  lea     rdx, aCmcallbackgetk; "CmCallbackGetKeyObjectIDEx"
0x14009245e  lea     rcx, [r11-38h]; DestinationString
0x140092462  call    cs:__imp_RtlInitUnicodeString
0x140092469  nop     dword ptr [rax+rax+00h]
0x14009246e  lea     rcx, [rsp+78h+SystemRoutineName]; SystemRoutineName
0x140092473  call    cs:__imp_MmGetSystemRoutineAddress
0x14009247a  nop     dword ptr [rax+rax+00h]
0x14009247f  mov     rdi, rax
0x140092482  test    rax, rax
0x140092485  jnz     short loc_1400924DE
0x140092487  mov     ebx, 0C0000002h
0x14009248c  mov     rcx, cs:WPP_GLOBAL_Control
0x140092493  lea     rax, WPP_GLOBAL_Control
0x14009249a  cmp     rcx, rax
0x14009249d  jz      loc_1400928CD
0x1400924a3  mov     eax, [rcx+2Ch]
0x1400924a6  test    al, 1
0x1400924a8  jz      loc_1400928CD
0x1400924ae  lea     edx, [rsi+0Ah]
0x1400924b1  mov     dword ptr [rsp+78h+Size], 0C0000002h
0x1400924b9  mov     r9, gs:188h
0x1400924c2  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400924c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400924d0  mov     rcx, [rcx+18h]
0x1400924d4  call    WPP_SF_qD
0x1400924d9  jmp     loc_1400928CD
0x1400924de  lea     rdx, aCmcallbackrele; "CmCallbackReleaseKeyObjectIDEx"
0x1400924e5  lea     rcx, [rsp+78h+SystemRoutineName]; DestinationString
0x1400924ea  call    cs:__imp_RtlInitUnicodeString
0x1400924f1  nop     dword ptr [rax+rax+00h]
0x1400924f6  lea     rcx, [rsp+78h+SystemRoutineName]; SystemRoutineName
0x1400924fb  call    cs:__imp_MmGetSystemRoutineAddress
0x140092502  nop     dword ptr [rax+rax+00h]
0x140092507  mov     rsi, rax
0x14009250a  test    rax, rax
0x14009250d  jnz     short loc_14009253E
0x14009250f  mov     ebx, 0C0000002h
0x140092514  mov     rcx, cs:WPP_GLOBAL_Control
0x14009251b  lea     rax, WPP_GLOBAL_Control
0x140092522  cmp     rcx, rax
0x140092525  jz      loc_1400928CD
0x14009252b  mov     eax, [rcx+2Ch]
0x14009252e  test    al, 1
0x140092530  jz      loc_1400928CD
0x140092536  lea     edx, [rsi+0Bh]
0x140092539  jmp     loc_1400924B1
0x14009253e  mov     ecx, cs:ExDefaultNonPagedPoolType
0x140092544  mov     edx, 500h
0x140092549  mov     r8d, 4472504Dh
0x14009254f  call    MpAllocatePoolWithTag
0x140092554  mov     cs:MpRegData, rax
0x14009255b  test    rax, rax
0x14009255e  jnz     short loc_140092599
0x140092560  mov     ebx, 0C000009Ah
0x140092565  mov     rcx, cs:WPP_GLOBAL_Control
0x14009256c  lea     rax, WPP_GLOBAL_Control
0x140092573  cmp     rcx, rax
0x140092576  jz      loc_1400928CD
0x14009257c  mov     eax, [rcx+2Ch]
0x14009257f  test    al, 1
0x140092581  jz      loc_1400928CD
0x140092587  mov     edx, 0Ch
0x14009258c  mov     dword ptr [rsp+78h+Size], 0C000009Ah
0x140092594  jmp     loc_1400924B9
0x140092599  mov     dword ptr [rax], 500DA09h
0x14009259f  lea     rcx, [rax+8]; PushLock
0x1400925a3  mov     [rax+20h], rdi
0x1400925a7  mov     [rax+28h], rsi
0x1400925ab  mov     [rax+100h], ebx
0x1400925b1  call    cs:__imp_FltInitializePushLock
0x1400925b8  nop     dword ptr [rax+rax+00h]
0x1400925bd  mov     rcx, cs:MpRegData
0x1400925c4  xor     r8d, r8d; State
0x1400925c7  mov     dword ptr [rcx+128h], 1
0x1400925d1  lea     edx, [r8+1]; Type
0x1400925d5  mov     [rcx+130h], rbx
0x1400925dc  mov     [rcx+138h], ebx
0x1400925e2  add     rcx, 140h; Event
0x1400925e9  call    cs:__imp_KeInitializeEvent
0x1400925f0  nop     dword ptr [rax+rax+00h]
0x1400925f5  mov     rcx, cs:MpRegData
0x1400925fc  xor     r8d, r8d; State
0x1400925ff  mov     dword ptr [rcx+0C0h], 1
0x140092609  lea     edx, [r8+1]; Type
0x14009260d  mov     [rcx+0C8h], rbx
0x140092614  mov     [rcx+0D0h], ebx
0x14009261a  add     rcx, 0D8h; Event
0x140092621  call    cs:__imp_KeInitializeEvent
0x140092628  nop     dword ptr [rax+rax+00h]
0x14009262d  mov     rcx, cs:MpRegData
0x140092634  xor     r9d, r9d; Flags
0x140092637  mov     [rsp+78h+Depth], bx; Depth
0x14009263c  xor     r8d, r8d; Free
0x14009263f  mov     [rsp+78h+Tag], 4E72504Dh; Tag
0x140092647  xor     edx, edx; Allocate
0x140092649  mov     [rsp+78h+Size], 78h ; 'x'; Size
0x140092652  lea     rax, [rcx+160h]
0x140092659  mov     [rax+8], rax
0x14009265d  mov     [rax], rax
0x140092660  lea     rax, [rcx+118h]
0x140092667  add     rcx, 40h ; '@'; Lookaside
0x14009266b  mov     [rax+8], rax
0x14009266f  mov     [rax], rax
0x140092672  call    cs:__imp_ExInitializePagedLookasideList
0x140092679  nop     dword ptr [rax+rax+00h]
0x14009267e  mov     rcx, cs:MpRegData
0x140092685  mov     ebp, 5872504Dh
0x14009268a  mov     [rsp+78h+Depth], bx; Depth
0x14009268f  mov     esi, 40h ; '@'
0x140092694  add     rcx, 180h; Lookaside
0x14009269b  mov     [rsp+78h+Tag], ebp; Tag
0x14009269f  xor     r9d, r9d; Flags
0x1400926a2  mov     [rsp+78h+Size], rsi; Size
0x1400926a7  xor     r8d, r8d; Free
0x1400926aa  xor     edx, edx; Allocate
0x1400926ac  call    cs:__imp_ExInitializePagedLookasideList
0x1400926b3  nop     dword ptr [rax+rax+00h]
0x1400926b8  mov     rcx, cs:MpRegData
0x1400926bf  lea     edi, [rsi+10h]
0x1400926c2  mov     [rsp+78h+Depth], bx; Depth
0x1400926c7  add     rcx, 200h; Lookaside
0x1400926ce  mov     [rsp+78h+Tag], ebp; Tag
0x1400926d2  xor     r9d, r9d; Flags
0x1400926d5  xor     r8d, r8d; Free
0x1400926d8  mov     [rsp+78h+Size], rdi; Size
0x1400926dd  xor     edx, edx; Allocate
0x1400926df  call    cs:__imp_ExInitializePagedLookasideList
0x1400926e6  nop     dword ptr [rax+rax+00h]
0x1400926eb  mov     rcx, cs:MpRegData
0x1400926f2  xor     r9d, r9d; Flags
0x1400926f5  mov     [rsp+78h+Depth], bx; Depth
0x1400926fa  add     rcx, 280h; Lookaside
0x140092701  mov     [rsp+78h+Tag], ebp; Tag
0x140092705  xor     r8d, r8d; Free
0x140092708  xor     edx, edx; Allocate
0x14009270a  mov     [rsp+78h+Size], rdi; Size
0x14009270f  call    cs:__imp_ExInitializePagedLookasideList
0x140092716  nop     dword ptr [rax+rax+00h]
0x14009271b  mov     rcx, cs:MpRegData
0x140092722  xor     r9d, r9d; Flags
0x140092725  mov     [rsp+78h+Depth], bx; Depth
0x14009272a  add     rcx, 300h; Lookaside
0x140092731  mov     [rsp+78h+Tag], ebp; Tag
0x140092735  xor     r8d, r8d; Free
0x140092738  xor     edx, edx; Allocate
0x14009273a  mov     [rsp+78h+Size], 38h ; '8'; Size
0x140092743  call    cs:__imp_ExInitializePagedLookasideList
0x14009274a  nop     dword ptr [rax+rax+00h]
0x14009274f  mov     rcx, cs:MpRegData
0x140092756  mov     [rsp+78h+Depth], bx; Depth
0x14009275b  add     rcx, 380h; Lookaside
0x140092762  mov     [rsp+78h+Tag], 5372504Dh; Tag
0x14009276a  mov     [rsp+78h+Size], 28h ; '('; Size
0x140092773  xor     r9d, r9d; Flags
0x140092776  xor     r8d, r8d; Free
0x140092779  xor     edx, edx; Allocate
0x14009277b  call    cs:__imp_ExInitializePagedLookasideList
0x140092782  nop     dword ptr [rax+rax+00h]
0x140092787  mov     rcx, cs:MpRegData
0x14009278e  xor     r9d, r9d; Flags
0x140092791  mov     [rsp+78h+Depth], bx; Depth
0x140092796  add     rcx, 400h; Lookaside
0x14009279d  mov     [rsp+78h+Tag], 4B72504Dh; Tag
0x1400927a5  xor     r8d, r8d; Free
0x1400927a8  xor     edx, edx; Allocate
0x1400927aa  mov     [rsp+78h+Size], 230h; Size
0x1400927b3  call    cs:__imp_ExInitializePagedLookasideList
0x1400927ba  nop     dword ptr [rax+rax+00h]
0x1400927bf  mov     rcx, cs:MpRegData
0x1400927c6  xor     r9d, r9d; Flags
0x1400927c9  mov     [rsp+78h+Depth], bx; Depth
0x1400927ce  add     rcx, 480h; Lookaside
0x1400927d5  mov     [rsp+78h+Tag], ebp; Tag
0x1400927d9  xor     r8d, r8d; Free
0x1400927dc  xor     edx, edx; Allocate
0x1400927de  mov     [rsp+78h+Size], rsi; Size
0x1400927e3  call    cs:__imp_ExInitializePagedLookasideList
0x1400927ea  nop     dword ptr [rax+rax+00h]
0x1400927ef  mov     rcx, cs:MpRegData
0x1400927f6  lea     rdx, aLoadappinitDll; "LoadAppInit_DLLs"
0x1400927fd  add     rcx, 108h; DestinationString
0x140092804  call    cs:__imp_RtlInitUnicodeString
0x14009280b  nop     dword ptr [rax+rax+00h]
0x140092810  xorps   xmm0, xmm0
0x140092813  lea     rdx, a328010; "328010"
0x14009281a  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14009281f  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140092824  call    cs:__imp_RtlInitUnicodeString
0x14009282b  nop     dword ptr [rax+rax+00h]
0x140092830  mov     r8, cs:MpData
0x140092837  mov     eax, [r8+360h]
0x14009283e  test    al, 8
0x140092840  jnz     loc_1400928C8
0x140092846  mov     rax, cs:MpRegData
0x14009284d  lea     rdx, [rsp+78h+DestinationString]; Altitude
0x140092852  mov     r8, [r8+8]; Driver
0x140092856  lea     rcx, MpRegHardeningCallback; Function
0x14009285d  add     rax, 0F8h
0x140092863  mov     qword ptr [rsp+78h+Tag], rbx; Reserved
0x140092868  xor     r9d, r9d; Context
0x14009286b  mov     [rsp+78h+Size], rax; Cookie
0x140092870  call    cs:__imp_CmRegisterCallbackEx
0x140092877  nop     dword ptr [rax+rax+00h]
0x14009287c  mov     r8d, eax
0x14009287f  test    eax, eax
0x140092881  jns     short loc_1400928C8
0x140092883  mov     rcx, cs:WPP_GLOBAL_Control
0x14009288a  lea     rax, WPP_GLOBAL_Control
0x140092891  cmp     rcx, rax
0x140092894  jz      short loc_1400928C8
0x140092896  mov     eax, [rcx+2Ch]
0x140092899  test    al, 1
0x14009289b  jz      short loc_1400928C8
0x14009289d  lfence
0x1400928a0  mov     r9, gs:188h
0x1400928a9  lea     edx, [rsi-33h]
0x1400928ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400928b3  mov     dword ptr [rsp+78h+Size], r8d
0x1400928b8  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x1400928bf  mov     rcx, [rcx+18h]
0x1400928c3  call    WPP_SF_qD
0x1400928c8  call    MpRegCreateHardeningList
0x1400928cd  mov     eax, ebx
0x1400928cf  mov     rcx, [rsp+78h+var_18]
0x1400928d4  xor     rcx, rsp; StackCookie
0x1400928d7  call    __security_check_cookie
0x1400928dc  lea     r11, [rsp+78h+var_8]
0x1400928e1  mov     rbx, [r11+10h]
0x1400928e5  mov     rbp, [r11+18h]
0x1400928e9  mov     rsi, [r11+20h]
0x1400928ed  mov     rsp, r11
0x1400928f0  pop     rdi
0x1400928f1  retn
```
