# CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)

- ea: `0x18000610c`
- end: `0x1800066f3`
- name: `?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z`
- size: `1511`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `34`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800051a0`
- `0x180006cb0`
- `0x180007374`
- `0x180011178`
- `0x180014a00`
- `0x180016550`
- `0x180019d64`
- `0x180019ecc`
- `0x18001a0d0`
- `0x18001b130`
- `0x18001c5dc`
- `0x18001e53c`
- `0x18001e6f8`
- `0x18001fb80`
- `0x180020638`
- `0x18002131c`
- `0x180021bc4`
- `0x1800235e0`
- `0x180023834`
- `0x18002432c`
- `0x180024a6c`
- `0x180025228`
- `0x1800298a0`
- `0x180029e60`
- `0x18002a4f8`
- `0x18002acd4`
- `0x18002b198`
- `0x18002b490`
- `0x18002e3a0`
- `0x180039394`
- `0x180040688`
- `0x180040a54`
- `0x180040cb0`
- `0x180041418`

## callees

- `0x180001580`
- `0x1800016c0`
- `0x18000212c`
- `0x180004944`
- `0x180004a38`
- `0x180004a78`
- `0x18000610c`
- `0x1800075b0`
- `0x18003649c`
- `0x1800367b8`
- `0x180037080`
- `0x18003750c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006356`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000633d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000633d`

## string_xrefs

