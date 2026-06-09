# ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)

- ea: `0x180006520`
- end: `0x180006abe`
- name: `?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z`
- size: `1438`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003ad0`
- `0x1800058b0`
- `0x180005bf0`
- `0x180006520`
- `0x180006ad0`

## callees

- `0x1800054f0`
- `0x18000592c`
- `0x180005cf4`
- `0x180006520`
- `0x1800071b4`
- `0x180007248`
- `0x1800072a4`
- `0x18000741c`
- `0x18000774c`
- `0x180007854`
- `0x180007938`
- `0x180007b08`
- `0x180008930`
- `0x180008af0`
- `0x1800099e8`
- `0x180009d08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067ef`
- `WSCAPI!wscLuaSettingsFix` at `0x1800066f4`
- `WSCAPI!wscLuaSettingsFix` at `0x1800066f4`
- `WSCAPI!wscIeSettingsFix` at `0x180006753`
- `WSCAPI!wscIeSettingsFix` at `0x180006753`
- `WSCAPI!wscIcfEnable` at `0x180006606`
- `WSCAPI!wscIcfEnable` at `0x180006606`

## string_xrefs

- `0x1800065da`: `http://go.microsoft.com/fwlink/?LinkId=534032`
- `0x1800065e3`: `http://go.microsoft.com/fwlink/?LinkId=534032`
- `0x1800065ec`: `http://go.microsoft.com/fwlink/?LinkId=534032`

## pseudocode

