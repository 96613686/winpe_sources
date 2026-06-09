# LogEventWithErrorParameter

- ea: `0x18000823c`
- end: `0x1800083fc`
- name: `LogEventWithErrorParameter`
- size: `448`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x18000df08`
- `0x18000ebd0`
- `0x18000f6e0`

## callees

- `0x18000823c`
- `0x1800089dc`
- `0x180008b90`
- `0x18000fa00`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083cd`
- `rtutils!RouterLogEventW` at `0x180008369`
- `rtutils!RouterLogEventW` at `0x1800083bc`
- `rtutils!RouterLogEventW` at `0x180008369`
- `rtutils!RouterLogEventW` at `0x1800083bc`
- `rtutils!RouterGetErrorStringW` at `0x1800082d4`
- `rtutils!RouterGetErrorStringW` at `0x1800082d4`

## pseudocode

```c
void __fastcall LogEventWithErrorParameter(DWORD dwMessageId, __int64 a2, DWORD a3, __int64 a4)
{
  DWORD ErrorStringW; // eax
  void *v8; // rcx
  DWORD v9; // r9d
  LPWSTR *p_plpszSubStringArray; // rax
  LPWSTR lpwszErrorString; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h]
  WCHAR WideCharStr[40]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v16[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  if ( *((_QWORD *)SstpSvcGlobals + 9) )
  {
    lpwszErrorString = 0;
    v15 = 0;
    memset_0(v16, 0, sizeof(v16));
    ConvertCorrelationIdToWideChar(WideCharStr);
    plpszSubStringArray = WideCharStr;
    v13 = 0;
    ErrorStringW = RouterGetErrorStringW(a3, &lpwszErrorString);
    if ( ErrorStringW )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString((wchar_t *)&v15, L"Unable to get the error string for (%d): %d", a3, ErrorStringW);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v15);
      }
      v8 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
      if ( a4 )
        RouterLogEventW(v8, 1u, dwMessageId, 1u, &plpszSubStringArray, a3);
      else
        RouterLogEventW(v8, 1u, dwMessageId, 0, 0, a3);
    }
    else
    {
      if ( a4 )
      {
        v9 = 2;
        *(_QWORD *)&v13 = lpwszErrorString;
        p_plpszSubStringArray = &plpszSubStringArray;
      }
      else
      {
        v9 = 1;
        p_plpszSubStringArray = &lpwszErrorString;
      }
      RouterLogEventW(*((HANDLE *)SstpSvcGlobals + 9), 1u, dwMessageId, v9, p_plpszSubStringArray, a3);
      LocalFree(lpwszErrorString);
    }
  }
}

```

## disassembly

