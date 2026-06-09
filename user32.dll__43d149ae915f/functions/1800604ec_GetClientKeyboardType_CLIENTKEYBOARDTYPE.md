# GetClientKeyboardType(_CLIENTKEYBOARDTYPE *)

- ea: `0x1800604ec`
- end: `0x180060620`
- name: `?GetClientKeyboardType@@YAHPEAU_CLIENTKEYBOARDTYPE@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct _CLIENTKEYBOARDTYPE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180018740`
- `0x18005a0d0`

## callees

- `0x1800604ec`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18006056d`
- `ntdll!RtlGetActiveConsoleId` at `0x18006060d`
- `ntdll!RtlGetActiveConsoleId` at `0x18006056d`
- `ntdll!RtlGetActiveConsoleId` at `0x18006060d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180060537`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180060554`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180060537`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180060554`
- `WINSTA!WinStationQueryInformationW` at `0x1800605a3`
- `WINSTA!WinStationQueryInformationW` at `0x1800605a3`

## pseudocode

```c
__int64 __fastcall GetClientKeyboardType(struct _CLIENTKEYBOARDTYPE *a1)
{
  ULONG SessionId; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  int v6; // eax
  _DWORD v7[4]; // [rsp+30h] [rbp-928h] BYREF
  _BYTE v8[1272]; // [rsp+40h] [rbp-918h] BYREF
  __int64 v9; // [rsp+538h] [rbp-420h]
  int v10; // [rsp+540h] [rbp-418h]

  v7[0] = 0;
  memset_0(v8, 0, 0x8F8u);
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId != (unsigned int)WTSGetServiceSessionId() )
    RtlGetActiveConsoleId();
  v3 = NtCurrentPeb()->SessionId;
  if ( v3 == (unsigned int)WTSGetServiceSessionId() )
    return 0;
  v4 = NtCurrentPeb()->SessionId;
  if ( v4 == (unsigned int)RtlGetActiveConsoleId() )
    return 0;
  if ( (_DWORD)qword_1800C8950 == -1 )
  {
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, __int64, __int64, _BYTE *, int, _DWORD *))WinStationQueryInformationW)(
                             0,
                             0xFFFFFFFFLL,
                             6,
                             v8,
                             2296,
                             v7) )
      return 0;
    qword_1800C8950 = v9;
    v6 = v10;
    dword_1800C8958 = v10;
  }
  else
  {
    v6 = dword_1800C8958;
  }
  *(_QWORD *)a1 = qword_1800C8950;
  *((_DWORD *)a1 + 2) = v6;
  return 1;
}

```

## disassembly

```asm
0x1800604ec  mov     [rsp+arg_8], rbx
0x1800604f1  push    rdi
0x1800604f2  sub     rsp, 950h
0x1800604f9  mov     rax, cs:__security_cookie
0x180060500  xor     rax, rsp
0x180060503  mov     [rsp+958h+var_18], rax
0x18006050b  mov     rdi, rcx
0x18006050e  mov     [rsp+958h+var_928], 0
0x180060516  lea     rcx, [rsp+958h+var_918]; void *
0x18006051b  xor     edx, edx; Val
0x18006051d  mov     r8d, 8F8h; Size
0x180060523  call    memset_0
0x180060528  mov     rax, gs:60h
0x180060531  mov     ebx, [rax+2C0h]
0x180060537  call    cs:__imp_WTSGetServiceSessionId
0x18006053d  cmp     ebx, eax
0x18006053f  jnz     loc_18006060D
0x180060545  mov     rax, gs:60h
0x18006054e  mov     ebx, [rax+2C0h]
0x180060554  call    cs:__imp_WTSGetServiceSessionId
0x18006055a  cmp     ebx, eax
0x18006055c  jz      short loc_1800605AD
0x18006055e  mov     rax, gs:60h
0x180060567  mov     ebx, [rax+2C0h]
0x18006056d  call    cs:__imp_RtlGetActiveConsoleId
0x180060573  cmp     ebx, eax
0x180060575  jz      short loc_1800605AD
0x180060577  or      edx, 0FFFFFFFFh
0x18006057a  cmp     dword ptr cs:qword_1800C8950, edx
0x180060580  jnz     loc_180060618
0x180060586  xor     ecx, ecx
0x180060588  lea     rax, [rsp+958h+var_928]
0x18006058d  mov     [rsp+958h+var_930], rax
0x180060592  lea     r9, [rsp+958h+var_918]
0x180060597  mov     [rsp+958h+var_938], 8F8h
0x18006059f  lea     r8d, [rcx+6]
0x1800605a3  call    cs:__imp_WinStationQueryInformationW
0x1800605a9  test    al, al
0x1800605ab  jnz     short loc_1800605D0
0x1800605ad  xor     eax, eax
0x1800605af  mov     rcx, [rsp+958h+var_18]
0x1800605b7  xor     rcx, rsp; StackCookie
0x1800605ba  call    __security_check_cookie
0x1800605bf  mov     rbx, [rsp+958h+arg_8]
0x1800605c7  add     rsp, 950h
0x1800605ce  pop     rdi
0x1800605cf  retn
0x1800605d0  mov     eax, dword ptr [rsp+958h+var_420]
0x1800605d7  mov     dword ptr cs:qword_1800C8950, eax
0x1800605dd  mov     eax, dword ptr [rsp+958h+var_420+4]
0x1800605e4  mov     dword ptr cs:qword_1800C8950+4, eax
0x1800605ea  mov     eax, [rsp+958h+var_418]
0x1800605f1  mov     cs:dword_1800C8958, eax
0x1800605f7  movsd   xmm0, cs:qword_1800C8950
0x1800605ff  movsd   qword ptr [rdi], xmm0
0x180060603  mov     [rdi+8], eax
0x180060606  mov     eax, 1
0x18006060b  jmp     short loc_1800605AF
0x18006060d  call    cs:__imp_RtlGetActiveConsoleId
0x180060613  jmp     loc_180060545
0x180060618  mov     eax, cs:dword_1800C8958
0x18006061e  jmp     short loc_1800605F7
```
