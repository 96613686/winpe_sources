# TmReadOnlyEnlistmentExt

- ea: `0x140019e50`
- end: `0x140019ef1`
- name: `TmReadOnlyEnlistmentExt`
- size: `161`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013950`

## callees

- `0x14001a000`

## pseudocode

```c
NTSTATUS __stdcall TmReadOnlyEnlistmentExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __m128i v3; // [rsp+48h] [rbp-9h] BYREF
  __m128i v4; // [rsp+58h] [rbp+7h] BYREF
  __int64 v5[2]; // [rsp+68h] [rbp+17h] BYREF
  __m128i si128; // [rsp+78h] [rbp+27h]
  _QWORD v7[4]; // [rsp+88h] [rbp+37h] BYREF

  v7[0] = TmpTxActionDoPrePrepareComplete;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v7[2] = 0;
  v7[1] = TmpTxActionDoPrepareComplete;
  *(__m128i *)v5 = _mm_load_si128((const __m128i *)&_xmm);
  v4 = _mm_load_si128((const __m128i *)&_xmm);
  v7[3] = 0;
  v3 = _mm_load_si128((const __m128i *)&_xmm);
  return TmpProcessNotificationResponse(Enlistment, (__int64)v5, (__int64)&v4, (__int64)v7, (__int64)&v3);
}

```

## disassembly

```asm
0x140019e50  mov     r11, rsp
0x140019e53  push    rbp
0x140019e54  lea     rbp, [r11-5Fh]
0x140019e58  sub     rsp, 0A0h
0x140019e5f  movdqa  xmm0, cs:__xmm@0000010000000111000001010000010a
0x140019e67  lea     rax, TmpTxActionDoPrePrepareComplete
0x140019e6e  movdqa  xmm1, cs:__xmm@000000010000000b0000000200000008
0x140019e76  lea     r9, [rbp+57h+var_30]
0x140019e7a  mov     [rbp+57h+var_20], rax
0x140019e7e  mov     r8d, 4
0x140019e84  movdqu  [rbp+57h+var_30], xmm0
0x140019e89  lea     rax, TmpTxActionDoPrepareComplete
0x140019e90  mov     [rbp+57h+var_10], 0
0x140019e98  movdqa  xmm0, cs:__xmm@0000010e0000010e0000010e0000010e
0x140019ea0  mov     [rbp+57h+var_18], rax
0x140019ea4  lea     rax, [rbp+57h+var_60]
0x140019ea8  mov     [r11-70h], rax
0x140019eac  lea     rax, [rbp+57h+var_20]
0x140019eb0  mov     [r11-78h], rax
0x140019eb4  lea     rax, [rbp+57h+var_50]
0x140019eb8  mov     [r11-80h], rax
0x140019ebc  lea     rax, [rbp+57h+var_40]
0x140019ec0  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x140019ec4  mov     [rsp+20h], rax; __int64
0x140019ec9  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x140019ed1  movdqu  [rbp+57h+var_50], xmm1
0x140019ed6  mov     [rbp+57h+var_8], 0
0x140019ede  movups  [rbp+57h+var_60], xmm0
0x140019ee2  call    TmpProcessNotificationResponse
0x140019ee7  add     rsp, 0A0h
0x140019eee  pop     rbp
0x140019eef  retn
```
