# TpmTransportSpbDevice::SPBWrite(void *,uint)

- ea: `0x140026a68`
- end: `0x140026abd`
- name: `?SPBWrite@TpmTransportSpbDevice@@IEAAJPEAXI@Z`
- size: `85`
- prototype: `__int64 __fastcall(TpmTransportSpbDevice *__hidden this, void *, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140025630`
- `0x140025724`
- `0x140025c20`
- `0x1400261d0`
- `0x1400266a0`
- `0x1400275d0`
- `0x140027770`
- `0x140027a80`

## callees

- `0x140039780`

## pseudocode

```c
__int64 __fastcall TpmTransportSpbDevice::SPBWrite(TpmTransportSpbDevice *this, void *a2, int a3)
{
  __int64 v3; // rdx
  _QWORD v5[2]; // [rsp+40h] [rbp-28h] BYREF
  int v6; // [rsp+50h] [rbp-18h]
  int v7; // [rsp+54h] [rbp-14h]

  v5[1] = a2;
  v3 = *((_QWORD *)this + 1);
  v7 = 0;
  v6 = a3;
  v5[0] = 1;
  return (*((__int64 (__fastcall **)(PKDPC, __int64, _QWORD, _QWORD *, _QWORD, _QWORD, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
          + 184))(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           v3,
           0,
           v5,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x140026a68  mov     r11, rsp
0x140026a6b  sub     rsp, 68h
0x140026a6f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140026a76  xor     r9d, r9d
0x140026a79  mov     [r11-38h], r9
0x140026a7d  mov     [r11-40h], r9
0x140026a81  mov     [r11-20h], rdx
0x140026a85  mov     rdx, [rcx+8]
0x140026a89  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140026a90  mov     [r11-14h], r9d
0x140026a94  mov     [r11-18h], r8d
0x140026a98  xor     r8d, r8d
0x140026a9b  mov     [r11-48h], r9
0x140026a9f  lea     r9, [r11-28h]
0x140026aa3  mov     qword ptr [r11-28h], 1
0x140026aab  mov     rax, [rax+5C0h]
0x140026ab2  call    _guard_dispatch_icall
0x140026ab7  add     rsp, 68h
0x140026abb  retn
```
