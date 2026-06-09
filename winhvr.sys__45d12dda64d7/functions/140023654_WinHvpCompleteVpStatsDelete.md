# WinHvpCompleteVpStatsDelete

- ea: `0x140023654`
- end: `0x1400236f6`
- name: `WinHvpCompleteVpStatsDelete`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001d9e0`

## callees

- `0x140009c50`
- `0x140023654`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1400236d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400236d7`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400236a9`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400236c4`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400236a9`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x1400236c4`

## pseudocode

```c
void __fastcall WinHvpCompleteVpStatsDelete(int a1, __int64 a2, int a3)
{
  _BYTE Buffer[48]; // [rsp+20h] [rbp-40h] BYREF

  memset(Buffer, 0, 44);
  if ( a1 >= 0 )
  {
    *(_QWORD *)&Buffer[8] = a2;
    memset(&Buffer[16], 0, 32);
    *(_QWORD *)Buffer = 65538;
    *(_DWORD *)&Buffer[16] = a3;
    Buffer[23] = 0;
    RtlDeleteElementGenericTable(&WinHvpStatsTable, Buffer);
    Buffer[23] = 1;
    RtlDeleteElementGenericTable(&WinHvpStatsTable, Buffer);
  }
  ExReleaseFastMutex(&WinHvpStatsTableLock);
}

```

## disassembly

```asm
0x140023654  push    rbp
0x140023656  mov     rbp, rsp
0x140023659  sub     rsp, 60h
0x14002365d  mov     rax, cs:__security_cookie
0x140023664  xor     rax, rsp
0x140023667  mov     [rbp+var_10], rax
0x14002366b  xorps   xmm0, xmm0
0x14002366e  xor     eax, eax
0x140023670  movups  [rbp+var_30], xmm0
0x140023674  movups  [rbp+var_30+0Ch], xmm0
0x140023678  movups  [rbp+Buffer], xmm0
0x14002367c  test    ecx, ecx
0x14002367e  js      short loc_1400236D0
0x140023680  movups  [rbp+Buffer], xmm0
0x140023684  mov     qword ptr [rbp+Buffer+8], rdx
0x140023688  lea     rdx, [rbp+Buffer]; Buffer
0x14002368c  movups  [rbp+var_30], xmm0
0x140023690  lea     rcx, WinHvpStatsTable; Table
0x140023697  mov     dword ptr [rbp+Buffer], 10002h
0x14002369e  movups  [rbp+var_20], xmm0
0x1400236a2  mov     dword ptr [rbp+var_30], r8d
0x1400236a6  mov     byte ptr [rbp+var_30+7], al
0x1400236a9  call    cs:__imp_RtlDeleteElementGenericTable
0x1400236b0  nop     dword ptr [rax+rax+00h]
0x1400236b5  lea     rdx, [rbp+Buffer]; Buffer
0x1400236b9  mov     byte ptr [rbp+var_30+7], 1
0x1400236bd  lea     rcx, WinHvpStatsTable; Table
0x1400236c4  call    cs:__imp_RtlDeleteElementGenericTable
0x1400236cb  nop     dword ptr [rax+rax+00h]
0x1400236d0  lea     rcx, WinHvpStatsTableLock; FastMutex
0x1400236d7  call    cs:__imp_ExReleaseFastMutex
0x1400236de  nop     dword ptr [rax+rax+00h]
0x1400236e3  mov     rcx, [rbp+var_10]
0x1400236e7  xor     rcx, rsp; StackCookie
0x1400236ea  call    __security_check_cookie
0x1400236ef  add     rsp, 60h
0x1400236f3  pop     rbp
0x1400236f4  retn
```
