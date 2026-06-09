# VhdmpiCompleteRecoveryRequestV2(_VHD_RECOVERY_REQUEST *)

- ea: `0x1400d20ac`
- end: `0x1400d22a2`
- name: `?VhdmpiCompleteRecoveryRequestV2@@YAXPEAU_VHD_RECOVERY_REQUEST@@@Z`
- size: `502`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400d22b0`
- `0x1400d25d0`

## callees

- `0x140015d1c`
- `0x14001bc1c`
- `0x14001c088`
- `0x140022750`
- `0x140023980`
- `0x14002e8b0`
- `0x14002ef28`
- `0x140036284`
- `0x14005dc30`
- `0x1400d20ac`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400d2234`
- `ntoskrnl!IofCompleteRequest` at `0x1400d2234`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400d2215`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400d2215`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2248`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2248`
- `ntoskrnl!KeSetEvent` at `0x1400d225f`
- `ntoskrnl!KeSetEvent` at `0x1400d225f`

## string_xrefs

- `0x1400d2160`: `VhdmpiCompleteRecoveryRequestV2`

## pseudocode

```c
void __fastcall VhdmpiCompleteRecoveryRequestV2(char *P, __int64 a2, int a3)
{
  struct _EX_RUNDOWN_REF *v3; // r15
  int v5; // eax
  __int64 v6; // rsi
  _QWORD *i; // r14
  __int64 (__fastcall *v8)(_QWORD *); // rax
  int v9; // ebp
  int v10; // ecx
  IRP *v11; // rbp

  v3 = *(struct _EX_RUNDOWN_REF **)P;
  v5 = *((_DWORD *)P + 30);
  v6 = *(_QWORD *)(*(_QWORD *)P + 56LL);
  if ( v5 == 259 )
  {
    *((_DWORD *)P + 30) = 0;
  }
  else if ( v5 < 0 )
  {
    goto LABEL_16;
  }
  VhdmpiAcquirePassiveLock(v6 + 128);
  for ( i = *(_QWORD **)(v6 + 144); i; i = (_QWORD *)i[143] )
  {
    VhdmpiFileWrapperResetIoErrorLogger(i + 9, 2);
    v8 = *(__int64 (__fastcall **)(_QWORD *))(*i + 536LL);
    if ( v8 )
    {
      v9 = v8(i);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
          TraceEvents("VhdmpiCompleteRecoveryRequestV2", 0x210u, 2u, 0x80000u, "Log status 0x%08X", v9);
        if ( *((int *)P + 30) >= 0 )
        {
          *((_DWORD *)P + 30) = v9;
          if ( (unsigned __int8)VhdmpiBackingStoreIoErrorIsRecoverable(i, (unsigned int)v9) )
            *((_DWORD *)P + 30) = -1073741267;
        }
      }
    }
  }
  VhdmpiReleasePassiveLock(v6 + 128);
LABEL_16:
  v10 = *((_DWORD *)P + 30);
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      McTemplateK0zjq_EtwWriteTransfer(
        v10,
        (unsigned int)VhdRecoveryRequestError,
        a3,
        *(_QWORD *)(*(_QWORD *)(v6 + 144) + 120LL),
        *(_QWORD *)(v6 + 144) + 620LL,
        v10);
  }
  else if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
  {
    McTemplateK0zjq_EtwWriteTransfer(
      v10,
      (unsigned int)VhdRecoveryRequestSuccess,
      a3,
      *(_QWORD *)(*(_QWORD *)(v6 + 144) + 120LL),
      *(_QWORD *)(v6 + 144) + 620LL,
      0);
  }
  v11 = (IRP *)VhdmpiDequeueControlDeviceIoctl(v3, 2955904);
  if ( v11 )
  {
    ExReleaseRundownProtection(v3 + 33);
    v11->IoStatus.Information = 0;
    v11->IoStatus.Status = *((_DWORD *)P + 30);
    IofCompleteRequest(v11, 0);
    ExFreePoolWithTag(P, 0x71444856u);
  }
  else
  {
    KeSetEvent((PRKEVENT)(P + 64), 0, 0);
  }
  VhdmpiAcquirePassiveLock(v6 + 184);
  --*(_DWORD *)(v6 + 256);
  *(_QWORD *)(v6 + 248) = 0;
  VhdmpiReleasePassiveLock(v6 + 184);
}

```

## disassembly

