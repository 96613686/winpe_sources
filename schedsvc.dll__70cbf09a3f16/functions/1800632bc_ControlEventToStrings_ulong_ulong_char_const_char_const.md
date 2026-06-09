# ControlEventToStrings(ulong,ulong,char const * &,char const * &)

- ea: `0x1800632bc`
- end: `0x180063545`
- name: `?ControlEventToStrings@@YAXKKAEAPEBD0@Z`
- size: `649`
- prototype: `void __fastcall(unsigned int, unsigned int, const char **, const char **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18003c5d0`
- `0x1800635b8`

## callees

- `0x1800632bc`

## string_xrefs

- `0x180063340`: `SERVICE_CONTROL_STOP`
- `0x180063334`: `SERVICE_CONTROL_PAUSE`
- `0x180063328`: `SERVICE_CONTROL_CONTINUE`
- `0x18006331c`: `SERVICE_CONTROL_INTERROGATE`
- `0x180063310`: `SERVICE_CONTROL_SHUTDOWN`
- `0x180063304`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x1800632f8`: `SERVICE_CONTROL_NETBINDADD`
- `0x18006334c`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x18006353a`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x180063531`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x180063528`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x18006351f`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x18006344d`: `SERVICE_CONTROL_POWEREVENT`
- `0x180063396`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x18006338a`: `UNKNOWN SERVICE CONTROL`

## pseudocode

```c
void __fastcall ControlEventToStrings(unsigned int a1, unsigned int a2, const char **a3, const char **a4)
{
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  const char *v10; // rax
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  const char *v24; // rax
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // edx
  unsigned int v33; // edx

  *a4 = (const char *)&qword_1800A4718;
  if ( a1 > 8 )
  {
    v11 = a1 - 9;
    if ( !v11 )
    {
      v10 = "SERVICE_CONTROL_NETBINDENABLE";
      goto LABEL_77;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v10 = "SERVICE_CONTROL_NETBINDDISABLE";
      goto LABEL_77;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v10 = "SERVICE_CONTROL_DEVICEEVENT";
      goto LABEL_77;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v10 = "SERVICE_CONTROL_HARDWAREPROFILECHANGE";
      goto LABEL_77;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
        goto LABEL_24;
      *a3 = "SERVICE_CONTROL_SESSIONCHANGE";
      v16 = a2 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                v21 = v20 - 1;
                if ( v21 )
                {
                  v22 = v21 - 1;
                  if ( v22 )
                  {
                    v23 = v22 - 1;
                    if ( v23 )
                    {
                      if ( v23 == 1 )
                        v24 = "WTS_SESSION_REMOTE_CONTROL";
                      else
                        v24 = "UNKNOWN SESSIONCHANGE";
                    }
                    else
                    {
                      v24 = "WTS_SESSION_UNLOCK";
                    }
                  }
                  else
                  {
                    v24 = "WTS_SESSION_LOCK";
                  }
                }
                else
                {
                  v24 = "WTS_SESSION_LOGOFF";
                }
              }
              else
              {
                v24 = "WTS_SESSION_LOGON";
              }
            }
            else
            {
              v24 = "WTS_REMOTE_DISCONNECT";
            }
          }
          else
          {
            v24 = "WTS_REMOTE_CONNECT";
          }
        }
        else
        {
          v24 = "WTS_CONSOLE_DISCONNECT";
        }
      }
      else
      {
        v24 = "WTS_CONSOLE_CONNECT";
      }
