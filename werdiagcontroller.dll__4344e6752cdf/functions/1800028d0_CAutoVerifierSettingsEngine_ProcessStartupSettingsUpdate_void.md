# CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate(void)

- ea: `0x1800028d0`
- end: `0x180002cc0`
- name: `?ProcessStartupSettingsUpdate@CAutoVerifierSettingsEngine@@QEAAJXZ`
- size: `1008`
- prototype: `__int64 __fastcall(CAutoVerifierSettingsEngine *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000202c`

## callees

- `0x180001cc6`
- `0x180001cd4`
- `0x1800028d0`
- `0x180002cc8`
- `0x180005810`
- `0x180005990`
- `0x180005a9c`
- `0x180005d24`
- `0x180005fc0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800029fd`
- `ntdll!RtlFreeUnicodeString` at `0x1800029fd`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800029ac`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800029ac`
- `ntdll!NtClose` at `0x180002c86`
- `ntdll!NtClose` at `0x180002c99`
- `ntdll!NtClose` at `0x180002caa`
- `ntdll!NtClose` at `0x180002c86`
- `ntdll!NtClose` at `0x180002c99`
- `ntdll!NtClose` at `0x180002caa`
- `ntdll!DbgPrintEx` at `0x1800029c9`
- `ntdll!DbgPrintEx` at `0x180002c48`
- `ntdll!DbgPrintEx` at `0x180002c61`
- `ntdll!DbgPrintEx` at `0x1800029c9`
- `ntdll!DbgPrintEx` at `0x180002c48`
- `ntdll!DbgPrintEx` at `0x180002c61`
- `ntdll!NtDeleteKey` at `0x180002c1b`
- `ntdll!NtDeleteKey` at `0x180002c28`
- `ntdll!NtDeleteKey` at `0x180002c1b`
- `ntdll!NtDeleteKey` at `0x180002c28`
- `ntdll!RtlCreateUserThread` at `0x180002bf7`
- `ntdll!RtlCreateUserThread` at `0x180002bf7`

## string_xrefs

