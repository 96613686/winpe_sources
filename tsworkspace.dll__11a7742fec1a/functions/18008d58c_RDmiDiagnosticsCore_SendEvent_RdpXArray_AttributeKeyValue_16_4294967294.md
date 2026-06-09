# RDmiDiagnosticsCore::SendEvent(RdpXArray<AttributeKeyValue,16,4294967294> &)

- ea: `0x18008d58c`
- end: `0x18008dae7`
- name: `?SendEvent@RDmiDiagnosticsCore@@IEBAXAEAV?$RdpXArray@UAttributeKeyValue@@$0BA@$0PPPPPPPO@@@@Z`
- size: `1371`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008d150`
- `0x18008d3ec`

## callees

- `0x1800058d4`
- `0x180007598`
- `0x18000ece0`
- `0x180019fb0`
- `0x18001a008`
- `0x18008ad9c`
- `0x18008b050`
- `0x18008b0bc`
- `0x18008cc44`
- `0x18008ce10`
- `0x18008d06c`
- `0x18008d0e4`
- `0x18008d58c`
- `0x18008e320`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateGuid` at `0x18008d5e0`
- `ole32!CoCreateGuid` at `0x18008d5e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d672`
- `OLEAUT32!__imp_SysFreeString` at `0x18008daa9`
- `OLEAUT32!__imp_SysFreeString` at `0x18008dab4`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d672`
- `OLEAUT32!__imp_SysFreeString` at `0x18008daa9`
- `OLEAUT32!__imp_SysFreeString` at `0x18008dab4`

## string_xrefs

- `0x18008d620`: `CoCreateGuid failed`
- `0x18008d9cf`: `Component`
- `0x18008da6f`: `SerializeToDiagnosticsEventJSON failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RDmiDiagnosticsCore::SendEvent(__int64 a1, __int64 a2)
{
  HRESULT v4; // edi
  int ActivityIdPrefix; // eax
  int v6; // edi
  unsigned int v7; // eax
  __int64 v8; // rdx
  int appended; // eax
  int CurrentUTCTimeString; // edi
  int v11; // eax
  int CurrentRoleInstance; // edi
  int v13; // eax
  int v14; // ebx
  int v15; // eax
  __int64 v16; // [rsp+28h] [rbp-58h]
  unsigned __int16 *v17[2]; // [rsp+30h] [rbp-50h] BYREF
  BSTR v18; // [rsp+40h] [rbp-40h] BYREF
  BSTR v19; // [rsp+48h] [rbp-38h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-30h] BYREF
  GUID pguid; // [rsp+60h] [rbp-20h] BYREF

  bstrString[1] = (BSTR)-2LL;
  *(_OWORD *)v17 = 0;
  pguid = 0;
  v19 = 0;
  v18 = 0;
  v4 = CoCreateGuid(&pguid);
  if ( v4 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids,
      ActivityIdPrefix,
      (__int64)"CoCreateGuid failed",
      v4,
      v17[0],
      v17[1],
      v18,
      v19);
  }
  ATL::CComBSTR::operator=(v17, L"Id");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, &pguid);
  ATL::CComBSTR::operator=(&v17[1], bstrString);
  SysFreeString(bstrString[0]);
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      v8 = 36;
LABEL_11:
      WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids, v7, v6, v6);
    }
  }
  else
  {
    ATL::CComBSTR::operator=(v17, L"ActivityId");
    ATL::CComBSTR::operator=(&v17[1], a1 + 64);
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        v8 = 37;
        goto LABEL_11;
      }
    }
    else
    {
      ATL::CComBSTR::operator=(v17, L"ActivityHint");
      ATL::CComBSTR::operator=(&v18, L"ms-wvd-hp:");
      appended = ATL::CComBSTR::AppendBSTR((ATL::CComBSTR *)&v18, *(unsigned __int16 **)(a1 + 80));
      if ( appended < 0 )
        ATL::AtlThrowImpl(appended);
      ATL::CComBSTR::operator=(&v17[1], &v18);
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v8 = 38;
          goto LABEL_11;
        }
      }
      else
      {
        ATL::CComBSTR::operator=(v17, L"Timestamp");
        ATL::CComBSTR::operator=(&v17[1], &LocaleName);
        CurrentUTCTimeString = GetCurrentUTCTimeString(&v17[1]);
        if ( CurrentUTCTimeString < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          LODWORD(v16) = CurrentUTCTimeString;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            (unsigned int)&WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids,
            v11,
            (__int64)"GetCurrentUTCTimeString failed",
            v16);
        }
        v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
            v8 = 40;
            goto LABEL_11;
          }
        }
        else
        {
          ATL::CComBSTR::operator=(v17, L"RoleInstance");
          ATL::CComBSTR::operator=(&v17[1], &LocaleName);
          CurrentRoleInstance = GetCurrentRoleInstance(&v17[1]);
          if ( CurrentRoleInstance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
            LODWORD(v16) = CurrentRoleInstance;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              41,
              (unsigned int)&WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids,
              v13,
              (__int64)"GetCurrentRoleInstance failed",
              v16);
          }
          v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
          if ( v6 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
              v8 = 42;
              goto LABEL_11;
            }
          }
          else
          {
            ATL::CComBSTR::operator=(v17, L"LamportTimestamp");
            ATL::CComBSTR::operator=(&v17[1], L"0");
            v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
            if ( v6 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
                v8 = 43;
                goto LABEL_11;
              }
            }
            else
            {
              ATL::CComBSTR::operator=(v17, L"Component");
              ATL::CComBSTR::operator=(&v17[1], L"Client");
              v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)a2 + 32LL))(a2, v17);
              if ( v6 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
                  v8 = 44;
                  goto LABEL_11;
                }
              }
              else
              {
                v14 = SerializeToDiagnosticsEventJSON(a2, &v19);
                if ( v14 >= 0 )
                {
                  RdpWinDiagnosticsHttpManager::SendMessageW(
                    *(const unsigned __int16 *const *)(a1 + 48),
                    *(const unsigned __int16 *const *)(a1 + 56),
                    v19);
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
                  LODWORD(v16) = v14;
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    45,
                    (unsigned int)&WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids,
                    v15,
                    (__int64)"SerializeToDiagnosticsEventJSON failed",
                    v16);
                }
              }
            }
          }
        }
      }
    }
  }
  SysFreeString(v18);
  SysFreeString(v19);
  AttributeKeyValue::~AttributeKeyValue((AttributeKeyValue *)v17);
}

