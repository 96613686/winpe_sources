# ?CreateServiceStartedEvent@CExec@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z

- ea: `0x1400f1dd8`
- end: `0x1400f1f3e`
- name: `?CreateServiceStartedEvent@CExec@@YA?AV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z`
- size: `358`
- prototype: `__int64 __fastcall(PHANDLE EventHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400e6b98`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea44`
- `0x14001e4f4`
- `0x140030078`
- `0x140044adc`
- `0x1400f1dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f1ebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400f1ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f1ea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f1ea1`
- `ntdll!NtCreateEvent` at `0x1400f1ed9`
- `ntdll!NtCreateEvent` at `0x1400f1ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f1eac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f1eac`

## string_xrefs

- `0x1400f1f2c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400f1f1a`: `onecore\vm\compute\service\cexec\common\cexecevent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHANDLE __fastcall CExec::CreateServiceStartedEvent(PHANDLE EventHandle, _WORD *a2)
{
  unsigned __int64 v3; // r8
  __int128 *p_Src; // rax
  void *v5; // rsi
  DWORD LastError; // edi
  const char *v7; // r9
  NTSTATUS v8; // eax
  int InitialState; // [rsp+20h] [rbp-49h]
  _WORD v11[2]; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+44h] [rbp-25h]
  __int128 *v13; // [rsp+48h] [rbp-21h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int128 Src; // [rsp+80h] [rbp+17h] BYREF
  __int64 v16; // [rsp+90h] [rbp+27h]
  unsigned __int64 v17; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *EventHandle = 0;
  Src = 0;
  v16 = 0;
  v17 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)&Src, a2, v3);
  std::wstring::operator+=(&Src, L"\\CExecSvcStarted");
  v11[0] = 2 * v16;
  v11[1] = 2 * v16;
  v12 = 0;
  p_Src = &Src;
  if ( v17 > 7 )
    p_Src = (__int128 *)Src;
  v13 = p_Src;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 128;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = *EventHandle;
  if ( *EventHandle )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(LastError);
  }
  *EventHandle = 0;
  v8 = NtCreateEvent(EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\common\\cexecevent.cpp",
      (const char *)(unsigned int)v8,
      InitialState);
  std::wstring::~wstring(&Src);
  return EventHandle;
}

```

## disassembly

```asm
0x1400f1dd8  mov     [rsp-8+arg_10], rbx
0x1400f1ddd  mov     [rsp-8+arg_18], rsi
0x1400f1de2  push    rbp
0x1400f1de3  push    rdi
0x1400f1de4  push    r14
0x1400f1de6  lea     rbp, [rsp-47h]
0x1400f1deb  sub     rsp, 0B0h
0x1400f1df2  mov     rax, cs:__security_cookie
0x1400f1df9  xor     rax, rsp
0x1400f1dfc  mov     [rbp+57h+var_20], rax
0x1400f1e00  mov     rbx, rcx
0x1400f1e03  mov     [rbp+57h+var_88], rcx
0x1400f1e07  xor     r14d, r14d
0x1400f1e0a  mov     [rbp+57h+var_90], r14d
0x1400f1e0e  mov     [rcx], r14
0x1400f1e11  mov     [rbp+57h+var_90], 1
0x1400f1e18  xorps   xmm0, xmm0
0x1400f1e1b  movups  [rbp+57h+Src], xmm0
0x1400f1e1f  mov     [rbp+57h+var_30], r14
0x1400f1e23  mov     [rbp+57h+var_28], r14
0x1400f1e27  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400f1e2b  inc     r8
0x1400f1e2e  cmp     [rdx+r8*2], r14w
0x1400f1e33  jnz     short loc_1400F1E2B
0x1400f1e35  lea     rcx, [rbp+57h+Src]
0x1400f1e39  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400f1e3e  nop
0x1400f1e3f  lea     rdx, aCexecsvcstarte; "\\CExecSvcStarted"
0x1400f1e46  lea     rcx, [rbp+57h+Src]; Src
0x1400f1e4a  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400f1e4f  movzx   eax, word ptr [rbp+57h+var_30]
0x1400f1e53  add     ax, ax
0x1400f1e56  mov     [rbp+57h+var_80], ax
0x1400f1e5a  mov     [rbp+57h+var_7E], ax
0x1400f1e5e  xor     eax, eax
0x1400f1e60  mov     [rbp+57h+var_7C], eax
0x1400f1e63  lea     rax, [rbp+57h+Src]
0x1400f1e67  cmp     [rbp+57h+var_28], 7
0x1400f1e6c  cmova   rax, qword ptr [rbp+57h+Src]
0x1400f1e71  mov     [rbp+57h+var_78], rax
0x1400f1e75  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400f1e7d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 80h
0x1400f1e85  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1400f1e89  lea     rax, [rbp+57h+var_80]
0x1400f1e8d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400f1e91  xorps   xmm0, xmm0
0x1400f1e94  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f1e99  mov     rsi, [rbx]
0x1400f1e9c  test    rsi, rsi
0x1400f1e9f  jz      short loc_1400F1EC2
0x1400f1ea1  call    cs:__imp_GetLastError
0x1400f1ea7  mov     edi, eax
0x1400f1ea9  mov     rcx, rsi; hObject
0x1400f1eac  call    cs:__imp_CloseHandle
0x1400f1eb2  mov     rcx, [rbp+5Fh]; this
0x1400f1eb6  test    eax, eax
0x1400f1eb8  jz      short loc_1400F1F2C
0x1400f1eba  mov     ecx, edi; dwErrCode
0x1400f1ebc  call    cs:__imp_SetLastError
0x1400f1ec2  mov     [rbx], r14
0x1400f1ec5  mov     byte ptr [rsp+0C0h+InitialState], r14b; int
0x1400f1eca  xor     r9d, r9d; EventType
0x1400f1ecd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400f1ed1  mov     edx, 1F0003h; DesiredAccess
0x1400f1ed6  mov     rcx, rbx; EventHandle
0x1400f1ed9  call    cs:__imp_NtCreateEvent
0x1400f1edf  mov     rcx, [rbp+5Fh]; this
0x1400f1ee3  test    eax, eax
0x1400f1ee5  js      short loc_1400F1F17
0x1400f1ee7  lea     rcx, [rbp+57h+Src]; void *
0x1400f1eeb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400f1ef0  mov     rax, rbx
0x1400f1ef3  mov     rcx, [rbp+57h+var_20]
0x1400f1ef7  xor     rcx, rsp; StackCookie
0x1400f1efa  call    __security_check_cookie
0x1400f1eff  lea     r11, [rsp+0C0h+var_10]
0x1400f1f07  mov     rbx, [r11+30h]
0x1400f1f0b  mov     rsi, [r11+38h]
0x1400f1f0f  mov     rsp, r11
0x1400f1f12  pop     r14
0x1400f1f14  pop     rdi
0x1400f1f15  pop     rbp
0x1400f1f16  retn
0x1400f1f17  mov     r9d, eax; char *
0x1400f1f1a  lea     r8, aOnecoreVmCompu_28; "onecore\\vm\\compute\\service\\cexec\\c"...
0x1400f1f21  mov     edx, 2Fh ; '/'; void *
0x1400f1f26  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400f1f2c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400f1f33  mov     edx, 0A0Bh; void *
0x1400f1f38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
