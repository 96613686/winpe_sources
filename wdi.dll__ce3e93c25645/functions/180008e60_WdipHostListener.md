# WdipHostListener

- ea: `0x180008e60`
- end: `0x18000927b`
- name: `WdipHostListener`
- size: `1051`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180003420`
- `0x180008e60`
- `0x18000d228`
- `0x18000f1f0`

## import_xrefs

- `ntdll!AlpcGetMessageAttribute` at `0x180008eed`
- `ntdll!AlpcGetMessageAttribute` at `0x180008eed`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180008edd`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180008edd`
- `ntdll!NtAlpcCancelMessage` at `0x180008f67`
- `ntdll!NtAlpcCancelMessage` at `0x180008fb1`
- `ntdll!NtAlpcCancelMessage` at `0x18000924a`
- `ntdll!NtAlpcCancelMessage` at `0x180008f67`
- `ntdll!NtAlpcCancelMessage` at `0x180008fb1`
- `ntdll!NtAlpcCancelMessage` at `0x18000924a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180008f35`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180008f96`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009170`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800091eb`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180008f35`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180008f96`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009170`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800091eb`
- `ntdll!RtlNtStatusToDosError` at `0x180008fb9`
- `ntdll!RtlNtStatusToDosError` at `0x180009086`
- `ntdll!RtlNtStatusToDosError` at `0x180009180`
- `ntdll!RtlNtStatusToDosError` at `0x1800091f7`
- `ntdll!RtlNtStatusToDosError` at `0x180008fb9`
- `ntdll!RtlNtStatusToDosError` at `0x180009086`
- `ntdll!RtlNtStatusToDosError` at `0x180009180`
- `ntdll!RtlNtStatusToDosError` at `0x1800091f7`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180009076`
- `ntdll!NtAlpcAcceptConnectPort` at `0x180009076`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008ec3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800090cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008ec3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800090cf`

## string_xrefs

- `0x180008fee`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationsrv.cpp`
- `0x180009123`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationsrv.cpp`
- `0x1800091b2`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationsrv.cpp`
- `0x180009225`: `clientcore\base\diagnosis\pdi\wdi\framework\library\communicationsrv.cpp`

## pseudocode

```c
__int64 __fastcall WdipHostListener(__int64 a1, void *a2)
{
  __int64 v3; // r15
  _BYTE *v4; // rdi
  __int64 MessageAttribute; // r12
  NTSTATUS v6; // esi
  __int64 v7; // rax
  signed int Args; // ebx
  signed int v9; // eax
  signed int v10; // eax
  bool v11; // sf
  int v12; // r8d
  NTSTATUS v13; // ebx
  int Session; // eax
  signed int v15; // eax
  bool v16; // sf
  bool v17; // sf
  unsigned __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[256]; // [rsp+110h] [rbp+10h] BYREF

  v20 = 160;
  v19 = 0;
  v3 = 0;
  if ( _InterlockedIncrement(&g_lReceivedHostMessageCount) == g_lExpectedHostMessageCount )
    SetEvent(g_hTPHostShutdown);
  AlpcInitializeMessageAttribute(2684354560LL, v22, v20, &v20);
  v4 = v23;
  MessageAttribute = AlpcGetMessageAttribute(v22, 0x20000000);
  v19 = 248;
  v6 = NtAlpcSendWaitReceivePort(g_hDMHost, 0, 0, 0, v23, &v19, v22, 0);
  if ( v6 != -1073741789 )
  {
LABEL_8:
    Args = 0;
    if ( v6 >= 0 )
      goto LABEL_13;
    goto LABEL_9;
  }
  if ( v19 <= 0xF8 )
    goto LABEL_9;
  v7 = WdipAlloc(v19);
  v3 = v7;
  if ( v7 )
  {
    v4 = (_BYTE *)v7;
    v6 = NtAlpcSendWaitReceivePort(g_hDMHost, 0, 0, 0, v7, &v19, v22, 0);
    goto LABEL_8;
  }
  NtAlpcCancelMessage(g_hDMHost, 0, MessageAttribute);
LABEL_9:
  NtAlpcCancelMessage(g_hDMHost, 0, MessageAttribute);
  v9 = RtlNtStatusToDosError(v6);
  Args = v9;
  if ( v9 > 0 )
    Args = (unsigned __int16)v9 | 0x80070000;
  if ( Args < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
      (int)L"WdipHostListener",
      238,
      (int)L"Error = %d",
      Args);
    return WdipFree(v3);
  }
