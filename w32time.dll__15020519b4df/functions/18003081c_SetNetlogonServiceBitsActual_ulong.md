# SetNetlogonServiceBitsActual(ulong)

- ea: `0x18003081c`
- end: `0x180030987`
- name: `?SetNetlogonServiceBitsActual@@YAJK@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e758`
- `0x18002d250`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003081c`
- `0x18004d9ac`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180030844`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180030960`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180030844`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180030960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030919`
- `logoncli!NetLogonSetServiceBits` at `0x18003087e`
- `logoncli!NetLogonSetServiceBits` at `0x18003087e`

## string_xrefs

- `0x180030868`: `Setting Netlogon Service bits: 0x%x\n`
- `0x1800308b5`: `Logging warning: Failed to communicate with Netlogon. Error: 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SetNetlogonServiceBitsActual(unsigned int a1)
{
  int v2; // eax
  int v3; // edi
  DWORD v4; // ebx
  signed int LastError; // eax
  DWORD v7; // [rsp+30h] [rbp-48h]
  __int64 v8; // [rsp+88h] [rbp+10h]

  if ( (dword_1800A45C0 & 0xFFFFFFFD) != 0 )
  {
    v8 = _set_se_translator(SeTransFunc);
    if ( (unsigned __int8)FileLogAllowEntry(52) )
      FileLogAdd(L"Setting Netlogon Service bits: 0x%x\n", a1);
    v2 = NetLogonSetServiceBits(0, 576, a1);
    v3 = v2;
    if ( v2 > 0 )
      v4 = (unsigned __int16)v2 | 0x80070000;
    else
      v4 = v2;
    v7 = v4;
    if ( v2 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(4) )
        FileLogAdd(L"Logging warning: Failed to communicate with Netlogon. Error: 0x%x\n", v4);
      LogThrottledErrorMessage(v4);
      if ( v3 != -1073610734 )
        return v7;
    }
    if ( !(unsigned int)((__int64 (__fastcall *)(struct SERVICE_STATUS_HANDLE__ *, __int64, _QWORD))fnW32TmI_ScSetServiceBits)(
                          g_servicestatushandle,
                          32,
                          a1 & 0x40) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
      if ( LastError != -2147024890 || g_servicestatushandle != (struct SERVICE_STATUS_HANDLE__ *)3 )
        return v7;
      v7 = 0;
    }
    _set_se_translator(v8);
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18003081c  mov     [rsp+arg_0], rbx
0x180030821  mov     [rsp+arg_10], rsi
0x180030826  push    rdi
0x180030827  sub     rsp, 70h
0x18003082b  mov     esi, ecx
0x18003082d  test    cs:dword_1800A45C0, 0FFFFFFFDh
0x180030837  jz      loc_180030972
0x18003083d  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180030844  call    cs:__imp__set_se_translator
0x18003084b  nop     dword ptr [rax+rax+00h]
0x180030850  mov     [rsp+78h+arg_8], rax
0x180030858  mov     ecx, 34h ; '4'
0x18003085d  call    FileLogAllowEntry
0x180030862  test    al, al
0x180030864  jz      short loc_180030874
0x180030866  mov     edx, esi
0x180030868  lea     rcx, aSettingNetlogo; "Setting Netlogon Service bits: 0x%x\n"
0x18003086f  call    FileLogAdd
0x180030874  mov     r8d, esi
0x180030877  mov     edx, 240h
0x18003087c  xor     ecx, ecx
0x18003087e  call    cs:__imp_NetLogonSetServiceBits
0x180030885  nop     dword ptr [rax+rax+00h]
0x18003088a  mov     edi, eax
0x18003088c  test    eax, eax
0x18003088e  jg      short loc_180030894
0x180030890  mov     ebx, eax
0x180030892  jmp     short loc_18003089D
0x180030894  movzx   ebx, di
0x180030897  or      ebx, 80070000h
0x18003089d  mov     [rsp+78h+var_48], ebx
0x1800308a1  test    edi, edi
0x1800308a3  jz      short loc_1800308E9
0x1800308a5  mov     ecx, 4
0x1800308aa  call    FileLogAllowEntry
0x1800308af  test    al, al
0x1800308b1  jz      short loc_1800308C1
0x1800308b3  mov     edx, ebx
0x1800308b5  lea     rcx, aLoggingWarning_3; "Logging warning: Failed to communicate "...
0x1800308bc  call    FileLogAdd
0x1800308c1  mov     r9d, 1B77400h
0x1800308c7  lea     r8, W32TIME_EVENT_NETLOGON_COMM_FAILURE
0x1800308ce  lea     rdx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x1800308d5  mov     ecx, ebx; dwMessageId
0x1800308d7  call    LogThrottledErrorMessage
0x1800308dc  cmp     edi, 0C0020012h
0x1800308e2  jz      short loc_1800308E9
0x1800308e4  jmp     loc_18003096C
0x1800308e9  and     esi, 40h
0x1800308ec  mov     [rsp+78h+var_58], 0
0x1800308f5  mov     r9d, 1
0x1800308fb  mov     r8d, esi
0x1800308fe  lea     edx, [r9+1Fh]
0x180030902  mov     rcx, cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x180030909  mov     rax, cs:?fnW32TmI_ScSetServiceBits@@3P6AHPEAUSERVICE_STATUS_HANDLE__@@KHHPEAG@ZEA; int (*fnW32TmI_ScSetServiceBits)(SERVICE_STATUS_HANDLE__ *,ulong,int,int,ushort *)
0x180030910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030915  test    eax, eax
0x180030917  jnz     short loc_180030952
0x180030919  call    cs:__imp_GetLastError
0x180030920  nop     dword ptr [rax+rax+00h]
0x180030925  test    eax, eax
0x180030927  jle     short loc_180030931
0x180030929  movzx   eax, ax
0x18003092c  or      eax, 80070000h
0x180030931  mov     [rsp+78h+var_48], eax
0x180030935  cmp     eax, 80070006h
0x18003093a  jnz     short loc_180030950
0x18003093c  cmp     cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 3; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x180030944  jnz     short loc_180030950
0x180030946  mov     [rsp+78h+var_48], 0
0x18003094e  jmp     short loc_180030952
0x180030950  jmp     short loc_18003096C
0x180030952  jmp     short loc_180030958
0x180030954  jmp     short loc_180030958
0x180030956  jmp     short $+2
0x180030958  mov     rcx, [rsp+78h+arg_8]
0x180030960  call    cs:__imp__set_se_translator
0x180030967  nop     dword ptr [rax+rax+00h]
0x18003096c  mov     eax, [rsp+78h+var_48]
0x180030970  jmp     short loc_180030974
0x180030972  xor     eax, eax
0x180030974  lea     r11, [rsp+78h+var_8]
0x180030979  mov     rbx, [r11+10h]
0x18003097d  mov     rsi, [r11+20h]
0x180030981  mov     rsp, r11
0x180030984  pop     rdi
0x180030985  retn
```
