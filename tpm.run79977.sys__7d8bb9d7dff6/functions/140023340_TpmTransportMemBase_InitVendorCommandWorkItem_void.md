# TpmTransportMemBase::InitVendorCommandWorkItem(void)

- ea: `0x140023340`
- end: `0x140023448`
- name: `?InitVendorCommandWorkItem@TpmTransportMemBase@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(TpmTransportMemBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400246b0`

## callees

- `0x140023340`
- `0x140039780`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140023414`
- `ntoskrnl!KeInitializeEvent` at `0x140023414`

## pseudocode

```c
__int64 __fastcall TpmTransportMemBase::InitVendorCommandWorkItem(TpmTransportMemBase *this)
{
  int v2; // edi
  __int64 v3; // rbx
  _QWORD v5[3]; // [rsp+30h] [rbp-19h] BYREF
  int v6; // [rsp+48h] [rbp-1h] BYREF
  __int128 v7; // [rsp+4Ch] [rbp+3h]
  int v8; // [rsp+5Ch] [rbp+13h]
  int v9; // [rsp+60h] [rbp+17h]
  int v10; // [rsp+64h] [rbp+1Bh]
  __int64 v11; // [rsp+68h] [rbp+1Fh]
  __int64 v12; // [rsp+70h] [rbp+27h]
  void *v13; // [rsp+78h] [rbp+2Fh]
  __int64 v14; // [rsp+B0h] [rbp+67h] BYREF

  v14 = 0;
  v5[2] = 1;
  v8 = 0;
  v5[0] = 24;
  v5[1] = TpmTransportMemBase::VendorCommandWorkItemCb;
  v12 = 0;
  v9 = 1;
  v10 = 1;
  v13 = off_1400470F0;
  v11 = *((_QWORD *)this + 3);
  v7 = 0;
  v6 = 56;
  v2 = (*((__int64 (__fastcall **)(PKDPC, _QWORD *, int *, __int64 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 379))(
         WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
         v5,
         &v6,
         &v14);
  if ( v2 >= 0 )
  {
    v3 = (*((__int64 (__fastcall **)(PKDPC, __int64, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           v14,
           off_1400470F0);
    KeInitializeEvent((PRKEVENT)(v3 + 8), NotificationEvent, 0);
    *(_DWORD *)v3 = 0;
    *(_BYTE *)(v3 + 32) = 0;
    *(_QWORD *)(v3 + 40) = this;
    *((_QWORD *)this + 62) = v14;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140023340  push    rbp
0x140023342  push    rbx
0x140023343  push    rsi
0x140023344  push    rdi
0x140023345  lea     rbp, [rsp-3Fh]
0x14002334a  sub     rsp, 88h
0x140023351  xor     eax, eax
0x140023353  mov     [rbp+57h+arg_0], 0
0x14002335b  mov     [rbp+57h+var_60], rax
0x14002335f  lea     r9, [rbp+57h+arg_0]
0x140023363  xorps   xmm0, xmm0
0x140023366  mov     [rbp+57h+var_44], 0
0x14002336d  movups  [rbp+57h+var_70], xmm0
0x140023371  lea     rax, ?VendorCommandWorkItemCb@TpmTransportMemBase@@CAXPEAUWDFWORKITEM__@@@Z; TpmTransportMemBase::VendorCommandWorkItemCb(WDFWORKITEM__ *)
0x140023378  mov     dword ptr [rbp+57h+var_70], 18h
0x14002337f  mov     qword ptr [rbp+57h+var_70+8], rax
0x140023383  lea     r8, [rbp+57h+var_58]
0x140023387  mov     eax, 1
0x14002338c  mov     [rbp+57h+var_30], 0
0x140023394  mov     byte ptr [rbp+57h+var_60], al
0x140023397  lea     rdx, [rbp+57h+var_70]
0x14002339b  mov     [rbp+57h+var_40], eax
0x14002339e  mov     rsi, rcx
0x1400233a1  mov     [rbp+57h+var_3C], eax
0x1400233a4  mov     rax, cs:off_1400470F0
0x1400233ab  mov     [rbp+57h+var_28], rax
0x1400233af  mov     rax, [rcx+18h]
0x1400233b3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400233ba  mov     [rbp+57h+var_38], rax
0x1400233be  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400233c5  movdqu  [rbp+57h+var_54], xmm0
0x1400233ca  mov     [rbp+57h+var_58], 38h ; '8'
0x1400233d1  mov     rax, [rax+0BD8h]
0x1400233d8  call    _guard_dispatch_icall
0x1400233dd  mov     edi, eax
0x1400233df  test    eax, eax
0x1400233e1  js      short loc_140023439
0x1400233e3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400233ea  mov     r8, cs:off_1400470F0
0x1400233f1  mov     rdx, [rbp+57h+arg_0]
0x1400233f5  mov     rax, [rcx+650h]
0x1400233fc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140023403  call    _guard_dispatch_icall
0x140023408  xor     r8d, r8d; State
0x14002340b  xor     edx, edx; Type
0x14002340d  mov     rbx, rax
0x140023410  lea     rcx, [rax+8]; Event
0x140023414  call    cs:__imp_KeInitializeEvent
0x14002341b  nop     dword ptr [rax+rax+00h]
0x140023420  mov     dword ptr [rbx], 0
0x140023426  mov     byte ptr [rbx+20h], 0
0x14002342a  mov     [rbx+28h], rsi
0x14002342e  mov     rax, [rbp+57h+arg_0]
0x140023432  mov     [rsi+1F0h], rax
0x140023439  mov     eax, edi
0x14002343b  add     rsp, 88h
0x140023442  pop     rdi
0x140023443  pop     rsi
0x140023444  pop     rbx
0x140023445  pop     rbp
0x140023446  retn
```
