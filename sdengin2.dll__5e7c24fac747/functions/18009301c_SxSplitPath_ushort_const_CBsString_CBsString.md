# SxSplitPath(ushort const *,CBsString *,CBsString *)

- ea: `0x18009301c`
- end: `0x180093413`
- name: `?SxSplitPath@@YAJPEBGPEAVCBsString@@1@Z`
- size: `1015`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *, struct CBsString *)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1800195ec`
- `0x180086d98`

## callees

- `0x180008240`
- `0x180014394`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009301c`
- `0x18009386c`
- `0x1800998c8`
- `0x180099c84`
- `0x18009a24c`
- `0x18009a354`
- `0x18009a3f0`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180093253`
- `KERNEL32!GetLastError` at `0x180093253`
- `KERNEL32!GetVolumePathNameW` at `0x18009323d`
- `KERNEL32!GetVolumePathNameW` at `0x18009323d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18009313f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18009318d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18009313f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18009318d`

## string_xrefs

- `0x1800933aa`: `dwPathLength != 0`
- `0x18009307a`: `SxSplitPath`

## pseudocode

```c
__int64 __fastcall SxSplitPath(const unsigned __int16 *a1, struct CBsString *a2, struct CBsString *a3)
{
  __int16 v5; // ax
  const WCHAR *v6; // rsi
  __int64 v7; // rcx
  DWORD FullPathNameW; // edi
  __int16 v9; // bx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  const WCHAR *v12; // rsi
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  unsigned int v17; // ebx
  LPWSTR lpszVolumePathName; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-51h]
  LPWSTR lpBuffer; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v22[2]; // [rsp+48h] [rbp-41h]
  _QWORD v23[2]; // [rsp+50h] [rbp-39h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-29h] BYREF
  int v25; // [rsp+70h] [rbp-19h] BYREF
  __int16 v26; // [rsp+74h] [rbp-15h]
  __int16 v27; // [rsp+76h] [rbp-13h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, (_DWORD)a3, (_DWORD)a1, 0, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v25, "SxSplitPath", 1488, 1);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpBuffer = (LPWSTR)qword_1800E8530;
  lpszVolumePathName = (LPWSTR)qword_1800E8530;
  v23[0] = qword_1800E8530;
  v5 = 1497;
  *(_QWORD *)v22 = 0;
  *(_QWORD *)v20 = 0;
  v23[1] = 0;
  if ( !a1 )
  {
    v25 = -2147024809;
    goto LABEL_44;
  }
  v25 = 0;
  v26 = 1497;
  v25 = CBsString::Set((CBsString *)lpFileName, a1);
  v5 = 1499;
  if ( v25 < 0 )
  {
LABEL_44:
    v27 = v5;
    goto LABEL_45;
  }
  v26 = 1499;
  v6 = lpFileName[0];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, lpFileName[0]);
  FullPathNameW = GetFullPathNameW(v6, 0, 0, 0);
  if ( FullPathNameW )
  {
    v25 = 0;
    v26 = 1507;
    v9 = 1510;
    do
    {
      v25 = CBsString::ExtendBuffer((CBsString *)&lpBuffer, FullPathNameW - 1);
      if ( v25 < 0 )
      {
LABEL_26:
        v27 = v9;
        goto LABEL_45;
      }
      v26 = 1510;
      v10 = v22[1];
      FullPathNameW = GetFullPathNameW(v6, v22[1] + 1, lpBuffer, 0);
      CBsString::BoundUpdateLength((CBsString *)&lpBuffer, v10);
      if ( !FullPathNameW )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
        v25 = LastFailureAsHRESULT;
        v27 = 1513;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          v16 = 49;
          goto LABEL_42;
        }
        goto LABEL_45;
      }
      v25 = 0;
      v26 = 1513;
      v9 = 1510;
    }
    while ( FullPathNameW > v22[1] );
    v25 = CBsString::SetLength((CBsString *)&lpBuffer, FullPathNameW);
    v5 = 1516;
    if ( v25 >= 0 )
    {
      v26 = 1516;
      v12 = lpBuffer;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (_DWORD)lpBuffer,
          FullPathNameW);
      v25 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, FullPathNameW);
      v5 = 1525;
      if ( v25 >= 0 )
      {
        while ( 1 )
        {
          v26 = v5;
          v9 = 1533;
          if ( GetVolumePathNameW(v12, lpszVolumePathName, FullPathNameW + 1) )
            break;
          CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v20[1]);
          if ( GetLastError() != 206 )
          {
            v25 = GetLastFailureAsHRESULT(v13);
            goto LABEL_26;
          }
          v26 = 1533;
          v5 = 1535;
          if ( 2 * FullPathNameW <= FullPathNameW )
          {
            v25 = -2147024362;
            goto LABEL_44;
          }
          v25 = 0;
          v26 = 1535;
          v25 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, 2 * FullPathNameW);
          v5 = 1536;
          if ( v25 < 0 )
            goto LABEL_44;
          FullPathNameW *= 2;
        }
        CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v20[1]);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            lpszVolumePathName);
        v25 = CBsString::Set((CBsString *)v23, &v12[v20[0]]);
        v5 = 1547;
        if ( v25 >= 0 )
        {
          v26 = 1547;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, v23[0]);
          if ( a3 )
            CBsString::Transfer((CBsString *)v23, a3);
          goto LABEL_45;
        }
      }
    }
    goto LABEL_44;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
  v25 = LastFailureAsHRESULT;
  v27 = 1507;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v16 = 48;
