# RootStartDeviceInterfaceByContext

- ea: `0x1400060d8`
- end: `0x140006388`
- name: `RootStartDeviceInterfaceByContext`
- size: `688`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x1400063d0`
- `0x14002bf50`

## callees

- `0x1400060d8`
- `0x140009798`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140006360`
- `ntoskrnl!ZwClose` at `0x140006360`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006161`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006161`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000634b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000634b`
- `ntoskrnl!ZwSetValueKey` at `0x1400062c4`
- `ntoskrnl!ZwSetValueKey` at `0x1400062ff`
- `ntoskrnl!ZwSetValueKey` at `0x1400062c4`
- `ntoskrnl!ZwSetValueKey` at `0x1400062ff`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006174`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140006174`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140006285`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140006285`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000633f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000633f`

## pseudocode

```c
__int64 __fastcall RootStartDeviceInterfaceByContext(__int64 a1, __int64 a2, char a3, char a4)
{
  __int64 v8; // rbx
  struct _FAST_MUTEX *v9; // r12
  NTSTATUS started; // ebx
  __int64 v11; // rcx
  int Data; // [rsp+20h] [rbp-50h]
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING v16; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+58h] [rbp-18h] BYREF
  void *DeviceInterfaceRegKey; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&ValueName.Length = 1703960;
  ValueName.Buffer = L"InstanceGuid";
  *(_QWORD *)&v16.Length = 1572886;
  v16.Buffer = L"UserDefined";
  v14 = 0;
  SymbolicLinkName = 0;
  DeviceInterfaceRegKey = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14001C0C8);
  KeEnterCriticalRegion();
  v9 = (struct _FAST_MUTEX *)(v8 + 24);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v8 + 24));
  if ( *(_DWORD *)(a2 + 48) == 4 )
  {
    started = -1073741130;
    goto LABEL_17;
  }
  if ( a4 && !*(_BYTE *)(a2 + 88) )
  {
LABEL_16:
    started = 0;
    goto LABEL_17;
  }
  if ( *(_BYTE *)(a2 + 72) )
  {
    started = VMBusDirectOfferStartInterface(v8, a2);
    goto LABEL_18;
  }
  started = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01033 + 616))(
              WdfDriverGlobals,
              a1,
              *(_QWORD *)(a2 + 32),
              a2 + 96);
  if ( started >= 0 )
  {
    if ( !a3
      || (started = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64 *))(WdfFunctions_01033 + 2464))(
                      WdfDriverGlobals,
                      0,
                      0,
                      &v14),
          started >= 0)
      && (started = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, __int64))(WdfFunctions_01033 + 632))(
                      WdfDriverGlobals,
                      a1,
                      *(_QWORD *)(a2 + 32),
                      a2 + 96,
                      v14),
          started >= 0)
      && ((*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 2472))(
            WdfDriverGlobals,
            v14,
            &SymbolicLinkName),
          started = IoOpenDeviceInterfaceRegistryKey(&SymbolicLinkName, 0xF003Fu, &DeviceInterfaceRegKey),
          started >= 0)
      && (started = ZwSetValueKey(DeviceInterfaceRegKey, &ValueName, 0, 3u, (PVOID)(*(_QWORD *)(a2 + 32) + 16LL), 0x10u),
          started >= 0)
      && ((v11 = *(_QWORD *)(a2 + 32), (*(_BYTE *)(v11 + 40) & 0x10) == 0)
       || (started = ZwSetValueKey(DeviceInterfaceRegKey, &v16, 0, 3u, (PVOID)(v11 + 60), 0x70u), started >= 0)) )
    {
      LOBYTE(Data) = 1;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64, int))(WdfFunctions_01033 + 624))(
        WdfDriverGlobals,
        a1,
        *(_QWORD *)(a2 + 32),
        a2 + 96,
        Data);
      goto LABEL_16;
    }
  }
LABEL_17:
  ExReleaseFastMutexUnsafe(v9);
  KeLeaveCriticalRegion();
LABEL_18:
  if ( DeviceInterfaceRegKey )
    ZwClose(DeviceInterfaceRegKey);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400060d8  mov     [rsp-28h+arg_0], rbx
0x1400060dd  mov     [rsp-28h+arg_10], rsi
0x1400060e2  push    rbp
0x1400060e3  push    rdi
0x1400060e4  push    r12
0x1400060e6  push    r14
0x1400060e8  push    r15
0x1400060ea  mov     rbp, rsp
0x1400060ed  sub     rsp, 70h
0x1400060f1  lea     rax, aInstanceguid; "InstanceGuid"
0x1400060f8  mov     qword ptr [rbp+ValueName.Length], 1A0018h
0x140006100  mov     [rbp+ValueName.Buffer], rax
0x140006104  xorps   xmm0, xmm0
0x140006107  lea     rax, aUserdefined; "UserDefined"
0x14000610e  mov     qword ptr [rbp+var_28.Length], 180016h
0x140006116  mov     [rbp+var_28.Buffer], rax
0x14000611a  mov     rdi, rdx
0x14000611d  mov     rax, cs:WdfFunctions_01033
0x140006124  mov     r15b, r8b
0x140006127  mov     r8, cs:off_14001C0C8
0x14000612e  mov     r14, rcx
0x140006131  mov     [rbp+var_40], 0
0x140006139  mov     rdx, rcx
0x14000613c  mov     rcx, cs:WdfDriverGlobals
0x140006143  mov     sil, r9b
0x140006146  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm0
0x14000614a  mov     [rbp+DeviceInterfaceRegKey], 0
0x140006152  mov     rax, [rax+650h]
0x140006159  call    _guard_dispatch_icall
0x14000615e  mov     rbx, rax
0x140006161  call    cs:__imp_KeEnterCriticalRegion
0x140006168  nop     dword ptr [rax+rax+00h]
0x14000616d  lea     r12, [rbx+18h]
0x140006171  mov     rcx, r12; FastMutex
0x140006174  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000617b  nop     dword ptr [rax+rax+00h]
0x140006180  cmp     dword ptr [rdi+30h], 4
0x140006184  jnz     short loc_140006190
0x140006186  mov     ebx, 0C00002B6h
0x14000618b  jmp     loc_14000633C
0x140006190  test    sil, sil
0x140006193  jz      short loc_14000619F
0x140006195  cmp     byte ptr [rdi+58h], 0
0x140006199  jz      loc_14000633A
0x14000619f  cmp     byte ptr [rdi+48h], 0
0x1400061a3  jz      short loc_1400061B7
0x1400061a5  mov     rdx, rdi
0x1400061a8  mov     rcx, rbx
0x1400061ab  call    VMBusDirectOfferStartInterface
0x1400061b0  mov     ebx, eax
0x1400061b2  jmp     loc_140006357
0x1400061b7  mov     rax, cs:WdfFunctions_01033
0x1400061be  lea     rsi, [rdi+60h]
0x1400061c2  mov     r8, [rdi+20h]
0x1400061c6  mov     r9, rsi
0x1400061c9  mov     rcx, cs:WdfDriverGlobals
0x1400061d0  mov     rdx, r14
0x1400061d3  mov     rax, [rax+268h]
0x1400061da  call    _guard_dispatch_icall
0x1400061df  mov     ebx, eax
0x1400061e1  test    eax, eax
0x1400061e3  js      loc_14000633C
0x1400061e9  test    r15b, r15b
0x1400061ec  jz      loc_140006311
0x1400061f2  mov     rax, cs:WdfFunctions_01033
0x1400061f9  lea     r9, [rbp+var_40]
0x1400061fd  mov     rcx, cs:WdfDriverGlobals
0x140006204  xor     r8d, r8d
0x140006207  xor     edx, edx
0x140006209  mov     rax, [rax+9A0h]
0x140006210  call    _guard_dispatch_icall
0x140006215  mov     ebx, eax
0x140006217  test    eax, eax
0x140006219  js      loc_14000633C
0x14000621f  mov     rcx, [rbp+var_40]
0x140006223  mov     r9, rsi
0x140006226  mov     rax, cs:WdfFunctions_01033
0x14000622d  mov     rdx, r14
0x140006230  mov     r8, [rdi+20h]
0x140006234  mov     [rsp+70h+Data], rcx
0x140006239  mov     rcx, cs:WdfDriverGlobals
0x140006240  mov     rax, [rax+278h]
0x140006247  call    _guard_dispatch_icall
0x14000624c  mov     ebx, eax
0x14000624e  test    eax, eax
0x140006250  js      loc_14000633C
0x140006256  mov     rax, cs:WdfFunctions_01033
0x14000625d  lea     r8, [rbp+SymbolicLinkName]
0x140006261  mov     rdx, [rbp+var_40]
0x140006265  mov     rcx, cs:WdfDriverGlobals
0x14000626c  mov     rax, [rax+9A8h]
0x140006273  call    _guard_dispatch_icall
0x140006278  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x14000627c  mov     edx, 0F003Fh; DesiredAccess
0x140006281  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x140006285  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x14000628c  nop     dword ptr [rax+rax+00h]
0x140006291  mov     ebx, eax
0x140006293  test    eax, eax
0x140006295  js      loc_14000633C
0x14000629b  mov     rax, [rdi+20h]
0x14000629f  lea     rdx, [rbp+ValueName]; ValueName
0x1400062a3  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x1400062a7  add     rax, 10h
0x1400062ab  mov     r15d, 3
0x1400062b1  mov     [rsp+70h+DataSize], 10h; DataSize
0x1400062b9  mov     r9d, r15d; Type
0x1400062bc  mov     [rsp+70h+Data], rax; Data
0x1400062c1  xor     r8d, r8d; TitleIndex
0x1400062c4  call    cs:__imp_ZwSetValueKey
0x1400062cb  nop     dword ptr [rax+rax+00h]
0x1400062d0  mov     ebx, eax
0x1400062d2  test    eax, eax
0x1400062d4  js      short loc_14000633C
0x1400062d6  mov     rcx, [rdi+20h]
0x1400062da  test    byte ptr [rcx+28h], 10h
0x1400062de  jz      short loc_140006311
0x1400062e0  lea     rax, [rcx+3Ch]
0x1400062e4  mov     [rsp+70h+DataSize], 70h ; 'p'; DataSize
0x1400062ec  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x1400062f0  lea     rdx, [rbp+var_28]; ValueName
0x1400062f4  mov     r9d, r15d; Type
0x1400062f7  mov     [rsp+70h+Data], rax; Data
0x1400062fc  xor     r8d, r8d; TitleIndex
0x1400062ff  call    cs:__imp_ZwSetValueKey
0x140006306  nop     dword ptr [rax+rax+00h]
0x14000630b  mov     ebx, eax
0x14000630d  test    eax, eax
0x14000630f  js      short loc_14000633C
0x140006311  mov     rax, cs:WdfFunctions_01033
0x140006318  mov     r9, rsi
0x14000631b  mov     r8, [rdi+20h]
0x14000631f  mov     rdx, r14
0x140006322  mov     rcx, cs:WdfDriverGlobals
0x140006329  mov     byte ptr [rsp+70h+Data], 1
0x14000632e  mov     rax, [rax+270h]
0x140006335  call    _guard_dispatch_icall
0x14000633a  xor     ebx, ebx
0x14000633c  mov     rcx, r12; FastMutex
0x14000633f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140006346  nop     dword ptr [rax+rax+00h]
0x14000634b  call    cs:__imp_KeLeaveCriticalRegion
0x140006352  nop     dword ptr [rax+rax+00h]
0x140006357  mov     rcx, [rbp+DeviceInterfaceRegKey]; Handle
0x14000635b  test    rcx, rcx
0x14000635e  jz      short loc_14000636C
0x140006360  call    cs:__imp_ZwClose
0x140006367  nop     dword ptr [rax+rax+00h]
0x14000636c  lea     r11, [rsp+70h+var_s0]
0x140006371  mov     eax, ebx
0x140006373  mov     rbx, [r11+30h]
0x140006377  mov     rsi, [r11+40h]
0x14000637b  mov     rsp, r11
0x14000637e  pop     r15
0x140006380  pop     r14
0x140006382  pop     r12
0x140006384  pop     rdi
0x140006385  pop     rbp
0x140006386  retn
```
