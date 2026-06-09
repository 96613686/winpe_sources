# TUNNEL_GetUsb4Host

- ea: `0x140090ef8`
- end: `0x140090fe1`
- name: `TUNNEL_GetUsb4Host`
- size: `233`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14008fb74`
- `0x14008ff30`
- `0x1400910b8`
- `0x140091750`

## callees

- `0x140045570`
- `0x140090ef8`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140090fb6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140090fb6`

## pseudocode

```c
_QWORD *__fastcall TUNNEL_GetUsb4Host(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdx
  UNICODE_STRING String1; // [rsp+20h] [rbp-38h] BYREF

  v4 = *(_QWORD *)(a1 + 2752);
  v5 = 0;
  String1 = 0;
  v6 = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 112))(WdfDriverGlobals, v4);
  if ( !v7 )
    return 0;
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 144))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 2752),
           v6);
    if ( !v8 )
      break;
    v5 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
                     WdfDriverGlobals,
                     v8,
                     0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, UNICODE_STRING *))(WdfFunctions_01015 + 2472))(
      WdfDriverGlobals,
      *v5,
      &String1);
    if ( !RtlCompareUnicodeString(&String1, a2, 1u) )
      break;
    if ( ++v6 >= v7 )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140090ef8  push    rbx
0x140090efa  push    rbp
0x140090efb  push    rsi
0x140090efc  push    rdi
0x140090efd  push    r14
0x140090eff  sub     rsp, 30h
0x140090f03  mov     rax, cs:WdfFunctions_01015
0x140090f0a  xorps   xmm0, xmm0
0x140090f0d  mov     r14, rdx
0x140090f10  mov     rbp, rcx
0x140090f13  mov     rdx, [rcx+0AC0h]
0x140090f1a  xor     edi, edi
0x140090f1c  mov     rcx, cs:WdfDriverGlobals
0x140090f23  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140090f28  mov     rax, [rax+70h]
0x140090f2c  call    _guard_dispatch_icall
0x140090f31  xor     ebx, ebx
0x140090f33  mov     esi, eax
0x140090f35  test    eax, eax
0x140090f37  jz      loc_140090FD0
0x140090f3d  mov     rax, cs:WdfFunctions_01015
0x140090f44  mov     r8d, ebx
0x140090f47  mov     rdx, [rbp+0AC0h]
0x140090f4e  mov     rcx, cs:WdfDriverGlobals
0x140090f55  mov     rax, [rax+90h]
0x140090f5c  call    _guard_dispatch_icall
0x140090f61  mov     rdx, rax
0x140090f64  test    rax, rax
0x140090f67  jz      short loc_140090FD2
0x140090f69  mov     rax, cs:WdfFunctions_01015
0x140090f70  xor     r8d, r8d
0x140090f73  mov     rcx, cs:WdfDriverGlobals
0x140090f7a  mov     rax, [rax+610h]
0x140090f81  call    _guard_dispatch_icall
0x140090f86  mov     rcx, cs:WdfFunctions_01015
0x140090f8d  lea     r8, [rsp+58h+String1]
0x140090f92  mov     rdi, rax
0x140090f95  mov     rax, [rcx+9A8h]
0x140090f9c  mov     rcx, cs:WdfDriverGlobals
0x140090fa3  mov     rdx, [rdi]
0x140090fa6  call    _guard_dispatch_icall
0x140090fab  mov     r8b, 1; CaseInSensitive
0x140090fae  lea     rcx, [rsp+58h+String1]; String1
0x140090fb3  mov     rdx, r14; String2
0x140090fb6  call    cs:__imp_RtlCompareUnicodeString
0x140090fbd  nop     dword ptr [rax+rax+00h]
0x140090fc2  test    eax, eax
0x140090fc4  jz      short loc_140090FD2
0x140090fc6  inc     ebx
0x140090fc8  cmp     ebx, esi
0x140090fca  jb      loc_140090F3D
0x140090fd0  xor     edi, edi
0x140090fd2  mov     rax, rdi
0x140090fd5  add     rsp, 30h
0x140090fd9  pop     r14
0x140090fdb  pop     rdi
0x140090fdc  pop     rsi
0x140090fdd  pop     rbp
0x140090fde  pop     rbx
0x140090fdf  retn
```
