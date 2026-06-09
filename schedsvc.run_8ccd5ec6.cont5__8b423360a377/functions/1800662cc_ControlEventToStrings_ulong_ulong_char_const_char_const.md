# ControlEventToStrings(ulong,ulong,char const * &,char const * &)

- ea: `0x1800662cc`
- end: `0x180066556`
- name: `?ControlEventToStrings@@YAXKKAEAPEBD0@Z`
- size: `650`
- prototype: `void __fastcall(unsigned int, unsigned int, const char **, const char **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18003e250`
- `0x1800665d4`

## callees

- `0x1800662cc`

## string_xrefs

- `0x180066350`: `SERVICE_CONTROL_STOP`
- `0x180066344`: `SERVICE_CONTROL_PAUSE`
- `0x180066338`: `SERVICE_CONTROL_CONTINUE`
- `0x18006632c`: `SERVICE_CONTROL_INTERROGATE`
- `0x180066320`: `SERVICE_CONTROL_SHUTDOWN`
- `0x180066314`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x180066308`: `SERVICE_CONTROL_NETBINDADD`
- `0x18006635c`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x18006654b`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x180066542`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x180066539`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x180066530`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x18006645d`: `SERVICE_CONTROL_POWEREVENT`
- `0x1800663a6`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x18006639a`: `UNKNOWN SERVICE CONTROL`

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

  *a4 = (const char *)&qword_1800A8718;
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
0x1800662cc  lea     rax, qword_1800A8718
0x1800662d3  mov     [r9], rax
0x1800662d6  cmp     ecx, 8
0x1800662d9  ja      loc_180066368
0x1800662df  jz      short loc_18006635C
0x1800662e1  sub     ecx, 1
0x1800662e4  jz      short loc_180066350
0x1800662e6  sub     ecx, 1
0x1800662e9  jz      short loc_180066344
0x1800662eb  sub     ecx, 1
0x1800662ee  jz      short loc_180066338
0x1800662f0  sub     ecx, 1
0x1800662f3  jz      short loc_18006632C
0x1800662f5  sub     ecx, 1
0x1800662f8  jz      short loc_180066320
0x1800662fa  sub     ecx, 1
0x1800662fd  jz      short loc_180066314
0x1800662ff  cmp     ecx, 1
0x180066302  jnz     loc_18006639A
0x180066308  lea     rax, aServiceControl_6; "SERVICE_CONTROL_NETBINDADD"
0x18006630f  jmp     loc_180066552
0x180066314  lea     rax, aServiceControl_12; "SERVICE_CONTROL_PARAMCHANGE"
0x18006631b  jmp     loc_180066552
0x180066320  lea     rax, aServiceControl_7; "SERVICE_CONTROL_SHUTDOWN"
0x180066327  jmp     loc_180066552
0x18006632c  lea     rax, aServiceControl_9; "SERVICE_CONTROL_INTERROGATE"
0x180066333  jmp     loc_180066552
0x180066338  lea     rax, aServiceControl_8; "SERVICE_CONTROL_CONTINUE"
0x18006633f  jmp     loc_180066552
0x180066344  lea     rax, aServiceControl_0; "SERVICE_CONTROL_PAUSE"
0x18006634b  jmp     loc_180066552
0x180066350  lea     rax, aServiceControl_2; "SERVICE_CONTROL_STOP"
0x180066357  jmp     loc_180066552
0x18006635c  lea     rax, aServiceControl_1; "SERVICE_CONTROL_NETBINDREMOVE"
0x180066363  jmp     loc_180066552
0x180066368  sub     ecx, 9
0x18006636b  jz      loc_18006654B
0x180066371  sub     ecx, 1
0x180066374  jz      loc_180066542
0x18006637a  sub     ecx, 1
0x18006637d  jz      loc_180066539
0x180066383  sub     ecx, 1
0x180066386  jz      loc_180066530
0x18006638c  sub     ecx, 1
0x18006638f  jz      loc_18006645D
0x180066395  cmp     ecx, 1
0x180066398  jz      short loc_1800663A6
0x18006639a  lea     rax, aUnknownService; "UNKNOWN SERVICE CONTROL"
0x1800663a1  jmp     loc_180066552
0x1800663a6  lea     rax, aServiceControl; "SERVICE_CONTROL_SESSIONCHANGE"
0x1800663ad  mov     [r8], rax
0x1800663b0  sub     edx, 1
0x1800663b3  jz      loc_180066451
0x1800663b9  sub     edx, 1
0x1800663bc  jz      loc_180066445
0x1800663c2  sub     edx, 1
0x1800663c5  jz      short loc_180066439
0x1800663c7  sub     edx, 1
0x1800663ca  jz      short loc_18006642D
0x1800663cc  sub     edx, 1
0x1800663cf  jz      short loc_180066421
0x1800663d1  sub     edx, 1
0x1800663d4  jz      short loc_180066415
0x1800663d6  sub     edx, 1
0x1800663d9  jz      short loc_180066409
0x1800663db  sub     edx, 1
0x1800663de  jz      short loc_1800663FD
0x1800663e0  cmp     edx, 1
0x1800663e3  jz      short loc_1800663F1
0x1800663e5  lea     rax, aUnknownSession; "UNKNOWN SESSIONCHANGE"
0x1800663ec  jmp     loc_18006652B
0x1800663f1  lea     rax, aWtsSessionRemo; "WTS_SESSION_REMOTE_CONTROL"
0x1800663f8  jmp     loc_18006652B
0x1800663fd  lea     rax, aWtsSessionUnlo; "WTS_SESSION_UNLOCK"
0x180066404  jmp     loc_18006652B
0x180066409  lea     rax, aWtsSessionLock; "WTS_SESSION_LOCK"
0x180066410  jmp     loc_18006652B
0x180066415  lea     rax, aWtsSessionLogo; "WTS_SESSION_LOGOFF"
0x18006641c  jmp     loc_18006652B
0x180066421  lea     rax, aWtsSessionLogo_0; "WTS_SESSION_LOGON"
0x180066428  jmp     loc_18006652B
0x18006642d  lea     rax, aWtsRemoteDisco; "WTS_REMOTE_DISCONNECT"
0x180066434  jmp     loc_18006652B
0x180066439  lea     rax, aWtsRemoteConne; "WTS_REMOTE_CONNECT"
0x180066440  jmp     loc_18006652B
0x180066445  lea     rax, aWtsConsoleDisc; "WTS_CONSOLE_DISCONNECT"
0x18006644c  jmp     loc_18006652B
0x180066451  lea     rax, aWtsConsoleConn; "WTS_CONSOLE_CONNECT"
0x180066458  jmp     loc_18006652B
0x18006645d  lea     rax, aServiceControl_5; "SERVICE_CONTROL_POWEREVENT"
0x180066464  mov     [r8], rax
0x180066467  cmp     edx, 6
0x18006646a  ja      short loc_1800664D0
0x18006646c  jz      short loc_1800664C7
0x18006646e  test    edx, edx
0x180066470  jz      short loc_1800664BE
0x180066472  sub     edx, 1
0x180066475  jz      short loc_1800664B5
0x180066477  sub     edx, 1
0x18006647a  jz      short loc_1800664AC
0x18006647c  sub     edx, 1
0x18006647f  jz      short loc_1800664A3
0x180066481  sub     edx, 1
0x180066484  jz      short loc_180066497
0x180066486  cmp     edx, 1
0x180066489  jnz     short loc_1800664EE
0x18006648b  lea     rax, aPbtApmstandby; "PBT_APMSTANDBY"
0x180066492  jmp     loc_18006652B
0x180066497  lea     rax, aPbtApmsuspend; "PBT_APMSUSPEND"
0x18006649e  jmp     loc_18006652B
0x1800664a3  lea     rax, aPbtApmquerysta; "PBT_APMQUERYSTANDBYFAILED"
0x1800664aa  jmp     short loc_18006652B
0x1800664ac  lea     rax, aPbtApmquerysus; "PBT_APMQUERYSUSPENDFAILED"
0x1800664b3  jmp     short loc_18006652B
0x1800664b5  lea     rax, aPbtApmquerysta_0; "PBT_APMQUERYSTANDBY"
0x1800664bc  jmp     short loc_18006652B
0x1800664be  lea     rax, aPbtApmquerysus_0; "PBT_APMQUERYSUSPEND"
0x1800664c5  jmp     short loc_18006652B
0x1800664c7  lea     rax, aPbtApmresumecr; "PBT_APMRESUMECRITICAL"
0x1800664ce  jmp     short loc_18006652B
0x1800664d0  sub     edx, 7
0x1800664d3  jz      short loc_180066524
0x1800664d5  sub     edx, 1
0x1800664d8  jz      short loc_18006651B
0x1800664da  sub     edx, 1
0x1800664dd  jz      short loc_180066512
0x1800664df  sub     edx, 1
0x1800664e2  jz      short loc_180066509
0x1800664e4  sub     edx, 1
0x1800664e7  jz      short loc_180066500
0x1800664e9  cmp     edx, 7
0x1800664ec  jz      short loc_1800664F7
0x1800664ee  lea     rax, aUnknownPowerev; "UNKNOWN POWEREVENT"
0x1800664f5  jmp     short loc_18006652B
0x1800664f7  lea     rax, aPbtApmresumeau; "PBT_APMRESUMEAUTOMATIC"
0x1800664fe  jmp     short loc_18006652B
0x180066500  lea     rax, aPbtApmoemevent; "PBT_APMOEMEVENT"
0x180066507  jmp     short loc_18006652B
0x180066509  lea     rax, aPbtApmpowersta; "PBT_APMPOWERSTATUSCHANGE"
0x180066510  jmp     short loc_18006652B
0x180066512  lea     rax, aPbtApmbatteryl; "PBT_APMBATTERYLOW"
0x180066519  jmp     short loc_18006652B
0x18006651b  lea     rax, aPbtApmresumest; "PBT_APMRESUMESTANDBY"
0x180066522  jmp     short loc_18006652B
0x180066524  lea     rax, aPbtApmresumesu; "PBT_APMRESUMESUSPEND"
0x18006652b  mov     [r9], rax
0x18006652e  retn
0x180066530  lea     rax, aServiceControl_4; "SERVICE_CONTROL_HARDWAREPROFILECHANGE"
0x180066537  jmp     short loc_180066552
0x180066539  lea     rax, aServiceControl_11; "SERVICE_CONTROL_DEVICEEVENT"
0x180066540  jmp     short loc_180066552
0x180066542  lea     rax, aServiceControl_10; "SERVICE_CONTROL_NETBINDDISABLE"
0x180066549  jmp     short loc_180066552
0x18006654b  lea     rax, aServiceControl_3; "SERVICE_CONTROL_NETBINDENABLE"
0x180066552  mov     [r8], rax
0x180066555  retn
```
