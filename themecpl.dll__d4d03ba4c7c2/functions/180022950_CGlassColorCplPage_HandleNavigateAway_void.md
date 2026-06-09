# CGlassColorCplPage::HandleNavigateAway(void)

- ea: `0x180022950`
- end: `0x180022b8c`
- name: `?HandleNavigateAway@CGlassColorCplPage@@UEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(CGlassColorCplPage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002280`
- `0x18000a9d4`
- `0x1800225d0`
- `0x180022950`
- `0x1800237e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180022a9a`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180022a9a`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800229d7`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180022a23`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800229d7`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180022a23`
- `ntdll!WinSqmSetDWORD` at `0x180022ab1`
- `ntdll!WinSqmSetDWORD` at `0x180022ac9`
- `ntdll!WinSqmSetDWORD` at `0x180022ab1`
- `ntdll!WinSqmSetDWORD` at `0x180022ac9`
- `USER32!SendNotifyMessageW` at `0x1800229bd`
- `USER32!SendNotifyMessageW` at `0x1800229bd`

## pseudocode

```c
__int64 __fastcall CGlassColorCplPage::HandleNavigateAway(CGlassColorCplPage *this, __int64 a2, __int64 a3, bool a4)
{
  signed int DwmColorizationColor; // ebx
  int v6; // eax
  CGlassColorCplPage *v7; // rcx
  bool v8; // r9
  __int64 v9; // rcx
  int v11; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+48h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  unsigned int *v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h]
  int *v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  unsigned int *v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  DwmColorizationColor = 0;
  if ( *((_BYTE *)this + 81) )
  {
    if ( *((_BYTE *)this + 88) )
    {
      v13 = *((_BYTE *)this + 96) != 0;
      v6 = _RegSetKeyValue(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"AutoColorization", 4u, (BYTE *)&v13, 4u);
      DwmColorizationColor = v6;
      if ( v6 > 0 )
        DwmColorizationColor = (unsigned __int16)v6 | 0x80070000;
      if ( DwmColorizationColor >= 0 )
      {
        if ( *((_BYTE *)this + 96) )
        {
          v9 = *((_QWORD *)this + 16);
          v11 = 0;
          DwmColorizationColor = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 168LL))(v9, &v11);
          if ( DwmColorizationColor < 0 )
            goto LABEL_19;
          *((_DWORD *)this + 23) = v11;
        }
        DwmColorizationColor = CGlassColorCplPage::_SetDwmColorizationColor(
                                 v7,
                                 (CGlassColorCplPage *)((char *)this + 92),
                                 0,
                                 v8);
        if ( DwmColorizationColor >= 0 )
          *((_BYTE *)this + 81) = 0;
      }
    }
    else if ( *((_BYTE *)this + 104)
           || (DwmColorizationColor = CGlassColorCplPage::_SetDwmColorizationColor(
                                        this,
                                        (CGlassColorCplPage *)((char *)this + 100),
                                        0,
                                        a4),
               DwmColorizationColor >= 0) )
    {
      *((_BYTE *)this + 81) = 0;
      SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"WindowsThemeElement");
      if ( EventEnabled(Microsoft_Windows_Shell_Core_Provider_Context, &Glass_Colorization) )
      {
        v12 = 0;
        v11 = 0;
        DwmColorizationColor = GetDwmColorizationColor(&v12, &v11);
        if ( DwmColorizationColor >= 0 )
        {
          v13 = v12;
          v12 = 1324;
          if ( EventEnabled(ThemeCPL_Provider_Context, &Glass_Colorization) )
          {
            v14 = 5;
            UserData.Ptr = (ULONGLONG)&g_SHSqmGlobalSession;
            v18 = &v14;
            v16 = &v12;
            *(_QWORD *)&UserData.Size = 16;
            v20 = &v13;
            v17 = 4;
            v19 = 4;
            v21 = 4;
            EventWrite(ThemeCPL_Provider_Context, &Glass_Colorization, 4u, &UserData);
          }
          WinSqmSetDWORD(0, 11272, (unsigned int)v11);
        }
      }
      WinSqmSetDWORD(0, 7471, *((unsigned __int8 *)this + 104));
    }
  }
LABEL_19:
  *((_BYTE *)this + 88) = 1;
  return (unsigned int)DwmColorizationColor;
}

