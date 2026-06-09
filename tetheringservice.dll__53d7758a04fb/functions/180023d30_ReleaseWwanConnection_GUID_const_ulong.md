# ReleaseWwanConnection(_GUID const *,ulong)

- ea: `0x180023d30`
- end: `0x180023eab`
- name: `?ReleaseWwanConnection@@YAJPEBU_GUID@@K@Z`
- size: `379`
- prototype: `__int64 __fastcall(const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180013a8c`

## callees

- `0x1800035a8`
- `0x18000bf74`
- `0x18001402c`
- `0x180023d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d88`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023d80`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023e96`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023d80`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180023e96`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180023da3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180023da3`
- `ext-ms-win-wwan-wwapi-l1-1-3!WwanDisconnect` at `0x180023dd3`
- `ext-ms-win-wwan-wwapi-l1-1-3!WwanDisconnect` at `0x180023dd3`

## pseudocode

```c
__int64 __fastcall ReleaseWwanConnection(const struct _GUID *a1, int a2)
{
  unsigned int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v6; // [rsp+30h] [rbp-10h] BYREF
  int v7; // [rsp+68h] [rbp+28h] BYREF
  int v8; // [rsp+70h] [rbp+30h] BYREF
  int v9; // [rsp+78h] [rbp+38h] BYREF

  v7 = a2;
  v6 = -1;
  v9 = 0;
  v8 = 0;
  if ( !(unsigned __int8)IsWwanOpenHandlePresent() )
  {
    v3 = 50;
    goto LABEL_11;
  }
  v6 = -1;
  v3 = WwanOpenHandle(1, 0, &v8, &v6);
  if ( v3 )
  {
LABEL_11:
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, v3);
    }
    goto LABEL_14;
  }
  v3 = WwanDisconnect(v6, a1, 0, &v7, &v9, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, a1, v7);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF__guid_d(*((_QWORD *)v4 + 2), 34, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, a1, v3);
LABEL_14:
    if ( (int)v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  if ( v6 != -1 )
    WwanCloseHandle(v6, 0);
  return v3;
}

```

## disassembly

```asm
0x180023d30  mov     [rsp-18h+arg_0], rbx
0x180023d35  mov     [rsp-18h+arg_8], edx
0x180023d39  push    rbp
0x180023d3a  push    rsi
0x180023d3b  push    rdi
0x180023d3c  mov     rbp, rsp
0x180023d3f  sub     rsp, 40h
0x180023d43  mov     rsi, rcx
0x180023d46  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180023d4e  mov     [rbp+arg_18], 0
0x180023d55  mov     [rbp+arg_10], 0
0x180023d5c  call    IsWwanOpenHandlePresent
0x180023d61  test    al, al
0x180023d63  jz      loc_180023E47
0x180023d69  mov     rdi, [rbp+var_10]
0x180023d6d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180023d71  jz      short loc_180023D8E
0x180023d73  call    cs:__imp_GetLastError
0x180023d79  xor     edx, edx
0x180023d7b  mov     rcx, rdi
0x180023d7e  mov     ebx, eax
0x180023d80  call    cs:__imp_WwanCloseHandle
0x180023d86  mov     ecx, ebx; dwErrCode
0x180023d88  call    cs:__imp_SetLastError
0x180023d8e  xor     edx, edx
0x180023d90  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180023d98  lea     r9, [rbp+var_10]
0x180023d9c  lea     r8, [rbp+arg_10]
0x180023da0  lea     ecx, [rdx+1]
0x180023da3  call    cs:__imp_WwanOpenHandle
0x180023da9  mov     ebx, eax
0x180023dab  test    eax, eax
0x180023dad  jnz     loc_180023E4C
0x180023db3  mov     rcx, [rbp+var_10]
0x180023db7  lea     rax, [rbp+arg_18]
0x180023dbb  mov     [rsp+40h+var_18], 0
0x180023dc4  lea     r9, [rbp+arg_8]
0x180023dc8  xor     r8d, r8d
0x180023dcb  mov     [rsp+40h+var_20], rax
0x180023dd0  mov     rdx, rsi
0x180023dd3  call    cs:__imp_WwanDisconnect
0x180023dd9  mov     ebx, eax
0x180023ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023de2  lea     rdi, WPP_GLOBAL_Control
0x180023de9  cmp     rcx, rdi
0x180023dec  jz      short loc_180023E1A
0x180023dee  test    byte ptr [rcx+1Ch], 4
0x180023df2  jz      short loc_180023E1A
0x180023df4  mov     eax, [rbp+arg_8]
0x180023df7  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180023dfe  mov     rcx, [rcx+10h]
0x180023e02  mov     edx, 21h ; '!'
0x180023e07  mov     r9, rsi
0x180023e0a  mov     dword ptr [rsp+40h+var_20], eax
0x180023e0e  call    WPP_SF__guid_d
0x180023e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e1a  test    ebx, ebx
0x180023e1c  jz      short loc_180023E8A
0x180023e1e  cmp     rcx, rdi
0x180023e21  jz      short loc_180023E7D
0x180023e23  test    byte ptr [rcx+1Ch], 1
0x180023e27  jz      short loc_180023E7D
0x180023e29  mov     rcx, [rcx+10h]
0x180023e2d  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180023e34  mov     edx, 22h ; '"'
0x180023e39  mov     dword ptr [rsp+40h+var_20], ebx
0x180023e3d  mov     r9, rsi
0x180023e40  call    WPP_SF__guid_d
0x180023e45  jmp     short loc_180023E7D
0x180023e47  mov     ebx, 32h ; '2'
0x180023e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e53  lea     rdi, WPP_GLOBAL_Control
0x180023e5a  cmp     rcx, rdi
0x180023e5d  jz      short loc_180023E7D
0x180023e5f  test    byte ptr [rcx+1Ch], 1
0x180023e63  jz      short loc_180023E7D
0x180023e65  mov     rcx, [rcx+10h]
0x180023e69  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180023e70  mov     edx, 20h ; ' '
0x180023e75  mov     r9d, ebx
0x180023e78  call    WPP_SF_d
0x180023e7d  test    ebx, ebx
0x180023e7f  jle     short loc_180023E8A
0x180023e81  movzx   ebx, bx
0x180023e84  or      ebx, 80070000h
0x180023e8a  mov     rcx, [rbp+var_10]
0x180023e8e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023e92  jz      short loc_180023E9C
0x180023e94  xor     edx, edx
0x180023e96  call    cs:__imp_WwanCloseHandle
0x180023e9c  mov     eax, ebx
0x180023e9e  mov     rbx, [rsp+40h+arg_0]
0x180023ea3  add     rsp, 40h
0x180023ea7  pop     rdi
0x180023ea8  pop     rsi
0x180023ea9  pop     rbp
0x180023eaa  retn
```
