# CExtraClocksDlg::_OnApply(void)

- ea: `0x1800100c4`
- end: `0x1800101ed`
- name: `?_OnApply@CExtraClocksDlg@@AEAAHXZ`
- size: `297`
- prototype: `__int64 __fastcall(CExtraClocksDlg *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800103a0`

## callees

- `0x180004da4`
- `0x1800085b8`
- `0x18000c220`
- `0x18000f70c`
- `0x18000f8e0`
- `0x18000f90c`
- `0x1800100c4`
- `0x180028f60`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x18001014a`
- `ntdll!WinSqmIsOptedIn` at `0x18001014a`
- `ntdll!WinSqmSetString` at `0x180010169`
- `ntdll!WinSqmSetString` at `0x180010188`
- `ntdll!WinSqmSetString` at `0x180010169`
- `ntdll!WinSqmSetString` at `0x180010188`
- `ntdll!WinSqmSetDWORD` at `0x180010198`
- `ntdll!WinSqmSetDWORD` at `0x180010198`

## pseudocode

```c
__int64 __fastcall CExtraClocksDlg::_OnApply(CExtraClocksDlg *this)
{
  unsigned int v2; // esi
  unsigned int v3; // ebp
  unsigned int v4; // edi
  __int64 v5; // r14
  int v6; // eax
  unsigned int v7; // edi
  _QWORD v9[42]; // [rsp+20h] [rbp-198h] BYREF

  v2 = 0;
  v3 = 0;
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "SetAdditionalClockSettings");
  v9[0] = &TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::`vftable';
  TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StartActivity((TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *)v9);
  v4 = 0;
  do
  {
    v5 = 304LL * v4++;
    if ( *(_DWORD *)((char *)this + v5 + 32) )
    {
      v6 = SetExtraTzInformation(v4, (CExtraClocksDlg *)((char *)this + v5 + 36));
      *(_DWORD *)((char *)this + v5 + 32) = 0;
      if ( !v6 )
        v2 = 1;
    }
  }
  while ( v4 < 2 );
  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    v7 = 0;
    if ( *((_DWORD *)this + 17) )
    {
      v7 = 1;
      WinSqmSetString(0, 6688, (char *)this + 72);
    }
    if ( *((_DWORD *)this + 93) )
    {
      ++v7;
      WinSqmSetString(0, 6689, (char *)this + 376);
    }
    WinSqmSetDWORD(0, 6690, v7);
  }
  if ( v2 )
  {
    v3 = -2147467259;
    ShowErrorMessage(*((HWND *)this + 1), 54);
  }
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v9, v3);
  TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::~SetAdditionalClockSettings((TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings *)v9);
  return v2;
}

```

## disassembly

```asm
0x1800100c4  push    rbx
0x1800100c6  push    rbp
0x1800100c7  push    rsi
0x1800100c8  push    rdi
0x1800100c9  push    r12
0x1800100cb  push    r14
0x1800100cd  sub     rsp, 188h
0x1800100d4  mov     rax, cs:__security_cookie
0x1800100db  xor     rax, rsp
0x1800100de  mov     [rsp+1B8h+var_48], rax
0x1800100e6  mov     rbx, rcx
0x1800100e9  lea     rdx, aSetadditionalc; "SetAdditionalClockSettings"
0x1800100f0  lea     rcx, [rsp+1B8h+var_198]
0x1800100f5  xor     esi, esi
0x1800100f7  xor     ebp, ebp
0x1800100f9  call    ??0?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800100fe  lea     rax, ??_7SetAdditionalClockSettings@TimeDateTraceLoggingTelemetry@@6B@; const TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::`vftable'
0x180010105  lea     rcx, [rsp+1B8h+var_198]; this
0x18001010a  mov     [rsp+1B8h+var_198], rax
0x18001010f  call    ?StartActivity@SetAdditionalClockSettings@TimeDateTraceLoggingTelemetry@@QEAAXXZ; TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::StartActivity(void)
0x180010114  xor     edi, edi
0x180010116  lea     r12d, [rsi+1]
0x18001011a  mov     eax, edi
0x18001011c  imul    r14, rax, 130h
0x180010123  inc     edi
0x180010125  cmp     [r14+rbx+20h], ebp
0x18001012a  jz      short loc_180010145
0x18001012c  lea     rdx, [rbx+24h]
0x180010130  mov     ecx, edi; unsigned int
0x180010132  add     rdx, r14; struct EXTRATZINFO *
0x180010135  call    ?SetExtraTzInformation@@YAHIPEBUEXTRATZINFO@@@Z; SetExtraTzInformation(uint,EXTRATZINFO const *)
0x18001013a  test    eax, eax
0x18001013c  mov     [r14+rbx+20h], ebp
0x180010141  cmovz   esi, r12d
0x180010145  cmp     edi, 2
0x180010148  jb      short loc_18001011A
0x18001014a  call    cs:__imp_WinSqmIsOptedIn
0x180010150  test    eax, eax
0x180010152  jz      short loc_18001019E
0x180010154  xor     edi, edi
0x180010156  cmp     [rbx+44h], edi
0x180010159  jz      short loc_18001016F
0x18001015b  lea     r8, [rbx+48h]
0x18001015f  mov     edx, 1A20h
0x180010164  xor     ecx, ecx
0x180010166  mov     edi, r12d
0x180010169  call    cs:__imp_WinSqmSetString
0x18001016f  cmp     [rbx+174h], ebp
0x180010175  jz      short loc_18001018E
0x180010177  add     edi, r12d
0x18001017a  lea     r8, [rbx+178h]
0x180010181  mov     edx, 1A21h
0x180010186  xor     ecx, ecx
0x180010188  call    cs:__imp_WinSqmSetString
0x18001018e  mov     r8d, edi
0x180010191  mov     edx, 1A22h
0x180010196  xor     ecx, ecx
0x180010198  call    cs:__imp_WinSqmSetDWORD
0x18001019e  test    esi, esi
0x1800101a0  jz      short loc_1800101B5
0x1800101a2  mov     rcx, [rbx+8]; HWND
0x1800101a6  mov     edx, 36h ; '6'; int
0x1800101ab  mov     ebp, 80004005h
0x1800101b0  call    ?ShowErrorMessage@@YAXPEAUHWND__@@H@Z; ShowErrorMessage(HWND__ *,int)
0x1800101b5  mov     edx, ebp
0x1800101b7  lea     rcx, [rsp+1B8h+var_198]
0x1800101bc  call    ?Stop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800101c1  lea     rcx, [rsp+1B8h+var_198]; this
0x1800101c6  call    ??1SetAdditionalClockSettings@TimeDateTraceLoggingTelemetry@@QEAA@XZ; TimeDateTraceLoggingTelemetry::SetAdditionalClockSettings::~SetAdditionalClockSettings(void)
0x1800101cb  mov     eax, esi
0x1800101cd  mov     rcx, [rsp+1B8h+var_48]
0x1800101d5  xor     rcx, rsp; StackCookie
0x1800101d8  call    __security_check_cookie
0x1800101dd  add     rsp, 188h
0x1800101e4  pop     r14
0x1800101e6  pop     r12
0x1800101e8  pop     rdi
0x1800101e9  pop     rsi
0x1800101ea  pop     rbp
0x1800101eb  pop     rbx
0x1800101ec  retn
```
