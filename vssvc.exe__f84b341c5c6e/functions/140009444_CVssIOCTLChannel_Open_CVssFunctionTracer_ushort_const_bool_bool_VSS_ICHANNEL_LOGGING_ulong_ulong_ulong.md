# CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)

- ea: `0x140009444`
- end: `0x140009a33`
- name: `?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z`
- size: `1519`
- prototype: ``
- caller_count: `36`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400090d0`
- `0x14004ba1c`
- `0x14004c29c`
- `0x140053bcc`
- `0x1400638d4`
- `0x140063f60`
- `0x1400664a0`
- `0x140067084`
- `0x140067464`
- `0x14006871c`
- `0x14006911c`
- `0x140069564`
- `0x14006ac58`
- `0x14006d260`
- `0x14006fbac`
- `0x140074528`
- `0x140077018`
- `0x140077a2c`
- `0x14007a974`
- `0x14007b750`
- `0x14007bd44`
- `0x14007c240`
- `0x14007c81c`
- `0x14007cf8c`
- `0x14007d6fc`
- `0x14008a2f0`
- `0x14008de40`
- `0x1400901e4`
- `0x14009bcf8`
- `0x1400bf9fc`
- `0x1400c3858`
- `0x1400c4d6c`
- `0x1400c5028`
- `0x1400ca588`
- `0x1400cb0f0`
- `0x1400d1cd8`

## callees

- `0x1400084c4`
- `0x140009444`
- `0x140009a40`
- `0x1400139c0`
- `0x140015e38`
- `0x14003b160`
- `0x14003fc04`
- `0x140049ec4`
- `0x140067af4`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009696`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000967a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000967a`

## string_xrefs

- `0x14000949d`: `CVssIOCTLChannel::Open`
- `0x14000956c`: `CVssIOCTLChannel::Open`
- `0x1400095f1`: `CVssIOCTLChannel::Open`
- `0x1400096fb`: `CVssIOCTLChannel::Open`
- `0x140009786`: `CVssIOCTLChannel::Open`
- `0x140009813`: `CVssIOCTLChannel::Open`
- `0x14000988d`: `CVssIOCTLChannel::Open`
- `0x140009904`: `CVssIOCTLChannel::Open`
- `0x1400099ae`: `CVssIOCTLChannel::Open`
- `0x1400099e6`: `The object '%s'. was opened under the device handle 0x%08lx`
- `0x1400094f0`: `Opening a handle to %s (access = 0x%08lx, share = 0x%08lx)`
- `0x140009730`: `CreateFileW(%s,0x%08lx,0x%08lx,...)`
- `0x140009848`: `CreateFileW(%s,0x%08lx,0x%08lx,...)`
- `0x140009629`: `StringCchCopyN`
- `0x1400098bd`: `Could not open the object '%s'. [0x%08lx]\n`
- `0x14000993b`: `Could not open the object '%s'. [0x%08lx]\n`

## pseudocode

```c
__int64 __fastcall CVssIOCTLChannel::Open(
        CVssIOCTLChannel *a1,
        __int64 a2,
        unsigned __int16 *a3,
        char a4,
        char a5,
        int a6,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        DWORD a9)
{
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rbx
  HANDLE FileW; // rax
  HANDLE v17; // rbx
  signed int LastError; // eax
  unsigned int v19; // ebx
  bool v20; // zf
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  const wchar_t *v26; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v27; // [rsp+50h] [rbp-B0h]
  const wchar_t *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  int v31; // [rsp+68h] [rbp-98h]
  _BYTE v32[120]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v34[264]; // [rsp+F0h] [rbp-10h] BYREF

  v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
  v29 = 200;
  v27 = L"CVssIOCTLChannel::Open";
  v30 = 10;
  v28 = L"INCICHLH";
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CVssFunctionTracer::Trace(
    a2,
    &v26,
    L"Opening a handle to %s (access = 0x%08lx, share = 0x%08lx)",
    a3,
    dwDesiredAccess,
    dwShareMode);
  *(_DWORD *)(a2 + 8) = 0;
  CVssIOCTLChannel::Close(a1);
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    if ( (unsigned __int64)(v13 - 1) > 0x103 )
    {
      v29 = 218;
      v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v30 = 10;
      v31 = 255;
      v27 = L"CVssIOCTLChannel::Open";
      v28 = L"INCICHLH";
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      dwFlagsAndAttributes[0] = 260;
      CVssFunctionTracer::TranslateGenericError(
        a2,
        &v26,
        2147549183LL,
        L"Error: the buffer is too small to fit %s (%d < %d)",
        a3,
        *(_QWORD *)dwFlagsAndAttributes,
        v13);
    }
    if ( a3[v13 - 1] != 92 )
    {
      v29 = 226;
      v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v30 = 10;
      v31 = 255;
      v27 = L"CVssIOCTLChannel::Open";
      v28 = L"INCICHLH";
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      CVssFunctionTracer::TranslateGenericError(
        a2,
        &v26,
        2147549183LL,
        L"Error: the object name %s does terminate with a backslash",
        a3);
    }
    v14 = v13 - 1;
    *(_DWORD *)(a2 + 8) = StringCchCopyNW(v34, 0x104u, a3, v14);
    v29 = 233;
    v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v30 = 10;
    v27 = L"CVssIOCTLChannel::Open";
    v28 = L"INCICHLH";
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::CheckForErrorInternal(a2, &v26, L"StringCchCopyN");
    v15 = v14;
    if ( v15 >= 260 )
      _report_rangecheckfailure();
    a3 = v34;
    v34[v15] = 0;
  }
  FileW = CreateFileW(a3, dwDesiredAccess, dwShareMode, 0, 3u, a9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  *(_QWORD *)a1 = FileW;
  v17 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *(_QWORD *)a1 = 0;
    LastError = GetLastError();
    v19 = LastError;
    if ( a5 )
    {
      if ( a6 )
      {
        if ( a6 == 1 )
        {
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          v29 = 264;
          v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v30 = 1;
          v31 = 255;
          v27 = L"CVssIOCTLChannel::Open";
          v28 = L"INCICHLH";
          v33 = 0x1000000;
          memset_0(v32, 0, sizeof(v32));
          LODWORD(hTemplateFile) = dwShareMode;
          dwFlagsAndAttributesa[0] = dwDesiredAccess;
          CVssFunctionTracer::TranslateGenericError(
            a2,
            &v26,
            v19,
            L"CreateFileW(%s,0x%08lx,0x%08lx,...)",
            a3,
            *(_QWORD *)dwFlagsAndAttributesa,
            hTemplateFile);
        }
        if ( a6 == 2 )
        {
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          v29 = 270;
          v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v30 = 2;
          v31 = 255;
          v27 = L"CVssIOCTLChannel::Open";
          v28 = L"INCICHLH";
          v33 = 0x1000000;
          memset_0(v32, 0, sizeof(v32));
          LODWORD(hTemplateFile) = dwDesiredAccess;
          CVssFunctionTracer::TranslateInternalProviderError(
            a2,
            &v26,
            v19,
            2147754758LL,
            L"CreateFileW(%s,0x%08lx,0x%08lx,...)",
            a3,
            hTemplateFile,
            dwShareMode);
        }
      }
      v29 = 258;
      v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v30 = 10;
      v31 = 255;
      v27 = L"CVssIOCTLChannel::Open";
      v28 = L"INCICHLH";
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      dwFlagsAndAttributesa[0] = v19;
      CVssFunctionTracer::Throw(
        a2,
        &v26,
        2147549183LL,
        L"Could not open the object '%s'. [0x%08lx]\n",
        a3,
        *(_QWORD *)dwFlagsAndAttributesa);
    }
    v29 = 279;
    v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v30 = 10;
    v31 = 255;
    v27 = L"CVssIOCTLChannel::Open";
    v28 = L"INCICHLH";
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    dwCreationDisposition[0] = v19;
    CVssFunctionTracer::Trace(
      a2,
      &v26,
      L"Could not open the object '%s'. [0x%08lx]\n",
      a3,
      *(_QWORD *)dwCreationDisposition);
    if ( a6 == 7 )
    {
      if ( (int)v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
    }
    else if ( v19 == 21 || v19 - 2 <= 1 || (v20 = v19 == 1167, v19 = -2147418113, v20) )
    {
      v19 = -2147212536;
    }
    *(_DWORD *)(a2 + 8) = v19;
  }
  else
  {
    v29 = 300;
    v26 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v30 = 10;
    v31 = 255;
    v27 = L"CVssIOCTLChannel::Open";
    v28 = L"INCICHLH";
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::Trace(a2, &v26, L"The object '%s'. was opened under the device handle 0x%08lx", a3, v17);
    CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((char *)a1 + 96, a3);
  }
  return *(unsigned int *)(a2 + 8);
}

