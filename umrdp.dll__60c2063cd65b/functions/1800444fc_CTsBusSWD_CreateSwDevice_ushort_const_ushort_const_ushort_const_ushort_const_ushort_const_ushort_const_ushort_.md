# CTsBusSWD::CreateSwDevice(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,_GUID const &,_DEVPROPERTY *,ulong,ulong,HSWDEVICE__ * *,ushort *,ulong)

- ea: `0x1800444fc`
- end: `0x180044840`
- name: `?CreateSwDevice@CTsBusSWD@@KAJPEBG000000AEBU_GUID@@1PEAU_DEVPROPERTY@@KKPEAPEAUHSWDEVICE__@@PEAGK@Z`
- size: `836`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, struct _DEVPROPERTY *, unsigned int, unsigned int, struct HSWDEVICE__ **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180043fa0`
- `0x180044f00`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x180043ee4`
- `0x180044394`
- `0x1800444fc`
- `0x1800452f0`
- `0x180045358`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004457c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004457c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044562`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180044562`
- `CFGMGR32!SwDeviceCreate` at `0x180044676`
- `CFGMGR32!SwDeviceCreate` at `0x180044676`
- `CFGMGR32!SwDeviceInterfaceRegister` at `0x18004478f`
- `CFGMGR32!SwDeviceInterfaceRegister` at `0x18004478f`
- `CFGMGR32!SwDeviceSetAttributes` at `0x180044733`
- `CFGMGR32!SwDeviceSetAttributes` at `0x180044733`

## pseudocode

```c
__int64 __fastcall CTsBusSWD::CreateSwDevice(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const struct _GUID *a8,
        const struct _GUID *a9,
        struct _DEVPROPERTY *a10,
        unsigned int a11,
        unsigned int a12,
        struct HSWDEVICE__ **a13,
        unsigned __int16 *a14)
{
  struct HSWDEVICE__ **v14; // rdi
  const struct _GUID *v15; // rbx
  __int64 v20; // rax
  struct HSWDEVICE__ **EventW; // rax
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rax
  _QWORD v29[2]; // [rsp+40h] [rbp-69h] BYREF
  void *v30; // [rsp+50h] [rbp-59h]
  __int64 v31; // [rsp+58h] [rbp-51h]
  _QWORD v32[5]; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+88h] [rbp-21h]
  int v34; // [rsp+8Ch] [rbp-1Dh]
  const unsigned __int16 *v35; // [rsp+90h] [rbp-19h]
  const unsigned __int16 *v36; // [rsp+98h] [rbp-11h]
  __int64 v37; // [rsp+A0h] [rbp-9h]

  v14 = a13;
  v15 = 0;
  if ( !*a13 )
  {
    v20 = *(_QWORD *)&a9->Data1;
    if ( !*(_QWORD *)&a9->Data1 )
      v20 = *(_QWORD *)a9->Data4;
    if ( v20 )
      v15 = a9;
    EventW = (struct HSWDEVICE__ **)CreateEventW(0, 1, 0, 0);
    a13 = EventW;
    if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      LODWORD(v15) = LastError;
      if ( LastError > 0 )
        LODWORD(v15) = (unsigned __int16)LastError | 0x80070000;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_45;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 21;
LABEL_44:
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v24,
        WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids,
        CurrentThreadActivityIdPrefix,
        (_DWORD)v15);
      goto LABEL_45;
    }
    v30 = EventW;
    v32[3] = a5;
    v32[2] = a4;
    v29[0] = a14;
    v33 = a12 | 2;
    v29[1] = 200;
    v34 = 0;
    v35 = a6;
    v36 = a7;
    if ( !a3 )
      a3 = L"HTREE\\ROOT\\0";
    v31 = 0;
    v32[0] = 72;
    v32[1] = a1;
    v32[4] = v15;
    v37 = 0;
    LODWORD(v15) = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD *, _QWORD, struct _DEVPROPERTY *, void (*)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), _QWORD *, struct HSWDEVICE__ **))SwDeviceCreate)(
                     a2,
                     a3,
                     v32,
                     a11,
                     a10,
                     CTsBusSWD::CreateSwDeviceCallback,
                     v29,
                     v14);
    if ( (int)v15 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_45;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 22;
      goto LABEL_44;
    }
    LODWORD(v15) = CTsBusSWD::WaitForAsyncCreation(v30);
    if ( (int)v15 >= 0 )
    {
      LODWORD(v15) = v31;
      if ( (int)v31 >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove>::GetImpl'::`2'::impl) )
          LODWORD(v15) = SwDeviceSetAttributes(*v14, 1);
        if ( (a12 & 8) != 0 )
          goto LABEL_45;
        v27 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a8->Data1;
        if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a8->Data1 )
          v27 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a8->Data4;
        if ( !v27 )
        {
          LODWORD(v15) = 0;
          goto LABEL_45;
        }
        LODWORD(v15) = SwDeviceInterfaceRegister(*v14, a8, 0, 0, 0, 1, 0);
        if ( (int)v15 >= 0 )
          goto LABEL_45;
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
LABEL_22:
          CTsBusSWD::CleanupSwDeviceHandle(v14);
