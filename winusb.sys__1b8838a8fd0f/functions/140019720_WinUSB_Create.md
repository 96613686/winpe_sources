# WinUSB_Create

- ea: `0x140019720`
- end: `0x140019938`
- name: `WinUSB_Create`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140010700`
- `0x140019720`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019811`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019811`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019805`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140019805`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400197a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400197a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400197b7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400197b7`

## pseudocode

```c
__int64 __fastcall WinUSB_Create(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbp
  __int64 v6; // rdi
  __int64 v7; // rax
  int v8; // esi
  int v9; // edx
  bool v10; // zf
  __int64 v11; // rax
  __int64 result; // rax
  int v13; // edx

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      52,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400150F0);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 336));
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 336))(WdfDriverGlobals, a1);
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1368))(WdfDriverGlobals, v7);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 336));
  KeLeaveCriticalRegion();
  if ( v8 >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        12,
        54,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
    }
    v10 = g_pIoGetInitiatorProcess == 0;
    *(_WORD *)(v6 + 312) = 0;
    if ( !v10 )
    {
      v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1120))(WdfDriverGlobals, a3);
      *(_QWORD *)(v6 + 392) = ((__int64 (__fastcall *)(__int64))g_pIoGetInitiatorProcess)(v11);
    }
    *(_BYTE *)(v6 + 144) = 1;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      12,
      53,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
      v8);
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             v4,
             (unsigned int)v8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v13) = 5;
      return WPP_RECORDER_SF_d(
               WPP_GLOBAL_Control->DeviceExtension,
               v13,
               1,
               55,
               (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
               v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019720  push    rbx
0x140019722  push    rbp
0x140019723  push    rsi
0x140019724  push    rdi
0x140019725  push    r12
0x140019727  push    r13
0x140019729  push    r14
0x14001972b  push    r15
0x14001972d  sub     rsp, 38h
0x140019731  mov     r14, r8
0x140019734  mov     rbp, rdx
0x140019737  mov     rsi, rcx
0x14001973a  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019741  xor     r15d, r15d
0x140019744  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001974b  lea     r13, WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids
0x140019752  jz      short loc_14001977A
0x140019754  mov     rcx, cs:WPP_GLOBAL_Control
0x14001975b  cmp     [rcx+48h], r15w
0x140019760  jz      short loc_14001977A
0x140019762  mov     rcx, [rcx+40h]
0x140019766  lea     r9d, [r15+34h]
0x14001976a  lea     r8d, [r15+1]
0x14001976e  mov     [rsp+78h+var_58], r13
0x140019773  mov     dl, 5
0x140019775  call    WPP_RECORDER_SF_
0x14001977a  mov     rax, cs:WdfFunctions_01015
0x140019781  mov     rdx, rsi
0x140019784  mov     r8, cs:off_1400150F0
0x14001978b  mov     rcx, cs:WdfDriverGlobals
0x140019792  mov     rax, [rax+650h]
0x140019799  call    _guard_dispatch_icall
0x14001979e  mov     rdi, rax
0x1400197a1  call    cs:__imp_KeEnterCriticalRegion
0x1400197a8  nop     dword ptr [rax+rax+00h]
0x1400197ad  lea     rbx, [rdi+150h]
0x1400197b4  mov     rcx, rbx; FastMutex
0x1400197b7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400197be  nop     dword ptr [rax+rax+00h]
0x1400197c3  mov     rcx, cs:WdfFunctions_01015
0x1400197ca  mov     rdx, rsi
0x1400197cd  mov     rax, [rcx+150h]
0x1400197d4  mov     rcx, cs:WdfDriverGlobals
0x1400197db  call    _guard_dispatch_icall
0x1400197e0  mov     rdx, cs:WdfFunctions_01015
0x1400197e7  mov     rcx, cs:WdfDriverGlobals
0x1400197ee  mov     r8, [rdx+558h]
0x1400197f5  mov     rdx, rax
0x1400197f8  mov     rax, r8
0x1400197fb  call    _guard_dispatch_icall
0x140019800  mov     rcx, rbx; FastMutex
0x140019803  mov     esi, eax
0x140019805  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001980c  nop     dword ptr [rax+rax+00h]
0x140019811  call    cs:__imp_KeLeaveCriticalRegion
0x140019818  nop     dword ptr [rax+rax+00h]
0x14001981d  test    esi, esi
0x14001981f  jns     short loc_140019855
0x140019821  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019828  jz      loc_1400198D1
0x14001982e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019835  mov     r9d, 35h ; '5'
0x14001983b  mov     [rsp+78h+var_50], esi
0x14001983f  mov     dl, 2
0x140019841  mov     [rsp+78h+var_58], r13
0x140019846  mov     rcx, [rcx+40h]
0x14001984a  lea     r8d, [r9-29h]
0x14001984e  call    WPP_RECORDER_SF_d
0x140019853  jmp     short loc_1400198D1
0x140019855  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14001985c  jz      short loc_140019886
0x14001985e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019865  cmp     [rcx+48h], r15w
0x14001986a  jz      short loc_140019886
0x14001986c  mov     rcx, [rcx+40h]
0x140019870  mov     r9d, 36h ; '6'
0x140019876  mov     dl, 5
0x140019878  mov     [rsp+78h+var_58], r13
0x14001987d  lea     r8d, [r9-2Ah]
0x140019881  call    WPP_RECORDER_SF_
0x140019886  cmp     cs:g_pIoGetInitiatorProcess, r15
0x14001988d  mov     [rdi+138h], r15w
0x140019895  jz      short loc_1400198CA
0x140019897  mov     rax, cs:WdfFunctions_01015
0x14001989e  mov     rdx, r14
0x1400198a1  mov     rcx, cs:WdfDriverGlobals
0x1400198a8  mov     rax, [rax+460h]
0x1400198af  call    _guard_dispatch_icall
0x1400198b4  mov     rcx, rax
0x1400198b7  mov     rax, cs:g_pIoGetInitiatorProcess
0x1400198be  call    _guard_dispatch_icall
0x1400198c3  mov     [rdi+188h], rax
0x1400198ca  mov     byte ptr [rdi+90h], 1
0x1400198d1  mov     rax, cs:WdfFunctions_01015
0x1400198d8  mov     r8d, esi
0x1400198db  mov     rcx, cs:WdfDriverGlobals
0x1400198e2  mov     rdx, rbp
0x1400198e5  mov     rax, [rax+838h]
0x1400198ec  call    _guard_dispatch_icall
0x1400198f1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400198f8  jz      short loc_140019926
0x1400198fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140019901  cmp     [rcx+48h], r15w
0x140019906  jz      short loc_140019926
0x140019908  mov     rcx, [rcx+40h]
0x14001990c  mov     r9d, 37h ; '7'
0x140019912  mov     [rsp+78h+var_50], esi
0x140019916  mov     dl, 5
0x140019918  mov     [rsp+78h+var_58], r13
0x14001991d  lea     r8d, [r9-36h]
0x140019921  call    WPP_RECORDER_SF_d
0x140019926  add     rsp, 38h
0x14001992a  pop     r15
0x14001992c  pop     r14
0x14001992e  pop     r13
0x140019930  pop     r12
0x140019932  pop     rdi
0x140019933  pop     rsi
0x140019934  pop     rbp
0x140019935  pop     rbx
0x140019936  retn
```
