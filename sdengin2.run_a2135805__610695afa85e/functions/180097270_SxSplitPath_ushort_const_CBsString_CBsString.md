# SxSplitPath(ushort const *,CBsString *,CBsString *)

- ea: `0x180097270`
- end: `0x180097680`
- name: `?SxSplitPath@@YAJPEBGPEAVCBsString@@1@Z`
- size: `1040`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *, struct CBsString *)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18001a040`
- `0x18008a70c`

## callees

- `0x1800083e4`
- `0x180014c30`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180097270`
- `0x180097b08`
- `0x18009dee8`
- `0x18009e2e8`
- `0x18009e904`
- `0x18009ea0c`
- `0x18009eab0`
- `0x18009f560`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800974b9`
- `KERNEL32!GetLastError` at `0x1800974b9`
- `KERNEL32!GetVolumePathNameW` at `0x18009749d`
- `KERNEL32!GetVolumePathNameW` at `0x18009749d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180097393`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800973e7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180097393`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800973e7`

## string_xrefs

- `0x180097616`: `dwPathLength != 0`
- `0x1800972ce`: `SxSplitPath`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v25, "SxSplitPath", 0x5D0u, 1u);
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpBuffer = (LPWSTR)qword_1800EE510;
  lpszVolumePathName = (LPWSTR)qword_1800EE510;
  v23[0] = qword_1800EE510;
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
0x180097270  push    rbp
0x180097272  push    rbx
0x180097273  push    rsi
0x180097274  push    rdi
0x180097275  push    r12
0x180097277  push    r13
0x180097279  push    r14
0x18009727b  lea     rbp, [rsp-27h]
0x180097280  sub     rsp, 0B0h
0x180097287  mov     r14, r8
0x18009728a  mov     rbx, rcx
0x18009728d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097294  lea     r12, WPP_GLOBAL_Control
0x18009729b  cmp     rcx, r12
0x18009729e  jz      short loc_1800972C8
0x1800972a0  test    dword ptr [rcx+1Ch], 20000000h
0x1800972a7  jz      short loc_1800972C8
0x1800972a9  mov     rcx, [rcx+10h]
0x1800972ad  mov     edx, 2Eh ; '.'
0x1800972b2  mov     [rsp+0E0h+var_B8], r8
0x1800972b7  mov     r9, rbx
0x1800972ba  mov     [rsp+0E0h+var_C0], 0
0x1800972c3  call    WPP_SF_Sqq
0x1800972c8  mov     r9d, 1; unsigned __int16
0x1800972ce  lea     rdx, aSxsplitpath; "SxSplitPath"
0x1800972d5  mov     r8d, 5D0h; unsigned __int16
0x1800972db  lea     rcx, [rbp+57h+var_70]; this
0x1800972df  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800972e4  mov     [rbp+57h+var_78], 0
0x1800972ec  lea     rax, qword_1800EE510
0x1800972f3  mov     [rbp+57h+lpFileName], rax
0x1800972f7  mov     [rbp+57h+lpBuffer], rax
0x1800972fb  mov     [rbp+57h+lpszVolumePathName], rax
0x1800972ff  mov     [rbp+57h+var_90], rax
0x180097303  mov     eax, 5D9h
0x180097308  mov     qword ptr [rbp+57h+var_98], 0
0x180097310  mov     qword ptr [rbp+57h+var_A8], 0
0x180097318  mov     [rbp+57h+var_88], 0
0x180097320  test    rbx, rbx
0x180097323  jz      loc_180097630
0x180097329  mov     rdx, rbx; unsigned __int16 *
0x18009732c  mov     [rbp+57h+var_70], 0
0x180097333  lea     rcx, [rbp+57h+lpFileName]; this
0x180097337  mov     [rbp+57h+var_6C], ax
0x18009733b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180097340  mov     [rbp+57h+var_70], eax
0x180097343  test    eax, eax
0x180097345  mov     eax, 5DBh
0x18009734a  js      loc_180097637
0x180097350  mov     [rbp+57h+var_6C], ax
0x180097354  mov     rcx, cs:WPP_GLOBAL_Control
0x18009735b  lea     r13, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180097362  mov     rsi, [rbp+57h+lpFileName]
0x180097366  cmp     rcx, r12
0x180097369  jz      short loc_180097388
0x18009736b  test    dword ptr [rcx+1Ch], 1000000h
0x180097372  jz      short loc_180097388
0x180097374  mov     rcx, [rcx+10h]
0x180097378  mov     edx, 2Fh ; '/'
0x18009737d  mov     r9, rsi
0x180097380  mov     r8, r13
0x180097383  call    WPP_SF_S
0x180097388  xor     r9d, r9d; lpFilePart
0x18009738b  xor     r8d, r8d; lpBuffer
0x18009738e  xor     edx, edx; nBufferLength
0x180097390  mov     rcx, rsi; lpFileName
0x180097393  call    cs:__imp_GetFullPathNameW
0x18009739a  nop     dword ptr [rax+rax+00h]
0x18009739f  mov     edi, eax
0x1800973a1  test    eax, eax
0x1800973a3  jz      loc_1800975E7
0x1800973a9  mov     ecx, 5E3h
0x1800973ae  mov     [rbp+57h+var_70], 0
0x1800973b5  mov     [rbp+57h+var_6C], cx
0x1800973b9  lea     ebx, [rcx+3]
0x1800973bc  lea     edx, [rdi-1]; unsigned int
0x1800973bf  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800973c3  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800973c8  mov     [rbp+57h+var_70], eax
0x1800973cb  test    eax, eax
0x1800973cd  js      loc_18009751A
0x1800973d3  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x1800973d7  xor     r9d, r9d; lpFilePart
0x1800973da  mov     [rbp+57h+var_6C], bx
0x1800973de  mov     rcx, rsi; lpFileName
0x1800973e1  mov     ebx, [rbp+57h+var_98+4]
0x1800973e4  lea     edx, [rbx+1]; nBufferLength
0x1800973e7  call    cs:__imp_GetFullPathNameW
0x1800973ee  nop     dword ptr [rax+rax+00h]
0x1800973f3  mov     edx, ebx; unsigned int
0x1800973f5  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800973f9  mov     edi, eax
0x1800973fb  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180097400  test    edi, edi
0x180097402  jz      loc_1800975BA
0x180097408  mov     eax, 5E9h
0x18009740d  mov     [rbp+57h+var_70], 0
0x180097414  mov     [rbp+57h+var_6C], ax
0x180097418  lea     ebx, [rax-3]
0x18009741b  cmp     edi, [rbp+57h+var_98+4]
0x18009741e  ja      short loc_1800973BC
0x180097420  mov     edx, edi; unsigned int
0x180097422  lea     rcx, [rbp+57h+lpBuffer]; this
0x180097426  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x18009742b  mov     [rbp+57h+var_70], eax
0x18009742e  test    eax, eax
0x180097430  lea     eax, [rbx+6]
0x180097433  js      loc_180097637
0x180097439  mov     [rbp+57h+var_6C], ax
0x18009743d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097444  mov     rsi, [rbp+57h+lpBuffer]
0x180097448  cmp     rcx, r12
0x18009744b  jz      short loc_18009746E
0x18009744d  test    dword ptr [rcx+1Ch], 1000000h
0x180097454  jz      short loc_18009746E
0x180097456  mov     rcx, [rcx+10h]
0x18009745a  mov     edx, 32h ; '2'
0x18009745f  mov     r9, rsi
0x180097462  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180097466  mov     r8, r13
0x180097469  call    WPP_SF_Sd
0x18009746e  mov     edx, edi; unsigned int
0x180097470  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180097474  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180097479  mov     [rbp+57h+var_70], eax
0x18009747c  test    eax, eax
0x18009747e  mov     eax, 5F5h
0x180097483  js      loc_180097637
0x180097489  mov     rdx, [rbp+57h+lpszVolumePathName]; lpszVolumePathName
0x18009748d  lea     r8d, [rdi+1]; cchBufferLength
0x180097491  mov     rcx, rsi; lpszFileName
0x180097494  mov     [rbp+57h+var_6C], ax
0x180097498  mov     ebx, 5FDh
0x18009749d  call    cs:__imp_GetVolumePathNameW
0x1800974a4  nop     dword ptr [rax+rax+00h]
0x1800974a9  mov     edx, [rbp+57h+var_A8+4]; unsigned int
0x1800974ac  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800974b0  test    eax, eax
0x1800974b2  jnz     short loc_180097523
0x1800974b4  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800974b9  call    cs:__imp_GetLastError
0x1800974c0  nop     dword ptr [rax+rax+00h]
0x1800974c5  cmp     eax, 0CEh
0x1800974ca  jnz     short loc_180097512
0x1800974cc  mov     [rbp+57h+var_6C], bx
0x1800974d0  mov     eax, 5FFh
0x1800974d5  lea     ebx, [rdi+rdi]
0x1800974d8  cmp     ebx, edi
0x1800974da  jbe     short loc_180097506
0x1800974dc  mov     edx, ebx; unsigned int
0x1800974de  mov     [rbp+57h+var_70], 0
0x1800974e5  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800974e9  mov     [rbp+57h+var_6C], ax
0x1800974ed  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800974f2  mov     [rbp+57h+var_70], eax
0x1800974f5  test    eax, eax
0x1800974f7  mov     eax, 600h
0x1800974fc  js      loc_180097637
0x180097502  mov     edi, ebx
0x180097504  jmp     short loc_180097489
0x180097506  mov     [rbp+57h+var_70], 80070216h
0x18009750d  jmp     loc_180097637
0x180097512  call    GetLastFailureAsHRESULT
0x180097517  mov     [rbp+57h+var_70], eax
0x18009751a  mov     [rbp+57h+var_6A], bx
0x18009751e  jmp     loc_18009763B
0x180097523  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180097528  mov     rcx, cs:WPP_GLOBAL_Control
0x18009752f  cmp     rcx, r12
0x180097532  jz      short loc_180097552
0x180097534  test    dword ptr [rcx+1Ch], 1000000h
0x18009753b  jz      short loc_180097552
0x18009753d  mov     r9, [rbp+57h+lpszVolumePathName]
0x180097541  mov     edx, 33h ; '3'
0x180097546  mov     rcx, [rcx+10h]
0x18009754a  mov     r8, r13
0x18009754d  call    WPP_SF_S
0x180097552  mov     eax, [rbp+57h+var_A8]
0x180097555  lea     rcx, [rbp+57h+var_90]; this
0x180097559  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x18009755d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180097562  mov     [rbp+57h+var_70], eax
0x180097565  test    eax, eax
0x180097567  mov     eax, 60Bh
0x18009756c  js      loc_180097637
0x180097572  mov     [rbp+57h+var_6C], ax
0x180097576  mov     rcx, cs:WPP_GLOBAL_Control
0x18009757d  cmp     rcx, r12
0x180097580  jz      short loc_1800975A0
0x180097582  test    dword ptr [rcx+1Ch], 1000000h
0x180097589  jz      short loc_1800975A0
0x18009758b  mov     r9, [rbp+57h+var_90]
0x18009758f  mov     edx, 34h ; '4'
0x180097594  mov     rcx, [rcx+10h]
0x180097598  mov     r8, r13
0x18009759b  call    WPP_SF_S
0x1800975a0  test    r14, r14
0x1800975a3  jz      loc_18009763B
0x1800975a9  mov     rdx, r14; struct CBsString *
0x1800975ac  lea     rcx, [rbp+57h+var_90]; this
0x1800975b0  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x1800975b5  jmp     loc_18009763B
0x1800975ba  call    GetLastFailureAsHRESULT
0x1800975bf  mov     ecx, 5E9h
0x1800975c4  mov     [rbp+57h+var_70], eax
0x1800975c7  mov     [rbp+57h+var_6A], cx
0x1800975cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800975d2  cmp     rcx, r12
0x1800975d5  jz      short loc_18009763B
0x1800975d7  test    dword ptr [rcx+1Ch], 2000000h
0x1800975de  jz      short loc_18009763B
0x1800975e0  mov     edx, 31h ; '1'
0x1800975e5  jmp     short loc_180097612
0x1800975e7  call    GetLastFailureAsHRESULT
0x1800975ec  mov     ecx, 5E3h
0x1800975f1  mov     [rbp+57h+var_70], eax
0x1800975f4  mov     [rbp+57h+var_6A], cx
0x1800975f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800975ff  cmp     rcx, r12
0x180097602  jz      short loc_18009763B
0x180097604  test    dword ptr [rcx+1Ch], 2000000h
0x18009760b  jz      short loc_18009763B
0x18009760d  mov     edx, 30h ; '0'
0x180097612  mov     rcx, [rcx+10h]
0x180097616  lea     r9, aDwpathlength0; "dwPathLength != 0"
0x18009761d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180097621  mov     r8, r13
0x180097624  mov     [rsp+0E0h+var_C0], rsi
0x180097629  call    WPP_SF_sSd
0x18009762e  jmp     short loc_18009763B
0x180097630  mov     [rbp+57h+var_70], 80070057h
0x180097637  mov     [rbp+57h+var_6A], ax
0x18009763b  mov     ebx, [rbp+57h+var_70]
0x18009763e  lea     rcx, [rbp+57h+var_90]; this
0x180097642  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180097647  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009764b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180097650  lea     rcx, [rbp+57h+lpBuffer]; this
0x180097654  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180097659  lea     rcx, [rbp+57h+lpFileName]; this
0x18009765d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180097662  lea     rcx, [rbp+57h+var_70]; this
0x180097666  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009766b  mov     eax, ebx
0x18009766d  add     rsp, 0B0h
0x180097674  pop     r14
0x180097676  pop     r13
0x180097678  pop     r12
0x18009767a  pop     rdi
0x18009767b  pop     rsi
0x18009767c  pop     rbx
0x18009767d  pop     rbp
0x18009767e  retn
```
