# WlanLogConnectionFailureEvent(_GUID *,ushort *,void *,long,_WLAN_CONNECTION_NOTIFICATION_DATA_V3 *)

- ea: `0x180058698`
- end: `0x1800589c1`
- name: `?WlanLogConnectionFailureEvent@@YAKPEAU_GUID@@PEAGPEAXJPEAU_WLAN_CONNECTION_NOTIFICATION_DATA_V3@@@Z`
- size: `809`
- prototype: `unsigned int __fastcall(struct _GUID *, unsigned __int16 *, void *, int, struct _WLAN_CONNECTION_NOTIFICATION_DATA_V3 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a65b8`

## callees

- `0x180058698`
- `0x180058c70`
- `0x180058d08`
- `0x180058d90`
- `0x1800a0194`
- `0x180106340`
- `0x180107330`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800588b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800588b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800588ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800588ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800588c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800588c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180058982`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180058982`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18005895f`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18005895f`
- `OneX!OneXReasonCodeToString` at `0x1800588a3`
- `OneX!OneXReasonCodeToString` at `0x1800588a3`

## string_xrefs

- `0x1800588b2`: `wlansvc.dll`

## pseudocode

```c
__int64 __fastcall WlanLogConnectionFailureEvent(
        struct _GUID *a1,
        unsigned __int16 *a2,
        void *a3,
        int a4,
        struct _WLAN_CONNECTION_NOTIFICATION_DATA_V3 *a5)
{
  struct _WLAN_CONNECTION_NOTIFICATION_DATA_V3 *v5; // rsi
  __int64 v8; // rdi
  __int64 v9; // rax
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  UINT v14; // ecx
  DWORD LocalizedString; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  unsigned int *v22; // rsi
  unsigned int v23; // ebx
  DWORD LastError; // eax
  HMODULE phModule[2]; // [rsp+28h] [rbp-E0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-C0h]
  __int64 v29; // [rsp+50h] [rbp-B8h]
  _WORD *v30; // [rsp+58h] [rbp-B0h]
  __int64 v31; // [rsp+60h] [rbp-A8h]
  char *v32; // [rsp+68h] [rbp-A0h]
  __int64 v33; // [rsp+70h] [rbp-98h]
  _WORD *v34; // [rsp+78h] [rbp-90h]
  int v35; // [rsp+80h] [rbp-88h]
  int v36; // [rsp+84h] [rbp-84h]
  __int64 v37; // [rsp+88h] [rbp-80h]
  int v38; // [rsp+90h] [rbp-78h]
  int v39; // [rsp+94h] [rbp-74h]
  _WORD *v40; // [rsp+98h] [rbp-70h]
  int v41; // [rsp+A0h] [rbp-68h]
  int v42; // [rsp+A4h] [rbp-64h]
  unsigned int *v43; // [rsp+A8h] [rbp-60h]
  __int64 v44; // [rsp+B0h] [rbp-58h]
  void **v45; // [rsp+B8h] [rbp-50h]
  __int64 v46; // [rsp+C0h] [rbp-48h]
  int *v47; // [rsp+C8h] [rbp-40h]
  __int64 v48; // [rsp+D0h] [rbp-38h]
  _WORD v49[256]; // [rsp+D8h] [rbp-30h] BYREF
  _WORD v50[256]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _WORD v51[256]; // [rsp+4D8h] [rbp+3D0h] BYREF
  void *v52; // [rsp+718h] [rbp+610h] BYREF
  int v53; // [rsp+720h] [rbp+618h] BYREF

  v53 = a4;
  v52 = a3;
  v5 = a5;
  memset_0(v50, 0, sizeof(v50));
  memset_0(v49, 0, sizeof(v49));
  if ( !v5 || !a2 || !a1 )
    return 87;
  UserData.Ptr = (ULONGLONG)a1;
  v8 = -1;
  v9 = -1;
  *(_QWORD *)&UserData.Size = 16;
  v28 = a2;
  do
    ++v9;
  while ( a2[v9] );
  v10 = *(_DWORD *)v5;
  v29 = (unsigned int)(2 * v9 + 2);
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 == 1 )
          {
            v14 = 263;
            goto LABEL_16;
          }
          return 87;
        }
        v14 = 262;
      }
      else
      {
        v14 = 261;
      }
    }
    else
    {
      v14 = 260;
    }
  }
  else
  {
    v14 = 259;
  }
LABEL_16:
  LocalizedString = LoadLocalizedString(v14);
  if ( !LocalizedString )
  {
    v30 = v50;
    v16 = -1;
    do
      ++v16;
    while ( v50[v16] );
    v31 = (unsigned int)(2 * v16 + 2);
    v17 = -1;
    v32 = (char *)v5 + 4;
    do
      ++v17;
    while ( *((_WORD *)v5 + v17 + 2) );
    v33 = (unsigned int)(2 * v17 + 2);
    LODWORD(phModule[0]) = 256;
    WlanSsidToWideString((char *)v5 + 516, v51, phModule);
    v34 = v51;
    v18 = -1;
    do
      ++v18;
    while ( v51[v18] );
    v19 = *((unsigned int *)v5 + 138);
    v35 = 2 * v18 + 2;
    v36 = 0;
    v20 = Dot11BssTypeStr(v19);
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(v20 + 2 * v21) );
    v22 = (unsigned int *)((char *)v5 + 564);
    v37 = v20;
    v39 = 0;
    v38 = 2 * v21 + 2;
    phModule[0] = 0;
    v23 = *v22;
    if ( *v22 - 327680 > 0xFFFF )
    {
      if ( GetModuleHandleExW(0, L"wlansvc.dll", phModule) )
        LastError = AcmReasonCodeToString(phModule[0], v23, 256, v49);
      else
        LastError = GetLastError();
    }
    else
    {
      LastError = OneXReasonCodeToString(v23, 256, v49, 0);
    }
    LocalizedString = LastError;
    if ( phModule[0] )
      FreeLibrary(phModule[0]);
    if ( !LocalizedString )
    {
      v40 = v49;
      do
        ++v8;
      while ( v49[v8] );
      v41 = 2 * v8 + 2;
      v42 = 0;
      v45 = &v52;
      v47 = &v53;
      v43 = v22;
      v44 = 4;
      v46 = 8;
      v48 = 4;
      if ( EventEnabled(WLANSVC_EVT_GUID_Context, &WlansvcConnectionFailEvtDesc) )
        return EventWrite(WLANSVC_EVT_GUID_Context, &WlansvcConnectionFailEvtDesc, 0xAu, &UserData);
      else
        return 5023;
    }
  }
  return LocalizedString;
}

```

