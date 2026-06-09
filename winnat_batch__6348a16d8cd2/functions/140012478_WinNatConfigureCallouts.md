# WinNatConfigureCallouts

- ea: `0x140012478`
- end: `0x14001266c`
- name: `WinNatConfigureCallouts`
- size: `500`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012100`
- `0x140012b9c`

## callees

- `0x14000caa0`
- `0x140012478`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `fwpkclnt!FwpmEngineClose0` at `0x140012641`
- `fwpkclnt!FwpmEngineClose0` at `0x140012641`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x1400125ed`
- `fwpkclnt!FwpmCalloutDeleteByKey0` at `0x1400125ed`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012607`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012630`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012607`
- `fwpkclnt!FwpsCalloutUnregisterByKey0` at `0x140012630`
- `fwpkclnt!FwpmCalloutAdd0` at `0x1400125c5`
- `fwpkclnt!FwpmCalloutAdd0` at `0x1400125c5`
- `fwpkclnt!FwpsCalloutRegister0` at `0x140012570`
- `fwpkclnt!FwpsCalloutRegister0` at `0x140012570`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400124dc`
- `fwpkclnt!FwpmEngineOpen0` at `0x1400124dc`

## pseudocode

```c
NTSTATUS __fastcall WinNatConfigureCallouts(char a1)
{
  NTSTATUS result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  NTSTATUS v7; // edi
  __int64 i; // rsi
  char v9; // al
  GUID *v10; // rax
  GUID v11; // xmm0
  GUID v12; // xmm0
  GUID *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  HANDLE engineHandle; // [rsp+30h] [rbp-89h] BYREF
  FWPS_CALLOUT0 callout; // [rsp+38h] [rbp-81h] BYREF
  FWPM_CALLOUT0 v20; // [rsp+70h] [rbp-49h] BYREF

  engineHandle = 0;
  memset(&callout, 0, sizeof(callout));
  memset(&v20, 0, sizeof(v20));
  result = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v7 = result;
  if ( result >= 0 )
  {
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      v9 = WinNatCallouts[9 * i + 8] & 1;
      if ( a1 )
      {
        if ( v9 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5, v6);
        v10 = (GUID *)WinNatCallouts[9 * i + 1];
        memset(&callout, 0, sizeof(callout));
        v11 = *v10;
        callout.classifyFn = (FWPS_CALLOUT_CLASSIFY_FN0)WinNatCallouts[9 * i + 6];
        callout.notifyFn = (FWPS_CALLOUT_NOTIFY_FN0)WinNatCallouts[9 * i + 7];
        callout.calloutKey = v11;
        callout.flowDeleteFn = 0;
        v7 = FwpsCalloutRegister0(deviceObject, &callout, (UINT32 *)&WinNatCallouts[9 * i]);
        if ( v7 < 0 )
          break;
        v12 = *(GUID *)WinNatCallouts[9 * i + 1];
        v20.displayData.name = L"Windows NAT forward layer callout";
        v20.displayData.description = L"Performs network adress translation";
        v13 = (GUID *)WinNatCallouts[9 * i + 3];
        v20.calloutKey = v12;
        v20.applicableLayer = *v13;
        v7 = FwpmCalloutAdd0(engineHandle, &v20, 0, 0);
        if ( v7 < 0 )
        {
          FwpsCalloutUnregisterByKey0((const GUID *)WinNatCallouts[9 * i + 1]);
          break;
        }
        LOBYTE(WinNatCallouts[9 * i + 8]) |= 1u;
      }
      else if ( v9 )
      {
        if ( FwpmCalloutDeleteByKey0(engineHandle, (const GUID *)WinNatCallouts[9 * i + 1]) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14, v16, v17);
        v7 = FwpsCalloutUnregisterByKey0((const GUID *)WinNatCallouts[9 * i + 1]);
        if ( v7 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5, v6);
        LOBYTE(WinNatCallouts[9 * i + 8]) &= ~1u;
      }
    }
    FwpmEngineClose0(engineHandle);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140012478  push    rbp
0x14001247a  push    rbx
0x14001247b  push    rsi
0x14001247c  push    rdi
0x14001247d  push    r14
0x14001247f  push    r15
0x140012481  lea     rbp, [rsp-2Fh]
0x140012486  sub     rsp, 0E8h
0x14001248d  mov     rax, cs:__security_cookie
0x140012494  xor     rax, rsp
0x140012497  mov     [rbp+57h+var_40], rax
0x14001249b  xorps   xmm0, xmm0
0x14001249e  mov     [rsp+110h+var_E0], 0
0x1400124a7  xor     edx, edx; Val
0x1400124a9  mov     r14b, cl
0x1400124ac  lea     rcx, [rbp+57h+var_A0]; void *
0x1400124b0  movups  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x1400124b5  lea     r8d, [rdx+58h]; Size
0x1400124b9  movups  xmmword ptr [rbp+57h+callout.flags], xmm0
0x1400124bd  movups  xmmword ptr [rbp+57h+callout.notifyFn], xmm0
0x1400124c1  call    memset
0x1400124c6  xor     r9d, r9d; session
0x1400124c9  lea     rax, [rsp+110h+var_E0]
0x1400124ce  xor     r8d, r8d; authIdentity
0x1400124d1  mov     [rsp+110h+engineHandle], rax; engineHandle
0x1400124d6  xor     ecx, ecx; serverName
0x1400124d8  lea     edx, [r9+0Ah]; authnService
0x1400124dc  call    cs:__imp_FwpmEngineOpen0
0x1400124e3  nop     dword ptr [rax+rax+00h]
0x1400124e8  mov     edi, eax
0x1400124ea  test    eax, eax
0x1400124ec  js      loc_14001264F
0x1400124f2  xor     esi, esi
0x1400124f4  lea     r15, WinNatCallouts
0x1400124fb  cmp     esi, 3
0x1400124fe  jnb     loc_14001263C
0x140012504  lea     rbx, [rsi+rsi*8]
0x140012508  mov     al, [r15+rbx*8+40h]
0x14001250d  and     al, 1
0x14001250f  test    r14b, r14b
0x140012512  jz      loc_1400125DF
0x140012518  test    al, al
0x14001251a  jz      short loc_140012521
0x14001251c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012521  mov     rax, [r15+rbx*8+8]
0x140012526  lea     r8, [r15+rbx*8]; calloutId
0x14001252a  mov     rcx, cs:deviceObject; deviceObject
0x140012531  lea     rdx, [rsp+110h+callout]; callout
0x140012536  xorps   xmm0, xmm0
0x140012539  movups  xmmword ptr [rbp+57h+callout.flags], xmm0
0x14001253d  movups  xmmword ptr [rbp+57h+callout.notifyFn], xmm0
0x140012541  movups  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x140012546  movups  xmm0, xmmword ptr [rax]
0x140012549  mov     rax, [r15+rbx*8+30h]
0x14001254e  mov     [rbp+57h+callout.classifyFn], rax
0x140012552  mov     rax, [r15+rbx*8+38h]
0x140012557  mov     [rbp+57h+callout.notifyFn], rax
0x14001255b  movdqu  xmmword ptr [rsp+110h+callout.calloutKey.Data1], xmm0
0x140012561  mov     [rbp+57h+callout.flags], 0
0x140012568  mov     [rbp+57h+callout.flowDeleteFn], 0
0x140012570  call    cs:__imp_FwpsCalloutRegister0
0x140012577  nop     dword ptr [rax+rax+00h]
0x14001257c  mov     edi, eax
0x14001257e  test    eax, eax
0x140012580  js      loc_14001263C
0x140012586  mov     rax, [r15+rbx*8+8]
0x14001258b  lea     rdx, [rbp+57h+var_A0]; callout
0x14001258f  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x140012594  xor     r9d, r9d; id
0x140012597  xor     r8d, r8d; sd
0x14001259a  movups  xmm0, xmmword ptr [rax]
0x14001259d  lea     rax, aWindowsNatForw_1; "Windows NAT forward layer callout"
0x1400125a4  mov     [rbp+57h+var_A0.displayData.name], rax
0x1400125a8  lea     rax, aPerformsNetwor; "Performs network adress translation"
0x1400125af  mov     [rbp+57h+var_A0.displayData.description], rax
0x1400125b3  mov     rax, [r15+rbx*8+18h]
0x1400125b8  movdqu  xmmword ptr [rbp+57h+var_A0.calloutKey.Data1], xmm0
0x1400125bd  movups  xmm0, xmmword ptr [rax]
0x1400125c0  movdqu  xmmword ptr [rbp+57h+var_A0.applicableLayer.Data1], xmm0
0x1400125c5  call    cs:__imp_FwpmCalloutAdd0
0x1400125cc  nop     dword ptr [rax+rax+00h]
0x1400125d1  mov     edi, eax
0x1400125d3  test    eax, eax
0x1400125d5  js      short loc_14001262B
0x1400125d7  or      byte ptr [r15+rbx*8+40h], 1
0x1400125dd  jmp     short loc_140012624
0x1400125df  test    al, al
0x1400125e1  jz      short loc_140012624
0x1400125e3  mov     rdx, [r15+rbx*8+8]; key
0x1400125e8  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x1400125ed  call    cs:__imp_FwpmCalloutDeleteByKey0
0x1400125f4  nop     dword ptr [rax+rax+00h]
0x1400125f9  test    eax, eax
0x1400125fb  jns     short loc_140012602
0x1400125fd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012602  mov     rcx, [r15+rbx*8+8]; calloutKey
0x140012607  call    cs:__imp_FwpsCalloutUnregisterByKey0
0x14001260e  nop     dword ptr [rax+rax+00h]
0x140012613  mov     edi, eax
0x140012615  test    eax, eax
0x140012617  jns     short loc_14001261E
0x140012619  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001261e  and     byte ptr [r15+rbx*8+40h], 0FEh
0x140012624  inc     esi
0x140012626  jmp     loc_1400124FB
0x14001262b  mov     rcx, [r15+rbx*8+8]; calloutKey
0x140012630  call    cs:__imp_FwpsCalloutUnregisterByKey0
0x140012637  nop     dword ptr [rax+rax+00h]
0x14001263c  mov     rcx, [rsp+110h+var_E0]; engineHandle
0x140012641  call    cs:__imp_FwpmEngineClose0
0x140012648  nop     dword ptr [rax+rax+00h]
0x14001264d  mov     eax, edi
0x14001264f  mov     rcx, [rbp+57h+var_40]
0x140012653  xor     rcx, rsp; StackCookie
0x140012656  call    __security_check_cookie
0x14001265b  add     rsp, 0E8h
0x140012662  pop     r15
0x140012664  pop     r14
0x140012666  pop     rdi
0x140012667  pop     rsi
0x140012668  pop     rbx
0x140012669  pop     rbp
0x14001266a  retn
```