```asm
0x1400d20ac  push    rbx
0x1400d20ae  push    rbp
0x1400d20af  push    rsi
0x1400d20b0  push    r12
0x1400d20b2  push    r14
0x1400d20b4  push    r15
0x1400d20b6  sub     rsp, 38h
0x1400d20ba  mov     r15, [rcx]
0x1400d20bd  mov     rbx, rcx
0x1400d20c0  mov     eax, [rcx+78h]
0x1400d20c3  mov     rsi, [r15+38h]
0x1400d20c7  cmp     eax, 103h
0x1400d20cc  jnz     short loc_1400D20D7
0x1400d20ce  mov     dword ptr [rcx+78h], 0
0x1400d20d5  jmp     short loc_1400D20DF
0x1400d20d7  test    eax, eax
0x1400d20d9  js      loc_1400D21A8
0x1400d20df  lea     r12, [rsi+80h]
0x1400d20e6  mov     rcx, r12
0x1400d20e9  call    VhdmpiAcquirePassiveLock
0x1400d20ee  mov     r14, [rsi+90h]
0x1400d20f5  jmp     loc_1400D2197
0x1400d20fa  lea     rcx, [r14+48h]
0x1400d20fe  mov     edx, 2
0x1400d2103  call    VhdmpiFileWrapperResetIoErrorLogger
0x1400d2108  mov     rax, [r14]
0x1400d210b  mov     rax, [rax+218h]
0x1400d2112  test    rax, rax
0x1400d2115  jz      short loc_1400D2190
0x1400d2117  mov     rcx, r14
0x1400d211a  call    _guard_dispatch_icall
0x1400d211f  mov     ebp, eax
0x1400d2121  test    eax, eax
0x1400d2123  jns     short loc_1400D2190
0x1400d2125  mov     ecx, cs:dword_1400876D0
0x1400d212b  cmp     ecx, 2
0x1400d212e  jbe     short loc_1400D2172
0x1400d2130  mov     edx, 80000h
0x1400d2135  lea     rcx, dword_1400876D0
0x1400d213c  call    _tlgKeywordOn
0x1400d2141  test    al, al
0x1400d2143  jz      short loc_1400D2172
0x1400d2145  lea     rax, aLogStatus0x08x_3; "Log status 0x%08X"
0x1400d214c  mov     dword ptr [rsp+68h+var_40], ebp; char
0x1400d2150  mov     edx, 210h; int
0x1400d2155  mov     [rsp+68h+var_48], rax; char *
0x1400d215a  mov     r9d, 80000h; int
0x1400d2160  lea     rcx, aVhdmpicomplete_15; "VhdmpiCompleteRecoveryRequestV2"
0x1400d2167  mov     r8d, 2; int
0x1400d216d  call    TraceEvents
0x1400d2172  cmp     dword ptr [rbx+78h], 0
0x1400d2176  jl      short loc_1400D2190
0x1400d2178  mov     edx, ebp
0x1400d217a  mov     [rbx+78h], ebp
0x1400d217d  mov     rcx, r14
0x1400d2180  call    VhdmpiBackingStoreIoErrorIsRecoverable
0x1400d2185  test    al, al
0x1400d2187  jz      short loc_1400D2190
0x1400d2189  mov     dword ptr [rbx+78h], 0C000022Dh
0x1400d2190  mov     r14, [r14+478h]
0x1400d2197  test    r14, r14
0x1400d219a  jnz     loc_1400D20FA
0x1400d21a0  mov     rcx, r12
0x1400d21a3  call    VhdmpiReleasePassiveLock
0x1400d21a8  mov     ecx, [rbx+78h]
0x1400d21ab  test    ecx, ecx
0x1400d21ad  js      short loc_1400D21C9
0x1400d21af  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400d21b6  jz      short loc_1400D21F9
0x1400d21b8  mov     dword ptr [rsp+68h+var_40], 0
0x1400d21c0  lea     rdx, VhdRecoveryRequestSuccess
0x1400d21c7  jmp     short loc_1400D21DD
0x1400d21c9  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400d21d0  jz      short loc_1400D21F9
0x1400d21d2  mov     dword ptr [rsp+68h+var_40], ecx
0x1400d21d6  lea     rdx, VhdRecoveryRequestError
0x1400d21dd  mov     r9, [rsi+90h]
0x1400d21e4  lea     rax, [r9+26Ch]
0x1400d21eb  mov     r9, [r9+78h]
0x1400d21ef  mov     [rsp+68h+var_48], rax
0x1400d21f4  call    McTemplateK0zjq_EtwWriteTransfer
0x1400d21f9  mov     edx, 2D1A80h
0x1400d21fe  mov     rcx, r15
0x1400d2201  call    VhdmpiDequeueControlDeviceIoctl
0x1400d2206  mov     rbp, rax
0x1400d2209  test    rax, rax
0x1400d220c  jz      short loc_1400D2256
0x1400d220e  lea     rcx, [r15+108h]; RunRef
0x1400d2215  call    cs:__imp_ExReleaseRundownProtection
0x1400d221c  nop     dword ptr [rax+rax+00h]
0x1400d2221  mov     qword ptr [rbp+38h], 0
0x1400d2229  xor     edx, edx; PriorityBoost
0x1400d222b  mov     ecx, [rbx+78h]
0x1400d222e  mov     [rbp+30h], ecx
0x1400d2231  mov     rcx, rbp; Irp
0x1400d2234  call    cs:__imp_IofCompleteRequest
0x1400d223b  nop     dword ptr [rax+rax+00h]
0x1400d2240  mov     edx, 71444856h; Tag
0x1400d2245  mov     rcx, rbx; P
0x1400d2248  call    cs:__imp_ExFreePoolWithTag
0x1400d224f  nop     dword ptr [rax+rax+00h]
0x1400d2254  jmp     short loc_1400D226B
0x1400d2256  lea     rcx, [rbx+40h]; Event
0x1400d225a  xor     r8d, r8d; Wait
0x1400d225d  xor     edx, edx; Increment
0x1400d225f  call    cs:__imp_KeSetEvent
0x1400d2266  nop     dword ptr [rax+rax+00h]
0x1400d226b  lea     rbx, [rsi+0B8h]
0x1400d2272  mov     rcx, rbx
0x1400d2275  call    VhdmpiAcquirePassiveLock
0x1400d227a  dec     dword ptr [rsi+100h]
0x1400d2280  mov     rcx, rbx
0x1400d2283  mov     qword ptr [rsi+0F8h], 0
0x1400d228e  call    VhdmpiReleasePassiveLock
0x1400d2293  add     rsp, 38h
0x1400d2297  pop     r15
0x1400d2299  pop     r14
0x1400d229b  pop     r12
0x1400d229d  pop     rsi
0x1400d229e  pop     rbp
0x1400d229f  pop     rbx
0x1400d22a0  retn
```
