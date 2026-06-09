# NotificationServiceImpl::RequestSecondaryChannel(unsigned __int64,ushort const *,ushort const *,ushort const *,ulong,ulong,long)

- ea: `0x180073940`
- end: `0x180073eba`
- name: `?RequestSecondaryChannel@NotificationServiceImpl@@UEAAJ_KPEBG11KKJ@Z`
- size: `1402`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *RandomBuffer, unsigned int, unsigned int, int)`
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
- `0x18006971c`
- `0x18006b000`
- `0x180073940`
- `0x180075bac`
- `0x180096010`

## import_xrefs

- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073bae`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180073bae`

## string_xrefs

- `0x180073a3e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073ad5`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073b6c`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073c4d`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073d46`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180073de1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::RequestSecondaryChannel(
        WNPMessageGenerator **this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *RandomBuffer,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  PVOID v12; // rcx
  const WCHAR *v13; // rdi
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v16; // rdx
  char v17; // r12
  int v18; // edx
  int v19; // ecx
  int v20; // edi
  int v21; // eax
  int v22; // eax
  void *v23; // rcx
  char *v24; // rcx
  char *v25; // rcx
  char *v26; // rcx
  int v28; // [rsp+20h] [rbp-89h]
  int v29; // [rsp+20h] [rbp-89h]
  unsigned int v30; // [rsp+20h] [rbp-89h]
  void *v31; // [rsp+70h] [rbp-39h] BYREF
  char *v32; // [rsp+78h] [rbp-31h] BYREF
  char *v33; // [rsp+80h] [rbp-29h] BYREF
  char *v34; // [rsp+88h] [rbp-21h] BYREF
  void *v35; // [rsp+90h] [rbp-19h] BYREF
  char *v36; // [rsp+98h] [rbp-11h] BYREF
  char v37; // [rsp+A0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]
  unsigned int v39; // [rsp+100h] [rbp+57h] BYREF
  unsigned int v40; // [rsp+108h] [rbp+5Fh]

  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  v13 = RandomBuffer;
  if ( !RandomBuffer )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  v32 = 0;
  v34 = 0;
  v33 = 0;
  v31 = 0;
  v39 = 0;
  v40 = 0;
  v35 = &v32;
  v36 = 0;
  v37 = 1;
  v14 = WpnUtf16ToUtf8(a3, &v36);
  wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v35);
  if ( (v14 & 0x80000000) == 0 )
  {
    v35 = &v34;
    v36 = 0;
    v37 = 1;
    v14 = WpnUtf16ToUtf8(a4, &v36);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v35);
    if ( (v14 & 0x80000000) == 0 )
    {
      v35 = &v33;
      v36 = 0;
      v37 = 1;
      v14 = WpnUtf16ToUtf8(v13, &v36);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v35);
      if ( (v14 & 0x80000000) == 0 )
      {
        RandomBuffer = 0;
        SystemFunction036(&RandomBuffer, 8u);
        v35 = &v31;
        v36 = 0;
        v37 = 1;
        v17 = a6;
        v14 = WNPMessageGenerator::GenerateSecondaryChannelRequest(
                this[16],
                v32,
                v34,
                v33,
                a6,
                (unsigned __int64)RandomBuffer,
                (unsigned __int8 **)&v36,
                &v39);
        wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v35);
        if ( (v14 & 0x80000000) == 0 )
        {
          v20 = a8;
          if ( (byte_1800AFD82 & 0x10) != 0 )
            McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer(v19, v18, a8, 0, (__int64)v32, v17);
          v30 = v39;
          v21 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, __int64, unsigned __int8 near **, const char *))(*(_QWORD *)this[14] + 48LL))(
                  this[14],
                  a2,
                  &WNPMessageGenerator::s_GetCommand,
                  "CHANNEL");
          v14 = v21;
          if ( v21 >= 0 )
          {
            v22 = NotificationServiceImpl::AddOutstandingRequest(this, this + 20, a2, v40);
            v14 = v22;
            if ( v22 >= 0 )
            {
LABEL_62:
              v15 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_63;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                157,
                &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
                (unsigned int)v22);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x662,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
              (const char *)v14,
              v20);
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v16 = 158;
                goto LABEL_61;
              }
              goto LABEL_63;
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
                155,
                &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
                (unsigned int)v21);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x65A,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
              (const char *)v14,
              v30);
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v16 = 156;
                goto LABEL_61;
              }
              goto LABEL_63;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x642,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
            (const char *)v14,
            v29);
          v15 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v16 = 154;
              goto LABEL_61;
            }
            goto LABEL_63;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x635,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v14,
          v28);
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v16 = 152;
            goto LABEL_61;
          }
          goto LABEL_63;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x631,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v14,
        v28);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v16 = 150;
          goto LABEL_61;
        }