```c
char __fastcall ExecuteSecurityActionHandler(HWND a1, int a2, struct SecurityLogicState *a3, char a4)
{
  int v6; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // edx
  const unsigned __int16 *v17; // rdx
  int v18; // edx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  __int64 v23; // r9
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rcx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  OLECHAR *v29; // rdx
  HANDLE Thread; // rax
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  unsigned int v35; // r9d
  const struct SecurityActionData *v36; // r8
  int v37; // eax
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  int v49[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = a2;
  if ( g_hMainWnd && a2 == 112 && (CStatusManager::m_dwDefenderBitfields & 0x10) == 0 )
    v6 = 110;
  if ( !(unsigned int)RunningAsAdministrator() && !a4 )
  {
    if ( v6 == 102 )
      return LaunchModalElevatedAction(a1, (unsigned int)v6);
    v9 = (const unsigned __int16 *)(unsigned int)(v6 - 117);
    if ( (unsigned int)v9 <= 1 )
      return LaunchModalElevatedAction(a1, (unsigned int)v6);
  }
  if ( v6 <= 125 )
  {
    if ( v6 == 125 )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DisableAMsEnableDefender, 0, 0, 0);
      CloseHandle(Thread);
      return 1;
    }
    if ( v6 <= 112 )
    {
      if ( v6 != 112 )
      {
        if ( v6 <= 107 )
        {
          if ( v6 == 107 )
          {
            v16 = 1248;
            return LaunchLinkAction(a1, v16);
          }
          v12 = v6 - 102;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  if ( v15 == 1 )
                  {
                    v16 = 1247;
                    return LaunchLinkAction(a1, v16);
                  }
                  return 1;
                }
                v17 = L"http://go.microsoft.com/fwlink/?LinkId=534032";
              }
              else
              {
                v17 = L"http://go.microsoft.com/fwlink/?LinkId=534032";
              }
            }
            else
            {
              v17 = L"http://go.microsoft.com/fwlink/?LinkId=534032";
            }
            return LaunchProgramSwitchToDesktop(a1, v17, 0, 0);
          }
          if ( (unsigned int)wscIcfEnable() )
          {
            v18 = 1166;
LABEL_29:
            SecurityLogicControl::ShowFailDlg(a1, v18);
            LOBYTE(v19) = 0;
            return v19;
          }
          goto LABEL_30;
        }
        if ( v6 == 108 )
        {
          v16 = 1249;
          return LaunchLinkAction(a1, v16);
        }
        if ( v6 == 109 )
          return handlerLaunchTakeActionDialog(a1, a3);
        if ( (unsigned int)(v6 - 110) > 1 )
          return 1;
      }
      return handlerWindowsDefenderAllActions(a1, a3, (unsigned int)v6);
    }
    if ( v6 <= 120 )
    {
      if ( v6 == 120 )
      {
        v24 = 0;
        v25 = L"Microsoft.WindowsFirewall";
      }
      else
      {
        v20 = v6 - 115;
        if ( !v20 )
        {
          if ( (unsigned int)wscIeSettingsFix() )
          {
            v18 = 1152;
            goto LABEL_29;
          }
          goto LABEL_30;
        }
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( !v22 )
          {
            v49[0] = 0;
            if ( !(unsigned int)wscLuaSettingsFix(v49) )
            {
              LOBYTE(v19) = 1;
              if ( v49[0] && (unsigned int)SecurityLogicControl::PromptUserReboot(a1) )
              {
                LOBYTE(v23) = 1;
                ExecuteSecurityActionHandler(a1, 118, 0, v23);
              }
              return v19;
            }
            v18 = 1153;
            goto LABEL_29;
          }
          v19 = v22 - 1;
          if ( !v19 )
          {
            if ( !OnRestart() )
            {
              v18 = 1154;
              goto LABEL_29;
            }
LABEL_30:
            LOBYTE(v19) = 1;
            return v19;
          }
          if ( v19 == 1 )
          {
            if ( (unsigned int)StartServiceW(v9, v8, v10) != 1 )
            {
              LOBYTE(v19) = 0;
              SecurityLogicControl::ShowFailDlg(a1, 1150);
            }
            return v19;
          }
          return 1;
        }
        v24 = L"1";
        v25 = L"Microsoft.InternetOptions";
      }
      return LaunchCpl(v25, v24);
    }
    v26 = v6 - 121;
    if ( !v26 )
      return handlerLaunchThirdParty(a1, a3);
    v27 = v26 - 1;
    if ( !v27 )
      return handlerLaunchThirdPartyDirect(a1, a3);
    v28 = v27 - 1;
    if ( v28 )
    {
      if ( v28 != 1 )
        return 1;
      v29 = L"mshelp://windows/?id=31d797aa-091d-4d67-a556-dbfaf21bf0dc";
    }
    else
    {
      v29 = (OLECHAR *)L"mshelp://windows/?id=bfe523a9-7eec-4d3f-add1-2f68b9cfa1c0";
    }
    return LaunchURL(a1, v29);
  }
  if ( v6 > 138 )
  {
    v41 = v6 - 139;
    if ( v41 )
    {
      v42 = v41 - 1;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( v44 )
          {
            v45 = v44 - 1;
            if ( v45 )
            {
              v46 = v45 - 1;
              if ( v46 )
              {
                v47 = v46 - 1;
                if ( v47 )
                {
                  v48 = v47 - 1;
                  if ( v48 )
                  {
                    if ( v48 != 1 )
                      return 1;
                    v37 = SecurityLogicControl::ShowRecDlg(
                            a1,
                            a3,
                            (const struct SecurityActionData *)L"s",
                            2u,
                            (const unsigned __int16 *)0x41E,
                            (const unsigned __int16 *)0x4A0);
                  }
                  else
                  {
                    v37 = SecurityLogicControl::ShowRecDlg(
                            a1,
                            a3,
                            (const struct SecurityActionData *)&unk_18000FB70,
                            3u,
                            (const unsigned __int16 *)0x41D,
                            (const unsigned __int16 *)0x4A3);
                  }
                }
                else
                {
                  v37 = SecurityLogicControl::ShowRecDlg(
                          a1,
                          a3,
                          (const struct SecurityActionData *)&unk_18000FB90,
                          3u,
                          (const unsigned __int16 *)0x41D,
                          (const unsigned __int16 *)0x4A3);
                }
              }
              else
              {
                v37 = SecurityLogicControl::ShowRecDlg(
                        a1,
                        a3,
                        (const struct SecurityActionData *)&unk_18000FBB0,
                        3u,
                        (const unsigned __int16 *)0x41D,
                        (const unsigned __int16 *)0x4A3);
              }
            }
            else
            {
              v37 = SecurityLogicControl::ShowRecDlg(
                      a1,
                      a3,
                      (const struct SecurityActionData *)&unk_18000FBD0,
                      3u,
                      (const unsigned __int16 *)0x41D,
                      (const unsigned __int16 *)0x4A3);
            }
          }
          else
          {
            v37 = SecurityLogicControl::ShowRecDlg(
                    a1,
                    a3,
                    (const struct SecurityActionData *)&unk_18000FBF0,
                    3u,
                    (const unsigned __int16 *)0x41D,
                    (const unsigned __int16 *)0x4A3);
          }
        }
        else
        {
          v37 = SecurityLogicControl::ShowRecDlg(
                  a1,
                  a3,
                  (const struct SecurityActionData *)&unk_18000FC10,
                  2u,
                  (const unsigned __int16 *)0x41D,
                  (const unsigned __int16 *)0x4A3);
        }
        return v37 == 1;
      }
      v36 = (const struct SecurityActionData *)&unk_18000FD40;
    }
    else
    {
      v36 = (const struct SecurityActionData *)&unk_18000FD50;
    }
LABEL_113:
    v35 = 2;
    goto LABEL_114;
  }
  if ( v6 == 138 )
  {
    v36 = (const struct SecurityActionData *)&unk_18000FD60;
    goto LABEL_113;
  }
  if ( v6 > 133 )
  {
    v38 = v6 - 134;
    if ( v38 )
    {
      v39 = v38 - 1;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( v40 )
        {
          if ( v40 != 1 )
            return 1;
          v37 = SecurityLogicControl::ShowRecDlg(
                  a1,
                  a3,
                  (const struct SecurityActionData *)&unk_18000FC20,
                  2u,
                  (const unsigned __int16 *)0x41D,
                  (const unsigned __int16 *)0x4A3);
          return v37 == 1;
        }
        v35 = 3;
        v36 = (const struct SecurityActionData *)&unk_18000FC80;
      }
      else
      {
        v35 = 3;
        v36 = (const struct SecurityActionData *)&unk_18000FCA0;
      }
    }
    else
    {
      v35 = 3;
      v36 = (const struct SecurityActionData *)&unk_18000FCC0;
    }
LABEL_114:
    v37 = SecurityLogicControl::ShowRecDlg(
            a1,
            a3,
            v36,
            v35,
            (const unsigned __int16 *)0x41C,
            (const unsigned __int16 *)0x4A2);
    return v37 == 1;
  }
  if ( v6 == 133 )
  {
    v35 = 3;
    v36 = (const struct SecurityActionData *)&unk_18000FCE0;
    goto LABEL_114;
  }
  v31 = v6 - 127;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 2;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( v34 )
        {
          if ( v34 != 1 )
            return 1;
          v35 = 3;
          v36 = (const struct SecurityActionData *)&unk_18000FD00;
          goto LABEL_114;
        }
        v36 = (const struct SecurityActionData *)&unk_18000FD20;
      }
      else
      {
        v36 = (const struct SecurityActionData *)&unk_18000FD30;
      }
      goto LABEL_113;
    }
    v37 = SecurityLogicControl::ShowRecDlg(
            a1,
            a3,
            (const struct SecurityActionData *)&unk_18000FD70,
            3u,
            (const unsigned __int16 *)0x41B,
            (const unsigned __int16 *)0x4A1);
  }
  else
  {
    v37 = SecurityLogicControl::ShowRecDlg(
            a1,
            a3,
            (const struct SecurityActionData *)&unk_18000FD90,
            3u,
            (const unsigned __int16 *)0x41B,
            (const unsigned __int16 *)0x4A1);
  }
  return v37 == 1;
}

```

