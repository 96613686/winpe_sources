# GetRemoteKeyboardLayout(ushort *,ushort *)

- ea: `0x1800565e0`
- end: `0x180056816`
- name: `?GetRemoteKeyboardLayout@@YAHPEAG0@Z`
- size: `566`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800564a0`
- `0x18005f274`

## callees

- `0x18001a2b8`
- `0x1800565e0`
- `0x18005fea0`
- `0x1800610e0`
- `0x180064ba4`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18005665c`
- `ntdll!RtlGetActiveConsoleId` at `0x18005665c`
- `ntdll!NtQueryValueKey` at `0x1800566ed`
- `ntdll!NtQueryValueKey` at `0x1800566ed`
- `ntdll!RtlOpenCurrentUser` at `0x180056741`
- `ntdll!RtlOpenCurrentUser` at `0x180056741`
- `ntdll!NtClose` at `0x1800566f9`
- `ntdll!NtClose` at `0x180056767`
- `ntdll!NtClose` at `0x1800567e7`
- `ntdll!NtClose` at `0x1800566f9`
- `ntdll!NtClose` at `0x180056767`
- `ntdll!NtClose` at `0x1800567e7`
- `ntdll!NtOpenKey` at `0x1800566ae`
- `ntdll!NtOpenKey` at `0x1800566ae`
- `ntdll!RtlInitUnicodeString` at `0x180056675`
- `ntdll!RtlInitUnicodeString` at `0x1800566c3`
- `ntdll!RtlInitUnicodeString` at `0x180056675`
- `ntdll!RtlInitUnicodeString` at `0x1800566c3`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005663f`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005663f`

## string_xrefs

- `0x18005666a`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layout\`

## pseudocode

```c
__int64 __fastcall GetRemoteKeyboardLayout(unsigned __int16 *a1, unsigned __int16 *a2)
{
  ULONG SessionId; // ebx
  ULONG v5; // ebx
  NTSTATUS v6; // ebx
  unsigned int RemoteKeyboardLayoutFromConfigData; // ebx
  int RemoteInputLanguage; // edi
  unsigned int ServerIMEKeyboardLayout; // eax
  HANDLE Handle; // [rsp+30h] [rbp-89h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-81h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-61h] BYREF
  __int128 KeyValueInformation; // [rsp+88h] [rbp-31h] BYREF
  int v17; // [rsp+98h] [rbp-21h]
  WCHAR String2[40]; // [rsp+A0h] [rbp-19h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  ResultLength = 0;
  DestinationString = 0;
  KeyValueInformation = 0;
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId == (unsigned int)WTSGetServiceSessionId() )
    return 0;
  v5 = NtCurrentPeb()->SessionId;
  if ( v5 == (unsigned int)RtlGetActiveConsoleId() )
    return 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layout\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"IgnoreRemoteKeyboardLayout");
    v6 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength);
    NtClose(KeyHandle);
    if ( v6 >= 0 )
    {
      if ( HIDWORD(KeyValueInformation) )
        return 0;
    }
  }
  RemoteKeyboardLayoutFromConfigData = GetRemoteKeyboardLayoutFromConfigData();
  RemoteInputLanguage = GetRemoteInputLanguage(a2, String2);
  if ( (*(_BYTE *)gpsi & 4) != 0 )
  {
    Handle = 0;
    if ( RtlOpenCurrentUser(0x2000000u, &Handle) < 0 )
      return 0;
    ((void (__fastcall *)(_QWORD, HANDLE))off_1800C8720[0])(0, Handle);
    if ( !RemoteInputLanguage )
    {
      NtClose(Handle);
      return 0;
    }
    if ( (HIWORD(RemoteKeyboardLayoutFromConfigData) & 0xF000) == 0xE000 )
    {
      ServerIMEKeyboardLayout = GetServerIMEKeyboardLayout(String2);
      if ( ServerIMEKeyboardLayout )
      {
        RemoteKeyboardLayoutFromConfigData = ServerIMEKeyboardLayout;
      }
      else if ( (RemoteKeyboardLayoutFromConfigData & 0xFF0000) < 0x200000 )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, HANDLE))off_1800C8720[0])(RemoteKeyboardLayoutFromConfigData, Handle) )
          RemoteKeyboardLayoutFromConfigData = (unsigned __int16)RemoteKeyboardLayoutFromConfigData;
        else
          RemoteKeyboardLayoutFromConfigData = 0;
      }
    }
    NtClose(Handle);
  }
  if ( !RemoteKeyboardLayoutFromConfigData )
    return 0;
  StringCchPrintfW(a1, 9u, L"%8.8lx", RemoteKeyboardLayoutFromConfigData);
  return 1;
}

