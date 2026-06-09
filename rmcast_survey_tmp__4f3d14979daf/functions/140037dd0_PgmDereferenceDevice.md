# PgmDereferenceDevice

- ea: `0x140037dd0`
- end: `0x140037f56`
- name: `PgmDereferenceDevice`
- size: `390`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000702c`
- `0x14000b0b0`

## callees

- `0x140005068`
- `0x1400052e4`
- `0x14001cdf0`
- `0x140037dd0`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140037e94`
- `ntoskrnl!KeStackAttachProcess` at `0x140037e94`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140037ee2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140037ee2`
- `ntoskrnl!ZwClose` at `0x140037ebc`
- `ntoskrnl!ZwClose` at `0x140037ebc`
- `ntoskrnl!IoDeleteDevice` at `0x140037f20`
- `ntoskrnl!IoDeleteDevice` at `0x140037f20`
- `ntoskrnl!ObfDereferenceObject` at `0x140037eac`
- `ntoskrnl!ObfDereferenceObject` at `0x140037eac`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037e77`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037e77`
- `TDI!TdiDeregisterDeviceObject` at `0x140037e22`
- `TDI!TdiDeregisterDeviceObject` at `0x140037e22`

## pseudocode

```c
void __fastcall PgmDereferenceDevice(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  void *Timer_high; // rcx
  unsigned int v7; // eax
  char v8; // di
  struct _KAPC_STATE ApcState; // [rsp+28h] [rbp-40h] BYREF

  v4 = pgPgmDevice;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( (*(_DWORD *)(pgPgmDevice + 16))-- == 1 )
  {
    Timer_high = *(void **)(v4 + 64);
    if ( Timer_high )
    {
      v7 = TdiDeregisterDeviceObject(Timer_high);
      a2 = 3221225472LL;
      Timer_high = (void *)(v7 & 0xC0000000);
      if ( (_DWORD)Timer_high == -1073741824 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = (void *)HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( ((unsigned __int8)Timer_high & 2) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, v7);
      }
      *(_QWORD *)(v4 + 64) = 0;
    }
    if ( *(_QWORD *)(v4 + 40) )
    {
      if ( (PRKPROCESS)PsGetCurrentProcess(Timer_high, a2, a3, a4) == PgmStaticConfig )
      {
        v8 = 0;
      }
      else
      {
        KeStackAttachProcess(PgmStaticConfig, &ApcState);
        v8 = 1;
      }
      ObfDereferenceObject(*(PVOID *)(v4 + 56));
      ZwClose(*(HANDLE *)(v4 + 40));
      *(_QWORD *)(v4 + 56) = 0;
      *(_QWORD *)(v4 + 40) = 0;
      if ( v8 )
        KeUnstackDetachProcess(&ApcState);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, pgPgmDevice);
    IoDeleteDevice(*(PDEVICE_OBJECT *)v4);
    pgPgmDevice = 0;
  }
}

```

## disassembly

```asm
0x140037dd0  mov     [rsp+arg_0], rbx
0x140037dd5  mov     [rsp+arg_8], rdi
0x140037dda  push    r14
0x140037ddc  sub     rsp, 60h
0x140037de0  mov     rax, cs:__security_cookie
0x140037de7  xor     rax, rsp
0x140037dea  mov     [rsp+68h+var_10], rax
0x140037def  mov     rbx, cs:pgPgmDevice
0x140037df6  xorps   xmm0, xmm0
0x140037df9  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink], xmm0
0x140037dfe  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink+10h], xmm0
0x140037e03  movups  xmmword ptr [rsp+68h+ApcState.Process], xmm0
0x140037e08  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x140037e0c  jnz     loc_140037F37
0x140037e12  mov     rcx, [rbx+40h]; RegistrationHandle
0x140037e16  lea     r14, WPP_GLOBAL_Control
0x140037e1d  test    rcx, rcx
0x140037e20  jz      short loc_140037E70
0x140037e22  call    cs:__imp_TdiDeregisterDeviceObject
0x140037e29  nop     dword ptr [rax+rax+00h]
0x140037e2e  mov     edx, 0C0000000h
0x140037e33  mov     ecx, eax
0x140037e35  and     ecx, edx
0x140037e37  cmp     ecx, edx
0x140037e39  jnz     short loc_140037E68
0x140037e3b  mov     r10, cs:WPP_GLOBAL_Control
0x140037e42  cmp     r10, r14
0x140037e45  jz      short loc_140037E68
0x140037e47  mov     ecx, [r10+2Ch]
0x140037e4b  test    cl, 2
0x140037e4e  jz      short loc_140037E68
0x140037e50  mov     rcx, [r10+18h]
0x140037e54  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037e5b  mov     edx, 1Ch
0x140037e60  mov     r9d, eax
0x140037e63  call    WPP_SF_d
0x140037e68  mov     qword ptr [rbx+40h], 0
0x140037e70  cmp     qword ptr [rbx+28h], 0
0x140037e75  jz      short loc_140037EEE
0x140037e77  call    cs:__imp_PsGetCurrentProcess
0x140037e7e  nop     dword ptr [rax+rax+00h]
0x140037e83  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140037e8a  cmp     rax, rcx
0x140037e8d  jz      short loc_140037EA5
0x140037e8f  lea     rdx, [rsp+68h+ApcState]; ApcState
0x140037e94  call    cs:__imp_KeStackAttachProcess
0x140037e9b  nop     dword ptr [rax+rax+00h]
0x140037ea0  mov     dil, 1
0x140037ea3  jmp     short loc_140037EA8
0x140037ea5  xor     dil, dil
0x140037ea8  mov     rcx, [rbx+38h]; Object
0x140037eac  call    cs:__imp_ObfDereferenceObject
0x140037eb3  nop     dword ptr [rax+rax+00h]
0x140037eb8  mov     rcx, [rbx+28h]; Handle
0x140037ebc  call    cs:__imp_ZwClose
0x140037ec3  nop     dword ptr [rax+rax+00h]
0x140037ec8  mov     qword ptr [rbx+38h], 0
0x140037ed0  mov     qword ptr [rbx+28h], 0
0x140037ed8  test    dil, dil
0x140037edb  jz      short loc_140037EEE
0x140037edd  lea     rcx, [rsp+68h+ApcState]; ApcState
0x140037ee2  call    cs:__imp_KeUnstackDetachProcess
0x140037ee9  nop     dword ptr [rax+rax+00h]
0x140037eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ef5  cmp     rcx, r14
0x140037ef8  jz      short loc_140037F1D
0x140037efa  mov     eax, [rcx+2Ch]
0x140037efd  test    al, 10h
0x140037eff  jz      short loc_140037F1D
0x140037f01  mov     r9, cs:pgPgmDevice
0x140037f08  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037f0f  mov     rcx, [rcx+18h]
0x140037f13  mov     edx, 1Dh
0x140037f18  call    WPP_SF_q
0x140037f1d  mov     rcx, [rbx]; DeviceObject
0x140037f20  call    cs:__imp_IoDeleteDevice
0x140037f27  nop     dword ptr [rax+rax+00h]
0x140037f2c  mov     cs:pgPgmDevice, 0
0x140037f37  mov     rcx, [rsp+68h+var_10]
0x140037f3c  xor     rcx, rsp; StackCookie
0x140037f3f  call    __security_check_cookie
0x140037f44  mov     rbx, [rsp+68h+arg_0]
0x140037f49  mov     rdi, [rsp+68h+arg_8]
0x140037f4e  add     rsp, 60h
0x140037f52  pop     r14
0x140037f54  retn
```