## disassembly

```asm
0x180006520  push    rbx
0x180006522  push    rbp
0x180006523  push    rsi
0x180006524  push    rdi
0x180006525  sub     rsp, 68h
0x180006529  cmp     cs:?g_hMainWnd@@3PEAUHWND__@@EA, 0; HWND__ * g_hMainWnd
0x180006531  mov     bpl, r9b
0x180006534  mov     rsi, r8
0x180006537  mov     ebx, edx
0x180006539  mov     rdi, rcx
0x18000653c  jz      short loc_180006550
0x18000653e  cmp     edx, 70h ; 'p'
0x180006541  jnz     short loc_180006550
0x180006543  test    cs:?m_dwDefenderBitfields@CStatusManager@@0KA, 10h; ulong CStatusManager::m_dwDefenderBitfields
0x18000654a  lea     eax, [rdx-2]
0x18000654d  cmovz   ebx, eax
0x180006550  call    RunningAsAdministrator
0x180006555  test    eax, eax
0x180006557  jnz     short loc_18000657E
0x180006559  test    bpl, bpl
0x18000655c  jnz     short loc_18000657E
0x18000655e  mov     ecx, ebx
0x180006560  sub     ecx, 66h ; 'f'
0x180006563  jz      short loc_18000656F
0x180006565  sub     ecx, 0Fh
0x180006568  jz      short loc_18000656F
0x18000656a  cmp     ecx, 1
0x18000656d  jnz     short loc_18000657E
0x18000656f  mov     edx, ebx
0x180006571  mov     rcx, rdi
0x180006574  call    ?LaunchModalElevatedAction@@YA_NPEAUHWND__@@W4SecurityAction@@@Z; LaunchModalElevatedAction(HWND__ *,SecurityAction)
0x180006579  jmp     loc_180006AB5
0x18000657e  cmp     ebx, 7Dh ; '}'
0x180006581  jg      loc_1800067FF
0x180006587  jz      loc_1800067C7
0x18000658d  cmp     ebx, 70h ; 'p'
0x180006590  jg      loc_18000667B
0x180006596  jz      loc_18000664E
0x18000659c  cmp     ebx, 6Bh ; 'k'
0x18000659f  jg      loc_180006634
0x1800065a5  jz      loc_18000662D
0x1800065ab  sub     ebx, 66h ; 'f'
0x1800065ae  jz      short loc_180006606
0x1800065b0  sub     ebx, 1
0x1800065b3  jz      short loc_1800065EC
0x1800065b5  sub     ebx, 1
0x1800065b8  jz      short loc_1800065E3
0x1800065ba  sub     ebx, 1
0x1800065bd  jz      short loc_1800065DA
0x1800065bf  cmp     ebx, 1
0x1800065c2  jnz     loc_1800067F5
0x1800065c8  mov     edx, 4DFh; int
0x1800065cd  mov     rcx, rdi; HWND
0x1800065d0  call    ?LaunchLinkAction@@YA_NPEAUHWND__@@H@Z; LaunchLinkAction(HWND__ *,int)
0x1800065d5  jmp     loc_180006AB5
0x1800065da  lea     rdx, aHttpGoMicrosof; "http://go.microsoft.com/fwlink/?LinkId="...
0x1800065e1  jmp     short loc_1800065F3
0x1800065e3  lea     rdx, aHttpGoMicrosof_0; "http://go.microsoft.com/fwlink/?LinkId="...
0x1800065ea  jmp     short loc_1800065F3
0x1800065ec  lea     rdx, aHttpGoMicrosof_1; "http://go.microsoft.com/fwlink/?LinkId="...
0x1800065f3  xor     r9d, r9d; int
0x1800065f6  xor     r8d, r8d; unsigned __int16 *
0x1800065f9  mov     rcx, rdi; HWND
0x1800065fc  call    ?LaunchProgramSwitchToDesktop@@YA_NPEAUHWND__@@PEBG1H@Z; LaunchProgramSwitchToDesktop(HWND__ *,ushort const *,ushort const *,int)
0x180006601  jmp     loc_180006AB5
0x180006606  call    cs:__imp_wscIcfEnable
0x18000660c  test    eax, eax
0x18000660e  jz      short loc_180006621
0x180006610  mov     edx, 48Eh; int
0x180006615  mov     rcx, rdi; HWND
0x180006618  call    ?ShowFailDlg@SecurityLogicControl@@SAHPEAUHWND__@@H@Z; SecurityLogicControl::ShowFailDlg(HWND__ *,int)
0x18000661d  xor     bl, bl
0x18000661f  jmp     short loc_180006626
0x180006621  mov     ebx, 1
0x180006626  mov     al, bl
0x180006628  jmp     loc_180006AB5
0x18000662d  mov     edx, 4E0h
0x180006632  jmp     short loc_1800065CD
0x180006634  mov     ecx, ebx
0x180006636  sub     ecx, 6Ch ; 'l'
0x180006639  jz      short loc_180006671
0x18000663b  sub     ecx, 1
0x18000663e  jz      short loc_180006661
0x180006640  sub     ecx, 1
0x180006643  jz      short loc_18000664E
0x180006645  cmp     ecx, 1
0x180006648  jnz     loc_1800067F5
0x18000664e  mov     r8d, ebx
0x180006651  mov     rdx, rsi
0x180006654  mov     rcx, rdi
0x180006657  call    ?handlerWindowsDefenderAllActions@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4SecurityAction@@@Z; handlerWindowsDefenderAllActions(HWND__ *,SecurityLogicState *,SecurityAction)
0x18000665c  jmp     loc_180006AB5
0x180006661  mov     rdx, rsi; struct SecurityLogicState *
0x180006664  mov     rcx, rdi; HWND
0x180006667  call    ?handlerLaunchTakeActionDialog@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z; handlerLaunchTakeActionDialog(HWND__ *,SecurityLogicState *)
0x18000666c  jmp     loc_180006AB5
0x180006671  mov     edx, 4E1h
0x180006676  jmp     loc_1800065CD
0x18000667b  cmp     ebx, 78h ; 'x'
0x18000667e  jg      loc_180006776
0x180006684  jz      loc_18000676B
0x18000668a  sub     ebx, 73h ; 's'
0x18000668d  jz      loc_180006753
0x180006693  sub     ebx, 1
0x180006696  jz      loc_18000673B
0x18000669c  sub     ebx, 1
0x18000669f  jz      short loc_1800066E7
0x1800066a1  sub     ebx, 1
0x1800066a4  jz      short loc_1800066D0
0x1800066a6  cmp     ebx, 1
0x1800066a9  jnz     loc_1800067F5
0x1800066af  call    ?StartServiceW@@YAHPEBG_NJ@Z; StartServiceW(ushort const *,bool,long)
0x1800066b4  cmp     eax, ebx
0x1800066b6  jz      loc_180006626
0x1800066bc  xor     bl, bl
0x1800066be  mov     edx, 47Eh; int
0x1800066c3  mov     rcx, rdi; HWND
0x1800066c6  call    ?ShowFailDlg@SecurityLogicControl@@SAHPEAUHWND__@@H@Z; SecurityLogicControl::ShowFailDlg(HWND__ *,int)
0x1800066cb  jmp     loc_180006626
0x1800066d0  call    ?OnRestart@@YA_NXZ; OnRestart(void)
0x1800066d5  test    al, al
0x1800066d7  jnz     loc_180006621
0x1800066dd  mov     edx, 482h
0x1800066e2  jmp     loc_180006615
0x1800066e7  lea     rcx, [rsp+88h+var_38]
0x1800066ec  mov     [rsp+88h+var_38], 0
0x1800066f4  call    cs:__imp_wscLuaSettingsFix
0x1800066fa  test    eax, eax
0x1800066fc  jnz     short loc_180006731
0x1800066fe  lea     ebx, [rax+1]
0x180006701  cmp     [rsp+88h+var_38], eax
0x180006705  jz      loc_180006626
0x18000670b  mov     rcx, rdi; HWND
0x18000670e  call    ?PromptUserReboot@SecurityLogicControl@@SAHPEAUHWND__@@@Z; SecurityLogicControl::PromptUserReboot(HWND__ *)
0x180006713  test    eax, eax
0x180006715  jz      loc_180006626
0x18000671b  mov     r9b, bl
0x18000671e  lea     edx, [rbx+75h]
0x180006721  xor     r8d, r8d
0x180006724  mov     rcx, rdi
0x180006727  call    ?ExecuteSecurityActionHandler@@YA_NPEAUHWND__@@W4SecurityAction@@PEAVSecurityLogicState@@_N@Z; ExecuteSecurityActionHandler(HWND__ *,SecurityAction,SecurityLogicState *,bool)
0x18000672c  jmp     loc_180006626
0x180006731  mov     edx, 481h
0x180006736  jmp     loc_180006615
0x18000673b  lea     rdx, a1; "1"
0x180006742  lea     rcx, aMicrosoftInter; "Microsoft.InternetOptions"
0x180006749  call    ?LaunchCpl@@YA_NPEBG0@Z; LaunchCpl(ushort const *,ushort const *)
0x18000674e  jmp     loc_180006AB5
0x180006753  call    cs:__imp_wscIeSettingsFix
0x180006759  test    eax, eax
0x18000675b  jz      loc_180006621
0x180006761  mov     edx, 480h
0x180006766  jmp     loc_180006615
0x18000676b  xor     edx, edx
0x18000676d  lea     rcx, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x180006774  jmp     short loc_180006749
0x180006776  sub     ebx, 79h ; 'y'
0x180006779  jz      short loc_1800067B7
0x18000677b  sub     ebx, 1
0x18000677e  jz      short loc_1800067A7
0x180006780  sub     ebx, 1
0x180006783  jz      short loc_180006793
0x180006785  cmp     ebx, 1
0x180006788  jnz     short loc_1800067F5
0x18000678a  lea     rdx, aMshelpWindowsI_0; "mshelp://windows/?id=31d797aa-091d-4d67"...
0x180006791  jmp     short loc_18000679A
0x180006793  lea     rdx, aMshelpWindowsI_1; "mshelp://windows/?id=bfe523a9-7eec-4d3f"...
0x18000679a  mov     rcx, rdi; HWND
0x18000679d  call    ?LaunchURL@@YA_NPEAUHWND__@@PEBG@Z; LaunchURL(HWND__ *,ushort const *)
0x1800067a2  jmp     loc_180006AB5
0x1800067a7  mov     rdx, rsi; struct SecurityLogicState *
0x1800067aa  mov     rcx, rdi; HWND
0x1800067ad  call    ?handlerLaunchThirdPartyDirect@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z; handlerLaunchThirdPartyDirect(HWND__ *,SecurityLogicState *)
0x1800067b2  jmp     loc_180006AB5
0x1800067b7  mov     rdx, rsi; struct SecurityLogicState *
0x1800067ba  mov     rcx, rdi; HWND
0x1800067bd  call    ?handlerLaunchThirdParty@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z; handlerLaunchThirdParty(HWND__ *,SecurityLogicState *)
0x1800067c2  jmp     loc_180006AB5
0x1800067c7  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x1800067d0  lea     r8, ?DisableAMsEnableDefender@@YAJXZ; lpStartAddress
0x1800067d7  xor     r9d, r9d; lpParameter
0x1800067da  mov     [rsp+88h+dwCreationFlags], 0; dwCreationFlags
0x1800067e2  xor     edx, edx; dwStackSize
0x1800067e4  xor     ecx, ecx; lpThreadAttributes
0x1800067e6  call    cs:__imp_CreateThread
0x1800067ec  mov     rcx, rax; hObject
0x1800067ef  call    cs:__imp_CloseHandle
0x1800067f5  mov     eax, 1
0x1800067fa  jmp     loc_180006AB5
0x1800067ff  mov     eax, 8Ah
0x180006804  cmp     ebx, eax
0x180006806  jg      loc_18000693F
0x18000680c  jz      loc_180006933
0x180006812  mov     eax, 85h
0x180006817  cmp     ebx, eax
0x180006819  jg      loc_1800068C0
0x18000681f  jz      loc_1800068AE
0x180006825  sub     ebx, 7Fh
0x180006828  jz      short loc_18000688A
0x18000682a  sub     ebx, 1
0x18000682d  jz      short loc_180006866
0x18000682f  sub     ebx, 2
0x180006832  jz      short loc_18000685A
0x180006834  sub     ebx, 1
0x180006837  jz      short loc_18000684E
0x180006839  cmp     ebx, 1
0x18000683c  jnz     short loc_1800067F5
0x18000683e  lea     r9d, [rbx+2]
0x180006842  lea     r8, unk_18000FD00
0x180006849  jmp     loc_180006A8E
0x18000684e  lea     r8, unk_18000FD20
0x180006855  jmp     loc_180006A88
0x18000685a  lea     r8, unk_18000FD30
0x180006861  jmp     loc_180006A88
0x180006866  mov     [rsp+88h+lpThreadId], 4A1h
0x18000686f  lea     r8, unk_18000FD70
0x180006876  mov     qword ptr [rsp+88h+dwCreationFlags], 41Bh
0x18000687f  mov     r9d, 3
0x180006885  jmp     loc_180006AA0
0x18000688a  mov     [rsp+88h+lpThreadId], 4A1h
0x180006893  lea     r8, unk_18000FD90
0x18000689a  mov     qword ptr [rsp+88h+dwCreationFlags], 41Bh
0x1800068a3  mov     r9d, 3
0x1800068a9  jmp     loc_180006AA0
0x1800068ae  mov     r9d, 3
0x1800068b4  lea     r8, unk_18000FCE0
0x1800068bb  jmp     loc_180006A8E
0x1800068c0  sub     ebx, 86h
0x1800068c6  jz      short loc_180006921
0x1800068c8  sub     ebx, 1
0x1800068cb  jz      short loc_18000690F
0x1800068cd  sub     ebx, 1
0x1800068d0  jz      short loc_1800068FD
0x1800068d2  cmp     ebx, 1
0x1800068d5  jnz     loc_1800067F5
0x1800068db  mov     [rsp+88h+lpThreadId], 4A3h
0x1800068e4  lea     r9d, [rbx+1]
0x1800068e8  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x1800068f1  lea     r8, unk_18000FC20
0x1800068f8  jmp     loc_180006AA0
0x1800068fd  mov     r9d, 3
0x180006903  lea     r8, unk_18000FC80
0x18000690a  jmp     loc_180006A8E
0x18000690f  mov     r9d, 3
0x180006915  lea     r8, unk_18000FCA0
0x18000691c  jmp     loc_180006A8E
0x180006921  mov     r9d, 3
0x180006927  lea     r8, unk_18000FCC0
0x18000692e  jmp     loc_180006A8E
0x180006933  lea     r8, unk_18000FD60
0x18000693a  jmp     loc_180006A88
0x18000693f  sub     ebx, 8Bh
0x180006945  jz      loc_180006A81
0x18000694b  sub     ebx, 1
0x18000694e  jz      loc_180006A78
0x180006954  sub     ebx, 1
0x180006957  jz      loc_180006A57
0x18000695d  sub     ebx, 1
0x180006960  jz      loc_180006A36
0x180006966  sub     ebx, 1
0x180006969  jz      loc_180006A15
0x18000696f  sub     ebx, 1
0x180006972  jz      short loc_1800069F1
0x180006974  sub     ebx, 1
0x180006977  jz      short loc_1800069CD
0x180006979  sub     ebx, 1
0x18000697c  jz      short loc_1800069A9
0x18000697e  cmp     ebx, 1
0x180006981  jnz     loc_1800067F5
0x180006987  mov     [rsp+88h+lpThreadId], 4A0h
0x180006990  lea     r9d, [rbx+1]
0x180006994  mov     qword ptr [rsp+88h+dwCreationFlags], 41Eh
0x18000699d  lea     r8, aS; "s"
0x1800069a4  jmp     loc_180006AA0
0x1800069a9  mov     [rsp+88h+lpThreadId], 4A3h
0x1800069b2  lea     r8, unk_18000FB70
0x1800069b9  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x1800069c2  mov     r9d, 3
0x1800069c8  jmp     loc_180006AA0
0x1800069cd  mov     [rsp+88h+lpThreadId], 4A3h
0x1800069d6  lea     r8, unk_18000FB90
0x1800069dd  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x1800069e6  mov     r9d, 3
0x1800069ec  jmp     loc_180006AA0
0x1800069f1  mov     [rsp+88h+lpThreadId], 4A3h
0x1800069fa  lea     r8, unk_18000FBB0
0x180006a01  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x180006a0a  mov     r9d, 3
0x180006a10  jmp     loc_180006AA0
0x180006a15  mov     [rsp+88h+lpThreadId], 4A3h
0x180006a1e  lea     r8, unk_18000FBD0
0x180006a25  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x180006a2e  mov     r9d, 3
0x180006a34  jmp     short loc_180006AA0
0x180006a36  mov     [rsp+88h+lpThreadId], 4A3h
0x180006a3f  lea     r8, unk_18000FBF0
0x180006a46  mov     qword ptr [rsp+88h+dwCreationFlags], 41Dh
0x180006a4f  mov     r9d, 3
0x180006a55  jmp     short loc_180006AA0
0x180006a57  mov     [rsp+88h+lpThreadId], 4A3h
  ... truncated ...
```
