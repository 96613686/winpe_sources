# VhdmpiCompleteRecoveryRequestV2(_VHD_RECOVERY_REQUEST *)

- ea: `0x1400d211c`
- end: `0x1400d2312`
- name: `?VhdmpiCompleteRecoveryRequestV2@@YAXPEAU_VHD_RECOVERY_REQUEST@@@Z`
- size: `502`
- prototype: `void __fastcall(char *P, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400d2320`
- `0x1400d2640`

## callees

- `0x14001587c`
- `0x14001b7fc`
- `0x14001bc68`
- `0x140022330`
- `0x140023560`
- `0x14002e3f0`
- `0x14002ea68`
- `0x140035e94`
- `0x14005d840`
- `0x1400d211c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400d22a4`
- `ntoskrnl!IofCompleteRequest` at `0x1400d22a4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400d2285`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400d2285`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d22b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d22b8`
- `ntoskrnl!KeSetEvent` at `0x1400d22cf`
- `ntoskrnl!KeSetEvent` at `0x1400d22cf`

## string_xrefs

- `0x1400d21d0`: `VhdmpiCompleteRecoveryRequestV2`

## pseudocode

```c
void __fastcall VhdmpiCompleteRecoveryRequestV2(char *P, __int64 a2, __int64 a3)
{
  struct _EX_RUNDOWN_REF *v3; // r15
  int v5; // eax
  __int64 v6; // rsi
  _QWORD *i; // r14
  __int64 (__fastcall *v8)(_QWORD *); // rax
  int v9; // ebp
  int v10; // ecx
  IRP *v11; // rbp
  __int64 v12; // rdx
  __int64 v13; // r8

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
  VhdmpiAcquirePassiveLock(v6 + 128, a2, a3);
  for ( i = *(_QWORD **)(v6 + 144); i; i = (_QWORD *)i[143] )
  {
    VhdmpiFileWrapperResetIoErrorLogger(i + 9, 2);
    v8 = *(__int64 (__fastcall **)(_QWORD *))(*i + 536LL);
    if ( v8 )
    {
      v9 = v8(i);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
          TraceEvents((int)"VhdmpiCompleteRecoveryRequestV2", 528, 2, 0x80000, "Log status 0x%08X", v9);
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
  VhdmpiAcquirePassiveLock(v6 + 184, v12, v13);
  --*(_DWORD *)(v6 + 256);
  *(_QWORD *)(v6 + 248) = 0;
  VhdmpiReleasePassiveLock(v6 + 184);
}

```

## disassembly

