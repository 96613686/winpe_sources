# IPxlatCreateInstance_old

- ea: `0x140016760`
- end: `0x1400169dd`
- name: `IPxlatCreateInstance_old`
- size: `637`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034d80`

## callees

- `0x14000e4b0`
- `0x140016238`
- `0x140016760`
- `0x140016e28`
- `0x140016f08`
- `0x1400177b8`
- `0x14001f680`
- `0x14002e53c`
- `0x14002e57c`
- `0x140034b28`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016937`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016937`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400168fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400168fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400168de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400168de`
- `ntoskrnl!ExAllocatePool2` at `0x140016827`
- `ntoskrnl!ExAllocatePool2` at `0x140016827`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400168cd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400169a4`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400168cd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400169a4`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400167e3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400167e3`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x1400167c3`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x1400167c3`

## pseudocode

```c
__int64 __fastcall IPxlatCreateInstance_old(NET_LUID *InterfaceLuid, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  NTSTATUS v7; // edi
  __int64 Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rdx
  _QWORD *v14; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-58h] BYREF
  ULONG InterfaceIndex; // [rsp+D0h] [rbp+18h] BYREF

  InterfaceIndex = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_i(InterfaceLuid, 15, a3, InterfaceLuid->Value);
  if ( !IPxlatInstancePropertiesValid((const UCHAR *)a2) )
  {
    v7 = -1073741811;
    goto LABEL_23;
  }
  v7 = ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
  if ( v7 >= 0 )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400278F0);
    if ( IPxlatGlobalState )
    {
      if ( IPxlatFindInstance(InterfaceLuid->Value) )
      {
        v7 = -1073741269;
      }
      else
      {
        Pool2 = ExAllocatePool2(64, 144, 1852394584);
        v11 = (_QWORD *)Pool2;
        if ( Pool2 )
        {
          *(NET_LUID *)(Pool2 + 16) = (NET_LUID)InterfaceLuid->Value;
          *(_DWORD *)(Pool2 + 24) = InterfaceIndex;
          memmove((void *)(Pool2 + 28), (const void *)(a2 + 8), (unsigned __int64)*(unsigned __int8 *)(a2 + 24) >> 3);
          LOBYTE(v12) = *(_BYTE *)(a2 + 24);
          IN6_SET_V4ADDR_IN_V4EMBV6((char *)v11 + 28, v12, a2);
          LOBYTE(v13) = 1;
          *((_OWORD *)v11 + 5) = *(_OWORD *)a2;
          *((_OWORD *)v11 + 6) = *(_OWORD *)(a2 + 16);
          *(_OWORD *)((char *)v11 + 108) = *(_OWORD *)(a2 + 28);
          v7 = IPxlatConfigureFiltersForInstance(v11, v13);
          if ( v7 < 0 )
          {
            ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
            ExFreePoolWithTag(v11, 0);
            goto LABEL_23;
          }
          KeAcquireInStackQueuedSpinLock(&qword_140027958, &LockHandle);
          v14 = (_QWORD *)qword_1400278E8;
          if ( *(PVOID **)qword_1400278E8 != &qword_1400278E0 )
            __fastfail(3u);
          *v11 = &qword_1400278E0;
          v11[1] = v14;
          *v14 = v11;
          qword_1400278E8 = (__int64)v11;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
            McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNAT_IPXLAT_INSTANCE_CREATION,
              (_DWORD)v11 + 106,
              v11[2],
              *((_DWORD *)v11 + 21),
              *((_DWORD *)v11 + 20),
              (__int64)v11 + 28,
              (__int64)v11 + 106,
              *((_BYTE *)v11 + 122),
              (__int64)(v11 + 11),
              *((_BYTE *)v11 + 104));
        }
        else
        {
          if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
            McTemplateK0z_EtwWriteTransfer(
              &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v9,
              v10,
              L"IPxlat instance buffer allocation failed");
          v7 = -1073741670;
        }
      }
    }
    else
    {
      v7 = -1073741436;
    }
    ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
  }
