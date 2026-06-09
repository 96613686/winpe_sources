# RemoteDoSendWindowMessage

- ea: `0x180012618`
- end: `0x180012911`
- name: `RemoteDoSendWindowMessage`
- size: `761`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800104f0`

## callees

- `0x180012618`
- `0x180012e40`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180012708`
- `ntdll!NtQueryValueKey` at `0x180012708`
- `ntdll!NtOpenKey` at `0x1800126b7`
- `ntdll!NtOpenKey` at `0x1800126b7`
- `ntdll!RtlInitUnicodeString` at `0x180012678`
- `ntdll!RtlInitUnicodeString` at `0x1800126d9`
- `ntdll!RtlInitUnicodeString` at `0x180012678`
- `ntdll!RtlInitUnicodeString` at `0x1800126d9`
- `ntdll!NtClose` at `0x180012733`
- `ntdll!NtClose` at `0x180012733`
- `win32u!NtUserSetInformationThread` at `0x180012836`
- `win32u!NtUserSetInformationThread` at `0x180012836`
- `USER32!SendMessageTimeoutW` at `0x18001286c`
- `USER32!SendMessageTimeoutW` at `0x18001286c`
- `USER32!GetGUIThreadInfo` at `0x180012781`
- `USER32!GetGUIThreadInfo` at `0x180012781`
- `USER32!SendInput` at `0x1800128e5`
- `USER32!SendInput` at `0x1800128e5`
- `USER32!SendNotifyMessageW` at `0x1800127c2`
- `USER32!SendNotifyMessageW` at `0x180012805`
- `USER32!SendNotifyMessageW` at `0x1800127c2`
- `USER32!SendNotifyMessageW` at `0x180012805`

## string_xrefs

- `0x180012661`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server`

## pseudocode

```c
__int64 __fastcall RemoteDoSendWindowMessage(__int64 a1, __int64 a2, __int64 a3)
{
  LPARAM v4; // r9
  __int64 v5; // rcx
  HWND hwndActive; // rcx
  WORD v8; // ax
  ULONG ResultLength; // [rsp+40h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-51h] BYREF
  ULONG_PTR dwResult; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  struct tagGUITHREADINFO ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  struct tagINPUT KeyValueInformation; // [rsp+C0h] [rbp+27h] BYREF

  dwResult = 0;
  if ( !dword_18001D918 )
  {
    KeyHandle = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server");
    ObjectAttributes.cbSize = 48;
    ObjectAttributes.hwndFocus = (HWND)&DestinationString;
    ObjectAttributes.hwndActive = 0;
    LODWORD(ObjectAttributes.hwndCapture) = 64;
    *(_OWORD *)&ObjectAttributes.hwndMenuOwner = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, (POBJECT_ATTRIBUTES)&ObjectAttributes) >= 0 )
    {
      ResultLength = 0;
      RtlInitUnicodeString(&DestinationString, L"NotificationTimeOut");
      if ( NtQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength) >= 0 )
      {
        uTimeout = KeyValueInformation.ki.dwFlags;
        if ( !KeyValueInformation.mi.dy )
          uTimeout = 10000;
      }
      NtClose(KeyHandle);
    }
    dword_18001D918 = 1;
  }
  v4 = a1 + 88;
  if ( !*(_DWORD *)(a1 + 8280) )
    v4 = *(_QWORD *)(a1 + 80);
  v5 = *(unsigned int *)(a1 + 64);
  if ( (_DWORD)v5 != 793 )
  {
    if ( (unsigned int)(v5 - 256) <= 1 )
    {
      v8 = *(_WORD *)(a1 + 72);
      memset(&KeyValueInformation, 0, sizeof(KeyValueInformation));
      KeyValueInformation.ki.wVk = v8;
      KeyValueInformation.ki.wScan = *(_WORD *)(a1 + 80);
      KeyValueInformation.type = 1;
      KeyValueInformation.mi.dy = (KeyValueInformation.ki.wScan != 0 ? 4 : 1) | ((_DWORD)v5 != 256 ? 2 : 0);
      SendInput(1u, &KeyValueInformation, 40);
      return 0;
    }
    switch ( (_DWORD)v5 )
    {
      case 0x32F:
        MicrosoftTelemetryAssertTriggeredNoArgs(v5, a2, a3, v4);
        return 0;
      case 0x1A:
        SendNotifyMessageW(*(HWND *)(a1 + 56), 0x1Au, *(_QWORD *)(a1 + 72), v4);
        *(_DWORD *)(a1 + 8296) = 0;
        return 0;
      case 0x2CE:
        NtUserSetInformationThread(-2, 17, 0);
        return 0;
    }
    if ( SendMessageTimeoutW(*(HWND *)(a1 + 56), v5, *(_QWORD *)(a1 + 72), v4, 2u, uTimeout, &dwResult) )
    {
      *(_DWORD *)(a1 + 8296) = dwResult;
      return 0;
    }
    return 3221225473LL;
  }
  memset_0(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.cbSize = 72;
  if ( !GetGUIThreadInfo(0, &ObjectAttributes) )
    return 3221225473LL;
  hwndActive = ObjectAttributes.hwndActive;
  if ( ObjectAttributes.hwndFocus )
    hwndActive = ObjectAttributes.hwndFocus;
  if ( !hwndActive )
    return 3221225473LL;
  SendNotifyMessageW(hwndActive, 0x319u, (WPARAM)hwndActive, (*(_QWORD *)(a1 + 72) | 0x1000LL) << 16);
  return 0;
}