```asm
0x1400d211c  push    rbx
0x1400d211e  push    rbp
0x1400d211f  push    rsi
0x1400d2120  push    r12
0x1400d2122  push    r14
0x1400d2124  push    r15
0x1400d2126  sub     rsp, 38h
0x1400d212a  mov     r15, [rcx]
0x1400d212d  mov     rbx, rcx
0x1400d2130  mov     eax, [rcx+78h]
0x1400d2133  mov     rsi, [r15+38h]
0x1400d2137  cmp     eax, 103h
0x1400d213c  jnz     short loc_1400D2147
0x1400d213e  mov     dword ptr [rcx+78h], 0
0x1400d2145  jmp     short loc_1400D214F
0x1400d2147  test    eax, eax
0x1400d2149  js      loc_1400D2218
0x1400d214f  lea     r12, [rsi+80h]
0x1400d2156  mov     rcx, r12
0x1400d2159  call    VhdmpiAcquirePassiveLock
0x1400d215e  mov     r14, [rsi+90h]
0x1400d2165  jmp     loc_1400D2207
0x1400d216a  lea     rcx, [r14+48h]
0x1400d216e  mov     edx, 2
0x1400d2173  call    VhdmpiFileWrapperResetIoErrorLogger
0x1400d2178  mov     rax, [r14]
0x1400d217b  mov     rax, [rax+218h]
0x1400d2182  test    rax, rax
0x1400d2185  jz      short loc_1400D2200
0x1400d2187  mov     rcx, r14
0x1400d218a  call    _guard_dispatch_icall
0x1400d218f  mov     ebp, eax
0x1400d2191  test    eax, eax
0x1400d2193  jns     short loc_1400D2200
0x1400d2195  mov     ecx, cs:dword_140087708
0x1400d219b  cmp     ecx, 2
0x1400d219e  jbe     short loc_1400D21E2
0x1400d21a0  mov     edx, 80000h
0x1400d21a5  lea     rcx, dword_140087708
0x1400d21ac  call    _tlgKeywordOn
0x1400d21b1  test    al, al
0x1400d21b3  jz      short loc_1400D21E2
0x1400d21b5  lea     rax, aLogStatus0x08x_3; "Log status 0x%08X"
0x1400d21bc  mov     dword ptr [rsp+68h+var_40], ebp; char
0x1400d21c0  mov     edx, 210h; int
0x1400d21c5  mov     [rsp+68h+var_48], rax; char *
0x1400d21ca  mov     r9d, 80000h; int
0x1400d21d0  lea     rcx, aVhdmpicomplete_15; "VhdmpiCompleteRecoveryRequestV2"
0x1400d21d7  mov     r8d, 2; int
0x1400d21dd  call    TraceEvents
0x1400d21e2  cmp     dword ptr [rbx+78h], 0
0x1400d21e6  jl      short loc_1400D2200
0x1400d21e8  mov     edx, ebp
0x1400d21ea  mov     [rbx+78h], ebp
0x1400d21ed  mov     rcx, r14
0x1400d21f0  call    VhdmpiBackingStoreIoErrorIsRecoverable
0x1400d21f5  test    al, al
0x1400d21f7  jz      short loc_1400D2200
0x1400d21f9  mov     dword ptr [rbx+78h], 0C000022Dh
0x1400d2200  mov     r14, [r14+478h]
0x1400d2207  test    r14, r14
0x1400d220a  jnz     loc_1400D216A
0x1400d2210  mov     rcx, r12
0x1400d2213  call    VhdmpiReleasePassiveLock
0x1400d2218  mov     ecx, [rbx+78h]
0x1400d221b  test    ecx, ecx
0x1400d221d  js      short loc_1400D2239
0x1400d221f  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400d2226  jz      short loc_1400D2269
0x1400d2228  mov     dword ptr [rsp+68h+var_40], 0
0x1400d2230  lea     rdx, VhdRecoveryRequestSuccess
0x1400d2237  jmp     short loc_1400D224D
0x1400d2239  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400d2240  jz      short loc_1400D2269
0x1400d2242  mov     dword ptr [rsp+68h+var_40], ecx
0x1400d2246  lea     rdx, VhdRecoveryRequestError
0x1400d224d  mov     r9, [rsi+90h]
0x1400d2254  lea     rax, [r9+26Ch]
0x1400d225b  mov     r9, [r9+78h]
0x1400d225f  mov     [rsp+68h+var_48], rax
0x1400d2264  call    McTemplateK0zjq_EtwWriteTransfer
0x1400d2269  mov     edx, 2D1A80h
0x1400d226e  mov     rcx, r15
0x1400d2271  call    VhdmpiDequeueControlDeviceIoctl
0x1400d2276  mov     rbp, rax
0x1400d2279  test    rax, rax
0x1400d227c  jz      short loc_1400D22C6
0x1400d227e  lea     rcx, [r15+108h]; RunRef
0x1400d2285  call    cs:__imp_ExReleaseRundownProtection
0x1400d228c  nop     dword ptr [rax+rax+00h]
0x1400d2291  mov     qword ptr [rbp+38h], 0
0x1400d2299  xor     edx, edx; PriorityBoost
0x1400d229b  mov     ecx, [rbx+78h]
0x1400d229e  mov     [rbp+30h], ecx
0x1400d22a1  mov     rcx, rbp; Irp
0x1400d22a4  call    cs:__imp_IofCompleteRequest
0x1400d22ab  nop     dword ptr [rax+rax+00h]
0x1400d22b0  mov     edx, 71444856h; Tag
0x1400d22b5  mov     rcx, rbx; P
0x1400d22b8  call    cs:__imp_ExFreePoolWithTag
0x1400d22bf  nop     dword ptr [rax+rax+00h]
0x1400d22c4  jmp     short loc_1400D22DB
0x1400d22c6  lea     rcx, [rbx+40h]; Event
0x1400d22ca  xor     r8d, r8d; Wait
0x1400d22cd  xor     edx, edx; Increment
0x1400d22cf  call    cs:__imp_KeSetEvent
0x1400d22d6  nop     dword ptr [rax+rax+00h]
0x1400d22db  lea     rbx, [rsi+0B8h]
0x1400d22e2  mov     rcx, rbx
0x1400d22e5  call    VhdmpiAcquirePassiveLock
0x1400d22ea  dec     dword ptr [rsi+100h]
0x1400d22f0  mov     rcx, rbx
0x1400d22f3  mov     qword ptr [rsi+0F8h], 0
0x1400d22fe  call    VhdmpiReleasePassiveLock
0x1400d2303  add     rsp, 38h
0x1400d2307  pop     r15
0x1400d2309  pop     r14
0x1400d230b  pop     r12
0x1400d230d  pop     rsi
0x1400d230e  pop     rbp
0x1400d230f  pop     rbx
0x1400d2310  retn
```