```

## disassembly

```asm
0x180022950  push    rbp
0x180022952  push    rbx
0x180022953  push    rsi
0x180022954  push    rdi
0x180022955  lea     rbp, [rsp-3Fh]
0x18002295a  sub     rsp, 0A8h
0x180022961  mov     rax, cs:__security_cookie
0x180022968  xor     rax, rsp
0x18002296b  mov     [rbp+57h+var_30], rax
0x18002296f  xor     esi, esi
0x180022971  mov     rdi, rcx
0x180022974  mov     ebx, esi
0x180022976  cmp     [rcx+51h], sil
0x18002297a  jz      loc_180022B6D
0x180022980  cmp     [rcx+58h], sil
0x180022984  jnz     loc_180022ADA
0x18002298a  cmp     [rcx+68h], sil
0x18002298e  jnz     short loc_1800229A6
0x180022990  lea     rdx, [rcx+64h]; struct CColorizationColor *
0x180022994  xor     r8d, r8d; int
0x180022997  call    ?_SetDwmColorizationColor@CGlassColorCplPage@@AEAAJAEBVCColorizationColor@@H_N@Z; CGlassColorCplPage::_SetDwmColorizationColor(CColorizationColor const &,int,bool)
0x18002299c  mov     ebx, eax
0x18002299e  test    eax, eax
0x1800229a0  js      loc_180022B6D
0x1800229a6  xor     r8d, r8d; wParam
0x1800229a9  mov     [rdi+51h], sil
0x1800229ad  lea     r9, lParam; "WindowsThemeElement"
0x1800229b4  mov     ecx, 0FFFFh; hWnd
0x1800229b9  lea     edx, [r8+1Ah]; Msg
0x1800229bd  call    cs:__imp_SendNotifyMessageW
0x1800229c4  nop     dword ptr [rax+rax+00h]
0x1800229c9  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x1800229d0  lea     rdx, Glass_Colorization; EventDescriptor
0x1800229d7  call    cs:__imp_EventEnabled
0x1800229de  nop     dword ptr [rax+rax+00h]
0x1800229e3  test    al, al
0x1800229e5  jz      loc_180022ABD
0x1800229eb  lea     rdx, [rbp+57h+var_90]; int *
0x1800229ef  mov     [rbp+57h+var_88], esi
0x1800229f2  lea     rcx, [rbp+57h+var_88]; unsigned int *
0x1800229f6  mov     [rbp+57h+var_90], esi
0x1800229f9  call    ?GetDwmColorizationColor@@YAJPEAKPEAH@Z; GetDwmColorizationColor(ulong *,int *)
0x1800229fe  mov     ebx, eax
0x180022a00  test    eax, eax
0x180022a02  js      loc_180022ABD
0x180022a08  mov     eax, [rbp+57h+var_88]
0x180022a0b  lea     rdx, Glass_Colorization; EventDescriptor
0x180022a12  mov     rcx, cs:ThemeCPL_Provider_Context; RegHandle
0x180022a19  mov     [rbp+57h+var_80], eax
0x180022a1c  mov     [rbp+57h+var_88], 52Ch
0x180022a23  call    cs:__imp_EventEnabled
0x180022a2a  nop     dword ptr [rax+rax+00h]
0x180022a2f  test    al, al
0x180022a31  jz      short loc_180022AA6
0x180022a33  xorps   xmm0, xmm0
0x180022a36  mov     [rbp+57h+var_78], 5
0x180022a3d  movups  [rbp+57h+var_58], xmm0
0x180022a41  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x180022a48  mov     [rbp+57h+UserData.Ptr], rax
0x180022a4c  lea     rcx, [rbp+57h+var_78]
0x180022a50  lea     rax, [rbp+57h+var_88]
0x180022a54  mov     qword ptr [rbp+57h+var_58+8], rcx
0x180022a58  movups  xmmword ptr [rbp+57h+UserData.Size], xmm0
0x180022a5c  mov     [rbp+57h+var_60], rax
0x180022a60  mov     eax, 4
0x180022a65  movups  [rbp+57h+var_48], xmm0
0x180022a69  lea     rcx, [rbp+57h+var_80]
0x180022a6d  mov     qword ptr [rbp+57h+UserData.Size], 10h
0x180022a75  mov     qword ptr [rbp+57h+var_48+8], rcx
0x180022a79  lea     r9, [rbp+57h+UserData]; UserData
0x180022a7d  mov     rcx, cs:ThemeCPL_Provider_Context; RegHandle
0x180022a84  lea     rdx, Glass_Colorization; EventDescriptor
0x180022a8b  mov     r8d, eax; UserDataCount
0x180022a8e  mov     qword ptr [rbp+57h+var_58], rax
0x180022a92  mov     qword ptr [rbp+57h+var_48], rax
0x180022a96  mov     [rbp+57h+var_38], rax
0x180022a9a  call    cs:__imp_EventWrite
0x180022aa1  nop     dword ptr [rax+rax+00h]
0x180022aa6  mov     r8d, [rbp+57h+var_90]
0x180022aaa  mov     edx, 2C08h
0x180022aaf  xor     ecx, ecx
0x180022ab1  call    cs:__imp_WinSqmSetDWORD
0x180022ab8  nop     dword ptr [rax+rax+00h]
0x180022abd  movzx   r8d, byte ptr [rdi+68h]
0x180022ac2  mov     edx, 1D2Fh
0x180022ac7  xor     ecx, ecx
0x180022ac9  call    cs:__imp_WinSqmSetDWORD
0x180022ad0  nop     dword ptr [rax+rax+00h]
0x180022ad5  jmp     loc_180022B6D
0x180022ada  cmp     [rcx+60h], sil
0x180022ade  lea     r8, aAutocolorizati; "AutoColorization"
0x180022ae5  mov     eax, esi
0x180022ae7  lea     rcx, [rbp+57h+var_80]
0x180022aeb  setnz   al
0x180022aee  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x180022af5  mov     [rbp+57h+var_80], eax
0x180022af8  mov     eax, 4
0x180022afd  mov     [rsp+0C0h+var_98], eax; unsigned int
0x180022b01  mov     r9d, eax; unsigned int
0x180022b04  mov     [rsp+0C0h+var_A0], rcx; void *
0x180022b09  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180022b10  call    ?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z; _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x180022b15  mov     ebx, eax
0x180022b17  test    eax, eax
0x180022b19  jle     short loc_180022B24
0x180022b1b  movzx   ebx, ax
0x180022b1e  or      ebx, 80070000h
0x180022b24  test    ebx, ebx
0x180022b26  js      short loc_180022B6D
0x180022b28  cmp     [rdi+60h], sil
0x180022b2c  jz      short loc_180022B57
0x180022b2e  mov     rcx, [rdi+80h]
0x180022b35  lea     rdx, [rbp+57h+var_90]
0x180022b39  mov     [rbp+57h+var_90], esi
0x180022b3c  mov     rax, [rcx]
0x180022b3f  mov     rax, [rax+0A8h]
0x180022b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b4b  mov     ebx, eax
0x180022b4d  test    eax, eax
0x180022b4f  js      short loc_180022B6D
0x180022b51  mov     eax, [rbp+57h+var_90]
0x180022b54  mov     [rdi+5Ch], eax
0x180022b57  lea     rdx, [rdi+5Ch]; struct CColorizationColor *
0x180022b5b  xor     r8d, r8d; int
0x180022b5e  call    ?_SetDwmColorizationColor@CGlassColorCplPage@@AEAAJAEBVCColorizationColor@@H_N@Z; CGlassColorCplPage::_SetDwmColorizationColor(CColorizationColor const &,int,bool)
0x180022b63  mov     ebx, eax
0x180022b65  test    eax, eax
0x180022b67  js      short loc_180022B6D
0x180022b69  mov     [rdi+51h], sil
0x180022b6d  mov     byte ptr [rdi+58h], 1
0x180022b71  mov     eax, ebx
0x180022b73  mov     rcx, [rbp+57h+var_30]
0x180022b77  xor     rcx, rsp; StackCookie
0x180022b7a  call    __security_check_cookie
0x180022b7f  add     rsp, 0A8h
0x180022b86  pop     rdi
0x180022b87  pop     rsi
0x180022b88  pop     rbx
0x180022b89  pop     rbp
0x180022b8a  retn
```
