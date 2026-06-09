# HelperInitialize

- ea: `0x18006f360`
- end: `0x18006f585`
- name: `HelperInitialize`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004b4c8`

## callees

- `0x18006f360`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006f419`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006f419`
- `rtutils!TraceRegisterExA` at `0x18006f3a3`
- `rtutils!TraceRegisterExA` at `0x18006f3a3`

## string_xrefs

- `0x18006f51a`: `HelperInitialize completed %d`
- `0x18006f55f`: `HelperInitialize completed %d`

## pseudocode

```c
__int64 HelperInitialize()
{
  int v1; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v2[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v1 = 0;
  memset_0(v2, 0, sizeof(v2));
  HelperTraceId = TraceRegisterExA("RASIPHLP", 0);
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_1800AB328,
        L"HelperInitialize");
  }
  else
  {
    TraceHlp("HelperInitialize");
  }
  while ( _InterlockedIncrement(&HelperLock) > 1 )
  {
    _InterlockedDecrement(&HelperLock);
    if ( HelperInitialized )
    {
      _InterlockedIncrement(&HelperLock);
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800AB328 )
        {
          LOWORD(v1) = 0;
          FormatRRASErrorString(&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
          ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v1);
        }
      }
      else
      {
        TraceHlp("HelperInitialize ref count is  %d");
      }
      goto LABEL_17;
    }
    Sleep(0x3E8u);
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800AB328 )
    {
      LOWORD(v1) = 0;
      FormatRRASErrorString(&v1, L"HelperInitialize ref count is  %d", (unsigned int)HelperLock);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v1);
    }
  }
  else
  {
    TraceHlp("HelperInitialize ref count is  %d");
  }
  HelperInitialized = 1;
LABEL_17:
  if ( !gIsIphlpEtwTracingAvailable )
    goto LABEL_21;
  if ( !(_QWORD)xmmword_1800AB328 )
  {
    if ( gIsIphlpEtwTracingAvailable )
      return 0;
LABEL_21:
    TraceHlp("HelperInitialize completed %d");
    return 0;
  }
  LOWORD(v1) = 0;
  FormatRRASErrorString(&v1, L"HelperInitialize completed %d", 0);
  ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800AB328, &v1);
  return 0;
}

