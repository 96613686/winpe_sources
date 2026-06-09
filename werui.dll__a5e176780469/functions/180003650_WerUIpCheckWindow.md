# WerUIpCheckWindow

- ea: `0x180003650`
- end: `0x180003803`
- name: `WerUIpCheckWindow`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180003650`
- `0x180016a0c`
- `0x180016c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003696`
- `KERNEL32!GetLastError` at `0x180003696`
- `KERNEL32!CompareStringOrdinal` at `0x18000371b`
- `KERNEL32!CompareStringOrdinal` at `0x18000371b`
- `USER32!CheckWindowThreadDesktop` at `0x1800037a7`
- `USER32!CheckWindowThreadDesktop` at `0x1800037a7`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x18000376b`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x18000376b`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameW` at `0x18000368c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassNameW` at `0x18000368c`

## pseudocode

```c
__int64 __fastcall WerUIpCheckWindow(__int64 a1)
{
  HWND v2; // rcx
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  WCHAR ClassName[12]; // [rsp+30h] [rbp-28h] BYREF

  v2 = *(HWND *)(a1 + 1432);
  if ( !v2 )
    goto LABEL_15;
  if ( GetClassNameW(v2, ClassName, 10) )
  {
    v5 = -1;
    do
      ++v5;
    while ( ClassName[v5] );
    if ( v5 == 5 && CompareStringOrdinal(ClassName, -1, L"GHOST", -1, 1) == 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v4 = 1;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v4;
      v7 = 11;
      goto LABEL_24;
    }
LABEL_15:
    v4 = 0;
    if ( !*(_DWORD *)(a1 + 1716) )
      return v4;
    if ( IsHungAppWindow(*(HWND *)(a1 + 1432)) )
    {
      if ( (unsigned int)CheckWindowThreadDesktop(*(_QWORD *)(a1 + 1432), *(unsigned int *)(a1 + 1716)) )
        return v4;
      v4 = -2147024891;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v7 = 13;
    }
    else
    {
      v4 = -2147024891;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v7 = 12;
    }
LABEL_24:
    WPP_SF_(v6[2], v7, WPP_5b420245d0b9367d9d154d5453088648_Traceguids);
    return v4;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5b420245d0b9367d9d154d5453088648_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180003650  mov     [rsp+arg_8], rbx
0x180003655  mov     [rsp+arg_10], rsi
0x18000365a  push    rdi
0x18000365b  sub     rsp, 50h
0x18000365f  mov     rax, cs:__security_cookie
0x180003666  xor     rax, rsp
0x180003669  mov     [rsp+58h+var_10], rax
0x18000366e  mov     rdi, rcx
0x180003671  xor     esi, esi
0x180003673  mov     rcx, [rcx+598h]; hWnd
0x18000367a  test    rcx, rcx
0x18000367d  jz      loc_180003756
0x180003683  lea     r8d, [rsi+0Ah]; nMaxCount
0x180003687  lea     rdx, [rsp+58h+ClassName]; lpClassName
0x18000368c  call    cs:__imp_GetClassNameW
0x180003692  test    eax, eax
0x180003694  jnz     short loc_1800036E9
0x180003696  call    cs:__imp_GetLastError
0x18000369c  mov     ebx, eax
0x18000369e  test    eax, eax
0x1800036a0  jle     short loc_1800036AB
0x1800036a2  movzx   ebx, ax
0x1800036a5  or      ebx, 80070000h
0x1800036ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036b2  lea     rax, WPP_GLOBAL_Control
0x1800036b9  cmp     rcx, rax
0x1800036bc  jz      loc_1800037E4
0x1800036c2  test    byte ptr [rcx+1Ch], 1
0x1800036c6  jz      loc_1800037E4
0x1800036cc  mov     rcx, [rcx+10h]
0x1800036d0  lea     r8, WPP_5b420245d0b9367d9d154d5453088648_Traceguids
0x1800036d7  mov     edx, 0Ah
0x1800036dc  mov     r9d, ebx
0x1800036df  call    WPP_SF_d
0x1800036e4  jmp     loc_1800037E4
0x1800036e9  or      rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x1800036ed  lea     rcx, [rsp+58h+ClassName]
0x1800036f2  mov     rax, rdx
0x1800036f5  inc     rax
0x1800036f8  cmp     [rcx+rax*2], si
0x1800036fc  jnz     short loc_1800036F5
0x1800036fe  cmp     rax, 5
0x180003702  jnz     short loc_180003756
0x180003704  mov     r9d, edx; cchCount2
0x180003707  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18000370f  lea     r8, String2; "GHOST"
0x180003716  lea     rcx, [rsp+58h+ClassName]; lpString1
0x18000371b  call    cs:__imp_CompareStringOrdinal
0x180003721  cmp     eax, 2
0x180003724  jnz     short loc_180003756
0x180003726  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000372b  mov     ebx, 1
0x180003730  mov     rcx, cs:WPP_GLOBAL_Control
0x180003737  lea     rax, WPP_GLOBAL_Control
0x18000373e  cmp     rcx, rax
0x180003741  jz      loc_1800037E4
0x180003747  test    byte ptr [rcx+1Ch], 4
0x18000374b  jz      loc_1800037E4
0x180003751  lea     edx, [rbx+0Ah]
0x180003754  jmp     short loc_1800037D4
0x180003756  mov     ebx, esi
0x180003758  cmp     [rdi+6B4h], esi
0x18000375e  jz      loc_1800037E4
0x180003764  mov     rcx, [rdi+598h]; hwnd
0x18000376b  call    cs:__imp_IsHungAppWindow
0x180003771  test    eax, eax
0x180003773  jnz     short loc_18000379A
0x180003775  mov     ebx, 80070005h
0x18000377a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003781  lea     rax, WPP_GLOBAL_Control
0x180003788  cmp     rcx, rax
0x18000378b  jz      short loc_1800037E4
0x18000378d  test    byte ptr [rcx+1Ch], 1
0x180003791  jz      short loc_1800037E4
0x180003793  mov     edx, 0Ch
0x180003798  jmp     short loc_1800037D4
0x18000379a  mov     edx, [rdi+6B4h]
0x1800037a0  mov     rcx, [rdi+598h]
0x1800037a7  call    cs:__imp_CheckWindowThreadDesktop
0x1800037ad  test    eax, eax
0x1800037af  jnz     short loc_1800037E4
0x1800037b1  mov     ebx, 80070005h
0x1800037b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037bd  lea     rax, WPP_GLOBAL_Control
0x1800037c4  cmp     rcx, rax
0x1800037c7  jz      short loc_1800037E4
0x1800037c9  test    byte ptr [rcx+1Ch], 1
0x1800037cd  jz      short loc_1800037E4
0x1800037cf  mov     edx, 0Dh
0x1800037d4  mov     rcx, [rcx+10h]
0x1800037d8  lea     r8, WPP_5b420245d0b9367d9d154d5453088648_Traceguids
0x1800037df  call    WPP_SF_
0x1800037e4  mov     eax, ebx
0x1800037e6  mov     rcx, [rsp+58h+var_10]
0x1800037eb  xor     rcx, rsp; StackCookie
0x1800037ee  call    __security_check_cookie
0x1800037f3  mov     rbx, [rsp+58h+arg_8]
0x1800037f8  mov     rsi, [rsp+58h+arg_10]
0x1800037fd  add     rsp, 50h
0x180003801  pop     rdi
0x180003802  retn
```