```

## disassembly

```asm
0x180012618  mov     [rsp-8+arg_8], rbx
0x18001261d  push    rbp
0x18001261e  lea     rbp, [rsp-57h]
0x180012623  sub     rsp, 0F0h
0x18001262a  mov     rax, cs:__security_cookie
0x180012631  xor     rax, rsp
0x180012634  mov     [rbp+57h+var_8], rax
0x180012638  cmp     cs:dword_18001D918, 0
0x18001263f  mov     rbx, rcx
0x180012642  mov     [rbp+57h+dwResult], 0
0x18001264a  jnz     loc_180012749
0x180012650  xorps   xmm0, xmm0
0x180012653  mov     [rbp+57h+KeyHandle], 0
0x18001265b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001265f  xor     eax, eax
0x180012661  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x180012668  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001266c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180012670  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180012674  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180012678  call    cs:__imp_RtlInitUnicodeString
0x18001267f  nop     dword ptr [rax+rax+00h]
0x180012684  lea     rax, [rbp+57h+DestinationString]
0x180012688  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001268f  xorps   xmm0, xmm0
0x180012692  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180012696  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001269a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800126a2  mov     edx, 20019h; DesiredAccess
0x1800126a7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800126ae  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800126b2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800126b7  call    cs:__imp_NtOpenKey
0x1800126be  nop     dword ptr [rax+rax+00h]
0x1800126c3  test    eax, eax
0x1800126c5  js      short loc_18001273F
0x1800126c7  lea     rdx, aNotificationti; "NotificationTimeOut"
0x1800126ce  mov     [rbp+57h+var_B0], 0
0x1800126d5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800126d9  call    cs:__imp_RtlInitUnicodeString
0x1800126e0  nop     dword ptr [rax+rax+00h]
0x1800126e5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800126e9  lea     rax, [rbp+57h+var_B0]
0x1800126ed  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x1800126f2  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800126f6  mov     r8d, 2; KeyValueInformationClass
0x1800126fc  mov     [rsp+0F0h+Length], 14h; Length
0x180012704  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180012708  call    cs:__imp_NtQueryValueKey
0x18001270f  nop     dword ptr [rax+rax+00h]
0x180012714  test    eax, eax
0x180012716  js      short loc_18001272F
0x180012718  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18001271b  mov     cs:uTimeout, eax
0x180012721  test    eax, eax
0x180012723  jnz     short loc_18001272F
0x180012725  mov     cs:uTimeout, 2710h
0x18001272f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180012733  call    cs:__imp_NtClose
0x18001273a  nop     dword ptr [rax+rax+00h]
0x18001273f  mov     cs:dword_18001D918, 1
0x180012749  cmp     dword ptr [rbx+2058h], 0
0x180012750  lea     r9, [rbx+58h]
0x180012754  jnz     short loc_18001275A
0x180012756  mov     r9, [rbx+50h]; lParam
0x18001275a  mov     ecx, [rbx+40h]
0x18001275d  cmp     ecx, 319h
0x180012763  jnz     short loc_1800127D3
0x180012765  xor     edx, edx; Val
0x180012767  lea     rcx, [rbp+57h+ObjectAttributes]; void *
0x18001276b  lea     r8d, [rdx+48h]; Size
0x18001276f  call    memset_0
0x180012774  lea     rdx, [rbp+57h+ObjectAttributes]; pgui
0x180012778  mov     [rbp+57h+ObjectAttributes.Length], 48h ; 'H'
0x18001277f  xor     ecx, ecx; idThread
0x180012781  call    cs:__imp_GetGUIThreadInfo
0x180012788  nop     dword ptr [rax+rax+00h]
0x18001278d  test    eax, eax
0x18001278f  jz      loc_18001287D
0x180012795  mov     rax, [rbp+57h+ObjectAttributes.ObjectName]
0x180012799  mov     rcx, [rbp+57h+ObjectAttributes.RootDirectory]
0x18001279d  test    rax, rax
0x1800127a0  cmovnz  rcx, rax; hWnd
0x1800127a4  test    rcx, rcx
0x1800127a7  jz      loc_18001287D
0x1800127ad  mov     r9, [rbx+48h]
0x1800127b1  mov     r8, rcx; wParam
0x1800127b4  bts     r9, 0Ch
0x1800127b9  mov     edx, 319h; Msg
0x1800127be  shl     r9, 10h; lParam
0x1800127c2  call    cs:__imp_SendNotifyMessageW
0x1800127c9  nop     dword ptr [rax+rax+00h]
0x1800127ce  jmp     loc_1800128F1
0x1800127d3  lea     eax, [rcx-100h]
0x1800127d9  cmp     eax, 1
0x1800127dc  jbe     loc_18001288F
0x1800127e2  cmp     ecx, 32Fh
0x1800127e8  jnz     short loc_1800127F4
0x1800127ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800127ef  jmp     loc_1800128F1
0x1800127f4  mov     edx, 1Ah; Msg
0x1800127f9  cmp     ecx, edx
0x1800127fb  jnz     short loc_180012820
0x1800127fd  mov     r8, [rbx+48h]; wParam
0x180012801  mov     rcx, [rbx+38h]; hWnd
0x180012805  call    cs:__imp_SendNotifyMessageW
0x18001280c  nop     dword ptr [rax+rax+00h]
0x180012811  mov     dword ptr [rbx+2068h], 0
0x18001281b  jmp     loc_1800128F1
0x180012820  cmp     ecx, 2CEh
0x180012826  jnz     short loc_180012847
0x180012828  xor     r9d, r9d
0x18001282b  xor     r8d, r8d
0x18001282e  lea     edx, [r9+11h]
0x180012832  lea     rcx, [r9-2]
0x180012836  call    cs:__imp_NtUserSetInformationThread
0x18001283d  nop     dword ptr [rax+rax+00h]
0x180012842  jmp     loc_1800128F1
0x180012847  mov     r8, [rbx+48h]; wParam
0x18001284b  lea     rax, [rbp+57h+dwResult]
0x18001284f  mov     [rsp+0F0h+lpdwResult], rax; lpdwResult
0x180012854  mov     edx, ecx; Msg
0x180012856  mov     eax, cs:uTimeout
0x18001285c  mov     rcx, [rbx+38h]; hWnd
0x180012860  mov     dword ptr [rsp+0F0h+ResultLength], eax; uTimeout
0x180012864  mov     [rsp+0F0h+Length], 2; fuFlags
0x18001286c  call    cs:__imp_SendMessageTimeoutW
0x180012873  nop     dword ptr [rax+rax+00h]
0x180012878  test    rax, rax
0x18001287b  jnz     short loc_180012884
0x18001287d  mov     eax, 0C0000001h
0x180012882  jmp     short loc_1800128F3
0x180012884  mov     eax, dword ptr [rbp+57h+dwResult]
0x180012887  mov     [rbx+2068h], eax
0x18001288d  jmp     short loc_1800128F1
0x18001288f  xor     eax, eax
0x180012891  sub     ecx, 100h
0x180012897  mov     [rbp+57h+var_10], rax
0x18001289b  neg     ecx
0x18001289d  movzx   eax, word ptr [rbx+48h]
0x1800128a1  xorps   xmm0, xmm0
0x1800128a4  sbb     r8d, r8d
0x1800128a7  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800128ab  and     r8d, 2
0x1800128af  mov     word ptr [rbp+57h+KeyValueInformation+8], ax
0x1800128b3  movzx   eax, word ptr [rbx+50h]
0x1800128b7  mov     word ptr [rbp+57h+KeyValueInformation+0Ah], ax
0x1800128bb  neg     ax
0x1800128be  movups  [rbp+57h+var_20], xmm0
0x1800128c2  sbb     edx, edx
0x1800128c4  mov     dword ptr [rbp+57h+KeyValueInformation], 1
0x1800128cb  and     edx, 3
0x1800128ce  inc     edx
0x1800128d0  or      r8d, edx
0x1800128d3  lea     rdx, [rbp+57h+KeyValueInformation]; pInputs
0x1800128d7  mov     dword ptr [rbp+57h+KeyValueInformation+0Ch], r8d
0x1800128db  mov     r8d, 28h ; '('; cbSize
0x1800128e1  lea     ecx, [r8-27h]; cInputs
0x1800128e5  call    cs:__imp_SendInput
0x1800128ec  nop     dword ptr [rax+rax+00h]
0x1800128f1  xor     eax, eax
0x1800128f3  mov     rcx, [rbp+57h+var_8]
0x1800128f7  xor     rcx, rsp; StackCookie
0x1800128fa  call    __security_check_cookie
0x1800128ff  mov     rbx, [rsp+0F0h+arg_8]
0x180012907  add     rsp, 0F0h
0x18001290e  pop     rbp
0x18001290f  retn
```
