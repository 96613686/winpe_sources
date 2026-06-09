# WinNatConfigureCallouts

- ea: `0x140012db8`
- end: `0x140012fac`
- name: `WinNatConfigureCallouts`
- size: `500`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012a40`
- `0x1400134dc`

## callees

- `0x14000caa0`
- `0x140012db8`
- `0x14001f320`
- `0x14001f980`

## import_xrefs

- `fwpkclnt!FwpmEngineClose0` at `0x140012f81`
- `fwpkclnt!FwpmEngineClose0` at `0x140012f81`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x140012f2d`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x140012f2d`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012f47`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012f70`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012f47`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012f70`
- `fwpkclnt!FwpmCalloutAdd0` at `0x140012f05`
- `fwpkclnt!FwpmCalloutAdd0` at `0x140012f05`
- `fwpkclnt!FwpsCalloutRegister0` at `0x140012eb0`
- `fwpkclnt!FwpsCalloutRegister0` at `0x140012eb0`
- `fwpkclnt!FwpmEngineOpen0` at `0x140012e1c`
- `fwpkclnt!FwpmEngineOpen0` at `0x140012e1c`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureCallouts(char a1)
{
  NTSTATUS result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  NTSTATUS v6; // edi
  __int64 i; // rsi
  char v8; // al
  GUID *v9; // rax
  GUID v10; // xmm0
  GUID v11; // xmm0
  GUID *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  HANDLE engineHandle; // [rsp+30h] [rbp-89h] BYREF
  FWPS_CALLOUT0 callout; // [rsp+38h] [rbp-81h] BYREF
  FWPM_CALLOUT0 v18; // [rsp+70h] [rbp-49h] BYREF

  engineHandle = 0;
  memset(&callout, 0, sizeof(callout));
  memset(&v18, 0, sizeof(v18));
  result = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v6 = result;
  if ( result >= 0 )
  {
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      v8 = WinNatCallouts[9 * i + 8] & 1;
      if ( a1 )
      {
        if ( v8 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
        v9 = (GUID *)WinNatCallouts[9 * i + 1];
        memset(&callout, 0, sizeof(callout));
        v10 = *v9;
        callout.classifyFn = (FWPS_CALLOUT_CLASSIFY_FN0)WinNatCallouts[9 * i + 6];
        callout.notifyFn = (FWPS_CALLOUT_NOTIFY_FN0)WinNatCallouts[9 * i + 7];
        callout.calloutKey = v10;
        callout.flowDeleteFn = 0;
        v6 = FwpsCalloutRegister0(deviceObject, &callout, (UINT32 *)&WinNatCallouts[9 * i]);
        if ( v6 < 0 )
          break;
        v11 = *(GUID *)WinNatCallouts[9 * i + 1];
        v18.displayData.name = L"Windows NAT forward layer callout";
        v18.displayData.description = L"Performs network adress translation";
        v12 = (GUID *)WinNatCallouts[9 * i + 3];
        v18.calloutKey = v11;
        v18.applicableLayer = *v12;
        v6 = FwpmCalloutAdd0(engineHandle, &v18, 0, 0);
        if ( v6 < 0 )
        {
          FwpsCalloutUnregisterByKey0((const GUID *)WinNatCallouts[9 * i + 1]);
          break;
        }
        LOBYTE(WinNatCallouts[9 * i + 8]) |= 1u;
      }
      else if ( v8 )
      {
        if ( FwpmCalloutDeleteByKey0(engineHandle, (const GUID *)WinNatCallouts[9 * i + 1]) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v14, v13, v15);
        v6 = FwpsCalloutUnregisterByKey0((const GUID *)WinNatCallouts[9 * i + 1]);
        if ( v6 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
        LOBYTE(WinNatCallouts[9 * i + 8]) &= ~1u;
      }
    }
    FwpmEngineClose0(engineHandle);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140012db8  push    rbp
0x140012dba  push    rbx
0x140012dbb  push    rsi
0x140012dbc  push    rdi
0x140012dbd  push    r14
0x140012dbf  push    r15
0x140012dc1  lea     rbp, [rsp-2Fh]
0x140012dc6  sub     rsp, 0E8h
0x140012dcd  mov     rax, cs:__security_cookie
0x140012dd4  xor     rax, rsp
0x140012dd7  mov     [rbp+57h+var_40], rax
0x140012ddb  xorps   xmm0, xmm0
0x140012dde  mov     [rsp+110h+var_E0], 0
0x140012de7  xor     edx, edx; Val
0x140012de9  mov     r14b, cl
0x140012dec  lea     rcx, [rbp+57h+var_A0]; void *
0x140012df0  movups  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x140012df5  lea     r8d, [rdx+58h]; Size
0x140012df9  movups  xmmword ptr [rbp+57h+callout.flags], xmm0
0x140012dfd  movups  xmmword ptr [rbp+57h+callout.notifyFn], xmm0
0x140012e01  call    memset
0x140012e06  xor     r9d, r9d; session
0x140012e09  lea     rax, [rsp+110h+var_E0]
0x140012e0e  xor     r8d, r8d; authIdentity
0x140012e11  mov     [rsp+110h+engineHandle], rax; engineHandle
0x140012e16  xor     ecx, ecx; serverName
0x140012e18  lea     edx, [r9+0Ah]; authnService
0x140012e1c  call    cs:__imp_FwpmEngineOpen0
0x140012e23  nop     dword ptr [rax+rax+00h]
0x140012e28  mov     edi, eax
0x140012e2a  test    eax, eax
0x140012e2c  js      loc_140012F8F
0x140012e32  xor     esi, esi
0x140012e34  lea     r15, WinNatCallouts
0x140012e3b  cmp     esi, 3
0x140012e3e  jnb     loc_140012F7C
0x140012e44  lea     rbx, [rsi+rsi*8]
0x140012e48  mov     al, [r15+rbx*8+40h]
0x140012e4d  and     al, 1
0x140012e4f  test    r14b, r14b
0x140012e52  jz      loc_140012F1F
0x140012e58  test    al, al
0x140012e5a  jz      short loc_140012E61
0x140012e5c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012e61  mov     rax, [r15+rbx*8+8]
0x140012e66  lea     r8, [r15+rbx*8]; calloutId
0x140012e6a  mov     rcx, cs:deviceObject; deviceObject
0x140012e71  lea     rdx, [rsp+110h+callout]; callout
0x140012e76  xorps   xmm0, xmm0
0x140012e79  movups  xmmword ptr [rbp+57h+callout.flags], xmm0
0x140012e7d  movups  xmmword ptr [rbp+57h+callout.notifyFn], xmm0
0x140012e81  movups  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x140012e86  movups  xmm0, xmmword ptr [rax]
0x140012e89  mov     rax, [r15+rbx*8+30h]
0x140012e8e  mov     [rbp+57h+callout.classifyFn], rax
0x140012e92  mov     rax, [r15+rbx*8+38h]
0x140012e97  mov     [rbp+57h+callout.notifyFn], rax
0x140012e9b  movdqu  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x140012ea1  mov     [rbp+57h+callout.flags], 0
0x140012ea8  mov     [rbp+57h+callout.flowDeleteFn], 0
0x140012eb0  call    cs:__imp_FwpsCalloutRegister0
0x140012eb7  nop     dword ptr [rax+rax+00h]
0x140012ebc  mov     edi, eax
0x140012ebe  test    eax, eax
0x140012ec0  js      loc_140012F7C
0x140012ec6  mov     rax, [r15+rbx*8+8]
0x140012ecb  lea     rdx, [rbp+57h+var_A0]; callout
0x140012ecf  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x140012ed4  xor     r9d, r9d; id
0x140012ed7  xor     r8d, r8d; sd
0x140012eda  movups  xmm0, xmmword ptr [rax]
0x140012edd  lea     rax, aWindowsNatForw_1; "Windows NAT forward layer callout"
0x140012ee4  mov     [rbp+57h+var_A0.displayData.name], rax
0x140012ee8  lea     rax, aPerformsNetwor; "Performs network adress translation"
0x140012eef  mov     [rbp+57h+var_A0.displayData.description], rax
0x140012ef3  mov     rax, [r15+rbx*8+18h]
0x140012ef8  movdqu  xmmword ptr [rbp+57h+var_A0.calloutKey.Data1], xmm0
0x140012efd  movups  xmm0, xmmword ptr [rax]
0x140012f00  movdqu  xmmword ptr [rbp+57h+var_A0.applicableLayer.Data1], xmm0
0x140012f05  call    cs:__imp_FwpmCalloutAdd0
0x140012f0c  nop     dword ptr [rax+rax+00h]
0x140012f11  mov     edi, eax
0x140012f13  test    eax, eax
0x140012f15  js      short loc_140012F6B
0x140012f17  or      byte ptr [r15+rbx*8+40h], 1
0x140012f1d  jmp     short loc_140012F64
0x140012f1f  test    al, al
0x140012f21  jz      short loc_140012F64
0x140012f23  mov     rdx, [r15+rbx*8+8]; key
0x140012f28  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x140012f2d  call    cs:__imp_FwpmCalloutDeleteByKey0
0x140012f34  nop     dword ptr [rax+rax+00h]
0x140012f39  test    eax, eax
0x140012f3b  jns     short loc_140012F42
0x140012f3d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012f42  mov     rcx, [r15+rbx*8+8]; calloutKey
0x140012f47  call    cs:__imp_FwpsCalloutUnregisterByKey0
0x140012f4e  nop     dword ptr [rax+rax+00h]
0x140012f53  mov     edi, eax
0x140012f55  test    eax, eax
0x140012f57  jns     short loc_140012F5E
0x140012f59  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012f5e  and     byte ptr [r15+rbx*8+40h], 0FEh
0x140012f64  inc     esi
0x140012f66  jmp     loc_140012E3B
0x140012f6b  mov     rcx, [r15+rbx*8+8]; calloutKey
0x140012f70  call    cs:__imp_FwpsCalloutUnregisterByKey0
0x140012f77  nop     dword ptr [rax+rax+00h]
0x140012f7c  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x140012f81  call    cs:__imp_FwpmEngineClose0
0x140012f88  nop     dword ptr [rax+rax+00h]
0x140012f8d  mov     eax, edi
0x140012f8f  mov     rcx, [rbp+57h+var_40]
0x140012f93  xor     rcx, rsp; StackCookie
0x140012f96  call    __security_check_cookie
0x140012f9b  add     rsp, 0E8h
0x140012fa2  pop     r15
0x140012fa4  pop     r14
0x140012fa6  pop     rdi
0x140012fa7  pop     rsi
0x140012fa8  pop     rbx
0x140012fa9  pop     rbp
0x140012faa  retn
```
