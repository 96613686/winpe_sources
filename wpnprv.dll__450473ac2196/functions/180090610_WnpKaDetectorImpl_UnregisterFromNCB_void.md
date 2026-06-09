# WnpKaDetectorImpl::UnregisterFromNCB(void)

- ea: `0x180090610`
- end: `0x180090958`
- name: `?UnregisterFromNCB@WnpKaDetectorImpl@@UEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(WnpKaDetectorImpl *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x180090610`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009076a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009076a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180090917`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180090917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009077c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009077c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800908d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800908d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WnpKaDetectorImpl::UnregisterFromNCB(WnpKaDetectorImpl *this)
{
  PVOID *v2; // rcx
  signed int v3; // ebx
  HMODULE v4; // rbp
  FARPROC ProcAddress; // rsi
  signed int LastError; // eax
  __int64 v7; // rdx
  int v8; // eax
  bool v9; // sf
  __int64 v10; // r9
  bool v11; // sf
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 65) )
  {
    v3 = 0;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    {
      WPP_SF_(v2[2], 66, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_QWORD *)this + 38) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*((_QWORD *)this + 39) )
      goto LABEL_63;
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    goto LABEL_62;
  }
  if ( *((_QWORD *)this + 38) )
  {
    if ( !*((_QWORD *)this + 52) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    v4 = (HMODULE)*((_QWORD *)this + 52);
    *((_QWORD *)this + 52) = 0;
    ProcAddress = GetProcAddress(v4, "KAMSS_DeregisterProvider");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
            (unsigned int)v3);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
          (const char *)(unsigned int)v3,
          v13);
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v7 = 70;
LABEL_35:
          WPP_SF_d(v2[2], v7, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, (unsigned int)v3);
LABEL_59:
          v2 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_60;
        }
        goto LABEL_60;
      }
    }
    v8 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)this + 38));
    *((_QWORD *)this + 39) = 0;
    v3 = v8;
    *((_QWORD *)this + 38) = 0;
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( v9 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_47:
        v11 = v3 < 0;
        if ( v3 > 0 )
        {
          v3 = (unsigned __int16)v3 | 0x80070000;
          v11 = v3 < 0;
        }
        if ( v11 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x270,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
            (const char *)(unsigned int)v3,
            v13);
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v7 = 72;
            goto LABEL_35;
          }
        }
        else
        {
          if ( *((_QWORD *)this + 49) )
          {
            WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 49), 0);
            v2 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 5u )
          {
            WPP_SF_(v2[2], 73, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
            goto LABEL_59;
          }
        }
LABEL_60:
        if ( v4 )
        {
          FreeLibrary(v4);
          goto LABEL_62;
        }
LABEL_63:
        if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
          WPP_SF_d(v2[2], 74, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, (unsigned int)v3);
        return (unsigned int)v3;
      }
      if ( v8 > 0 )
        v10 = (unsigned __int16)v8 | 0x80070000;
      else
        v10 = (unsigned int)v8;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v10);
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v3 = -2147418113;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_d(v2[2], 67, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147549183LL);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x255,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
    (const char *)0x8000FFFFLL,
    v13);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, 2147549183LL);
LABEL_62:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180090610  push    rbx
0x180090612  push    rbp
0x180090613  push    rsi
0x180090614  push    rdi
0x180090615  push    r12
0x180090617  push    r15
0x180090619  sub     rsp, 28h
0x18009061d  mov     rdi, rcx
0x180090620  mov     rcx, cs:WPP_GLOBAL_Control
0x180090627  lea     r15, WPP_GLOBAL_Control
0x18009062e  lea     r12, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x180090635  cmp     rcx, r15
0x180090638  jz      short loc_18009065E
0x18009063a  test    byte ptr [rcx+1Ch], 8
0x18009063e  jz      short loc_18009065E
0x180090640  cmp     byte ptr [rcx+19h], 6
0x180090644  jb      short loc_18009065E
0x180090646  mov     rcx, [rcx+10h]
0x18009064a  mov     edx, 41h ; 'A'
0x18009064f  mov     r8, r12
0x180090652  call    WPP_SF_
0x180090657  mov     rcx, cs:WPP_GLOBAL_Control
0x18009065e  cmp     dword ptr [rdi+104h], 0
0x180090665  jz      short loc_1800906BC
0x180090667  xor     ebx, ebx
0x180090669  cmp     rcx, r15
0x18009066c  jz      short loc_180090690
0x18009066e  test    byte ptr [rcx+1Ch], 8
0x180090672  jz      short loc_180090690
0x180090674  cmp     byte ptr [rcx+19h], 5
0x180090678  jb      short loc_180090690
0x18009067a  mov     rcx, [rcx+10h]
0x18009067e  lea     edx, [rbx+42h]
0x180090681  mov     r8, r12
0x180090684  call    WPP_SF_
0x180090689  mov     rcx, cs:WPP_GLOBAL_Control
0x180090690  cmp     [rdi+130h], rbx
0x180090697  jz      short loc_1800906A5
0x180090699  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009069e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800906a5  cmp     [rdi+138h], rbx
0x1800906ac  jz      loc_180090924
0x1800906b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800906b7  jmp     loc_18009091D
0x1800906bc  cmp     qword ptr [rdi+130h], 0
0x1800906c4  jnz     short loc_18009073F
0x1800906c6  mov     ebx, 8000FFFFh
0x1800906cb  cmp     rcx, r15
0x1800906ce  jz      short loc_1800906F0
0x1800906d0  test    byte ptr [rcx+1Ch], 8
0x1800906d4  jz      short loc_1800906F0
0x1800906d6  cmp     byte ptr [rcx+19h], 2
0x1800906da  jb      short loc_1800906F0
0x1800906dc  mov     rcx, [rcx+10h]
0x1800906e0  mov     edx, 43h ; 'C'
0x1800906e5  mov     r9d, ebx
0x1800906e8  mov     r8, r12
0x1800906eb  call    WPP_SF_d
0x1800906f0  mov     rcx, [rsp+58h]; this
0x1800906f5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800906fc  mov     r9d, ebx; char *
0x1800906ff  mov     edx, 255h; void *
0x180090704  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180090709  mov     rcx, cs:WPP_GLOBAL_Control
0x180090710  cmp     rcx, r15
0x180090713  jz      loc_180090949
0x180090719  test    byte ptr [rcx+1Ch], 80h
0x18009071d  jz      loc_180090924
0x180090723  mov     rcx, [rcx+10h]
0x180090727  mov     edx, 44h ; 'D'
0x18009072c  mov     r9d, 8000FFFFh
0x180090732  mov     r8, r12
0x180090735  call    WPP_SF_d
0x18009073a  jmp     loc_18009091D
0x18009073f  cmp     qword ptr [rdi+1A0h], 0
0x180090747  jnz     short loc_18009074E
0x180090749  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009074e  mov     rbp, [rdi+1A0h]
0x180090755  lea     rdx, aKamssDeregiste; "KAMSS_DeregisterProvider"
0x18009075c  mov     rcx, rbp; hModule
0x18009075f  mov     qword ptr [rdi+1A0h], 0
0x18009076a  call    cs:__imp_GetProcAddress
0x180090770  mov     rsi, rax
0x180090773  test    rax, rax
0x180090776  jnz     loc_18009080D
0x18009077c  call    cs:__imp_GetLastError
0x180090782  mov     ebx, eax
0x180090784  test    eax, eax
0x180090786  jle     short loc_180090791
0x180090788  movzx   ebx, ax
0x18009078b  or      ebx, 80070000h
0x180090791  test    ebx, ebx
0x180090793  jns     short loc_18009080D
0x180090795  mov     rcx, cs:WPP_GLOBAL_Control
0x18009079c  cmp     rcx, r15
0x18009079f  jz      short loc_1800907C1
0x1800907a1  test    byte ptr [rcx+1Ch], 8
0x1800907a5  jz      short loc_1800907C1
0x1800907a7  cmp     byte ptr [rcx+19h], 2
0x1800907ab  jb      short loc_1800907C1
0x1800907ad  mov     rcx, [rcx+10h]
0x1800907b1  mov     edx, 45h ; 'E'
0x1800907b6  mov     r9d, ebx
0x1800907b9  mov     r8, r12
0x1800907bc  call    WPP_SF_d
0x1800907c1  mov     rcx, [rsp+58h]; this
0x1800907c6  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800907cd  mov     r9d, ebx; char *
0x1800907d0  mov     edx, 263h; void *
0x1800907d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800907da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800907e1  cmp     rcx, r15
0x1800907e4  jz      loc_18009090F
0x1800907ea  test    byte ptr [rcx+1Ch], 80h
0x1800907ee  jz      loc_18009090F
0x1800907f4  mov     edx, 46h ; 'F'
0x1800907f9  mov     rcx, [rcx+10h]
0x1800907fd  mov     r9d, ebx
0x180090800  mov     r8, r12
0x180090803  call    WPP_SF_d
0x180090808  jmp     loc_180090908
0x18009080d  mov     rcx, [rdi+130h]
0x180090814  mov     rax, rsi
0x180090817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009081c  mov     qword ptr [rdi+138h], 0
0x180090827  mov     ebx, eax
0x180090829  mov     qword ptr [rdi+130h], 0
0x180090834  mov     esi, 80070000h
0x180090839  test    eax, eax
0x18009083b  jle     short loc_180090844
0x18009083d  movzx   eax, bx
0x180090840  or      eax, esi
0x180090842  test    eax, eax
0x180090844  jns     short loc_18009087F
0x180090846  mov     rcx, cs:WPP_GLOBAL_Control
0x18009084d  cmp     rcx, r15
0x180090850  jz      short loc_180090886
0x180090852  test    byte ptr [rcx+1Ch], 8
0x180090856  jz      short loc_180090886
0x180090858  cmp     byte ptr [rcx+19h], 2
0x18009085c  jb      short loc_180090886
0x18009085e  test    ebx, ebx
0x180090860  jg      short loc_180090867
0x180090862  mov     r9d, ebx
0x180090865  jmp     short loc_18009086E
0x180090867  movzx   r9d, bx
0x18009086b  or      r9d, esi
0x18009086e  mov     rcx, [rcx+10h]
0x180090872  mov     edx, 47h ; 'G'
0x180090877  mov     r8, r12
0x18009087a  call    WPP_SF_d
0x18009087f  mov     rcx, cs:WPP_GLOBAL_Control
0x180090886  test    ebx, ebx
0x180090888  jle     short loc_180090891
0x18009088a  movzx   ebx, bx
0x18009088d  or      ebx, esi
0x18009088f  test    ebx, ebx
0x180090891  jns     short loc_1800908C8
0x180090893  mov     rcx, [rsp+58h]; this
0x180090898  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009089f  mov     r9d, ebx; char *
0x1800908a2  mov     edx, 270h; void *
0x1800908a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800908ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800908b3  cmp     rcx, r15
0x1800908b6  jz      short loc_18009090F
0x1800908b8  test    byte ptr [rcx+1Ch], 80h
0x1800908bc  jz      short loc_18009090F
0x1800908be  mov     edx, 48h ; 'H'
0x1800908c3  jmp     loc_1800907F9
0x1800908c8  mov     rax, [rdi+188h]
0x1800908cf  test    rax, rax
0x1800908d2  jz      short loc_1800908E6
0x1800908d4  xor     edx, edx; fCancelPendingCallbacks
0x1800908d6  mov     rcx, rax; pwk
0x1800908d9  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800908df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800908e6  cmp     rcx, r15
0x1800908e9  jz      short loc_18009090F
0x1800908eb  test    byte ptr [rcx+1Ch], 8
0x1800908ef  jz      short loc_18009090F
0x1800908f1  cmp     byte ptr [rcx+19h], 5
0x1800908f5  jb      short loc_18009090F
0x1800908f7  mov     rcx, [rcx+10h]
0x1800908fb  mov     edx, 49h ; 'I'
0x180090900  mov     r8, r12
0x180090903  call    WPP_SF_
0x180090908  mov     rcx, cs:WPP_GLOBAL_Control
0x18009090f  test    rbp, rbp
0x180090912  jz      short loc_180090924
0x180090914  mov     rcx, rbp; hLibModule
0x180090917  call    cs:__imp_FreeLibrary
0x18009091d  mov     rcx, cs:WPP_GLOBAL_Control
0x180090924  cmp     rcx, r15
0x180090927  jz      short loc_180090949
0x180090929  test    byte ptr [rcx+1Ch], 8
0x18009092d  jz      short loc_180090949
0x18009092f  cmp     byte ptr [rcx+19h], 6
0x180090933  jb      short loc_180090949
0x180090935  mov     rcx, [rcx+10h]
0x180090939  mov     edx, 4Ah ; 'J'
0x18009093e  mov     r9d, ebx
0x180090941  mov     r8, r12
0x180090944  call    WPP_SF_d
0x180090949  mov     eax, ebx
0x18009094b  add     rsp, 28h
0x18009094f  pop     r15
0x180090951  pop     r12
0x180090953  pop     rdi
0x180090954  pop     rsi
0x180090955  pop     rbp
0x180090956  pop     rbx
0x180090957  retn
```