LABEL_72:
      *a4 = v24;
      return;
    }
    *a3 = "SERVICE_CONTROL_POWEREVENT";
    if ( a2 > 6 )
    {
      v29 = a2 - 7;
      if ( !v29 )
      {
        v24 = "PBT_APMRESUMESUSPEND";
        goto LABEL_72;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        v24 = "PBT_APMRESUMESTANDBY";
        goto LABEL_72;
      }
      v31 = v30 - 1;
      if ( !v31 )
      {
        v24 = "PBT_APMBATTERYLOW";
        goto LABEL_72;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
        v24 = "PBT_APMPOWERSTATUSCHANGE";
        goto LABEL_72;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        v24 = "PBT_APMOEMEVENT";
        goto LABEL_72;
      }
      if ( v33 == 7 )
      {
        v24 = "PBT_APMRESUMEAUTOMATIC";
        goto LABEL_72;
      }
    }
    else
    {
      if ( a2 == 6 )
      {
        v24 = "PBT_APMRESUMECRITICAL";
        goto LABEL_72;
      }
      if ( !a2 )
      {
        v24 = "PBT_APMQUERYSUSPEND";
        goto LABEL_72;
      }
      v25 = a2 - 1;
      if ( !v25 )
      {
        v24 = "PBT_APMQUERYSTANDBY";
        goto LABEL_72;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        v24 = "PBT_APMQUERYSUSPENDFAILED";
        goto LABEL_72;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v24 = "PBT_APMQUERYSTANDBYFAILED";
        goto LABEL_72;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        v24 = "PBT_APMSUSPEND";
        goto LABEL_72;
      }
      if ( v28 == 1 )
      {
        v24 = "PBT_APMSTANDBY";
        goto LABEL_72;
      }
    }
    v24 = "UNKNOWN POWEREVENT";
    goto LABEL_72;
  }
  if ( a1 == 8 )
  {
    v10 = "SERVICE_CONTROL_NETBINDREMOVE";
    goto LABEL_77;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v10 = "SERVICE_CONTROL_STOP";
    goto LABEL_77;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = "SERVICE_CONTROL_PAUSE";
    goto LABEL_77;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v10 = "SERVICE_CONTROL_CONTINUE";
    goto LABEL_77;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = "SERVICE_CONTROL_INTERROGATE";
    goto LABEL_77;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v10 = "SERVICE_CONTROL_SHUTDOWN";
    goto LABEL_77;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v10 = "SERVICE_CONTROL_PARAMCHANGE";
    goto LABEL_77;
  }
  if ( v9 != 1 )
  {
LABEL_24:
    v10 = "UNKNOWN SERVICE CONTROL";
    goto LABEL_77;
  }
  v10 = "SERVICE_CONTROL_NETBINDADD";
LABEL_77:
  *a3 = v10;
}

