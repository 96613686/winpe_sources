# UmsHlprInit

- ea: `0x1400310c0`
- end: `0x140031886`
- name: `UmsHlprInit`
- size: `1990`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400877f0`

## callees

- `0x1400057f4`
- `0x1400310c0`
- `0x140053720`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x14003115d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400311a4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400311eb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003122f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031273`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400312b4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400312f8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003133c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031380`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400313c4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031417`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003146a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400314ee`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031534`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003115d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400311a4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400311eb`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003122f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031273`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400312b4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400312f8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003133c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031380`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400313c4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031417`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14003146a`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400314ee`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031534`
- `ntdll!RtlNtStatusToDosError` at `0x140031478`
- `ntdll!RtlNtStatusToDosError` at `0x140031546`
- `ntdll!RtlNtStatusToDosError` at `0x140031598`
- `ntdll!RtlNtStatusToDosError` at `0x1400315d4`
- `ntdll!RtlNtStatusToDosError` at `0x140031613`
- `ntdll!RtlNtStatusToDosError` at `0x140031652`
- `ntdll!RtlNtStatusToDosError` at `0x140031691`
- `ntdll!RtlNtStatusToDosError` at `0x1400316d0`
- `ntdll!RtlNtStatusToDosError` at `0x14003170f`
- `ntdll!RtlNtStatusToDosError` at `0x14003174e`
- `ntdll!RtlNtStatusToDosError` at `0x14003178d`
- `ntdll!RtlNtStatusToDosError` at `0x1400317cc`
- `ntdll!RtlNtStatusToDosError` at `0x1400317ff`
- `ntdll!RtlNtStatusToDosError` at `0x140031832`
- `ntdll!RtlNtStatusToDosError` at `0x140031478`
- `ntdll!RtlNtStatusToDosError` at `0x140031546`
- `ntdll!RtlNtStatusToDosError` at `0x140031598`
- `ntdll!RtlNtStatusToDosError` at `0x1400315d4`
- `ntdll!RtlNtStatusToDosError` at `0x140031613`
- `ntdll!RtlNtStatusToDosError` at `0x140031652`
- `ntdll!RtlNtStatusToDosError` at `0x140031691`
- `ntdll!RtlNtStatusToDosError` at `0x1400316d0`
- `ntdll!RtlNtStatusToDosError` at `0x14003170f`
- `ntdll!RtlNtStatusToDosError` at `0x14003174e`
- `ntdll!RtlNtStatusToDosError` at `0x14003178d`
- `ntdll!RtlNtStatusToDosError` at `0x1400317cc`
- `ntdll!RtlNtStatusToDosError` at `0x1400317ff`
- `ntdll!RtlNtStatusToDosError` at `0x140031832`

## pseudocode

```c
__int64 UmsHlprInit()
{
  ULONG v0; // ebx
  int v1; // eax
  unsigned int v2; // edi
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  CUser *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+68h] [rbp-30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v21; // [rsp+70h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v22; // [rsp+78h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+80h] [rbp-18h] BYREF

  *(_DWORD *)v21.Value = 0;
  *(_WORD *)&v21.Value[4] = 512;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v22.Value = 0;
  *(_WORD *)&v22.Value[4] = 256;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 768;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 3840;
  v0 = 0;
  v1 = RtlAllocateAndInitializeSid(&v21, 1u, 0, 0, 0, 0, 0, 0, 0, 0, (PSID *)&g_pSidLocal);
  v2 = v1;
  if ( v1 < 0 )
  {
    v0 = RtlNtStatusToDosError(v1);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 10;
      goto LABEL_23;
    }
  }
  else
  {
    v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &g_pSidAdmin);
    v2 = v3;
    if ( v3 < 0 )
    {
      v0 = RtlNtStatusToDosError(v3);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 11;
        goto LABEL_23;
      }
    }
    else
    {
      v4 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x223u, 0, 0, 0, 0, 0, 0, &g_pSidPowerUser);
      v2 = v4;
      if ( v4 < 0 )
      {
        v0 = RtlNtStatusToDosError(v4);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 12;
          goto LABEL_23;
        }
      }
      else
      {
        v5 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &g_pSidRestricted);
        v2 = v5;
        if ( v5 < 0 )
        {
          v0 = RtlNtStatusToDosError(v5);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 13;
            goto LABEL_23;
          }
        }
        else
        {
          v6 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &g_pSidLocalService);
          v2 = v6;
          if ( v6 < 0 )
          {
            v0 = RtlNtStatusToDosError(v6);
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = 14;
              goto LABEL_23;
            }
          }
          else
          {
            v7 = RtlAllocateAndInitializeSid(&v22, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &g_pSidWorld);
            v2 = v7;
            if ( v7 < 0 )
            {
              v0 = RtlNtStatusToDosError(v7);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = 15;
                goto LABEL_23;
              }
            }
            else
            {
              v8 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &g_pSidSystem);
              v2 = v8;
              if ( v8 < 0 )
              {
                v0 = RtlNtStatusToDosError(v8);
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = 16;
                  goto LABEL_23;
                }
              }
              else
              {
                v9 = RtlAllocateAndInitializeSid(&v23, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &g_pSidCreator);
                v2 = v9;
                if ( v9 < 0 )
                {
                  v0 = RtlNtStatusToDosError(v9);
                  v14 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = 17;
                    goto LABEL_23;
                  }
                }
                else
                {
                  v10 = RtlAllocateAndInitializeSid(
                          &IdentifierAuthority,
                          1u,
                          4u,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &g_pSidInteractive);
                  v2 = v10;
                  if ( v10 < 0 )
                  {
                    v0 = RtlNtStatusToDosError(v10);
                    v14 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v15 = 18;
                      goto LABEL_23;
                    }
                  }
                  else
                  {
                    v11 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, &g_pSidService);
                    v2 = v11;
                    if ( v11 < 0 )
                    {
                      v0 = RtlNtStatusToDosError(v11);
                      v14 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v15 = 19;
                        goto LABEL_23;
                      }
                    }
                    else
                    {
                      v12 = RtlAllocateAndInitializeSid(
                              &IdentifierAuthority,
                              3u,
                              0x5Au,
                              0,
                              NtCurrentPeb()->SessionId,
                              0,
                              0,
                              0,
                              0,
                              0,
                              &g_pSidWindowManager);
                      v2 = v12;
                      if ( v12 < 0 )
                      {
                        v0 = RtlNtStatusToDosError(v12);
                        v14 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          v15 = 20;
                          goto LABEL_23;
                        }
                      }
                      else
                      {
                        v13 = RtlAllocateAndInitializeSid(
                                &IdentifierAuthority,
                                3u,
                                0x60u,
                                0,
                                NtCurrentPeb()->SessionId,
                                0,
                                0,
                                0,
                                0,
                                0,
                                &g_pSidFontDriverHost);
                        v2 = v13;
                        if ( v13 >= 0 )
                        {
                          v16 = RtlAllocateAndInitializeSid(&v20, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &g_pSidAnyPackage);
                          v2 = v16;
                          if ( v16 < 0 )
                          {
                            v0 = RtlNtStatusToDosError(v16);
                            v14 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              v15 = 22;
                              goto LABEL_23;
                            }
                          }
                          else
                          {
                            v17 = RtlAllocateAndInitializeSid(
                                    &v20,
                                    2u,
                                    2u,
                                    2u,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    &g_pSidAnyRestrictedPackage);
                            v2 = v17;
                            if ( v17 < 0 )
                            {
                              v0 = RtlNtStatusToDosError(v17);
                              v14 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                v15 = 23;
                                goto LABEL_23;
                              }
                            }
                          }
                        }
                        else
                        {
                          v0 = RtlNtStatusToDosError(v13);
                          v14 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v15 = 21;
LABEL_23:
                            WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_b764378308ac3a0666162e458f2d70df_Traceguids, v2);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1400310c0  mov     r11, rsp
