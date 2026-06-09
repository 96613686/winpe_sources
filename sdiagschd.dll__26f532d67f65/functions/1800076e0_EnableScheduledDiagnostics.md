# EnableScheduledDiagnostics

- ea: `0x1800076e0`
- end: `0x180007804`
- name: `EnableScheduledDiagnostics`
- size: `292`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006f20`
- `0x1800076e0`
- `0x18000b13c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800077b9`
- `ADVAPI32!RegCloseKey` at `0x1800077b9`
- `ADVAPI32!RegSetValueExW` at `0x180007779`
- `ADVAPI32!RegSetValueExW` at `0x180007779`
- `ADVAPI32!RegOpenKeyExW` at `0x18000771c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000771c`

## string_xrefs

- `0x1800076ee`: `Software\Microsoft\Windows\ScheduledDiagnostics`
- `0x1800077e8`: `EnableScheduledDiagnostics`

## pseudocode

```c
__int64 __fastcall EnableScheduledDiagnostics(int a1)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  int v3; // r8d
  LSTATUS v4; // eax
  int v5; // r9d
  int v6; // r8d
  int v7; // eax
  BOOL Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1 == 1;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\ScheduledDiagnostics", 0, 2u, &hKey);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 < 0 )
  {
    v3 = 225;
LABEL_11:
    SdpDebugTrace(1u, L"SchdpSetAdminSetting", v3, v2);
    goto LABEL_12;
  }
  if ( !hKey )
  {
    v2 = -2147467261;
    v3 = 226;
    goto LABEL_11;
  }
  v4 = RegSetValueExW(hKey, L"EnabledExecution", 0, 4u, (const BYTE *)&Data, 4u);
  v2 = v4;
  if ( v4 > 0 )
    v2 = (unsigned __int16)v4 | 0x80070000;
  if ( v2 < 0 )
  {
    v3 = 234;
    goto LABEL_11;
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 < 0 )
  {
    v5 = v2;
    v6 = 526;
LABEL_18:
    SdpDebugTrace(1u, L"EnableScheduledDiagnostics", v6, v5);
    return (unsigned int)v2;
  }
  v7 = SchdpExecuteTask();
  v2 = v7;
  if ( v7 < 0 )
  {
    v5 = v7;
    v6 = 529;
    goto LABEL_18;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800076e0  mov     r11, rsp
0x1800076e3  mov     [r11+18h], rbx
0x1800076e7  push    rdi
0x1800076e8  sub     rsp, 30h
0x1800076ec  xor     eax, eax
0x1800076ee  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Scheduled"...
0x1800076f5  lea     edi, [rax+1]
0x1800076f8  cmp     ecx, edi
0x1800076fa  lea     r9d, [rdi+1]; samDesired
0x1800076fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007705  setz    al
0x180007708  and     qword ptr [r11+10h], 0
0x18000770d  mov     [rsp+38h+Data], eax
0x180007711  xor     r8d, r8d; ulOptions
0x180007714  lea     rax, [r11+10h]
0x180007718  mov     [r11-18h], rax
0x18000771c  call    cs:__imp_RegOpenKeyExW
0x180007723  nop     dword ptr [rax+rax+00h]
0x180007728  mov     ebx, eax
0x18000772a  test    eax, eax
0x18000772c  jle     short loc_180007737
0x18000772e  movzx   ebx, ax
0x180007731  or      ebx, 80070000h
0x180007737  test    ebx, ebx
0x180007739  jns     short loc_180007743
0x18000773b  mov     r8d, 0E1h
0x180007741  jmp     short loc_18000779E
0x180007743  mov     rcx, [rsp+38h+hKey]; hKey
0x180007748  test    rcx, rcx
0x18000774b  jnz     short loc_18000775A
0x18000774d  mov     ebx, 80004003h
0x180007752  mov     r8d, 0E2h
0x180007758  jmp     short loc_18000779E
0x18000775a  mov     r9d, 4; dwType
0x180007760  lea     rax, [rsp+38h+Data]
0x180007765  mov     [rsp+38h+cbData], r9d; cbData
0x18000776a  lea     rdx, ValueName; "EnabledExecution"
0x180007771  xor     r8d, r8d; Reserved
0x180007774  mov     [rsp+38h+lpData], rax; lpData
0x180007779  call    cs:__imp_RegSetValueExW
0x180007780  nop     dword ptr [rax+rax+00h]
0x180007785  mov     ebx, eax
0x180007787  test    eax, eax
0x180007789  jle     short loc_180007794
0x18000778b  movzx   ebx, ax
0x18000778e  or      ebx, 80070000h
0x180007794  test    ebx, ebx
0x180007796  jns     short loc_1800077AF
0x180007798  mov     r8d, 0EAh; int
0x18000779e  mov     r9d, ebx; int
0x1800077a1  lea     rdx, aSchdpsetadmins; "SchdpSetAdminSetting"
0x1800077a8  mov     ecx, edi; Level
0x1800077aa  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800077af  mov     rcx, [rsp+38h+hKey]; hKey
0x1800077b4  test    rcx, rcx
0x1800077b7  jz      short loc_1800077C5
0x1800077b9  call    cs:__imp_RegCloseKey
0x1800077c0  nop     dword ptr [rax+rax+00h]
0x1800077c5  test    ebx, ebx
0x1800077c7  jns     short loc_1800077D4
0x1800077c9  mov     r9d, ebx
0x1800077cc  mov     r8d, 20Eh
0x1800077d2  jmp     short loc_1800077E8
0x1800077d4  call    ?SchdpExecuteTask@@YAJXZ; SchdpExecuteTask(void)
0x1800077d9  mov     ebx, eax
0x1800077db  test    eax, eax
0x1800077dd  jns     short loc_1800077F6
0x1800077df  mov     r9d, eax; int
0x1800077e2  mov     r8d, 211h; int
0x1800077e8  lea     rdx, aEnableschedule_0; "EnableScheduledDiagnostics"
0x1800077ef  mov     ecx, edi; Level
0x1800077f1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800077f6  mov     eax, ebx
0x1800077f8  mov     rbx, [rsp+38h+arg_10]
0x1800077fd  add     rsp, 30h
0x180007801  pop     rdi
0x180007802  retn
```
