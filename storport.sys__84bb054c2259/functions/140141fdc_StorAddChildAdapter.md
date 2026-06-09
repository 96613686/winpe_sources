# StorAddChildAdapter

- ea: `0x140141fdc`
- end: `0x1401421b5`
- name: `StorAddChildAdapter`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140054e60`

## callees

- `0x14003c528`
- `0x140044c10`
- `0x14009d8dc`
- `0x140141fdc`
- `0x14014b400`
- `0x140190a30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140142078`
- `ntoskrnl!RtlInitUnicodeString` at `0x140142078`
- `ntoskrnl!IoDeleteDevice` at `0x140142143`
- `ntoskrnl!IoDeleteDevice` at `0x140142143`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401420cb`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401420cb`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14014217b`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14014217b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140142133`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140142133`
- `ntoskrnl!IoCreateDevice` at `0x1401420a9`
- `ntoskrnl!IoCreateDevice` at `0x1401420a9`

## pseudocode

```c
__int64 __fastcall StorAddChildAdapter(__int64 a1, __int64 a2)
{
  __int64 CommonAdapterMiniport; // rax
  __int64 v5; // rsi
  void *DeviceExtension; // rdi
  NTSTATUS inited; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  unsigned int v12; // ebx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v13; // rcx
  signed __int32 v15[8]; // [rsp+0h] [rbp-79h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  wchar_t pszDest[40]; // [rsp+60h] [rbp-19h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  if ( !a2 )
    return (unsigned int)-1056964602;
  CommonAdapterMiniport = StorGetCommonAdapterMiniport(a1);
  v5 = CommonAdapterMiniport;
  if ( !CommonAdapterMiniport || (*(_DWORD *)(CommonAdapterMiniport + 248) & 0x280) != 0 )
    return (unsigned int)-1056964602;
  DeviceExtension = 0;
  inited = RtlStringCbPrintfW(
             pszDest,
             0x4Cu,
             L"\\Device\\STORPORT_CA%d",
             (unsigned int)_InterlockedIncrement(&StorChildAdapterNumber));
  if ( inited >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, pszDest);
    inited = IoCreateDevice(
               *(PDRIVER_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL),
               0x50u,
               &DestinationString,
               0x22u,
               0,
               0,
               &DeviceObject);
    if ( inited >= 0 )
    {
      DeviceExtension = DeviceObject->DeviceExtension;
      CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x6D526152u);
      *((_QWORD *)DeviceExtension + 8) = CacheAwareRundownProtection;
      if ( CacheAwareRundownProtection )
      {
        *(_DWORD *)DeviceExtension = 1396916560;
        *((_DWORD *)DeviceExtension + 15) = 2;
        *((_QWORD *)DeviceExtension + 2) = *(_QWORD *)(a1 + 16);
        *((_QWORD *)DeviceExtension + 4) = DeviceObject;
        *((_QWORD *)DeviceExtension + 9) = a1;
        inited = RaSaveDriverInitData(*(_QWORD *)(a1 + 16), a2);
        if ( inited >= 0 )
        {
          v12 = 0;
          *(_QWORD *)(v5 + 384) = DeviceObject;
          _InterlockedOr(v15, 0);
          *(_DWORD *)(v5 + 248) |= 0x180u;
          DeviceObject->Flags &= ~0x80u;
          IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(a1 + 32), BusRelations);
          return v12;
        }
      }
      else
      {
        inited = -1073741801;
      }
    }
  }
  v12 = RaidNtStatusToStorStatus((unsigned int)inited, v8, v9, v10);
  if ( v12 && DeviceExtension )
  {
    v13 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)DeviceExtension + 8);
    if ( v13 )
      ExFreeCacheAwareRundownProtection(v13);
    IoDeleteDevice(DeviceObject);
  }
  return v12;
}

```

## disassembly

