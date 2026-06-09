# HUBMISC_EvtDsmDestroy

- ea: `0x14002f1c0`
- end: `0x14002f612`
- name: `HUBMISC_EvtDsmDestroy`
- size: `1106`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002f1c0`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002f294`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002f294`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f248`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f262`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f281`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f316`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f330`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f34a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f364`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f37e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f39c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f248`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f262`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f281`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f2fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f316`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f330`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f34a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f364`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f37e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f39c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f3e0`
- `ntoskrnl!ExDeleteTimer` at `0x14002f4d7`
- `ntoskrnl!ExDeleteTimer` at `0x14002f4d7`

## string_xrefs

- `0x14002f5db`: `DSM Create Tag`

## pseudocode

```c
__int64 __fastcall HUBMISC_EvtDsmDestroy(__int64 a1)
{
  struct _UNICODE_STRING *v1; // rax
  struct _UNICODE_STRING *v2; // rbx
  PVOID *v3; // rax
  void *v4; // rcx
  void *v5; // rcx
  wchar_t *Buffer; // rcx
  void *v7; // rcx
  wchar_t *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  wchar_t *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  wchar_t *v15; // rcx
  wchar_t *v16; // rcx
  wchar_t *v17; // rcx
  wchar_t *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax

  v1 = (struct _UNICODE_STRING *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                                   WdfDriverGlobals,
                                   a1,
                                   off_14006B1A8);
  v2 = v1;
  if ( *(_QWORD *)&v1[94].Length )
  {
    (*(void (**)(void))(*(_QWORD *)&v1->Length + 528LL))();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)&v2->Length + 512LL))(*(_QWORD *)&v2[94].Length);
    *(_QWORD *)&v2[94].Length = 0;
  }
  v3 = *(PVOID **)&v2[166].Length;
  if ( v3 && *v3 )
    ExFreePoolWithTag(*v3, 0x68334855u);
  v4 = *(void **)&v2[166].Length;
  if ( v4 )
    ExFreePoolWithTag(v4, 0x68334855u);
  v5 = *(void **)&v2[135].Length;
  if ( v5 )
    ExFreePoolWithTag(v5, 0x64334855u);
  RtlFreeUnicodeString(v2 + 133);
  Buffer = v2[153].Buffer;
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x64334855u);
  v7 = *(void **)&v2[136].Length;
  if ( v7 )
    ExFreePoolWithTag(v7, 0x64334855u);
  v8 = v2[126].Buffer;
  if ( v8 )
    ExFreePoolWithTag(v8, 0x64334855u);
  v9 = *(void **)&v2[132].Length;
  if ( v9 )
    ExFreePoolWithTag(v9, 0x64334855u);
  v10 = *(void **)&v2[127].Length;
  if ( v10 )
    ExFreePoolWithTag(v10, 0x64334855u);
  v11 = v2[127].Buffer;
  if ( v11 )
    ExFreePoolWithTag(v11, 0x64334855u);
  v12 = *(void **)&v2[129].Length;
  if ( v12 )
    ExFreePoolWithTag(v12, 0x64334855u);
  v13 = *(void **)&v2[161].Length;
  if ( v13 )
    ExFreePoolWithTag(v13, 0x64334855u);
  v14 = *(void **)&v2[156].Length;
  if ( v14 )
    ExFreePoolWithTag(v14, 0x64334855u);
  v15 = v2[6].Buffer;
  *(_DWORD *)&v2[6].Length = 0;
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0x64334855u);
    v2[6].Buffer = 0;
  }
  v16 = v2[8].Buffer;
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0x64334855u);
    v2[8].Buffer = 0;
  }
  v17 = v2[7].Buffer;
  if ( v17 )
  {
    ExFreePoolWithTag(v17, 0x64334855u);
    v2[7].Buffer = 0;
  }
  if ( *(_QWORD *)&v2[16].Length )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
      WdfDriverGlobals,
      *(_QWORD *)&v2[16].Length,
      "DSM Tag",
      7395,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    *(_QWORD *)&v2[16].Length = 0;
  }
  v18 = v2[26].Buffer;
  if ( v18 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, wchar_t *, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
      WdfDriverGlobals,
      v2[26].Buffer,
      "DSM Tag",
      7395,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    v2[26].Buffer = 0;
  }
  v19 = *(_QWORD *)&v2[97].Length;
  if ( v19 )
  {
    LOBYTE(v18) = 1;
    ExDeleteTimer(v19, v18, 0, 0);
    *(_QWORD *)&v2[97].Length = 0;
  }
  if ( v2[151].Buffer )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, wchar_t *, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
      WdfDriverGlobals,
      v2[151].Buffer,
      "DSM Tag",
      7395,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    v2[151].Buffer = 0;
  }
  if ( v2[27].Buffer )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, wchar_t *, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1648))(
      WdfDriverGlobals,
      v2[27].Buffer,
      "DSM Tag",
      7395,
      "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
    v2[27].Buffer = 0;
  }
  v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, wchar_t *))(WdfFunctions_01015 + 1632))(
          WdfDriverGlobals,
          v2->Buffer);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
           WdfDriverGlobals,
           v20,
           "DSM Create Tag",
           7481,
           "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\hubmisc.c");
}

```

