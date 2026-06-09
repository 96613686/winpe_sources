# CheckTrustedServers(ushort *)

- ea: `0x180003178`
- end: `0x18000335e`
- name: `?CheckTrustedServers@@YAJPEAG@Z`
- size: `486`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800041a4`

## callees

- `0x180003178`
- `0x180003970`
- `0x1800053ac`
- `0x1800054b8`
- `0x18000aafc`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800031e2`
- `ole32!CoTaskMemAlloc` at `0x1800031e2`
- `ole32!CoTaskMemFree` at `0x180003339`
- `ole32!CoTaskMemFree` at `0x180003339`
- `ADVAPI32!RegQueryValueExW` at `0x18000324f`
- `ADVAPI32!RegQueryValueExW` at `0x18000324f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000320c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000320c`
- `ADVAPI32!RegCloseKey` at `0x180003349`
- `ADVAPI32!RegCloseKey` at `0x180003349`

## pseudocode

```c
__int64 __fastcall CheckTrustedServers(wchar_t *String2)
{
  unsigned int v2; // ebx
  BYTE *v3; // rdi
  LSTATUS v4; // eax
  bool v5; // cc
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  wchar_t *i; // rbx
  __int64 v9; // rax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0x2000;
  Type = 0;
  if ( !String2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, L"serverFQDN");
    }
    v2 = -2147024809;
    goto LABEL_34;
  }
  v3 = (BYTE *)CoTaskMemAlloc(0x2000u);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Terminal Server Client\\TrustedGateways",
         0,
         0x20019u,
         &hKey);
  v2 = v4;
  v5 = v4 <= 0;
  if ( v4 || (v4 = RegQueryValueExW(hKey, L"GatewayFQDN", 0, &Type, v3, &cbData), v2 = v4, v5 = v4 <= 0, v4) )
  {
    if ( !v5 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_32;
  }
  if ( Type == 7 )
  {
    if ( cbData >= 4 )
    {
      for ( i = (wchar_t *)v3; ; i += v9 )
      {
        if ( !*i )
        {
          if ( !i[1] )
          {
            v2 = -2147001873;
            goto LABEL_32;
          }
          do
            ++i;
          while ( !*i );
        }
        if ( (unsigned int)CUT::IsEqualDomainName(i, String2) )
          break;
        v9 = -1;
        do
          ++v9;
        while ( i[v9] );
      }
      v2 = 0;
      goto LABEL_32;
    }
    v2 = -2147001873;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 70;
      goto LABEL_16;
    }
  }
  else
  {
    v2 = -2147001873;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 69;
LABEL_16:
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
LABEL_32:
  if ( v3 )
    CoTaskMemFree(v3);
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180003178  mov     rax, rsp
0x18000317b  mov     [rax+20h], rbx
0x18000317f  push    rbp
0x180003180  push    rsi
0x180003181  push    rdi
0x180003182  sub     rsp, 30h
0x180003186  xor     ebp, ebp
0x180003188  mov     rsi, rcx
0x18000318b  mov     [rax+18h], rbp
0x18000318f  mov     ecx, 2000h; cb
0x180003194  mov     [rax+10h], ecx
0x180003197  mov     [rax+8], ebp
0x18000319a  test    rsi, rsi
0x18000319d  jnz     short loc_1800031E2
0x18000319f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031a6  lea     rax, WPP_GLOBAL_Control
0x1800031ad  cmp     rcx, rax
0x1800031b0  jz      short loc_1800031D8
0x1800031b2  test    byte ptr [rcx+1Ch], 8
0x1800031b6  jz      short loc_1800031D8
0x1800031b8  cmp     byte ptr [rcx+19h], 2
0x1800031bc  jb      short loc_1800031D8
0x1800031be  mov     rcx, [rcx+10h]
0x1800031c2  lea     edx, [rbp+44h]
0x1800031c5  lea     r9, aServerfqdn; "serverFQDN"
0x1800031cc  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800031d3  call    WPP_SF_S
0x1800031d8  mov     ebx, 80070057h
0x1800031dd  jmp     loc_18000333F
0x1800031e2  call    cs:__imp_CoTaskMemAlloc
0x1800031e8  mov     r9d, 20019h; samDesired
0x1800031ee  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Terminal Server Cl"...
0x1800031f5  mov     rdi, rax
0x1800031f8  xor     r8d, r8d; ulOptions
0x1800031fb  lea     rax, [rsp+48h+hKey]
0x180003200  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003207  mov     [rsp+48h+phkResult], rax; phkResult
0x18000320c  call    cs:__imp_RegOpenKeyExW
0x180003212  mov     ebx, eax
0x180003214  test    eax, eax
0x180003216  jz      short loc_18000322C
0x180003218  jle     loc_180003331
0x18000321e  movzx   ebx, ax
0x180003221  or      ebx, 80070000h
0x180003227  jmp     loc_180003331
0x18000322c  mov     rcx, [rsp+48h+hKey]; hKey
0x180003231  lea     rax, [rsp+48h+cbData]
0x180003236  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000323b  lea     r9, [rsp+48h+Type]; lpType
0x180003240  xor     r8d, r8d; lpReserved
0x180003243  mov     [rsp+48h+phkResult], rdi; lpData
0x180003248  lea     rdx, ValueName; "GatewayFQDN"
0x18000324f  call    cs:__imp_RegQueryValueExW
0x180003255  mov     ebx, eax
0x180003257  test    eax, eax
0x180003259  jnz     short loc_180003218
0x18000325b  cmp     [rsp+48h+Type], 7
0x180003260  jz      short loc_1800032B8
0x180003262  mov     ebx, 800759EFh
0x180003267  mov     rcx, cs:WPP_GLOBAL_Control
0x18000326e  lea     rax, WPP_GLOBAL_Control
0x180003275  cmp     rcx, rax
0x180003278  jz      loc_180003331
0x18000327e  test    byte ptr [rcx+1Ch], 1
0x180003282  jz      loc_180003331
0x180003288  cmp     byte ptr [rcx+19h], 2
0x18000328c  jb      loc_180003331
0x180003292  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180003297  mov     edx, 45h ; 'E'
0x18000329c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032a3  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800032aa  mov     r9d, eax
0x1800032ad  mov     rcx, [rcx+10h]
0x1800032b1  call    WPP_SF_D
0x1800032b6  jmp     short loc_180003331
0x1800032b8  cmp     [rsp+48h+cbData], 4
0x1800032bd  jnb     short loc_1800032EF
0x1800032bf  mov     ebx, 800759EFh
0x1800032c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032cb  lea     rax, WPP_GLOBAL_Control
0x1800032d2  cmp     rcx, rax
0x1800032d5  jz      short loc_180003331
0x1800032d7  test    byte ptr [rcx+1Ch], 1
0x1800032db  jz      short loc_180003331
0x1800032dd  cmp     byte ptr [rcx+19h], 2
0x1800032e1  jb      short loc_180003331
0x1800032e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800032e8  mov     edx, 46h ; 'F'
0x1800032ed  jmp     short loc_18000329C
0x1800032ef  mov     rbx, rdi
0x1800032f2  cmp     [rbx], bp
0x1800032f5  jnz     short loc_180003306
0x1800032f7  cmp     [rbx+2], bp
0x1800032fb  jz      short loc_180003328
0x1800032fd  add     rbx, 2
0x180003301  cmp     [rbx], bp
0x180003304  jz      short loc_1800032FD
0x180003306  mov     rdx, rsi; String2
0x180003309  mov     rcx, rbx; String1
0x18000330c  call    ?IsEqualDomainName@CUT@@SAHPEBG0@Z; CUT::IsEqualDomainName(ushort const *,ushort const *)
0x180003311  test    eax, eax
0x180003313  jnz     short loc_18000332F
0x180003315  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003319  inc     rax
0x18000331c  cmp     [rbx+rax*2], bp
0x180003320  jnz     short loc_180003319
0x180003322  lea     rbx, [rbx+rax*2]
0x180003326  jmp     short loc_1800032F2
0x180003328  mov     ebx, 800759EFh
0x18000332d  jmp     short loc_180003331
0x18000332f  mov     ebx, ebp
0x180003331  test    rdi, rdi
0x180003334  jz      short loc_18000333F
0x180003336  mov     rcx, rdi; pv
0x180003339  call    cs:__imp_CoTaskMemFree
0x18000333f  mov     rcx, [rsp+48h+hKey]; hKey
0x180003344  test    rcx, rcx
0x180003347  jz      short loc_18000334F
0x180003349  call    cs:__imp_RegCloseKey
0x18000334f  mov     eax, ebx
0x180003351  mov     rbx, [rsp+48h+arg_18]
0x180003356  add     rsp, 30h
0x18000335a  pop     rdi
0x18000335b  pop     rsi
0x18000335c  pop     rbp
0x18000335d  retn
```
