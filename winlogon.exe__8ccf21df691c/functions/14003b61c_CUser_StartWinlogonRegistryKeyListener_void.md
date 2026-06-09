# CUser::StartWinlogonRegistryKeyListener(void)

- ea: `0x14003b61c`
- end: `0x14003b81f`
- name: `?StartWinlogonRegistryKeyListener@CUser@@QEAAKXZ`
- size: `515`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003394c`

## callees

- `0x1400057f4`
- `0x14003b61c`
- `0x14003b828`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003b6e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14003b6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b759`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b69a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003b69a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14003b7b6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x14003b7b6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x14003b74f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x14003b74f`

## pseudocode

```c
__int64 __fastcall CUser::StartWinlogonRegistryKeyListener(CUser *this)
{
  DWORD LastError; // ebx
  CUser *v4; // rcx
  __int64 v5; // rdx
  HANDLE EventW; // rax
  CUser *v7; // rcx
  __int64 v8; // rdx

  if ( *((_DWORD *)this + 160) != 1 )
  {
    CUser::StopWinlogonRegistryKeyListener(this);
    LastError = RegOpenKeyExW(
                  *((HKEY *)this + 29),
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                  0,
                  0x20019u,
                  (PHKEY)this + 76);
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v5 = 242;
      goto LABEL_30;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 77) = EventW;
    if ( EventW )
    {
      if ( RegisterWaitForSingleObject(
             (PHANDLE)this + 78,
             EventW,
             CUser::WinlogonKeyChangedCallback,
             this,
             0xFFFFFFFF,
             0) )
      {
        LastError = RegNotifyChangeKeyValue(*((HKEY *)this + 76), 0, 4u, *((HANDLE *)this + 77), 1);
        if ( !LastError )
        {
          *((_DWORD *)this + 160) = 1;
          return LastError;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_31:
          CUser::StopWinlogonRegistryKeyListener(this);
          return LastError;
        }
        v5 = 245;
LABEL_30:
        WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
        goto LABEL_31;
      }
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 244;
        goto LABEL_22;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 243;
LABEL_22:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
      }
    }
    if ( !LastError )
      return LastError;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14003b61c  mov     [rsp+arg_0], rbx
