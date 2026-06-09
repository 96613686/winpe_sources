# handlerLaunchThirdPartyDirect(HWND__ *,SecurityLogicState *)

- ea: `0x180007938`
- end: `0x180007aff`
- name: `?handlerLaunchThirdPartyDirect@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@@Z`
- size: `455`
- prototype: `bool __fastcall(HWND, struct SecurityLogicState *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006520`
- `0x180007854`

## callees

- `0x180001034`
- `0x18000112c`
- `0x180001b90`
- `0x180006fec`
- `0x18000750c`
- `0x180007938`
- `0x18000811c`
- `0x180008d98`
- `0x18000917c`
- `0x180009988`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800079a8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800079a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800079f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall handlerLaunchThirdPartyDirect(HWND a1, LPCWSTR *a2)
{
  char v4; // si
  char *FileW; // r14
  int v6; // eax
  int v7; // r9d
  HWND v8; // rcx
  __int64 v9; // r8
  unsigned int ProductNotification; // eax
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v18; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v19; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(Dst, 0, 0x208u);
  v16 = 0;
  GetApplicationParameters(&v17, *((unsigned int *)a2 + 22), *((unsigned int *)a2 + 2));
  v4 = 0;
  if ( !ExpandEnvironmentStringsW(a2[9], Dst, 0x104u) )
  {
    ShowThirdPartyExeError(a1, a2, 2);
    goto LABEL_13;
  }
  FileW = (char *)CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_13;
  v6 = CheckTrust(Dst, &v16);
  v8 = a1;
  if ( v6 < 0 )
  {
    v9 = 0;
    goto LABEL_9;
  }
  if ( !LaunchProgram(a1, Dst, v17, v7) )
  {
    v9 = 2;
    v8 = a1;
LABEL_9:
    ShowThirdPartyExeError(v8, a2, v9);
    goto LABEL_10;
  }
  v4 = 1;
LABEL_10:
  if ( v16 )
    FreeWVTStateData(v16);
  CloseHandle(FileW);
LABEL_13:
  ProductNotification = ExtractProductNotification(*((unsigned int *)a2 + 22));
  if ( ProductNotification
    && (unsigned int)dword_180014060 > 5
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180014060, v11, ProductNotification) )
  {
    LODWORD(v16) = v13;
    v18 = a2[9];
    v19 = a2[8];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&unk_1800106C1,
      v13,
      v14,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v16);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 12));
  return v4;
}

