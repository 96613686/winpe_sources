# PgmDereferenceDevice

- ea: `0x140037e20`
- end: `0x140037fa6`
- name: `PgmDereferenceDevice`
- size: `390`
- prototype: ``
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
- `0x140037e20`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140037ee4`
- `ntoskrnl!KeStackAttachProcess` at `0x140037ee4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140037f32`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140037f32`
- `ntoskrnl!ZwClose` at `0x140037f0c`
- `ntoskrnl!ZwClose` at `0x140037f0c`
- `ntoskrnl!IoDeleteDevice` at `0x140037f70`
- `ntoskrnl!IoDeleteDevice` at `0x140037f70`
- `ntoskrnl!ObfDereferenceObject` at `0x140037efc`
- `ntoskrnl!ObfDereferenceObject` at `0x140037efc`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037ec7`
- `ntoskrnl!PsGetCurrentProcess` at `0x140037ec7`
- `TDI!TdiDeregisterDeviceObject` at `0x140037e72`
- `TDI!TdiDeregisterDeviceObject` at `0x140037e72`

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
0x140037e20  mov     [rsp+arg_0], rbx
0x140037e25  mov     [rsp+arg_8], rdi
0x140037e2a  push    r14
0x140037e2c  sub     rsp, 60h
0x140037e30  mov     rax, cs:__security_cookie
0x140037e37  xor     rax, rsp
0x140037e3a  mov     [rsp+68h+var_10], rax
0x140037e3f  mov     rbx, cs:pgPgmDevice
0x140037e46  xorps   xmm0, xmm0
0x140037e49  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink], xmm0
0x140037e4e  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink+10h], xmm0
0x140037e53  movups  xmmword ptr [rsp+68h+ApcState.Process], xmm0
0x140037e58  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x140037e5c  jnz     loc_140037F87
0x140037e62  mov     rcx, [rbx+40h]; RegistrationHandle
0x140037e66  lea     r14, WPP_GLOBAL_Control
0x140037e6d  test    rcx, rcx
0x140037e70  jz      short loc_140037EC0
0x140037e72  call    cs:__imp_TdiDeregisterDeviceObject
0x140037e79  nop     dword ptr [rax+rax+00h]
0x140037e7e  mov     edx, 0C0000000h
0x140037e83  mov     ecx, eax
0x140037e85  and     ecx, edx
0x140037e87  cmp     ecx, edx
0x140037e89  jnz     short loc_140037EB8
0x140037e8b  mov     r10, cs:WPP_GLOBAL_Control
0x140037e92  cmp     r10, r14
0x140037e95  jz      short loc_140037EB8
0x140037e97  mov     ecx, [r10+2Ch]
0x140037e9b  test    cl, 2
0x140037e9e  jz      short loc_140037EB8
0x140037ea0  mov     rcx, [r10+18h]
0x140037ea4  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037eab  mov     edx, 1Ch
0x140037eb0  mov     r9d, eax
0x140037eb3  call    WPP_SF_d
0x140037eb8  mov     qword ptr [rbx+40h], 0
0x140037ec0  cmp     qword ptr [rbx+28h], 0
0x140037ec5  jz      short loc_140037F3E
0x140037ec7  call    cs:__imp_PsGetCurrentProcess
0x140037ece  nop     dword ptr [rax+rax+00h]
0x140037ed3  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140037eda  cmp     rax, rcx
0x140037edd  jz      short loc_140037EF5
0x140037edf  lea     rdx, [rsp+68h+ApcState]; ApcState
0x140037ee4  call    cs:__imp_KeStackAttachProcess
0x140037eeb  nop     dword ptr [rax+rax+00h]
0x140037ef0  mov     dil, 1
0x140037ef3  jmp     short loc_140037EF8
0x140037ef5  xor     dil, dil
0x140037ef8  mov     rcx, [rbx+38h]; Object
0x140037efc  call    cs:__imp_ObfDereferenceObject
0x140037f03  nop     dword ptr [rax+rax+00h]
0x140037f08  mov     rcx, [rbx+28h]; Handle
0x140037f0c  call    cs:__imp_ZwClose
0x140037f13  nop     dword ptr [rax+rax+00h]
0x140037f18  mov     qword ptr [rbx+38h], 0
0x140037f20  mov     qword ptr [rbx+28h], 0
0x140037f28  test    dil, dil
0x140037f2b  jz      short loc_140037F3E
0x140037f2d  lea     rcx, [rsp+68h+ApcState]; ApcState
0x140037f32  call    cs:__imp_KeUnstackDetachProcess
0x140037f39  nop     dword ptr [rax+rax+00h]
0x140037f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037f45  cmp     rcx, r14
0x140037f48  jz      short loc_140037F6D
0x140037f4a  mov     eax, [rcx+2Ch]
0x140037f4d  test    al, 10h
0x140037f4f  jz      short loc_140037F6D
0x140037f51  mov     r9, cs:pgPgmDevice
0x140037f58  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140037f5f  mov     rcx, [rcx+18h]
0x140037f63  mov     edx, 1Dh
0x140037f68  call    WPP_SF_q
0x140037f6d  mov     rcx, [rbx]; DeviceObject
0x140037f70  call    cs:__imp_IoDeleteDevice
0x140037f77  nop     dword ptr [rax+rax+00h]
0x140037f7c  mov     cs:pgPgmDevice, 0
0x140037f87  mov     rcx, [rsp+68h+var_10]
0x140037f8c  xor     rcx, rsp; StackCookie
0x140037f8f  call    __security_check_cookie
0x140037f94  mov     rbx, [rsp+68h+arg_0]
0x140037f99  mov     rdi, [rsp+68h+arg_8]
0x140037f9e  add     rsp, 60h
0x140037fa2  pop     r14
0x140037fa4  retn
```
