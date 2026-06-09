# SxGetInterestingVolumes(CSxVolumeInfoArray * *)

- ea: `0x180028ee8`
- end: `0x180029363`
- name: `?SxGetInterestingVolumes@@YAJPEAPEAVCSxVolumeInfoArray@@@Z`
- size: `1147`
- prototype: `__int64 __fastcall(struct CSxVolumeInfoArray **)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x180004ff0`

## callees

- `0x18000406c`
- `0x180007344`
- `0x18000e38c`
- `0x18000e3cc`
- `0x180020908`
- `0x180020968`
- `0x1800216c8`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800276ac`
- `0x180028ee8`
- `0x18002936c`
- `0x18002a08c`
- `0x18002a4fc`
- `0x18002a96c`
- `0x18002d6e8`
- `0x18003532c`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800290ad`
- `KERNEL32!GetLastError` at `0x180029120`
- `KERNEL32!GetLastError` at `0x1800292b7`
- `KERNEL32!GetLastError` at `0x1800290ad`
- `KERNEL32!GetLastError` at `0x180029120`
- `KERNEL32!GetLastError` at `0x1800292b7`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800290f9`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800290f9`
- `KERNEL32!GetVolumeInformationW` at `0x180029086`
- `KERNEL32!GetVolumeInformationW` at `0x180029086`
- `KERNEL32!FindFirstVolumeW` at `0x180028fcc`
- `KERNEL32!FindFirstVolumeW` at `0x180028fcc`
- `KERNEL32!FindNextVolumeW` at `0x1800292a9`
- `KERNEL32!FindNextVolumeW` at `0x1800292a9`
- `KERNEL32!FindVolumeClose` at `0x1800292f8`
- `KERNEL32!FindVolumeClose` at `0x1800292f8`

## pseudocode