- `0x1800061b7`: `Opening a handle to %s (access = 0x%08lx, share = 0x%08lx)`
- `0x1800062ea`: `StringCchCopyN`
- `0x1800063f0`: `CreateFileW(%s,0x%08lx,0x%08lx,...)`
- `0x180006508`: `CreateFileW(%s,0x%08lx,0x%08lx,...)`
- `0x18000657d`: `Could not open the object '%s'. [0x%08lx]\n`
- `0x1800065fb`: `Could not open the object '%s'. [0x%08lx]\n`
- `0x1800066a6`: `The object '%s'. was opened under the device handle 0x%08lx`
- `0x18000615c`: `CVssIOCTLChannel::Open`
- `0x18000622d`: `CVssIOCTLChannel::Open`
- `0x1800062b2`: `CVssIOCTLChannel::Open`
- `0x1800063bb`: `CVssIOCTLChannel::Open`
- `0x180006446`: `CVssIOCTLChannel::Open`
- `0x1800064d3`: `CVssIOCTLChannel::Open`
- `0x18000654d`: `CVssIOCTLChannel::Open`
- `0x1800065c4`: `CVssIOCTLChannel::Open`
- `0x18000666e`: `CVssIOCTLChannel::Open`

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
        __int64 a8,
        DWORD a9)
{
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  HANDLE FileW; // rax
  HANDLE v18; // rbx
  signed int LastError; // eax
  unsigned int v20; // ebx
  bool v21; // zf
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v28; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  int v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[120]; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v35[264]; // [rsp+F0h] [rbp-10h] BYREF

  v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
  v30 = 200;
  v28 = L"CVssIOCTLChannel::Open";
  v31 = 10;
  v29 = L"INCICHLH";
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::Trace(
    a2,
    &v27,
    L"Opening a handle to %s (access = 0x%08lx, share = 0x%08lx)",
    a3,
    dwDesiredAccess,
    3);
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
      v30 = 218;
      v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v31 = 10;
      v32 = 255;
      v28 = L"CVssIOCTLChannel::Open";
      v29 = L"INCICHLH";
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      dwFlagsAndAttributes[0] = 260;
      CVssFunctionTracer::TranslateGenericError(
        a2,
        &v27,
        2147549183LL,
        L"Error: the buffer is too small to fit %s (%d < %d)",
        a3,
        *(_QWORD *)dwFlagsAndAttributes,
        v13);
    }
    if ( a3[v13 - 1] != 92 )
    {
      v30 = 226;
      v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v31 = 10;
      v32 = 255;
      v28 = L"CVssIOCTLChannel::Open";
      v29 = L"INCICHLH";
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::TranslateGenericError(
        a2,
        &v27,
        2147549183LL,
        L"Error: the object name %s does terminate with a backslash",
        a3);
    }
    v14 = v13 - 1;
    *(_DWORD *)(a2 + 8) = StringCchCopyNW(v35, 0x104u, a3, v14);
    v30 = 233;
    v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v31 = 10;
    v28 = L"CVssIOCTLChannel::Open";
    v29 = L"INCICHLH";
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::CheckForErrorInternal(a2, &v27, L"StringCchCopyN");
    v16 = v14;
    if ( v16 >= 260 )
      _report_rangecheckfailure(v15);
    v35[v16] = 0;
    a3 = v35;
  }
  FileW = CreateFileW(a3, dwDesiredAccess, 3u, 0, 3u, a9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  *(_QWORD *)a1 = FileW;
  v18 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *(_QWORD *)a1 = 0;
    LastError = GetLastError();
    v20 = LastError;
    if ( a5 )
    {
      if ( a6 )
      {
        if ( a6 == 1 )
        {
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          v30 = 264;
          v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v31 = 1;
          v32 = 255;
          v28 = L"CVssIOCTLChannel::Open";
          v29 = L"INCICHLH";
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          LODWORD(hTemplateFile) = 3;
          dwFlagsAndAttributesa[0] = dwDesiredAccess;
          CVssFunctionTracer::TranslateGenericError(
            a2,
            &v27,
            v20,
            L"CreateFileW(%s,0x%08lx,0x%08lx,...)",
            a3,
            *(_QWORD *)dwFlagsAndAttributesa,
            hTemplateFile);
        }
        if ( a6 == 2 )
        {
          if ( LastError > 0 )
            v20 = (unsigned __int16)LastError | 0x80070000;
          v30 = 270;
          v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
          v31 = 2;
          v32 = 255;
          v28 = L"CVssIOCTLChannel::Open";
          v29 = L"INCICHLH";
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          LODWORD(hTemplateFile) = dwDesiredAccess;
          CVssFunctionTracer::TranslateInternalProviderError(
            a2,
            &v27,
            v20,
            2147754758LL,
            L"CreateFileW(%s,0x%08lx,0x%08lx,...)",
            a3,
            hTemplateFile,
            3);
        }
      }
      v30 = 258;
      v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v31 = 10;
      v32 = 255;
      v28 = L"CVssIOCTLChannel::Open";
      v29 = L"INCICHLH";
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      dwFlagsAndAttributesa[0] = v20;
      CVssFunctionTracer::Throw(
        a2,
        &v27,
        2147549183LL,
        L"Could not open the object '%s'. [0x%08lx]\n",
        a3,
        *(_QWORD *)dwFlagsAndAttributesa);
    }
    v30 = 279;
    v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v31 = 10;
    v32 = 255;
    v28 = L"CVssIOCTLChannel::Open";
    v29 = L"INCICHLH";
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    dwCreationDisposition[0] = v20;
    CVssFunctionTracer::Trace(
      a2,
      &v27,
      L"Could not open the object '%s'. [0x%08lx]\n",
      a3,
      *(_QWORD *)dwCreationDisposition);
    if ( a6 == 7 )
    {
      if ( (int)v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
    }
    else if ( v20 == 21 || v20 - 2 <= 1 || (v21 = v20 == 1167, v20 = -2147418113, v21) )
    {
      v20 = -2147212536;
    }
    *(_DWORD *)(a2 + 8) = v20;
  }
  else
  {
    v30 = 300;
    v27 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v31 = 10;
    v32 = 255;
    v28 = L"CVssIOCTLChannel::Open";
    v29 = L"INCICHLH";
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Trace(a2, &v27, L"The object '%s'. was opened under the device handle 0x%08lx", a3, v18);
    CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)a1 + 96, a3);
  }
  return *(unsigned int *)(a2 + 8);
}

