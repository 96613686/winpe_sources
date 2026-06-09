# CWnpConnManager::IsPrefferedCellularPolicyEnabled(void)

- ea: `0x18006558c`
- end: `0x1800656bd`
- name: `?IsPrefferedCellularPolicyEnabled@CWnpConnManager@@AEAA_NXZ`
- size: `305`
- prototype: `bool __fastcall(CWnpConnManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800665f4`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x1800154f4`
- `0x18002f808`
- `0x18006558c`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006563c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006563c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180065603`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180065603`

## pseudocode

```c
bool __fastcall CWnpConnManager::IsPrefferedCellularPolicyEnabled(CWnpConnManager *this)
{
  bool IsMobileCore; // bl
  int v2; // eax
  __int64 v3; // r9
  PVOID *v4; // rcx
  CWnpConnManager *v6; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v6 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
  }
  hKey = 0;
  IsMobileCore = WpnIsMobileCore();
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( !v2 )
  {
    LODWORD(v6) = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"PreferCellularConnectivity", (unsigned int *)&v6) >= 0 )
      IsMobileCore = (_DWORD)v6 != 0;
    RegCloseKey(hKey);
LABEL_15:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return IsMobileCore;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
      (unsigned int)v2);
    goto LABEL_15;
  }
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v3) = IsMobileCore;
    WPP_SF_c(v4[2], 132, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v3);
  }
  return IsMobileCore;
}

```

## disassembly

```asm
0x18006558c  mov     [rsp+arg_10], rbx
0x180065591  mov     [rsp+arg_0], rcx
0x180065596  push    rsi
0x180065597  sub     rsp, 30h
0x18006559b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655a2  lea     rsi, WPP_GLOBAL_Control
0x1800655a9  cmp     rcx, rsi
0x1800655ac  jz      short loc_1800655CF
0x1800655ae  test    byte ptr [rcx+1Ch], 4
0x1800655b2  jz      short loc_1800655CF
0x1800655b4  cmp     byte ptr [rcx+19h], 6
0x1800655b8  jb      short loc_1800655CF
0x1800655ba  mov     rcx, [rcx+10h]
0x1800655be  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800655c5  mov     edx, 82h
0x1800655ca  call    WPP_SF_
0x1800655cf  mov     [rsp+38h+hKey], 0
0x1800655d8  call    ?WpnIsMobileCore@@YAHXZ; WpnIsMobileCore(void)
0x1800655dd  test    eax, eax
0x1800655df  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800655e6  lea     rax, [rsp+38h+hKey]
0x1800655eb  mov     r9d, 1; samDesired
0x1800655f1  setnz   bl
0x1800655f4  mov     [rsp+38h+phkResult], rax; phkResult
0x1800655f9  xor     r8d, r8d; ulOptions
0x1800655fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065603  call    cs:__imp_RegOpenKeyExA
0x180065609  test    eax, eax
0x18006560b  jnz     short loc_180065644
0x18006560d  mov     rcx, [rsp+38h+hKey]; hKey
0x180065612  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x180065617  lea     rdx, aPrefercellular; "PreferCellularConnectivity"
0x18006561e  mov     dword ptr [rsp+38h+arg_0], 1
0x180065626  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18006562b  test    eax, eax
0x18006562d  js      short loc_180065637
0x18006562f  cmp     dword ptr [rsp+38h+arg_0], 0
0x180065634  setnz   bl
0x180065637  mov     rcx, [rsp+38h+hKey]; hKey
0x18006563c  call    cs:__imp_RegCloseKey
0x180065642  jmp     short loc_180065680
0x180065644  mov     rcx, cs:WPP_GLOBAL_Control
0x18006564b  cmp     rcx, rsi
0x18006564e  jz      short loc_1800656B0
0x180065650  test    byte ptr [rcx+1Ch], 4
0x180065654  jz      short loc_180065687
0x180065656  cmp     byte ptr [rcx+19h], 2
0x18006565a  jb      short loc_180065687
0x18006565c  test    eax, eax
0x18006565e  jle     short loc_180065668
0x180065660  movzx   eax, ax
0x180065663  or      eax, 80070000h
0x180065668  mov     rcx, [rcx+10h]
0x18006566c  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180065673  mov     edx, 83h
0x180065678  mov     r9d, eax
0x18006567b  call    WPP_SF_d
0x180065680  mov     rcx, cs:WPP_GLOBAL_Control
0x180065687  cmp     rcx, rsi
0x18006568a  jz      short loc_1800656B0
0x18006568c  test    byte ptr [rcx+1Ch], 4
0x180065690  jz      short loc_1800656B0
0x180065692  cmp     byte ptr [rcx+19h], 6
0x180065696  jb      short loc_1800656B0
0x180065698  mov     rcx, [rcx+10h]
0x18006569c  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800656a3  mov     edx, 84h
0x1800656a8  mov     r9b, bl
0x1800656ab  call    WPP_SF_c
0x1800656b0  mov     al, bl
0x1800656b2  mov     rbx, [rsp+38h+arg_10]
0x1800656b7  add     rsp, 30h
0x1800656bb  pop     rsi
0x1800656bc  retn
```
