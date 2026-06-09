# PnPServices::Initialize(void)

- ea: `0x180025460`
- end: `0x180025576`
- name: `?Initialize@PnPServices@@YAJXZ`
- size: `278`
- prototype: `__int64 __fastcall(PnPServices *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18001b404`
- `0x18001c2d0`
- `0x18002441c`
- `0x1800244cc`
- `0x18002457c`
- `0x180024608`
- `0x180025460`
- `0x180032c90`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x18002551e`
- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x18002551e`

## pseudocode

```c
__int64 __fastcall PnPServices::Initialize(PnPServices *this)
{
  signed int v1; // ecx
  struct CRegisterNotificationOnAllInterfaces *v2; // rax
  struct CRegisterNotificationOnAllInterfaces *v3; // rbx
  __int64 v4; // rax
  int v6; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+24h] [rbp-34h]
  GUID v8; // [rsp+2Ch] [rbp-2Ch]
  int v9; // [rsp+3Ch] [rbp-1Ch]

  v1 = CCritSectWithResource<CDummyResource>::Init(&PnPServices::g_csRegistration);
  if ( v1 >= 0 )
  {
    v1 = CreateHelperAndInit<CNamedElemList<PnPServices::CHandleNotif>>();
    if ( v1 >= 0 )
    {
      v1 = CreateHelperAndInit<CNamedElemList<PnPServices::CInterfaceNotif>>();
      if ( v1 >= 0 )
      {
        v2 = (struct CRegisterNotificationOnAllInterfaces *)operator new(0x10u);
        v3 = v2;
        if ( v2 )
        {
          *((_QWORD *)v2 + 1) = 0;
          PnPServices::g_prnoaiPnPNotifForAllInterfaces = v2;
          *(_QWORD *)v2 = &CRegisterNotificationOnAllInterfaces::`vftable';
          v7 = 5;
          v9 = 0;
          v6 = 32;
          v8 = guidInvalid;
          v4 = I_ScRegisterDeviceNotification(
                 *(&CRegisterNotification::_hfr + 1),
                 &v6,
                 5 - (unsigned int)(CRegisterNotification::_hfr != 1));
          *((_QWORD *)v3 + 1) = v4;
          v1 = v4 == 0 ? 0x80004005 : 0;
          if ( v4 )
          {
            v1 = CreateHelperAndInit<CMostRecentEvents<PnPServices::CPnPInterfaceEvent,20>>();
            if ( v1 >= 0 )
              return (unsigned int)CreateHelperAndInit<CMostRecentEvents<PnPServices::CPnPDeviceEvent,20>>();
          }
        }
        else
        {
          PnPServices::g_prnoaiPnPNotifForAllInterfaces = 0;
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180025460  push    rbx
0x180025462  sub     rsp, 50h
0x180025466  mov     rax, cs:__security_cookie
0x18002546d  xor     rax, rsp
0x180025470  mov     [rsp+58h+var_18], rax
0x180025475  lea     rcx, ?g_csRegistration@PnPServices@@3VCCritSect@@A; CCritSect PnPServices::g_csRegistration
0x18002547c  call    ?Init@?$CCritSectWithResource@VCDummyResource@@@@QEAAJXZ; CCritSectWithResource<CDummyResource>::Init(void)
0x180025481  mov     ecx, eax
0x180025483  test    eax, eax
0x180025485  js      loc_180025561
0x18002548b  call    ??$CreateHelperAndInit@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@YAJPEAPEAV?$CNamedElemList@VCHandleNotif@PnPServices@@@@@Z; CreateHelperAndInit<CNamedElemList<PnPServices::CHandleNotif>>(CNamedElemList<PnPServices::CHandleNotif> * *)
0x180025490  mov     ecx, eax
0x180025492  test    eax, eax
0x180025494  js      loc_180025561
0x18002549a  call    ??$CreateHelperAndInit@V?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@@@YAJPEAPEAV?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@@Z; CreateHelperAndInit<CNamedElemList<PnPServices::CInterfaceNotif>>(CNamedElemList<PnPServices::CInterfaceNotif> * *)
0x18002549f  mov     ecx, eax
0x1800254a1  test    eax, eax
0x1800254a3  js      loc_180025561
0x1800254a9  mov     ecx, 10h; Size
0x1800254ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800254b3  mov     rbx, rax
0x1800254b6  test    rax, rax
0x1800254b9  jz      loc_180025551
0x1800254bf  mov     qword ptr [rax+8], 0
0x1800254c7  lea     rdx, [rsp+58h+var_38]
0x1800254cc  lea     rax, ??_7CRegisterNotificationOnAllInterfaces@@6B@; const CRegisterNotificationOnAllInterfaces::`vftable'
0x1800254d3  mov     cs:?g_prnoaiPnPNotifForAllInterfaces@PnPServices@@3PEAVCRegisterNotificationOnAllInterfaces@@EA, rbx; CRegisterNotificationOnAllInterfaces * PnPServices::g_prnoaiPnPNotifForAllInterfaces
0x1800254da  mov     [rbx], rax
0x1800254dd  mov     eax, 1
0x1800254e2  sub     eax, dword ptr cs:?_hfr@CRegisterNotification@@1UHANDLEFORREGISTRATION@@A; HANDLEFORREGISTRATION CRegisterNotification::_hfr
0x1800254e8  movups  xmm0, xmmword ptr cs:?guidInvalid@@3U_GUID@@B.Data1; _GUID const guidInvalid ...
0x1800254ef  mov     rcx, qword ptr cs:?_hfr@CRegisterNotification@@1UHANDLEFORREGISTRATION@@A+8; HANDLEFORREGISTRATION CRegisterNotification::_hfr
0x1800254f6  neg     eax
0x1800254f8  mov     [rsp+58h+var_34], 5
0x180025501  sbb     r8d, r8d
0x180025504  mov     [rsp+58h+var_1C], 0
0x18002550c  add     r8d, 5
0x180025510  mov     [rsp+58h+var_38], 20h ; ' '
0x180025518  movdqu  [rsp+58h+var_2C], xmm0
0x18002551e  call    cs:__imp_I_ScRegisterDeviceNotification
0x180025524  mov     rcx, rax
0x180025527  mov     [rbx+8], rax
0x18002552b  neg     rcx
0x18002552e  sbb     ecx, ecx
0x180025530  not     ecx
0x180025532  and     ecx, 80004005h
0x180025538  test    rax, rax
0x18002553b  jz      short loc_180025561
0x18002553d  call    ??$CreateHelperAndInit@V?$CMostRecentEvents@VCPnPInterfaceEvent@PnPServices@@$0BE@@@@@YAJPEAPEAV?$CMostRecentEvents@VCPnPInterfaceEvent@PnPServices@@$0BE@@@@Z; CreateHelperAndInit<CMostRecentEvents<PnPServices::CPnPInterfaceEvent,20>>(CMostRecentEvents<PnPServices::CPnPInterfaceEvent,20> * *)
0x180025542  mov     ecx, eax
0x180025544  test    eax, eax
0x180025546  js      short loc_180025561
0x180025548  call    ??$CreateHelperAndInit@V?$CMostRecentEvents@VCPnPDeviceEvent@PnPServices@@$0BE@@@@@YAJPEAPEAV?$CMostRecentEvents@VCPnPDeviceEvent@PnPServices@@$0BE@@@@Z; CreateHelperAndInit<CMostRecentEvents<PnPServices::CPnPDeviceEvent,20>>(CMostRecentEvents<PnPServices::CPnPDeviceEvent,20> * *)
0x18002554d  mov     ecx, eax
0x18002554f  jmp     short loc_180025561
0x180025551  mov     cs:?g_prnoaiPnPNotifForAllInterfaces@PnPServices@@3PEAVCRegisterNotificationOnAllInterfaces@@EA, 0; CRegisterNotificationOnAllInterfaces * PnPServices::g_prnoaiPnPNotifForAllInterfaces
0x18002555c  mov     ecx, 8007000Eh
0x180025561  mov     eax, ecx
0x180025563  mov     rcx, [rsp+58h+var_18]
0x180025568  xor     rcx, rsp; StackCookie
0x18002556b  call    __security_check_cookie
0x180025570  add     rsp, 50h
0x180025574  pop     rbx
0x180025575  retn
```
