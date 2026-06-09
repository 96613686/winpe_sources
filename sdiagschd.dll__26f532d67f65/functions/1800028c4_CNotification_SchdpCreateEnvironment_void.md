# CNotification::SchdpCreateEnvironment(void * *)

- ea: `0x1800028c4`
- end: `0x180002b80`
- name: `?SchdpCreateEnvironment@CNotification@@AEAAJPEAPEAX@Z`
- size: `700`
- prototype: `__int64 __fastcall(CNotification *__hidden this, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a94`

## callees

- `0x1800028c4`
- `0x18000b13c`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180002b28`
- `ntdll!RtlDestroyEnvironment` at `0x180002b28`
- `ntdll!RtlSetEnvironmentVariable` at `0x180002a83`
- `ntdll!RtlSetEnvironmentVariable` at `0x180002a83`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800029dd`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002a46`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800029dd`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002a46`
- `ntdll!RtlNtStatusToDosError` at `0x180002913`
- `ntdll!RtlNtStatusToDosError` at `0x1800029ef`
- `ntdll!RtlNtStatusToDosError` at `0x180002a58`
- `ntdll!RtlNtStatusToDosError` at `0x180002a99`
- `ntdll!RtlNtStatusToDosError` at `0x180002913`
- `ntdll!RtlNtStatusToDosError` at `0x1800029ef`
- `ntdll!RtlNtStatusToDosError` at `0x180002a58`
- `ntdll!RtlNtStatusToDosError` at `0x180002a99`
- `ntdll!RtlCreateEnvironment` at `0x180002901`
- `ntdll!RtlCreateEnvironment` at `0x180002901`
- `OLEAUT32!__imp_SysFreeString` at `0x180002981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000299b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b42`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002981`
- `OLEAUT32!__imp_SysFreeString` at `0x18000299b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b42`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b5c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800029bf`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180002a28`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800029bf`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180002a28`

## string_xrefs

- `0x180002b0e`: `CNotification::SchdpCreateEnvironment`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpCreateEnvironment(CNotification *this, PWSTR *a2)
{
  int v4; // eax
  signed int v5; // eax
  signed int v6; // ebx
  int v7; // r8d
  PWSTR v8; // rcx
  int v9; // r14d
  int v10; // esi
  SAFEARRAY *v11; // rcx
  HRESULT Element; // eax
  int inited; // eax
  signed int v14; // eax
  SAFEARRAY *v15; // rcx
  HRESULT v16; // eax
  int v17; // eax
  signed int v18; // eax
  int v19; // eax
  signed int v20; // eax
  int v21; // r9d
  LONG rgIndices; // [rsp+20h] [rbp-30h] BYREF
  int v24; // [rsp+24h] [rbp-2Ch]
  BSTR pv; // [rsp+28h] [rbp-28h] BYREF
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-20h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PWSTR Environment; // [rsp+90h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  bstrString = 0;
  pv = 0;
  Environment = 0;
  DestinationString = 0;
  Value = 0;
  v4 = RtlCreateEnvironment(0, &Environment);
  if ( v4 < 0 )
  {
    v5 = RtlNtStatusToDosError(v4);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 570;
LABEL_38:
      v21 = v6;
      goto LABEL_39;
    }
  }
  v8 = Environment;
  if ( !Environment )
  {
    v6 = -2147467261;
    v7 = 571;
    goto LABEL_38;
  }
  v9 = *(_DWORD *)(*((_QWORD *)this + 3) + 24LL);
  if ( (unsigned int)v9 > 0x7FFFFFFF )
  {
    v6 = -2147024362;
    v7 = 578;
    goto LABEL_38;
  }
  v6 = 0;
  v10 = 0;
  if ( v9 <= 0 )
  {
LABEL_31:
    Environment = 0;
    *a2 = v8;
    goto LABEL_40;
  }
  while ( 1 )
  {
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( pv )
    {
      SysFreeString(pv);
      pv = 0;
    }
    v11 = (SAFEARRAY *)*((_QWORD *)this + 3);
    rgIndices = 0;
    v24 = v10;
    Element = SafeArrayGetElement(v11, &rgIndices, &bstrString);
    v6 = Element;
    if ( Element < 0 )
      break;
    inited = RtlInitUnicodeStringEx(&DestinationString, bstrString);
    if ( inited < 0 )
    {
      v14 = RtlNtStatusToDosError(inited);
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 596;
        goto LABEL_38;
      }
    }
    v15 = (SAFEARRAY *)*((_QWORD *)this + 3);
    rgIndices = 1;
    v24 = v10;
    v16 = SafeArrayGetElement(v15, &rgIndices, &pv);
    v6 = v16;
    if ( v16 < 0 )
    {
      v21 = v16;
      v7 = 602;
      goto LABEL_39;
    }
    v17 = RtlInitUnicodeStringEx(&Value, pv);
    if ( v17 < 0 )
    {
      v18 = RtlNtStatusToDosError(v17);
      v6 = v18;
      if ( v18 > 0 )
        v6 = (unsigned __int16)v18 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 606;
        goto LABEL_38;
      }
    }
    v19 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v19 < 0 )
    {
      v20 = RtlNtStatusToDosError(v19);
      v6 = v20;
      if ( v20 > 0 )
        v6 = (unsigned __int16)v20 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 611;
        goto LABEL_38;
      }
    }
    else
    {
      v6 = 0;
    }
    if ( ++v10 >= v9 )
    {
      v8 = Environment;
      goto LABEL_31;
    }
  }
  v21 = Element;
  v7 = 592;
