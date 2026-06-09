# NotificationServiceImpl::RenewSecondaryChannel(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,long)

- ea: `0x180072f00`
- end: `0x18007355e`
- name: `?RenewSecondaryChannel@NotificationServiceImpl@@UEAAJ_KPEBG111KKJ@Z`
- size: `1630`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *RandomBuffer, LPCWCH lpWideCharStr, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000af1c`
- `0x18000fddc`
- `0x18000fe54`
- `0x1800133b0`
- `0x18001c06c`
- `0x18001c4bc`
- `0x18001cc10`
- `0x1800694b8`
- `0x18006b000`
- `0x180072f00`
- `0x180075bac`
- `0x180096010`

## import_xrefs

- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073233`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073233`

## string_xrefs

- `0x180073017`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800730b5`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073153`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800731f1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800732db`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800733d8`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073473`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NotificationServiceImpl::RenewSecondaryChannel(
        WNPMessageGenerator **this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *RandomBuffer,
        LPCWCH lpWideCharStr,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  PVOID v13; // rcx
  const WCHAR *v14; // rdi
  const WCHAR *v15; // r14
  unsigned int v16; // ebx
  PVOID *v17; // rcx
  __int64 v18; // rdx
  char v19; // r15
  int v20; // edx
  int v21; // ecx
  int v22; // edi
  int v23; // eax
  int v24; // eax
  void *v25; // rcx
  char *v26; // rcx
  char *v27; // rcx
  char *v28; // rcx
  char *v29; // rcx
  int v31; // [rsp+20h] [rbp-89h]
  int v32; // [rsp+20h] [rbp-89h]
  unsigned int v33; // [rsp+20h] [rbp-89h]
  int v34; // [rsp+20h] [rbp-89h]
  void *v35; // [rsp+70h] [rbp-39h] BYREF
  char *v36; // [rsp+78h] [rbp-31h] BYREF
  char *v37; // [rsp+80h] [rbp-29h] BYREF
  char *v38; // [rsp+88h] [rbp-21h] BYREF
  char *v39; // [rsp+90h] [rbp-19h] BYREF
  void *v40; // [rsp+98h] [rbp-11h] BYREF
  char *v41; // [rsp+A0h] [rbp-9h] BYREF
  char v42; // [rsp+A8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]
  unsigned int v44; // [rsp+100h] [rbp+57h] BYREF
  int v45; // [rsp+108h] [rbp+5Fh]

  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  v14 = RandomBuffer;
  if ( !RandomBuffer )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  v15 = lpWideCharStr;
  if ( !lpWideCharStr )
    MicrosoftTelemetryAssertTriggeredNoArgs(v13);
  v37 = 0;
  v36 = 0;
  v39 = 0;
  v38 = 0;
  v35 = 0;
  v44 = 0;
  v45 = 0;
  v40 = &v37;
  v41 = 0;
  v42 = 1;
  v16 = WpnUtf16ToUtf8(a3, &v41);
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v40);
  if ( (v16 & 0x80000000) == 0 )
  {
    v40 = &v36;
    v41 = 0;
    v42 = 1;
    v16 = WpnUtf16ToUtf8(a4, &v41);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v40);
    if ( (v16 & 0x80000000) == 0 )
    {
      v40 = &v39;
      v41 = 0;
      v42 = 1;
      v16 = WpnUtf16ToUtf8(v14, &v41);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v40);
      if ( (v16 & 0x80000000) == 0 )
      {
        v40 = &v38;
        v41 = 0;
        v42 = 1;
        v16 = WpnUtf16ToUtf8(v15, &v41);
        wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v40);
        if ( (v16 & 0x80000000) == 0 )
        {
          RandomBuffer = 0;
          SystemFunction036(&RandomBuffer, 8u);
          v40 = &v35;
          v41 = 0;
          v42 = 1;
          v19 = a7;
          v16 = WNPMessageGenerator::GenerateSecondaryChannelRenewal(
                  this[16],
                  v37,
                  v36,
                  v39,
                  v38,
                  a7,
                  (unsigned __int64)RandomBuffer,
                  (unsigned __int8 **)&v41,
                  &v44);
          wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v40);
          if ( (v16 & 0x80000000) == 0 )
          {
            v22 = a9;
            if ( (byte_1800AFD82 & 0x10) != 0 )
              McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer(v21, v20, a9, (_DWORD)v37, (__int64)v36, v19);
            v33 = v44;
            v23 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, __int64, unsigned __int8 near **, const char *))(*(_QWORD *)this[14] + 48LL))(
                    this[14],
                    a2,
                    &WNPMessageGenerator::s_GetCommand,
                    "CHANNEL");
            v16 = v23;
            if ( v23 >= 0 )
            {
              v24 = NotificationServiceImpl::AddOutstandingRequest((__int64)this, (__int64)(this + 20), a2, v45, v22, 2);
              v16 = v24;
              if ( v24 >= 0 )
              {
LABEL_72:
                v17 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_73;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  173,
                  &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
                  (unsigned int)v24);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6C0,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                (const char *)v16,
                v34);
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  v18 = 174;
                  goto LABEL_71;
                }
                goto LABEL_73;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  171,
                  &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
                  (unsigned int)v23);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6B8,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                (const char *)v16,
                v33);
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  v18 = 172;
                  goto LABEL_71;
                }
                goto LABEL_73;
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x69F,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
              (const char *)v16,
              v32);
            v17 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v18 = 170;
                goto LABEL_71;
              }
              goto LABEL_73;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x691,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
            (const char *)v16,
            v31);
          v17 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v18 = 168;
              goto LABEL_71;
            }
            goto LABEL_73;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x68D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v16,
          v31);
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v18 = 166;
            goto LABEL_71;
          }
          goto LABEL_73;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x689,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v16,
        v31);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v18 = 164;
          goto LABEL_71;
        }