```asm
0x18000823c  mov     [rsp-8+arg_8], rbx
0x180008241  push    rbp
0x180008242  push    rsi
0x180008243  push    rdi
0x180008244  lea     rbp, [rsp-7B0h]
0x18000824c  sub     rsp, 8B0h
0x180008253  mov     rax, cs:__security_cookie
0x18000825a  xor     rax, rsp
0x18000825d  mov     [rbp+7C0h+var_20], rax
0x180008264  mov     rax, cs:SstpSvcGlobals
0x18000826b  mov     rsi, r9
0x18000826e  mov     ebx, r8d
0x180008271  mov     edi, ecx
0x180008273  cmp     qword ptr [rax+48h], 0
0x180008278  jz      loc_1800083D9
0x18000827e  xorps   xmm0, xmm0
0x180008281  mov     [rsp+8C0h+lpwszErrorString], 0
0x18000828a  xor     eax, eax
0x18000828c  mov     [rsp+8C0h+var_888], 0
0x180008295  xor     edx, edx; Val
0x180008297  mov     [rbp+7C0h+var_820], eax
0x18000829a  mov     r8d, 7FCh; Size
0x1800082a0  lea     rcx, [rbp+7C0h+var_81C]; void *
0x1800082a4  movups  [rsp+8C0h+var_880], xmm0
0x1800082a9  call    memset_0
0x1800082ae  mov     r8, rsi
0x1800082b1  lea     rcx, [rsp+8C0h+WideCharStr]; lpWideCharStr
0x1800082b6  call    ConvertCorrelationIdToWideChar
0x1800082bb  lea     rax, [rsp+8C0h+WideCharStr]
0x1800082c0  xorps   xmm0, xmm0
0x1800082c3  lea     rdx, [rsp+8C0h+lpwszErrorString]; lplpwszErrorString
0x1800082c8  mov     [rsp+8C0h+var_888], rax
0x1800082cd  mov     ecx, ebx; dwErrorCode
0x1800082cf  movups  [rsp+8C0h+var_880], xmm0
0x1800082d4  call    cs:__imp_RouterGetErrorStringW
0x1800082db  nop     dword ptr [rax+rax+00h]
0x1800082e0  test    eax, eax
0x1800082e2  jz      loc_180008377
0x1800082e8  test    cs:byte_18002E903, 8
0x1800082ef  jz      short loc_18000832D
0x1800082f1  xor     ecx, ecx
0x1800082f3  lea     rdx, aUnableToGetThe_0; "Unable to get the error string for (%d)"...
0x1800082fa  mov     word ptr [rbp+7C0h+var_820], cx
0x1800082fe  mov     r9d, eax
0x180008301  lea     rcx, [rbp+7C0h+var_820]
0x180008305  mov     r8d, ebx
0x180008308  call    FormatRRASErrorString
0x18000830d  test    cs:byte_18002E903, 8
0x180008314  jz      short loc_18000832D
0x180008316  lea     r8, [rbp+7C0h+var_820]
0x18000831a  lea     rdx, RasSSTPSvcTraceError
0x180008321  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008328  call    McTemplateU0z_EventWriteTransfer
0x18000832d  mov     rcx, cs:SstpSvcGlobals
0x180008334  mov     r8d, edi; dwMessageId
0x180008337  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x18000833b  mov     rcx, [rcx+48h]; hLogHandle
0x18000833f  test    rsi, rsi
0x180008342  jz      short loc_180008359
0x180008344  lea     rax, [rsp+8C0h+var_888]
0x180008349  mov     r9d, 1
0x18000834f  mov     [rsp+8C0h+plpszSubStringArray], rax
0x180008354  mov     edx, r9d
0x180008357  jmp     short loc_180008369
0x180008359  xor     r9d, r9d; dwSubStringCount
0x18000835c  mov     [rsp+8C0h+plpszSubStringArray], 0; plpszSubStringArray
0x180008365  lea     edx, [r9+1]; dwEventType
0x180008369  call    cs:__imp_RouterLogEventW
0x180008370  nop     dword ptr [rax+rax+00h]
0x180008375  jmp     short loc_1800083D9
0x180008377  mov     rcx, cs:SstpSvcGlobals
0x18000837e  mov     r8d, edi; dwMessageId
0x180008381  mov     [rsp+8C0h+dwErrorCode], ebx; dwErrorCode
0x180008385  test    rsi, rsi
0x180008388  jz      short loc_1800083A5
0x18000838a  mov     rax, [rsp+8C0h+lpwszErrorString]
0x18000838f  mov     r9d, 2
0x180008395  mov     qword ptr [rsp+8C0h+var_880], rax
0x18000839a  lea     rax, [rsp+8C0h+var_888]
0x18000839f  lea     edx, [r9-1]
0x1800083a3  jmp     short loc_1800083B3
0x1800083a5  mov     r9d, 1; dwSubStringCount
0x1800083ab  lea     rax, [rsp+8C0h+lpwszErrorString]
0x1800083b0  mov     edx, r9d; dwEventType
0x1800083b3  mov     rcx, [rcx+48h]; hLogHandle
0x1800083b7  mov     [rsp+8C0h+plpszSubStringArray], rax; plpszSubStringArray
0x1800083bc  call    cs:__imp_RouterLogEventW
0x1800083c3  nop     dword ptr [rax+rax+00h]
0x1800083c8  mov     rcx, [rsp+8C0h+lpwszErrorString]; hMem
0x1800083cd  call    cs:__imp_LocalFree
0x1800083d4  nop     dword ptr [rax+rax+00h]
0x1800083d9  mov     rcx, [rbp+7C0h+var_20]
0x1800083e0  xor     rcx, rsp; StackCookie
0x1800083e3  call    __security_check_cookie
0x1800083e8  mov     rbx, [rsp+8C0h+arg_8]
0x1800083f0  add     rsp, 8B0h
0x1800083f7  pop     rdi
0x1800083f8  pop     rsi
0x1800083f9  pop     rbp
0x1800083fa  retn
```
