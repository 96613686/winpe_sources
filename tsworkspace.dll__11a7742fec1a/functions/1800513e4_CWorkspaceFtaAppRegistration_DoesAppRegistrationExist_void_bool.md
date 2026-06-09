# CWorkspaceFtaAppRegistration::DoesAppRegistrationExist(void *,bool &)

- ea: `0x1800513e4`
- end: `0x180051628`
- name: `?DoesAppRegistrationExist@CWorkspaceFtaAppRegistration@@IEAAJPEAXAEA_N@Z`
- size: `580`
- prototype: `int(CWorkspaceFtaAppRegistration *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180051968`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x1800513e4`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800514ef`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800514ef`
- `ADVAPI32!RegQueryValueExW` at `0x180051530`
- `ADVAPI32!RegQueryValueExW` at `0x180051530`
- `ADVAPI32!RegCloseKey` at `0x180051549`
- `ADVAPI32!RegCloseKey` at `0x180051613`
- `ADVAPI32!RegCloseKey` at `0x180051549`
- `ADVAPI32!RegCloseKey` at `0x180051613`

## pseudocode

```c
__int64 __fastcall CWorkspaceFtaAppRegistration::DoesAppRegistrationExist(
        CWorkspaceFtaAppRegistration *this,
        void *a2,
        bool *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v7; // ebx
  int i; // edi
  unsigned int v9; // eax
  LSTATUS v10; // eax
  const WCHAR *v11; // rax
  LSTATUS Value; // eax
  unsigned int v13; // esi
  unsigned int v14; // eax
  __int64 v15; // rdx
  HKEY hKey[9]; // [rsp+40h] [rbp-48h]
  HKEY phkResult; // [rsp+98h] [rbp+10h] BYREF

  phkResult = 0;
  *(__m128i *)hKey = _mm_load_si128((const __m128i *)&_xmm_ffffffff80000002ffffffff80000001);
  if ( a2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    v7 = -2147024809;
    goto LABEL_38;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      *a3 = 0;
      v7 = 1;
      goto LABEL_38;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v9, i);
    }
    v10 = RegOpenKeyTransactedW(hKey[i], L"Software\\RegisteredApplications", 0, 0x20019u, &phkResult, a2, 0);
    v7 = v10;
    if ( v10 == 2 )
      continue;
    if ( v10 )
      break;
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
    Value = RegQueryValueExW(phkResult, v11, 0, 0, 0, 0);
    v7 = Value;
    if ( !Value )
    {
      *a3 = 1;
      v7 = 0;
      goto LABEL_38;
    }
    if ( Value != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( Value > 0 )
          v13 = (unsigned __int16)Value | 0x80070000;
        else
          v13 = Value;
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 32;
LABEL_34:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids, v14, v13);
        goto LABEL_35;
      }
      goto LABEL_35;
    }
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v10 > 0 )
      v13 = (unsigned __int16)v10 | 0x80070000;
    else
      v13 = v10;
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 31;
    goto LABEL_34;
  }
