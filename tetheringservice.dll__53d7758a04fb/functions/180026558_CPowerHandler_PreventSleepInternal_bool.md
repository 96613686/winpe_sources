# CPowerHandler::PreventSleepInternal(bool)

- ea: `0x180026558`
- end: `0x1800266b0`
- name: `?PreventSleepInternal@CPowerHandler@@AEAAJ_N@Z`
- size: `344`
- prototype: `__int64 __fastcall(const struct _WNF_STATE_NAME *this, unsigned __int8)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015e30`
- `0x18001e4a4`
- `0x18001f740`

## callees

- `0x18000dea0`
- `0x180026558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002664f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800265be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002664f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026690`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1800265ae`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1800265ae`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180026634`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180026645`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18002666d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180026634`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180026645`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18002666d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1800265f5`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x180026608`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1800265f5`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x180026608`

## pseudocode

```c
__int64 __fastcall CPowerHandler::PreventSleepInternal(const struct _WNF_STATE_NAME *this, unsigned __int8 a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  signed int v6; // eax
  signed int v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  _REASON_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 )
  {
    if ( *(_QWORD *)&this[6] == -1 )
      goto LABEL_3;
    return (unsigned int)-2147019873;
  }
  if ( *(_QWORD *)&this[6] == -1 )
    return (unsigned int)-2147019873;
LABEL_3:
  v4 = 0;
  CSebHelper::SetEventLevel(this, a2);
  if ( !a2 )
  {
    if ( !PowerClearRequest(*(HANDLE *)&this[6], PowerRequestAwayModeRequired) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( PowerClearRequest(*(HANDLE *)&this[6], PowerRequestSystemRequired) )
      goto LABEL_20;
    goto LABEL_18;
  }
  Context.Version = 0;
  Context.Flags = 1;
  Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)L"icssvc";
  *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
  v5 = PowerCreateRequest(&Context);
  this[6] = (const struct _WNF_STATE_NAME)v5;
  if ( v5 != (HANDLE)-1LL )
  {
    if ( PowerSetRequest(v5, PowerRequestAwayModeRequired) )
    {
      if ( PowerSetRequest(*(HANDLE *)&this[6], PowerRequestSystemRequired) )
        return v4;
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      PowerClearRequest(*(HANDLE *)&this[6], PowerRequestAwayModeRequired);
LABEL_20:
      CloseHandle(*(HANDLE *)&this[6]);
      this[6] = (const struct _WNF_STATE_NAME)-1LL;
      return v4;
    }
LABEL_18:
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_20;
  }
  v6 = GetLastError();
  v4 = v6;
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x180026558  mov     [rsp+arg_0], rbx
0x18002655d  mov     [rsp+arg_8], rbp
0x180026562  push    rdi
0x180026563  sub     rsp, 40h
0x180026567  mov     bpl, dl
0x18002656a  mov     rdi, rcx
0x18002656d  test    dl, dl
0x18002656f  jz      short loc_1800265DC
0x180026571  cmp     qword ptr [rcx+30h], 0FFFFFFFFFFFFFFFFh
0x180026576  jnz     short loc_1800265E3
0x180026578  xor     ebx, ebx
0x18002657a  call    ?SetEventLevel@CSebHelper@@SAJPEBU_WNF_STATE_NAME@@E@Z; CSebHelper::SetEventLevel(_WNF_STATE_NAME const *,uchar)
0x18002657f  test    bpl, bpl
0x180026582  jz      loc_18002663C
0x180026588  xorps   xmm0, xmm0
0x18002658b  mov     [rsp+48h+Context.Version], ebx
0x18002658f  lea     rax, ServiceName; "icssvc"
0x180026596  mov     [rsp+48h+Context.Flags], 1
0x18002659e  lea     rcx, [rsp+48h+Context]; Context
0x1800265a3  mov     qword ptr [rsp+48h+Context.Reason], rax
0x1800265a8  movdqu  xmmword ptr [rsp+48h+Context.Reason+8], xmm0
0x1800265ae  call    cs:__imp_PowerCreateRequest
0x1800265b4  mov     [rdi+30h], rax
0x1800265b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800265bc  jnz     short loc_1800265ED
0x1800265be  call    cs:__imp_GetLastError
0x1800265c4  mov     ebx, eax
0x1800265c6  test    eax, eax
0x1800265c8  jle     loc_18002669E
0x1800265ce  movzx   ebx, ax
0x1800265d1  or      ebx, 80070000h
0x1800265d7  jmp     loc_18002669E
0x1800265dc  cmp     qword ptr [rcx+30h], 0FFFFFFFFFFFFFFFFh
0x1800265e1  jnz     short loc_180026578
0x1800265e3  mov     ebx, 8007139Fh
0x1800265e8  jmp     loc_18002669E
0x1800265ed  mov     edx, 2; RequestType
0x1800265f2  mov     rcx, rax; PowerRequest
0x1800265f5  call    cs:__imp_PowerSetRequest
0x1800265fb  test    eax, eax
0x1800265fd  jz      short loc_180026677
0x1800265ff  mov     rcx, [rdi+30h]; PowerRequest
0x180026603  mov     edx, 1; RequestType
0x180026608  call    cs:__imp_PowerSetRequest
0x18002660e  test    eax, eax
0x180026610  jnz     loc_18002669E
0x180026616  call    cs:__imp_GetLastError
0x18002661c  mov     ebx, eax
0x18002661e  test    eax, eax
0x180026620  jle     short loc_18002662B
0x180026622  movzx   ebx, ax
0x180026625  or      ebx, 80070000h
0x18002662b  mov     rcx, [rdi+30h]; PowerRequest
0x18002662f  mov     edx, 2; RequestType
0x180026634  call    cs:__imp_PowerClearRequest
0x18002663a  jmp     short loc_18002668C
0x18002663c  mov     rcx, [rdi+30h]; PowerRequest
0x180026640  mov     edx, 2; RequestType
0x180026645  call    cs:__imp_PowerClearRequest
0x18002664b  test    eax, eax
0x18002664d  jnz     short loc_180026664
0x18002664f  call    cs:__imp_GetLastError
0x180026655  mov     ebx, eax
0x180026657  test    eax, eax
0x180026659  jle     short loc_180026664
0x18002665b  movzx   ebx, ax
0x18002665e  or      ebx, 80070000h
0x180026664  mov     rcx, [rdi+30h]; PowerRequest
0x180026668  mov     edx, 1; RequestType
0x18002666d  call    cs:__imp_PowerClearRequest
0x180026673  test    eax, eax
0x180026675  jnz     short loc_18002668C
0x180026677  call    cs:__imp_GetLastError
0x18002667d  mov     ebx, eax
0x18002667f  test    eax, eax
0x180026681  jle     short loc_18002668C
0x180026683  movzx   ebx, ax
0x180026686  or      ebx, 80070000h
0x18002668c  mov     rcx, [rdi+30h]; hObject
0x180026690  call    cs:__imp_CloseHandle
0x180026696  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x18002669e  mov     rbp, [rsp+48h+arg_8]
0x1800266a3  mov     eax, ebx
0x1800266a5  mov     rbx, [rsp+48h+arg_0]
0x1800266aa  add     rsp, 40h
0x1800266ae  pop     rdi
0x1800266af  retn
```