```

## disassembly

```asm
0x1800632bc  lea     rax, qword_1800A4718
0x1800632c3  mov     [r9], rax
0x1800632c6  cmp     ecx, 8
0x1800632c9  ja      loc_180063358
0x1800632cf  jz      short loc_18006334C
0x1800632d1  sub     ecx, 1
0x1800632d4  jz      short loc_180063340
0x1800632d6  sub     ecx, 1
0x1800632d9  jz      short loc_180063334
0x1800632db  sub     ecx, 1
0x1800632de  jz      short loc_180063328
0x1800632e0  sub     ecx, 1
0x1800632e3  jz      short loc_18006331C
0x1800632e5  sub     ecx, 1
0x1800632e8  jz      short loc_180063310
0x1800632ea  sub     ecx, 1
0x1800632ed  jz      short loc_180063304
0x1800632ef  cmp     ecx, 1
0x1800632f2  jnz     loc_18006338A
0x1800632f8  lea     rax, aServiceControl_6; "SERVICE_CONTROL_NETBINDADD"
0x1800632ff  jmp     loc_180063541
0x180063304  lea     rax, aServiceControl_12; "SERVICE_CONTROL_PARAMCHANGE"
0x18006330b  jmp     loc_180063541
0x180063310  lea     rax, aServiceControl_7; "SERVICE_CONTROL_SHUTDOWN"
0x180063317  jmp     loc_180063541
0x18006331c  lea     rax, aServiceControl_9; "SERVICE_CONTROL_INTERROGATE"
0x180063323  jmp     loc_180063541
0x180063328  lea     rax, aServiceControl_8; "SERVICE_CONTROL_CONTINUE"
0x18006332f  jmp     loc_180063541
0x180063334  lea     rax, aServiceControl_0; "SERVICE_CONTROL_PAUSE"
0x18006333b  jmp     loc_180063541
0x180063340  lea     rax, aServiceControl_2; "SERVICE_CONTROL_STOP"
0x180063347  jmp     loc_180063541
0x18006334c  lea     rax, aServiceControl_1; "SERVICE_CONTROL_NETBINDREMOVE"
0x180063353  jmp     loc_180063541
0x180063358  sub     ecx, 9
0x18006335b  jz      loc_18006353A
0x180063361  sub     ecx, 1
0x180063364  jz      loc_180063531
0x18006336a  sub     ecx, 1
0x18006336d  jz      loc_180063528
0x180063373  sub     ecx, 1
0x180063376  jz      loc_18006351F
0x18006337c  sub     ecx, 1
0x18006337f  jz      loc_18006344D
0x180063385  cmp     ecx, 1
0x180063388  jz      short loc_180063396
0x18006338a  lea     rax, aUnknownService; "UNKNOWN SERVICE CONTROL"
0x180063391  jmp     loc_180063541
0x180063396  lea     rax, aServiceControl; "SERVICE_CONTROL_SESSIONCHANGE"
0x18006339d  mov     [r8], rax
0x1800633a0  sub     edx, 1
0x1800633a3  jz      loc_180063441
0x1800633a9  sub     edx, 1
0x1800633ac  jz      loc_180063435
0x1800633b2  sub     edx, 1
0x1800633b5  jz      short loc_180063429
0x1800633b7  sub     edx, 1
0x1800633ba  jz      short loc_18006341D
0x1800633bc  sub     edx, 1
0x1800633bf  jz      short loc_180063411
0x1800633c1  sub     edx, 1
0x1800633c4  jz      short loc_180063405
0x1800633c6  sub     edx, 1
0x1800633c9  jz      short loc_1800633F9
0x1800633cb  sub     edx, 1
0x1800633ce  jz      short loc_1800633ED
0x1800633d0  cmp     edx, 1
0x1800633d3  jz      short loc_1800633E1
0x1800633d5  lea     rax, aUnknownSession; "UNKNOWN SESSIONCHANGE"
0x1800633dc  jmp     loc_18006351B
0x1800633e1  lea     rax, aWtsSessionRemo; "WTS_SESSION_REMOTE_CONTROL"
0x1800633e8  jmp     loc_18006351B
0x1800633ed  lea     rax, aWtsSessionUnlo; "WTS_SESSION_UNLOCK"
0x1800633f4  jmp     loc_18006351B
0x1800633f9  lea     rax, aWtsSessionLock; "WTS_SESSION_LOCK"
0x180063400  jmp     loc_18006351B
0x180063405  lea     rax, aWtsSessionLogo; "WTS_SESSION_LOGOFF"
0x18006340c  jmp     loc_18006351B
0x180063411  lea     rax, aWtsSessionLogo_0; "WTS_SESSION_LOGON"
0x180063418  jmp     loc_18006351B
0x18006341d  lea     rax, aWtsRemoteDisco; "WTS_REMOTE_DISCONNECT"
0x180063424  jmp     loc_18006351B
0x180063429  lea     rax, aWtsRemoteConne; "WTS_REMOTE_CONNECT"
0x180063430  jmp     loc_18006351B
0x180063435  lea     rax, aWtsConsoleDisc; "WTS_CONSOLE_DISCONNECT"
0x18006343c  jmp     loc_18006351B
0x180063441  lea     rax, aWtsConsoleConn; "WTS_CONSOLE_CONNECT"
0x180063448  jmp     loc_18006351B
0x18006344d  lea     rax, aServiceControl_5; "SERVICE_CONTROL_POWEREVENT"
0x180063454  mov     [r8], rax
0x180063457  cmp     edx, 6
0x18006345a  ja      short loc_1800634C0
0x18006345c  jz      short loc_1800634B7
0x18006345e  test    edx, edx
0x180063460  jz      short loc_1800634AE
0x180063462  sub     edx, 1
0x180063465  jz      short loc_1800634A5
0x180063467  sub     edx, 1
0x18006346a  jz      short loc_18006349C
0x18006346c  sub     edx, 1
0x18006346f  jz      short loc_180063493
0x180063471  sub     edx, 1
0x180063474  jz      short loc_180063487
0x180063476  cmp     edx, 1
0x180063479  jnz     short loc_1800634DE
0x18006347b  lea     rax, aPbtApmstandby; "PBT_APMSTANDBY"
0x180063482  jmp     loc_18006351B
0x180063487  lea     rax, aPbtApmsuspend; "PBT_APMSUSPEND"
0x18006348e  jmp     loc_18006351B
0x180063493  lea     rax, aPbtApmquerysta; "PBT_APMQUERYSTANDBYFAILED"
0x18006349a  jmp     short loc_18006351B
0x18006349c  lea     rax, aPbtApmquerysus; "PBT_APMQUERYSUSPENDFAILED"
0x1800634a3  jmp     short loc_18006351B
0x1800634a5  lea     rax, aPbtApmquerysta_0; "PBT_APMQUERYSTANDBY"
0x1800634ac  jmp     short loc_18006351B
0x1800634ae  lea     rax, aPbtApmquerysus_0; "PBT_APMQUERYSUSPEND"
0x1800634b5  jmp     short loc_18006351B
0x1800634b7  lea     rax, aPbtApmresumecr; "PBT_APMRESUMECRITICAL"
0x1800634be  jmp     short loc_18006351B
0x1800634c0  sub     edx, 7
0x1800634c3  jz      short loc_180063514
0x1800634c5  sub     edx, 1
0x1800634c8  jz      short loc_18006350B
0x1800634ca  sub     edx, 1
0x1800634cd  jz      short loc_180063502
0x1800634cf  sub     edx, 1
0x1800634d2  jz      short loc_1800634F9
0x1800634d4  sub     edx, 1
0x1800634d7  jz      short loc_1800634F0
0x1800634d9  cmp     edx, 7
0x1800634dc  jz      short loc_1800634E7
0x1800634de  lea     rax, aUnknownPowerev; "UNKNOWN POWEREVENT"
0x1800634e5  jmp     short loc_18006351B
0x1800634e7  lea     rax, aPbtApmresumeau; "PBT_APMRESUMEAUTOMATIC"
0x1800634ee  jmp     short loc_18006351B
0x1800634f0  lea     rax, aPbtApmoemevent; "PBT_APMOEMEVENT"
0x1800634f7  jmp     short loc_18006351B
0x1800634f9  lea     rax, aPbtApmpowersta; "PBT_APMPOWERSTATUSCHANGE"
0x180063500  jmp     short loc_18006351B
0x180063502  lea     rax, aPbtApmbatteryl; "PBT_APMBATTERYLOW"
0x180063509  jmp     short loc_18006351B
0x18006350b  lea     rax, aPbtApmresumest; "PBT_APMRESUMESTANDBY"
0x180063512  jmp     short loc_18006351B
0x180063514  lea     rax, aPbtApmresumesu; "PBT_APMRESUMESUSPEND"
0x18006351b  mov     [r9], rax
0x18006351e  retn
0x18006351f  lea     rax, aServiceControl_4; "SERVICE_CONTROL_HARDWAREPROFILECHANGE"
0x180063526  jmp     short loc_180063541
0x180063528  lea     rax, aServiceControl_11; "SERVICE_CONTROL_DEVICEEVENT"
0x18006352f  jmp     short loc_180063541
0x180063531  lea     rax, aServiceControl_10; "SERVICE_CONTROL_NETBINDDISABLE"
0x180063538  jmp     short loc_180063541
0x18006353a  lea     rax, aServiceControl_3; "SERVICE_CONTROL_NETBINDENABLE"
0x180063541  mov     [r8], rax
0x180063544  retn
```
