# IPxlatCreateInstance

- ea: `0x1400164a8`
- end: `0x140016759`
- name: `IPxlatCreateInstance`
- size: `689`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034d80`

## callees

- `0x14000e4b0`
- `0x1400164a8`
- `0x140016e28`
- `0x140016ea4`
- `0x140016f08`
- `0x1400177b8`
- `0x14002e53c`
- `0x14002e57c`
- `0x140034b28`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001667f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001667f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016643`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016643`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016626`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016626`
- `ntoskrnl!ExAllocatePool2` at `0x14001657e`
- `ntoskrnl!ExAllocatePool2` at `0x14001657e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016615`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016713`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016615`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016713`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016538`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016538`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140016517`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140016517`

## pseudocode

```c
__int64 __fastcall IPxlatCreateInstance(NET_LUID *InterfaceLuid, __int128 *a2, __int64 a3)
{
  const NET_LUID *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  NTSTATUS v7; // r13d
  __int64 Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  char *v11; // rdi
  int *v12; // r14
  __int128 v13; // xmm0
  char **v14; // rax
  char v15; // si
  char v16; // bp
  int v17; // r15d
  __int64 v18; // r12
  int v19; // r14d
  __int64 v20; // rax
  int v21; // r8d
  char v23[16]; // [rsp+60h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-58h] BYREF
  ULONG InterfaceIndex; // [rsp+E0h] [rbp+18h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+20h]

  InterfaceIndex = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = InterfaceLuid;
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_i(InterfaceLuid, 17, a3, InterfaceLuid->Value);
  if ( !(unsigned __int8)IPxlatInstancePropertiesValid(a2) )
  {
    v7 = -1073741811;
    goto LABEL_23;
  }
  v7 = ConvertInterfaceLuidToIndex(v4, &InterfaceIndex);
  if ( v7 >= 0 )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400278F0);
    if ( IPxlatGlobalState )
    {
      if ( IPxlatFindInstance(v4->Value) )
      {
        v7 = -1073741269;
      }
      else
      {
        Pool2 = ExAllocatePool2(64, 144, 1852394584);
        v11 = (char *)Pool2;
        if ( Pool2 )
        {
          v12 = (int *)(Pool2 + 80);
          *(NET_LUID *)(Pool2 + 16) = (NET_LUID)v4->Value;
          LOBYTE(v9) = 1;
          *(_DWORD *)(Pool2 + 24) = InterfaceIndex;
          v13 = *a2;
          v27 = Pool2 + 80;
          *(_OWORD *)(Pool2 + 80) = v13;
          *(_OWORD *)(Pool2 + 96) = a2[1];
          *(_OWORD *)(Pool2 + 112) = a2[2];
          *(_OWORD *)(Pool2 + 124) = *(__int128 *)((char *)a2 + 44);
          v7 = IPxlatConfigureFiltersForInstance(Pool2, v9);
          if ( v7 < 0 )
          {
            ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
            ExFreePoolWithTag(v11, 0);
            goto LABEL_23;
          }
          KeAcquireInStackQueuedSpinLock(&qword_140027958, &LockHandle);
          v14 = (char **)qword_1400278E8;
          if ( *(PVOID **)qword_1400278E8 != &qword_1400278E0 )
            __fastfail(3u);
          *(_QWORD *)v11 = &qword_1400278E0;
          *((_QWORD *)v11 + 1) = v14;
          *v14 = v11;
          qword_1400278E8 = (__int64)v11;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          {
            v15 = v11[104];
            v16 = v11[122];
            v17 = *((_DWORD *)v11 + 21);
            v18 = *((_QWORD *)v11 + 2);
            v19 = *v12;
            v20 = IPxlatResolveSyntheticIPv6Address(v23);
            McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNAT_IPXLAT_INSTANCE_CREATION,
              v21,
              v18,
              v17,
              v19,
              v20,
              (__int64)(v11 + 106),
              v16,
              (__int64)(v11 + 88),
              v15);
            v4 = InterfaceLuid;
          }
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
    WPP_SF_id(v5, 18, v6, v4->Value, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400164a8  mov     r11, rsp
0x1400164ab  mov     [r11+10h], rbx
0x1400164af  mov     [r11+8], rcx
0x1400164b3  push    rbp
0x1400164b4  push    rsi
0x1400164b5  push    rdi
0x1400164b6  push    r12
0x1400164b8  push    r13
0x1400164ba  push    r14
0x1400164bc  push    r15
0x1400164be  sub     rsp, 90h
0x1400164c5  xorps   xmm0, xmm0
0x1400164c8  mov     dword ptr [r11+18h], 0
0x1400164d0  xor     eax, eax
0x1400164d2  mov     rsi, rdx
0x1400164d5  movups  xmmword ptr [rsp+0C8h+LockHandle.LockQueue.Next], xmm0
0x1400164da  mov     [r11-48h], rax
0x1400164de  mov     rbx, rcx
0x1400164e1  test    byte ptr cs:xmmword_1400272E0, 2
0x1400164e8  jz      short loc_1400164F5
0x1400164ea  mov     r9, [rcx]
0x1400164ed  lea     edx, [rax+11h]
0x1400164f0  call    WPP_SF_i
0x1400164f5  mov     rcx, rsi
0x1400164f8  call    IPxlatInstancePropertiesValid
0x1400164fd  test    al, al
0x1400164ff  jnz     short loc_14001650C
0x140016501  mov     r13d, 0C000000Dh
0x140016507  jmp     loc_14001671F
0x14001650c  lea     rdx, [rsp+0C8h+InterfaceIndex]; InterfaceIndex
0x140016514  mov     rcx, rbx; InterfaceLuid
0x140016517  call    cs:__imp_ConvertInterfaceLuidToIndex
0x14001651e  nop     dword ptr [rax+rax+00h]
0x140016523  mov     r13d, eax
0x140016526  test    eax, eax
0x140016528  js      loc_14001671F
0x14001652e  lea     rbp, stru_1400278F0
0x140016535  mov     rcx, rbp; Resource
0x140016538  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14001653f  nop     dword ptr [rax+rax+00h]
0x140016544  cmp     cs:IPxlatGlobalState, 0
0x14001654b  jnz     short loc_140016558
0x14001654d  mov     r13d, 0C0000184h
0x140016553  jmp     loc_140016710
0x140016558  mov     rcx, [rbx]
0x14001655b  call    IPxlatFindInstance
0x140016560  test    rax, rax
0x140016563  jz      short loc_140016570
0x140016565  mov     r13d, 0C000022Bh
0x14001656b  jmp     loc_140016710
0x140016570  mov     edx, 90h
0x140016575  mov     r8d, 6E694C58h
0x14001657b  lea     ecx, [rdx-50h]
0x14001657e  call    cs:__imp_ExAllocatePool2
0x140016585  nop     dword ptr [rax+rax+00h]
0x14001658a  mov     rdi, rax
0x14001658d  test    rax, rax
0x140016590  jnz     short loc_1400165C2
0x140016592  cmp     cs:dword_140027104, 1
0x140016599  jnz     short loc_1400165B7
0x14001659b  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x1400165a2  jz      short loc_1400165B7
0x1400165a4  lea     r9, aIpxlatInstance; "IPxlat instance buffer allocation faile"...
0x1400165ab  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400165b2  call    McTemplateK0z_EtwWriteTransfer
0x1400165b7  mov     r13d, 0C000009Ah
0x1400165bd  jmp     loc_140016710
0x1400165c2  mov     rax, [rbx]
0x1400165c5  lea     r14, [rdi+50h]
0x1400165c9  mov     [rdi+10h], rax
0x1400165cd  mov     dl, 1
0x1400165cf  mov     eax, [rsp+0C8h+InterfaceIndex]
0x1400165d6  mov     rcx, rdi
0x1400165d9  mov     [rdi+18h], eax
0x1400165dc  movups  xmm0, xmmword ptr [rsi]
0x1400165df  mov     [rsp+0C8h+arg_18], r14
0x1400165e7  movups  xmmword ptr [r14], xmm0
0x1400165eb  movups  xmm1, xmmword ptr [rsi+10h]
0x1400165ef  movups  xmmword ptr [r14+10h], xmm1
0x1400165f4  movups  xmm0, xmmword ptr [rsi+20h]
0x1400165f8  movups  xmmword ptr [r14+20h], xmm0
0x1400165fd  movups  xmm1, xmmword ptr [rsi+2Ch]
0x140016601  movups  xmmword ptr [r14+2Ch], xmm1
0x140016606  call    IPxlatConfigureFiltersForInstance
0x14001660b  mov     r13d, eax
0x14001660e  test    eax, eax
0x140016610  jns     short loc_140016637
0x140016612  mov     rcx, rbp; Resource
0x140016615  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14001661c  nop     dword ptr [rax+rax+00h]
0x140016621  xor     edx, edx; Tag
0x140016623  mov     rcx, rdi; P
0x140016626  call    cs:__imp_ExFreePoolWithTag
0x14001662d  nop     dword ptr [rax+rax+00h]
0x140016632  jmp     loc_14001671F
0x140016637  lea     rdx, [rsp+0C8h+LockHandle]; LockHandle
0x14001663c  lea     rcx, qword_140027958; SpinLock
0x140016643  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001664a  nop     dword ptr [rax+rax+00h]
0x14001664f  mov     rax, cs:qword_1400278E8
0x140016656  lea     rcx, qword_1400278E0
0x14001665d  cmp     [rax], rcx
0x140016660  jz      short loc_140016669
0x140016662  mov     ecx, 3
0x140016667  int     29h; Win8: RtlFailFast(ecx)
0x140016669  mov     [rdi], rcx
0x14001666c  lea     rcx, [rsp+0C8h+LockHandle]; LockHandle
0x140016671  mov     [rdi+8], rax
0x140016675  mov     [rax], rdi
0x140016678  mov     cs:qword_1400278E8, rdi
0x14001667f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140016686  nop     dword ptr [rax+rax+00h]
0x14001668b  cmp     cs:dword_140027104, 1
0x140016692  jnz     short loc_140016710
0x140016694  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14001669b  jz      short loc_140016710
0x14001669d  movzx   esi, byte ptr [rdi+68h]
0x1400166a1  lea     rbx, [rdi+58h]
0x1400166a5  movzx   ebp, byte ptr [rdi+7Ah]
0x1400166a9  lea     rcx, [rsp+0C8h+var_68]; void *
0x1400166ae  mov     r15d, [rdi+54h]
0x1400166b2  mov     r12, [rdi+10h]
0x1400166b6  add     rdi, 6Ah ; 'j'
0x1400166ba  mov     rdx, [rsp+0C8h+arg_18]
0x1400166c2  mov     r14d, [r14]
0x1400166c5  call    IPxlatResolveSyntheticIPv6Address
0x1400166ca  mov     [rsp+0C8h+var_78], esi
0x1400166ce  lea     rdx, WINNAT_IPXLAT_INSTANCE_CREATION
0x1400166d5  mov     [rsp+0C8h+var_80], rbx
0x1400166da  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400166e1  mov     [rsp+0C8h+var_88], ebp
0x1400166e5  mov     r9, r12
0x1400166e8  mov     [rsp+0C8h+var_90], rdi
0x1400166ed  mov     [rsp+0C8h+var_98], rax
0x1400166f2  mov     [rsp+0C8h+var_A0], r14d
0x1400166f7  mov     [rsp+0C8h+var_A8], r15d
0x1400166fc  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x140016701  mov     rbx, [rsp+0C8h+arg_0]
0x140016709  lea     rbp, stru_1400278F0
0x140016710  mov     rcx, rbp; Resource
0x140016713  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14001671a  nop     dword ptr [rax+rax+00h]
0x14001671f  test    byte ptr cs:xmmword_1400272E0, 2
0x140016726  jz      short loc_14001673A
0x140016728  mov     r9, [rbx]
0x14001672b  mov     edx, 12h
0x140016730  mov     [rsp+0C8h+var_A8], r13d
0x140016735  call    WPP_SF_id
0x14001673a  mov     rbx, [rsp+0C8h+arg_8]
0x140016742  mov     eax, r13d
0x140016745  add     rsp, 90h
0x14001674c  pop     r15
0x14001674e  pop     r14
0x140016750  pop     r13
0x140016752  pop     r12
0x140016754  pop     rdi
0x140016755  pop     rsi
0x140016756  pop     rbp
0x140016757  retn
```
