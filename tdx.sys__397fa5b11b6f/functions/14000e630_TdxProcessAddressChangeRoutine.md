# TdxProcessAddressChangeRoutine

- ea: `0x14000e630`
- end: `0x14000eb95`
- name: `TdxProcessAddressChangeRoutine`
- size: `1381`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e550`

## callees

- `0x14000e630`
- `0x14000eba0`
- `0x140010608`
- `0x140012e90`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000e8d4`
- `ntoskrnl!KeReleaseMutex` at `0x14000e8d4`
- `ntoskrnl!RtlCompareMemory` at `0x14000e722`
- `ntoskrnl!RtlCompareMemory` at `0x14000ea34`
- `ntoskrnl!RtlCompareMemory` at `0x14000e722`
- `ntoskrnl!RtlCompareMemory` at `0x14000ea34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e836`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e909`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e836`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e909`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e86f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e86f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e747`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e84d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e973`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e747`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e84d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e973`
- `NETIO!NsiGetAllParameters` at `0x14000e7a3`
- `NETIO!NsiGetAllParameters` at `0x14000e9cc`
- `NETIO!NsiGetAllParameters` at `0x14000e7a3`
- `NETIO!NsiGetAllParameters` at `0x14000e9cc`
- `TDI!TdiDeregisterNetAddress` at `0x14000e8e8`
- `TDI!TdiDeregisterNetAddress` at `0x14000e8e8`
- `TDI!TdiDeregisterDeviceObject` at `0x14000eb7d`
- `TDI!TdiDeregisterDeviceObject` at `0x14000eb7d`

## pseudocode

```c
void __fastcall TdxProcessAddressChangeRoutine(_QWORD *P)
{
  _QWORD *v1; // r13
  const NPI_MODULEID *v2; // r15
  __int128 *v3; // rdi
  unsigned int v4; // ebx
  KIRQL v5; // al
  SIZE_T v6; // rsi
  KIRQL v7; // r12
  const void *v8; // r14
  KDEVICE_QUEUE *i; // rbx
  __int64 v10; // rbx
  unsigned int v11; // edi
  void ***v12; // r15
  void **v13; // rdx
  void **v14; // rax
  void **v15; // rdi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  void *v19; // rbx
  void *v20; // rcx
  int AllParameters; // eax
  KIRQL v22; // al
  SIZE_T v23; // rsi
  const void *v24; // r14
  KIRQL v25; // r12
  KDEVICE_QUEUE *v26; // rdi
  __int64 v27; // [rsp+68h] [rbp-39h] BYREF
  PVOID Pa; // [rsp+70h] [rbp-31h] BYREF
  _QWORD v29[2]; // [rsp+78h] [rbp-29h] BYREF
  _OWORD v30[2]; // [rsp+88h] [rbp-19h] BYREF
  __int128 v31; // [rsp+A8h] [rbp+7h] BYREF
  __int128 v32; // [rsp+B8h] [rbp+17h] BYREF
  __int64 v33; // [rsp+C8h] [rbp+27h]

  Pa = 0;
  v33 = 0;
  v27 = 0;
  v1 = P;
  v29[0] = 0;
  memset(v30, 0, 28);
  v31 = 0;
  v32 = 0;
  if ( P )
  {
    do
    {
      v2 = &NPI_MS_IPV4_MODULEID;
      v3 = &v32;
      v4 = 16;
      if ( v1[1] )
      {
        v2 = &NPI_MS_IPV6_MODULEID;
        v4 = 24;
      }
      else
      {
        v3 = &v31;
      }
      if ( v1[2] )
      {
        v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
        v6 = *((unsigned int *)v1 + 6);
        v7 = v5;
        v8 = (const void *)v1[2];
        for ( i = *(KDEVICE_QUEUE **)&WPP_MAIN_CB.DeviceQueue.Type; ; i = *(KDEVICE_QUEUE **)&i->Type )
        {
          while ( 1 )
          {
            if ( i == &WPP_MAIN_CB.DeviceQueue )
              goto LABEL_12;
            if ( LODWORD(i->DeviceListHead.Blink) == (_DWORD)v6 )
              break;
            i = *(KDEVICE_QUEUE **)&i->Type;
          }
          if ( RtlCompareMemory((const void *)i->Lock, v8, v6) == v6 )
            break;
        }
        if ( i )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v7);
          AllParameters = NsiGetAllParameters(3, v2, 10, v1[2], *((_DWORD *)v1 + 6), v30, 28, &v27, 8, v29, 8);
          if ( AllParameters == -1073741275 || !AllParameters && HIDWORD(v27) != 4 )
          {
            Pa = 0;
            v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
            v23 = *((unsigned int *)v1 + 6);
            v12 = 0;
            v24 = (const void *)v1[2];
            v25 = v22;
            v26 = *(KDEVICE_QUEUE **)&WPP_MAIN_CB.DeviceQueue.Type;
            while ( v26 != &WPP_MAIN_CB.DeviceQueue )
            {
              if ( LODWORD(v26->DeviceListHead.Blink) == (_DWORD)v23 )
              {
                if ( RtlCompareMemory((const void *)v26->Lock, v24, v23) == v23 )
                {
                  v12 = (void ***)v26;
                  break;
                }
                v26 = *(KDEVICE_QUEUE **)&v26->Type;
              }
              else
              {
                v26 = *(KDEVICE_QUEUE **)&v26->Type;
              }
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                v12,
                &Pa);
            }
            v13 = *v12;
            if ( (*v12)[1] != v12 || (v14 = v12[1], *v14 != v12) )
LABEL_49:
              __fastfail(3u);
            *v14 = v13;
            v13[1] = v14;
            v15 = v12[5];
            Pa = v12[4];
            ExFreePoolWithTag(v12, 0x6E786454u);
            KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v25);
            KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
            v16 = Pa;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Pa + 4, 0xFFFFFFFF) == 1 )
            {
              v17 = *v16;
              if ( *(_QWORD **)(*v16 + 8LL) != v16 )
                goto LABEL_49;
              v18 = (_QWORD *)v16[1];
              if ( (_QWORD *)*v18 != v16 )
                goto LABEL_49;
              v19 = (void *)v16[35];
              *v18 = v17;
              *(_QWORD *)(v17 + 8) = v18;
              ExFreePoolWithTag(v16, 0x6F786454u);
            }
            else
            {
              v19 = 0;
            }
            KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
            if ( v15 )
              TdiDeregisterNetAddress(v15);
            if ( v19 )
              TdiDeregisterDeviceObject(v19);
          }
        }
        else
        {
LABEL_12:
          KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v7);
          v10 = v1[2];
          v11 = *((_DWORD *)v1 + 6);
          if ( (int)NsiGetAllParameters(3, v2, 10, v10, v11, v30, 28, &v27, 8, v29, 8) >= 0 && HIDWORD(v27) == 4 )
            TdxCreateAndRegisterNetAddress(*((unsigned int *)v1 + 2), v2, v11, v10);
        }
      }
      else if ( (int)TdxGetAllParameters(
                       3,
                       1,
                       (_DWORD)v2,
                       10,
                       (__int64)v3,
                       v4,
                       (__int64)v30,
                       28,
                       (__int64)&v27,
                       8,
                       (__int64)v29,
                       8) >= 0 )
      {
        do
        {
          if ( HIDWORD(v27) == 4 )
            TdxCreateAndRegisterNetAddress(*((unsigned int *)v1 + 2), v2, v4, v3);
        }
        while ( (int)TdxGetAllParameters(
                       3,
                       2,
                       (_DWORD)v2,
                       10,
                       (__int64)v3,
                       v4,
                       (__int64)v30,
                       28,
                       (__int64)&v27,
                       8,
                       (__int64)v29,
                       8) >= 0 );
      }
      v20 = v1;
      v1 = (_QWORD *)*v1;
      ExFreePoolWithTag(v20, 0x20786454u);
    }
    while ( v1 );
  }
}

