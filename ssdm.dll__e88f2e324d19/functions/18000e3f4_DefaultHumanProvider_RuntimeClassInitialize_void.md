# DefaultHumanProvider::RuntimeClassInitialize(void)

- ea: `0x18000e3f4`
- end: `0x18000e45f`
- name: `?RuntimeClassInitialize@DefaultHumanProvider@@QEAAJXZ`
- size: `107`
- prototype: `int(DefaultHumanProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a3d0`

## callees

- `0x180007484`
- `0x18000e3f4`
- `0x18000e468`
- `0x18000e7e4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000e402`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000e402`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000e435`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000e435`

## string_xrefs

- `0x18000e44c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DefaultHumanProvider::RuntimeClassInitialize(DefaultHumanProvider *this)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // r8d
  wil::details::in1diag3 *v5; // rcx
  const char *v6; // r9
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = RoInitialize(1);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x14F2,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        (const char *)(unsigned int)v2,
        v8);
    v3 = DefaultHumanProvider::StartMonitoringIpdChange(this);
    v5 = retaddr;
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x10, v4, (const char *)(unsigned int)v3, v8);
    RoUninitialize(v5);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12,
                           (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\defaulthumanprovider.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000e3f4  push    rbx; int
0x18000e3f6  sub     rsp, 20h
0x18000e3fa  mov     rbx, rcx
0x18000e3fd  mov     ecx, 1
0x18000e402  call    cs:__imp_RoInitialize
0x18000e408  mov     rcx, [rsp+28h]; this
0x18000e40d  test    eax, eax
0x18000e40f  js      short loc_18000E449
0x18000e411  mov     byte ptr [rsp+28h+arg_8], 1
0x18000e416  mov     rcx, rbx; this
0x18000e419  call    ?StartMonitoringIpdChange@DefaultHumanProvider@@AEAAJXZ; DefaultHumanProvider::StartMonitoringIpdChange(void)
0x18000e41e  mov     rcx, [rsp+28h]; this
0x18000e423  test    eax, eax
0x18000e425  jns     short loc_18000E435
0x18000e427  mov     r9d, eax; char *
0x18000e42a  mov     edx, 10h; void *
0x18000e42f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e434  nop
0x18000e435  call    cs:__imp_RoUninitialize
0x18000e43b  xor     eax, eax
0x18000e43d  jmp     short loc_18000E443
0x18000e43f  mov     eax, [rsp+28h+arg_8]
0x18000e443  add     rsp, 20h
0x18000e447  pop     rbx
0x18000e448  retn
0x18000e449  mov     r9d, eax; char *
0x18000e44c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e453  mov     edx, 14F2h; void *
0x18000e458  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