```

## disassembly

```asm
0x18000610c  mov     [rsp-8+arg_18], rbx
0x180006111  push    rbp
0x180006112  push    rsi
0x180006113  push    rdi
0x180006114  push    r12
0x180006116  push    r13
0x180006118  push    r14
0x18000611a  push    r15
0x18000611c  lea     rbp, [rsp-210h]
0x180006124  sub     rsp, 310h
0x18000612b  mov     rax, cs:__security_cookie
0x180006132  xor     rax, rsp
0x180006135  mov     [rbp+240h+var_40], rax
0x18000613c  mov     r15d, [rbp+240h+dwDesiredAccess]
0x180006143  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x18000614a  mov     r12d, [rbp+240h+arg_40]
0x180006151  mov     rdi, r8
0x180006154  mov     [rsp+340h+var_2F8], rax
0x180006159  mov     rsi, rdx
0x18000615c  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x180006163  mov     [rsp+340h+var_2E0], 0C8h
0x18000616b  mov     [rsp+340h+var_2F0], rax
0x180006170  mov     r14, rcx
0x180006173  lea     rax, aIncichlh; "INCICHLH"
0x18000617a  mov     [rsp+340h+var_2DC], 0Ah
0x180006182  xor     r13d, r13d
0x180006185  mov     [rsp+340h+var_2E8], rax
0x18000618a  xor     edx, edx; Val
0x18000618c  mov     [rsp+340h+var_2D8], 0FFh
0x180006194  lea     rcx, [rsp+340h+var_2D0]; void *
0x180006199  mov     [rbp+240h+var_258], 1000000h
0x1800061a0  mov     bl, r9b
0x1800061a3  lea     r8d, [r13+78h]; Size
0x1800061a7  call    memset_0
0x1800061ac  mov     r9, rdi
0x1800061af  mov     [rsp+340h+dwFlagsAndAttributes], 3
0x1800061b7  lea     r8, aOpeningAHandle; "Opening a handle to %s (access = 0x%08l"...
0x1800061be  mov     [rsp+340h+dwCreationDisposition], r15d
0x1800061c3  lea     rdx, [rsp+340h+var_2F8]
0x1800061c8  mov     rcx, rsi
0x1800061cb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800061d0  mov     rcx, r14; this
0x1800061d3  mov     [rsi+8], r13d
0x1800061d7  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x1800061dc  test    bl, bl
0x1800061de  jz      loc_180006318
0x1800061e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800061e8  inc     rbx
0x1800061eb  cmp     [rdi+rbx*2], r13w
0x1800061f0  jnz     short loc_1800061E8
0x1800061f2  lea     rax, [rbx-1]
0x1800061f6  cmp     rax, 103h
0x1800061fc  ja      loc_180006423
0x180006202  cmp     word ptr [rdi+rbx*2-2], 5Ch ; '\'
0x180006208  jz      short loc_18000627D
0x18000620a  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180006211  mov     [rsp+340h+var_2E0], 0E2h
0x180006219  mov     [rsp+340h+var_2F8], rax
0x18000621e  lea     rcx, [rsp+340h+var_2D0]; void *
0x180006223  xor     edx, edx; Val
0x180006225  mov     [rsp+340h+var_2DC], 0Ah
0x18000622d  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x180006234  mov     [rsp+340h+var_2D8], 0FFh
0x18000623c  mov     [rsp+340h+var_2F0], rax
0x180006241  lea     rax, aIncichlh; "INCICHLH"
0x180006248  mov     [rsp+340h+var_2E8], rax
0x18000624d  lea     r8d, [rdx+78h]; Size
0x180006251  mov     [rbp+240h+var_258], 1000000h
0x180006258  call    memset_0
0x18000625d  lea     r9, aErrorTheObject; "Error: the object name %s does terminat"...
0x180006264  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x180006269  mov     r8d, 8000FFFFh
0x18000626f  lea     rdx, [rsp+340h+var_2F8]
0x180006274  mov     rcx, rsi
0x180006277  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18000627d  dec     rbx
0x180006280  lea     rcx, [rbp+240h+var_250]; unsigned __int16 *
0x180006284  mov     r9, rbx; unsigned __int64
0x180006287  mov     r8, rdi; unsigned __int16 *
0x18000628a  mov     edx, 104h; unsigned __int64
0x18000628f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180006294  mov     [rsi+8], eax
0x180006297  lea     rcx, [rsp+340h+var_2D0]; void *
0x18000629c  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1800062a3  mov     [rsp+340h+var_2E0], 0E9h
0x1800062ab  mov     [rsp+340h+var_2F8], rax
0x1800062b0  xor     edx, edx; Val
0x1800062b2  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x1800062b9  mov     [rsp+340h+var_2DC], 0Ah
0x1800062c1  mov     [rsp+340h+var_2F0], rax
0x1800062c6  lea     rax, aIncichlh; "INCICHLH"
0x1800062cd  mov     [rsp+340h+var_2E8], rax
0x1800062d2  lea     r8d, [rdx+78h]; Size
0x1800062d6  mov     [rsp+340h+var_2D8], 0FFh
0x1800062de  mov     [rbp+240h+var_258], 1000000h
0x1800062e5  call    memset_0
0x1800062ea  lea     r8, aStringcchcopyn; "StringCchCopyN"
0x1800062f1  mov     rcx, rsi
0x1800062f4  lea     rdx, [rsp+340h+var_2F8]
0x1800062f9  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1800062fe  add     rbx, rbx
0x180006301  cmp     rbx, 208h
0x180006308  jnb     loc_18000641D
0x18000630e  mov     [rbp+rbx+240h+var_250], r13w
0x180006314  lea     rdi, [rbp+240h+var_250]
0x180006318  mov     [rsp+340h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180006321  xor     r9d, r9d; lpSecurityAttributes
0x180006324  mov     [rsp+340h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180006329  mov     edx, r15d; dwDesiredAccess
0x18000632c  mov     r12d, 3
0x180006332  mov     rcx, rdi; lpFileName
0x180006335  mov     r8d, r12d; dwShareMode
0x180006338  mov     [rsp+340h+dwCreationDisposition], r12d; dwCreationDisposition
0x18000633d  call    cs:__imp_CreateFileW
0x180006343  mov     [r14], rax
0x180006346  mov     rbx, rax
0x180006349  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000634d  jnz     loc_18000664B
0x180006353  mov     [r14], r13
0x180006356  call    cs:__imp_GetLastError
0x18000635c  mov     ebx, eax
0x18000635e  cmp     [rbp+240h+arg_20], r13b
0x180006365  jz      loc_1800065A1
0x18000636b  mov     ecx, [rbp+240h+arg_28]
0x180006371  test    ecx, ecx
0x180006373  jz      loc_18000652A
0x180006379  sub     ecx, 1
0x18000637c  jz      loc_1800064A3
0x180006382  cmp     ecx, 1
0x180006385  jnz     loc_18000652A
0x18000638b  test    eax, eax
0x18000638d  jle     short loc_180006398
0x18000638f  movzx   ebx, bx
0x180006392  or      ebx, 80070000h
0x180006398  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x18000639f  mov     [rsp+340h+var_2E0], 10Eh
0x1800063a7  mov     [rsp+340h+var_2F8], rax
0x1800063ac  lea     rcx, [rsp+340h+var_2D0]; void *
0x1800063b1  xor     edx, edx; Val
0x1800063b3  mov     [rsp+340h+var_2DC], 2
0x1800063bb  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x1800063c2  mov     [rsp+340h+var_2D8], 0FFh
0x1800063ca  mov     [rsp+340h+var_2F0], rax
0x1800063cf  lea     rax, aIncichlh; "INCICHLH"
0x1800063d6  mov     [rsp+340h+var_2E8], rax
0x1800063db  lea     r8d, [rdx+78h]; Size
0x1800063df  mov     [rbp+240h+var_258], 1000000h
0x1800063e6  call    memset_0
0x1800063eb  mov     [rsp+340h+var_308], r12d
0x1800063f0  lea     r9, aCreatefilewS0x; "CreateFileW(%s,0x%08lx,0x%08lx,...)"
0x1800063f7  mov     dword ptr [rsp+340h+hTemplateFile], r15d
0x1800063fc  lea     rdx, [rsp+340h+var_2F8]
0x180006401  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rdi
0x180006406  mov     r8d, ebx
0x180006409  mov     qword ptr [rsp+340h+dwCreationDisposition], r9
0x18000640e  mov     rcx, rsi
0x180006411  mov     r9d, 80042306h
0x180006417  call    ?TranslateInternalProviderError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JJPEBGZZ; CVssFunctionTracer::TranslateInternalProviderError(CVssDebugInfo,long,long,ushort const *,...)
0x18000641d  call    __report_rangecheckfailure
0x180006423  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x18000642a  mov     [rsp+340h+var_2E0], 0DAh
0x180006432  mov     [rsp+340h+var_2F8], rax
0x180006437  lea     rcx, [rsp+340h+var_2D0]; void *
0x18000643c  xor     edx, edx; Val
0x18000643e  mov     [rsp+340h+var_2DC], 0Ah
0x180006446  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x18000644d  mov     [rsp+340h+var_2D8], 0FFh
0x180006455  mov     [rsp+340h+var_2F0], rax
0x18000645a  lea     rax, aIncichlh; "INCICHLH"
0x180006461  mov     [rsp+340h+var_2E8], rax
0x180006466  lea     r8d, [rdx+78h]; Size
0x18000646a  mov     [rbp+240h+var_258], 1000000h
0x180006471  call    memset_0
0x180006476  mov     [rsp+340h+hTemplateFile], rbx
0x18000647b  lea     r9, aErrorTheBuffer; "Error: the buffer is too small to fit %"...
0x180006482  mov     [rsp+340h+dwFlagsAndAttributes], 104h
0x18000648a  lea     rdx, [rsp+340h+var_2F8]
0x18000648f  mov     r8d, 8000FFFFh
0x180006495  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x18000649a  mov     rcx, rsi
0x18000649d  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800064a3  test    ebx, ebx
0x1800064a5  jle     short loc_1800064B0
0x1800064a7  movzx   ebx, bx
0x1800064aa  or      ebx, 80070000h
0x1800064b0  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1800064b7  mov     [rsp+340h+var_2E0], 108h
0x1800064bf  mov     [rsp+340h+var_2F8], rax
0x1800064c4  lea     rcx, [rsp+340h+var_2D0]; void *
0x1800064c9  xor     edx, edx; Val
0x1800064cb  mov     [rsp+340h+var_2DC], 1
0x1800064d3  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x1800064da  mov     [rsp+340h+var_2D8], 0FFh
0x1800064e2  mov     [rsp+340h+var_2F0], rax
0x1800064e7  lea     rax, aIncichlh; "INCICHLH"
0x1800064ee  mov     [rsp+340h+var_2E8], rax
0x1800064f3  lea     r8d, [rdx+78h]; Size
0x1800064f7  mov     [rbp+240h+var_258], 1000000h
0x1800064fe  call    memset_0
0x180006503  mov     dword ptr [rsp+340h+hTemplateFile], r12d
0x180006508  lea     r9, aCreatefilewS0x; "CreateFileW(%s,0x%08lx,0x%08lx,...)"
0x18000650f  mov     [rsp+340h+dwFlagsAndAttributes], r15d
0x180006514  lea     rdx, [rsp+340h+var_2F8]
0x180006519  mov     r8d, ebx
0x18000651c  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x180006521  mov     rcx, rsi
0x180006524  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18000652a  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180006531  mov     [rsp+340h+var_2E0], 102h
0x180006539  mov     [rsp+340h+var_2F8], rax
0x18000653e  lea     rcx, [rsp+340h+var_2D0]; void *
0x180006543  xor     edx, edx; Val
0x180006545  mov     [rsp+340h+var_2DC], 0Ah
0x18000654d  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x180006554  mov     [rsp+340h+var_2D8], 0FFh
0x18000655c  mov     [rsp+340h+var_2F0], rax
0x180006561  lea     rax, aIncichlh; "INCICHLH"
0x180006568  mov     [rsp+340h+var_2E8], rax
0x18000656d  lea     r8d, [rdx+78h]; Size
0x180006571  mov     [rbp+240h+var_258], 1000000h
0x180006578  call    memset_0
0x18000657d  lea     r9, aCouldNotOpenTh; "Could not open the object '%s'. [0x%08l"...
0x180006584  mov     [rsp+340h+dwFlagsAndAttributes], ebx
0x180006588  mov     r8d, 8000FFFFh
0x18000658e  mov     qword ptr [rsp+340h+dwCreationDisposition], rdi
0x180006593  lea     rdx, [rsp+340h+var_2F8]
0x180006598  mov     rcx, rsi
0x18000659b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800065a1  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x1800065a8  mov     [rsp+340h+var_2E0], 117h
0x1800065b0  mov     [rsp+340h+var_2F8], rax
0x1800065b5  lea     rcx, [rsp+340h+var_2D0]; void *
0x1800065ba  xor     edx, edx; Val
0x1800065bc  mov     [rsp+340h+var_2DC], 0Ah
0x1800065c4  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x1800065cb  mov     [rsp+340h+var_2D8], 0FFh
0x1800065d3  mov     [rsp+340h+var_2F0], rax
0x1800065d8  lea     rax, aIncichlh; "INCICHLH"
0x1800065df  mov     [rsp+340h+var_2E8], rax
0x1800065e4  lea     r8d, [rdx+78h]; Size
0x1800065e8  mov     [rbp+240h+var_258], 1000000h
0x1800065ef  call    memset_0
0x1800065f4  mov     r9, rdi
0x1800065f7  mov     [rsp+340h+dwCreationDisposition], ebx
0x1800065fb  lea     r8, aCouldNotOpenTh; "Could not open the object '%s'. [0x%08l"...
0x180006602  mov     rcx, rsi
0x180006605  lea     rdx, [rsp+340h+var_2F8]
0x18000660a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000660f  cmp     [rbp+240h+arg_28], 7
0x180006616  jnz     short loc_180006627
0x180006618  test    ebx, ebx
0x18000661a  jle     short loc_180006646
0x18000661c  movzx   ebx, bx
0x18000661f  or      ebx, 80070000h
0x180006625  jmp     short loc_180006646
0x180006627  cmp     ebx, 15h
0x18000662a  jz      short loc_180006641
0x18000662c  lea     eax, [rbx-2]
0x18000662f  cmp     eax, 1
0x180006632  jbe     short loc_180006641
0x180006634  cmp     ebx, 48Fh
0x18000663a  mov     ebx, 8000FFFFh
0x18000663f  jnz     short loc_180006646
0x180006641  mov     ebx, 80042308h
0x180006646  mov     [rsi+8], ebx
0x180006649  jmp     short loc_1800066C6
0x18000664b  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180006652  mov     [rsp+340h+var_2E0], 12Ch
0x18000665a  mov     [rsp+340h+var_2F8], rax
0x18000665f  lea     rcx, [rsp+340h+var_2D0]; void *
0x180006664  xor     edx, edx; Val
0x180006666  mov     [rsp+340h+var_2DC], 0Ah
0x18000666e  lea     rax, aCvssioctlchann_1; "CVssIOCTLChannel::Open"
0x180006675  mov     [rsp+340h+var_2D8], 0FFh
0x18000667d  mov     [rsp+340h+var_2F0], rax
0x180006682  lea     rax, aIncichlh; "INCICHLH"
0x180006689  mov     [rsp+340h+var_2E8], rax
0x18000668e  lea     r8d, [rdx+78h]; Size
0x180006692  mov     [rbp+240h+var_258], 1000000h
0x180006699  call    memset_0
0x18000669e  mov     r9, rdi
0x1800066a1  mov     qword ptr [rsp+340h+dwCreationDisposition], rbx
0x1800066a6  lea     r8, aTheObjectSWasO; "The object '%s'. was opened under the d"...
0x1800066ad  mov     rcx, rsi
0x1800066b0  lea     rdx, [rsp+340h+var_2F8]
0x1800066b5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800066ba  lea     rcx, [r14+60h]
0x1800066be  mov     rdx, rdi
0x1800066c1  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x1800066c6  mov     eax, [rsi+8]
0x1800066c9  mov     rcx, [rbp+240h+var_40]
0x1800066d0  xor     rcx, rsp; StackCookie
0x1800066d3  call    __security_check_cookie
0x1800066d8  mov     rbx, [rsp+340h+arg_18]
0x1800066e0  add     rsp, 310h
0x1800066e7  pop     r15
0x1800066e9  pop     r14
0x1800066eb  pop     r13
0x1800066ed  pop     r12
0x1800066ef  pop     rdi
  ... truncated ...
```
