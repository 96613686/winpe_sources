# HUBMISC_WaitForSignal

- ea: `0x1400336a8`
- end: `0x1400337f2`
- name: `HUBMISC_WaitForSignal`
- size: `330`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `16`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004d68`
- `0x14000ce50`
- `0x14000d120`
- `0x14000d580`
- `0x140014f80`
- `0x1400153c0`
- `0x140015610`
- `0x140015a80`
- `0x1400165c0`
- `0x1400178bc`
- `0x140017be0`
- `0x140078bd0`
- `0x140079940`
- `0x14007a4e0`
- `0x140081660`
- `0x140081a00`

## callees

- `0x1400336a8`
- `0x140033ea8`
- `0x140034030`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140033715`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033799`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033715`
- `ntoskrnl!KeWaitForSingleObject` at `0x140033799`
- `ntoskrnl!DbgPrint` at `0x140033747`
- `ntoskrnl!DbgPrint` at `0x140033747`

## string_xrefs

- `0x140033733`: `\nUSBHUB3 Watchdog: Thread 0x%p has waited %d minutes for %s to complete for WDF object 0x%p\n`

## pseudocode

```c
NTSTATUS __fastcall HUBMISC_WaitForSignal(PVOID Object, const char *a2, const void *a3)
{
  int v6; // ebx
  __int64 v7; // rbp
  NTSTATUS result; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int Timeout; // [rsp+20h] [rbp-68h]
  int Timeouta; // [rsp+20h] [rbp-68h]
  union _LARGE_INTEGER v17; // [rsp+A8h] [rbp+20h] BYREF

  v17.QuadPart = 0;
  v6 = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v17.QuadPart = -600000000;
  for ( result = KeWaitForSingleObject(Object, Executive, 0, 0, &v17);
        result == 258;
        result = KeWaitForSingleObject(Object, Executive, 0, 0, &v17) )
  {
    DbgPrint(
      "\nUSBHUB3 Watchdog: Thread 0x%p has waited %d minutes for %s to complete for WDF object 0x%p\n",
      KeGetCurrentThread(),
      ++v6,
      a2,
      a3);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qsqd(
        *(_QWORD *)(v7 + 64),
        v12,
        v13,
        v14,
        Timeouta,
        (char)KeGetCurrentThread(),
        (__int64)a2,
        (char)a3,
        v6);
  }
  if ( result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_dqqs(
             *(_QWORD *)(v7 + 64),
             v9,
             v10,
             v11,
             Timeout,
             result,
             (char)KeGetCurrentThread(),
             (char)a3,
             (__int64)a2);
  return result;
}

```

## disassembly

```asm
0x1400336a8  mov     rax, rsp
0x1400336ab  push    rbx
0x1400336ac  push    rbp
0x1400336ad  push    rsi
0x1400336ae  push    rdi
0x1400336af  push    r14
0x1400336b1  push    r15
0x1400336b3  sub     rsp, 58h
0x1400336b7  mov     qword ptr [rax+20h], 0
0x1400336bf  mov     r14, rcx
0x1400336c2  mov     rax, cs:WdfFunctions_01015
0x1400336c9  mov     rdi, r8
0x1400336cc  mov     rcx, cs:WdfDriverGlobals
0x1400336d3  mov     rsi, rdx
0x1400336d6  mov     r8, cs:off_14006B2C0
0x1400336dd  xor     ebx, ebx
0x1400336df  mov     rax, [rax+650h]
0x1400336e6  mov     rdx, [rcx]
0x1400336e9  call    _guard_dispatch_icall
0x1400336ee  mov     rbp, rax
0x1400336f1  mov     qword ptr [rsp+88h+arg_18], 0FFFFFFFFDC3CBA00h
0x1400336fd  lea     rax, [rsp+88h+arg_18]
0x140033705  xor     r9d, r9d; Alertable
0x140033708  xor     r8d, r8d; WaitMode
0x14003370b  mov     [rsp+88h+Timeout], rax; Timeout
0x140033710  xor     edx, edx; WaitReason
0x140033712  mov     rcx, r14; Object
0x140033715  call    cs:__imp_KeWaitForSingleObject
0x14003371c  nop     dword ptr [rax+rax+00h]
0x140033721  lea     r15, WPP_RECORDER_INITIALIZED
0x140033728  jmp     short loc_1400337A5
0x14003372a  mov     rdx, gs:188h
0x140033733  lea     rcx, aUsbhub3Watchdo; "\nUSBHUB3 Watchdog: Thread 0x%p has wai"...
0x14003373a  inc     ebx
0x14003373c  mov     [rsp+88h+Timeout], rdi
0x140033741  mov     r8d, ebx
0x140033744  mov     r9, rsi
0x140033747  call    cs:__imp_DbgPrint
0x14003374e  nop     dword ptr [rax+rax+00h]
0x140033753  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14003375a  jz      short loc_140033781
0x14003375c  mov     rax, gs:188h
0x140033765  mov     rcx, [rbp+40h]
0x140033769  mov     dword ptr [rsp+88h+var_48], ebx
0x14003376d  mov     [rsp+88h+var_50], rdi
0x140033772  mov     [rsp+88h+var_58], rsi
0x140033777  mov     [rsp+88h+var_60], rax
0x14003377c  call    WPP_RECORDER_SF_qsqd
0x140033781  lea     rax, [rsp+88h+arg_18]
0x140033789  xor     r9d, r9d; Alertable
0x14003378c  xor     r8d, r8d; WaitMode
0x14003378f  mov     [rsp+88h+Timeout], rax; Timeout
0x140033794  xor     edx, edx; WaitReason
0x140033796  mov     rcx, r14; Object
0x140033799  call    cs:__imp_KeWaitForSingleObject
0x1400337a0  nop     dword ptr [rax+rax+00h]
0x1400337a5  mov     ecx, eax
0x1400337a7  cmp     eax, 102h
0x1400337ac  jz      loc_14003372A
0x1400337b2  test    eax, eax
0x1400337b4  jns     short loc_1400337E4
0x1400337b6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400337bd  jz      short loc_1400337E4
0x1400337bf  mov     rax, gs:188h
0x1400337c8  mov     [rsp+88h+var_48], rsi
0x1400337cd  mov     [rsp+88h+var_50], rdi
0x1400337d2  mov     [rsp+88h+var_58], rax
0x1400337d7  mov     dword ptr [rsp+88h+var_60], ecx
0x1400337db  mov     rcx, [rbp+40h]
0x1400337df  call    WPP_RECORDER_SF_dqqs
0x1400337e4  add     rsp, 58h
0x1400337e8  pop     r15
0x1400337ea  pop     r14
0x1400337ec  pop     rdi
0x1400337ed  pop     rsi
0x1400337ee  pop     rbp
0x1400337ef  pop     rbx
0x1400337f0  retn
```
