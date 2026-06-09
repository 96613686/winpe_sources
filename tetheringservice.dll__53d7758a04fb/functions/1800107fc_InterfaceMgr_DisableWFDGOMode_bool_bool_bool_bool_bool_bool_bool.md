# InterfaceMgr::DisableWFDGOMode(bool,bool,bool,bool,bool,bool,bool)

- ea: `0x1800107fc`
- end: `0x180010a2d`
- name: `?DisableWFDGOMode@InterfaceMgr@@AEAAJ_N000000@Z`
- size: `561`
- prototype: `__int64 __fastcall(InterfaceMgr *this, bool, bool, char, bool, bool, bool, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180010660`
- `0x1800110d4`
- `0x180015e30`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x1800102b0`
- `0x1800107fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010950`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010950`
- `wlanapi!WlanNotifyVsIeProviderInt` at `0x1800108c0`
- `wlanapi!WlanNotifyVsIeProviderInt` at `0x1800108c0`
- `wlanapi!WFDCloseHandleInt` at `0x1800109ac`
- `wlanapi!WFDCloseHandleInt` at `0x1800109ac`
- `wlanapi!WiFiDisplayResetSinkStateInt` at `0x1800109d0`
- `wlanapi!WiFiDisplayResetSinkStateInt` at `0x1800109d0`

## string_xrefs

