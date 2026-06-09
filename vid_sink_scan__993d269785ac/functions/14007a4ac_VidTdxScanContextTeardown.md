# VidTdxScanContextTeardown

- ea: `0x14007a4ac`
- end: `0x14007a571`
- name: `VidTdxScanContextTeardown`
- size: `197`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14007a578`
- `0x14007b274`
- `0x14007ba88`

## callees

- `0x140024c78`
- `0x140030790`
- `0x1400307d0`
- `0x14007a4ac`
- `0x1400ed1f0`
- `0x1400ed9b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007a554`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a554`
- `winhvr!WinHvDeleteTdScanContext` at `0x14007a4fb`
- `winhvr!WinHvDeleteTdScanContext` at `0x14007a4fb`

## pseudocode

```c
void __fastcall VidTdxScanContextTeardown(__int64 a1, _QWORD *a2)
{
  int v4; // eax

  VidLockAcquireExclusive(a2);
  VidClientBufferUnShare(a2 + 4, 0, a2 + 4);
  a2[13] = 0;
  VidClientBufferUninitialize(a2 + 4);
  if ( a2[1] != -1 )
  {
    v4 = WinHvDeleteTdScanContext(*(_QWORD *)(a1 + 648));
    if ( v4 < 0 )
      VidTracePartitionErrorInternal0(
        (__int64)"VidTdxScanContextTeardown",
        (__int64)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
        483,
        a1 + 656,
        (unsigned __int16 *)(a1 + 120),
        *(_QWORD *)(a1 + 648),
        v4);
  }
  VidLockRelease(a2);
  ExFreePoolWithTag(a2, 0x72446456u);
}

```

## disassembly

```asm
0x14007a4ac  mov     [rsp+arg_0], rbx
0x14007a4b1  mov     [rsp+arg_8], rsi
0x14007a4b6  push    rdi
0x14007a4b7  sub     rsp, 40h
0x14007a4bb  mov     rsi, rcx
0x14007a4be  mov     rdi, rdx
0x14007a4c1  mov     rcx, rdx
0x14007a4c4  call    VidLockAcquireExclusive
0x14007a4c9  lea     rbx, [rdi+20h]
0x14007a4cd  xor     edx, edx
0x14007a4cf  mov     r8, rbx
0x14007a4d2  mov     rcx, rbx
0x14007a4d5  call    VidClientBufferUnShare
0x14007a4da  mov     rcx, rbx
0x14007a4dd  mov     qword ptr [rdi+68h], 0
0x14007a4e5  call    VidClientBufferUninitialize
0x14007a4ea  mov     rdx, [rdi+8]
0x14007a4ee  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14007a4f2  jz      short loc_14007A544
0x14007a4f4  mov     rcx, [rsi+288h]
0x14007a4fb  call    cs:__imp_WinHvDeleteTdScanContext
0x14007a502  nop     dword ptr [rax+rax+00h]
0x14007a507  test    eax, eax
0x14007a509  jns     short loc_14007A544
0x14007a50b  mov     [rsp+48h+var_18], eax
0x14007a50f  lea     rcx, [rsi+78h]
0x14007a513  mov     rax, [rsi+288h]
0x14007a51a  lea     r9, [rsi+290h]
0x14007a521  mov     [rsp+48h+var_20], rax
0x14007a526  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007a52d  mov     [rsp+48h+var_28], rcx
0x14007a532  mov     r8d, 1E3h
0x14007a538  lea     rcx, aVidtdxscancont; "VidTdxScanContextTeardown"
0x14007a53f  call    VidTracePartitionErrorInternal0
0x14007a544  mov     rcx, rdi
0x14007a547  call    VidLockRelease
0x14007a54c  mov     edx, 72446456h; Tag
0x14007a551  mov     rcx, rdi; P
0x14007a554  call    cs:__imp_ExFreePoolWithTag
0x14007a55b  nop     dword ptr [rax+rax+00h]
0x14007a560  mov     rbx, [rsp+48h+arg_0]
0x14007a565  mov     rsi, [rsp+48h+arg_8]
0x14007a56a  add     rsp, 40h
0x14007a56e  pop     rdi
0x14007a56f  retn
```