```

## disassembly

```asm
0x1800565e0  mov     [rsp-8+arg_10], rbx
0x1800565e5  push    rbp
0x1800565e6  push    rsi
0x1800565e7  push    rdi
0x1800565e8  lea     rbp, [rsp-47h]
0x1800565ed  sub     rsp, 100h
0x1800565f4  mov     rax, cs:__security_cookie
0x1800565fb  xor     rax, rsp
0x1800565fe  mov     [rbp+57h+var_20], rax
0x180056602  xorps   xmm0, xmm0
0x180056605  mov     [rbp+57h+KeyHandle], 0
0x18005660d  xor     eax, eax
0x18005660f  mov     rdi, rdx
0x180056612  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180056616  mov     [rbp+57h+var_78], eax
0x180056619  mov     rsi, rcx
0x18005661c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180056620  mov     [rsp+110h+var_D8], eax
0x180056624  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180056628  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18005662c  movups  [rbp+57h+KeyValueInformation], xmm0
0x180056630  mov     rax, gs:60h
0x180056639  mov     ebx, [rax+2C0h]
0x18005663f  call    cs:__imp_WTSGetServiceSessionId
0x180056645  cmp     ebx, eax
0x180056647  jz      loc_18005676D
0x18005664d  mov     rax, gs:60h
0x180056656  mov     ebx, [rax+2C0h]
0x18005665c  call    cs:__imp_RtlGetActiveConsoleId
0x180056662  cmp     ebx, eax
0x180056664  jz      loc_18005676D
0x18005666a  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x180056671  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180056675  call    cs:__imp_RtlInitUnicodeString
0x18005667b  lea     rax, [rbp+57h+DestinationString]
0x18005667f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180056686  xorps   xmm0, xmm0
0x180056689  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005668d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180056691  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180056699  mov     edx, 20019h; DesiredAccess
0x18005669e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800566a5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800566a9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800566ae  call    cs:__imp_NtOpenKey
0x1800566b4  test    eax, eax
0x1800566b6  js      short loc_180056709
0x1800566b8  lea     rdx, aIgnoreremoteke; "IgnoreRemoteKeyboardLayout"
0x1800566bf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800566c3  call    cs:__imp_RtlInitUnicodeString
0x1800566c9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800566cd  lea     rax, [rsp+110h+var_D8]
0x1800566d2  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1800566d7  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800566db  mov     r8d, 2; KeyValueInformationClass
0x1800566e1  mov     [rsp+110h+Length], 14h; Length
0x1800566e9  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800566ed  call    cs:__imp_NtQueryValueKey
0x1800566f3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800566f7  mov     ebx, eax
0x1800566f9  call    cs:__imp_NtClose
0x1800566ff  test    ebx, ebx
0x180056701  js      short loc_180056709
0x180056703  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], 0
0x180056707  jnz     short loc_18005676D
0x180056709  call    ?GetRemoteKeyboardLayoutFromConfigData@@YAKXZ; GetRemoteKeyboardLayoutFromConfigData(void)
0x18005670e  lea     rdx, [rbp+57h+String2]; unsigned __int16 *
0x180056712  mov     rcx, rdi; unsigned __int16 *
0x180056715  mov     ebx, eax
0x180056717  call    ?GetRemoteInputLanguage@@YAHPEAG0@Z; GetRemoteInputLanguage(ushort *,ushort *)
0x18005671c  mov     rcx, cs:gpsi
0x180056723  mov     edi, eax
0x180056725  test    byte ptr [rcx], 4
0x180056728  jz      loc_1800567ED
0x18005672e  lea     rdx, [rsp+110h+Handle]; KeyHandle
0x180056733  mov     [rsp+110h+Handle], 0
0x18005673c  mov     ecx, 2000000h; DesiredAccess
0x180056741  call    cs:__imp_RtlOpenCurrentUser
0x180056747  test    eax, eax
0x180056749  js      short loc_18005676D
0x18005674b  mov     rdx, [rsp+110h+Handle]
0x180056750  xor     ecx, ecx
0x180056752  mov     rax, cs:off_1800C8720
0x180056759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005675e  test    edi, edi
0x180056760  jnz     short loc_18005678E
0x180056762  mov     rcx, [rsp+110h+Handle]; Handle
0x180056767  call    cs:__imp_NtClose
0x18005676d  xor     eax, eax
0x18005676f  mov     rcx, [rbp+57h+var_20]
0x180056773  xor     rcx, rsp; StackCookie
0x180056776  call    __security_check_cookie
0x18005677b  mov     rbx, [rsp+110h+arg_10]
0x180056783  add     rsp, 100h
0x18005678a  pop     rdi
0x18005678b  pop     rsi
0x18005678c  pop     rbp
0x18005678d  retn
0x18005678e  mov     ecx, 0F000h
0x180056793  mov     eax, ebx
0x180056795  shr     eax, 10h
0x180056798  and     ax, cx
0x18005679b  mov     ecx, 0E000h
0x1800567a0  cmp     ax, cx
0x1800567a3  jnz     short loc_1800567E2
0x1800567a5  lea     rcx, [rbp+57h+String2]; lpString2
0x1800567a9  call    ?GetServerIMEKeyboardLayout@@YAKPEAG@Z; GetServerIMEKeyboardLayout(ushort *)
0x1800567ae  test    eax, eax
0x1800567b0  jz      short loc_1800567B6
0x1800567b2  mov     ebx, eax
0x1800567b4  jmp     short loc_1800567E2
0x1800567b6  mov     eax, ebx
0x1800567b8  and     eax, 0FF0000h
0x1800567bd  cmp     eax, 200000h
0x1800567c2  jnb     short loc_1800567E2
0x1800567c4  mov     rdx, [rsp+110h+Handle]
0x1800567c9  mov     ecx, ebx
0x1800567cb  mov     rax, cs:off_1800C8720
0x1800567d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567d7  test    eax, eax
0x1800567d9  jz      short loc_1800567E0
0x1800567db  movzx   ebx, bx
0x1800567de  jmp     short loc_1800567E2
0x1800567e0  xor     ebx, ebx
0x1800567e2  mov     rcx, [rsp+110h+Handle]; Handle
0x1800567e7  call    cs:__imp_NtClose
0x1800567ed  test    ebx, ebx
0x1800567ef  jz      loc_18005676D
0x1800567f5  mov     r9d, ebx
0x1800567f8  lea     r8, a88lx; "%8.8lx"
0x1800567ff  mov     edx, 9; unsigned __int64
0x180056804  mov     rcx, rsi; unsigned __int16 *
0x180056807  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005680c  mov     eax, 1
0x180056811  jmp     loc_18005676F
```