- `0x180010933`: `System\CurrentControlSet\Services\IcsSvc\Settings`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::DisableWFDGOMode(
        InterfaceMgr *this,
        bool a2,
        bool a3,
        char a4,
        bool a5,
        bool a6,
        bool a7,
        bool a8)
{
  TetheringServiceTelemetry *v12; // rcx
  bool v13; // zf
  unsigned int v14; // ebx
  signed int v15; // eax
  int pvData; // [rsp+50h] [rbp-78h] BYREF
  DWORD pcbData[3]; // [rsp+54h] [rbp-74h] BYREF
  __int128 v19; // [rsp+60h] [rbp-68h] BYREF
  __m128i si128; // [rsp+70h] [rbp-58h] BYREF

  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  v13 = *((_QWORD *)this + 7) == 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !v13 )
  {
    v14 = 0;
    v19 = TETHERING_IE_PROVIDER_GUID;
    v15 = WlanNotifyVsIeProviderInt(&v19, 16, &si128);
    if ( v15 )
    {
      v14 = v15 > 0 ? (unsigned __int16)v15 | 0x80070000 : v15;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v14);
      }
    }
    if ( a4 )
    {
      pvData = 0;
      pcbData[0] = 4;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\IcsSvc\\Settings",
              L"Set80211Rate",
              0x10u,
              0,
              &pvData,
              pcbData) )
        a4 = pvData != 0 ? a4 : 0;
    }
    InterfaceMgr::CleanupWfdConnect(this, *((void **)this + 7), a2, a3, a4, a5, a6, a7, a8);
    WFDCloseHandleInt(*((_QWORD *)this + 7));
    *((_QWORD *)this + 7) = 0;
    goto LABEL_19;
  }
  v14 = 1;
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v12 + 2), 77, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
LABEL_19:
    v12 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 25) )
  {
    WiFiDisplayResetSinkStateInt(*((_QWORD *)this + 25));
    *((_QWORD *)this + 25) = 0;
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v12 + 2), 79, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x1800107fc  push    rbx
0x1800107fe  push    rbp
0x1800107ff  push    rsi
0x180010800  push    rdi
0x180010801  push    r12
0x180010803  push    r14
0x180010805  sub     rsp, 98h
0x18001080c  mov     rax, cs:__security_cookie
0x180010813  xor     rax, rsp
0x180010816  mov     [rsp+0C8h+var_48], rax
0x18001081e  mov     sil, r9b
0x180010821  mov     bpl, r8b
0x180010824  mov     r14b, dl
0x180010827  mov     rdi, rcx
0x18001082a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010831  lea     r12, WPP_GLOBAL_Control
0x180010838  cmp     rcx, r12
0x18001083b  jz      short loc_18001085F
0x18001083d  test    byte ptr [rcx+1Ch], 8
0x180010841  jz      short loc_18001085F
0x180010843  mov     rcx, [rcx+10h]
0x180010847  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001084e  mov     edx, 4Ch ; 'L'
0x180010853  call    WPP_SF_
0x180010858  mov     rcx, cs:WPP_GLOBAL_Control
0x18001085f  cmp     qword ptr [rdi+38h], 0
0x180010864  movdqa  xmm0, cs:__xmm@00000000000000000000000000000001
0x18001086c  movdqu  [rsp+0C8h+var_58], xmm0
0x180010872  jnz     short loc_1800108A4
0x180010874  mov     ebx, 1
0x180010879  cmp     rcx, r12
0x18001087c  jz      loc_1800109C1
0x180010882  test    byte ptr [rcx+1Ch], 8
0x180010886  jz      loc_1800109C1
0x18001088c  mov     rcx, [rcx+10h]
0x180010890  lea     edx, [rbx+4Ch]
0x180010893  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x18001089a  call    WPP_SF_
0x18001089f  jmp     loc_1800109BA
0x1800108a4  movups  xmm0, cs:TETHERING_IE_PROVIDER_GUID
0x1800108ab  xor     ebx, ebx
0x1800108ad  lea     r8, [rsp+0C8h+var_58]
0x1800108b2  lea     rcx, [rsp+0C8h+var_68]
0x1800108b7  movdqu  [rsp+0C8h+var_68], xmm0
0x1800108bd  lea     edx, [rbx+10h]
0x1800108c0  call    cs:__imp_WlanNotifyVsIeProviderInt
0x1800108c6  test    eax, eax
0x1800108c8  jz      short loc_180010903
0x1800108ca  jg      short loc_1800108D0
0x1800108cc  mov     ebx, eax
0x1800108ce  jmp     short loc_1800108D9
0x1800108d0  movzx   ebx, ax
0x1800108d3  or      ebx, 80070000h
0x1800108d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108e0  cmp     rcx, r12
0x1800108e3  jz      short loc_180010903
0x1800108e5  test    byte ptr [rcx+1Ch], 1
0x1800108e9  jz      short loc_180010903
0x1800108eb  mov     rcx, [rcx+10h]
0x1800108ef  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x1800108f6  mov     edx, 4Eh ; 'N'
0x1800108fb  mov     r9d, ebx
0x1800108fe  call    WPP_SF_d
0x180010903  test    sil, sil
0x180010906  jz      short loc_180010965
0x180010908  lea     rax, [rsp+0C8h+var_74]
0x18001090d  mov     [rsp+0C8h+var_78], 0
0x180010915  mov     [rsp+0C8h+pcbData], rax; pcbData
0x18001091a  lea     r8, Value; "Set80211Rate"
0x180010921  lea     rax, [rsp+0C8h+var_78]
0x180010926  mov     [rsp+0C8h+var_74], 4
0x18001092e  mov     [rsp+0C8h+pvData], rax; pvData
0x180010933  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ic"...
0x18001093a  mov     r9d, 10h; dwFlags
0x180010940  mov     [rsp+0C8h+pdwType], 0; pdwType
0x180010949  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180010950  call    cs:__imp_RegGetValueW
0x180010956  test    eax, eax
0x180010958  jnz     short loc_180010965
0x18001095a  mov     eax, [rsp+0C8h+var_78]
0x18001095e  neg     eax
0x180010960  sbb     cl, cl
0x180010962  and     sil, cl
0x180010965  mov     al, [rsp+0C8h+arg_38]
0x18001096c  mov     r9b, bpl; bool
0x18001096f  mov     rdx, [rdi+38h]; void *
0x180010973  mov     r8b, r14b; bool
0x180010976  mov     [rsp+0C8h+var_88], al; bool
0x18001097a  mov     rcx, rdi; this
0x18001097d  mov     al, [rsp+0C8h+arg_30]
0x180010984  mov     [rsp+0C8h+var_90], al; bool
0x180010988  mov     al, [rsp+0C8h+arg_28]
0x18001098f  mov     byte ptr [rsp+0C8h+pcbData], al; bool
0x180010993  mov     al, [rsp+0C8h+arg_20]
0x18001099a  mov     byte ptr [rsp+0C8h+pvData], al; bool
0x18001099e  mov     byte ptr [rsp+0C8h+pdwType], sil; bool
0x1800109a3  call    ?CleanupWfdConnect@InterfaceMgr@@AEAAXPEAX_N111111@Z; InterfaceMgr::CleanupWfdConnect(void *,bool,bool,bool,bool,bool,bool,bool)
0x1800109a8  mov     rcx, [rdi+38h]
0x1800109ac  call    cs:__imp_WFDCloseHandleInt
0x1800109b2  mov     qword ptr [rdi+38h], 0
0x1800109ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109c1  mov     rax, [rdi+0C8h]
0x1800109c8  test    rax, rax
0x1800109cb  jz      short loc_1800109E8
0x1800109cd  mov     rcx, rax
0x1800109d0  call    cs:__imp_WiFiDisplayResetSinkStateInt
0x1800109d6  mov     qword ptr [rdi+0C8h], 0
0x1800109e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109e8  cmp     rcx, r12
0x1800109eb  jz      short loc_180010A0B
0x1800109ed  test    byte ptr [rcx+1Ch], 8
0x1800109f1  jz      short loc_180010A0B
0x1800109f3  mov     rcx, [rcx+10h]
0x1800109f7  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x1800109fe  mov     edx, 4Fh ; 'O'
0x180010a03  mov     r9d, ebx
0x180010a06  call    WPP_SF_d
0x180010a0b  mov     eax, ebx
0x180010a0d  mov     rcx, [rsp+0C8h+var_48]
0x180010a15  xor     rcx, rsp; StackCookie
0x180010a18  call    __security_check_cookie
0x180010a1d  add     rsp, 98h
0x180010a24  pop     r14
0x180010a26  pop     r12
0x180010a28  pop     rdi
0x180010a29  pop     rsi
0x180010a2a  pop     rbp
0x180010a2b  pop     rbx
0x180010a2c  retn
```