LABEL_73:
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 && *((_BYTE *)v17 + 25) >= 6u )
          WPP_SF_d(v17[2], 175, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v16,
      v31);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v18 = 162;
LABEL_71:
        WPP_SF_d(v17[2], v18, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
        goto LABEL_72;
      }
      goto LABEL_73;
    }
  }
  v25 = v35;
  v35 = 0;
  if ( v25 )
    MemoryFree(v25);
  v26 = v38;
  v38 = 0;
  if ( v26 )
    MemoryFree(v26);
  v27 = v39;
  v39 = 0;
  if ( v27 )
    MemoryFree(v27);
  v28 = v36;
  v36 = 0;
  if ( v28 )
    MemoryFree(v28);
  v29 = v37;
  v37 = 0;
  if ( v29 )
    MemoryFree(v29);
  return v16;
}

```

## disassembly

```asm
0x180072f00  mov     [rsp-8+arg_0], rbx
0x180072f05  push    rbp
0x180072f06  push    rsi
0x180072f07  push    rdi
0x180072f08  push    r12
0x180072f0a  push    r13
0x180072f0c  push    r14
0x180072f0e  push    r15
0x180072f10  lea     rbp, [rsp-7]
0x180072f15  sub     rsp, 0B0h
0x180072f1c  mov     r15, r9
0x180072f1f  mov     rbx, r8
0x180072f22  mov     rsi, rdx
0x180072f25  mov     r13, rcx
0x180072f28  lea     rax, WPP_GLOBAL_Control
0x180072f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f36  cmp     rcx, rax
0x180072f39  jz      short loc_180072F5F
0x180072f3b  test    byte ptr [rcx+1Ch], 2
0x180072f3f  jz      short loc_180072F5F
0x180072f41  cmp     byte ptr [rcx+19h], 6
0x180072f45  jb      short loc_180072F5F
0x180072f47  mov     edx, 0A0h
0x180072f4c  mov     r9, rsi
0x180072f4f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180072f56  mov     rcx, [rcx+10h]
0x180072f5a  call    WPP_SF_I
0x180072f5f  xor     r12d, r12d
0x180072f62  test    rbx, rbx
0x180072f65  jnz     short loc_180072F6C
0x180072f67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f6c  test    r15, r15
0x180072f6f  jnz     short loc_180072F76
0x180072f71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f76  mov     rdi, [rbp+37h+RandomBuffer]
0x180072f7a  test    rdi, rdi
0x180072f7d  jnz     short loc_180072F84
0x180072f7f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f84  mov     r14, [rbp+37h+lpWideCharStr]
0x180072f88  test    r14, r14
0x180072f8b  jnz     short loc_180072F92
0x180072f8d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f92  mov     [rbp+37h+var_60], r12
0x180072f96  mov     [rbp+37h+var_68], r12
0x180072f9a  mov     [rbp+37h+var_50], r12
0x180072f9e  mov     [rbp+37h+var_58], r12
0x180072fa2  mov     [rbp+37h+var_70], r12
0x180072fa6  mov     [rbp+37h+arg_10], r12d
0x180072faa  mov     [rbp+37h+arg_18], r12d
0x180072fae  lea     rax, [rbp+37h+var_60]
0x180072fb2  mov     [rbp+37h+var_48], rax
0x180072fb6  mov     [rbp+37h+var_40], r12
0x180072fba  mov     [rbp+37h+var_38], 1
0x180072fbe  lea     rdx, [rbp+37h+var_40]; char **
0x180072fc2  mov     rcx, rbx; lpWideCharStr
0x180072fc5  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180072fca  mov     ebx, eax
0x180072fcc  lea     rcx, [rbp+37h+var_48]
0x180072fd0  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180072fd5  test    ebx, ebx
0x180072fd7  jns     short loc_18007304C
0x180072fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fe0  lea     rdi, WPP_GLOBAL_Control
0x180072fe7  cmp     rcx, rdi
0x180072fea  jz      short loc_180073010
0x180072fec  test    byte ptr [rcx+1Ch], 2
0x180072ff0  jz      short loc_180073010
0x180072ff2  cmp     byte ptr [rcx+19h], 2
0x180072ff6  jb      short loc_180073010
0x180072ff8  mov     edx, 0A1h
0x180072ffd  mov     r9d, ebx
0x180073000  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073007  mov     rcx, [rcx+10h]
0x18007300b  call    WPP_SF_d
0x180073010  mov     rcx, [rbp+3Fh]; this
0x180073014  mov     r9d, ebx; char *
0x180073017  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007301e  mov     edx, 685h; void *
0x180073023  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073028  mov     rcx, cs:WPP_GLOBAL_Control
0x18007302f  cmp     rcx, rdi
0x180073032  jz      loc_1800734E7
0x180073038  test    byte ptr [rcx+1Ch], 80h
0x18007303c  jz      loc_1800734BE
0x180073042  mov     edx, 0A2h
0x180073047  jmp     loc_18007349B
0x18007304c  lea     rax, [rbp+37h+var_68]
0x180073050  mov     [rbp+37h+var_48], rax
0x180073054  mov     [rbp+37h+var_40], r12
0x180073058  mov     [rbp+37h+var_38], 1
0x18007305c  lea     rdx, [rbp+37h+var_40]; char **
0x180073060  mov     rcx, r15; lpWideCharStr
0x180073063  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180073068  mov     ebx, eax
0x18007306a  lea     rcx, [rbp+37h+var_48]
0x18007306e  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073073  test    ebx, ebx
0x180073075  jns     short loc_1800730EA
0x180073077  mov     rcx, cs:WPP_GLOBAL_Control
0x18007307e  lea     rdi, WPP_GLOBAL_Control
0x180073085  cmp     rcx, rdi
0x180073088  jz      short loc_1800730AE
0x18007308a  test    byte ptr [rcx+1Ch], 2
0x18007308e  jz      short loc_1800730AE
0x180073090  cmp     byte ptr [rcx+19h], 2
0x180073094  jb      short loc_1800730AE
0x180073096  mov     edx, 0A3h
0x18007309b  mov     r9d, ebx
0x18007309e  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800730a5  mov     rcx, [rcx+10h]
0x1800730a9  call    WPP_SF_d
0x1800730ae  mov     rcx, [rbp+3Fh]; this
0x1800730b2  mov     r9d, ebx; char *
0x1800730b5  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800730bc  mov     edx, 689h; void *
0x1800730c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800730c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800730cd  cmp     rcx, rdi
0x1800730d0  jz      loc_1800734E7
0x1800730d6  test    byte ptr [rcx+1Ch], 80h
0x1800730da  jz      loc_1800734BE
0x1800730e0  mov     edx, 0A4h
0x1800730e5  jmp     loc_18007349B
0x1800730ea  lea     rax, [rbp+37h+var_50]
0x1800730ee  mov     [rbp+37h+var_48], rax
0x1800730f2  mov     [rbp+37h+var_40], r12
0x1800730f6  mov     [rbp+37h+var_38], 1
0x1800730fa  lea     rdx, [rbp+37h+var_40]; char **
0x1800730fe  mov     rcx, rdi; lpWideCharStr
0x180073101  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180073106  mov     ebx, eax
0x180073108  lea     rcx, [rbp+37h+var_48]
0x18007310c  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073111  test    ebx, ebx
0x180073113  jns     short loc_180073188
0x180073115  mov     rcx, cs:WPP_GLOBAL_Control
0x18007311c  lea     rdi, WPP_GLOBAL_Control
0x180073123  cmp     rcx, rdi
0x180073126  jz      short loc_18007314C
0x180073128  test    byte ptr [rcx+1Ch], 2
0x18007312c  jz      short loc_18007314C
0x18007312e  cmp     byte ptr [rcx+19h], 2
0x180073132  jb      short loc_18007314C
0x180073134  mov     edx, 0A5h
0x180073139  mov     r9d, ebx
0x18007313c  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073143  mov     rcx, [rcx+10h]
0x180073147  call    WPP_SF_d
0x18007314c  mov     rcx, [rbp+3Fh]; this
0x180073150  mov     r9d, ebx; char *
0x180073153  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007315a  mov     edx, 68Dh; void *
0x18007315f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073164  mov     rcx, cs:WPP_GLOBAL_Control
0x18007316b  cmp     rcx, rdi
0x18007316e  jz      loc_1800734E7
0x180073174  test    byte ptr [rcx+1Ch], 80h
0x180073178  jz      loc_1800734BE
0x18007317e  mov     edx, 0A6h
0x180073183  jmp     loc_18007349B
0x180073188  lea     rax, [rbp+37h+var_58]
0x18007318c  mov     [rbp+37h+var_48], rax
0x180073190  mov     [rbp+37h+var_40], r12
0x180073194  mov     [rbp+37h+var_38], 1
0x180073198  lea     rdx, [rbp+37h+var_40]; char **
0x18007319c  mov     rcx, r14; lpWideCharStr
0x18007319f  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x1800731a4  mov     ebx, eax
0x1800731a6  lea     rcx, [rbp+37h+var_48]
0x1800731aa  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x1800731af  test    ebx, ebx
0x1800731b1  jns     short loc_180073226
0x1800731b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800731ba  lea     rdi, WPP_GLOBAL_Control
0x1800731c1  cmp     rcx, rdi
0x1800731c4  jz      short loc_1800731EA
0x1800731c6  test    byte ptr [rcx+1Ch], 2
0x1800731ca  jz      short loc_1800731EA
0x1800731cc  cmp     byte ptr [rcx+19h], 2
0x1800731d0  jb      short loc_1800731EA
0x1800731d2  mov     edx, 0A7h
0x1800731d7  mov     r9d, ebx
0x1800731da  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800731e1  mov     rcx, [rcx+10h]
0x1800731e5  call    WPP_SF_d
0x1800731ea  mov     rcx, [rbp+3Fh]; this
0x1800731ee  mov     r9d, ebx; char *
0x1800731f1  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800731f8  mov     edx, 691h; void *
0x1800731fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073202  mov     rcx, cs:WPP_GLOBAL_Control
0x180073209  cmp     rcx, rdi
0x18007320c  jz      loc_1800734E7
0x180073212  test    byte ptr [rcx+1Ch], 80h
0x180073216  jz      loc_1800734BE
0x18007321c  mov     edx, 0A8h
0x180073221  jmp     loc_18007349B
0x180073226  mov     [rbp+37h+RandomBuffer], r12
0x18007322a  mov     edx, 8; RandomBufferLength
0x18007322f  lea     rcx, [rbp+37h+RandomBuffer]; RandomBuffer
0x180073233  call    cs:__imp_SystemFunction036
0x180073239  mov     r14, [rbp+37h+RandomBuffer]
0x18007323d  lea     rax, [rbp+37h+var_70]
0x180073241  mov     [rbp+37h+var_48], rax
0x180073245  mov     [rbp+37h+var_40], r12
0x180073249  mov     [rbp+37h+var_38], 1
0x18007324d  mov     rax, [rbp+37h+var_58]
0x180073251  lea     rcx, [rbp+37h+arg_10]
0x180073255  mov     [rsp+0E0h+var_A0], rcx; unsigned int *
0x18007325a  lea     rcx, [rbp+37h+var_40]
0x18007325e  mov     [rsp+0E0h+var_A8], rcx; unsigned __int8 **
0x180073263  mov     [rsp+0E0h+var_B0], r14; unsigned __int64
0x180073268  mov     r15d, [rbp+37h+arg_30]
0x18007326c  mov     [rsp+0E0h+var_B8], r15d; unsigned int
0x180073271  mov     [rsp+0E0h+var_C0], rax; int
0x180073276  mov     r9, [rbp+37h+var_50]; char *
0x18007327a  mov     r8, [rbp+37h+var_68]; char *
0x18007327e  mov     rdx, [rbp+37h+var_60]; char *
0x180073282  mov     rcx, [r13+80h]; this
0x180073289  call    ?GenerateSecondaryChannelRenewal@WNPMessageGenerator@@QEAAJPEBD000K_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateSecondaryChannelRenewal(char const *,char const *,char const *,char const *,ulong,unsigned __int64,uchar * *,ulong *)
0x18007328e  mov     ebx, eax
0x180073290  lea     rcx, [rbp+37h+var_48]
0x180073294  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073299  test    ebx, ebx
0x18007329b  jns     short loc_180073310
0x18007329d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800732a4  lea     rdi, WPP_GLOBAL_Control
0x1800732ab  cmp     rcx, rdi
0x1800732ae  jz      short loc_1800732D4
0x1800732b0  test    byte ptr [rcx+1Ch], 2
0x1800732b4  jz      short loc_1800732D4
0x1800732b6  cmp     byte ptr [rcx+19h], 2
0x1800732ba  jb      short loc_1800732D4
0x1800732bc  mov     edx, 0A9h
0x1800732c1  mov     r9d, ebx
0x1800732c4  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800732cb  mov     rcx, [rcx+10h]
0x1800732cf  call    WPP_SF_d
0x1800732d4  mov     rcx, [rbp+3Fh]; this
0x1800732d8  mov     r9d, ebx; char *
0x1800732db  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800732e2  mov     edx, 69Fh; void *
0x1800732e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800732ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800732f3  cmp     rcx, rdi
0x1800732f6  jz      loc_1800734E7
0x1800732fc  test    byte ptr [rcx+1Ch], 80h
0x180073300  jz      loc_1800734BE
0x180073306  mov     edx, 0AAh
0x18007330b  jmp     loc_18007349B
0x180073310  mov     edi, [rbp+37h+arg_40]
0x180073316  test    cs:byte_1800AFD82, 10h
0x18007331d  jz      short loc_180073353
0x18007331f  mov     [rsp+0E0h+var_80], rsi
0x180073324  mov     rax, [rbp+37h+var_70]
0x180073328  mov     [rsp+0E0h+var_88], rax
0x18007332d  mov     eax, [rbp+37h+arg_10]
0x180073330  mov     [rsp+0E0h+var_90], eax
0x180073334  mov     [rsp+0E0h+var_98], r14
0x180073339  mov     [rsp+0E0h+var_B8], r15d
0x18007333e  mov     rax, [rbp+37h+var_68]
0x180073342  mov     [rsp+0E0h+var_C0], rax
0x180073347  mov     r9, [rbp+37h+var_60]
0x18007334b  mov     r8d, edi
0x18007334e  call    McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer
0x180073353  mov     rcx, [r13+70h]
0x180073357  mov     rdx, [rbp+37h+var_70]
0x18007335b  mov     r8d, [rbp+37h+arg_10]
0x18007335f  mov     rax, [rcx]
0x180073362  lea     r9, [rbp+37h+arg_18]
0x180073366  mov     [rsp+0E0h+var_A8], r9
0x18007336b  mov     [rsp+0E0h+var_B0], r12
0x180073370  mov     qword ptr [rsp+0E0h+var_B8], rdx
0x180073375  mov     dword ptr [rsp+0E0h+var_C0], r8d; int
0x18007337a  lea     r9, aChannel; "CHANNEL"
0x180073381  lea     r8, ?s_GetCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_GetCommand
0x180073388  mov     rdx, rsi
0x18007338b  mov     rax, [rax+30h]
0x18007338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073394  mov     ebx, eax
0x180073396  test    eax, eax
0x180073398  jns     short loc_18007340D
0x18007339a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733a1  lea     rdi, WPP_GLOBAL_Control
0x1800733a8  cmp     rcx, rdi
0x1800733ab  jz      short loc_1800733D1
0x1800733ad  test    byte ptr [rcx+1Ch], 2
0x1800733b1  jz      short loc_1800733D1
0x1800733b3  cmp     byte ptr [rcx+19h], 2
0x1800733b7  jb      short loc_1800733D1
0x1800733b9  mov     edx, 0ABh
0x1800733be  mov     r9d, eax
0x1800733c1  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800733c8  mov     rcx, [rcx+10h]
0x1800733cc  call    WPP_SF_d
0x1800733d1  mov     rcx, [rbp+3Fh]; this
0x1800733d5  mov     r9d, ebx; char *
0x1800733d8  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800733df  mov     edx, 6B8h; void *
0x1800733e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