```

## disassembly

```asm
0x18008d58c  mov     rax, rsp
0x18008d58f  push    rbp
0x18008d590  push    rsi
0x18008d591  push    rdi
0x18008d592  push    r12
0x18008d594  push    r15
0x18008d596  mov     rbp, rsp
0x18008d599  sub     rsp, 80h
0x18008d5a0  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x18008d5a8  mov     [rax+18h], rbx
0x18008d5ac  mov     rax, cs:__security_cookie
0x18008d5b3  xor     rax, rsp
0x18008d5b6  mov     [rbp+var_10], rax
0x18008d5ba  mov     rbx, rdx
0x18008d5bd  mov     rsi, rcx
0x18008d5c0  xorps   xmm0, xmm0
0x18008d5c3  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18008d5c8  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x18008d5cc  mov     [rbp+var_38], 0
0x18008d5d4  mov     [rbp+var_40], 0
0x18008d5dc  lea     rcx, [rbp+pguid]; pguid
0x18008d5e0  call    cs:__imp_CoCreateGuid
0x18008d5e6  mov     edi, eax
0x18008d5e8  lea     r12, WPP_7ef26a53edb436c2b1b0889c07de6fce_Traceguids
0x18008d5ef  lea     r15, WPP_GLOBAL_Control
0x18008d5f6  test    eax, eax
0x18008d5f8  jns     short loc_18008D642
0x18008d5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d601  cmp     rcx, r15
0x18008d604  jz      short loc_18008D642
0x18008d606  test    byte ptr [rcx+1Ch], 8
0x18008d60a  jz      short loc_18008D642
0x18008d60c  cmp     byte ptr [rcx+19h], 2
0x18008d610  jb      short loc_18008D642
0x18008d612  call    RdpX_GetActivityIdPrefix
0x18008d617  mov     edx, 23h ; '#'
0x18008d61c  mov     dword ptr [rsp+80h+var_58], edi
0x18008d620  lea     rcx, aCocreateguidFa; "CoCreateGuid failed"
0x18008d627  mov     [rsp+80h+var_60], rcx
0x18008d62c  mov     r9d, eax
0x18008d62f  mov     r8, r12
0x18008d632  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d639  mov     rcx, [rcx+10h]
0x18008d63d  call    WPP_SF_DsD
0x18008d642  lea     rdx, aId; "Id"
0x18008d649  lea     rcx, [rbp+var_50]
0x18008d64d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d652  lea     rdx, [rbp+pguid]; struct _GUID *
0x18008d656  lea     rcx, [rbp+bstrString]; this
0x18008d65a  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x18008d65f  nop
0x18008d660  lea     rdx, [rbp+bstrString]
0x18008d664  lea     rcx, [rbp+var_50+8]
0x18008d668  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18008d66d  nop
0x18008d66e  mov     rcx, [rbp+bstrString]; bstrString
0x18008d672  call    cs:__imp_SysFreeString
0x18008d678  mov     rax, [rbx]
0x18008d67b  lea     rdx, [rbp+var_50]
0x18008d67f  mov     rcx, rbx
0x18008d682  mov     rax, [rax+20h]
0x18008d686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d68b  mov     edi, eax
0x18008d68d  test    eax, eax
0x18008d68f  jz      short loc_18008D6E2
0x18008d691  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d698  cmp     rcx, r15
0x18008d69b  jz      loc_18008DAA5
0x18008d6a1  test    byte ptr [rcx+1Ch], 1
0x18008d6a5  jz      loc_18008DAA5
0x18008d6ab  cmp     byte ptr [rcx+19h], 2
0x18008d6af  jb      loc_18008DAA5
0x18008d6b5  call    RdpX_GetActivityIdPrefix
0x18008d6ba  mov     edx, 24h ; '$'
0x18008d6bf  mov     dword ptr [rsp+80h+var_58], edi
0x18008d6c3  mov     dword ptr [rsp+80h+var_60], edi
0x18008d6c7  mov     r9d, eax
0x18008d6ca  mov     r8, r12
0x18008d6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d6d4  mov     rcx, [rcx+10h]
0x18008d6d8  call    WPP_SF_DLD
0x18008d6dd  jmp     loc_18008DAA5
0x18008d6e2  lea     rdx, aActivityid; "ActivityId"
0x18008d6e9  lea     rcx, [rbp+var_50]
0x18008d6ed  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d6f2  lea     rdx, [rsi+40h]
0x18008d6f6  lea     rcx, [rbp+var_50+8]
0x18008d6fa  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18008d6ff  mov     rax, [rbx]
0x18008d702  lea     rdx, [rbp+var_50]
0x18008d706  mov     rcx, rbx
0x18008d709  mov     rax, [rax+20h]
0x18008d70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d712  mov     edi, eax
0x18008d714  test    eax, eax
0x18008d716  jz      short loc_18008D74B
0x18008d718  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d71f  cmp     rcx, r15
0x18008d722  jz      loc_18008DAA5
0x18008d728  test    byte ptr [rcx+1Ch], 1
0x18008d72c  jz      loc_18008DAA5
0x18008d732  cmp     byte ptr [rcx+19h], 2
0x18008d736  jb      loc_18008DAA5
0x18008d73c  call    RdpX_GetActivityIdPrefix
0x18008d741  mov     edx, 25h ; '%'
0x18008d746  jmp     loc_18008D6BF
0x18008d74b  lea     rdx, aActivityhint; "ActivityHint"
0x18008d752  lea     rcx, [rbp+var_50]
0x18008d756  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d75b  lea     rdx, aMsWvdHp; "ms-wvd-hp:"
0x18008d762  lea     rcx, [rbp+var_40]
0x18008d766  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d76b  mov     rdx, [rsi+50h]; unsigned __int16 *
0x18008d76f  lea     rcx, [rbp+var_40]; this
0x18008d773  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x18008d778  test    eax, eax
0x18008d77a  jns     short loc_18008D784
0x18008d77c  mov     ecx, eax; int
0x18008d77e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008d784  lea     rdx, [rbp+var_40]
0x18008d788  lea     rcx, [rbp+var_50+8]
0x18008d78c  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18008d791  mov     rax, [rbx]
0x18008d794  lea     rdx, [rbp+var_50]
0x18008d798  mov     rcx, rbx
0x18008d79b  mov     rax, [rax+20h]
0x18008d79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d7a4  mov     edi, eax
0x18008d7a6  test    eax, eax
0x18008d7a8  jz      short loc_18008D7DD
0x18008d7aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d7b1  cmp     rcx, r15
0x18008d7b4  jz      loc_18008DAA5
0x18008d7ba  test    byte ptr [rcx+1Ch], 1
0x18008d7be  jz      loc_18008DAA5
0x18008d7c4  cmp     byte ptr [rcx+19h], 2
0x18008d7c8  jb      loc_18008DAA5
0x18008d7ce  call    RdpX_GetActivityIdPrefix
0x18008d7d3  mov     edx, 26h ; '&'
0x18008d7d8  jmp     loc_18008D6BF
0x18008d7dd  lea     rdx, aTimestamp; "Timestamp"
0x18008d7e4  lea     rcx, [rbp+var_50]
0x18008d7e8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d7ed  lea     rdx, LocaleName
0x18008d7f4  lea     rcx, [rbp+var_50+8]
0x18008d7f8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d7fd  lea     rcx, [rbp+var_50+8]; unsigned __int16 **
0x18008d801  call    ?GetCurrentUTCTimeString@@YAJPEAPEAG@Z; GetCurrentUTCTimeString(ushort * *)
0x18008d806  mov     edi, eax
0x18008d808  test    eax, eax
0x18008d80a  jns     short loc_18008D854
0x18008d80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d813  cmp     rcx, r15
0x18008d816  jz      short loc_18008D854
0x18008d818  test    byte ptr [rcx+1Ch], 8
0x18008d81c  jz      short loc_18008D854
0x18008d81e  cmp     byte ptr [rcx+19h], 2
0x18008d822  jb      short loc_18008D854
0x18008d824  call    RdpX_GetActivityIdPrefix
0x18008d829  mov     edx, 27h ; '''
0x18008d82e  mov     dword ptr [rsp+80h+var_58], edi
0x18008d832  lea     rcx, aGetcurrentutct; "GetCurrentUTCTimeString failed"
0x18008d839  mov     [rsp+80h+var_60], rcx
0x18008d83e  mov     r9d, eax
0x18008d841  mov     r8, r12
0x18008d844  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d84b  mov     rcx, [rcx+10h]
0x18008d84f  call    WPP_SF_DsD
0x18008d854  mov     rax, [rbx]
0x18008d857  lea     rdx, [rbp+var_50]
0x18008d85b  mov     rcx, rbx
0x18008d85e  mov     rax, [rax+20h]
0x18008d862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d867  mov     edi, eax
0x18008d869  test    eax, eax
0x18008d86b  jz      short loc_18008D8A0
0x18008d86d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d874  cmp     rcx, r15
0x18008d877  jz      loc_18008DAA5
0x18008d87d  test    byte ptr [rcx+1Ch], 1
0x18008d881  jz      loc_18008DAA5
0x18008d887  cmp     byte ptr [rcx+19h], 2
0x18008d88b  jb      loc_18008DAA5
0x18008d891  call    RdpX_GetActivityIdPrefix
0x18008d896  mov     edx, 28h ; '('
0x18008d89b  jmp     loc_18008D6BF
0x18008d8a0  lea     rdx, aRoleinstance; "RoleInstance"
0x18008d8a7  lea     rcx, [rbp+var_50]
0x18008d8ab  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d8b0  lea     rdx, LocaleName
0x18008d8b7  lea     rcx, [rbp+var_50+8]
0x18008d8bb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d8c0  lea     rcx, [rbp+var_50+8]; unsigned __int16 **
0x18008d8c4  call    ?GetCurrentRoleInstance@@YAJPEAPEAG@Z; GetCurrentRoleInstance(ushort * *)
0x18008d8c9  mov     edi, eax
0x18008d8cb  test    eax, eax
0x18008d8cd  jns     short loc_18008D917
0x18008d8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d8d6  cmp     rcx, r15
0x18008d8d9  jz      short loc_18008D917
0x18008d8db  test    byte ptr [rcx+1Ch], 8
0x18008d8df  jz      short loc_18008D917
0x18008d8e1  cmp     byte ptr [rcx+19h], 2
0x18008d8e5  jb      short loc_18008D917
0x18008d8e7  call    RdpX_GetActivityIdPrefix
0x18008d8ec  mov     edx, 29h ; ')'
0x18008d8f1  mov     dword ptr [rsp+80h+var_58], edi
0x18008d8f5  lea     rcx, aGetcurrentrole; "GetCurrentRoleInstance failed"
0x18008d8fc  mov     [rsp+80h+var_60], rcx
0x18008d901  mov     r9d, eax
0x18008d904  mov     r8, r12
0x18008d907  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d90e  mov     rcx, [rcx+10h]
0x18008d912  call    WPP_SF_DsD
0x18008d917  mov     rax, [rbx]
0x18008d91a  lea     rdx, [rbp+var_50]
0x18008d91e  mov     rcx, rbx
0x18008d921  mov     rax, [rax+20h]
0x18008d925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d92a  mov     edi, eax
0x18008d92c  test    eax, eax
0x18008d92e  jz      short loc_18008D963
0x18008d930  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d937  cmp     rcx, r15
0x18008d93a  jz      loc_18008DAA5
0x18008d940  test    byte ptr [rcx+1Ch], 1
0x18008d944  jz      loc_18008DAA5
0x18008d94a  cmp     byte ptr [rcx+19h], 2
0x18008d94e  jb      loc_18008DAA5
0x18008d954  call    RdpX_GetActivityIdPrefix
0x18008d959  mov     edx, 2Ah ; '*'
0x18008d95e  jmp     loc_18008D6BF
0x18008d963  lea     rdx, aLamporttimesta; "LamportTimestamp"
0x18008d96a  lea     rcx, [rbp+var_50]
0x18008d96e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d973  lea     rdx, a0; "0"
0x18008d97a  lea     rcx, [rbp+var_50+8]
0x18008d97e  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d983  mov     rax, [rbx]
0x18008d986  lea     rdx, [rbp+var_50]
0x18008d98a  mov     rcx, rbx
0x18008d98d  mov     rax, [rax+20h]
0x18008d991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d996  mov     edi, eax
0x18008d998  test    eax, eax
0x18008d99a  jz      short loc_18008D9CF
0x18008d99c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d9a3  cmp     rcx, r15
0x18008d9a6  jz      loc_18008DAA5
0x18008d9ac  test    byte ptr [rcx+1Ch], 1
0x18008d9b0  jz      loc_18008DAA5
0x18008d9b6  cmp     byte ptr [rcx+19h], 2
0x18008d9ba  jb      loc_18008DAA5
0x18008d9c0  call    RdpX_GetActivityIdPrefix
0x18008d9c5  mov     edx, 2Bh ; '+'
0x18008d9ca  jmp     loc_18008D6BF
0x18008d9cf  lea     rdx, aComponent; "Component"
0x18008d9d6  lea     rcx, [rbp+var_50]
0x18008d9da  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d9df  lea     rdx, aClient; "Client"
0x18008d9e6  lea     rcx, [rbp+var_50+8]
0x18008d9ea  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008d9ef  mov     rax, [rbx]
0x18008d9f2  lea     rdx, [rbp+var_50]
0x18008d9f6  mov     rcx, rbx
0x18008d9f9  mov     rax, [rax+20h]
0x18008d9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008da02  mov     edi, eax
0x18008da04  test    eax, eax
0x18008da06  jz      short loc_18008DA37
0x18008da08  mov     rcx, cs:WPP_GLOBAL_Control
0x18008da0f  cmp     rcx, r15
0x18008da12  jz      loc_18008DAA5
0x18008da18  test    byte ptr [rcx+1Ch], 1
0x18008da1c  jz      loc_18008DAA5
0x18008da22  cmp     byte ptr [rcx+19h], 2
0x18008da26  jb      short loc_18008DAA5
0x18008da28  call    RdpX_GetActivityIdPrefix
0x18008da2d  mov     edx, 2Ch ; ','
0x18008da32  jmp     loc_18008D6BF
0x18008da37  lea     rdx, [rbp+var_38]
0x18008da3b  mov     rcx, rbx
0x18008da3e  call    ?SerializeToDiagnosticsEventJSON@@YAJAEBV?$RdpXArray@UAttributeKeyValue@@$0BA@$0PPPPPPPO@@@PEAPEAG@Z; SerializeToDiagnosticsEventJSON(RdpXArray<AttributeKeyValue,16,4294967294> const &,ushort * *)
0x18008da43  mov     ebx, eax
0x18008da45  test    eax, eax
0x18008da47  jns     short loc_18008DA93
0x18008da49  mov     rcx, cs:WPP_GLOBAL_Control
0x18008da50  cmp     rcx, r15
0x18008da53  jz      short loc_18008DAA5
0x18008da55  test    byte ptr [rcx+1Ch], 8
0x18008da59  jz      short loc_18008DAA5
0x18008da5b  cmp     byte ptr [rcx+19h], 2
0x18008da5f  jb      short loc_18008DAA5
0x18008da61  call    RdpX_GetActivityIdPrefix
0x18008da66  mov     edx, 2Dh ; '-'
0x18008da6b  mov     dword ptr [rsp+80h+var_58], ebx
0x18008da6f  lea     rcx, aSerializetodia; "SerializeToDiagnosticsEventJSON failed"
0x18008da76  mov     [rsp+80h+var_60], rcx
0x18008da7b  mov     r9d, eax
0x18008da7e  mov     r8, r12
  ... truncated ...
```