## disassembly

```asm
0x180058698  mov     rax, rsp
0x18005869b  mov     [rax+8], rbx
0x18005869f  mov     [rax+10h], rsi
0x1800586a3  mov     [rax+20h], r9d
0x1800586a7  mov     [rax+18h], r8
0x1800586ab  push    rbp
0x1800586ac  push    rdi
0x1800586ad  push    r14
0x1800586af  lea     rbp, [rax-5F8h]
0x1800586b6  sub     rsp, 6E0h
0x1800586bd  mov     rax, cs:__security_cookie
0x1800586c4  xor     rax, rsp
0x1800586c7  mov     [rbp+5F0h+var_20], rax
0x1800586ce  mov     rsi, [rbp+5F0h+arg_20]
0x1800586d5  mov     rbx, rdx
0x1800586d8  mov     rdi, rcx
0x1800586db  mov     r14d, 200h
0x1800586e1  mov     r8d, r14d; Size
0x1800586e4  lea     rcx, [rbp+5F0h+var_420]; void *
0x1800586eb  xor     edx, edx; Val
0x1800586ed  call    memset_0
0x1800586f2  mov     r8d, r14d; Size
0x1800586f5  lea     rcx, [rbp+5F0h+var_620]; void *
0x1800586f9  xor     edx, edx; Val
0x1800586fb  call    memset_0
0x180058700  xor     r14d, r14d
0x180058703  test    rsi, rsi
0x180058706  jz      loc_180058993
0x18005870c  test    rbx, rbx
0x18005870f  jz      loc_180058993
0x180058715  test    rdi, rdi
0x180058718  jz      loc_180058993
0x18005871e  mov     [rsp+6F0h+UserData.Ptr], rdi
0x180058723  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180058727  mov     rax, rdi
0x18005872a  mov     qword ptr [rsp+6F0h+UserData.Size], 10h
0x180058733  mov     [rsp+6F0h+var_6B0], rbx
0x180058738  inc     rax
0x18005873b  cmp     [rbx+rax*2], r14w
0x180058740  jnz     short loc_180058738
0x180058742  mov     ecx, [rsi]
0x180058744  lea     eax, ds:2[rax*2]
0x18005874b  mov     dword ptr [rsp+6F0h+var_6A8], eax
0x18005874f  mov     dword ptr [rsp+6F0h+var_6A8+4], r14d
0x180058754  test    ecx, ecx
0x180058756  jz      short loc_18005878C
0x180058758  sub     ecx, 1
0x18005875b  jz      short loc_180058785
0x18005875d  sub     ecx, 1
0x180058760  jz      short loc_18005877E
0x180058762  sub     ecx, 1
0x180058765  jz      short loc_180058777
0x180058767  cmp     ecx, 1
0x18005876a  jnz     loc_180058993
0x180058770  mov     ecx, 107h
0x180058775  jmp     short loc_180058791
0x180058777  mov     ecx, 106h
0x18005877c  jmp     short loc_180058791
0x18005877e  mov     ecx, 105h
0x180058783  jmp     short loc_180058791
0x180058785  mov     ecx, 104h
0x18005878a  jmp     short loc_180058791
0x18005878c  mov     ecx, 103h; uID
0x180058791  lea     r8, [rbp+5F0h+var_420]
0x180058798  call    LoadLocalizedString
0x18005879d  mov     ebx, eax
0x18005879f  test    eax, eax
0x1800587a1  jnz     loc_180058998
0x1800587a7  lea     rax, [rbp+5F0h+var_420]
0x1800587ae  mov     [rsp+6F0h+var_6A0], rax
0x1800587b3  lea     rcx, [rbp+5F0h+var_420]
0x1800587ba  mov     rax, rdi
0x1800587bd  inc     rax
0x1800587c0  cmp     [rcx+rax*2], r14w
0x1800587c5  jnz     short loc_1800587BD
0x1800587c7  lea     eax, ds:2[rax*2]
0x1800587ce  mov     dword ptr [rsp+6F0h+var_698+4], r14d
0x1800587d3  lea     rcx, [rsi+4]
0x1800587d7  mov     dword ptr [rsp+6F0h+var_698], eax
0x1800587db  mov     rax, rdi
0x1800587de  mov     [rsp+6F0h+var_690], rcx
0x1800587e3  inc     rax
0x1800587e6  cmp     [rcx+rax*2], r14w
0x1800587eb  jnz     short loc_1800587E3
0x1800587ed  lea     eax, ds:2[rax*2]
0x1800587f4  mov     dword ptr [rsp+6F0h+var_688+4], r14d
0x1800587f9  lea     rcx, [rsi+204h]
0x180058800  mov     dword ptr [rsp+6F0h+var_688], eax
0x180058804  lea     r8, [rsp+6F0h+phModule]
0x180058809  mov     dword ptr [rsp+6F0h+phModule], 100h
0x180058811  lea     rdx, [rbp+5F0h+var_220]
0x180058818  call    WlanSsidToWideString
0x18005881d  lea     rax, [rbp+5F0h+var_220]
0x180058824  mov     [rsp+6F0h+var_680], rax
0x180058829  lea     rcx, [rbp+5F0h+var_220]
0x180058830  mov     rax, rdi
0x180058833  inc     rax
0x180058836  cmp     [rcx+rax*2], r14w
0x18005883b  jnz     short loc_180058833
0x18005883d  mov     ecx, [rsi+228h]
0x180058843  lea     eax, ds:2[rax*2]
0x18005884a  mov     [rsp+6F0h+var_678], eax
0x18005884e  mov     [rsp+6F0h+var_674], r14d
0x180058853  call    Dot11BssTypeStr
0x180058858  mov     r8, rax
0x18005885b  mov     rax, rdi
0x18005885e  inc     rax
0x180058861  cmp     [r8+rax*2], r14w
0x180058866  jnz     short loc_18005885E
0x180058868  add     rsi, 234h
0x18005886f  mov     [rbp+5F0h+var_670], r8
0x180058873  lea     eax, ds:2[rax*2]
0x18005887a  mov     [rbp+5F0h+var_664], r14d
0x18005887e  mov     [rbp+5F0h+var_668], eax
0x180058881  mov     [rsp+6F0h+phModule], r14
0x180058886  mov     ebx, [rsi]
0x180058888  lea     eax, [rbx-50000h]
0x18005888e  cmp     eax, 0FFFFh
0x180058893  ja      short loc_1800588AB
0x180058895  xor     r9d, r9d
0x180058898  lea     r8, [rbp+5F0h+var_620]
0x18005889c  mov     edx, 100h
0x1800588a1  mov     ecx, ebx
0x1800588a3  call    cs:__imp_OneXReasonCodeToString
0x1800588a9  jmp     short loc_1800588E1
0x1800588ab  lea     r8, [rsp+6F0h+phModule]; phModule
0x1800588b0  xor     ecx, ecx; dwFlags
0x1800588b2  lea     rdx, ModuleName; "wlansvc.dll"
0x1800588b9  call    cs:__imp_GetModuleHandleExW
0x1800588bf  test    eax, eax
0x1800588c1  jnz     short loc_1800588CB
0x1800588c3  call    cs:__imp_GetLastError
0x1800588c9  jmp     short loc_1800588E1
0x1800588cb  mov     rcx, [rsp+6F0h+phModule]
0x1800588d0  lea     r9, [rbp+5F0h+var_620]
0x1800588d4  mov     r8d, 100h
0x1800588da  mov     edx, ebx
0x1800588dc  call    AcmReasonCodeToString
0x1800588e1  mov     rcx, [rsp+6F0h+phModule]; hLibModule
0x1800588e6  mov     ebx, eax
0x1800588e8  test    rcx, rcx
0x1800588eb  jz      short loc_1800588F3
0x1800588ed  call    cs:__imp_FreeLibrary
0x1800588f3  test    ebx, ebx
0x1800588f5  jnz     loc_180058998
0x1800588fb  lea     rax, [rbp+5F0h+var_620]
0x1800588ff  mov     [rbp+5F0h+var_660], rax
0x180058903  lea     rax, [rbp+5F0h+var_620]
0x180058907  inc     rdi
0x18005890a  cmp     [rax+rdi*2], r14w
0x18005890f  jnz     short loc_180058907
0x180058911  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180058918  lea     eax, ds:2[rdi*2]
0x18005891f  mov     [rbp+5F0h+var_658], eax
0x180058922  lea     rdx, WlansvcConnectionFailEvtDesc; EventDescriptor
0x180058929  lea     rax, [rbp+5F0h+arg_10]
0x180058930  mov     [rbp+5F0h+var_654], r14d
0x180058934  mov     [rbp+5F0h+var_640], rax
0x180058938  lea     rax, [rbp+5F0h+arg_18]
0x18005893f  mov     [rbp+5F0h+var_630], rax
0x180058943  mov     [rbp+5F0h+var_650], rsi
0x180058947  mov     [rbp+5F0h+var_648], 4
0x18005894f  mov     [rbp+5F0h+var_638], 8
0x180058957  mov     [rbp+5F0h+var_628], 4
0x18005895f  call    cs:__imp_EventEnabled
0x180058965  test    al, al
0x180058967  jz      short loc_18005898C
0x180058969  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180058970  lea     r9, [rsp+6F0h+UserData]; UserData
0x180058975  mov     r8d, 0Ah; UserDataCount
0x18005897b  lea     rdx, WlansvcConnectionFailEvtDesc; EventDescriptor
0x180058982  call    cs:__imp_EventWrite
0x180058988  mov     ebx, eax
0x18005898a  jmp     short loc_180058998
0x18005898c  mov     ebx, 139Fh
0x180058991  jmp     short loc_180058998
0x180058993  mov     ebx, 57h ; 'W'
0x180058998  mov     eax, ebx
0x18005899a  mov     rcx, [rbp+5F0h+var_20]
0x1800589a1  xor     rcx, rsp; StackCookie
0x1800589a4  call    __security_check_cookie
0x1800589a9  lea     r11, [rsp+6F0h+var_10]
0x1800589b1  mov     rbx, [r11+20h]
0x1800589b5  mov     rsi, [r11+28h]
0x1800589b9  mov     rsp, r11
0x1800589bc  pop     r14
0x1800589be  pop     rdi
0x1800589bf  pop     rbp
0x1800589c0  retn
```
