# HUBFDO_RegisterSleepstudyBlockerReason

- ea: `0x14007e518`
- end: `0x14007e671`
- name: `HUBFDO_RegisterSleepstudyBlockerReason`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14007e678`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x140045530`
- `0x140045570`
- `0x14007e518`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14007e5fe`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x14007e5fe`

## pseudocode

```c
__int64 __fastcall HUBFDO_RegisterSleepstudyBlockerReason(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int128 *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // r13
  int v11; // edx
  NTSTATUS v12; // ebx
  int v13; // r9d
  __int128 v14; // xmm1
  __int64 v15; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  char v20; // [rsp+60h] [rbp-A0h] BYREF

  DestinationString.Buffer = (wchar_t *)&v20;
  *(_QWORD *)&DestinationString.Length = 0x2000000;
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          WdfDriverGlobals->Driver,
          off_14006B2C0);
  v12 = RtlUnicodeStringPrintf(&DestinationString, L"%wZ (%s)", a3, a5);
  if ( v12 >= 0 )
  {
    v14 = *a2;
    v15 = *(_QWORD *)(v10 + 96);
    v18 = *a4;
    v19 = v14;
    v12 = SleepstudyHelper_RegisterComponentEx(v15, &v19, &v18, &DestinationString, a6);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 114;
      goto LABEL_7;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 113;
LABEL_7:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 2536),
      v11,
      2,
      v13,
      (__int64)WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids,
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14007e518  push    rbp
0x14007e51a  push    rbx
0x14007e51b  push    rsi
0x14007e51c  push    rdi
0x14007e51d  push    r12
0x14007e51f  push    r13
0x14007e521  push    r14
0x14007e523  push    r15
0x14007e525  lea     rbp, [rsp-178h]
0x14007e52d  sub     rsp, 278h
0x14007e534  mov     rax, cs:__security_cookie
0x14007e53b  xor     rax, rsp
0x14007e53e  mov     [rbp+1B0h+var_50], rax
0x14007e545  mov     rbx, [rbp+1B0h+arg_20]
0x14007e54c  lea     rax, [rsp+2B0h+var_250]
0x14007e551  mov     r12, [rbp+1B0h+arg_28]
0x14007e558  mov     rsi, rcx
0x14007e55b  mov     rcx, cs:WdfDriverGlobals
0x14007e562  mov     rdi, r8
0x14007e565  mov     r8, cs:off_14006B2C0
0x14007e56c  mov     r14, rdx
0x14007e56f  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x14007e574  mov     r15, r9
0x14007e577  mov     rax, cs:WdfFunctions_01015
0x14007e57e  mov     qword ptr [rsp+2B0h+DestinationString.Length], 2000000h
0x14007e587  mov     rdx, [rcx]
0x14007e58a  mov     rax, [rax+650h]
0x14007e591  call    _guard_dispatch_icall
0x14007e596  mov     r9, rbx
0x14007e599  lea     rdx, aWzS
0x14007e5a0  mov     r8, rdi
0x14007e5a3  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x14007e5a8  mov     r13, rax
0x14007e5ab  call    RtlUnicodeStringPrintf
0x14007e5b0  mov     ebx, eax
0x14007e5b2  test    eax, eax
0x14007e5b4  jns     short loc_14007E5D2
0x14007e5b6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007e5bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007e5c4  jz      loc_14007E64B
0x14007e5ca  mov     r9d, 71h ; 'q'
0x14007e5d0  jmp     short loc_14007E626
0x14007e5d2  movaps  xmm0, xmmword ptr [r15]
0x14007e5d6  lea     r9, [rsp+2B0h+DestinationString]
0x14007e5db  movaps  xmm1, xmmword ptr [r14]
0x14007e5df  lea     r8, [rsp+2B0h+var_270]
0x14007e5e4  mov     rcx, [r13+60h]
0x14007e5e8  lea     rdx, [rsp+2B0h+var_260]
0x14007e5ed  movdqa  [rsp+2B0h+var_270], xmm0
0x14007e5f3  movdqa  [rsp+2B0h+var_260], xmm1
0x14007e5f9  mov     [rsp+2B0h+var_290], r12
0x14007e5fe  call    cs:__imp_SleepstudyHelper_RegisterComponentEx
0x14007e605  nop     dword ptr [rax+rax+00h]
0x14007e60a  mov     ebx, eax
0x14007e60c  test    eax, eax
0x14007e60e  jns     short loc_14007E64B
0x14007e610  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007e617  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007e61e  jz      short loc_14007E64B
0x14007e620  mov     r9d, 72h ; 'r'
0x14007e626  mov     rcx, [rsi+9E8h]
0x14007e62d  lea     rax, WPP_2e0dbc61611a37aa5578b122392b1411_Traceguids
0x14007e634  mov     r8d, 2
0x14007e63a  mov     [rsp+2B0h+var_288], ebx
0x14007e63e  mov     dl, r8b
0x14007e641  mov     [rsp+2B0h+var_290], rax
0x14007e646  call    WPP_RECORDER_SF_d
0x14007e64b  mov     eax, ebx
0x14007e64d  mov     rcx, [rbp+1B0h+var_50]
0x14007e654  xor     rcx, rsp; StackCookie
0x14007e657  call    __security_check_cookie
0x14007e65c  add     rsp, 278h
0x14007e663  pop     r15
0x14007e665  pop     r14
0x14007e667  pop     r13
0x14007e669  pop     r12
0x14007e66b  pop     rdi
0x14007e66c  pop     rsi
0x14007e66d  pop     rbx
0x14007e66e  pop     rbp
0x14007e66f  retn
```