```

## disassembly

```asm
0x140009444  mov     [rsp-8+arg_18], rbx
0x140009449  push    rbp
0x14000944a  push    rsi
0x14000944b  push    rdi
0x14000944c  push    r12
0x14000944e  push    r13
0x140009450  push    r14
0x140009452  push    r15
0x140009454  lea     rbp, [rsp-210h]
0x14000945c  sub     rsp, 310h
0x140009463  mov     rax, cs:__security_cookie
0x14000946a  xor     rax, rsp
0x14000946d  mov     [rbp+240h+var_40], rax
0x140009474  mov     r15d, [rbp+240h+dwDesiredAccess]
0x14000947b  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140009482  mov     r12d, [rbp+240h+dwShareMode]
0x140009489  mov     rsi, rdx
0x14000948c  mov     r13d, [rbp+240h+arg_40]
0x140009493  xor     edx, edx; Val
0x140009495  mov     [rsp+340h+var_2F8], rax
0x14000949a  mov     rdi, r8
0x14000949d  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x1400094a4  mov     [rsp+340h+var_2E0], 0C8h
0x1400094ac  mov     [rsp+340h+var_2F0], rax
0x1400094b1  mov     r14, rcx
0x1400094b4  lea     rax, aIncichlh; "INCICHLH"
0x1400094bb  mov     [rsp+340h+var_2DC], 0Ah
0x1400094c3  lea     r8d, [rdx+78h]; Size
0x1400094c7  mov     [rsp+340h+var_2E8], rax
0x1400094cc  lea     rcx, [rsp+340h+var_2D0]; void *
0x1400094d1  mov     [rsp+340h+var_2D8], 0FFh
0x1400094d9  mov     bl, r9b
0x1400094dc  mov     [rbp+240h+var_258], 1000000h
0x1400094e3  call    memset_0
0x1400094e8  mov     r9, rdi
0x1400094eb  mov     [rsp+340h+dwFlagsAndAttributes], r12d
0x1400094f0  lea     r8, aOpeningAHandle; "Opening a handle to %s (access = 0x%08l"...
0x1400094f7  mov     [rsp+340h+dwCreationDisposition], r15d
0x1400094fc  lea     rdx, [rsp+340h+var_2F8]
0x140009501  mov     rcx, rsi
0x140009504  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140009509  mov     rcx, r14; this
0x14000950c  mov     dword ptr [rsi+8], 0
0x140009513  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x140009518  xor     r11d, r11d
0x14000951b  test    bl, bl
0x14000951d  jz      loc_140009658
0x140009523  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140009527  inc     rbx
0x14000952a  cmp     [rdi+rbx*2], r11w
0x14000952f  jnz     short loc_140009527
0x140009531  lea     rax, [rbx-1]
0x140009535  cmp     rax, 103h
0x14000953b  ja      loc_140009763
0x140009541  cmp     word ptr [rdi+rbx*2-2], 5Ch ; '\'
0x140009547  jz      short loc_1400095BC
0x140009549  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140009550  mov     [rsp+340h+var_2E0], 0E2h
0x140009558  mov     [rsp+340h+var_2F8], rax
0x14000955d  lea     rcx, [rsp+340h+var_2D0]; void *
0x140009562  xor     edx, edx; Val
0x140009564  mov     [rsp+340h+var_2DC], 0Ah
0x14000956c  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x140009573  mov     [rsp+340h+var_2D8], 0FFh
0x14000957b  mov     [rsp+340h+var_2F0], rax
0x140009580  lea     rax, aIncichlh; "INCICHLH"
0x140009587  mov     [rsp+340h+var_2E8], rax
0x14000958c  lea     r8d, [rdx+78h]; Size
0x140009590  mov     [rbp+240h+var_258], 1000000h
0x140009597  call    memset_0
0x14000959c  lea     r9, aErrorTheObject; "Error: the object name %s does terminat"...
0x1400095a3  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x1400095a8  mov     r8d, 8000FFFFh
0x1400095ae  lea     rdx, [rsp+340h+var_2F8]
0x1400095b3  mov     rcx, rsi
0x1400095b6  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1400095bc  dec     rbx
0x1400095bf  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
0x1400095c3  mov     r9, rbx; unsigned __int64
0x1400095c6  mov     r8, rdi; unsigned __int16 *
0x1400095c9  mov     edx, 104h; unsigned __int64
0x1400095ce  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400095d3  mov     [rsi+8], eax
0x1400095d6  lea     rcx, [rsp+340h+var_2D0]; void *
0x1400095db  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1400095e2  mov     [rsp+340h+var_2E0], 0E9h
0x1400095ea  mov     [rsp+340h+var_2F8], rax
0x1400095ef  xor     edx, edx; Val
0x1400095f1  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x1400095f8  mov     [rsp+340h+var_2DC], 0Ah
0x140009600  mov     [rsp+340h+var_2F0], rax
0x140009605  lea     rax, aIncichlh; "INCICHLH"
0x14000960c  mov     [rsp+340h+var_2E8], rax
0x140009611  lea     r8d, [rdx+78h]; Size
0x140009615  mov     [rsp+340h+var_2D8], 0FFh
0x14000961d  mov     [rbp+240h+var_258], 1000000h
0x140009624  call    memset_0
0x140009629  lea     r8, aStringcchcopyn_0; "StringCchCopyN"
0x140009630  mov     rcx, rsi
0x140009633  lea     rdx, [rsp+340h+var_2F8]
0x140009638  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14000963d  add     rbx, rbx
0x140009640  cmp     rbx, 208h
0x140009647  jnb     loc_14000975D
0x14000964d  xor     eax, eax
0x14000964f  lea     rdi, [rbp+240h+var_250]
0x140009653  mov     [rbp+rbx+240h+var_250], ax
0x140009658  mov     [rsp+340h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140009661  xor     r9d, r9d; lpSecurityAttributes
0x140009664  mov     [rsp+340h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x140009669  mov     r8d, r12d; dwShareMode
0x14000966c  mov     edx, r15d; dwDesiredAccess
0x14000966f  mov     [rsp+340h+dwCreationDisposition], 3; dwCreationDisposition
0x140009677  mov     rcx, rdi; lpFileName
0x14000967a  call    cs:__imp_CreateFileW
0x140009680  mov     [r14], rax
0x140009683  mov     rbx, rax
0x140009686  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000968a  jnz     loc_14000998B
0x140009690  xor     r13d, r13d
0x140009693  mov     [r14], r13
0x140009696  call    cs:__imp_GetLastError
0x14000969c  mov     ebx, eax
0x14000969e  cmp     [rbp+240h+arg_20], r13b
0x1400096a5  jz      loc_1400098E1
0x1400096ab  mov     ecx, [rbp+240h+arg_28]
0x1400096b1  test    ecx, ecx
0x1400096b3  jz      loc_14000986A
0x1400096b9  sub     ecx, 1
0x1400096bc  jz      loc_1400097E3
0x1400096c2  cmp     ecx, 1
0x1400096c5  jnz     loc_14000986A
0x1400096cb  test    eax, eax
0x1400096cd  jle     short loc_1400096D8
0x1400096cf  movzx   ebx, bx
0x1400096d2  or      ebx, 80070000h
0x1400096d8  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1400096df  mov     [rsp+340h+var_2E0], 10Eh
0x1400096e7  mov     [rsp+340h+var_2F8], rax
0x1400096ec  lea     rcx, [rsp+340h+var_2D0]; void *
0x1400096f1  xor     edx, edx; Val
0x1400096f3  mov     [rsp+340h+var_2DC], 2
0x1400096fb  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x140009702  mov     [rsp+340h+var_2D8], 0FFh
0x14000970a  mov     [rsp+340h+var_2F0], rax
0x14000970f  lea     rax, aIncichlh; "INCICHLH"
0x140009716  mov     [rsp+340h+var_2E8], rax
0x14000971b  lea     r8d, [rdx+78h]; Size
0x14000971f  mov     [rbp+240h+var_258], 1000000h
0x140009726  call    memset_0
0x14000972b  mov     [rsp+340h+var_308], r12d
0x140009730  lea     r9, aCreatefilewS0x; "CreateFileW(%s,0x%08lx,0x%08lx,...)"
0x140009737  mov     dword ptr [rsp+340h+hTemplateFile], r15d
0x14000973c  lea     rdx, [rsp+340h+var_2F8]
0x140009741  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x140009746  mov     r8d, ebx
0x140009749  mov     qword ptr [rsp+340h+dwCreationDisposition], r9
0x14000974e  mov     rcx, rsi
0x140009751  mov     r9d, 80042306h
0x140009757  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
0x14000975d  call    __report_rangecheckfailure
0x140009763  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x14000976a  mov     [rsp+340h+var_2E0], 0DAh
0x140009772  mov     [rsp+340h+var_2F8], rax
0x140009777  lea     rcx, [rsp+340h+var_2D0]; void *
0x14000977c  xor     edx, edx; Val
0x14000977e  mov     [rsp+340h+var_2DC], 0Ah
0x140009786  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x14000978d  mov     [rsp+340h+var_2D8], 0FFh
0x140009795  mov     [rsp+340h+var_2F0], rax
0x14000979a  lea     rax, aIncichlh; "INCICHLH"
0x1400097a1  mov     [rsp+340h+var_2E8], rax
0x1400097a6  lea     r8d, [rdx+78h]; Size
0x1400097aa  mov     [rbp+240h+var_258], 1000000h
0x1400097b1  call    memset_0
0x1400097b6  mov     [rsp+340h+hTemplateFile], rbx
0x1400097bb  lea     r9, aErrorTheBuffer; "Error: the buffer is too small to fit %"...
0x1400097c2  mov     [rsp+340h+dwFlagsAndAttributes], 104h
0x1400097ca  lea     rdx, [rsp+340h+var_2F8]
0x1400097cf  mov     r8d, 8000FFFFh
0x1400097d5  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x1400097da  mov     rcx, rsi
0x1400097dd  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1400097e3  test    ebx, ebx
0x1400097e5  jle     short loc_1400097F0
0x1400097e7  movzx   ebx, bx
0x1400097ea  or      ebx, 80070000h
0x1400097f0  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1400097f7  mov     [rsp+340h+var_2E0], 108h
0x1400097ff  mov     [rsp+340h+var_2F8], rax
0x140009804  lea     rcx, [rsp+340h+var_2D0]; void *
0x140009809  xor     edx, edx; Val
0x14000980b  mov     [rsp+340h+var_2DC], 1
0x140009813  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x14000981a  mov     [rsp+340h+var_2D8], 0FFh
0x140009822  mov     [rsp+340h+var_2F0], rax
0x140009827  lea     rax, aIncichlh; "INCICHLH"
0x14000982e  mov     [rsp+340h+var_2E8], rax
0x140009833  lea     r8d, [rdx+78h]; Size
0x140009837  mov     [rbp+240h+var_258], 1000000h
0x14000983e  call    memset_0
0x140009843  mov     dword ptr [rsp+340h+hTemplateFile], r12d
0x140009848  lea     r9, aCreatefilewS0x; "CreateFileW(%s,0x%08lx,0x%08lx,...)"
0x14000984f  mov     [rsp+340h+dwFlagsAndAttributes], r15d
0x140009854  lea     rdx, [rsp+340h+var_2F8]
0x140009859  mov     r8d, ebx
0x14000985c  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x140009861  mov     rcx, rsi
0x140009864  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14000986a  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140009871  mov     [rsp+340h+var_2E0], 102h
0x140009879  mov     [rsp+340h+var_2F8], rax
0x14000987e  lea     rcx, [rsp+340h+var_2D0]; void *
0x140009883  xor     edx, edx; Val
0x140009885  mov     [rsp+340h+var_2DC], 0Ah
0x14000988d  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x140009894  mov     [rsp+340h+var_2D8], 0FFh
0x14000989c  mov     [rsp+340h+var_2F0], rax
0x1400098a1  lea     rax, aIncichlh; "INCICHLH"
0x1400098a8  mov     [rsp+340h+var_2E8], rax
0x1400098ad  lea     r8d, [rdx+78h]; Size
0x1400098b1  mov     [rbp+240h+var_258], 1000000h
0x1400098b8  call    memset_0
0x1400098bd  lea     r9, aCouldNotOpenTh; "Could not open the object '%s'. [0x%08l"...
0x1400098c4  mov     [rsp+340h+dwFlagsAndAttributes], ebx
0x1400098c8  mov     r8d, 8000FFFFh
0x1400098ce  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x1400098d3  lea     rdx, [rsp+340h+var_2F8]
0x1400098d8  mov     rcx, rsi
0x1400098db  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400098e1  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1400098e8  mov     [rsp+340h+var_2E0], 117h
0x1400098f0  mov     [rsp+340h+var_2F8], rax
0x1400098f5  lea     rcx, [rsp+340h+var_2D0]; void *
0x1400098fa  xor     edx, edx; Val
0x1400098fc  mov     [rsp+340h+var_2DC], 0Ah
0x140009904  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x14000990b  mov     [rsp+340h+var_2D8], 0FFh
0x140009913  mov     [rsp+340h+var_2F0], rax
0x140009918  lea     rax, aIncichlh; "INCICHLH"
0x14000991f  mov     [rsp+340h+var_2E8], rax
0x140009924  lea     r8d, [rdx+78h]; Size
0x140009928  mov     [rbp+240h+var_258], 1000000h
0x14000992f  call    memset_0
0x140009934  mov     r9, rdi
0x140009937  mov     [rsp+340h+dwCreationDisposition], ebx
0x14000993b  lea     r8, aCouldNotOpenTh; "Could not open the object '%s'. [0x%08l"...
0x140009942  mov     rcx, rsi
0x140009945  lea     rdx, [rsp+340h+var_2F8]
0x14000994a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000994f  cmp     [rbp+240h+arg_28], 7
0x140009956  jnz     short loc_140009967
0x140009958  test    ebx, ebx
0x14000995a  jle     short loc_140009986
0x14000995c  movzx   ebx, bx
0x14000995f  or      ebx, 80070000h
0x140009965  jmp     short loc_140009986
0x140009967  cmp     ebx, 15h
0x14000996a  jz      short loc_140009981
0x14000996c  lea     eax, [rbx-2]
0x14000996f  cmp     eax, 1
0x140009972  jbe     short loc_140009981
0x140009974  cmp     ebx, 48Fh
0x14000997a  mov     ebx, 8000FFFFh
0x14000997f  jnz     short loc_140009986
0x140009981  mov     ebx, 80042308h
0x140009986  mov     [rsi+8], ebx
0x140009989  jmp     short loc_140009A06
0x14000998b  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x140009992  mov     [rsp+340h+var_2E0], 12Ch
0x14000999a  mov     [rsp+340h+var_2F8], rax
0x14000999f  lea     rcx, [rsp+340h+var_2D0]; void *
0x1400099a4  xor     edx, edx; Val
0x1400099a6  mov     [rsp+340h+var_2DC], 0Ah
0x1400099ae  lea     rax, aCvssioctlchann_0; "CVssIOCTLChannel::Open"
0x1400099b5  mov     [rsp+340h+var_2D8], 0FFh
0x1400099bd  mov     [rsp+340h+var_2F0], rax
0x1400099c2  lea     rax, aIncichlh; "INCICHLH"
0x1400099c9  mov     [rsp+340h+var_2E8], rax
0x1400099ce  lea     r8d, [rdx+78h]; Size
0x1400099d2  mov     [rbp+240h+var_258], 1000000h
0x1400099d9  call    memset_0
0x1400099de  mov     r9, rdi
0x1400099e1  mov     qword ptr [rsp+340h+dwCreationDisposition], rbx
0x1400099e6  lea     r8, aTheObjectSWasO; "The object '%s'. was opened under the d"...
0x1400099ed  mov     rcx, rsi
0x1400099f0  lea     rdx, [rsp+340h+var_2F8]
0x1400099f5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400099fa  lea     rcx, [r14+60h]
0x1400099fe  mov     rdx, rdi
0x140009a01  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x140009a06  mov     eax, [rsi+8]
0x140009a09  mov     rcx, [rbp+240h+var_40]
0x140009a10  xor     rcx, rsp; StackCookie
0x140009a13  call    __security_check_cookie
0x140009a18  mov     rbx, [rsp+340h+arg_18]
0x140009a20  add     rsp, 310h
0x140009a27  pop     r15
0x140009a29  pop     r14
0x140009a2b  pop     r13
  ... truncated ...
```