```

## disassembly

```asm
0x18006f360  push    rbp
0x18006f362  lea     rbp, [rsp-730h]
0x18006f36a  sub     rsp, 830h
0x18006f371  mov     rax, cs:__security_cookie
0x18006f378  xor     rax, rsp
0x18006f37b  mov     [rbp+730h+var_10], rax
0x18006f382  xor     eax, eax
0x18006f384  lea     rcx, [rsp+830h+var_80C]; void *
0x18006f389  xor     edx, edx; Val
0x18006f38b  mov     [rsp+830h+var_810], eax
0x18006f38f  mov     r8d, 7FCh; Size
0x18006f395  call    memset_0
0x18006f39a  xor     edx, edx; dwFlags
0x18006f39c  lea     rcx, szCallerName; "RASIPHLP"
0x18006f3a3  call    cs:__imp_TraceRegisterExA
0x18006f3a9  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006f3b0  mov     cs:HelperTraceId, eax
0x18006f3b6  jz      short loc_18006F3E0
0x18006f3b8  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006f3bf  test    rdx, rdx
0x18006f3c2  jz      short loc_18006F3EC
0x18006f3c4  mov     rcx, cs:gIphlpEtwContext
0x18006f3cb  lea     r8, aHelperinitiali_5; "HelperInitialize"
0x18006f3d2  mov     rax, cs:gIphlpTemplateFunc
0x18006f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f3de  jmp     short loc_18006F3EC
0x18006f3e0  lea     rcx, aHelperinitiali_0; "HelperInitialize"
0x18006f3e7  call    TraceHlp
0x18006f3ec  mov     eax, 1
0x18006f3f1  lock xadd cs:HelperLock, eax
0x18006f3f9  inc     eax
0x18006f3fb  cmp     eax, 1
0x18006f3fe  jle     loc_18006F496
0x18006f404  lock dec cs:HelperLock
0x18006f40b  cmp     cs:HelperInitialized, 0
0x18006f412  jnz     short loc_18006F421
0x18006f414  mov     ecx, 3E8h; dwMilliseconds
0x18006f419  call    cs:__imp_Sleep
0x18006f41f  jmp     short loc_18006F3EC
0x18006f421  lock inc cs:HelperLock
0x18006f428  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006f42f  jz      short loc_18006F482
0x18006f431  cmp     qword ptr cs:xmmword_1800AB328, 0
0x18006f439  jz      loc_18006F505
0x18006f43f  mov     r8d, cs:HelperLock
0x18006f446  lea     rdx, aHelperinitiali_2; "HelperInitialize ref count is  %d"
0x18006f44d  xor     eax, eax
0x18006f44f  lea     rcx, [rsp+830h+var_810]
0x18006f454  mov     word ptr [rsp+830h+var_810], ax
0x18006f459  call    FormatRRASErrorString
0x18006f45e  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006f465  lea     r8, [rsp+830h+var_810]
0x18006f46a  mov     rcx, cs:gIphlpEtwContext
0x18006f471  mov     rax, cs:gIphlpTemplateFunc
0x18006f478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f47d  jmp     loc_18006F505
0x18006f482  mov     edx, cs:HelperLock
0x18006f488  lea     rcx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x18006f48f  call    TraceHlp
0x18006f494  jmp     short loc_18006F505
0x18006f496  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006f49d  jz      short loc_18006F4E9
0x18006f49f  cmp     qword ptr cs:xmmword_1800AB328, 0
0x18006f4a7  jz      short loc_18006F4FB
0x18006f4a9  mov     r8d, cs:HelperLock
0x18006f4b0  lea     rdx, aHelperinitiali_2; "HelperInitialize ref count is  %d"
0x18006f4b7  xor     eax, eax
0x18006f4b9  lea     rcx, [rsp+830h+var_810]
0x18006f4be  mov     word ptr [rsp+830h+var_810], ax
0x18006f4c3  call    FormatRRASErrorString
0x18006f4c8  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006f4cf  lea     r8, [rsp+830h+var_810]
0x18006f4d4  mov     rcx, cs:gIphlpEtwContext
0x18006f4db  mov     rax, cs:gIphlpTemplateFunc
0x18006f4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4e7  jmp     short loc_18006F4FB
0x18006f4e9  mov     edx, cs:HelperLock
0x18006f4ef  lea     rcx, aHelperinitiali_1; "HelperInitialize ref count is  %d"
0x18006f4f6  call    TraceHlp
0x18006f4fb  mov     cs:HelperInitialized, 1
0x18006f505  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006f50c  jz      short loc_18006F55D
0x18006f50e  cmp     qword ptr cs:xmmword_1800AB328, 0
0x18006f516  jz      short loc_18006F554
0x18006f518  xor     eax, eax
0x18006f51a  lea     rdx, aHelperinitiali_4; "HelperInitialize completed %d"
0x18006f521  xor     r8d, r8d
0x18006f524  mov     word ptr [rsp+830h+var_810], ax
0x18006f529  lea     rcx, [rsp+830h+var_810]
0x18006f52e  call    FormatRRASErrorString
0x18006f533  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006f53a  lea     r8, [rsp+830h+var_810]
0x18006f53f  mov     rcx, cs:gIphlpEtwContext
0x18006f546  mov     rax, cs:gIphlpTemplateFunc
0x18006f54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f552  jmp     short loc_18006F56B
0x18006f554  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006f55b  jnz     short loc_18006F56B
0x18006f55d  xor     edx, edx
0x18006f55f  lea     rcx, aHelperinitiali_3; "HelperInitialize completed %d"
0x18006f566  call    TraceHlp
0x18006f56b  xor     eax, eax
0x18006f56d  mov     rcx, [rbp+730h+var_10]
0x18006f574  xor     rcx, rsp; StackCookie
0x18006f577  call    __security_check_cookie
0x18006f57c  add     rsp, 830h
0x18006f583  pop     rbp
0x18006f584  retn
```