```

## disassembly

```asm
0x14000e630  mov     r11, rsp
0x14000e633  push    rbp
0x14000e634  push    rsi
0x14000e635  push    r13
0x14000e637  lea     rbp, [r11-5Fh]
0x14000e63b  sub     rsp, 0E0h
0x14000e642  mov     rax, cs:__security_cookie
0x14000e649  xor     rax, rsp
0x14000e64c  mov     [rbp+57h+var_28], rax
0x14000e650  xor     esi, esi
0x14000e652  xorps   xmm0, xmm0
0x14000e655  xor     eax, eax
0x14000e657  mov     [rbp+57h+P], rsi
0x14000e65b  mov     [rbp+57h+var_30], rax
0x14000e65f  xorps   xmm1, xmm1
0x14000e662  mov     [rbp+57h+var_90], rsi
0x14000e666  mov     r13, rcx
0x14000e669  mov     [rbp+57h+var_80], rsi
0x14000e66d  movups  [rbp+57h+var_70], xmm0
0x14000e671  movups  [rbp+57h+var_70+0Ch], xmm0
0x14000e675  movups  [rbp+57h+var_50], xmm0
0x14000e679  movups  [rbp+57h+var_40], xmm1
0x14000e67d  test    rcx, rcx
0x14000e680  jz      loc_14000E946
0x14000e686  mov     [r11+10h], rbx
0x14000e68a  mov     [r11+18h], rdi
0x14000e68e  mov     [r11-20h], r14
0x14000e692  mov     [r11-28h], r15
0x14000e696  mov     [r11+20h], r12
0x14000e69a  mov     rax, [r13+8]
0x14000e69e  lea     rcx, NPI_MS_IPV4_MODULEID
0x14000e6a5  test    rax, rax
0x14000e6a8  lea     rdx, NPI_MS_IPV6_MODULEID
0x14000e6af  mov     r15, rcx
0x14000e6b2  lea     rdi, [rbp+57h+var_40]
0x14000e6b6  lea     rcx, [rbp+57h+var_50]
0x14000e6ba  mov     r8d, 18h
0x14000e6c0  mov     ebx, 10h
0x14000e6c5  cmovnz  r15, rdx
0x14000e6c9  cmovnz  ebx, r8d
0x14000e6cd  cmovz   rdi, rcx
0x14000e6d1  cmp     qword ptr [r13+10h], 0
0x14000e6d6  jz      loc_14000EA6D
0x14000e6dc  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000e6e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e6ea  nop     dword ptr [rax+rax+00h]
0x14000e6ef  mov     esi, [r13+18h]
0x14000e6f3  movzx   r12d, al
0x14000e6f7  mov     r14, [r13+10h]
0x14000e6fb  mov     rbx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14000e702  lea     rax, WPP_MAIN_CB.DeviceQueue
0x14000e709  cmp     rbx, rax
0x14000e70c  jz      short loc_14000E73C
0x14000e70e  cmp     [rbx+10h], esi
0x14000e711  jz      short loc_14000E718
0x14000e713  mov     rbx, [rbx]
0x14000e716  jmp     short loc_14000E709
0x14000e718  mov     rcx, [rbx+18h]; Source1
0x14000e71c  mov     r8, rsi; Length
0x14000e71f  mov     rdx, r14; Source2
0x14000e722  call    cs:__imp_RtlCompareMemory
0x14000e729  nop     dword ptr [rax+rax+00h]
0x14000e72e  cmp     rax, rsi
0x14000e731  jz      loc_14000E95F
0x14000e737  mov     rbx, [rbx]
0x14000e73a  jmp     short loc_14000E702
0x14000e73c  movzx   edx, r12b; NewIrql
0x14000e740  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000e747  call    cs:__imp_KeReleaseSpinLock
0x14000e74e  nop     dword ptr [rax+rax+00h]
0x14000e753  mov     rbx, [r13+10h]
0x14000e757  lea     rax, [rbp+57h+var_80]
0x14000e75b  mov     edi, [r13+18h]
0x14000e75f  mov     r9, rbx
0x14000e762  mov     [rsp+0F0h+var_A0], 8
0x14000e76a  mov     r8d, 0Ah
0x14000e770  mov     [rsp+0F0h+var_A8], rax
0x14000e775  mov     rdx, r15
0x14000e778  mov     dword ptr [rsp+0F0h+var_B0], 8
0x14000e780  lea     rax, [rbp+57h+var_90]
0x14000e784  mov     [rsp+0F0h+var_B8], rax
0x14000e789  mov     ecx, 3
0x14000e78e  lea     rax, [rbp+57h+var_70]
0x14000e792  mov     dword ptr [rsp+0F0h+var_C0], 1Ch
0x14000e79a  mov     [rsp+0F0h+var_C8], rax
0x14000e79f  mov     dword ptr [rsp+0F0h+Timeout], edi
0x14000e7a3  call    cs:__imp_NsiGetAllParameters
0x14000e7aa  nop     dword ptr [rax+rax+00h]
0x14000e7af  test    eax, eax
0x14000e7b1  js      loc_14000E8FD
0x14000e7b7  cmp     dword ptr [rbp+57h+var_90+4], 4
0x14000e7bb  jnz     loc_14000E8FD
0x14000e7c1  mov     ecx, [r13+8]
0x14000e7c5  lea     rax, [rbp+57h+var_90]
0x14000e7c9  mov     r9, rbx
0x14000e7cc  mov     [rsp+0F0h+var_C8], rax
0x14000e7d1  mov     r8d, edi
0x14000e7d4  mov     rdx, r15
0x14000e7d7  call    TdxCreateAndRegisterNetAddress
0x14000e7dc  jmp     loc_14000E8FD
0x14000e7e1  mov     r15, rdi
0x14000e7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7eb  lea     rax, WPP_GLOBAL_Control
0x14000e7f2  cmp     rcx, rax
0x14000e7f5  jz      short loc_14000E801
0x14000e7f7  cmp     byte ptr [rcx+29h], 4
0x14000e7fb  jnb     loc_14000EB47
0x14000e801  mov     rdx, [r15]
0x14000e804  cmp     [rdx+8], r15
0x14000e808  jnz     loc_14000EB8E
0x14000e80e  mov     rax, [r15+8]
0x14000e812  cmp     [rax], r15
0x14000e815  jnz     loc_14000EB8E
0x14000e81b  mov     [rax], rdx
0x14000e81e  mov     rcx, r15; P
0x14000e821  mov     [rdx+8], rax
0x14000e825  mov     edx, 6E786454h; Tag
0x14000e82a  mov     rax, [r15+20h]
0x14000e82e  mov     rdi, [r15+28h]
0x14000e832  mov     [rbp+57h+P], rax
0x14000e836  call    cs:__imp_ExFreePoolWithTag
0x14000e83d  nop     dword ptr [rax+rax+00h]
0x14000e842  movzx   edx, r12b; NewIrql
0x14000e846  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000e84d  call    cs:__imp_KeReleaseSpinLock
0x14000e854  nop     dword ptr [rax+rax+00h]
0x14000e859  xor     esi, esi
0x14000e85b  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Object
0x14000e862  xor     r9d, r9d; Alertable
0x14000e865  mov     [rsp+0F0h+Timeout], rsi; Timeout
0x14000e86a  xor     r8d, r8d; WaitMode
0x14000e86d  xor     edx, edx; WaitReason
0x14000e86f  call    cs:__imp_KeWaitForSingleObject
0x14000e876  nop     dword ptr [rax+rax+00h]
0x14000e87b  mov     rcx, [rbp+57h+P]; P
0x14000e87f  mov     eax, 0FFFFFFFFh
0x14000e884  lock xadd [rcx+10h], eax
0x14000e889  cmp     eax, 1
0x14000e88c  jnz     loc_14000EA4E
0x14000e892  mov     rdx, [rcx]
0x14000e895  cmp     [rdx+8], rcx
0x14000e899  jnz     loc_14000EB8E
0x14000e89f  mov     rax, [rcx+8]
0x14000e8a3  cmp     [rax], rcx
0x14000e8a6  jnz     loc_14000EB8E
0x14000e8ac  mov     rbx, [rcx+118h]
0x14000e8b3  mov     [rax], rdx
0x14000e8b6  mov     [rdx+8], rax
0x14000e8ba  mov     edx, 6F786454h; Tag
0x14000e8bf  call    cs:__imp_ExFreePoolWithTag
0x14000e8c6  nop     dword ptr [rax+rax+00h]
0x14000e8cb  xor     edx, edx; Wait
0x14000e8cd  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000e8d4  call    cs:__imp_KeReleaseMutex
0x14000e8db  nop     dword ptr [rax+rax+00h]
0x14000e8e0  test    rdi, rdi
0x14000e8e3  jz      short loc_14000E8F4
0x14000e8e5  mov     rcx, rdi; RegistrationHandle
0x14000e8e8  call    cs:__imp_TdiDeregisterNetAddress
0x14000e8ef  nop     dword ptr [rax+rax+00h]
0x14000e8f4  test    rbx, rbx
0x14000e8f7  jnz     loc_14000EB7A
0x14000e8fd  mov     rcx, r13; P
0x14000e900  mov     edx, 20786454h; Tag
0x14000e905  mov     r13, [r13+0]
0x14000e909  call    cs:__imp_ExFreePoolWithTag
0x14000e910  nop     dword ptr [rax+rax+00h]
0x14000e915  test    r13, r13
0x14000e918  jnz     loc_14000E69A
0x14000e91e  mov     r12, [rsp+0F0h+arg_18]
0x14000e926  mov     r14, [rsp+0D8h]
0x14000e92e  mov     rdi, [rsp+0F0h+arg_10]
0x14000e936  mov     rbx, [rsp+0F0h+arg_8]
0x14000e93e  mov     r15, [rsp+0F0h+var_20]
0x14000e946  mov     rcx, [rbp+57h+var_28]
0x14000e94a  xor     rcx, rsp; StackCookie
0x14000e94d  call    __security_check_cookie
0x14000e952  add     rsp, 0E0h
0x14000e959  pop     r13
0x14000e95b  pop     rsi
0x14000e95c  pop     rbp
0x14000e95d  retn
0x14000e95f  test    rbx, rbx
0x14000e962  jz      loc_14000E73C
0x14000e968  movzx   edx, r12b; NewIrql
0x14000e96c  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000e973  call    cs:__imp_KeReleaseSpinLock
0x14000e97a  nop     dword ptr [rax+rax+00h]
0x14000e97f  mov     r9, [r13+10h]
0x14000e983  lea     rax, [rbp+57h+var_80]
0x14000e987  mov     [rsp+0F0h+var_A0], 8
0x14000e98f  mov     r8d, 0Ah
0x14000e995  mov     [rsp+0F0h+var_A8], rax
0x14000e99a  mov     rdx, r15
0x14000e99d  mov     dword ptr [rsp+0F0h+var_B0], 8
0x14000e9a5  lea     rax, [rbp+57h+var_90]
0x14000e9a9  mov     [rsp+0F0h+var_B8], rax
0x14000e9ae  mov     ecx, 3
0x14000e9b3  lea     rax, [rbp+57h+var_70]
0x14000e9b7  mov     dword ptr [rsp+0F0h+var_C0], 1Ch
0x14000e9bf  mov     [rsp+0F0h+var_C8], rax
0x14000e9c4  mov     eax, [r13+18h]
0x14000e9c8  mov     dword ptr [rsp+0F0h+Timeout], eax
0x14000e9cc  call    cs:__imp_NsiGetAllParameters
0x14000e9d3  nop     dword ptr [rax+rax+00h]
0x14000e9d8  cmp     eax, 0C0000225h
0x14000e9dd  jnz     short loc_14000EA56
0x14000e9df  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000e9e6  mov     [rbp+57h+P], 0
0x14000e9ee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e9f5  nop     dword ptr [rax+rax+00h]
0x14000e9fa  mov     esi, [r13+18h]
0x14000e9fe  xor     r15d, r15d
0x14000ea01  mov     r14, [r13+10h]
0x14000ea05  movzx   r12d, al
0x14000ea09  mov     rdi, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x14000ea10  lea     rax, WPP_MAIN_CB.DeviceQueue
0x14000ea17  cmp     rdi, rax
0x14000ea1a  jz      loc_14000E7E4
0x14000ea20  cmp     [rdi+10h], esi
0x14000ea23  jz      short loc_14000EA2A
0x14000ea25  mov     rdi, [rdi]
0x14000ea28  jmp     short loc_14000EA17
0x14000ea2a  mov     rcx, [rdi+18h]; Source1
0x14000ea2e  mov     r8, rsi; Length
0x14000ea31  mov     rdx, r14; Source2
0x14000ea34  call    cs:__imp_RtlCompareMemory
0x14000ea3b  nop     dword ptr [rax+rax+00h]
0x14000ea40  cmp     rax, rsi
0x14000ea43  jz      loc_14000E7E1
0x14000ea49  mov     rdi, [rdi]
0x14000ea4c  jmp     short loc_14000EA10
0x14000ea4e  mov     rbx, rsi
0x14000ea51  jmp     loc_14000E8CB
0x14000ea56  test    eax, eax
0x14000ea58  jnz     loc_14000E8FD
0x14000ea5e  cmp     dword ptr [rbp+57h+var_90+4], 4
0x14000ea62  jnz     loc_14000E9DF
0x14000ea68  jmp     loc_14000E8FD
0x14000ea6d  mov     dword ptr [rsp+58h], 8
0x14000ea75  lea     rax, [rbp+57h+var_80]
0x14000ea79  mov     qword ptr [rsp+0F0h+var_A0], rax
0x14000ea7e  mov     r9d, 0Ah
0x14000ea84  mov     dword ptr [rsp+0F0h+var_A8], 8
0x14000ea8c  lea     rax, [rbp+57h+var_90]
0x14000ea90  mov     [rsp+0F0h+var_B0], rax
0x14000ea95  mov     r8, r15
0x14000ea98  mov     dword ptr [rsp+0F0h+var_B8], 1Ch
0x14000eaa0  lea     rax, [rbp+57h+var_70]
0x14000eaa4  mov     [rsp+0F0h+var_C0], rax
0x14000eaa9  mov     edx, 1
0x14000eaae  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x14000eab2  mov     ecx, 3
0x14000eab7  mov     [rsp+0F0h+Timeout], rdi
0x14000eabc  call    TdxGetAllParameters
0x14000eac1  test    eax, eax
0x14000eac3  js      loc_14000E8FD
0x14000eac9  cmp     dword ptr [rbp+57h+var_90+4], 4
0x14000eacd  jnz     short loc_14000EAEA
0x14000eacf  mov     ecx, [r13+8]
0x14000ead3  lea     rax, [rbp+57h+var_90]
0x14000ead7  mov     r9, rdi
0x14000eada  mov     [rsp+0F0h+var_C8], rax
0x14000eadf  mov     r8d, ebx
0x14000eae2  mov     rdx, r15
0x14000eae5  call    TdxCreateAndRegisterNetAddress
0x14000eaea  mov     dword ptr [rsp+58h], 8
0x14000eaf2  lea     rax, [rbp+57h+var_80]
0x14000eaf6  mov     qword ptr [rsp+0F0h+var_A0], rax
0x14000eafb  mov     r9d, 0Ah
0x14000eb01  mov     dword ptr [rsp+0F0h+var_A8], 8
0x14000eb09  lea     rax, [rbp+57h+var_90]
0x14000eb0d  mov     [rsp+0F0h+var_B0], rax
0x14000eb12  mov     r8, r15
0x14000eb15  mov     dword ptr [rsp+0F0h+var_B8], 1Ch
0x14000eb1d  lea     rax, [rbp+57h+var_70]
0x14000eb21  mov     [rsp+0F0h+var_C0], rax
0x14000eb26  mov     edx, 2
0x14000eb2b  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x14000eb2f  mov     ecx, 3
0x14000eb34  mov     [rsp+0F0h+Timeout], rdi
0x14000eb39  call    TdxGetAllParameters
0x14000eb3e  test    eax, eax
0x14000eb40  jns     short loc_14000EAC9
0x14000eb42  jmp     loc_14000E8FD
0x14000eb47  test    dword ptr [rcx+2Ch], 200h
0x14000eb4e  jz      loc_14000E801
0x14000eb54  mov     rcx, [rcx+18h]
0x14000eb58  lea     rax, [rbp+57h+P]
0x14000eb5c  mov     edx, 14h
0x14000eb61  mov     [rsp+0F0h+Timeout], rax
0x14000eb66  mov     r9, r15
0x14000eb69  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000eb70  call    WPP_SF_qq
0x14000eb75  jmp     loc_14000E801
0x14000eb7a  mov     rcx, rbx; RegistrationHandle
0x14000eb7d  call    cs:__imp_TdiDeregisterDeviceObject
0x14000eb84  nop     dword ptr [rax+rax+00h]
0x14000eb89  jmp     loc_14000E8FD
0x14000eb8e  mov     ecx, 3
  ... truncated ...
```