LABEL_23:
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_id(v5, 16, v6, InterfaceLuid->Value, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140016760  mov     rax, rsp
0x140016763  push    rbx
0x140016764  push    rbp
0x140016765  push    rsi
0x140016766  push    rdi
0x140016767  push    r14
0x140016769  push    r15
0x14001676b  sub     rsp, 88h
0x140016772  mov     dword ptr [rax+18h], 0
0x140016779  xorps   xmm0, xmm0
0x14001677c  xor     eax, eax
0x14001677e  mov     rbp, rdx
0x140016781  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140016786  mov     rsi, rcx
0x140016789  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14001678e  test    byte ptr cs:xmmword_1400272E0, 2
0x140016795  jz      short loc_1400167A2
0x140016797  mov     r9, [rcx]
0x14001679a  lea     edx, [rax+0Fh]
0x14001679d  call    WPP_SF_i
0x1400167a2  mov     rcx, rbp
0x1400167a5  call    IPxlatInstancePropertiesValid
0x1400167aa  test    al, al
0x1400167ac  jnz     short loc_1400167B8
0x1400167ae  mov     edi, 0C000000Dh
0x1400167b3  jmp     loc_1400169B0
0x1400167b8  lea     rdx, [rsp+0B8h+InterfaceIndex]; InterfaceIndex
0x1400167c0  mov     rcx, rsi; InterfaceLuid
0x1400167c3  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1400167ca  nop     dword ptr [rax+rax+00h]
0x1400167cf  mov     edi, eax
0x1400167d1  test    eax, eax
0x1400167d3  js      loc_1400169B0
0x1400167d9  lea     r15, stru_1400278F0
0x1400167e0  mov     rcx, r15; Resource
0x1400167e3  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400167ea  nop     dword ptr [rax+rax+00h]
0x1400167ef  cmp     cs:IPxlatGlobalState, 0
0x1400167f6  jnz     short loc_140016802
0x1400167f8  mov     edi, 0C0000184h
0x1400167fd  jmp     loc_1400169A1
0x140016802  mov     rcx, [rsi]
0x140016805  call    IPxlatFindInstance
0x14001680a  test    rax, rax
0x14001680d  jz      short loc_140016819
0x14001680f  mov     edi, 0C000022Bh
0x140016814  jmp     loc_1400169A1
0x140016819  mov     edx, 90h
0x14001681e  mov     r8d, 6E694C58h
0x140016824  lea     ecx, [rdx-50h]
0x140016827  call    cs:__imp_ExAllocatePool2
0x14001682e  nop     dword ptr [rax+rax+00h]
0x140016833  mov     rbx, rax
0x140016836  test    rax, rax
0x140016839  jnz     short loc_14001686A
0x14001683b  cmp     cs:dword_140027104, 1
0x140016842  jnz     short loc_140016860
0x140016844  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14001684b  jz      short loc_140016860
0x14001684d  lea     r9, aIpxlatInstance; "IPxlat instance buffer allocation faile"...
0x140016854  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001685b  call    McTemplateK0z_EtwWriteTransfer
0x140016860  mov     edi, 0C000009Ah
0x140016865  jmp     loc_1400169A1
0x14001686a  mov     rax, [rsi]
0x14001686d  lea     r14, [rbx+1Ch]
0x140016871  mov     [rbx+10h], rax
0x140016875  lea     rdx, [rbp+8]; Src
0x140016879  mov     eax, [rsp+0B8h+InterfaceIndex]
0x140016880  mov     rcx, r14; void *
0x140016883  mov     [rbx+18h], eax
0x140016886  movzx   r8d, byte ptr [rbp+18h]
0x14001688b  shr     r8, 3; Size
0x14001688f  call    memmove
0x140016894  mov     dl, [rbp+18h]
0x140016897  mov     r8, rbp
0x14001689a  mov     rcx, r14
0x14001689d  call    IN6_SET_V4ADDR_IN_V4EMBV6
0x1400168a2  movups  xmm0, xmmword ptr [rbp+0]
0x1400168a6  mov     dl, 1
0x1400168a8  mov     rcx, rbx
0x1400168ab  movups  xmmword ptr [rbx+50h], xmm0
0x1400168af  movups  xmm1, xmmword ptr [rbp+10h]
0x1400168b3  movups  xmmword ptr [rbx+60h], xmm1
0x1400168b7  movups  xmm0, xmmword ptr [rbp+1Ch]
0x1400168bb  movups  xmmword ptr [rbx+6Ch], xmm0
0x1400168bf  call    IPxlatConfigureFiltersForInstance
0x1400168c4  mov     edi, eax
0x1400168c6  test    eax, eax
0x1400168c8  jns     short loc_1400168EF
0x1400168ca  mov     rcx, r15; Resource
0x1400168cd  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400168d4  nop     dword ptr [rax+rax+00h]
0x1400168d9  xor     edx, edx; Tag
0x1400168db  mov     rcx, rbx; P
0x1400168de  call    cs:__imp_ExFreePoolWithTag
0x1400168e5  nop     dword ptr [rax+rax+00h]
0x1400168ea  jmp     loc_1400169B0
0x1400168ef  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x1400168f4  lea     rcx, qword_140027958; SpinLock
0x1400168fb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140016902  nop     dword ptr [rax+rax+00h]
0x140016907  mov     rax, cs:qword_1400278E8
0x14001690e  lea     rcx, qword_1400278E0
0x140016915  cmp     [rax], rcx
0x140016918  jz      short loc_140016921
0x14001691a  mov     ecx, 3
0x14001691f  int     29h; Win8: RtlFailFast(ecx)
0x140016921  mov     [rbx], rcx
0x140016924  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140016929  mov     [rbx+8], rax
0x14001692d  mov     [rax], rbx
0x140016930  mov     cs:qword_1400278E8, rbx
0x140016937  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001693e  nop     dword ptr [rax+rax+00h]
0x140016943  cmp     cs:dword_140027104, 1
0x14001694a  jnz     short loc_1400169A1
0x14001694c  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140016953  jz      short loc_1400169A1
0x140016955  movzx   eax, byte ptr [rbx+68h]
0x140016959  lea     rcx, [rbx+58h]
0x14001695d  movzx   edx, byte ptr [rbx+7Ah]
0x140016961  lea     r8, [rbx+6Ah]
0x140016965  mov     r9, [rbx+10h]
0x140016969  mov     [rsp+0B8h+var_68], eax
0x14001696d  mov     eax, [rbx+50h]
0x140016970  mov     [rsp+0B8h+var_70], rcx
0x140016975  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001697c  mov     [rsp+0B8h+var_78], edx
0x140016980  lea     rdx, WINNAT_IPXLAT_INSTANCE_CREATION
0x140016987  mov     [rsp+0B8h+var_80], r8
0x14001698c  mov     [rsp+0B8h+var_88], r14
0x140016991  mov     [rsp+0B8h+var_90], eax
0x140016995  mov     eax, [rbx+54h]
0x140016998  mov     [rsp+0B8h+var_98], eax
0x14001699c  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x1400169a1  mov     rcx, r15; Resource
0x1400169a4  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400169ab  nop     dword ptr [rax+rax+00h]
0x1400169b0  test    byte ptr cs:xmmword_1400272E0, 2
0x1400169b7  jz      short loc_1400169CA
0x1400169b9  mov     r9, [rsi]
0x1400169bc  mov     edx, 10h
0x1400169c1  mov     [rsp+0B8h+var_98], edi
0x1400169c5  call    WPP_SF_id
0x1400169ca  mov     eax, edi
0x1400169cc  add     rsp, 88h
0x1400169d3  pop     r15
0x1400169d5  pop     r14
0x1400169d7  pop     rdi
0x1400169d8  pop     rsi
0x1400169d9  pop     rbp
0x1400169da  pop     rbx
0x1400169db  retn
```