```

## disassembly

```asm
0x180007938  mov     [rsp-8+arg_10], rbx
0x18000793d  mov     [rsp-8+arg_18], rsi
0x180007942  push    rbp
0x180007943  push    rdi
0x180007944  push    r14
0x180007946  lea     rbp, [rsp-180h]
0x18000794e  sub     rsp, 280h
0x180007955  mov     rax, cs:__security_cookie
0x18000795c  xor     rax, rsp
0x18000795f  mov     [rbp+190h+var_20], rax
0x180007966  mov     rbx, rdx
0x180007969  mov     rdi, rcx
0x18000796c  xor     edx, edx; Val
0x18000796e  mov     r8d, 208h; Size
0x180007974  lea     rcx, [rsp+290h+Dst]; void *
0x180007979  call    memset_0
0x18000797e  mov     [rsp+290h+var_250], 0
0x180007987  mov     r8d, [rbx+8]
0x18000798b  mov     edx, [rbx+58h]
0x18000798e  lea     rcx, [rsp+290h+var_248]
0x180007993  call    ?GetApplicationParameters@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KW4SecurityType@@@Z; GetApplicationParameters(ulong,SecurityType)
0x180007998  nop
0x180007999  mov     r8d, 104h; nSize
0x18000799f  lea     rdx, [rsp+290h+Dst]; lpDst
0x1800079a4  mov     rcx, [rbx+48h]; lpSrc
0x1800079a8  call    cs:__imp_ExpandEnvironmentStringsW
0x1800079ae  xor     sil, sil
0x1800079b1  test    eax, eax
0x1800079b3  jnz     short loc_1800079C9
0x1800079b5  lea     r8d, [rax+2]
0x1800079b9  mov     rdx, rbx
0x1800079bc  mov     rcx, rdi
0x1800079bf  call    ?ShowThirdPartyExeError@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4ThirdPartyExeError@@@Z; ShowThirdPartyExeError(HWND__ *,SecurityLogicState *,ThirdPartyExeError)
0x1800079c4  jmp     loc_180007A62
0x1800079c9  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x1800079d2  mov     [rsp+290h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800079da  mov     [rsp+290h+dwCreationDisposition], 3; dwCreationDisposition
0x1800079e2  xor     r9d, r9d; lpSecurityAttributes
0x1800079e5  mov     edx, 80000000h; dwDesiredAccess
0x1800079ea  lea     r8d, [r9+1]; dwShareMode
0x1800079ee  lea     rcx, [rsp+290h+Dst]; lpFileName
0x1800079f3  call    cs:__imp_CreateFileW
0x1800079f9  mov     r14, rax
0x1800079fc  lea     rcx, [rax-1]
0x180007a00  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007a04  ja      short loc_180007A62
0x180007a06  lea     rdx, [rsp+290h+var_250]; void **
0x180007a0b  lea     rcx, [rsp+290h+Dst]; unsigned __int16 *
0x180007a10  call    ?CheckTrust@@YAJPEBGAEAPEAX@Z; CheckTrust(ushort const *,void * &)
0x180007a15  mov     rcx, rdi; HWND
0x180007a18  test    eax, eax
0x180007a1a  js      short loc_180007A3F
0x180007a1c  mov     r8, [rsp+290h+var_248]; unsigned __int16 *
0x180007a21  lea     rdx, [rsp+290h+Dst]; unsigned __int16 *
0x180007a26  call    ?LaunchProgram@@YA_NPEAUHWND__@@PEBG1H@Z; LaunchProgram(HWND__ *,ushort const *,ushort const *,int)
0x180007a2b  test    al, al
0x180007a2d  jz      short loc_180007A34
0x180007a2f  mov     sil, 1
0x180007a32  jmp     short loc_180007A4A
0x180007a34  mov     r8d, 2
0x180007a3a  mov     rcx, rdi
0x180007a3d  jmp     short loc_180007A42
0x180007a3f  xor     r8d, r8d
0x180007a42  mov     rdx, rbx
0x180007a45  call    ?ShowThirdPartyExeError@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4ThirdPartyExeError@@@Z; ShowThirdPartyExeError(HWND__ *,SecurityLogicState *,ThirdPartyExeError)
0x180007a4a  mov     rcx, [rsp+290h+var_250]; void *
0x180007a4f  test    rcx, rcx
0x180007a52  jz      short loc_180007A59
0x180007a54  call    ?FreeWVTStateData@@YAJPEAX@Z; FreeWVTStateData(void *)
0x180007a59  mov     rcx, r14; hObject
0x180007a5c  call    cs:__imp_CloseHandle
0x180007a62  mov     ecx, [rbx+58h]
0x180007a65  call    ?ExtractProductNotification@@YA?AW4ProductNotification@@K@Z; ExtractProductNotification(ulong)
0x180007a6a  mov     r8d, eax
0x180007a6d  test    eax, eax
0x180007a6f  jz      short loc_180007AC7
0x180007a71  mov     ecx, cs:dword_180014060
0x180007a77  cmp     ecx, 5
0x180007a7a  jbe     short loc_180007AC7
0x180007a7c  call    _tlgKeywordOn
0x180007a81  test    al, al
0x180007a83  jz      short loc_180007AC7
0x180007a85  mov     dword ptr [rsp+290h+var_250], r8d
0x180007a8a  mov     rax, [rbx+48h]
0x180007a8e  mov     [rsp+290h+var_240], rax
0x180007a93  mov     rax, [rbx+40h]
0x180007a97  mov     [rsp+290h+var_238], rax
0x180007a9c  lea     rax, [rsp+290h+var_250]
0x180007aa1  mov     [rsp+290h+hTemplateFile], rax
0x180007aa6  lea     rax, [rsp+290h+var_240]
0x180007aab  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rax
0x180007ab0  lea     rax, [rsp+290h+var_238]
0x180007ab5  mov     qword ptr [rsp+290h+dwCreationDisposition], rax
0x180007aba  lea     rdx, unk_1800106C1
0x180007ac1  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180007ac6  nop
0x180007ac7  mov     rcx, [rsp+290h+var_248]
0x180007acc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007ad0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007ad5  mov     al, sil
0x180007ad8  mov     rcx, [rbp+190h+var_20]
0x180007adf  xor     rcx, rsp; StackCookie
0x180007ae2  call    __security_check_cookie
0x180007ae7  lea     r11, [rsp+290h+var_10]
0x180007aef  mov     rbx, [r11+30h]
0x180007af3  mov     rsi, [r11+38h]
0x180007af7  mov     rsp, r11
0x180007afa  pop     r14
0x180007afc  pop     rdi
0x180007afd  pop     rbp
0x180007afe  retn
```