- `0x180002a0a`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`
- `0x1800029b8`: `WERDIAG: Failed getting current user registry path. NTSTATUS: %08X\n`
- `0x180002c53`: `WERDIAG: Handle to registry key is null\n`
- `0x180002abc`: `WERDIAG: Failed reading key value. NTSTATUS: %08X\n`
- `0x180002af0`: `WERDIAG: Failed writing registry value. NTSTATUS: %08X\n`
- `0x180002c03`: `WERDIAG: Failed creating timer thread. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate(CAutoVerifierSettingsEngine *this)
{
  void *v1; // rsi
  int *v2; // rcx
  _OWORD *v3; // rax
  __int64 v4; // rdx
  int ProcessExeName; // eax
  int v6; // ebx
  const CHAR *v7; // r8
  unsigned int v8; // edx
  wchar_t *v9; // rcx
  __int64 v10; // r9
  HANDLE v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  int RegStringValue; // eax
  __int64 v15; // rcx
  __int16 *v16; // r8
  __int64 v17; // rdx
  int *v18; // rax
  __int16 v19; // r9
  int *v20; // rcx
  CAutoVerifierSettingsEngine *v21; // rcx
  int v22; // eax
  HANDLE v24; // [rsp+50h] [rbp-B0h] BYREF
  void *v25; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+60h] [rbp-A0h] BYREF
  __int128 Reserved8; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[560]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v29; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v30; // [rsp+2C4h] [rbp+1C4h]
  unsigned int v31; // [rsp+2C8h] [rbp+1C8h] BYREF
  HANDLE KeyHandle; // [rsp+2D0h] [rbp+1D0h] BYREF
  HANDLE Handle; // [rsp+2D8h] [rbp+1D8h] BYREF

  v30 = HIDWORD(this);
  v24 = 0;
  Handle = 0;
  KeyHandle = 0;
  v29 = 0;
  v31 = 0;
  Reserved8 = 0;
  KeyPath = 0;
  v1 = 0;
  v25 = 0;
  g_SettingsEngine = 0;
  Reserved7 = 0;
  memset_0(v28, 0, 0x204u);
  v2 = &dword_18000D450;
  v3 = v28;
  v4 = 4;
  do
  {
    *(_OWORD *)v2 = *v3;
    *((_OWORD *)v2 + 1) = v3[1];
    *((_OWORD *)v2 + 2) = v3[2];
    *((_OWORD *)v2 + 3) = v3[3];
    *((_OWORD *)v2 + 4) = v3[4];
    *((_OWORD *)v2 + 5) = v3[5];
    *((_OWORD *)v2 + 6) = v3[6];
    *((_OWORD *)v2 + 7) = v3[7];
    v2 += 32;
    v3 += 8;
    --v4;
  }
  while ( v4 );
  *v2 = *(_DWORD *)v3;
  ProcessExeName = RtlFormatCurrentUserKeyPath(&KeyPath);
  v6 = ProcessExeName;
  if ( ProcessExeName < 0 )
  {
    v7 = "WERDIAG: Failed getting current user registry path. NTSTATUS: %08X\n";
LABEL_5:
    DbgPrintEx(0x96u, 0, v7, (unsigned int)ProcessExeName);
    goto LABEL_41;
  }
  v6 = PluginsNtOpenKey(
         1u,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options",
         KeyPath.Buffer,
         0,
         &v24);
  RtlFreeUnicodeString(&KeyPath);
  if ( v6 < 0 )
  {
    v10 = (unsigned int)v6;
LABEL_9:
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", v10);
    goto LABEL_41;
  }
  v11 = v24;
  if ( !v24 )
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Handle to registry key is null\n");
    v6 = -1073741595;
    goto LABEL_41;
  }
  if ( !g_SettingsEngine )
  {
    ProcessExeName = PluginsNtGetProcessExeName(v9, v8);
    v6 = ProcessExeName;
    if ( ProcessExeName < 0 )
    {
      v7 = "WERDIAG: Failed getting process name. NTSTATUS: %08X\n";
      goto LABEL_5;
    }
    v11 = v24;
  }
  v12 = PluginsNtOpenKey(0x10001u, &g_SettingsEngine, 0, v11, &Handle);
  v6 = v12;
  if ( v12 < 0 || (v12 = PluginsNtOpenKey(0x10003u, L"Autoverifier", 0, Handle, &KeyHandle), v6 = v12, v12 < 0) )
  {
    v10 = (unsigned int)v12;
    goto LABEL_9;
  }
  ProcessExeName = PluginsNtGetRegDwordValue(KeyHandle, L"AutoVerifierCount", &v29);
  v6 = ProcessExeName;
  if ( ProcessExeName < 0 )
    goto LABEL_19;
  v13 = v29;
  if ( v29 > 1 )
  {
    ProcessExeName = PluginsNtSetRegDwordValue(KeyHandle, L"AutoVerifierCount", v29 - 1);
    v6 = ProcessExeName;
    if ( ProcessExeName < 0 )
    {
      v7 = "WERDIAG: Failed writing registry value. NTSTATUS: %08X\n";
      goto LABEL_5;
    }
  }
  RegStringValue = PluginsNtGetRegStringValue(KeyHandle, L"OriginalBucket", &v25);
  v1 = v25;
  if ( RegStringValue >= 0 )
  {
    v15 = 2147483646;
    v16 = (__int16 *)v25;
    v17 = 256;
    v18 = &dword_18000D454;
    do
    {
      if ( !v15 )
        break;
      v19 = *v16;
      if ( !*v16 )
        break;
      ++v16;
      *(_WORD *)v18 = v19;
      v18 = (int *)((char *)v18 + 2);
      --v15;
      --v17;
    }
    while ( v17 );
    v20 = (int *)((char *)v18 - 2);
    if ( v17 )
      v20 = v18;
    *(_WORD *)v20 = 0;
    if ( v17 )
      dword_18000D450 = 1096172337;
  }
  ProcessExeName = PluginsNtGetRegDwordValue(KeyHandle, L"AutoVerifierTimeDuration", &v31);
  v6 = ProcessExeName;
  if ( ProcessExeName < 0 )
  {
LABEL_19:
    v7 = "WERDIAG: Failed reading key value. NTSTATUS: %08X\n";
    goto LABEL_5;
  }
  if ( v31 )
  {
    qword_18000D448 = -10000000LL * v31;
    Reserved7 = 0;
    ProcessExeName = RtlCreateUserThread(
                       (PVOID)0xFFFFFFFFFFFFFFFFLL,
                       0,
                       0,
                       0,
                       0,
                       0,
                       WaitingThread,
                       &qword_18000D448,
                       &Reserved7,
                       &Reserved8);
    v6 = ProcessExeName;
    if ( ProcessExeName < 0 )
    {
      v7 = "WERDIAG: Failed creating timer thread. NTSTATUS: %08X\n";
      goto LABEL_5;
    }
  }
  if ( v13 <= 1 )
  {
    NtDeleteKey(KeyHandle);
    NtDeleteKey(Handle);
    v22 = CAutoVerifierSettingsEngine::ResetAutoverifierEnabledFlag(v21);
    if ( v22 < 0 )
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed deleting autovefier enabled flag. NTSTATUS: %08X\n", v22);
  }
  v6 = 0;