LABEL_13:
  if ( (*((unsigned __int16 *)v4 + 2) & 0xFFFF00FF) != 1 )
  {
    if ( (*((unsigned __int16 *)v4 + 2) & 0xFFFF00FF) != 3 )
    {
      if ( (*((unsigned __int16 *)v4 + 2) & 0xFFFF00FF) != 5 )
      {
        if ( (*((unsigned __int16 *)v4 + 2) & 0xFFFF00FF) != 0xA )
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
            (int)L"WdipHostListener",
            340,
            (int)L"Error = %d",
            255);
          goto LABEL_45;
        }
        v21 = 0;
        if ( (int)NtAlpcAcceptConnectPort(&v21, g_hDMHost, 0, 0, 0, 0, v4, v22, 0) < 0 )
        {
          v10 = RtlNtStatusToDosError(Args);
          v11 = v10 < 0;
          if ( v10 > 0 )
          {
            v10 = (unsigned __int16)v10 | 0x80070000;
            v11 = v10 < 0;
          }
          if ( v11 )
          {
            v12 = 262;
LABEL_44:
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
              (int)L"WdipHostListener",
              v12,
              (int)L"Error = %d",
              v10);
LABEL_45:
            if ( (*((_WORD *)v4 + 2) & 0x2000) != 0 )
              NtAlpcCancelMessage(g_hDMHost, 0, MessageAttribute);
            return WdipFree(v3);
          }
        }
        return WdipFree(v3);
      }
LABEL_26:
      SetEvent(a2);
      return WdipFree(v3);
    }
    if ( v19 < 0xF8 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
        (int)L"WdipHostListener",
        290,
        (int)L"Error = %d",
        5);
      goto LABEL_45;
    }
    if ( *((_DWORD *)v4 + 11) == 28 )
      goto LABEL_26;
    if ( *((_DWORD *)v4 + 11) == 5 )
    {
      Session = WdipLoadSession((int)g_hDMHost, (__int64)v4);
    }
    else
    {
      v13 = 0;
      if ( *((_DWORD *)v4 + 11) != 18 )
        goto LABEL_33;
      Session = WdipCancelInstance(v4);
    }
    v13 = Session;
    if ( Session < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
        (int)L"WdipHostListener",
        308,
        (int)L"Error = %d",
        Session);
      v13 = 0;
    }
LABEL_33:
    if ( (*((_WORD *)v4 + 2) & 0x2000) != 0
      && (int)NtAlpcSendWaitReceivePort(g_hDMHost, 0x10000, v4, v22, 0, &v19, 0, 0) < 0 )
    {
      v15 = RtlNtStatusToDosError(v13);
      v16 = v15 < 0;
      if ( v15 > 0 )
      {
        v15 = (unsigned __int16)v15 | 0x80070000;
        v16 = v15 < 0;
      }
      if ( v16 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\communicationsrv.cpp",
          (int)L"WdipHostListener",
          325,
          (int)L"Error = %d",
          v15);
        goto LABEL_45;
      }
    }
    return WdipFree(v3);
  }
  if ( (int)NtAlpcSendWaitReceivePort(g_hDMHost, 0x10000, v4, 0, 0, &v19, 0, 0) < 0 )
  {
    v10 = RtlNtStatusToDosError(Args);
    v17 = v10 < 0;
    if ( v10 > 0 )
    {
      v10 = (unsigned __int16)v10 | 0x80070000;
      v17 = v10 < 0;
    }
    if ( v17 )
    {
      v12 = 281;
      goto LABEL_44;
    }
  }
  return WdipFree(v3);
}

