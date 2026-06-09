# SrvNetQUICUpdateConfHelper

- ea: `0x140049db0`
- end: `0x140049e89`
- name: `SrvNetQUICUpdateConfHelper`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140049e90`
- `0x14004a114`

## callees

- `0x14001389c`
- `0x14001c134`
- `0x14002a4c0`
- `0x140049db0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049e49`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049e49`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140049e2a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140049e2a`

## pseudocode

```c
__int64 __fastcall SrvNetQUICUpdateConfHelper(__int64 a1, _DWORD *a2, unsigned int a3)
{
  int v5; // edi
  __int64 v6; // rbp
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  v5 = SrvNetQUICCreateNewConfiguration((__int64)a2, a3, &v8);
  if ( v5 >= 0 )
  {
    ExAcquirePushLockExclusiveEx(a1 + 40, 0);
    v6 = *(_QWORD *)(a1 + 48);
    *(_QWORD *)(a1 + 48) = v8;
    ExReleasePushLockExclusiveEx(a1 + 40, 0);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(MsQuic + 72))(v6);
    *(_DWORD *)(a1 + 36) = *a2;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140049db0  mov     r11, rsp
0x140049db3  mov     [r11+8], rbx
0x140049db7  mov     [r11+10h], rbp
0x140049dbb  push    rsi
0x140049dbc  push    rdi
0x140049dbd  push    r14
0x140049dbf  sub     rsp, 20h
0x140049dc3  mov     eax, r8d
0x140049dc6  mov     qword ptr [r11+20h], 0
0x140049dce  mov     r14, rdx
0x140049dd1  lea     r8, [r11+20h]
0x140049dd5  mov     rsi, rcx
0x140049dd8  mov     edx, eax
0x140049dda  mov     rcx, r14
0x140049ddd  call    SrvNetQUICCreateNewConfiguration
0x140049de2  mov     edi, eax
0x140049de4  test    eax, eax
0x140049de6  jns     short loc_140049E24
0x140049de8  mov     rcx, cs:WPP_GLOBAL_Control
0x140049def  lea     rax, WPP_GLOBAL_Control
0x140049df6  cmp     rcx, rax
0x140049df9  jz      short loc_140049E73
0x140049dfb  test    dword ptr [rcx+2Ch], 200000h
0x140049e02  jz      short loc_140049E73
0x140049e04  cmp     byte ptr [rcx+29h], 2
0x140049e08  jb      short loc_140049E73
0x140049e0a  mov     rcx, [rcx+18h]
0x140049e0e  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x140049e15  mov     edx, 5Ch ; '\'
0x140049e1a  mov     r9d, edi
0x140049e1d  call    WPP_SF_d
0x140049e22  jmp     short loc_140049E73
0x140049e24  xor     edx, edx
0x140049e26  lea     rcx, [rsi+28h]
0x140049e2a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140049e31  nop     dword ptr [rax+rax+00h]
0x140049e36  mov     rax, [rsp+38h+arg_18]
0x140049e3b  lea     rcx, [rsi+28h]
0x140049e3f  mov     rbp, [rsi+30h]
0x140049e43  xor     edx, edx
0x140049e45  mov     [rsi+30h], rax
0x140049e49  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140049e50  nop     dword ptr [rax+rax+00h]
0x140049e55  test    rbp, rbp
0x140049e58  jz      short loc_140049E6D
0x140049e5a  mov     rax, cs:MsQuic
0x140049e61  mov     rcx, rbp
0x140049e64  mov     rax, [rax+48h]
0x140049e68  call    _guard_dispatch_icall
0x140049e6d  mov     eax, [r14]
0x140049e70  mov     [rsi+24h], eax
0x140049e73  mov     rbx, [rsp+38h+arg_0]
0x140049e78  mov     eax, edi
0x140049e7a  mov     rbp, [rsp+38h+arg_8]
0x140049e7f  add     rsp, 20h
0x140049e83  pop     r14
0x140049e85  pop     rdi
0x140049e86  pop     rsi
0x140049e87  retn
```