LABEL_63:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 6u )
          WPP_SF_d(v15[2], 159, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x62D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v14,
      v28);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v16 = 148;
LABEL_61:
        WPP_SF_d(v15[2], v16, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
        goto LABEL_62;
      }
      goto LABEL_63;
    }
  }
  v23 = v31;
  v31 = 0;
  if ( v23 )
    MemoryFree(v23);
  v24 = v33;
  v33 = 0;
  if ( v24 )
    MemoryFree(v24);
  v25 = v34;
  v34 = 0;
  if ( v25 )
    MemoryFree(v25);
  v26 = v32;
  v32 = 0;
  if ( v26 )
    MemoryFree(v26);
  return v14;
}

```

## disassembly

```asm
0x180073940  mov     [rsp-8+arg_0], rbx
0x180073945  push    rbp
0x180073946  push    rsi
0x180073947  push    rdi
0x180073948  push    r12
0x18007394a  push    r13
0x18007394c  push    r14
0x18007394e  push    r15
0x180073950  lea     rbp, [rsp-7]
0x180073955  sub     rsp, 0B0h
0x18007395c  mov     r14, r9
0x18007395f  mov     rbx, r8
0x180073962  mov     rsi, rdx
0x180073965  mov     r15, rcx
0x180073968  lea     r12, WPP_GLOBAL_Control
0x18007396f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073976  cmp     rcx, r12
0x180073979  jz      short loc_18007399F
0x18007397b  test    byte ptr [rcx+1Ch], 2
0x18007397f  jz      short loc_18007399F
0x180073981  cmp     byte ptr [rcx+19h], 6
0x180073985  jb      short loc_18007399F
0x180073987  mov     edx, 92h
0x18007398c  mov     r9, rsi
0x18007398f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073996  mov     rcx, [rcx+10h]
0x18007399a  call    WPP_SF_I
0x18007399f  xor     r13d, r13d
0x1800739a2  test    rbx, rbx
0x1800739a5  jnz     short loc_1800739AC
0x1800739a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800739ac  test    r14, r14
0x1800739af  jnz     short loc_1800739B6
0x1800739b1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800739b6  mov     rdi, [rbp+37h+RandomBuffer]
0x1800739ba  test    rdi, rdi
0x1800739bd  jnz     short loc_1800739C4
0x1800739bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800739c4  mov     [rbp+37h+var_68], r13
0x1800739c8  mov     [rbp+37h+var_58], r13
0x1800739cc  mov     [rbp+37h+var_60], r13
0x1800739d0  mov     [rbp+37h+var_70], r13
0x1800739d4  mov     [rbp+37h+arg_10], r13d
0x1800739d8  mov     [rbp+37h+arg_18], r13d
0x1800739dc  lea     rax, [rbp+37h+var_68]
0x1800739e0  mov     [rbp+37h+var_50], rax
0x1800739e4  mov     [rbp+37h+var_48], r13
0x1800739e8  mov     [rbp+37h+var_40], 1
0x1800739ec  lea     rdx, [rbp+37h+var_48]; char **
0x1800739f0  mov     rcx, rbx; lpWideCharStr
0x1800739f3  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x1800739f8  mov     ebx, eax
0x1800739fa  lea     rcx, [rbp+37h+var_50]
0x1800739fe  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073a03  test    ebx, ebx
0x180073a05  jns     short loc_180073A73
0x180073a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a0e  cmp     rcx, r12
0x180073a11  jz      short loc_180073A37
0x180073a13  test    byte ptr [rcx+1Ch], 2
0x180073a17  jz      short loc_180073A37
0x180073a19  cmp     byte ptr [rcx+19h], 2
0x180073a1d  jb      short loc_180073A37
0x180073a1f  mov     edx, 93h
0x180073a24  mov     r9d, ebx
0x180073a27  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073a2e  mov     rcx, [rcx+10h]
0x180073a32  call    WPP_SF_d
0x180073a37  mov     rcx, [rbp+3Fh]; this
0x180073a3b  mov     r9d, ebx; char *
0x180073a3e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073a45  mov     edx, 62Dh; void *
0x180073a4a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a56  cmp     rcx, r12
0x180073a59  jz      loc_180073E55
0x180073a5f  test    byte ptr [rcx+1Ch], 80h
0x180073a63  jz      loc_180073E2C
0x180073a69  mov     edx, 94h
0x180073a6e  jmp     loc_180073E09
0x180073a73  lea     rax, [rbp+37h+var_58]
0x180073a77  mov     [rbp+37h+var_50], rax
0x180073a7b  mov     [rbp+37h+var_48], r13
0x180073a7f  mov     [rbp+37h+var_40], 1
0x180073a83  lea     rdx, [rbp+37h+var_48]; char **
0x180073a87  mov     rcx, r14; lpWideCharStr
0x180073a8a  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180073a8f  mov     ebx, eax
0x180073a91  lea     rcx, [rbp+37h+var_50]
0x180073a95  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073a9a  test    ebx, ebx
0x180073a9c  jns     short loc_180073B0A
0x180073a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073aa5  cmp     rcx, r12
0x180073aa8  jz      short loc_180073ACE
0x180073aaa  test    byte ptr [rcx+1Ch], 2
0x180073aae  jz      short loc_180073ACE
0x180073ab0  cmp     byte ptr [rcx+19h], 2
0x180073ab4  jb      short loc_180073ACE
0x180073ab6  mov     edx, 95h
0x180073abb  mov     r9d, ebx
0x180073abe  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073ac5  mov     rcx, [rcx+10h]
0x180073ac9  call    WPP_SF_d
0x180073ace  mov     rcx, [rbp+3Fh]; this
0x180073ad2  mov     r9d, ebx; char *
0x180073ad5  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073adc  mov     edx, 631h; void *
0x180073ae1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180073aed  cmp     rcx, r12
0x180073af0  jz      loc_180073E55
0x180073af6  test    byte ptr [rcx+1Ch], 80h
0x180073afa  jz      loc_180073E2C
0x180073b00  mov     edx, 96h
0x180073b05  jmp     loc_180073E09
0x180073b0a  lea     rax, [rbp+37h+var_60]
0x180073b0e  mov     [rbp+37h+var_50], rax
0x180073b12  mov     [rbp+37h+var_48], r13
0x180073b16  mov     [rbp+37h+var_40], 1
0x180073b1a  lea     rdx, [rbp+37h+var_48]; char **
0x180073b1e  mov     rcx, rdi; lpWideCharStr
0x180073b21  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180073b26  mov     ebx, eax
0x180073b28  lea     rcx, [rbp+37h+var_50]
0x180073b2c  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073b31  test    ebx, ebx
0x180073b33  jns     short loc_180073BA1
0x180073b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b3c  cmp     rcx, r12
0x180073b3f  jz      short loc_180073B65
0x180073b41  test    byte ptr [rcx+1Ch], 2
0x180073b45  jz      short loc_180073B65
0x180073b47  cmp     byte ptr [rcx+19h], 2
0x180073b4b  jb      short loc_180073B65
0x180073b4d  mov     edx, 97h
0x180073b52  mov     r9d, ebx
0x180073b55  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073b5c  mov     rcx, [rcx+10h]
0x180073b60  call    WPP_SF_d
0x180073b65  mov     rcx, [rbp+3Fh]; this
0x180073b69  mov     r9d, ebx; char *
0x180073b6c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073b73  mov     edx, 635h; void *
0x180073b78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b84  cmp     rcx, r12
0x180073b87  jz      loc_180073E55
0x180073b8d  test    byte ptr [rcx+1Ch], 80h
0x180073b91  jz      loc_180073E2C
0x180073b97  mov     edx, 98h
0x180073b9c  jmp     loc_180073E09
0x180073ba1  mov     [rbp+37h+RandomBuffer], r13
0x180073ba5  mov     edx, 8; RandomBufferLength
0x180073baa  lea     rcx, [rbp+37h+RandomBuffer]; RandomBuffer
0x180073bae  call    cs:__imp_SystemFunction036
0x180073bb4  mov     r14, [rbp+37h+RandomBuffer]
0x180073bb8  lea     rax, [rbp+37h+var_70]
0x180073bbc  mov     [rbp+37h+var_50], rax
0x180073bc0  mov     [rbp+37h+var_48], r13
0x180073bc4  mov     [rbp+37h+var_40], 1
0x180073bc8  lea     rax, [rbp+37h+arg_10]
0x180073bcc  mov     [rsp+0E0h+var_A8], rax; unsigned int *
0x180073bd1  lea     rax, [rbp+37h+var_48]
0x180073bd5  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 **
0x180073bda  mov     [rsp+0E0h+var_B8], r14; unsigned __int64
0x180073bdf  mov     r12d, [rbp+37h+arg_28]
0x180073be3  mov     [rsp+0E0h+var_C0], r12d; int
0x180073be8  mov     r9, [rbp+37h+var_60]; char *
0x180073bec  mov     r8, [rbp+37h+var_58]; char *
0x180073bf0  mov     rdx, [rbp+37h+var_68]; char *
0x180073bf4  mov     rcx, [r15+80h]; this
0x180073bfb  call    ?GenerateSecondaryChannelRequest@WNPMessageGenerator@@QEAAJPEBD00K_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateSecondaryChannelRequest(char const *,char const *,char const *,ulong,unsigned __int64,uchar * *,ulong *)
0x180073c00  mov     ebx, eax
0x180073c02  lea     rcx, [rbp+37h+var_50]
0x180073c06  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180073c0b  test    ebx, ebx
0x180073c0d  jns     short loc_180073C82
0x180073c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c16  lea     r12, WPP_GLOBAL_Control
0x180073c1d  cmp     rcx, r12
0x180073c20  jz      short loc_180073C46
0x180073c22  test    byte ptr [rcx+1Ch], 2
0x180073c26  jz      short loc_180073C46
0x180073c28  cmp     byte ptr [rcx+19h], 2
0x180073c2c  jb      short loc_180073C46
0x180073c2e  mov     edx, 99h
0x180073c33  mov     r9d, ebx
0x180073c36  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073c3d  mov     rcx, [rcx+10h]
0x180073c41  call    WPP_SF_d
0x180073c46  mov     rcx, [rbp+3Fh]; this
0x180073c4a  mov     r9d, ebx; char *
0x180073c4d  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073c54  mov     edx, 642h; void *
0x180073c59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c65  cmp     rcx, r12
0x180073c68  jz      loc_180073E55
0x180073c6e  test    byte ptr [rcx+1Ch], 80h
0x180073c72  jz      loc_180073E2C
0x180073c78  mov     edx, 9Ah
0x180073c7d  jmp     loc_180073E09
0x180073c82  mov     edi, [rbp+37h+arg_38]
0x180073c85  test    cs:byte_1800AFD82, 10h
0x180073c8c  jz      short loc_180073CC1
0x180073c8e  mov     [rsp+0E0h+var_80], rsi
0x180073c93  mov     rax, [rbp+37h+var_70]
0x180073c97  mov     [rsp+0E0h+var_88], rax
0x180073c9c  mov     eax, [rbp+37h+arg_10]
0x180073c9f  mov     [rsp+0E0h+var_90], eax
0x180073ca3  mov     [rsp+0E0h+var_98], r14
0x180073ca8  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x180073cad  mov     rax, [rbp+37h+var_68]
0x180073cb1  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180073cb6  xor     r9d, r9d
0x180073cb9  mov     r8d, edi
0x180073cbc  call    McTemplateU0dssqqbr4sxqbr8x_EventWriteTransfer
0x180073cc1  mov     rcx, [r15+70h]
0x180073cc5  mov     rdx, [rbp+37h+var_70]
0x180073cc9  mov     r8d, [rbp+37h+arg_10]
0x180073ccd  mov     rax, [rcx]
0x180073cd0  lea     r9, [rbp+37h+arg_18]
0x180073cd4  mov     [rsp+0E0h+var_A8], r9
0x180073cd9  mov     [rsp+0E0h+var_B0], r13
0x180073cde  mov     [rsp+0E0h+var_B8], rdx
0x180073ce3  mov     [rsp+0E0h+var_C0], r8d; int
0x180073ce8  lea     r9, aChannel; "CHANNEL"
0x180073cef  lea     r8, ?s_GetCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_GetCommand
0x180073cf6  mov     rdx, rsi
0x180073cf9  mov     rax, [rax+30h]
0x180073cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d02  mov     ebx, eax
0x180073d04  test    eax, eax
0x180073d06  jns     short loc_180073D7B
0x180073d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d0f  lea     r12, WPP_GLOBAL_Control
0x180073d16  cmp     rcx, r12
0x180073d19  jz      short loc_180073D3F
0x180073d1b  test    byte ptr [rcx+1Ch], 2
0x180073d1f  jz      short loc_180073D3F
0x180073d21  cmp     byte ptr [rcx+19h], 2
0x180073d25  jb      short loc_180073D3F
0x180073d27  mov     edx, 9Bh
0x180073d2c  mov     r9d, eax
0x180073d2f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073d36  mov     rcx, [rcx+10h]
0x180073d3a  call    WPP_SF_d
0x180073d3f  mov     rcx, [rbp+3Fh]; this
0x180073d43  mov     r9d, ebx; char *
0x180073d46  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073d4d  mov     edx, 65Ah; void *
0x180073d52  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d5e  cmp     rcx, r12
0x180073d61  jz      loc_180073E55
0x180073d67  test    byte ptr [rcx+1Ch], 80h
0x180073d6b  jz      loc_180073E2C
0x180073d71  mov     edx, 9Ch
0x180073d76  jmp     loc_180073E09
0x180073d7b  lea     rdx, [r15+0A0h]
0x180073d82  mov     dword ptr [rsp+0E0h+var_B8], 1
0x180073d8a  mov     [rsp+0E0h+var_C0], edi; int
0x180073d8e  mov     r9d, [rbp+37h+arg_18]
0x180073d92  mov     r8, rsi
0x180073d95  mov     rcx, r15
0x180073d98  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x180073d9d  mov     ebx, eax
0x180073d9f  test    eax, eax
0x180073da1  jns     short loc_180073E1E
0x180073da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180073daa  lea     r12, WPP_GLOBAL_Control
0x180073db1  cmp     rcx, r12
0x180073db4  jz      short loc_180073DDA
0x180073db6  test    byte ptr [rcx+1Ch], 2
0x180073dba  jz      short loc_180073DDA
0x180073dbc  cmp     byte ptr [rcx+19h], 2
0x180073dc0  jb      short loc_180073DDA
0x180073dc2  mov     edx, 9Dh
0x180073dc7  mov     r9d, eax
0x180073dca  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073dd1  mov     rcx, [rcx+10h]
0x180073dd5  call    WPP_SF_d
0x180073dda  mov     rcx, [rbp+3Fh]; this
0x180073dde  mov     r9d, ebx; char *
0x180073de1  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073de8  mov     edx, 662h; void *
0x180073ded  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180073df9  cmp     rcx, r12
0x180073dfc  jz      short loc_180073E55
0x180073dfe  test    byte ptr [rcx+1Ch], 80h
0x180073e02  jz      short loc_180073E2C
0x180073e04  mov     edx, 9Eh
0x180073e09  mov     r9d, ebx
0x180073e0c  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073e13  mov     rcx, [rcx+10h]
0x180073e17  call    WPP_SF_d
0x180073e1c  jmp     short loc_180073E25
0x180073e1e  lea     r12, WPP_GLOBAL_Control
  ... truncated ...
```