LABEL_42:
    WPP_SF_sSd(
      v15[2],
      v16,
      (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
      (unsigned int)"dwPathLength != 0",
      (__int64)v6,
      LastFailureAsHRESULT);
  }
LABEL_45:
  v17 = v25;
  CBsString::_Release((CBsString *)v23);
  CBsString::_Release((CBsString *)&lpszVolumePathName);
  CBsString::_Release((CBsString *)&lpBuffer);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v25);
  return v17;
}

```

## disassembly

```asm
0x18009301c  push    rbp
0x18009301e  push    rbx
0x18009301f  push    rsi
0x180093020  push    rdi
0x180093021  push    r12
0x180093023  push    r13
0x180093025  push    r14
0x180093027  lea     rbp, [rsp-27h]
0x18009302c  sub     rsp, 0B0h
0x180093033  mov     r14, r8
0x180093036  mov     rbx, rcx
0x180093039  mov     rcx, cs:WPP_GLOBAL_Control
0x180093040  lea     r12, WPP_GLOBAL_Control
0x180093047  cmp     rcx, r12
0x18009304a  jz      short loc_180093074
0x18009304c  test    dword ptr [rcx+1Ch], 20000000h
0x180093053  jz      short loc_180093074
0x180093055  mov     rcx, [rcx+10h]
0x180093059  mov     edx, 2Eh ; '.'
0x18009305e  mov     [rsp+0E0h+var_B8], r8
0x180093063  mov     r9, rbx
0x180093066  mov     [rsp+0E0h+var_C0], 0
0x18009306f  call    WPP_SF_Sqq
0x180093074  mov     r9d, 1; unsigned __int16
0x18009307a  lea     rdx, aSxsplitpath; "SxSplitPath"
0x180093081  mov     r8d, 5D0h; unsigned __int16
0x180093087  lea     rcx, [rbp+57h+var_70]; this
0x18009308b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180093090  mov     [rbp+57h+var_78], 0
0x180093098  lea     rax, qword_1800E8530
0x18009309f  mov     [rbp+57h+lpFileName], rax
0x1800930a3  mov     [rbp+57h+lpBuffer], rax
0x1800930a7  mov     [rbp+57h+lpszVolumePathName], rax
0x1800930ab  mov     [rbp+57h+var_90], rax
0x1800930af  mov     eax, 5D9h
0x1800930b4  mov     qword ptr [rbp+57h+var_98], 0
0x1800930bc  mov     qword ptr [rbp+57h+var_A8], 0
0x1800930c4  mov     [rbp+57h+var_88], 0
0x1800930cc  test    rbx, rbx
0x1800930cf  jz      loc_1800933C4
0x1800930d5  mov     rdx, rbx; unsigned __int16 *
0x1800930d8  mov     [rbp+57h+var_70], 0
0x1800930df  lea     rcx, [rbp+57h+lpFileName]; this
0x1800930e3  mov     [rbp+57h+var_6C], ax
0x1800930e7  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800930ec  mov     [rbp+57h+var_70], eax
0x1800930ef  test    eax, eax
0x1800930f1  mov     eax, 5DBh
0x1800930f6  js      loc_1800933CB
0x1800930fc  mov     [rbp+57h+var_6C], ax
0x180093100  mov     rcx, cs:WPP_GLOBAL_Control
0x180093107  lea     r13, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009310e  mov     rsi, [rbp+57h+lpFileName]
0x180093112  cmp     rcx, r12
0x180093115  jz      short loc_180093134
0x180093117  test    dword ptr [rcx+1Ch], 1000000h
0x18009311e  jz      short loc_180093134
0x180093120  mov     rcx, [rcx+10h]
0x180093124  mov     edx, 2Fh ; '/'
0x180093129  mov     r9, rsi
0x18009312c  mov     r8, r13
0x18009312f  call    WPP_SF_S
0x180093134  xor     r9d, r9d; lpFilePart
0x180093137  xor     r8d, r8d; lpBuffer
0x18009313a  xor     edx, edx; nBufferLength
0x18009313c  mov     rcx, rsi; lpFileName
0x18009313f  call    cs:__imp_GetFullPathNameW
0x180093145  mov     edi, eax
0x180093147  test    eax, eax
0x180093149  jz      loc_18009337B
0x18009314f  mov     ecx, 5E3h
0x180093154  mov     [rbp+57h+var_70], 0
0x18009315b  mov     [rbp+57h+var_6C], cx
0x18009315f  lea     ebx, [rcx+3]
0x180093162  lea     edx, [rdi-1]; unsigned int
0x180093165  lea     rcx, [rbp+57h+lpBuffer]; this
0x180093169  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18009316e  mov     [rbp+57h+var_70], eax
0x180093171  test    eax, eax
0x180093173  js      loc_1800932AE
0x180093179  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x18009317d  xor     r9d, r9d; lpFilePart
0x180093180  mov     [rbp+57h+var_6C], bx
0x180093184  mov     rcx, rsi; lpFileName
0x180093187  mov     ebx, [rbp+57h+var_98+4]
0x18009318a  lea     edx, [rbx+1]; nBufferLength
0x18009318d  call    cs:__imp_GetFullPathNameW
0x180093193  mov     edx, ebx; unsigned int
0x180093195  lea     rcx, [rbp+57h+lpBuffer]; this
0x180093199  mov     edi, eax
0x18009319b  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800931a0  test    edi, edi
0x1800931a2  jz      loc_18009334E
0x1800931a8  mov     eax, 5E9h
0x1800931ad  mov     [rbp+57h+var_70], 0
0x1800931b4  mov     [rbp+57h+var_6C], ax
0x1800931b8  lea     ebx, [rax-3]
0x1800931bb  cmp     edi, [rbp+57h+var_98+4]
0x1800931be  ja      short loc_180093162
0x1800931c0  mov     edx, edi; unsigned int
0x1800931c2  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800931c6  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x1800931cb  mov     [rbp+57h+var_70], eax
0x1800931ce  test    eax, eax
0x1800931d0  lea     eax, [rbx+6]
0x1800931d3  js      loc_1800933CB
0x1800931d9  mov     [rbp+57h+var_6C], ax
0x1800931dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800931e4  mov     rsi, [rbp+57h+lpBuffer]
0x1800931e8  cmp     rcx, r12
0x1800931eb  jz      short loc_18009320E
0x1800931ed  test    dword ptr [rcx+1Ch], 1000000h
0x1800931f4  jz      short loc_18009320E
0x1800931f6  mov     rcx, [rcx+10h]
0x1800931fa  mov     edx, 32h ; '2'
0x1800931ff  mov     r9, rsi
0x180093202  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180093206  mov     r8, r13
0x180093209  call    WPP_SF_Sd
0x18009320e  mov     edx, edi; unsigned int
0x180093210  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180093214  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180093219  mov     [rbp+57h+var_70], eax
0x18009321c  test    eax, eax
0x18009321e  mov     eax, 5F5h
0x180093223  js      loc_1800933CB
0x180093229  mov     rdx, [rbp+57h+lpszVolumePathName]; lpszVolumePathName
0x18009322d  lea     r8d, [rdi+1]; cchBufferLength
0x180093231  mov     rcx, rsi; lpszFileName
0x180093234  mov     [rbp+57h+var_6C], ax
0x180093238  mov     ebx, 5FDh
0x18009323d  call    cs:__imp_GetVolumePathNameW
0x180093243  mov     edx, [rbp+57h+var_A8+4]; unsigned int
0x180093246  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009324a  test    eax, eax
0x18009324c  jnz     short loc_1800932B7
0x18009324e  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180093253  call    cs:__imp_GetLastError
0x180093259  cmp     eax, 0CEh
0x18009325e  jnz     short loc_1800932A6
0x180093260  mov     [rbp+57h+var_6C], bx
0x180093264  mov     eax, 5FFh
0x180093269  lea     ebx, [rdi+rdi]
0x18009326c  cmp     ebx, edi
0x18009326e  jbe     short loc_18009329A
0x180093270  mov     edx, ebx; unsigned int
0x180093272  mov     [rbp+57h+var_70], 0
0x180093279  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009327d  mov     [rbp+57h+var_6C], ax
0x180093281  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180093286  mov     [rbp+57h+var_70], eax
0x180093289  test    eax, eax
0x18009328b  mov     eax, 600h
0x180093290  js      loc_1800933CB
0x180093296  mov     edi, ebx
0x180093298  jmp     short loc_180093229
0x18009329a  mov     [rbp+57h+var_70], 80070216h
0x1800932a1  jmp     loc_1800933CB
0x1800932a6  call    GetLastFailureAsHRESULT
0x1800932ab  mov     [rbp+57h+var_70], eax
0x1800932ae  mov     [rbp+57h+var_6A], bx
0x1800932b2  jmp     loc_1800933CF
0x1800932b7  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800932bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800932c3  cmp     rcx, r12
0x1800932c6  jz      short loc_1800932E6
0x1800932c8  test    dword ptr [rcx+1Ch], 1000000h
0x1800932cf  jz      short loc_1800932E6
0x1800932d1  mov     r9, [rbp+57h+lpszVolumePathName]
0x1800932d5  mov     edx, 33h ; '3'
0x1800932da  mov     rcx, [rcx+10h]
0x1800932de  mov     r8, r13
0x1800932e1  call    WPP_SF_S
0x1800932e6  mov     eax, [rbp+57h+var_A8]
0x1800932e9  lea     rcx, [rbp+57h+var_90]; this
0x1800932ed  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x1800932f1  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800932f6  mov     [rbp+57h+var_70], eax
0x1800932f9  test    eax, eax
0x1800932fb  mov     eax, 60Bh
0x180093300  js      loc_1800933CB
0x180093306  mov     [rbp+57h+var_6C], ax
0x18009330a  mov     rcx, cs:WPP_GLOBAL_Control
0x180093311  cmp     rcx, r12
0x180093314  jz      short loc_180093334
0x180093316  test    dword ptr [rcx+1Ch], 1000000h
0x18009331d  jz      short loc_180093334
0x18009331f  mov     r9, [rbp+57h+var_90]
0x180093323  mov     edx, 34h ; '4'
0x180093328  mov     rcx, [rcx+10h]
0x18009332c  mov     r8, r13
0x18009332f  call    WPP_SF_S
0x180093334  test    r14, r14
0x180093337  jz      loc_1800933CF
0x18009333d  mov     rdx, r14; struct CBsString *
0x180093340  lea     rcx, [rbp+57h+var_90]; this
0x180093344  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x180093349  jmp     loc_1800933CF
0x18009334e  call    GetLastFailureAsHRESULT
0x180093353  mov     ecx, 5E9h
0x180093358  mov     [rbp+57h+var_70], eax
0x18009335b  mov     [rbp+57h+var_6A], cx
0x18009335f  mov     rcx, cs:WPP_GLOBAL_Control
0x180093366  cmp     rcx, r12
0x180093369  jz      short loc_1800933CF
0x18009336b  test    dword ptr [rcx+1Ch], 2000000h
0x180093372  jz      short loc_1800933CF
0x180093374  mov     edx, 31h ; '1'
0x180093379  jmp     short loc_1800933A6
0x18009337b  call    GetLastFailureAsHRESULT
0x180093380  mov     ecx, 5E3h
0x180093385  mov     [rbp+57h+var_70], eax
0x180093388  mov     [rbp+57h+var_6A], cx
0x18009338c  mov     rcx, cs:WPP_GLOBAL_Control
0x180093393  cmp     rcx, r12
0x180093396  jz      short loc_1800933CF
0x180093398  test    dword ptr [rcx+1Ch], 2000000h
0x18009339f  jz      short loc_1800933CF
0x1800933a1  mov     edx, 30h ; '0'
0x1800933a6  mov     rcx, [rcx+10h]
0x1800933aa  lea     r9, aDwpathlength0; "dwPathLength != 0"
0x1800933b1  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800933b5  mov     r8, r13
0x1800933b8  mov     [rsp+0E0h+var_C0], rsi
0x1800933bd  call    WPP_SF_sSd
0x1800933c2  jmp     short loc_1800933CF
0x1800933c4  mov     [rbp+57h+var_70], 80070057h
0x1800933cb  mov     [rbp+57h+var_6A], ax
0x1800933cf  mov     ebx, [rbp+57h+var_70]
0x1800933d2  lea     rcx, [rbp+57h+var_90]; this
0x1800933d6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800933db  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800933df  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800933e4  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800933e8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800933ed  lea     rcx, [rbp+57h+lpFileName]; this
0x1800933f1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800933f6  lea     rcx, [rbp+57h+var_70]; this
0x1800933fa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800933ff  mov     eax, ebx
0x180093401  add     rsp, 0B0h
0x180093408  pop     r14
0x18009340a  pop     r13
0x18009340c  pop     r12
0x18009340e  pop     rdi
0x18009340f  pop     rsi
0x180093410  pop     rbx
0x180093411  pop     rbp
0x180093412  retn
```