LABEL_39:
  SdpDebugTrace(1u, L"CNotification::SchdpCreateEnvironment", v7, v21);
LABEL_40:
  if ( Environment )
  {
    RtlDestroyEnvironment(Environment);
    Environment = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( pv )
    SysFreeString(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800028c4  mov     [rsp-28h+arg_0], rbx
0x1800028c9  push    rbp
0x1800028ca  push    rsi
0x1800028cb  push    r12
0x1800028cd  push    r14
0x1800028cf  push    r15
0x1800028d1  mov     rbp, rsp
0x1800028d4  sub     rsp, 50h
0x1800028d8  and     [rbp+bstrString], 0
0x1800028dd  mov     r12, rdx
0x1800028e0  and     [rbp+pv], 0
0x1800028e5  lea     rdx, [rbp+Environment]; Environment
0x1800028e9  and     [rbp+Environment], 0
0x1800028ee  mov     r15, rcx
0x1800028f1  xorps   xmm0, xmm0
0x1800028f4  xorps   xmm1, xmm1
0x1800028f7  xor     ecx, ecx; Inherit
0x1800028f9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800028fd  movups  xmmword ptr [rbp+Value.Length], xmm1
0x180002901  call    cs:__imp_RtlCreateEnvironment
0x180002908  nop     dword ptr [rax+rax+00h]
0x18000290d  test    eax, eax
0x18000290f  jns     short loc_18000293D
0x180002911  mov     ecx, eax; Status
0x180002913  call    cs:__imp_RtlNtStatusToDosError
0x18000291a  nop     dword ptr [rax+rax+00h]
0x18000291f  mov     ebx, eax
0x180002921  test    eax, eax
0x180002923  jle     short loc_18000292E
0x180002925  movzx   ebx, ax
0x180002928  or      ebx, 80070000h
0x18000292e  test    ebx, ebx
0x180002930  jns     short loc_18000293D
0x180002932  mov     r8d, 23Ah
0x180002938  jmp     loc_180002B0B
0x18000293d  mov     rcx, [rbp+Environment]
0x180002941  test    rcx, rcx
0x180002944  jnz     short loc_180002956
0x180002946  mov     ebx, 80004003h
0x18000294b  mov     r8d, 23Bh
0x180002951  jmp     loc_180002B0B
0x180002956  mov     rax, [r15+18h]
0x18000295a  mov     r14d, [rax+18h]
0x18000295e  cmp     r14d, 7FFFFFFFh
0x180002965  ja      loc_180002B00
0x18000296b  xor     ebx, ebx
0x18000296d  xor     esi, esi
0x18000296f  test    r14d, r14d
0x180002972  jle     loc_180002AC7
0x180002978  mov     rcx, [rbp+bstrString]; bstrString
0x18000297c  test    rcx, rcx
0x18000297f  jz      short loc_180002992
0x180002981  call    cs:__imp_SysFreeString
0x180002988  nop     dword ptr [rax+rax+00h]
0x18000298d  and     [rbp+bstrString], 0
0x180002992  mov     rcx, [rbp+pv]; bstrString
0x180002996  test    rcx, rcx
0x180002999  jz      short loc_1800029AC
0x18000299b  call    cs:__imp_SysFreeString
0x1800029a2  nop     dword ptr [rax+rax+00h]
0x1800029a7  and     [rbp+pv], 0
0x1800029ac  mov     rcx, [r15+18h]; psa
0x1800029b0  lea     r8, [rbp+bstrString]; pv
0x1800029b4  and     [rbp+rgIndices], 0
0x1800029b8  lea     rdx, [rbp+rgIndices]; rgIndices
0x1800029bc  mov     [rbp+var_2C], esi
0x1800029bf  call    cs:__imp_SafeArrayGetElement
0x1800029c6  nop     dword ptr [rax+rax+00h]
0x1800029cb  mov     ebx, eax
0x1800029cd  test    eax, eax
0x1800029cf  js      loc_180002AF5
0x1800029d5  mov     rdx, [rbp+bstrString]; SourceString
0x1800029d9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800029dd  call    cs:__imp_RtlInitUnicodeStringEx
0x1800029e4  nop     dword ptr [rax+rax+00h]
0x1800029e9  test    eax, eax
0x1800029eb  jns     short loc_180002A12
0x1800029ed  mov     ecx, eax; Status
0x1800029ef  call    cs:__imp_RtlNtStatusToDosError
0x1800029f6  nop     dword ptr [rax+rax+00h]
0x1800029fb  mov     ebx, eax
0x1800029fd  test    eax, eax
0x1800029ff  jle     short loc_180002A0A
0x180002a01  movzx   ebx, ax
0x180002a04  or      ebx, 80070000h
0x180002a0a  test    ebx, ebx
0x180002a0c  js      loc_180002AD2
0x180002a12  mov     rcx, [r15+18h]; psa
0x180002a16  lea     r8, [rbp+pv]; pv
0x180002a1a  lea     rdx, [rbp+rgIndices]; rgIndices
0x180002a1e  mov     [rbp+rgIndices], 1
0x180002a25  mov     [rbp+var_2C], esi
0x180002a28  call    cs:__imp_SafeArrayGetElement
0x180002a2f  nop     dword ptr [rax+rax+00h]
0x180002a34  mov     ebx, eax
0x180002a36  test    eax, eax
0x180002a38  js      loc_180002AEA
0x180002a3e  mov     rdx, [rbp+pv]; SourceString
0x180002a42  lea     rcx, [rbp+Value]; DestinationString
0x180002a46  call    cs:__imp_RtlInitUnicodeStringEx
0x180002a4d  nop     dword ptr [rax+rax+00h]
0x180002a52  test    eax, eax
0x180002a54  jns     short loc_180002A77
0x180002a56  mov     ecx, eax; Status
0x180002a58  call    cs:__imp_RtlNtStatusToDosError
0x180002a5f  nop     dword ptr [rax+rax+00h]
0x180002a64  mov     ebx, eax
0x180002a66  test    eax, eax
0x180002a68  jle     short loc_180002A73
0x180002a6a  movzx   ebx, ax
0x180002a6d  or      ebx, 80070000h
0x180002a73  test    ebx, ebx
0x180002a75  js      short loc_180002ADA
0x180002a77  lea     r8, [rbp+Value]; Value
0x180002a7b  lea     rdx, [rbp+DestinationString]; Name
0x180002a7f  lea     rcx, [rbp+Environment]; Environment
0x180002a83  call    cs:__imp_RtlSetEnvironmentVariable
0x180002a8a  nop     dword ptr [rax+rax+00h]
0x180002a8f  test    eax, eax
0x180002a91  js      short loc_180002A97
0x180002a93  xor     ebx, ebx
0x180002a95  jmp     short loc_180002AB8
0x180002a97  mov     ecx, eax; Status
0x180002a99  call    cs:__imp_RtlNtStatusToDosError
0x180002aa0  nop     dword ptr [rax+rax+00h]
0x180002aa5  mov     ebx, eax
0x180002aa7  test    eax, eax
0x180002aa9  jle     short loc_180002AB4
0x180002aab  movzx   ebx, ax
0x180002aae  or      ebx, 80070000h
0x180002ab4  test    ebx, ebx
0x180002ab6  js      short loc_180002AE2
0x180002ab8  inc     esi
0x180002aba  cmp     esi, r14d
0x180002abd  jl      loc_180002978
0x180002ac3  mov     rcx, [rbp+Environment]
0x180002ac7  and     [rbp+Environment], 0
0x180002acc  mov     [r12], rcx
0x180002ad0  jmp     short loc_180002B1F
0x180002ad2  mov     r8d, 254h
0x180002ad8  jmp     short loc_180002B0B
0x180002ada  mov     r8d, 25Eh
0x180002ae0  jmp     short loc_180002B0B
0x180002ae2  mov     r8d, 263h
0x180002ae8  jmp     short loc_180002B0B
0x180002aea  mov     r9d, eax
0x180002aed  mov     r8d, 25Ah
0x180002af3  jmp     short loc_180002B0E
0x180002af5  mov     r9d, eax
0x180002af8  mov     r8d, 250h
0x180002afe  jmp     short loc_180002B0E
0x180002b00  mov     ebx, 80070216h
0x180002b05  mov     r8d, 242h; int
0x180002b0b  mov     r9d, ebx; int
0x180002b0e  lea     rdx, aCnotificationS_7; "CNotification::SchdpCreateEnvironment"
0x180002b15  mov     ecx, 1; Level
0x180002b1a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002b1f  mov     rcx, [rbp+Environment]; Environment
0x180002b23  test    rcx, rcx
0x180002b26  jz      short loc_180002B39
0x180002b28  call    cs:__imp_RtlDestroyEnvironment
0x180002b2f  nop     dword ptr [rax+rax+00h]
0x180002b34  and     [rbp+Environment], 0
0x180002b39  mov     rcx, [rbp+bstrString]; bstrString
0x180002b3d  test    rcx, rcx
0x180002b40  jz      short loc_180002B53
0x180002b42  call    cs:__imp_SysFreeString
0x180002b49  nop     dword ptr [rax+rax+00h]
0x180002b4e  and     [rbp+bstrString], 0
0x180002b53  mov     rcx, [rbp+pv]; bstrString
0x180002b57  test    rcx, rcx
0x180002b5a  jz      short loc_180002B68
0x180002b5c  call    cs:__imp_SysFreeString
0x180002b63  nop     dword ptr [rax+rax+00h]
0x180002b68  mov     eax, ebx
0x180002b6a  mov     rbx, [rsp+50h+arg_0]
0x180002b72  add     rsp, 50h
0x180002b76  pop     r15
0x180002b78  pop     r14
0x180002b7a  pop     r12
0x180002b7c  pop     rsi
0x180002b7d  pop     rbp
0x180002b7e  retn
```