LABEL_41:
  if ( v1 )
    operator delete[](v1);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v24 )
    NtClose(v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800028d0  mov     qword ptr [rsp-8+arg_0], rcx
0x1800028d5  push    rbp
0x1800028d6  push    rbx
0x1800028d7  push    rsi
0x1800028d8  push    rdi
0x1800028d9  push    r14
0x1800028db  lea     rbp, [rsp-190h]
0x1800028e3  sub     rsp, 290h
0x1800028ea  xor     r14d, r14d
0x1800028ed  mov     [rsp+2B0h+var_260], r14
0x1800028f2  mov     [rbp+1B0h+Handle], r14
0x1800028f9  mov     [rbp+1B0h+KeyHandle], r14
0x180002900  mov     [rbp+1B0h+arg_0], r14d
0x180002907  mov     [rbp+1B0h+arg_8], r14d
0x18000290e  xorps   xmm0, xmm0
0x180002911  movups  [rsp+2B0h+var_240], xmm0
0x180002916  xorps   xmm1, xmm1
0x180002919  movups  xmmword ptr [rsp+2B0h+KeyPath.Length], xmm1
0x18000291e  mov     esi, r14d
0x180002921  mov     [rsp+2B0h+var_258], r14
0x180002926  mov     cs:?g_SettingsEngine@@3VCAutoVerifierSettingsEngine@@A, r14w; CAutoVerifierSettingsEngine g_SettingsEngine
0x18000292e  mov     cs:Reserved7, r14
0x180002935  xor     edx, edx; Val
0x180002937  mov     r8d, 204h; Size
0x18000293d  lea     rcx, [rbp+1B0h+var_230]; void *
0x180002941  call    memset_0
0x180002946  lea     rcx, dword_18000D450
0x18000294d  lea     rax, [rbp+1B0h+var_230]
0x180002951  lea     edx, [r14+4]
0x180002955  lea     r8d, [rdx+7Ch]
0x180002959  movups  xmm0, xmmword ptr [rax]
0x18000295c  movups  xmmword ptr [rcx], xmm0
0x18000295f  movups  xmm1, xmmword ptr [rax+10h]
0x180002963  movups  xmmword ptr [rcx+10h], xmm1
0x180002967  movups  xmm0, xmmword ptr [rax+20h]
0x18000296b  movups  xmmword ptr [rcx+20h], xmm0
0x18000296f  movups  xmm1, xmmword ptr [rax+30h]
0x180002973  movups  xmmword ptr [rcx+30h], xmm1
0x180002977  movups  xmm0, xmmword ptr [rax+40h]
0x18000297b  movups  xmmword ptr [rcx+40h], xmm0
0x18000297f  movups  xmm1, xmmword ptr [rax+50h]
0x180002983  movups  xmmword ptr [rcx+50h], xmm1
0x180002987  movups  xmm0, xmmword ptr [rax+60h]
0x18000298b  movups  xmmword ptr [rcx+60h], xmm0
0x18000298f  movups  xmm1, xmmword ptr [rax+70h]
0x180002993  movups  xmmword ptr [rcx+70h], xmm1
0x180002997  add     rcx, r8
0x18000299a  add     rax, r8
0x18000299d  sub     rdx, 1
0x1800029a1  jnz     short loc_180002959
0x1800029a3  mov     eax, [rax]
0x1800029a5  mov     [rcx], eax
0x1800029a7  lea     rcx, [rsp+2B0h+KeyPath]; KeyPath
0x1800029ac  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800029b2  mov     ebx, eax
0x1800029b4  test    eax, eax
0x1800029b6  jns     short loc_1800029D4
0x1800029b8  lea     r8, aWerdiagFailedG; "WERDIAG: Failed getting current user re"...
0x1800029bf  mov     r9d, eax
0x1800029c2  xor     edx, edx; Level
0x1800029c4  mov     ecx, 96h; ComponentId
0x1800029c9  call    cs:__imp_DbgPrintEx
0x1800029cf  jmp     loc_180002C6C
0x1800029d4  lea     rax, [rsp+2B0h+var_260]
0x1800029d9  mov     [rsp+2B0h+Reserved3], rax; KeyHandle
0x1800029de  xor     r9d, r9d
0x1800029e1  mov     r8, [rsp+2B0h+KeyPath.Buffer]
0x1800029e6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800029ed  lea     ecx, [r9+1]; DesiredAccess
0x1800029f1  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x1800029f6  mov     ebx, eax
0x1800029f8  lea     rcx, [rsp+2B0h+KeyPath]; UnicodeString
0x1800029fd  call    cs:__imp_RtlFreeUnicodeString
0x180002a03  test    ebx, ebx
0x180002a05  jns     short loc_180002A13
0x180002a07  mov     r9d, ebx
0x180002a0a  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x180002a11  jmp     short loc_1800029C2
0x180002a13  mov     r9, [rsp+2B0h+var_260]
0x180002a18  test    r9, r9
0x180002a1b  jz      loc_180002C53
0x180002a21  cmp     cs:?g_SettingsEngine@@3VCAutoVerifierSettingsEngine@@A, r14w; CAutoVerifierSettingsEngine g_SettingsEngine
0x180002a29  jnz     short loc_180002A44
0x180002a2b  call    ?PluginsNtGetProcessExeName@@YAJPEA_WK@Z; PluginsNtGetProcessExeName(wchar_t *,ulong)
0x180002a30  mov     ebx, eax
0x180002a32  test    eax, eax
0x180002a34  jns     short loc_180002A3F
0x180002a36  lea     r8, aWerdiagFailedG_0; "WERDIAG: Failed getting process name. N"...
0x180002a3d  jmp     short loc_1800029BF
0x180002a3f  mov     r9, [rsp+2B0h+var_260]
0x180002a44  lea     rax, [rbp+1B0h+Handle]
0x180002a4b  mov     [rsp+2B0h+Reserved3], rax; KeyHandle
0x180002a50  xor     r8d, r8d
0x180002a53  lea     rdx, ?g_SettingsEngine@@3VCAutoVerifierSettingsEngine@@A; SourceString
0x180002a5a  mov     ecx, 10001h; DesiredAccess
0x180002a5f  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180002a64  mov     ebx, eax
0x180002a66  test    eax, eax
0x180002a68  jns     short loc_180002A6F
0x180002a6a  mov     r9d, eax
0x180002a6d  jmp     short loc_180002A0A
0x180002a6f  lea     rax, [rbp+1B0h+KeyHandle]
0x180002a76  mov     [rsp+2B0h+Reserved3], rax; KeyHandle
0x180002a7b  mov     r9, [rbp+1B0h+Handle]
0x180002a82  xor     r8d, r8d
0x180002a85  lea     rdx, aAutoverifier; "Autoverifier"
0x180002a8c  mov     ecx, 10003h; DesiredAccess
0x180002a91  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180002a96  mov     ebx, eax
0x180002a98  test    eax, eax
0x180002a9a  js      short loc_180002A6A
0x180002a9c  lea     r8, [rbp+1B0h+arg_0]; unsigned int *
0x180002aa3  lea     rdx, aAutoverifierco; "AutoVerifierCount"
0x180002aaa  mov     rcx, [rbp+1B0h+KeyHandle]; KeyHandle
0x180002ab1  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x180002ab6  mov     ebx, eax
0x180002ab8  test    eax, eax
0x180002aba  jns     short loc_180002AC8
0x180002abc  lea     r8, aWerdiagFailedR_0; "WERDIAG: Failed reading key value. NTST"...
0x180002ac3  jmp     loc_1800029BF
0x180002ac8  mov     edi, [rbp+1B0h+arg_0]
0x180002ace  cmp     edi, 1
0x180002ad1  jbe     short loc_180002AFC
0x180002ad3  lea     r8d, [rdi-1]; unsigned int
0x180002ad7  lea     rdx, aAutoverifierco; "AutoVerifierCount"
0x180002ade  mov     rcx, [rbp+1B0h+KeyHandle]; KeyHandle
0x180002ae5  call    ?PluginsNtSetRegDwordValue@@YAJPEAXPEB_WK@Z; PluginsNtSetRegDwordValue(void *,wchar_t const *,ulong)
0x180002aea  mov     ebx, eax
0x180002aec  test    eax, eax
0x180002aee  jns     short loc_180002AFC
0x180002af0  lea     r8, aWerdiagFailedW_0; "WERDIAG: Failed writing registry value."...
0x180002af7  jmp     loc_1800029BF
0x180002afc  lea     r8, [rsp+2B0h+var_258]
0x180002b01  lea     rdx, aOriginalbucket; "OriginalBucket"
0x180002b08  mov     rcx, [rbp+1B0h+KeyHandle]; KeyHandle
0x180002b0f  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180002b14  mov     rsi, [rsp+2B0h+var_258]
0x180002b19  test    eax, eax
0x180002b1b  js      short loc_180002B70
0x180002b1d  mov     ecx, 7FFFFFFEh
0x180002b22  mov     r8, rsi
0x180002b25  mov     edx, 100h
0x180002b2a  lea     rax, dword_18000D454
0x180002b31  test    rcx, rcx
0x180002b34  jz      short loc_180002B55
0x180002b36  movzx   r9d, word ptr [r8]
0x180002b3a  test    r9w, r9w
0x180002b3e  jz      short loc_180002B55
0x180002b40  add     r8, 2
0x180002b44  mov     [rax], r9w
0x180002b48  add     rax, 2
0x180002b4c  dec     rcx
0x180002b4f  sub     rdx, 1
0x180002b53  jnz     short loc_180002B31
0x180002b55  lea     rcx, [rax-2]
0x180002b59  test    rdx, rdx
0x180002b5c  cmovnz  rcx, rax
0x180002b60  mov     [rcx], r14w
0x180002b64  jz      short loc_180002B70
0x180002b66  mov     cs:dword_18000D450, 41564331h
0x180002b70  lea     r8, [rbp+1B0h+arg_8]; unsigned int *
0x180002b77  lea     rdx, aAutoverifierti; "AutoVerifierTimeDuration"
0x180002b7e  mov     rcx, [rbp+1B0h+KeyHandle]; KeyHandle
0x180002b85  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x180002b8a  mov     ebx, eax
0x180002b8c  test    eax, eax
0x180002b8e  js      loc_180002ABC
0x180002b94  mov     eax, [rbp+1B0h+arg_8]
0x180002b9a  test    eax, eax
0x180002b9c  jz      short loc_180002C0F
0x180002b9e  imul    rcx, rax, 0FFFFFFFFFF676980h
0x180002ba5  mov     cs:qword_18000D448, rcx
0x180002bac  mov     cs:Reserved7, r14
0x180002bb3  lea     rax, [rsp+2B0h+var_240]
0x180002bb8  mov     [rsp+2B0h+Reserved8], rax; Reserved8
0x180002bbd  lea     rax, Reserved7
0x180002bc4  mov     [rsp+2B0h+Reserved7], rax; Reserved7
0x180002bc9  lea     rax, qword_18000D448
0x180002bd0  mov     [rsp+2B0h+Reserved6], rax; Reserved6
0x180002bd5  lea     rax, ?WaitingThread@@YAJPEAX@Z; WaitingThread(void *)
0x180002bdc  mov     [rsp+2B0h+Reserved5], rax; Reserved5
0x180002be1  mov     [rsp+2B0h+Reserved4], r14; Reserved4
0x180002be6  mov     [rsp+2B0h+Reserved3], r14; Reserved3
0x180002beb  xor     r9d, r9d; Reserved2
0x180002bee  xor     r8d, r8d; Reserved1
0x180002bf1  xor     edx, edx; OutThreadHandle
0x180002bf3  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x180002bf7  call    cs:__imp_RtlCreateUserThread
0x180002bfd  mov     ebx, eax
0x180002bff  test    eax, eax
0x180002c01  jns     short loc_180002C0F
0x180002c03  lea     r8, aWerdiagFailedC_0; "WERDIAG: Failed creating timer thread. "...
0x180002c0a  jmp     loc_1800029BF
0x180002c0f  cmp     edi, 1
0x180002c12  ja      short loc_180002C4E
0x180002c14  mov     rcx, [rbp+1B0h+KeyHandle]; KeyHandle
0x180002c1b  call    cs:__imp_NtDeleteKey
0x180002c21  mov     rcx, [rbp+1B0h+Handle]; KeyHandle
0x180002c28  call    cs:__imp_NtDeleteKey
0x180002c2e  call    ?ResetAutoverifierEnabledFlag@CAutoVerifierSettingsEngine@@AEAAJXZ; CAutoVerifierSettingsEngine::ResetAutoverifierEnabledFlag(void)
0x180002c33  test    eax, eax
0x180002c35  jns     short loc_180002C4E
0x180002c37  mov     r9d, eax
0x180002c3a  lea     r8, aWerdiagFailedD_1; "WERDIAG: Failed deleting autovefier ena"...
0x180002c41  xor     edx, edx; Level
0x180002c43  mov     ecx, 96h; ComponentId
0x180002c48  call    cs:__imp_DbgPrintEx
0x180002c4e  mov     ebx, r14d
0x180002c51  jmp     short loc_180002C6C
0x180002c53  lea     r8, aWerdiagHandleT; "WERDIAG: Handle to registry key is null"...
0x180002c5a  xor     edx, edx; Level
0x180002c5c  mov     ecx, 96h; ComponentId
0x180002c61  call    cs:__imp_DbgPrintEx
0x180002c67  mov     ebx, 0C00000E5h
0x180002c6c  test    rsi, rsi
0x180002c6f  jz      short loc_180002C7A
0x180002c71  mov     rcx, rsi; void *
0x180002c74  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002c79  nop
0x180002c7a  mov     rcx, [rbp+1B0h+KeyHandle]; Handle
0x180002c81  test    rcx, rcx
0x180002c84  jz      short loc_180002C8D
0x180002c86  call    cs:__imp_NtClose
0x180002c8c  nop
0x180002c8d  mov     rcx, [rbp+1B0h+Handle]; Handle
0x180002c94  test    rcx, rcx
0x180002c97  jz      short loc_180002CA0
0x180002c99  call    cs:__imp_NtClose
0x180002c9f  nop
0x180002ca0  mov     rcx, [rsp+2B0h+var_260]; Handle
0x180002ca5  test    rcx, rcx
0x180002ca8  jz      short loc_180002CB0
0x180002caa  call    cs:__imp_NtClose
0x180002cb0  mov     eax, ebx
0x180002cb2  add     rsp, 290h
0x180002cb9  pop     r14
0x180002cbb  pop     rdi
0x180002cbc  pop     rsi
0x180002cbd  pop     rbx
0x180002cbe  pop     rbp
0x180002cbf  retn
```