```asm
0x140141fdc  mov     [rsp-8+arg_10], rbx
0x140141fe1  mov     [rsp-8+arg_18], rsi
0x140141fe6  push    rbp
0x140141fe7  push    rdi
0x140141fe8  push    r14
0x140141fea  lea     rbp, [rsp-47h]
0x140141fef  sub     rsp, 0C0h
0x140141ff6  mov     rax, cs:__security_cookie
0x140141ffd  xor     rax, rsp
0x140142000  mov     [rbp+57h+var_20], rax
0x140142004  mov     [rbp+57h+var_90], 0
0x14014200c  xorps   xmm0, xmm0
0x14014200f  mov     rbx, rdx
0x140142012  mov     r14, rcx
0x140142015  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140142019  test    rdx, rdx
0x14014201c  jz      loc_140142189
0x140142022  call    StorGetCommonAdapterMiniport
0x140142027  mov     rsi, rax
0x14014202a  test    rax, rax
0x14014202d  jz      loc_140142189
0x140142033  test    dword ptr [rax+0F8h], 280h
0x14014203d  jnz     loc_140142189
0x140142043  xor     edi, edi
0x140142045  lea     r9d, [rdi+1]
0x140142049  lock xadd cs:StorChildAdapterNumber, r9d
0x140142052  inc     r9d
0x140142055  lea     r8, aDeviceStorport_0; "\\Device\\STORPORT_CA%d"
0x14014205c  lea     edx, [rdi+4Ch]; cbDest
0x14014205f  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140142063  call    RtlStringCbPrintfW
0x140142068  test    eax, eax
0x14014206a  js      loc_140142118
0x140142070  lea     rdx, [rbp+57h+pszDest]; SourceString
0x140142074  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140142078  call    cs:__imp_RtlInitUnicodeString
0x14014207f  nop     dword ptr [rax+rax+00h]
0x140142084  mov     rcx, [r14+10h]
0x140142088  lea     rax, [rbp+57h+var_90]
0x14014208c  mov     [rsp+0D0h+DeviceObject], rax; DeviceObject
0x140142091  lea     r9d, [rdi+22h]; DeviceType
0x140142095  mov     [rsp+0D0h+Exclusive], dil; Exclusive
0x14014209a  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14014209e  lea     edx, [rdi+50h]; DeviceExtensionSize
0x1401420a1  mov     [rsp+0D0h+DeviceCharacteristics], edi; DeviceCharacteristics
0x1401420a5  mov     rcx, [rcx+8]; DriverObject
0x1401420a9  call    cs:__imp_IoCreateDevice
0x1401420b0  nop     dword ptr [rax+rax+00h]
0x1401420b5  test    eax, eax
0x1401420b7  js      short loc_140142118
0x1401420b9  mov     rax, [rbp+57h+var_90]
0x1401420bd  mov     edx, 6D526152h; PoolTag
0x1401420c2  mov     ecx, 200h; PoolType
0x1401420c7  mov     rdi, [rax+40h]
0x1401420cb  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401420d2  nop     dword ptr [rax+rax+00h]
0x1401420d7  mov     [rdi+40h], rax
0x1401420db  test    rax, rax
0x1401420de  jnz     short loc_1401420E7
0x1401420e0  mov     eax, 0C0000017h
0x1401420e5  jmp     short loc_140142118
0x1401420e7  mov     dword ptr [rdi], 53434150h
0x1401420ed  mov     rdx, rbx
0x1401420f0  mov     dword ptr [rdi+3Ch], 2
0x1401420f7  mov     rax, [r14+10h]
0x1401420fb  mov     [rdi+10h], rax
0x1401420ff  mov     rax, [rbp+57h+var_90]
0x140142103  mov     [rdi+20h], rax
0x140142107  mov     [rdi+48h], r14
0x14014210b  mov     rcx, [r14+10h]
0x14014210f  call    RaSaveDriverInitData
0x140142114  test    eax, eax
0x140142116  jns     short loc_140142151
0x140142118  mov     ecx, eax
0x14014211a  call    RaidNtStatusToStorStatus
0x14014211f  mov     ebx, eax
0x140142121  test    eax, eax
0x140142123  jz      short loc_14014218E
0x140142125  test    rdi, rdi
0x140142128  jz      short loc_14014218E
0x14014212a  mov     rcx, [rdi+40h]; RunRefCacheAware
0x14014212e  test    rcx, rcx
0x140142131  jz      short loc_14014213F
0x140142133  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14014213a  nop     dword ptr [rax+rax+00h]
0x14014213f  mov     rcx, [rbp+57h+var_90]; DeviceObject
0x140142143  call    cs:__imp_IoDeleteDevice
0x14014214a  nop     dword ptr [rax+rax+00h]
0x14014214f  jmp     short loc_14014218E
0x140142151  mov     rax, [rbp+57h+var_90]
0x140142155  xor     ebx, ebx
0x140142157  mov     [rsi+180h], rax
0x14014215e  lock or [rsp+0D0h+var_D0], ebx
0x140142162  or      dword ptr [rsi+0F8h], 180h
0x14014216c  xor     edx, edx; Type
0x14014216e  mov     rax, [rbp+57h+var_90]
0x140142172  btr     dword ptr [rax+30h], 7
0x140142177  mov     rcx, [r14+20h]; DeviceObject
0x14014217b  call    cs:__imp_IoInvalidateDeviceRelations
0x140142182  nop     dword ptr [rax+rax+00h]
0x140142187  jmp     short loc_14014218E
0x140142189  mov     ebx, 0C1000006h
0x14014218e  mov     eax, ebx
0x140142190  mov     rcx, [rbp+57h+var_20]
0x140142194  xor     rcx, rsp; StackCookie
0x140142197  call    __security_check_cookie
0x14014219c  lea     r11, [rsp+0D0h+var_10]
0x1401421a4  mov     rbx, [r11+30h]
0x1401421a8  mov     rsi, [r11+38h]
0x1401421ac  mov     rsp, r11
0x1401421af  pop     r14
0x1401421b1  pop     rdi
0x1401421b2  pop     rbp
0x1401421b3  retn
```
