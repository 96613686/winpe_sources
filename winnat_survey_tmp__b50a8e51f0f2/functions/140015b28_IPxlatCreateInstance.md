# IPxlatCreateInstance

- ea: `0x140015b28`
- end: `0x140015da5`
- name: `IPxlatCreateInstance`
- size: `637`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140033a40`

## callees

- `0x14000e488`
- `0x1400158b8`
- `0x140015b28`
- `0x1400161c0`
- `0x14001623c`
- `0x140016aec`
- `0x14001f140`
- `0x14002d53c`
- `0x14002d57c`
- `0x140033868`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015cff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015cff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015cc3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ca6`
- `ntoskrnl!ExAllocatePool2` at `0x140015bef`
- `ntoskrnl!ExAllocatePool2` at `0x140015bef`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015c95`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015d6c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015c95`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015d6c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140015bab`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140015bab`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140015b8b`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140015b8b`

## pseudocode

```c
__int64 __fastcall IPxlatCreateInstance(NET_LUID *InterfaceLuid, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  NTSTATUS v7; // edi
  __int64 Pool2; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rbx
  int v12; // edx
  __int64 v13; // rdx
  _QWORD *v14; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-58h] BYREF
  ULONG InterfaceIndex; // [rsp+D0h] [rbp+18h] BYREF

  InterfaceIndex = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_i(InterfaceLuid, 15, a3, InterfaceLuid->Value);
  if ( !(unsigned __int8)IPxlatInstancePropertiesValid(a2) )
  {
    v7 = -1073741811;
    goto LABEL_23;
  }
  v7 = ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
  if ( v7 >= 0 )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400268F0);
    if ( IPxlatGlobalState )
    {
      if ( IPxlatFindInstance(InterfaceLuid->Value) )
      {
        v7 = -1073741269;
      }
      else
      {
        Pool2 = ExAllocatePool2(64, 128, 1852394584);
        v11 = (_QWORD *)Pool2;
        if ( Pool2 )
        {
          *(NET_LUID *)(Pool2 + 16) = (NET_LUID)InterfaceLuid->Value;
          *(_DWORD *)(Pool2 + 24) = InterfaceIndex;
          memmove((void *)(Pool2 + 28), (const void *)(a2 + 8), (unsigned __int64)*(unsigned __int8 *)(a2 + 24) >> 3);
          LOBYTE(v12) = *(_BYTE *)(a2 + 24);
          IN6_SET_V4ADDR_IN_V4EMBV6((__int64)v11 + 28, v12, a2);
          LOBYTE(v13) = 1;
          *((_OWORD *)v11 + 5) = *(_OWORD *)a2;
          *((_OWORD *)v11 + 6) = *(_OWORD *)(a2 + 16);
          *(_OWORD *)((char *)v11 + 108) = *(_OWORD *)(a2 + 28);
          v7 = IPxlatConfigureFiltersForInstance(v11, v13);
          if ( v7 < 0 )
          {
            ExReleaseResourceAndLeaveCriticalRegion(&stru_1400268F0);
            ExFreePoolWithTag(v11, 0);
            goto LABEL_23;
          }
          KeAcquireInStackQueuedSpinLock(&qword_140026958, &LockHandle);
          v14 = (_QWORD *)qword_1400268E8;
          if ( *(PVOID **)qword_1400268E8 != &qword_1400268E0 )
            __fastfail(3u);
          *v11 = &qword_1400268E0;
          v11[1] = v14;
          *v14 = v11;
          qword_1400268E8 = (__int64)v11;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
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
          if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
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
    ExReleaseResourceAndLeaveCriticalRegion(&stru_1400268F0);
  }
LABEL_23:
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_id(v5, 16, v6, InterfaceLuid->Value, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140015b28  mov     rax, rsp
0x140015b2b  push    rbx
0x140015b2c  push    rbp
0x140015b2d  push    rsi
0x140015b2e  push    rdi
0x140015b2f  push    r14
0x140015b31  push    r15
0x140015b33  sub     rsp, 88h
0x140015b3a  mov     dword ptr [rax+18h], 0
0x140015b41  xorps   xmm0, xmm0
0x140015b44  xor     eax, eax
0x140015b46  mov     rbp, rdx
0x140015b49  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140015b4e  mov     rsi, rcx
0x140015b51  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140015b56  test    byte ptr cs:xmmword_1400262E0, 2
0x140015b5d  jz      short loc_140015B6A
0x140015b5f  mov     r9, [rcx]
0x140015b62  lea     edx, [rax+0Fh]
0x140015b65  call    WPP_SF_i
0x140015b6a  mov     rcx, rbp
0x140015b6d  call    IPxlatInstancePropertiesValid
0x140015b72  test    al, al
0x140015b74  jnz     short loc_140015B80
0x140015b76  mov     edi, 0C000000Dh
0x140015b7b  jmp     loc_140015D78
0x140015b80  lea     rdx, [rsp+0B8h+InterfaceIndex]; InterfaceIndex
0x140015b88  mov     rcx, rsi; InterfaceLuid
0x140015b8b  call    cs:__imp_ConvertInterfaceLuidToIndex
0x140015b92  nop     dword ptr [rax+rax+00h]
0x140015b97  mov     edi, eax
0x140015b99  test    eax, eax
0x140015b9b  js      loc_140015D78
0x140015ba1  lea     r15, stru_1400268F0
0x140015ba8  mov     rcx, r15; Resource
0x140015bab  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140015bb2  nop     dword ptr [rax+rax+00h]
0x140015bb7  cmp     cs:IPxlatGlobalState, 0
0x140015bbe  jnz     short loc_140015BCA
0x140015bc0  mov     edi, 0C0000184h
0x140015bc5  jmp     loc_140015D69
0x140015bca  mov     rcx, [rsi]
0x140015bcd  call    IPxlatFindInstance
0x140015bd2  test    rax, rax
0x140015bd5  jz      short loc_140015BE1
0x140015bd7  mov     edi, 0C000022Bh
0x140015bdc  jmp     loc_140015D69
0x140015be1  mov     edx, 80h
0x140015be6  mov     r8d, 6E694C58h
0x140015bec  lea     ecx, [rdx-40h]
0x140015bef  call    cs:__imp_ExAllocatePool2
0x140015bf6  nop     dword ptr [rax+rax+00h]
0x140015bfb  mov     rbx, rax
0x140015bfe  test    rax, rax
0x140015c01  jnz     short loc_140015C32
0x140015c03  cmp     cs:dword_140026104, 1
0x140015c0a  jnz     short loc_140015C28
0x140015c0c  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140015c13  jz      short loc_140015C28
0x140015c15  lea     r9, aIpxlatInstance; "IPxlat instance buffer allocation faile"...
0x140015c1c  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140015c23  call    McTemplateK0z_EtwWriteTransfer
0x140015c28  mov     edi, 0C000009Ah
0x140015c2d  jmp     loc_140015D69
0x140015c32  mov     rax, [rsi]
0x140015c35  lea     r14, [rbx+1Ch]
0x140015c39  mov     [rbx+10h], rax
0x140015c3d  lea     rdx, [rbp+8]; Src
0x140015c41  mov     eax, [rsp+0B8h+InterfaceIndex]
0x140015c48  mov     rcx, r14; void *
0x140015c4b  mov     [rbx+18h], eax
0x140015c4e  movzx   r8d, byte ptr [rbp+18h]
0x140015c53  shr     r8, 3; Size
0x140015c57  call    memmove
0x140015c5c  mov     dl, [rbp+18h]
0x140015c5f  mov     r8, rbp
0x140015c62  mov     rcx, r14
0x140015c65  call    IN6_SET_V4ADDR_IN_V4EMBV6
0x140015c6a  movups  xmm0, xmmword ptr [rbp+0]
0x140015c6e  mov     dl, 1
0x140015c70  mov     rcx, rbx
0x140015c73  movups  xmmword ptr [rbx+50h], xmm0
0x140015c77  movups  xmm1, xmmword ptr [rbp+10h]
0x140015c7b  movups  xmmword ptr [rbx+60h], xmm1
0x140015c7f  movups  xmm0, xmmword ptr [rbp+1Ch]
0x140015c83  movups  xmmword ptr [rbx+6Ch], xmm0
0x140015c87  call    IPxlatConfigureFiltersForInstance
0x140015c8c  mov     edi, eax
0x140015c8e  test    eax, eax
0x140015c90  jns     short loc_140015CB7
0x140015c92  mov     rcx, r15; Resource
0x140015c95  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140015c9c  nop     dword ptr [rax+rax+00h]
0x140015ca1  xor     edx, edx; Tag
0x140015ca3  mov     rcx, rbx; P
0x140015ca6  call    cs:__imp_ExFreePoolWithTag
0x140015cad  nop     dword ptr [rax+rax+00h]
0x140015cb2  jmp     loc_140015D78
0x140015cb7  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140015cbc  lea     rcx, qword_140026958; SpinLock
0x140015cc3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140015cca  nop     dword ptr [rax+rax+00h]
0x140015ccf  mov     rax, cs:qword_1400268E8
0x140015cd6  lea     rcx, qword_1400268E0
0x140015cdd  cmp     [rax], rcx
0x140015ce0  jz      short loc_140015CE9
0x140015ce2  mov     ecx, 3
0x140015ce7  int     29h; Win8: RtlFailFast(ecx)
0x140015ce9  mov     [rbx], rcx
0x140015cec  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140015cf1  mov     [rbx+8], rax
0x140015cf5  mov     [rax], rbx
0x140015cf8  mov     cs:qword_1400268E8, rbx
0x140015cff  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140015d06  nop     dword ptr [rax+rax+00h]
0x140015d0b  cmp     cs:dword_140026104, 1
0x140015d12  jnz     short loc_140015D69
0x140015d14  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140015d1b  jz      short loc_140015D69
0x140015d1d  movzx   eax, byte ptr [rbx+68h]
0x140015d21  lea     rcx, [rbx+58h]
0x140015d25  movzx   edx, byte ptr [rbx+7Ah]
0x140015d29  lea     r8, [rbx+6Ah]
0x140015d2d  mov     r9, [rbx+10h]
0x140015d31  mov     [rsp+0B8h+var_68], eax
0x140015d35  mov     eax, [rbx+50h]
0x140015d38  mov     [rsp+0B8h+var_70], rcx
0x140015d3d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140015d44  mov     [rsp+0B8h+var_78], edx
0x140015d48  lea     rdx, WINNAT_IPXLAT_INSTANCE_CREATION
0x140015d4f  mov     [rsp+0B8h+var_80], r8
0x140015d54  mov     [rsp+0B8h+var_88], r14
0x140015d59  mov     [rsp+0B8h+var_90], eax
0x140015d5d  mov     eax, [rbx+54h]
0x140015d60  mov     [rsp+0B8h+var_98], eax
0x140015d64  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x140015d69  mov     rcx, r15; Resource
0x140015d6c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140015d73  nop     dword ptr [rax+rax+00h]
0x140015d78  test    byte ptr cs:xmmword_1400262E0, 2
0x140015d7f  jz      short loc_140015D92
0x140015d81  mov     r9, [rsi]
0x140015d84  mov     edx, 10h
0x140015d89  mov     [rsp+0B8h+var_98], edi
0x140015d8d  call    WPP_SF_id
0x140015d92  mov     eax, edi
0x140015d94  add     rsp, 88h
0x140015d9b  pop     r15
0x140015d9d  pop     r14
0x140015d9f  pop     rdi
0x140015da0  pop     rsi
0x140015da1  pop     rbp
0x140015da2  pop     rbx
0x140015da3  retn
```
