# LowResourceNotificationCallback

- ea: `0x140008124`
- end: `0x140008277`
- name: `LowResourceNotificationCallback`
- size: `339`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006f30`

## callees

- `0x140001010`
- `0x140001110`
- `0x140001480`
- `0x140002030`
- `0x1400021c0`
- `0x140004650`
- `0x140004bd0`
- `0x140008124`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400081c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400081c2`

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
0x140008124  mov     [rsp-8+arg_10], rbx
0x140008129  push    rbp
0x14000812a  push    rsi
0x14000812b  push    rdi
0x14000812c  lea     rbp, [rsp-47h]
0x140008131  sub     rsp, 0A0h
0x140008138  mov     rax, cs:__security_cookie
0x14000813f  xor     rax, rsp
0x140008142  mov     [rbp+57h+var_20], rax
0x140008146  mov     rbx, rdx
0x140008149  mov     rsi, rcx
0x14000814c  call    QueryServiceHeapInformation
0x140008151  test    eax, eax
0x140008153  jnz     short loc_140008173
0x140008155  mov     cs:TelemetryState, 1
0x14000815f  call    DoSvchostHeapInfoTelemetry
0x140008164  mov     cs:TelemetryState, 2
0x14000816e  call    ArmTheServiceMemoryTracingTimer
0x140008173  mov     ecx, cs:ServiceCount
0x140008179  cmp     ecx, 1
0x14000817c  jz      short loc_1400081DB
0x14000817e  xor     edi, edi
0x140008180  mov     dword ptr [rbx+8], 0
0x140008187  test    ecx, ecx
0x140008189  jz      short loc_1400081E2
0x14000818b  mov     rdx, cs:ServiceArray
0x140008192  lea     r8, [rdi+rdi*2]
0x140008196  shl     r8, 5
0x14000819a  cmp     dword ptr [r8+rdx+30h], 0
0x1400081a0  jz      short loc_1400081D3
0x1400081a2  mov     rax, [rbx]
0x1400081a5  cmp     [r8+rdx+48h], rax
0x1400081aa  jb      short loc_1400081D3
0x1400081ac  mov     r8, [r8+rdx]; lpString2
0x1400081b0  or      r9d, 0FFFFFFFFh; cchCount2
0x1400081b4  or      edx, r9d; cchCount1
0x1400081b7  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x1400081bf  mov     rcx, rsi; lpString1
0x1400081c2  call    cs:__imp_CompareStringOrdinal
0x1400081c8  cmp     eax, 2
0x1400081cb  jz      short loc_1400081DB
0x1400081cd  mov     ecx, cs:ServiceCount
0x1400081d3  inc     edi
0x1400081d5  cmp     edi, ecx
0x1400081d7  jb      short loc_14000818B
0x1400081d9  jmp     short loc_1400081E2
0x1400081db  mov     dword ptr [rbx+8], 1
0x1400081e2  mov     eax, cs:dword_14000F000
0x1400081e8  cmp     eax, 5
0x1400081eb  jbe     short loc_140008256
0x1400081ed  mov     rdx, 400000000000h
0x1400081f7  call    _tlgKeywordOn
0x1400081fc  test    al, al
0x1400081fe  jz      short loc_140008256
0x140008200  mov     rdx, rsi
0x140008203  lea     rcx, [rbp+57h+var_50]
0x140008207  call    _tlgCreate1Sz_wchar_t
0x14000820c  mov     rcx, [rbx]; int
0x14000820f  lea     rax, [rbp+57h+var_78]
0x140008213  mov     [rbp+57h+var_40], rax
0x140008217  lea     rdx, dword_14000BBD5; int
0x14000821e  mov     eax, [rbx+8]
0x140008221  mov     [rbp+57h+var_80], eax
0x140008224  lea     rax, [rbp+57h+var_80]
0x140008228  mov     [rbp+57h+var_30], rax
0x14000822c  lea     rax, [rbp+57h+var_70]
0x140008230  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x140008235  mov     [rsp+0B0h+bIgnoreCase], 5; ULONG
0x14000823d  mov     [rbp+57h+var_78], rcx
0x140008241  mov     [rbp+57h+var_38], 8
0x140008249  mov     [rbp+57h+var_28], 4
0x140008251  call    _tlgWriteTransfer_EventWriteTransfer
0x140008256  xor     eax, eax
0x140008258  mov     rcx, [rbp+57h+var_20]
0x14000825c  xor     rcx, rsp; StackCookie
0x14000825f  call    __security_check_cookie
0x140008264  mov     rbx, [rsp+0B0h+arg_10]
0x14000826c  add     rsp, 0A0h
0x140008273  pop     rdi
0x140008274  pop     rsi
0x140008275  pop     rbp
0x140008276  retn
```