0x14003b621  mov     [rsp+arg_8], rsi
0x14003b626  push    rdi
0x14003b627  sub     rsp, 30h
0x14003b62b  cmp     dword ptr [rcx+280h], 1
0x14003b632  mov     rdi, rcx
0x14003b635  jnz     short loc_14003B672
0x14003b637  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b63e  lea     rax, WPP_GLOBAL_Control
0x14003b645  cmp     rcx, rax
0x14003b648  jz      short loc_14003B66B
0x14003b64a  test    byte ptr [rcx+1Ch], 20h
0x14003b64e  jz      short loc_14003B66B
0x14003b650  cmp     byte ptr [rcx+19h], 5
0x14003b654  jb      short loc_14003B66B
0x14003b656  mov     rcx, [rcx+10h]
0x14003b65a  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003b661  mov     edx, 0F1h
0x14003b666  call    WPP_SF_
0x14003b66b  xor     eax, eax
0x14003b66d  jmp     loc_14003B80F
0x14003b672  call    ?StopWinlogonRegistryKeyListener@CUser@@QEAAXXZ; CUser::StopWinlogonRegistryKeyListener(void)
0x14003b677  mov     rcx, [rdi+0E8h]; hKey
0x14003b67e  lea     rsi, [rdi+260h]
0x14003b685  mov     r9d, 20019h; samDesired
0x14003b68b  mov     [rsp+38h+phkResult], rsi; phkResult
0x14003b690  xor     r8d, r8d; ulOptions
0x14003b693  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14003b69a  call    cs:__imp_RegOpenKeyExW
0x14003b6a0  mov     ebx, eax
0x14003b6a2  test    eax, eax
0x14003b6a4  jz      short loc_14003B6DB
0x14003b6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b6ad  lea     rax, WPP_GLOBAL_Control
0x14003b6b4  cmp     rcx, rax
0x14003b6b7  jz      loc_14003B7F9
0x14003b6bd  test    byte ptr [rcx+1Ch], 20h
0x14003b6c1  jz      loc_14003B7F9
0x14003b6c7  cmp     byte ptr [rcx+19h], 2
0x14003b6cb  jb      loc_14003B7F9
0x14003b6d1  mov     edx, 0F2h
0x14003b6d6  jmp     loc_14003B7E6
0x14003b6db  xor     r9d, r9d; lpName
0x14003b6de  xor     r8d, r8d; bInitialState
0x14003b6e1  xor     ecx, ecx; lpEventAttributes
0x14003b6e3  lea     edx, [r9+1]; bManualReset
0x14003b6e7  call    cs:__imp_CreateEventW
0x14003b6ed  mov     [rdi+268h], rax
0x14003b6f4  test    rax, rax
0x14003b6f7  jnz     short loc_14003B72B
0x14003b6f9  call    cs:__imp_GetLastError
0x14003b6ff  mov     ebx, eax
0x14003b701  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b708  lea     rax, WPP_GLOBAL_Control
0x14003b70f  cmp     rcx, rax
0x14003b712  jz      loc_14003B798
0x14003b718  test    byte ptr [rcx+1Ch], 20h
0x14003b71c  jz      short loc_14003B798
0x14003b71e  cmp     byte ptr [rcx+19h], 2
0x14003b722  jb      short loc_14003B798
0x14003b724  mov     edx, 0F3h
0x14003b729  jmp     short loc_14003B785
0x14003b72b  lea     rcx, [rdi+270h]; phNewWaitObject
0x14003b732  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14003b73a  mov     r9, rdi; Context
0x14003b73d  mov     dword ptr [rsp+38h+phkResult], 0FFFFFFFFh; dwMilliseconds
0x14003b745  lea     r8, ?WinlogonKeyChangedCallback@CUser@@CAXPEAXE@Z; Callback
0x14003b74c  mov     rdx, rax; hObject
0x14003b74f  call    cs:__imp_RegisterWaitForSingleObject
0x14003b755  test    eax, eax
0x14003b757  jnz     short loc_14003B79E
0x14003b759  call    cs:__imp_GetLastError
0x14003b75f  mov     ebx, eax
0x14003b761  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b768  lea     rax, WPP_GLOBAL_Control
0x14003b76f  cmp     rcx, rax
0x14003b772  jz      short loc_14003B798
0x14003b774  test    byte ptr [rcx+1Ch], 20h
0x14003b778  jz      short loc_14003B798
0x14003b77a  cmp     byte ptr [rcx+19h], 2
0x14003b77e  jb      short loc_14003B798
0x14003b780  mov     edx, 0F4h
0x14003b785  mov     rcx, [rcx+10h]
0x14003b789  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003b790  mov     r9d, ebx
0x14003b793  call    WPP_SF_d
0x14003b798  test    ebx, ebx
0x14003b79a  jnz     short loc_14003B7F9
0x14003b79c  jmp     short loc_14003B80D
0x14003b79e  mov     r9, [rdi+268h]; hEvent
0x14003b7a5  xor     edx, edx; bWatchSubtree
0x14003b7a7  mov     rcx, [rsi]; hKey
0x14003b7aa  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x14003b7b2  lea     r8d, [rdx+4]; dwNotifyFilter
0x14003b7b6  call    cs:__imp_RegNotifyChangeKeyValue
0x14003b7bc  mov     ebx, eax
0x14003b7be  test    eax, eax
0x14003b7c0  jz      short loc_14003B803
0x14003b7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b7c9  lea     rax, WPP_GLOBAL_Control
0x14003b7d0  cmp     rcx, rax
0x14003b7d3  jz      short loc_14003B7F9
0x14003b7d5  test    byte ptr [rcx+1Ch], 20h
0x14003b7d9  jz      short loc_14003B7F9
0x14003b7db  cmp     byte ptr [rcx+19h], 2
0x14003b7df  jb      short loc_14003B7F9
0x14003b7e1  mov     edx, 0F5h
0x14003b7e6  mov     rcx, [rcx+10h]
0x14003b7ea  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003b7f1  mov     r9d, ebx
0x14003b7f4  call    WPP_SF_d
0x14003b7f9  mov     rcx, rdi; this
0x14003b7fc  call    ?StopWinlogonRegistryKeyListener@CUser@@QEAAXXZ; CUser::StopWinlogonRegistryKeyListener(void)
0x14003b801  jmp     short loc_14003B80D
0x14003b803  mov     dword ptr [rdi+280h], 1
0x14003b80d  mov     eax, ebx
0x14003b80f  mov     rbx, [rsp+38h+arg_0]
0x14003b814  mov     rsi, [rsp+38h+arg_8]
0x14003b819  add     rsp, 30h
0x14003b81d  pop     rdi
0x14003b81e  retn
```