LABEL_35:
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_38:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800513e4  mov     rax, rsp
0x1800513e7  push    rbx
0x1800513e8  push    rbp
0x1800513e9  push    rsi
0x1800513ea  push    rdi
0x1800513eb  push    r14
0x1800513ed  push    r15
0x1800513ef  sub     rsp, 58h
0x1800513f3  movdqa  xmm0, cs:__xmm@ffffffff80000002ffffffff80000001
0x1800513fb  mov     r14, r8
0x1800513fe  mov     qword ptr [rax+10h], 0
0x180051406  mov     rbp, rdx
0x180051409  mov     r15, rcx
0x18005140c  movdqu  xmmword ptr [rax-48h], xmm0
0x180051411  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180051415  jnz     short loc_18005146A
0x180051417  mov     rax, cs:WPP_GLOBAL_Control
0x18005141e  lea     rsi, WPP_GLOBAL_Control
0x180051425  cmp     rax, rsi
0x180051428  jz      short loc_180051460
0x18005142a  test    byte ptr [rax+1Ch], 8
0x18005142e  jz      short loc_180051460
0x180051430  cmp     byte ptr [rax+19h], 2
0x180051434  jb      short loc_180051460
0x180051436  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005143b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051442  lea     edx, [rbp+1Eh]
0x180051445  mov     r9d, eax
0x180051448  mov     dword ptr [rsp+88h+phkResult], 80070057h
0x180051450  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x180051457  mov     rcx, [rcx+10h]
0x18005145b  call    WPP_SF_Dd
0x180051460  mov     ebx, 80070057h
0x180051465  jmp     loc_180051606
0x18005146a  xor     edi, edi
0x18005146c  lea     rsi, WPP_GLOBAL_Control
0x180051473  cmp     edi, 2
0x180051476  jge     loc_1800515FD
0x18005147c  mov     rax, cs:WPP_GLOBAL_Control
0x180051483  cmp     rax, rsi
0x180051486  jz      short loc_1800514BC
0x180051488  test    byte ptr [rax+1Ch], 1
0x18005148c  jz      short loc_1800514BC
0x18005148e  cmp     byte ptr [rax+19h], 4
0x180051492  jb      short loc_1800514BC
0x180051494  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800514a0  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x1800514a7  mov     edx, 1Eh
0x1800514ac  mov     dword ptr [rsp+88h+phkResult], edi
0x1800514b0  mov     r9d, eax
0x1800514b3  mov     rcx, [rcx+10h]
0x1800514b7  call    WPP_SF_Dd
0x1800514bc  mov     [rsp+88h+pExtendedParemeter], 0; pExtendedParemeter
0x1800514c5  lea     rax, [rsp+88h+arg_8]
0x1800514cd  movsxd  rcx, edi
0x1800514d0  lea     rdx, aSoftwareRegist; "Software\\RegisteredApplications"
0x1800514d7  mov     [rsp+88h+hTransaction], rbp; hTransaction
0x1800514dc  mov     r9d, 20019h; samDesired
0x1800514e2  xor     r8d, r8d; ulOptions
0x1800514e5  mov     [rsp+88h+phkResult], rax; phkResult
0x1800514ea  mov     rcx, [rsp+rcx*8+88h+hKey]; hKey
0x1800514ef  call    cs:__imp_RegOpenKeyTransactedW
0x1800514f5  mov     ebx, eax
0x1800514f7  cmp     eax, 2
0x1800514fa  jz      short loc_18005155B
0x1800514fc  test    eax, eax
0x1800514fe  jnz     loc_1800515A0
0x180051504  lea     rcx, [r15+50h]
0x180051508  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005150d  mov     rcx, [rsp+88h+arg_8]; hKey
0x180051515  xor     r9d, r9d; lpType
0x180051518  xor     r8d, r8d; lpReserved
0x18005151b  mov     [rsp+88h+hTransaction], 0; lpcbData
0x180051524  mov     rdx, rax; lpValueName
0x180051527  mov     [rsp+88h+phkResult], 0; lpData
0x180051530  call    cs:__imp_RegQueryValueExW
0x180051536  mov     ebx, eax
0x180051538  test    eax, eax
0x18005153a  jz      short loc_180051598
0x18005153c  cmp     eax, 2
0x18005153f  jnz     short loc_180051562
0x180051541  mov     rcx, [rsp+88h+arg_8]; hKey
0x180051549  call    cs:__imp_RegCloseKey
0x18005154f  mov     [rsp+88h+arg_8], 0
0x18005155b  inc     edi
0x18005155d  jmp     loc_180051473
0x180051562  mov     rax, cs:WPP_GLOBAL_Control
0x180051569  mov     edi, 80070000h
0x18005156e  cmp     rax, rsi
0x180051571  jz      short loc_1800515F2
0x180051573  test    byte ptr [rax+1Ch], 8
0x180051577  jz      short loc_1800515F2
0x180051579  cmp     byte ptr [rax+19h], 2
0x18005157d  jb      short loc_1800515F2
0x18005157f  test    ebx, ebx
0x180051581  jg      short loc_180051587
0x180051583  mov     esi, ebx
0x180051585  jmp     short loc_18005158C
0x180051587  movzx   esi, bx
0x18005158a  or      esi, edi
0x18005158c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180051591  mov     edx, 20h ; ' '
0x180051596  jmp     short loc_1800515D4
0x180051598  mov     byte ptr [r14], 1
0x18005159c  xor     ebx, ebx
0x18005159e  jmp     short loc_180051606
0x1800515a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800515a7  mov     edi, 80070000h
0x1800515ac  cmp     rax, rsi
0x1800515af  jz      short loc_1800515F2
0x1800515b1  test    byte ptr [rax+1Ch], 8
0x1800515b5  jz      short loc_1800515F2
0x1800515b7  cmp     byte ptr [rax+19h], 2
0x1800515bb  jb      short loc_1800515F2
0x1800515bd  test    ebx, ebx
0x1800515bf  jg      short loc_1800515C5
0x1800515c1  mov     esi, ebx
0x1800515c3  jmp     short loc_1800515CA
0x1800515c5  movzx   esi, bx
0x1800515c8  or      esi, edi
0x1800515ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800515cf  mov     edx, 1Fh
0x1800515d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800515db  lea     r8, WPP_4457a498d3623a043bdd7d35ccf3f7df_Traceguids
0x1800515e2  mov     r9d, eax
0x1800515e5  mov     dword ptr [rsp+88h+phkResult], esi
0x1800515e9  mov     rcx, [rcx+10h]
0x1800515ed  call    WPP_SF_Dd
0x1800515f2  test    ebx, ebx
0x1800515f4  jle     short loc_180051606
0x1800515f6  movzx   ebx, bx
0x1800515f9  or      ebx, edi
0x1800515fb  jmp     short loc_180051606
0x1800515fd  mov     byte ptr [r14], 0
0x180051601  mov     ebx, 1
0x180051606  mov     rcx, [rsp+88h+arg_8]; hKey
0x18005160e  test    rcx, rcx
0x180051611  jz      short loc_180051619
0x180051613  call    cs:__imp_RegCloseKey
0x180051619  mov     eax, ebx
0x18005161b  add     rsp, 58h
0x18005161f  pop     r15
0x180051621  pop     r14
0x180051623  pop     rdi
0x180051624  pop     rsi
0x180051625  pop     rbp
0x180051626  pop     rbx
0x180051627  retn
```