## disassembly

```asm
0x14002f1c0  mov     [rsp+arg_0], rbx
0x14002f1c5  push    rsi
0x14002f1c6  sub     rsp, 30h
0x14002f1ca  mov     rax, cs:WdfFunctions_01015
0x14002f1d1  mov     rdx, rcx
0x14002f1d4  mov     r8, cs:off_14006B1A8
0x14002f1db  mov     rcx, cs:WdfDriverGlobals
0x14002f1e2  mov     rax, [rax+650h]
0x14002f1e9  call    _guard_dispatch_icall
0x14002f1ee  mov     rbx, rax
0x14002f1f1  mov     rcx, [rax+5E0h]
0x14002f1f8  test    rcx, rcx
0x14002f1fb  jz      short loc_14002F22D
0x14002f1fd  mov     rdx, [rax]
0x14002f200  mov     rax, [rdx+210h]
0x14002f207  call    _guard_dispatch_icall
0x14002f20c  mov     rcx, [rbx]
0x14002f20f  mov     rax, [rcx+200h]
0x14002f216  mov     rcx, [rbx+5E0h]
0x14002f21d  call    _guard_dispatch_icall
0x14002f222  mov     qword ptr [rbx+5E0h], 0
0x14002f22d  mov     rax, [rbx+0A60h]
0x14002f234  mov     esi, 68334855h
0x14002f239  test    rax, rax
0x14002f23c  jz      short loc_14002F254
0x14002f23e  mov     rcx, [rax]; P
0x14002f241  test    rcx, rcx
0x14002f244  jz      short loc_14002F254
0x14002f246  mov     edx, esi; Tag
0x14002f248  call    cs:__imp_ExFreePoolWithTag
0x14002f24f  nop     dword ptr [rax+rax+00h]
0x14002f254  mov     rcx, [rbx+0A60h]; P
0x14002f25b  test    rcx, rcx
0x14002f25e  jz      short loc_14002F26E
0x14002f260  mov     edx, esi; Tag
0x14002f262  call    cs:__imp_ExFreePoolWithTag
0x14002f269  nop     dword ptr [rax+rax+00h]
0x14002f26e  mov     rcx, [rbx+870h]; P
0x14002f275  mov     esi, 64334855h
0x14002f27a  test    rcx, rcx
0x14002f27d  jz      short loc_14002F28D
0x14002f27f  mov     edx, esi; Tag
0x14002f281  call    cs:__imp_ExFreePoolWithTag
0x14002f288  nop     dword ptr [rax+rax+00h]
0x14002f28d  lea     rcx, [rbx+850h]; UnicodeString
0x14002f294  call    cs:__imp_RtlFreeUnicodeString
0x14002f29b  nop     dword ptr [rax+rax+00h]
0x14002f2a0  mov     rcx, [rbx+998h]; P
0x14002f2a7  test    rcx, rcx
0x14002f2aa  jz      short loc_14002F2BA
0x14002f2ac  mov     edx, esi; Tag
0x14002f2ae  call    cs:__imp_ExFreePoolWithTag
0x14002f2b5  nop     dword ptr [rax+rax+00h]
0x14002f2ba  mov     rcx, [rbx+880h]; P
0x14002f2c1  test    rcx, rcx
0x14002f2c4  jz      short loc_14002F2D4
0x14002f2c6  mov     edx, esi; Tag
0x14002f2c8  call    cs:__imp_ExFreePoolWithTag
0x14002f2cf  nop     dword ptr [rax+rax+00h]
0x14002f2d4  mov     rcx, [rbx+7E8h]; P
0x14002f2db  test    rcx, rcx
0x14002f2de  jz      short loc_14002F2EE
0x14002f2e0  mov     edx, esi; Tag
0x14002f2e2  call    cs:__imp_ExFreePoolWithTag
0x14002f2e9  nop     dword ptr [rax+rax+00h]
0x14002f2ee  mov     rcx, [rbx+840h]; P
0x14002f2f5  test    rcx, rcx
0x14002f2f8  jz      short loc_14002F308
0x14002f2fa  mov     edx, esi; Tag
0x14002f2fc  call    cs:__imp_ExFreePoolWithTag
0x14002f303  nop     dword ptr [rax+rax+00h]
0x14002f308  mov     rcx, [rbx+7F0h]; P
0x14002f30f  test    rcx, rcx
0x14002f312  jz      short loc_14002F322
0x14002f314  mov     edx, esi; Tag
0x14002f316  call    cs:__imp_ExFreePoolWithTag
0x14002f31d  nop     dword ptr [rax+rax+00h]
0x14002f322  mov     rcx, [rbx+7F8h]; P
0x14002f329  test    rcx, rcx
0x14002f32c  jz      short loc_14002F33C
0x14002f32e  mov     edx, esi; Tag
0x14002f330  call    cs:__imp_ExFreePoolWithTag
0x14002f337  nop     dword ptr [rax+rax+00h]
0x14002f33c  mov     rcx, [rbx+810h]; P
0x14002f343  test    rcx, rcx
0x14002f346  jz      short loc_14002F356
0x14002f348  mov     edx, esi; Tag
0x14002f34a  call    cs:__imp_ExFreePoolWithTag
0x14002f351  nop     dword ptr [rax+rax+00h]
0x14002f356  mov     rcx, [rbx+0A10h]; P
0x14002f35d  test    rcx, rcx
0x14002f360  jz      short loc_14002F370
0x14002f362  mov     edx, esi; Tag
0x14002f364  call    cs:__imp_ExFreePoolWithTag
0x14002f36b  nop     dword ptr [rax+rax+00h]
0x14002f370  mov     rcx, [rbx+9C0h]; P
0x14002f377  test    rcx, rcx
0x14002f37a  jz      short loc_14002F38A
0x14002f37c  mov     edx, esi; Tag
0x14002f37e  call    cs:__imp_ExFreePoolWithTag
0x14002f385  nop     dword ptr [rax+rax+00h]
0x14002f38a  mov     rcx, [rbx+68h]; P
0x14002f38e  mov     dword ptr [rbx+60h], 0
0x14002f395  test    rcx, rcx
0x14002f398  jz      short loc_14002F3B0
0x14002f39a  mov     edx, esi; Tag
0x14002f39c  call    cs:__imp_ExFreePoolWithTag
0x14002f3a3  nop     dword ptr [rax+rax+00h]
0x14002f3a8  mov     qword ptr [rbx+68h], 0
0x14002f3b0  mov     rcx, [rbx+88h]; P
0x14002f3b7  test    rcx, rcx
0x14002f3ba  jz      short loc_14002F3D5
0x14002f3bc  mov     edx, esi; Tag
0x14002f3be  call    cs:__imp_ExFreePoolWithTag
0x14002f3c5  nop     dword ptr [rax+rax+00h]
0x14002f3ca  mov     qword ptr [rbx+88h], 0
0x14002f3d5  mov     rcx, [rbx+78h]; P
0x14002f3d9  test    rcx, rcx
0x14002f3dc  jz      short loc_14002F3F4
0x14002f3de  mov     edx, esi; Tag
0x14002f3e0  call    cs:__imp_ExFreePoolWithTag
0x14002f3e7  nop     dword ptr [rax+rax+00h]
0x14002f3ec  mov     qword ptr [rbx+78h], 0
0x14002f3f4  mov     rdx, [rbx+100h]
0x14002f3fb  lea     rsi, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14002f402  test    rdx, rdx
0x14002f405  jz      short loc_14002F45F
0x14002f407  mov     rax, cs:WdfFunctions_01015
0x14002f40e  mov     rcx, cs:WdfDriverGlobals
0x14002f415  mov     rax, [rax+680h]
0x14002f41c  call    _guard_dispatch_icall
0x14002f421  mov     rax, cs:WdfFunctions_01015
0x14002f428  lea     r8, DsmTag; "DSM Tag"
0x14002f42f  mov     rdx, [rbx+100h]
0x14002f436  mov     r9d, 1CE3h
0x14002f43c  mov     rcx, cs:WdfDriverGlobals
0x14002f443  mov     [rsp+38h+var_18], rsi
0x14002f448  mov     rax, [rax+670h]
0x14002f44f  call    _guard_dispatch_icall
0x14002f454  mov     qword ptr [rbx+100h], 0
0x14002f45f  mov     rdx, [rbx+1A8h]
0x14002f466  test    rdx, rdx
0x14002f469  jz      short loc_14002F4C3
0x14002f46b  mov     rax, cs:WdfFunctions_01015
0x14002f472  mov     rcx, cs:WdfDriverGlobals
0x14002f479  mov     rax, [rax+680h]
0x14002f480  call    _guard_dispatch_icall
0x14002f485  mov     rax, cs:WdfFunctions_01015
0x14002f48c  lea     r8, DsmTag; "DSM Tag"
0x14002f493  mov     rdx, [rbx+1A8h]
0x14002f49a  mov     r9d, 1CE3h
0x14002f4a0  mov     rcx, cs:WdfDriverGlobals
0x14002f4a7  mov     [rsp+38h+var_18], rsi
0x14002f4ac  mov     rax, [rax+670h]
0x14002f4b3  call    _guard_dispatch_icall
0x14002f4b8  mov     qword ptr [rbx+1A8h], 0
0x14002f4c3  mov     rcx, [rbx+610h]
0x14002f4ca  test    rcx, rcx
0x14002f4cd  jz      short loc_14002F4EE
0x14002f4cf  xor     r9d, r9d
0x14002f4d2  xor     r8d, r8d
0x14002f4d5  mov     dl, 1
0x14002f4d7  call    cs:__imp_ExDeleteTimer
0x14002f4de  nop     dword ptr [rax+rax+00h]
0x14002f4e3  mov     qword ptr [rbx+610h], 0
0x14002f4ee  mov     rdx, [rbx+978h]
0x14002f4f5  test    rdx, rdx
0x14002f4f8  jz      short loc_14002F552
0x14002f4fa  mov     rax, cs:WdfFunctions_01015
0x14002f501  mov     rcx, cs:WdfDriverGlobals
0x14002f508  mov     rax, [rax+680h]
0x14002f50f  call    _guard_dispatch_icall
0x14002f514  mov     rax, cs:WdfFunctions_01015
0x14002f51b  lea     r8, DsmTag; "DSM Tag"
0x14002f522  mov     rdx, [rbx+978h]
0x14002f529  mov     r9d, 1CE3h
0x14002f52f  mov     rcx, cs:WdfDriverGlobals
0x14002f536  mov     [rsp+38h+var_18], rsi
0x14002f53b  mov     rax, [rax+670h]
0x14002f542  call    _guard_dispatch_icall
0x14002f547  mov     qword ptr [rbx+978h], 0
0x14002f552  mov     rdx, [rbx+1B8h]
0x14002f559  test    rdx, rdx
0x14002f55c  jz      short loc_14002F5B6
0x14002f55e  mov     rax, cs:WdfFunctions_01015
0x14002f565  mov     rcx, cs:WdfDriverGlobals
0x14002f56c  mov     rax, [rax+680h]
0x14002f573  call    _guard_dispatch_icall
0x14002f578  mov     rax, cs:WdfFunctions_01015
0x14002f57f  lea     r8, DsmTag; "DSM Tag"
0x14002f586  mov     rdx, [rbx+1B8h]
0x14002f58d  mov     r9d, 1CE3h
0x14002f593  mov     rcx, cs:WdfDriverGlobals
0x14002f59a  mov     [rsp+38h+var_18], rsi
0x14002f59f  mov     rax, [rax+670h]
0x14002f5a6  call    _guard_dispatch_icall
0x14002f5ab  mov     qword ptr [rbx+1B8h], 0
0x14002f5b6  mov     rax, cs:WdfFunctions_01015
0x14002f5bd  mov     rdx, [rbx+8]
0x14002f5c1  mov     rcx, cs:WdfDriverGlobals
0x14002f5c8  mov     rax, [rax+660h]
0x14002f5cf  call    _guard_dispatch_icall
0x14002f5d4  mov     rcx, cs:WdfFunctions_01015
0x14002f5db  lea     r8, DsmCreateTag; "DSM Create Tag"
0x14002f5e2  mov     rdx, rax
0x14002f5e5  mov     [rsp+38h+var_18], rsi
0x14002f5ea  mov     r9d, 1D39h
0x14002f5f0  mov     r10, [rcx+670h]
0x14002f5f7  mov     rcx, cs:WdfDriverGlobals
0x14002f5fe  mov     rax, r10
0x14002f601  call    _guard_dispatch_icall
0x14002f606  mov     rbx, [rsp+38h+arg_0]
0x14002f60b  add     rsp, 30h
0x14002f60f  pop     rsi
0x14002f610  retn
```
