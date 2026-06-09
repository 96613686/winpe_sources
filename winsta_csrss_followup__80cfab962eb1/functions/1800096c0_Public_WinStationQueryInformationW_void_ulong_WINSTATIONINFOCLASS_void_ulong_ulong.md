# Public_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x1800096c0`
- end: `0x180009c22`
- name: `?Public_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `1378`
- prototype: `unsigned __int8 __fastcall(CPublicBinding *this, unsigned int, enum _WINSTATIONINFOCLASS, struct _WINSTATIONLOADINDICATORDATA *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x1800152d0`

## callees

- `0x180002464`
- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x180006000`
- `0x1800065f0`
- `0x1800066d0`
- `0x180006b20`
- `0x1800075a0`
- `0x180008640`
- `0x1800096c0`
- `0x180009c30`
- `0x180009dec`
- `0x18000a784`
- `0x18000aac4`
- `0x18000eda4`
- `0x180011050`
- `0x1800249e8`
- `0x180024a1c`
- `0x18002f0a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009c03`
- `ntdll!RtlNtStatusToDosError` at `0x180009c03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ad3`

## string_xrefs

- `0x180009906`: `StringCchCopy failed: %x`
- `0x180009bad`: `Failed to open binding`
- `0x18000993f`: `GetCurrentSessionConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall Public_WinStationQueryInformationW(
        CPublicBinding *this,
        ULONG SessionId,
        unsigned int a3,
        struct _WINSTATIONINFORMATIONW *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int64 v7; // rsi
  CPublicBinding *v10; // rax
  CPublicBinding *v11; // rbx
  _WORD *v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rcx
  int *v15; // rdx
  __int64 v16; // r10
  _WORD *v17; // rcx
  int v18; // edi
  __int64 v19; // rcx
  int IsCurrentSession; // eax
  int v21; // edi
  unsigned __int8 InformationW; // di
  unsigned int *v23; // r8
  int CurrentSessionInformation; // eax
  int v25; // ebx
  int v27; // esi
  int v28; // esi
  int CurrentSessionConfigData; // eax
  int v30; // ebx
  int v31; // ecx
  int CurrentSessionClientData; // eax
  int v33; // ebx
  DWORD v34; // eax
  int CurrentSessionWinStationType; // eax
  int v36; // ebx
  DWORD v37; // eax
  DWORD v38; // eax
  unsigned __int16 v39[4]; // [rsp+30h] [rbp-A8h] BYREF
  CPublicBinding *v40; // [rsp+38h] [rbp-A0h]
  _BYTE v41[112]; // [rsp+40h] [rbp-98h] BYREF
  int v42; // [rsp+E0h] [rbp+8h] BYREF

  *(_QWORD *)v39 = 0;
  v7 = a3;
  if ( this )
  {
    v11 = this;
    v40 = this;
    if ( *(_WORD *)this && !*((_DWORD *)this + 12) )
      goto LABEL_47;
  }
  else
  {
    v10 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 6) = 1;
      *((_QWORD *)v10 + 7) = 0;
      v12 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)v11 + 5) = v12;
      v13 = v12;
      if ( v12 )
      {
        v14 = 2147483646;
        v15 = &dword_18003FF34;
        v16 = 1;
        do
        {
          if ( !v14 )
            break;
          if ( !*(_WORD *)v15 )
            break;
          *v13 = *(_WORD *)v15;
          v15 = (int *)((char *)v15 + 2);
          ++v13;
          --v14;
          --v16;
        }
        while ( v16 );
        v17 = v13 - 1;
        v18 = -2147024774;
        if ( v16 )
        {
          v17 = v13;
          v18 = 0;
        }
        *v17 = 0;
        if ( v16 )
        {
          if ( !*((_QWORD *)v11 + 3) && !*((_DWORD *)v11 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle(v11) == -2147023174 )
              *((_DWORD *)v11 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle(v11);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v18);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v18);
        }
      }
      v40 = v11;
      *(_DWORD *)&v39[2] = 1;
    }
    else
    {
      v11 = 0;
      v40 = 0;
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( (unsigned int)v7 <= 0x27 )
  {
    v19 = 0x8000000142LL;
    if ( _bittest64(&v19, v7) )
    {
      v42 = 0;
      IsCurrentSession = CUtils::IsCurrentSession(SessionId, &v42);
      v21 = IsCurrentSession;
      if ( IsCurrentSession < 0 )
      {
        _DbgPrintMessage(
          8,
          "CUtils::IsCurrentSession failed: 0x%x in %s",
          IsCurrentSession,
          "Public_WinStationQueryInformationW");
        v34 = ConvertHRESULT2WIN32(v21);
        SetLastError(v34);
        InformationW = 0;
        goto LABEL_28;
      }
      if ( v42 )
      {
        InformationW = 0;
        if ( a4 )
        {
          v23 = a6;
          if ( a6 )
          {
            *a6 = 0;
            if ( (_DWORD)v7 == 8 )
            {
              CurrentSessionInformation = GetCurrentSessionInformation(a4, a5, v23);
              v25 = CurrentSessionInformation;
              if ( CurrentSessionInformation >= 0 )
              {
LABEL_22:
                InformationW = 1;
                goto LABEL_28;
              }
              _DbgPrintMessage(
                8,
                "GetCurrentSessionInformation failed: 0x%x in %s",
                CurrentSessionInformation,
                "WinStationQueryCurrentSessionInformation");
              v31 = v25;
LABEL_61:
              v37 = ConvertHRESULT2WIN32(v31);
              SetLastError(v37);
              goto LABEL_28;
            }
            v27 = v7 - 1;
            if ( !v27 )
            {
              CurrentSessionConfigData = GetCurrentSessionConfigData((struct _WINSTATIONCONFIGW *)a4, a5, v23);
              v30 = CurrentSessionConfigData;
              if ( CurrentSessionConfigData >= 0 )
                goto LABEL_22;
              _DbgPrintMessage(
                8,
                "GetCurrentSessionConfigData failed: 0x%x in %s",
                CurrentSessionConfigData,
                "WinStationQueryCurrentSessionInformation");
              v31 = v30;
              goto LABEL_61;
            }
            v28 = v27 - 5;
            if ( !v28 )
            {
              CurrentSessionClientData = GetCurrentSessionClientData((struct _WINSTATIONCLIENTW *)a4, a5, v23);
              v33 = CurrentSessionClientData;
              if ( CurrentSessionClientData >= 0 )
                goto LABEL_22;
              _DbgPrintMessage(
                8,
                "GetCurrentSessionClientData failed: 0x%x in %s",
                CurrentSessionClientData,
                "WinStationQueryCurrentSessionInformation");
              v31 = v33;
              goto LABEL_61;
            }
            if ( v28 == 33 )
            {
              CurrentSessionWinStationType = GetCurrentSessionWinStationType((unsigned int *)a4->Reserved2, a5, v23);
              v36 = CurrentSessionWinStationType;
              if ( CurrentSessionWinStationType >= 0 )
                goto LABEL_22;
              _DbgPrintMessage(
                8,
                "GetCurrentSessionWinStationType failed: 0x%x in %s",
                CurrentSessionWinStationType,
                "WinStationQueryCurrentSessionInformation");
              v31 = v36;
              goto LABEL_61;
            }
          }
        }
LABEL_32:
        SetLastError(0x57u);
        goto LABEL_28;
      }
    }
  }
LABEL_47:
  InformationW = 0;
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(this) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      goto LABEL_32;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  if ( !CSmartPublicBinding::operator void *(v39) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_28;
  }
  if ( v11 && *((_DWORD *)v11 + 13) != 1 )
  {
    if ( SessionId >= 0x10000 )
    {
      InformationW = Listener_WinStationQueryInformationW(
                       this,
                       SessionId - 0x10000,
                       (enum _WINSTATIONINFOCLASS)v7,
                       a4,
                       a5,
                       a6);
      goto LABEL_28;
    }
    if ( (_DWORD)v7 == 25 )
    {
      if ( a5 < 0x48 )
      {
        v38 = RtlNtStatusToDosError(-1073741789);
        SetLastError(v38);
        goto LABEL_28;
      }
      CLoadBalancingMetrics::CLoadBalancingMetrics((CLoadBalancingMetrics *)v41);
      CLoadBalancingMetrics::GetData((CLoadBalancingMetrics *)v41, (struct _WINSTATIONLOADINDICATORDATA *)a4);
      *a6 = 72;
      goto LABEL_22;
    }
    if ( (_DWORD)v7 != 41 )
    {
      InformationW = _tsrpcQuerySessionInfo(this, SessionId, v7, a4, a5, a6);
      goto LABEL_28;
    }
    _DbgPrintMessage(
      8,
      "WinStationValidationInfo is not supported on win8 and above failed: 0x%x in %s",
      -2147467263,
      "Public_WinStationQueryInformationW");
    v31 = -2147467263;
    goto LABEL_61;
  }
  InformationW = Legacy_WinStationQueryInformationW(this, SessionId, (enum _WINSTATIONINFOCLASS)v7, a4, a5, a6);
  if ( !InformationW )
    GetLastError();
LABEL_28:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v39);
  return InformationW;
}

```

## disassembly

```asm
0x1800096c0  mov     [rsp+arg_8], rbx
0x1800096c5  mov     [rsp+arg_10], rbp
0x1800096ca  push    rsi
0x1800096cb  push    rdi
0x1800096cc  push    r12
0x1800096ce  push    r14
0x1800096d0  push    r15
0x1800096d2  sub     rsp, 0B0h
0x1800096d9  xor     r12d, r12d
0x1800096dc  mov     r15, r9
0x1800096df  mov     qword ptr [rsp+0D8h+var_A8], r12
0x1800096e4  mov     esi, r8d
0x1800096e7  mov     r14d, edx
0x1800096ea  mov     rbp, rcx
0x1800096ed  test    rcx, rcx
0x1800096f0  jnz     loc_180009A5A
0x1800096f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800096fd  mov     ecx, 40h ; '@'; unsigned __int64
0x180009702  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009707  mov     rbx, rax
0x18000970a  test    rax, rax
0x18000970d  jz      loc_180009B4A
0x180009713  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000971a  mov     [rax], r12
0x18000971d  mov     ecx, 2; unsigned __int64
0x180009722  mov     [rax+8], r12
0x180009726  mov     [rax+10h], r12
0x18000972a  mov     [rax+18h], r12
0x18000972e  mov     [rax+20h], r12
0x180009732  mov     [rax+28h], r12
0x180009736  mov     qword ptr [rax+30h], 1
0x18000973e  mov     [rax+38h], r12
0x180009742  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009747  mov     [rbx+28h], rax
0x18000974b  mov     r9, rax
0x18000974e  test    rax, rax
0x180009751  jz      short loc_1800097B5
0x180009753  mov     ecx, 7FFFFFFEh
0x180009758  lea     rdx, dword_18003FF34
0x18000975f  mov     r10d, 1
0x180009765  test    rcx, rcx
0x180009768  jz      short loc_180009787
0x18000976a  movzx   eax, word ptr [rdx]
0x18000976d  test    ax, ax
0x180009770  jz      short loc_180009787
0x180009772  mov     [r9], ax
0x180009776  add     rdx, 2
0x18000977a  add     r9, 2
0x18000977e  dec     rcx
0x180009781  sub     r10, 1
0x180009785  jnz     short loc_180009765
0x180009787  test    r10, r10
0x18000978a  lea     rcx, [r9-2]
0x18000978e  mov     edi, 8007007Ah
0x180009793  cmovnz  rcx, r9
0x180009797  cmovnz  edi, r12d
0x18000979b  mov     [rcx], r12w
0x18000979f  jz      loc_1800098FC
0x1800097a5  cmp     [rbx+18h], r12
0x1800097a9  jnz     short loc_1800097B5
0x1800097ab  cmp     [rbx+30h], r12d
0x1800097af  jz      loc_1800099CA
0x1800097b5  mov     [rsp+0D8h+var_A0], rbx
0x1800097ba  mov     dword ptr [rsp+0D8h+var_A8+4], 1
0x1800097c2  cmp     esi, 27h ; '''
0x1800097c5  ja      loc_180009A76
0x1800097cb  mov     rcx, 8000000142h
0x1800097d5  bt      rcx, rsi
0x1800097d9  jnb     loc_180009A76
0x1800097df  lea     rdx, [rsp+0D8h+arg_0]; int *
0x1800097e7  mov     [rsp+0D8h+arg_0], r12d
0x1800097ef  mov     ecx, r14d; unsigned int
0x1800097f2  call    ?IsCurrentSession@CUtils@@SAJKPEAH@Z; CUtils::IsCurrentSession(ulong,int *)
0x1800097f7  mov     edi, eax
0x1800097f9  test    eax, eax
0x1800097fb  js      loc_180009992
0x180009801  cmp     [rsp+0D8h+arg_0], r12d
0x180009809  jz      loc_180009A76
0x18000980f  xor     dil, dil
0x180009812  test    r15, r15
0x180009815  jz      loc_1800098E9
0x18000981b  mov     r8, [rsp+0D8h+arg_28]; unsigned int *
0x180009823  test    r8, r8
0x180009826  jz      loc_1800098E9
0x18000982c  mov     [r8], r12d
0x18000982f  cmp     esi, 8
0x180009832  jnz     loc_1800098D6
0x180009838  mov     edx, [rsp+0D8h+arg_20]; unsigned int
0x18000983f  mov     rcx, r15; struct _WINSTATIONINFORMATIONW *
0x180009842  call    ?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x180009847  mov     ebx, eax
0x180009849  test    eax, eax
0x18000984b  js      loc_180009B79
0x180009851  mov     dil, 1
0x180009854  jmp     short loc_1800098AB
0x180009856  cmp     dword ptr [rbx+34h], 1
0x18000985a  jz      loc_180009A9F
0x180009860  cmp     r14d, 10000h
0x180009867  jnb     loc_180009A25
0x18000986d  cmp     esi, 19h
0x180009870  jz      loc_180009AE4
0x180009876  cmp     esi, 29h ; ')'
0x180009879  jz      loc_180009BC3
0x18000987f  mov     rax, [rsp+0D8h+arg_28]
0x180009887  mov     r9, r15; void *
0x18000988a  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x18000988f  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x180009892  mov     eax, [rsp+0D8h+arg_20]
0x180009899  mov     edx, r14d; unsigned int
0x18000989c  mov     rcx, rbp; this
0x18000989f  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x1800098a3  call    ?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x1800098a8  movzx   edi, al
0x1800098ab  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800098b0  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800098b5  lea     r11, [rsp+0D8h+var_28]
0x1800098bd  movzx   eax, dil
0x1800098c1  mov     rbx, [r11+38h]
0x1800098c5  mov     rbp, [r11+40h]
0x1800098c9  mov     rsp, r11
0x1800098cc  pop     r15
0x1800098ce  pop     r14
0x1800098d0  pop     r12
0x1800098d2  pop     rdi
0x1800098d3  pop     rsi
0x1800098d4  retn
0x1800098d6  sub     esi, 1
0x1800098d9  jz      short loc_18000991C
0x1800098db  sub     esi, 5
0x1800098de  jz      short loc_180009957
0x1800098e0  cmp     esi, 21h ; '!'
0x1800098e3  jz      loc_1800099EA
0x1800098e9  mov     ecx, 57h ; 'W'; dwErrCode
0x1800098ee  call    cs:__imp_SetLastError
0x1800098f5  nop     dword ptr [rax+rax+00h]
0x1800098fa  jmp     short loc_1800098AB
0x1800098fc  mov     ecx, edi; int
0x1800098fe  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009903  mov     r8d, edi
0x180009906  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000990d  mov     ecx, 8; int
0x180009912  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009917  jmp     loc_1800097B5
0x18000991c  mov     edx, [rsp+0D8h+arg_20]; unsigned int
0x180009923  mov     rcx, r15; struct _WINSTATIONCONFIGW *
0x180009926  call    ?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000992b  mov     ebx, eax
0x18000992d  test    eax, eax
0x18000992f  jns     loc_180009851
0x180009935  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x18000993c  mov     r8d, eax
0x18000993f  lea     rdx, aGetcurrentsess; "GetCurrentSessionConfigData failed: 0x%"...
0x180009946  mov     ecx, 8; int
0x18000994b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009950  mov     ecx, ebx
0x180009952  jmp     loc_180009BE6
0x180009957  mov     edx, [rsp+0D8h+arg_20]; unsigned int
0x18000995e  mov     rcx, r15; struct _WINSTATIONCLIENTW *
0x180009961  call    ?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)
0x180009966  mov     ebx, eax
0x180009968  test    eax, eax
0x18000996a  jns     loc_180009851
0x180009970  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x180009977  mov     r8d, eax
0x18000997a  lea     rdx, aGetcurrentsess_0; "GetCurrentSessionClientData failed: 0x%"...
0x180009981  mov     ecx, 8; int
0x180009986  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000998b  mov     ecx, ebx
0x18000998d  jmp     loc_180009BE6
0x180009992  lea     r9, aPublicWinstati; "Public_WinStationQueryInformationW"
0x180009999  mov     r8d, edi
0x18000999c  lea     rdx, aCutilsIscurren; "CUtils::IsCurrentSession failed: 0x%x i"...
0x1800099a3  mov     ecx, 8; int
0x1800099a8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800099ad  mov     ecx, edi; int
0x1800099af  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800099b4  mov     ecx, eax; dwErrCode
0x1800099b6  call    cs:__imp_SetLastError
0x1800099bd  nop     dword ptr [rax+rax+00h]
0x1800099c2  xor     dil, dil
0x1800099c5  jmp     loc_1800098AB
0x1800099ca  mov     rcx, rbx; this
0x1800099cd  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800099d2  cmp     eax, 800706BAh
0x1800099d7  jz      loc_180009B3E
0x1800099dd  mov     rcx, rbx; this
0x1800099e0  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800099e5  jmp     loc_1800097B5
0x1800099ea  mov     edx, [rsp+0D8h+arg_20]; unsigned int
0x1800099f1  mov     rcx, r15; unsigned int *
0x1800099f4  call    ?GetCurrentSessionWinStationType@@YAJPEAKK0@Z; GetCurrentSessionWinStationType(ulong *,ulong,ulong *)
0x1800099f9  mov     ebx, eax
0x1800099fb  test    eax, eax
0x1800099fd  jns     loc_180009851
0x180009a03  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x180009a0a  mov     r8d, eax
0x180009a0d  lea     rdx, aGetcurrentsess_6; "GetCurrentSessionWinStationType failed:"...
0x180009a14  mov     ecx, 8; int
0x180009a19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009a1e  mov     ecx, ebx
0x180009a20  jmp     loc_180009BE6
0x180009a25  mov     rax, [rsp+0D8h+arg_28]
0x180009a2d  lea     edx, [r14-10000h]; unsigned int
0x180009a34  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180009a39  mov     r9, r15; void *
0x180009a3c  mov     eax, [rsp+0D8h+arg_20]
0x180009a43  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x180009a46  mov     rcx, rbp; this
0x180009a49  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x180009a4d  call    ?Listener_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; Listener_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x180009a52  movzx   edi, al
0x180009a55  jmp     loc_1800098AB
0x180009a5a  mov     rbx, rbp
0x180009a5d  mov     [rsp+0D8h+var_A0], rbx
0x180009a62  cmp     r12w, [rcx]
0x180009a66  jz      loc_1800097C2
0x180009a6c  cmp     [rcx+30h], r12d
0x180009a70  jnz     loc_1800097C2
0x180009a76  xor     dil, dil
0x180009a79  cmp     r14d, 0FFFFFFFFh
0x180009a7d  jz      loc_180009B1C
0x180009a83  lea     rcx, [rsp+0D8h+var_A8]; unsigned __int16 *
0x180009a88  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180009a8d  test    rax, rax
0x180009a90  jz      loc_180009BAD
0x180009a96  test    rbx, rbx
0x180009a99  jnz     loc_180009856
0x180009a9f  mov     rax, [rsp+0D8h+arg_28]
0x180009aa7  mov     r9, r15; void *
0x180009aaa  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x180009aaf  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x180009ab2  mov     eax, [rsp+0D8h+arg_20]
0x180009ab9  mov     edx, r14d; unsigned int
0x180009abc  mov     rcx, rbp; this
0x180009abf  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x180009ac3  call    ?Legacy_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; Legacy_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x180009ac8  movzx   edi, al
0x180009acb  test    al, al
0x180009acd  jnz     loc_1800098AB
0x180009ad3  call    cs:__imp_GetLastError
0x180009ada  nop     dword ptr [rax+rax+00h]
0x180009adf  jmp     loc_1800098AB
0x180009ae4  cmp     [rsp+0D8h+arg_20], 48h ; 'H'
0x180009aec  jb      loc_180009BFE
0x180009af2  lea     rcx, [rsp+0D8h+var_98]; this
0x180009af7  call    ??0CLoadBalancingMetrics@@QEAA@XZ; CLoadBalancingMetrics::CLoadBalancingMetrics(void)
0x180009afc  mov     rdx, r15; struct _WINSTATIONLOADINDICATORDATA *
0x180009aff  lea     rcx, [rsp+0D8h+var_98]; this
0x180009b04  call    ?GetData@CLoadBalancingMetrics@@QEAAKPEAU_WINSTATIONLOADINDICATORDATA@@@Z; CLoadBalancingMetrics::GetData(_WINSTATIONLOADINDICATORDATA *)
0x180009b09  mov     rax, [rsp+0D8h+arg_28]
0x180009b11  mov     dword ptr [rax], 48h ; 'H'
0x180009b17  jmp     loc_180009851
0x180009b1c  mov     rcx, rbp; void *
0x180009b1f  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180009b24  test    eax, eax
0x180009b26  jnz     short loc_180009B98
0x180009b28  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180009b2f  mov     ecx, 4; int
0x180009b34  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009b39  jmp     loc_1800098E9
0x180009b3e  mov     dword ptr [rbx+34h], 1
0x180009b45  jmp     loc_1800099DD
0x180009b4a  mov     rbx, r12
0x180009b4d  mov     ecx, 0Eh; dwErrCode
0x180009b52  mov     [rsp+0D8h+var_A0], rbx
0x180009b57  call    cs:__imp_SetLastError
0x180009b5e  nop     dword ptr [rax+rax+00h]
0x180009b63  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180009b6a  mov     ecx, 8; int
0x180009b6f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009b74  jmp     loc_1800097C2
0x180009b79  lea     r9, aWinstationquer_10; "WinStationQueryCurrentSessionInformatio"...
0x180009b80  mov     r8d, ebx
0x180009b83  lea     rdx, aGetcurrentsess_1; "GetCurrentSessionInformation failed: 0x"...
0x180009b8a  mov     ecx, 8; int
0x180009b8f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009b94  mov     ecx, ebx
0x180009b96  jmp     short loc_180009BE6
0x180009b98  mov     rax, gs:60h
0x180009ba1  mov     r14d, [rax+2C0h]
0x180009ba8  jmp     loc_180009A83
0x180009bad  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180009bb4  mov     ecx, 8; int
0x180009bb9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009bbe  jmp     loc_1800098AB
0x180009bc3  lea     r9, aPublicWinstati; "Public_WinStationQueryInformationW"
0x180009bca  mov     r8d, 80004001h
0x180009bd0  lea     rdx, aWinstationvali; "WinStationValidationInfo is not support"...
0x180009bd7  mov     ecx, 8; int
0x180009bdc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009be1  mov     ecx, 80004001h; int
0x180009be6  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009beb  mov     ecx, eax; dwErrCode
0x180009bed  call    cs:__imp_SetLastError
0x180009bf4  nop     dword ptr [rax+rax+00h]
0x180009bf9  jmp     loc_1800098AB
0x180009bfe  mov     ecx, 0C0000023h; Status
0x180009c03  call    cs:__imp_RtlNtStatusToDosError
0x180009c0a  nop     dword ptr [rax+rax+00h]
0x180009c0f  mov     ecx, eax; dwErrCode
  ... truncated ...
```