0x1400310c3  mov     [r11+8], rbx
0x1400310c7  push    rdi
0x1400310c8  sub     rsp, 90h
0x1400310cf  mov     rax, cs:__security_cookie
0x1400310d6  xor     rax, rsp
0x1400310d9  mov     [rsp+98h+var_10], rax
0x1400310e1  mov     [rsp+98h+var_28], 0
0x1400310e9  mov     [rsp+98h+var_24], 200h
0x1400310f0  mov     dword ptr [rsp+98h+IdentifierAuthority.Value], 0
0x1400310f8  mov     word ptr [rsp+98h+IdentifierAuthority.Value+4], 500h
0x1400310ff  mov     dword ptr [rsp+98h+var_20.Value], 0
0x140031107  mov     word ptr [rsp+98h+var_20.Value+4], 100h
0x14003110e  mov     dword ptr [r11-18h], 0
0x140031116  mov     word ptr [r11-14h], 300h
0x14003111d  mov     dword ptr [rsp+98h+var_30.Value], 0
0x140031125  mov     word ptr [rsp+98h+var_30.Value+4], 0F00h
0x14003112c  lea     rax, g_pSidLocal
0x140031133  mov     [r11-48h], rax
0x140031137  xor     ebx, ebx
0x140031139  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003113d  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031141  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031145  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x140031149  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003114d  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x140031151  xor     r9d, r9d; SubAuthority1
0x140031154  xor     r8d, r8d; SubAuthority0
0x140031157  mov     dl, 1; SubAuthorityCount
0x140031159  lea     rcx, [r11-28h]; IdentifierAuthority
0x14003115d  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031163  mov     edi, eax
0x140031165  test    eax, eax
0x140031167  js      loc_1400315D2
0x14003116d  lea     rax, g_pSidAdmin
0x140031174  mov     [rsp+98h+Sid], rax; Sid
0x140031179  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003117d  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031181  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031185  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x140031189  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003118d  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x140031191  mov     r9d, 220h; SubAuthority1
0x140031197  mov     r8d, 20h ; ' '; SubAuthority0
0x14003119d  mov     dl, 2; SubAuthorityCount
0x14003119f  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x1400311a4  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400311aa  mov     edi, eax
0x1400311ac  test    eax, eax
0x1400311ae  js      loc_140031611
0x1400311b4  lea     rax, g_pSidPowerUser
0x1400311bb  mov     [rsp+98h+Sid], rax; Sid
0x1400311c0  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x1400311c4  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x1400311c8  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x1400311cc  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x1400311d0  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400311d4  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x1400311d8  mov     r9d, 223h; SubAuthority1
0x1400311de  mov     r8d, 20h ; ' '; SubAuthority0
0x1400311e4  mov     dl, 2; SubAuthorityCount
0x1400311e6  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x1400311eb  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400311f1  mov     edi, eax
0x1400311f3  test    eax, eax
0x1400311f5  js      loc_140031650
0x1400311fb  lea     rax, g_pSidRestricted
0x140031202  mov     [rsp+98h+Sid], rax; Sid
0x140031207  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003120b  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x14003120f  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031213  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x140031217  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003121b  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x14003121f  xor     r9d, r9d; SubAuthority1
0x140031222  mov     r8d, 0Ch; SubAuthority0
0x140031228  mov     dl, 1; SubAuthorityCount
0x14003122a  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x14003122f  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031235  mov     edi, eax
0x140031237  test    eax, eax
0x140031239  js      loc_14003168F
0x14003123f  lea     rax, g_pSidLocalService
0x140031246  mov     [rsp+98h+Sid], rax; Sid
0x14003124b  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003124f  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031253  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031257  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x14003125b  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003125f  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x140031263  xor     r9d, r9d; SubAuthority1
0x140031266  mov     r8d, 13h; SubAuthority0
0x14003126c  mov     dl, 1; SubAuthorityCount
0x14003126e  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x140031273  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031279  mov     edi, eax
0x14003127b  test    eax, eax
0x14003127d  js      loc_1400316CE
0x140031283  lea     rax, g_pSidWorld
0x14003128a  mov     [rsp+98h+Sid], rax; Sid
0x14003128f  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x140031293  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031297  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x14003129b  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x14003129f  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400312a3  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x1400312a7  xor     r9d, r9d; SubAuthority1
0x1400312aa  xor     r8d, r8d; SubAuthority0
0x1400312ad  mov     dl, 1; SubAuthorityCount
0x1400312af  lea     rcx, [rsp+98h+var_20]; IdentifierAuthority
0x1400312b4  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400312ba  mov     edi, eax
0x1400312bc  test    eax, eax
0x1400312be  js      loc_14003170D
0x1400312c4  lea     rax, g_pSidSystem
0x1400312cb  mov     [rsp+98h+Sid], rax; Sid
0x1400312d0  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x1400312d4  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x1400312d8  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x1400312dc  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x1400312e0  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400312e4  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x1400312e8  xor     r9d, r9d; SubAuthority1
0x1400312eb  mov     r8d, 12h; SubAuthority0
0x1400312f1  mov     dl, 1; SubAuthorityCount
0x1400312f3  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x1400312f8  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400312fe  mov     edi, eax
0x140031300  test    eax, eax
0x140031302  js      loc_14003174C
0x140031308  lea     rax, g_pSidCreator
0x14003130f  mov     [rsp+98h+Sid], rax; Sid
0x140031314  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x140031318  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x14003131c  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031320  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x140031324  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x140031328  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x14003132c  xor     r9d, r9d; SubAuthority1
0x14003132f  xor     r8d, r8d; SubAuthority0
0x140031332  mov     dl, 1; SubAuthorityCount
0x140031334  lea     rcx, [rsp+98h+var_18]; IdentifierAuthority
0x14003133c  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031342  mov     edi, eax
0x140031344  test    eax, eax
0x140031346  js      loc_14003178B
0x14003134c  lea     rax, g_pSidInteractive
0x140031353  mov     [rsp+98h+Sid], rax; Sid
0x140031358  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003135c  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031360  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031364  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x140031368  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003136c  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x140031370  xor     r9d, r9d; SubAuthority1
0x140031373  mov     r8d, 4; SubAuthority0
0x140031379  mov     dl, 1; SubAuthorityCount
0x14003137b  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x140031380  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031386  mov     edi, eax
0x140031388  test    eax, eax
0x14003138a  js      loc_1400317CA
0x140031390  lea     rax, g_pSidService
0x140031397  mov     [rsp+98h+Sid], rax; Sid
0x14003139c  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x1400313a0  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x1400313a4  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x1400313a8  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x1400313ac  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400313b0  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x1400313b4  xor     r9d, r9d; SubAuthority1
0x1400313b7  mov     r8d, 6; SubAuthority0
0x1400313bd  mov     dl, 1; SubAuthorityCount
0x1400313bf  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x1400313c4  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400313ca  mov     edi, eax
0x1400313cc  test    eax, eax
0x1400313ce  js      loc_140031596
0x1400313d4  mov     rax, gs:60h
0x1400313dd  lea     rcx, g_pSidWindowManager
0x1400313e4  mov     [rsp+98h+Sid], rcx; Sid
0x1400313e9  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x1400313ed  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x1400313f1  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x1400313f5  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x1400313f9  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400313fd  mov     eax, [rax+2C0h]
0x140031403  mov     [rsp+98h+SubAuthority2], eax; SubAuthority2
0x140031407  xor     r9d, r9d; SubAuthority1
0x14003140a  mov     r8d, 5Ah ; 'Z'; SubAuthority0
0x140031410  mov     dl, 3; SubAuthorityCount
0x140031412  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x140031417  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003141d  mov     edi, eax
0x14003141f  test    eax, eax
0x140031421  js      loc_1400317FD
0x140031427  mov     rax, gs:60h
0x140031430  lea     rcx, g_pSidFontDriverHost
0x140031437  mov     [rsp+98h+Sid], rcx; Sid
0x14003143c  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x140031440  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031444  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031448  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x14003144c  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x140031450  mov     eax, [rax+2C0h]
0x140031456  mov     [rsp+98h+SubAuthority2], eax; SubAuthority2
0x14003145a  xor     r9d, r9d; SubAuthority1
0x14003145d  mov     r8d, 60h ; '`'; SubAuthority0
0x140031463  mov     dl, 3; SubAuthorityCount
0x140031465  lea     rcx, [rsp+98h+IdentifierAuthority]; IdentifierAuthority
0x14003146a  call    cs:__imp_RtlAllocateAndInitializeSid
0x140031470  mov     edi, eax
0x140031472  test    eax, eax
0x140031474  jns     short loc_1400314B5
0x140031476  mov     ecx, eax; Status
0x140031478  call    cs:__imp_RtlNtStatusToDosError
0x14003147e  mov     ebx, eax
0x140031480  lea     rdx, WPP_GLOBAL_Control
0x140031487  mov     rcx, cs:WPP_GLOBAL_Control
0x14003148e  cmp     rcx, rdx
0x140031491  jz      loc_140031863
0x140031497  test    byte ptr [rcx+1Ch], 1
0x14003149b  jz      loc_140031863
0x1400314a1  cmp     byte ptr [rcx+19h], 2
0x1400314a5  jb      loc_140031863
0x1400314ab  mov     edx, 15h
0x1400314b0  jmp     loc_14003157E
0x1400314b5  lea     rax, g_pSidAnyPackage
0x1400314bc  mov     [rsp+98h+Sid], rax; Sid
0x1400314c1  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x1400314c5  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x1400314c9  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x1400314cd  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x1400314d1  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x1400314d5  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x1400314d9  mov     r9d, 1; SubAuthority1
0x1400314df  mov     r8d, 2; SubAuthority0
0x1400314e5  movzx   edx, r8b; SubAuthorityCount
0x1400314e9  lea     rcx, [rsp+98h+var_30]; IdentifierAuthority
0x1400314ee  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400314f4  mov     edi, eax
0x1400314f6  test    eax, eax
0x1400314f8  js      loc_140031830
0x1400314fe  lea     rax, g_pSidAnyRestrictedPackage
0x140031505  mov     [rsp+98h+Sid], rax; Sid
0x14003150a  mov     [rsp+98h+SubAuthority7], ebx; SubAuthority7
0x14003150e  mov     [rsp+98h+SubAuthority6], ebx; SubAuthority6
0x140031512  mov     [rsp+98h+SubAuthority5], ebx; SubAuthority5
0x140031516  mov     [rsp+98h+SubAuthority4], ebx; SubAuthority4
0x14003151a  mov     [rsp+98h+SubAuthority3], ebx; SubAuthority3
0x14003151e  mov     [rsp+98h+SubAuthority2], ebx; SubAuthority2
0x140031522  mov     r9d, 2; SubAuthority1
0x140031528  mov     r8d, r9d; SubAuthority0
0x14003152b  movzx   edx, r9b; SubAuthorityCount
0x14003152f  lea     rcx, [rsp+98h+var_30]; IdentifierAuthority
0x140031534  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003153a  mov     edi, eax
0x14003153c  test    eax, eax
0x14003153e  jns     loc_140031863
0x140031544  mov     ecx, eax; Status
0x140031546  call    cs:__imp_RtlNtStatusToDosError
0x14003154c  mov     ebx, eax
0x14003154e  lea     rdx, WPP_GLOBAL_Control
0x140031555  mov     rcx, cs:WPP_GLOBAL_Control
0x14003155c  cmp     rcx, rdx
0x14003155f  jz      loc_140031863
0x140031565  test    byte ptr [rcx+1Ch], 1
0x140031569  jz      loc_140031863
0x14003156f  cmp     byte ptr [rcx+19h], 2
0x140031573  jb      loc_140031863
0x140031579  mov     edx, 17h
0x14003157e  mov     r9d, edi
0x140031581  lea     r8, WPP_b764378308ac3a0666162e458f2d70df_Traceguids
0x140031588  mov     rcx, [rcx+10h]
0x14003158c  call    WPP_SF_d
0x140031591  jmp     loc_140031863
0x140031596  mov     ecx, edi; Status
0x140031598  call    cs:__imp_RtlNtStatusToDosError
0x14003159e  mov     ebx, eax
0x1400315a0  lea     rdx, WPP_GLOBAL_Control
0x1400315a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315ae  cmp     rcx, rdx
0x1400315b1  jz      loc_140031863
0x1400315b7  test    byte ptr [rcx+1Ch], 1
0x1400315bb  jz      loc_140031863
0x1400315c1  cmp     byte ptr [rcx+19h], 2
0x1400315c5  jb      loc_140031863
0x1400315cb  mov     edx, 13h
0x1400315d0  jmp     short loc_14003157E
0x1400315d2  mov     ecx, edi; Status
0x1400315d4  call    cs:__imp_RtlNtStatusToDosError
0x1400315da  mov     ebx, eax
0x1400315dc  lea     rdx, WPP_GLOBAL_Control
0x1400315e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315ea  cmp     rcx, rdx
0x1400315ed  jz      loc_140031863
0x1400315f3  test    byte ptr [rcx+1Ch], 1
0x1400315f7  jz      loc_140031863
0x1400315fd  cmp     byte ptr [rcx+19h], 2
0x140031601  jb      loc_140031863
  ... truncated ...
```
