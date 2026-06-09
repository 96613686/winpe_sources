# CWinSATTaskMangerTask::UpdateErrorCountRegKey(ulong)

- ea: `0x18002177c`
- end: `0x1800218b8`
- name: `?UpdateErrorCountRegKey@CWinSATTaskMangerTask@@AEAA_NK@Z`
- size: `316`
- prototype: `bool(CWinSATTaskMangerTask *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180020dcc`
- `0x1800211f8`

## callees

- `0x18000e234`
- `0x1800173a4`
- `0x18001aaf4`
- `0x18001c414`
- `0x18002177c`
- `0x18002d328`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180021864`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180021864`

## string_xrefs

- `0x1800217e0`: `cannot open the winast API registry key`
- `0x1800217ef`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002184f`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x18002187d`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021840`: `cannot write the task error count to the registry`
- `0x18002186e`: `cannot flush the task error count to the registry`
- `0x18002180f`: `TaskErrorCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::UpdateErrorCountRegKey(CWinSATTaskMangerTask *this, unsigned int a2)
{
  int v4; // eax
  char v5; // bl
  HKEY hKey[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD Buffer[32]; // [rsp+40h] [rbp-C0h] BYREF
  int v8; // [rsp+140h] [rbp+40h]
  char v9; // [rsp+144h] [rbp+44h]
  __int64 v10; // [rsp+148h] [rbp+48h]

  memset(hKey, 0, 24);
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)hKey,
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
                       0xF003Fu) )
  {
    Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)hKey[0]);
    ATL::CRegKey::Close(hKey);
    return 0;
  }
  else
  {
    v4 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"TaskErrorCount", a2);
    if ( v4 )
    {
      v8 = v4;
      v9 = 1;
      v10 = 0;
      mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
      Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)hKey[0]);
      v5 = 0;
    }
    else
    {
      if ( RegFlushKey(hKey[0]) )
        Record_Win32Error_w("base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp", (char)hKey[0]);
      v5 = 1;
    }
    ATL::CRegKey::Close(hKey);
    return v5;
  }
}

```

## disassembly

```asm
0x18002177c  mov     [rsp-8+arg_0], rbx
0x180021781  mov     [rsp-8+arg_10], rdi
0x180021786  push    rbp
0x180021787  lea     rbp, [rsp-60h]
0x18002178c  sub     rsp, 160h
0x180021793  mov     rax, cs:__security_cookie
0x18002179a  xor     rax, rsp
0x18002179d  mov     [rbp+60h+var_10], rax
0x1800217a1  mov     ebx, edx
0x1800217a3  mov     [rsp+160h+hKey], 0; char
0x1800217ac  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800217b3  mov     [rsp+160h+var_138], 0
0x1800217bc  mov     r9d, 0F003Fh; unsigned int
0x1800217c2  mov     [rsp+160h+var_130], 0
0x1800217cb  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800217d2  lea     rcx, [rsp+160h+hKey]; this
0x1800217d7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800217dc  test    eax, eax
0x1800217de  jz      short loc_18002180C
0x1800217e0  lea     r9, aCannotOpenTheW; "cannot open the winast API registry key"
0x1800217e7  mov     r8d, eax
0x1800217ea  mov     edx, 2Fh ; '/'
0x1800217ef  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x1800217f6  call    Record_Win32Error_w
0x1800217fb  lea     rcx, [rsp+160h+hKey]; this
0x180021800  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021805  xor     al, al
0x180021807  jmp     loc_180021897
0x18002180c  mov     r8d, ebx; unsigned int
0x18002180f  lea     rdx, aTaskerrorcount; "TaskErrorCount"
0x180021816  lea     rcx, [rsp+160h+hKey]; this
0x18002181b  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180021820  mov     edi, eax
0x180021822  test    eax, eax
0x180021824  jz      short loc_18002185F
0x180021826  mov     bl, 1
0x180021828  mov     [rbp+60h+var_20], eax
0x18002182b  lea     rcx, [rsp+160h+Buffer]; lpBuffer
0x180021830  mov     [rbp+60h+var_1C], bl
0x180021833  mov     [rbp+60h+var_18], 0
0x18002183b  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x180021840  lea     r9, aCannotWriteThe; "cannot write the task error count to th"...
0x180021847  mov     r8d, edi
0x18002184a  mov     edx, 35h ; '5'
0x18002184f  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021856  call    Record_Win32Error_w
0x18002185b  xor     ebx, ebx
0x18002185d  jmp     short loc_18002188B
0x18002185f  mov     rcx, [rsp+160h+hKey]; hKey
0x180021864  call    cs:__imp_RegFlushKey
0x18002186a  test    eax, eax
0x18002186c  jz      short loc_180021889
0x18002186e  lea     r9, aCannotFlushThe; "cannot flush the task error count to th"...
0x180021875  mov     r8d, eax
0x180021878  mov     edx, 3Ah ; ':'
0x18002187d  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021884  call    Record_Win32Error_w
0x180021889  mov     bl, 1
0x18002188b  lea     rcx, [rsp+160h+hKey]; this
0x180021890  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180021895  mov     al, bl
0x180021897  mov     rcx, [rbp+60h+var_10]
0x18002189b  xor     rcx, rsp; StackCookie
0x18002189e  call    __security_check_cookie
0x1800218a3  lea     r11, [rsp+160h+var_s0]
0x1800218ab  mov     rbx, [r11+10h]
0x1800218af  mov     rdi, [r11+20h]
0x1800218b3  mov     rsp, r11
0x1800218b6  pop     rbp
0x1800218b7  retn
```
