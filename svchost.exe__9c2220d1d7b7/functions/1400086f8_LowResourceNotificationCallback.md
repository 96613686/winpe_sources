# LowResourceNotificationCallback

- ea: `0x1400086f8`
- end: `0x140008852`
- name: `LowResourceNotificationCallback`
- size: `346`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007460`

## callees

- `0x140001010`
- `0x140001120`
- `0x1400014b0`
- `0x140002150`
- `0x140002300`
- `0x1400049f0`
- `0x140004f90`
- `0x1400086f8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140008796`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140008796`

## pseudocode

```c
__int64 __fastcall LowResourceNotificationCallback(LPCWCH lpString1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v11; // [rsp+30h] [rbp-29h] BYREF
  __int64 v12; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-19h] BYREF
  char v14[16]; // [rsp+60h] [rbp+7h] BYREF
  __int64 *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  int *v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  if ( !(unsigned int)QueryServiceHeapInformation() )
  {
    TelemetryState = 1;
    DoSvchostHeapInfoTelemetry();
    TelemetryState = 2;
    ArmTheServiceMemoryTracingTimer();
  }
  v4 = (unsigned int)ServiceCount;
  if ( ServiceCount == 1 )
  {
LABEL_11:
    *(_DWORD *)(a2 + 8) = 1;
  }
  else
  {
    v5 = 0;
    for ( *(_DWORD *)(a2 + 8) = 0; (unsigned int)v5 < (unsigned int)v4; v5 = (unsigned int)(v5 + 1) )
    {
      v6 = 96 * v5;
      if ( *(_DWORD *)(96 * v5 + ServiceArray + 48) && *(_QWORD *)(v6 + ServiceArray + 72) >= *(_QWORD *)a2 )
      {
        if ( CompareStringOrdinal(lpString1, -1, *(LPCWCH *)(v6 + ServiceArray), -1, 1) == 2 )
          goto LABEL_11;
        v4 = (unsigned int)ServiceCount;
      }
    }
  }
  if ( (unsigned int)dword_14000F000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    tlgCreate1Sz_wchar_t(v14, lpString1);
    v7 = *(_QWORD *)a2;
    v15 = &v12;
    v11 = *(_DWORD *)(a2 + 8);
    v17 = &v11;
    v12 = v7;
    v16 = 8;
    v18 = 4;
    tlgWriteTransfer_EventWriteTransfer(v7, (unsigned __int8 *)dword_14000BBD5, v8, v9, 5u, &v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1400086f8  mov     [rsp-8+arg_10], rbx
0x1400086fd  push    rbp
0x1400086fe  push    rsi
0x1400086ff  push    rdi
0x140008700  lea     rbp, [rsp-47h]
0x140008705  sub     rsp, 0A0h
0x14000870c  mov     rax, cs:__security_cookie
0x140008713  xor     rax, rsp
0x140008716  mov     [rbp+57h+var_20], rax
0x14000871a  mov     rbx, rdx
0x14000871d  mov     rsi, rcx
0x140008720  call    QueryServiceHeapInformation
0x140008725  test    eax, eax
0x140008727  jnz     short loc_140008747
0x140008729  mov     cs:TelemetryState, 1
0x140008733  call    DoSvchostHeapInfoTelemetry
0x140008738  mov     cs:TelemetryState, 2
0x140008742  call    ArmTheServiceMemoryTracingTimer
0x140008747  mov     ecx, cs:ServiceCount
0x14000874d  cmp     ecx, 1
0x140008750  jz      short loc_1400087B5
0x140008752  xor     edi, edi
0x140008754  mov     dword ptr [rbx+8], 0
0x14000875b  test    ecx, ecx
0x14000875d  jz      short loc_1400087BC
0x14000875f  mov     rdx, cs:ServiceArray
0x140008766  lea     r8, [rdi+rdi*2]
0x14000876a  shl     r8, 5
0x14000876e  cmp     dword ptr [r8+rdx+30h], 0
0x140008774  jz      short loc_1400087AD
0x140008776  mov     rax, [rbx]
0x140008779  cmp     [r8+rdx+48h], rax
0x14000877e  jb      short loc_1400087AD
0x140008780  mov     r8, [r8+rdx]; lpString2
0x140008784  or      r9d, 0FFFFFFFFh; cchCount2
0x140008788  or      edx, r9d; cchCount1
0x14000878b  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x140008793  mov     rcx, rsi; lpString1
0x140008796  call    cs:__imp_CompareStringOrdinal
0x14000879d  nop     dword ptr [rax+rax+00h]
0x1400087a2  cmp     eax, 2
0x1400087a5  jz      short loc_1400087B5
0x1400087a7  mov     ecx, cs:ServiceCount
0x1400087ad  inc     edi
0x1400087af  cmp     edi, ecx
0x1400087b1  jb      short loc_14000875F
0x1400087b3  jmp     short loc_1400087BC
0x1400087b5  mov     dword ptr [rbx+8], 1
0x1400087bc  mov     eax, cs:dword_14000F000
0x1400087c2  cmp     eax, 5
0x1400087c5  jbe     short loc_140008830
0x1400087c7  mov     rdx, 400000000000h
0x1400087d1  call    _tlgKeywordOn
0x1400087d6  test    al, al
0x1400087d8  jz      short loc_140008830
0x1400087da  mov     rdx, rsi
0x1400087dd  lea     rcx, [rbp+57h+var_50]
0x1400087e1  call    _tlgCreate1Sz_wchar_t
0x1400087e6  mov     rcx, [rbx]; int
0x1400087e9  lea     rax, [rbp+57h+var_78]
0x1400087ed  mov     [rbp+57h+var_40], rax
0x1400087f1  lea     rdx, dword_14000BBD5; int
0x1400087f8  mov     eax, [rbx+8]
0x1400087fb  mov     [rbp+57h+var_80], eax
0x1400087fe  lea     rax, [rbp+57h+var_80]
0x140008802  mov     [rbp+57h+var_30], rax
0x140008806  lea     rax, [rbp+57h+var_70]
0x14000880a  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x14000880f  mov     [rsp+0B0h+bIgnoreCase], 5; ULONG
0x140008817  mov     [rbp+57h+var_78], rcx
0x14000881b  mov     [rbp+57h+var_38], 8
0x140008823  mov     [rbp+57h+var_28], 4
0x14000882b  call    _tlgWriteTransfer_EventWriteTransfer
0x140008830  xor     eax, eax
0x140008832  mov     rcx, [rbp+57h+var_20]
0x140008836  xor     rcx, rsp; StackCookie
0x140008839  call    __security_check_cookie
0x14000883e  mov     rbx, [rsp+0B0h+arg_10]
0x140008846  add     rsp, 0A0h
0x14000884d  pop     rdi
0x14000884e  pop     rsi
0x14000884f  pop     rbp
0x140008850  retn
```