```

## disassembly

```asm
0x180008e60  push    rbp
0x180008e62  push    rbx
0x180008e63  push    rsi
0x180008e64  push    rdi
0x180008e65  push    r12
0x180008e67  push    r13
0x180008e69  push    r14
0x180008e6b  push    r15
0x180008e6d  lea     rbp, [rsp-128h]
0x180008e75  sub     rsp, 228h
0x180008e7c  mov     rax, cs:__security_cookie
0x180008e83  xor     rax, rsp
0x180008e86  mov     [rbp+160h+var_50], rax
0x180008e8d  xor     r13d, r13d
0x180008e90  mov     [rsp+260h+var_208], 0A0h
0x180008e99  mov     r14, rdx
0x180008e9c  mov     [rsp+260h+var_210], r13
0x180008ea1  mov     r15d, r13d
0x180008ea4  lea     ecx, [r13+1]
0x180008ea8  lock xadd cs:g_lReceivedHostMessageCount, ecx
0x180008eb0  mov     eax, cs:g_lExpectedHostMessageCount
0x180008eb6  inc     ecx
0x180008eb8  cmp     ecx, eax
0x180008eba  jnz     short loc_180008EC9
0x180008ebc  mov     rcx, cs:g_hTPHostShutdown; hEvent
0x180008ec3  call    cs:__imp_SetEvent
0x180008ec9  mov     r8, [rsp+260h+var_208]
0x180008ece  lea     r9, [rsp+260h+var_208]
0x180008ed3  lea     rdx, [rsp+260h+var_1F0]
0x180008ed8  mov     ecx, 0A0000000h
0x180008edd  call    cs:__imp_AlpcInitializeMessageAttribute
0x180008ee3  mov     edx, 20000000h
0x180008ee8  lea     rcx, [rsp+260h+var_1F0]
0x180008eed  call    cs:__imp_AlpcGetMessageAttribute
0x180008ef3  mov     rcx, cs:g_hDMHost
0x180008efa  lea     rdi, [rbp+160h+var_150]
0x180008efe  mov     r12, rax
0x180008f01  mov     [rsp+260h+var_228], r13
0x180008f06  lea     rax, [rsp+260h+var_1F0]
0x180008f0b  mov     ebx, 0F8h
0x180008f10  mov     [rsp+260h+var_230], rax
0x180008f15  xor     r9d, r9d
0x180008f18  lea     rax, [rsp+260h+var_210]
0x180008f1d  mov     [rsp+260h+var_210], rbx
0x180008f22  mov     [rsp+260h+var_238], rax
0x180008f27  xor     r8d, r8d
0x180008f2a  lea     rax, [rbp+160h+var_150]
0x180008f2e  xor     edx, edx
0x180008f30  mov     qword ptr [rsp+260h+Args], rax
0x180008f35  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180008f3b  mov     esi, eax
0x180008f3d  cmp     eax, 0C0000023h
0x180008f42  jnz     short loc_180008F9E
0x180008f44  mov     rcx, [rsp+260h+var_210]
0x180008f49  cmp     rcx, rbx
0x180008f4c  jbe     short loc_180008FA5
0x180008f4e  call    WdipAlloc
0x180008f53  mov     rcx, cs:g_hDMHost
0x180008f5a  xor     edx, edx
0x180008f5c  mov     r15, rax
0x180008f5f  test    rax, rax
0x180008f62  jnz     short loc_180008F6F
0x180008f64  mov     r8, r12
0x180008f67  call    cs:__imp_NtAlpcCancelMessage
0x180008f6d  jmp     short loc_180008FA5
0x180008f6f  mov     [rsp+260h+var_228], r13
0x180008f74  lea     rax, [rsp+260h+var_1F0]
0x180008f79  mov     [rsp+260h+var_230], rax
0x180008f7e  xor     r9d, r9d
0x180008f81  lea     rax, [rsp+260h+var_210]
0x180008f86  xor     r8d, r8d
0x180008f89  mov     [rsp+260h+var_238], rax
0x180008f8e  mov     rdi, r15
0x180008f91  mov     qword ptr [rsp+260h+Args], r15
0x180008f96  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180008f9c  mov     esi, eax
0x180008f9e  mov     ebx, r13d
0x180008fa1  test    esi, esi
0x180008fa3  jns     short loc_180008FFF
0x180008fa5  mov     rcx, cs:g_hDMHost
0x180008fac  mov     r8, r12
0x180008faf  xor     edx, edx
0x180008fb1  call    cs:__imp_NtAlpcCancelMessage
0x180008fb7  mov     ecx, esi; Status
0x180008fb9  call    cs:__imp_RtlNtStatusToDosError
0x180008fbf  mov     ebx, eax
0x180008fc1  mov     esi, 80070000h
0x180008fc6  test    eax, eax
0x180008fc8  jle     short loc_180008FCF
0x180008fca  movzx   ebx, ax
0x180008fcd  or      ebx, esi
0x180008fcf  test    ebx, ebx
0x180008fd1  jns     short loc_180009004
0x180008fd3  movzx   eax, bx
0x180008fd6  lea     r9, aErrorD_0; "Error = %d"
0x180008fdd  mov     r8d, 0EEh; int
0x180008fe3  mov     dword ptr [rsp+260h+Args], eax; Args
0x180008fe7  lea     rdx, aWdiphostlisten; "WdipHostListener"
0x180008fee  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008ff5  call    WdipTraceError
0x180008ffa  jmp     loc_180009250
0x180008fff  mov     esi, 80070000h
0x180009004  movzx   ecx, word ptr [rdi+4]
0x180009008  and     ecx, 0FFFF00FFh
0x18000900e  sub     ecx, 1
0x180009011  jz      loc_1800091C0
0x180009017  sub     ecx, 2
0x18000901a  jz      loc_1800090A8
0x180009020  sub     ecx, 2
0x180009023  jz      loc_1800090CC
0x180009029  cmp     ecx, 5
0x18000902c  jz      short loc_180009041
0x18000902e  mov     dword ptr [rsp+260h+Args], 0FFFFh
0x180009036  mov     r8d, 154h
0x18000903c  jmp     loc_180009217
0x180009041  mov     rdx, cs:g_hDMHost
0x180009048  lea     rax, [rsp+260h+var_1F0]
0x18000904d  mov     [rsp+260h+var_220], r13b
0x180009052  lea     rcx, [rsp+260h+var_200]
0x180009057  mov     [rsp+260h+var_228], rax
0x18000905c  xor     r9d, r9d
0x18000905f  mov     [rsp+260h+var_230], rdi
0x180009064  xor     r8d, r8d
0x180009067  mov     [rsp+260h+var_238], r13
0x18000906c  mov     qword ptr [rsp+260h+Args], r13
0x180009071  mov     [rsp+260h+var_200], r13
0x180009076  call    cs:__imp_NtAlpcAcceptConnectPort
0x18000907c  test    eax, eax
0x18000907e  jns     loc_180009250
0x180009084  mov     ecx, ebx; Status
0x180009086  call    cs:__imp_RtlNtStatusToDosError
0x18000908c  test    eax, eax
0x18000908e  jle     short loc_180009097
0x180009090  movzx   eax, ax
0x180009093  or      eax, esi
0x180009095  test    eax, eax
0x180009097  jns     loc_180009250
0x18000909d  mov     r8d, 106h
0x1800090a3  jmp     loc_180009210
0x1800090a8  cmp     [rsp+260h+var_210], 0F8h
0x1800090b1  jnb     short loc_1800090C6
0x1800090b3  mov     dword ptr [rsp+260h+Args], 4005h
0x1800090bb  mov     r8d, 122h
0x1800090c1  jmp     loc_180009217
0x1800090c6  cmp     dword ptr [rdi+2Ch], 1Ch
0x1800090ca  jnz     short loc_1800090DA
0x1800090cc  mov     rcx, r14; hEvent
0x1800090cf  call    cs:__imp_SetEvent
0x1800090d5  jmp     loc_180009250
0x1800090da  cmp     dword ptr [rdi+2Ch], 5
0x1800090de  jz      short loc_1800090F3
0x1800090e0  cmp     dword ptr [rdi+2Ch], 12h
0x1800090e4  mov     ebx, r13d
0x1800090e7  jnz     short loc_180009132
0x1800090e9  mov     rcx, rdi
0x1800090ec  call    WdipCancelInstance
0x1800090f1  jmp     short loc_180009102
0x1800090f3  mov     rcx, cs:g_hDMHost
0x1800090fa  mov     rdx, rdi
0x1800090fd  call    WdipLoadSession
0x180009102  mov     ebx, eax
0x180009104  test    eax, eax
0x180009106  jns     short loc_180009132
0x180009108  movzx   eax, bx
0x18000910b  lea     r9, aErrorD_0; "Error = %d"
0x180009112  mov     r8d, 134h; int
0x180009118  mov     dword ptr [rsp+260h+Args], eax; Args
0x18000911c  lea     rdx, aWdiphostlisten; "WdipHostListener"
0x180009123  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000912a  call    WdipTraceError
0x18000912f  mov     ebx, r13d
0x180009132  mov     r14d, 2000h
0x180009138  test    [rdi+4], r14w
0x18000913d  jz      loc_180009250
0x180009143  mov     rcx, cs:g_hDMHost
0x18000914a  lea     rax, [rsp+260h+var_210]
0x18000914f  mov     [rsp+260h+var_228], r13
0x180009154  lea     r9, [rsp+260h+var_1F0]
0x180009159  mov     [rsp+260h+var_230], r13
0x18000915e  mov     r8, rdi
0x180009161  mov     [rsp+260h+var_238], rax
0x180009166  mov     edx, 10000h
0x18000916b  mov     qword ptr [rsp+260h+Args], r13
0x180009170  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180009176  test    eax, eax
0x180009178  jns     loc_180009250
0x18000917e  mov     ecx, ebx; Status
0x180009180  call    cs:__imp_RtlNtStatusToDosError
0x180009186  test    eax, eax
0x180009188  jle     short loc_180009191
0x18000918a  movzx   eax, ax
0x18000918d  or      eax, esi
0x18000918f  test    eax, eax
0x180009191  jns     loc_180009250
0x180009197  movzx   eax, ax
0x18000919a  lea     r9, aErrorD_0; "Error = %d"
0x1800091a1  mov     r8d, 145h; int
0x1800091a7  mov     dword ptr [rsp+260h+Args], eax; Args
0x1800091ab  lea     rdx, aWdiphostlisten; "WdipHostListener"
0x1800091b2  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800091b9  call    WdipTraceError
0x1800091be  jmp     short loc_180009237
0x1800091c0  mov     rcx, cs:g_hDMHost
0x1800091c7  lea     rax, [rsp+260h+var_210]
0x1800091cc  mov     [rsp+260h+var_228], r13
0x1800091d1  xor     r9d, r9d
0x1800091d4  mov     [rsp+260h+var_230], r13
0x1800091d9  mov     r8, rdi
0x1800091dc  mov     [rsp+260h+var_238], rax
0x1800091e1  mov     edx, 10000h
0x1800091e6  mov     qword ptr [rsp+260h+Args], r13
0x1800091eb  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800091f1  test    eax, eax
0x1800091f3  jns     short loc_180009250
0x1800091f5  mov     ecx, ebx; Status
0x1800091f7  call    cs:__imp_RtlNtStatusToDosError
0x1800091fd  test    eax, eax
0x1800091ff  jle     short loc_180009208
0x180009201  movzx   eax, ax
0x180009204  or      eax, esi
0x180009206  test    eax, eax
0x180009208  jns     short loc_180009250
0x18000920a  mov     r8d, 119h; int
0x180009210  movzx   eax, ax
0x180009213  mov     dword ptr [rsp+260h+Args], eax; Args
0x180009217  lea     r9, aErrorD_0; "Error = %d"
0x18000921e  lea     rdx, aWdiphostlisten; "WdipHostListener"
0x180009225  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000922c  call    WdipTraceError
0x180009231  mov     r14d, 2000h
0x180009237  test    [rdi+4], r14w
0x18000923c  jz      short loc_180009250
0x18000923e  mov     rcx, cs:g_hDMHost
0x180009245  mov     r8, r12
0x180009248  xor     edx, edx
0x18000924a  call    cs:__imp_NtAlpcCancelMessage
0x180009250  mov     rcx, r15
0x180009253  call    WdipFree
0x180009258  mov     rcx, [rbp+160h+var_50]
0x18000925f  xor     rcx, rsp; StackCookie
0x180009262  call    __security_check_cookie
0x180009267  add     rsp, 228h
0x18000926e  pop     r15
0x180009270  pop     r14
0x180009272  pop     r13
0x180009274  pop     r12
0x180009276  pop     rdi
0x180009277  pop     rsi
0x180009278  pop     rbx
0x180009279  pop     rbp
0x18000927a  retn
```