```c
__int64 __fastcall SxGetInterestingVolumes(struct CSxVolumeInfoArray **a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  struct CSxVolumeInfoArray *v4; // rsi
  struct CSxVolumeInfo *v5; // rdi
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v8; // rcx
  HANDLE FirstVolumeW; // rbx
  int IsVolumeInteresting; // eax
  int PresentableVolumeName; // eax
  int v12; // edx
  _QWORD *v13; // rcx
  DWORD v14; // r8d
  int v15; // eax
  bool v16; // sf
  __int16 v17; // ax
  __int64 v18; // rcx
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v21; // [rsp+44h] [rbp-BCh]
  __int16 v22; // [rsp+46h] [rbp-BAh]
  struct CSxVolumeInfoArray *v23; // [rsp+78h] [rbp-88h] BYREF
  struct CSxVolumeInfo *v24; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchReturnLength; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szVolumeName[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "SxGetInterestingVolumes", 1703, 1);
  v4 = 0;
  v5 = 0;
  v23 = 0;
  v6 = 1718;
  v24 = 0;
  cchReturnLength = 0;
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
    v20 = -2147024809;
    goto LABEL_53;
  }
  *a1 = 0;
  v20 = 0;
  v21 = 1718;
  LastFailureAsHRESULT = CSxVolumeInfoArray::CreateInstance(&v23);
  v20 = LastFailureAsHRESULT;
  v6 = 1720;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_6:
    v4 = v23;
LABEL_53:
    v22 = v6;
    goto LABEL_54;
  }
  v21 = 1720;
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v20 = LastFailureAsHRESULT;
    v6 = 1723;
    goto LABEL_6;
  }
  v20 = 0;
  v4 = v23;
  v21 = 1723;
  do
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, szVolumeName);
    IsVolumeInteresting = SxIsVolumeInteresting(szVolumeName);
    v20 = IsVolumeInteresting;
    if ( IsVolumeInteresting < 0 )
    {
      v17 = 1729;
      goto LABEL_50;
    }
    v21 = 1729;
    if ( !IsVolumeInteresting )
    {
      if ( GetVolumeInformationW(szVolumeName, VolumeNameBuffer, 0x104u, 0, 0, 0, 0, 0) )
      {
        if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x104u, &cchReturnLength) )
        {
          PresentableVolumeName = SxGetPresentableVolumeName(szVolumeName, szVolumePathNames, v14);
          if ( PresentableVolumeName >= 0 )
          {
            if ( v5 )
            {
              v24 = 0;
              CSxVolumeInfo::Release(v5);
            }
            v15 = CSxVolumeInfo::CreateInstance(&v24);
            v5 = v24;
            v16 = v15 < 0;
            v20 = v15;
            v17 = 1752;
            if ( v16 )
              goto LABEL_50;
            v21 = 1752;
            v20 = CBsString::Set((struct CSxVolumeInfo *)((char *)v24 + 8), szVolumeName);
            v17 = 1753;
            if ( v20 < 0 )
              goto LABEL_50;
            v21 = 1753;
            v20 = CBsString::Set((struct CSxVolumeInfo *)((char *)v5 + 40), VolumeNameBuffer);
            v17 = 1754;
            if ( v20 < 0 )
              goto LABEL_50;
            v21 = 1754;
            v20 = CBsString::Set((struct CSxVolumeInfo *)((char *)v5 + 24), szVolumePathNames);
            v17 = 1755;
            if ( v20 < 0 )
              goto LABEL_50;
            v21 = 1755;
            PresentableVolumeName = SxGetVolumeIdentifier(
                                      szVolumeName,
                                      (unsigned __int8 **)v5 + 7,
                                      (unsigned int *)v5 + 16);
            if ( PresentableVolumeName >= 0 )
            {
              PresentableVolumeName = SxGetVolumeSize(szVolumeName, (unsigned __int64 *)v5 + 9);
              if ( PresentableVolumeName >= 0 )
              {
                v20 = CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append((__int64)v4, (volatile signed __int32 *)v5);
                v17 = 1771;
                if ( v20 < 0 )
                  goto LABEL_50;
                v21 = 1771;
              }
              else
              {
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
                {
                  v12 = 62;
                  goto LABEL_20;
                }
              }
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
              {
                v12 = 61;
                goto LABEL_20;
              }
            }
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
            {
              v12 = 60;
              goto LABEL_20;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          LOBYTE(PresentableVolumeName) = GetLastError();
          v12 = 59;
          goto LABEL_19;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        LOBYTE(PresentableVolumeName) = GetLastError();
        v12 = 58;
LABEL_19:
        v13 = WPP_GLOBAL_Control;
LABEL_20:
        WPP_SF_Sd(
          v13[2],
          v12,
          (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)szVolumeName,
          PresentableVolumeName);
      }
    }
  }
  while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  if ( GetLastError() == 18 )
  {
    *a1 = v4;
    v21 = 1783;
    v4 = 0;
    v20 = 0;
    goto LABEL_51;
  }
  v20 = GetLastFailureAsHRESULT(v18);
  v17 = 1783;
LABEL_50:
  v22 = v17;
LABEL_51:
  FindVolumeClose(FirstVolumeW);
  LastFailureAsHRESULT = v20;
LABEL_54:
  if ( v5 )
    CSxVolumeInfo::Release(v5);
  if ( v4 )
    CSxVolumeInfoArray::Release(v4);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20, v2, v3);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180028ee8  mov     [rsp-8+arg_8], rbx
0x180028eed  mov     [rsp-8+arg_10], rsi
0x180028ef2  push    rbp
0x180028ef3  push    rdi
0x180028ef4  push    r12
0x180028ef6  push    r13
0x180028ef8  push    r14
0x180028efa  lea     rbp, [rsp-5D0h]
0x180028f02  sub     rsp, 6D0h
0x180028f09  mov     rax, cs:__security_cookie
0x180028f10  xor     rax, rsp
0x180028f13  mov     [rbp+5F0h+var_30], rax
0x180028f1a  mov     r14, rcx
0x180028f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f24  lea     r12, WPP_GLOBAL_Control
0x180028f2b  lea     r13, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180028f32  cmp     rcx, r12
0x180028f35  jz      short loc_180028F54
0x180028f37  test    dword ptr [rcx+1Ch], 20000000h
0x180028f3e  jz      short loc_180028F54
0x180028f40  mov     rcx, [rcx+10h]
0x180028f44  mov     edx, 38h ; '8'
0x180028f49  mov     r9, r14
0x180028f4c  mov     r8, r13
0x180028f4f  call    WPP_SF_q
0x180028f54  mov     r9d, 1; unsigned __int16
0x180028f5a  lea     rdx, aSxgetinteresti; "SxGetInterestingVolumes"
0x180028f61  mov     r8d, 6A7h; unsigned __int16
0x180028f67  lea     rcx, [rsp+6F0h+var_6B0]; this
0x180028f6c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180028f71  xor     esi, esi
0x180028f73  xor     edi, edi
0x180028f75  mov     [rsp+6F0h+var_678], rsi
0x180028f7a  mov     eax, 6B6h
0x180028f7f  mov     [rbp+5F0h+var_670], rdi
0x180028f83  mov     [rbp+5F0h+cchReturnLength], esi
0x180028f86  test    r14, r14
0x180028f89  jz      loc_180029304
0x180028f8f  lea     rcx, [rsp+6F0h+var_678]; struct CSxVolumeInfoArray **
0x180028f94  mov     [r14], rsi
0x180028f97  mov     [rsp+6F0h+var_6B0], esi
0x180028f9b  mov     [rsp+6F0h+var_6AC], ax
0x180028fa0  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x180028fa5  mov     ebx, eax
0x180028fa7  mov     [rsp+6F0h+var_6B0], eax
0x180028fab  test    eax, eax
0x180028fad  mov     eax, 6B8h
0x180028fb2  jns     short loc_180028FBE
0x180028fb4  mov     rsi, [rsp+6F0h+var_678]
0x180028fb9  jmp     loc_18002930D
0x180028fbe  mov     edx, 104h; cchBufferLength
0x180028fc3  mov     [rsp+6F0h+var_6AC], ax
0x180028fc8  lea     rcx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x180028fcc  call    cs:__imp_FindFirstVolumeW
0x180028fd2  mov     rbx, rax
0x180028fd5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028fd9  jnz     short loc_180028FED
0x180028fdb  call    GetLastFailureAsHRESULT
0x180028fe0  mov     ebx, eax
0x180028fe2  mov     [rsp+6F0h+var_6B0], eax
0x180028fe6  mov     eax, 6BBh
0x180028feb  jmp     short loc_180028FB4
0x180028fed  mov     eax, 6BBh
0x180028ff2  mov     [rsp+6F0h+var_6B0], esi
0x180028ff6  mov     rsi, [rsp+6F0h+var_678]
0x180028ffb  mov     [rsp+6F0h+var_6AC], ax
0x180029000  mov     rcx, cs:WPP_GLOBAL_Control
0x180029007  cmp     rcx, r12
0x18002900a  jz      short loc_18002902A
0x18002900c  test    dword ptr [rcx+1Ch], 8000000h
0x180029013  jz      short loc_18002902A
0x180029015  mov     rcx, [rcx+10h]
0x180029019  lea     r9, [rbp+5F0h+szVolumeName]
0x18002901d  mov     edx, 39h ; '9'
0x180029022  mov     r8, r13
0x180029025  call    WPP_SF_S
0x18002902a  lea     rcx, [rbp+5F0h+szVolumeName]; lpRootPathName
0x18002902e  call    ?SxIsVolumeInteresting@@YAJPEBG@Z; SxIsVolumeInteresting(ushort const *)
0x180029033  mov     [rsp+6F0h+var_6B0], eax
0x180029037  test    eax, eax
0x180029039  js      loc_1800292EB
0x18002903f  mov     ecx, 6C1h
0x180029044  mov     [rsp+6F0h+var_6AC], cx
0x180029049  jnz     loc_18002929C
0x18002904f  mov     [rsp+6F0h+nFileSystemNameSize], 0; nFileSystemNameSize
0x180029057  lea     rdx, [rbp+5F0h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18002905e  mov     [rsp+6F0h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x180029067  lea     rcx, [rbp+5F0h+szVolumeName]; lpRootPathName
0x18002906b  mov     [rsp+6F0h+lpFileSystemFlags], 0; lpFileSystemFlags
0x180029074  xor     r9d, r9d; lpVolumeSerialNumber
0x180029077  mov     r8d, 104h; nVolumeNameSize
0x18002907d  mov     [rsp+6F0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x180029086  call    cs:__imp_GetVolumeInformationW
0x18002908c  test    eax, eax
0x18002908e  jnz     short loc_1800290E4
0x180029090  mov     rax, cs:WPP_GLOBAL_Control
0x180029097  cmp     rax, r12
0x18002909a  jz      loc_18002929C
0x1800290a0  test    dword ptr [rax+1Ch], 2000000h
0x1800290a7  jz      loc_18002929C
0x1800290ad  call    cs:__imp_GetLastError
0x1800290b3  test    eax, eax
0x1800290b5  jle     short loc_1800290BF
0x1800290b7  movzx   eax, ax
0x1800290ba  or      eax, 80070000h
0x1800290bf  mov     edx, 3Ah ; ':'
0x1800290c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290cb  mov     rcx, [rcx+10h]
0x1800290cf  lea     r9, [rbp+5F0h+szVolumeName]
0x1800290d3  mov     r8, r13
0x1800290d6  mov     dword ptr [rsp+6F0h+lpMaximumComponentLength], eax
0x1800290da  call    WPP_SF_Sd
0x1800290df  jmp     loc_18002929C
0x1800290e4  lea     r9, [rbp+5F0h+cchReturnLength]; lpcchReturnLength
0x1800290e8  mov     r8d, 104h; cchBufferLength
0x1800290ee  lea     rdx, [rbp+5F0h+szVolumePathNames]; lpszVolumePathNames
0x1800290f5  lea     rcx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x1800290f9  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800290ff  test    eax, eax
0x180029101  jnz     short loc_180029139
0x180029103  mov     rax, cs:WPP_GLOBAL_Control
0x18002910a  cmp     rax, r12
0x18002910d  jz      loc_18002929C
0x180029113  test    dword ptr [rax+1Ch], 2000000h
0x18002911a  jz      loc_18002929C
0x180029120  call    cs:__imp_GetLastError
0x180029126  test    eax, eax
0x180029128  jle     short loc_180029132
0x18002912a  movzx   eax, ax
0x18002912d  or      eax, 80070000h
0x180029132  mov     edx, 3Bh ; ';'
0x180029137  jmp     short loc_1800290C4
0x180029139  lea     rdx, [rbp+5F0h+szVolumePathNames]; unsigned __int16 *
0x180029140  lea     rcx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x180029144  call    ?SxGetPresentableVolumeName@@YAJPEBGPEAGK@Z; SxGetPresentableVolumeName(ushort const *,ushort *,ulong)
0x180029149  test    eax, eax
0x18002914b  jns     short loc_180029174
0x18002914d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029154  cmp     rcx, r12
0x180029157  jz      loc_18002929C
0x18002915d  test    dword ptr [rcx+1Ch], 2000000h
0x180029164  jz      loc_18002929C
0x18002916a  mov     edx, 3Ch ; '<'
0x18002916f  jmp     loc_1800290CB
0x180029174  test    rdi, rdi
0x180029177  jz      short loc_180029189
0x180029179  mov     rcx, rdi; this
0x18002917c  mov     [rbp+5F0h+var_670], 0
0x180029184  call    ?Release@CSxVolumeInfo@@QEAAKXZ; CSxVolumeInfo::Release(void)
0x180029189  lea     rcx, [rbp+5F0h+var_670]; struct CSxVolumeInfo **
0x18002918d  call    ?CreateInstance@CSxVolumeInfo@@SAJPEAPEAV1@@Z; CSxVolumeInfo::CreateInstance(CSxVolumeInfo * *)
0x180029192  mov     rdi, [rbp+5F0h+var_670]
0x180029196  test    eax, eax
0x180029198  mov     [rsp+6F0h+var_6B0], eax
0x18002919c  mov     eax, 6D8h
0x1800291a1  js      loc_1800292F0
0x1800291a7  lea     rcx, [rdi+8]; this
0x1800291ab  mov     [rsp+6F0h+var_6AC], ax
0x1800291b0  lea     rdx, [rbp+5F0h+szVolumeName]; unsigned __int16 *
0x1800291b4  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800291b9  mov     [rsp+6F0h+var_6B0], eax
0x1800291bd  test    eax, eax
0x1800291bf  mov     eax, 6D9h
0x1800291c4  js      loc_1800292F0
0x1800291ca  lea     rcx, [rdi+28h]; this
0x1800291ce  mov     [rsp+6F0h+var_6AC], ax
0x1800291d3  lea     rdx, [rbp+5F0h+VolumeNameBuffer]; unsigned __int16 *
0x1800291da  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800291df  mov     [rsp+6F0h+var_6B0], eax
0x1800291e3  test    eax, eax
0x1800291e5  mov     eax, 6DAh
0x1800291ea  js      loc_1800292F0
0x1800291f0  lea     rcx, [rdi+18h]; this
0x1800291f4  mov     [rsp+6F0h+var_6AC], ax
0x1800291f9  lea     rdx, [rbp+5F0h+szVolumePathNames]; unsigned __int16 *
0x180029200  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180029205  mov     [rsp+6F0h+var_6B0], eax
0x180029209  test    eax, eax
0x18002920b  mov     eax, 6DBh
0x180029210  js      loc_1800292F0
0x180029216  lea     r8, [rdi+40h]; unsigned int *
0x18002921a  mov     [rsp+6F0h+var_6AC], ax
0x18002921f  lea     rdx, [rdi+38h]; unsigned __int8 **
0x180029223  lea     rcx, [rbp+5F0h+szVolumeName]; unsigned __int16 *
0x180029227  call    ?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z; SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)
0x18002922c  test    eax, eax
0x18002922e  jns     short loc_18002924F
0x180029230  mov     rcx, cs:WPP_GLOBAL_Control
0x180029237  cmp     rcx, r12
0x18002923a  jz      short loc_18002929C
0x18002923c  test    dword ptr [rcx+1Ch], 2000000h
0x180029243  jz      short loc_18002929C
0x180029245  mov     edx, 3Dh ; '='
0x18002924a  jmp     loc_1800290CB
0x18002924f  lea     rdx, [rdi+48h]; unsigned __int64 *
0x180029253  lea     rcx, [rbp+5F0h+szVolumeName]; unsigned __int16 *
0x180029257  call    ?SxGetVolumeSize@@YAJPEBGPEA_K@Z; SxGetVolumeSize(ushort const *,unsigned __int64 *)
0x18002925c  test    eax, eax
0x18002925e  jns     short loc_18002927F
0x180029260  mov     rcx, cs:WPP_GLOBAL_Control
0x180029267  cmp     rcx, r12
0x18002926a  jz      short loc_18002929C
0x18002926c  test    dword ptr [rcx+1Ch], 2000000h
0x180029273  jz      short loc_18002929C
0x180029275  mov     edx, 3Eh ; '>'
0x18002927a  jmp     loc_1800290CB
0x18002927f  mov     rdx, rdi
0x180029282  mov     rcx, rsi
0x180029285  call    ?Append@?$CSxRefArray@VCSxVolumeInfoArray@@VCSxVolumeInfo@@@@QEAAJPEAVCSxVolumeInfo@@@Z; CSxRefArray<CSxVolumeInfoArray,CSxVolumeInfo>::Append(CSxVolumeInfo *)
0x18002928a  mov     [rsp+6F0h+var_6B0], eax
0x18002928e  test    eax, eax
0x180029290  mov     eax, 6EBh
0x180029295  js      short loc_1800292F0
0x180029297  mov     [rsp+6F0h+var_6AC], ax
0x18002929c  mov     r8d, 104h; cchBufferLength
0x1800292a2  lea     rdx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x1800292a6  mov     rcx, rbx; hFindVolume
0x1800292a9  call    cs:__imp_FindNextVolumeW
0x1800292af  test    eax, eax
0x1800292b1  jnz     loc_180029000
0x1800292b7  call    cs:__imp_GetLastError
0x1800292bd  cmp     eax, 12h
0x1800292c0  jz      short loc_1800292D2
0x1800292c2  call    GetLastFailureAsHRESULT
0x1800292c7  mov     [rsp+6F0h+var_6B0], eax
0x1800292cb  mov     eax, 6F7h
0x1800292d0  jmp     short loc_1800292F0
0x1800292d2  mov     eax, 6F7h
0x1800292d7  mov     [r14], rsi
0x1800292da  mov     [rsp+6F0h+var_6AC], ax
0x1800292df  xor     esi, esi
0x1800292e1  mov     [rsp+6F0h+var_6B0], 0
0x1800292e9  jmp     short loc_1800292F5
0x1800292eb  mov     eax, 6C1h
0x1800292f0  mov     [rsp+6F0h+var_6AA], ax
0x1800292f5  mov     rcx, rbx; hFindVolume
0x1800292f8  call    cs:__imp_FindVolumeClose
0x1800292fe  mov     ebx, [rsp+6F0h+var_6B0]
0x180029302  jmp     short loc_180029312
0x180029304  mov     ebx, 80070057h
0x180029309  mov     [rsp+6F0h+var_6B0], ebx
0x18002930d  mov     [rsp+6F0h+var_6AA], ax
0x180029312  test    rdi, rdi
0x180029315  jz      short loc_18002931F
0x180029317  mov     rcx, rdi; this
0x18002931a  call    ?Release@CSxVolumeInfo@@QEAAKXZ; CSxVolumeInfo::Release(void)
0x18002931f  test    rsi, rsi
0x180029322  jz      short loc_18002932C
0x180029324  mov     rcx, rsi; this
0x180029327  call    ?Release@CSxVolumeInfoArray@@QEAAKXZ; CSxVolumeInfoArray::Release(void)
0x18002932c  lea     rcx, [rsp+6F0h+var_6B0]; this
0x180029331  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180029336  mov     eax, ebx
0x180029338  mov     rcx, [rbp+5F0h+var_30]
0x18002933f  xor     rcx, rsp; StackCookie
0x180029342  call    __security_check_cookie
0x180029347  lea     r11, [rsp+6F0h+var_20]
0x18002934f  mov     rbx, [r11+38h]
0x180029353  mov     rsi, [r11+40h]
0x180029357  mov     rsp, r11
0x18002935a  pop     r14
0x18002935c  pop     r13
0x18002935e  pop     r12
0x180029360  pop     rdi
0x180029361  pop     rbp
0x180029362  retn
```
