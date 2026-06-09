# p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::Initialize(void *)

- ea: `0x18002dd30`
- end: `0x18002de8d`
- name: `?Initialize@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@SAJPEAX@Z`
- size: `349`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004120`
- `0x18001c75c`
- `0x18002dd30`
- `0x18002e4d0`
- `0x18002eb5c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ddaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ddaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd9b`
- `vmvirtio!VirtioEnableQueues` at `0x18002de06`
- `vmvirtio!VirtioEnableQueues` at `0x18002de06`
- `vmvirtio!VirtioCreateInstance` at `0x18002dde0`
- `vmvirtio!VirtioCreateInstance` at `0x18002dde0`

## string_xrefs

- `0x18002de52`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`
- `0x18002de66`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`
- `0x18002de7a`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::Initialize(__int64 a1)
{
  int v2; // eax
  _QWORD *v3; // rdi
  DWORD LastError; // ebx
  struct _VIRTIO_INSTANCE **v5; // rdx
  __int64 v6; // rbx
  int Instance; // eax
  int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = 0;
  v2 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::QueryInterface(
         a1,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v12);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
        (const char *)(unsigned int)v2,
        v11);
    v3 = (_QWORD *)(a1 + 136);
    if ( *(_QWORD *)(a1 + 136) )
    {
      v13 = *(_QWORD *)(a1 + 136);
      LastError = GetLastError();
      p9fs::details::VirtioDeleteInstance((p9fs::details *)&v13, v5);
      SetLastError(LastError);
    }
    *v3 = 0;
    v6 = v12;
    Instance = VirtioCreateInstance(v12, 4169, 0x200000001LL, 0);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
        (const char *)(unsigned int)Instance,
        0);
    v8 = VirtioEnableQueues(*v3, 1, 1, p9fs::Plan9VirtioDevice::ProcessVirtioWork);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
        (const char *)(unsigned int)v8,
        a1);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x20,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18002dd30  mov     r11, rsp
0x18002dd33  mov     [r11+10h], rbx
0x18002dd37  mov     [r11+18h], rsi
0x18002dd3b  push    rdi
0x18002dd3c  sub     rsp, 50h
0x18002dd40  mov     rax, cs:__security_cookie
0x18002dd47  xor     rax, rsp
0x18002dd4a  mov     [rsp+58h+var_10], rax
0x18002dd4f  mov     rsi, rcx
0x18002dd52  mov     dword ptr [rsp+58h+var_28+4], 2
0x18002dd5a  mov     dword ptr [rsp+58h+var_28], 1
0x18002dd62  mov     qword ptr [r11-20h], 0
0x18002dd6a  lea     r8, [r11-20h]
0x18002dd6e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002dd75  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIVmFiovGuestMemoryAccess@@UIVmFiovGuestMsiAccess@@UIVmFiovGuestMemoryFastNotification@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IVmFiovGuestMemoryAccess,IVmFiovGuestMsiAccess,IVmFiovGuestMemoryFastNotification>::QueryInterface(_GUID const &,void * *)
0x18002dd7a  mov     rcx, [rsp+58h]; this
0x18002dd7f  test    eax, eax
0x18002dd81  js      loc_18002DE4F
0x18002dd87  lea     rdi, [rsi+88h]
0x18002dd8e  mov     rax, [rdi]
0x18002dd91  test    rax, rax
0x18002dd94  jz      short loc_18002DDB6
0x18002dd96  mov     [rsp+58h+var_18], rax
0x18002dd9b  call    cs:__imp_GetLastError
0x18002dda1  mov     ebx, eax
0x18002dda3  lea     rcx, [rsp+58h+var_18]; this
0x18002dda8  call    ?VirtioDeleteInstance@details@p9fs@@YAXAEAPEAU_VIRTIO_INSTANCE@@@Z; p9fs::details::VirtioDeleteInstance(_VIRTIO_INSTANCE * &)
0x18002ddad  mov     ecx, ebx; dwErrCode
0x18002ddaf  call    cs:__imp_SetLastError
0x18002ddb5  nop
0x18002ddb6  mov     qword ptr [rdi], 0
0x18002ddbd  mov     edx, 1049h
0x18002ddc2  mov     [rsp+58h+var_30], rdi
0x18002ddc7  mov     qword ptr [rsp+58h+var_38], 0; int
0x18002ddd0  xor     r9d, r9d
0x18002ddd3  mov     r8, [rsp+58h+var_28]
0x18002ddd8  mov     rbx, [rsp+58h+var_20]
0x18002dddd  mov     rcx, rbx
0x18002dde0  call    cs:__imp_VirtioCreateInstance
0x18002dde6  mov     rcx, [rsp+58h]; this
0x18002ddeb  test    eax, eax
0x18002dded  js      short loc_18002DE63
0x18002ddef  mov     edx, 1
0x18002ddf4  mov     qword ptr [rsp+58h+var_38], rsi; int
0x18002ddf9  lea     r9, ?ProcessVirtioWork@Plan9VirtioDevice@p9fs@@CAJPEAXGPEAU_VIRTIO_MEMORY_STREAM@@PEAK@Z; p9fs::Plan9VirtioDevice::ProcessVirtioWork(void *,ushort,_VIRTIO_MEMORY_STREAM *,ulong *)
0x18002de00  mov     r8d, edx
0x18002de03  mov     rcx, [rdi]
0x18002de06  call    cs:__imp_VirtioEnableQueues
0x18002de0c  mov     rcx, [rsp+58h]; this
0x18002de11  test    eax, eax
0x18002de13  js      short loc_18002DE77
0x18002de15  test    rbx, rbx
0x18002de18  jz      short loc_18002DE2A
0x18002de1a  mov     rax, [rbx]
0x18002de1d  mov     rcx, rbx
0x18002de20  mov     rax, [rax+10h]
0x18002de24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de29  nop
0x18002de2a  xor     eax, eax
0x18002de2c  jmp     short loc_18002DE32
0x18002de2e  mov     eax, dword ptr [rsp+58h+var_28]
0x18002de32  mov     rcx, [rsp+58h+var_10]
0x18002de37  xor     rcx, rsp; StackCookie
0x18002de3a  call    __security_check_cookie
0x18002de3f  mov     rbx, [rsp+58h+arg_8]
0x18002de44  mov     rsi, [rsp+58h+arg_10]
0x18002de49  add     rsp, 50h
0x18002de4d  pop     rdi
0x18002de4e  retn
0x18002de4f  mov     r9d, eax; char *
0x18002de52  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002de59  mov     edx, 60h ; '`'; void *
0x18002de5e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002de63  mov     r9d, eax; char *
0x18002de66  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002de6d  mov     edx, 62h ; 'b'; void *
0x18002de72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002de77  mov     r9d, eax; char *
0x18002de7a  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002de81  mov     edx, 65h ; 'e'; void *
0x18002de86  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