LABEL_45:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&a13);
          return (unsigned int)v15;
        }
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        v26 = 25;
      }
      else
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_22;
        }
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        v26 = 24;
      }
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_22;
      }
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      v26 = 23;
    }
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v26,
      WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids,
      v25,
      (_DWORD)v15);
    goto LABEL_22;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800444fc  push    rbp
0x1800444fe  push    rbx
0x1800444ff  push    rsi
0x180044500  push    rdi
0x180044501  push    r12
0x180044503  push    r14
0x180044505  push    r15
0x180044507  lea     rbp, [rsp-7]
0x18004450c  sub     rsp, 0B0h
0x180044513  mov     rdi, [rbp+37h+arg_60]
0x18004451a  xor     ebx, ebx
0x18004451c  mov     rsi, r9
0x18004451f  mov     r14, r8
0x180044522  mov     r15, rdx
0x180044525  mov     r12, rcx
0x180044528  cmp     [rdi], rbx
0x18004452b  jnz     loc_18004482C
0x180044531  mov     r9, [rbp+37h+arg_40]
0x180044538  mov     rax, [r9]
0x18004453b  sub     rax, cs:qword_180053818
0x180044542  jnz     short loc_18004454F
0x180044544  mov     rax, [r9+8]
0x180044548  sub     rax, cs:qword_180053820
0x18004454f  test    rax, rax
0x180044552  cmovnz  rbx, r9
0x180044556  xor     r9d, r9d; lpName
0x180044559  xor     r8d, r8d; bInitialState
0x18004455c  xor     ecx, ecx; lpEventAttributes
0x18004455e  lea     edx, [r9+1]; bManualReset
0x180044562  call    cs:__imp_CreateEventW
0x180044568  mov     [rbp+37h+arg_60], rax
0x18004456f  lea     rcx, [rax+1]
0x180044573  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18004457a  jnz     short loc_1800445CB
0x18004457c  call    cs:__imp_GetLastError
0x180044582  mov     ebx, eax
0x180044584  test    eax, eax
0x180044586  jle     short loc_180044591
0x180044588  movzx   ebx, ax
0x18004458b  or      ebx, 80070000h
0x180044591  mov     rcx, cs:WPP_GLOBAL_Control
0x180044598  lea     rax, WPP_GLOBAL_Control
0x18004459f  cmp     rcx, rax
0x1800445a2  jz      loc_180044820
0x1800445a8  test    byte ptr [rcx+1Ch], 1
0x1800445ac  jz      loc_180044820
0x1800445b2  cmp     byte ptr [rcx+19h], 2
0x1800445b6  jb      loc_180044820
0x1800445bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800445c1  mov     edx, 15h
0x1800445c6  jmp     loc_180044802
0x1800445cb  mov     rcx, [rbp+37h+arg_68]
0x1800445d2  lea     r8, [rbp+37h+var_80]
0x1800445d6  mov     r9d, [rbp+37h+arg_50]
0x1800445dd  mov     [rbp+37h+var_90], rax
0x1800445e1  mov     rax, [rbp+37h+arg_20]
0x1800445e5  mov     [rbp+37h+var_68], rax
0x1800445e9  mov     [rsp+0E0h+var_A8], rdi
0x1800445ee  mov     [rbp+37h+var_70], rsi
0x1800445f2  mov     esi, [rbp+37h+arg_58]
0x1800445f8  mov     eax, esi
0x1800445fa  or      eax, 2
0x1800445fd  mov     [rbp+37h+var_A0], rcx
0x180044601  mov     [rbp+37h+var_58], eax
0x180044604  mov     rcx, r15
0x180044607  xor     eax, eax
0x180044609  mov     [rbp+37h+var_98], 0C8h
0x180044611  mov     [rbp+37h+var_54], eax
0x180044614  test    r14, r14
0x180044617  mov     rax, [rbp+37h+arg_28]
0x18004461b  mov     [rbp+37h+var_50], rax
0x18004461f  mov     rax, [rbp+37h+arg_30]
0x180044623  mov     [rbp+37h+var_48], rax
0x180044627  lea     rax, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18004462e  cmovz   r14, rax
0x180044632  mov     [rbp+37h+var_88], 0
0x18004463a  lea     rax, [rbp+37h+var_A0]
0x18004463e  mov     [rbp+37h+var_80], 48h ; 'H'
0x180044646  mov     [rsp+0E0h+var_B0], rax
0x18004464b  mov     rdx, r14
0x18004464e  lea     rax, ?CreateSwDeviceCallback@CTsBusSWD@@KAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CTsBusSWD::CreateSwDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180044655  mov     [rbp+37h+var_78], r12
0x180044659  mov     [rsp+0E0h+var_B8], rax
0x18004465e  mov     rax, [rbp+37h+arg_48]
0x180044665  mov     [rsp+0E0h+var_C0], rax
0x18004466a  mov     [rbp+37h+var_60], rbx
0x18004466e  mov     [rbp+37h+var_40], 0
0x180044676  call    cs:__imp_SwDeviceCreate
0x18004467c  mov     ebx, eax
0x18004467e  test    eax, eax
0x180044680  js      loc_1800447D9
0x180044686  mov     rcx, [rbp+37h+var_90]; void *
0x18004468a  call    ?WaitForAsyncCreation@CTsBusSWD@@KAJPEAX@Z; CTsBusSWD::WaitForAsyncCreation(void *)
0x18004468f  mov     ebx, eax
0x180044691  test    eax, eax
0x180044693  jns     short loc_1800446E9
0x180044695  mov     rcx, cs:WPP_GLOBAL_Control
0x18004469c  lea     rax, WPP_GLOBAL_Control
0x1800446a3  cmp     rcx, rax
0x1800446a6  jz      short loc_1800446DC
0x1800446a8  test    byte ptr [rcx+1Ch], 1
0x1800446ac  jz      short loc_1800446DC
0x1800446ae  cmp     byte ptr [rcx+19h], 2
0x1800446b2  jb      short loc_1800446DC
0x1800446b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800446b9  mov     edx, 17h
0x1800446be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446c5  lea     r8, WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids
0x1800446cc  mov     r9d, eax
0x1800446cf  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800446d3  mov     rcx, [rcx+10h]
0x1800446d7  call    WPP_SF_Dd
0x1800446dc  mov     rcx, rdi; struct HSWDEVICE__ **
0x1800446df  call    ?CleanupSwDeviceHandle@CTsBusSWD@@KAXPEAPEAUHSWDEVICE__@@@Z; CTsBusSWD::CleanupSwDeviceHandle(HSWDEVICE__ * *)
0x1800446e4  jmp     loc_180044820
0x1800446e9  mov     ebx, dword ptr [rbp+37h+var_88]
0x1800446ec  test    ebx, ebx
0x1800446ee  jns     short loc_18004471B
0x1800446f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446f7  lea     rax, WPP_GLOBAL_Control
0x1800446fe  cmp     rcx, rax
0x180044701  jz      short loc_1800446DC
0x180044703  test    byte ptr [rcx+1Ch], 1
0x180044707  jz      short loc_1800446DC
0x180044709  cmp     byte ptr [rcx+19h], 2
0x18004470d  jb      short loc_1800446DC
0x18004470f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044714  mov     edx, 18h
0x180044719  jmp     short loc_1800446BE
0x18004471b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove> `wil::Feature<__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove>::GetImpl(void)'::`2'::impl
0x180044722  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDeviceUninstallOnRemove>::__private_IsEnabled(void)
0x180044727  test    al, al
0x180044729  jz      short loc_18004473B
0x18004472b  mov     rcx, [rdi]
0x18004472e  mov     edx, 1
0x180044733  call    cs:__imp_SwDeviceSetAttributes
0x180044739  mov     ebx, eax
0x18004473b  test    sil, 8
0x18004473f  jnz     loc_180044820
0x180044745  mov     rdx, [rbp+37h+arg_38]
0x180044749  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180044750  sub     rax, [rdx]
0x180044753  jnz     short loc_180044760
0x180044755  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18004475c  sub     rax, [rdx+8]
0x180044760  test    rax, rax
0x180044763  jnz     short loc_18004476C
0x180044765  xor     ebx, ebx
0x180044767  jmp     loc_180044820
0x18004476c  mov     rcx, [rdi]
0x18004476f  xor     r9d, r9d
0x180044772  mov     [rsp+0E0h+var_B0], 0
0x18004477b  xor     r8d, r8d
0x18004477e  mov     dword ptr [rsp+0E0h+var_B8], 1
0x180044786  mov     [rsp+0E0h+var_C0], 0
0x18004478f  call    cs:__imp_SwDeviceInterfaceRegister
0x180044795  mov     ebx, eax
0x180044797  test    eax, eax
0x180044799  jns     loc_180044820
0x18004479f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447a6  lea     rax, WPP_GLOBAL_Control
0x1800447ad  cmp     rcx, rax
0x1800447b0  jz      loc_1800446DC
0x1800447b6  test    byte ptr [rcx+1Ch], 1
0x1800447ba  jz      loc_1800446DC
0x1800447c0  cmp     byte ptr [rcx+19h], 2
0x1800447c4  jb      loc_1800446DC
0x1800447ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800447cf  mov     edx, 19h
0x1800447d4  jmp     loc_1800446BE
0x1800447d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447e0  lea     rax, WPP_GLOBAL_Control
0x1800447e7  cmp     rcx, rax
0x1800447ea  jz      short loc_180044820
0x1800447ec  test    byte ptr [rcx+1Ch], 1
0x1800447f0  jz      short loc_180044820
0x1800447f2  cmp     byte ptr [rcx+19h], 2
0x1800447f6  jb      short loc_180044820
0x1800447f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800447fd  mov     edx, 16h
0x180044802  mov     rcx, cs:WPP_GLOBAL_Control
0x180044809  lea     r8, WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids
0x180044810  mov     r9d, eax
0x180044813  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180044817  mov     rcx, [rcx+10h]
0x18004481b  call    WPP_SF_Dd
0x180044820  lea     rcx, [rbp+37h+arg_60]
0x180044827  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004482c  mov     eax, ebx
0x18004482e  add     rsp, 0B0h
0x180044835  pop     r15
0x180044837  pop     r14
0x180044839  pop     r12
0x18004483b  pop     rdi
0x18004483c  pop     rsi
0x18004483d  pop     rbx
0x18004483e  pop     rbp
0x18004483f  retn
```
