# SxGetPresentableVolumeName(ushort const *,ushort *,ulong)

- ea: `0x18002936c`
- end: `0x1800295b5`
- name: `?SxGetPresentableVolumeName@@YAJPEBGPEAGK@Z`
- size: `585`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028ee8`

## callees

- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x180026cf4`
- `0x18002936c`
- `0x18002b404`
- `0x18002b530`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029459`
- `KERNEL32!GetLastError` at `0x180029459`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002944b`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002944b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002958d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002958d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180029422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180029422`

## pseudocode

```c
__int64 __fastcall SxGetPresentableVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2, DWORD a3)
{
  WCHAR *v5; // rbx
  __int16 v6; // ax
  DWORD v7; // eax
  WCHAR *v8; // rax
  signed int LastError; // eax
  unsigned int v10; // r9d
  WCHAR *v11; // r8
  const unsigned __int16 *i; // r11
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // r11
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  int v24; // [rsp+40h] [rbp-29h] BYREF
  __int16 v25; // [rsp+44h] [rbp-25h]
  __int16 v26; // [rsp+46h] [rbp-23h]
  DWORD cchReturnLength; // [rsp+E0h] [rbp+77h] BYREF

  cchReturnLength = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)lpszVolumeName, (char)a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "SxGetPresentableVolumeName", 50, 1);
  cchReturnLength = 0;
  v5 = 0;
  v6 = 61;
  if ( !lpszVolumeName )
    goto LABEL_34;
  v25 = 61;
  if ( !a2 )
  {
    v6 = 62;
LABEL_34:
    v26 = v6;
    v24 = -2147024809;
    goto LABEL_35;
  }
  v24 = 0;
  v25 = 63;
  v7 = 261;
  *a2 = 0;
  cchReturnLength = 261;
  while ( 1 )
  {
    v8 = (WCHAR *)CoTaskMemRealloc(v5, 2LL * v7);
    v5 = v8;
    if ( !v8 )
    {
      v24 = -2147024882;
      v26 = 74;
      goto LABEL_35;
    }
    v24 = 0;
    v25 = 74;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v8, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v24 = LastError;
    if ( LastError < 0 )
    {
      v26 = 84;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)lpszVolumeName,
          LastError);
      goto LABEL_35;
    }
    v7 = cchReturnLength;
    v25 = 84;
  }
  v10 = -1;
  v11 = v5;
  for ( i = v5; *v11; v11 += v15 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v11[v13] );
    v14 = v11;
    if ( (unsigned int)v13 >= v10 )
      v14 = i;
    i = v14;
    v15 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= v10 )
      LODWORD(v13) = v10;
    v10 = v13;
  }
  v24 = StringCchCopyW(a2, 0x104u, i);
  if ( v24 >= 0 )
  {
    v25 = 112;
  }
  else
  {
    v26 = 112;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sSSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, v18, (__int64)lpszVolumeName, v19);
  }
LABEL_35:
  CoTaskMemFree(v5);
  v20 = v24;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24, v21, v22);
  return v20;
}

```

## disassembly

```asm
0x18002936c  mov     [rsp-8+cchReturnLength], r8d
0x180029371  push    rbp
0x180029372  push    rbx
0x180029373  push    rsi
0x180029374  push    rdi
0x180029375  push    r12
0x180029377  push    r13
0x180029379  push    r14
0x18002937b  push    r15
0x18002937d  lea     rbp, [rsp-1Fh]
0x180029382  sub     rsp, 88h
0x180029389  mov     rsi, rdx
0x18002938c  mov     rdi, rcx
0x18002938f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029396  lea     r12, WPP_GLOBAL_Control
0x18002939d  cmp     rcx, r12
0x1800293a0  jz      short loc_1800293BC
0x1800293a2  test    dword ptr [rcx+1Ch], 20000000h
0x1800293a9  jz      short loc_1800293BC
0x1800293ab  mov     rcx, [rcx+10h]
0x1800293af  mov     r9, rdi
0x1800293b2  mov     [rsp+0C0h+var_A0], rdx
0x1800293b7  call    WPP_SF_Sqd
0x1800293bc  mov     r9d, 1; unsigned __int16
0x1800293c2  lea     rdx, aSxgetpresentab; "SxGetPresentableVolumeName"
0x1800293c9  lea     rcx, [rbp+57h+var_80]; this
0x1800293cd  lea     r8d, [r9+31h]; unsigned __int16
0x1800293d1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800293d6  xor     r14d, r14d
0x1800293d9  mov     [rbp+57h+cchReturnLength], r14d
0x1800293dd  mov     ebx, r14d
0x1800293e0  lea     eax, [r14+3Dh]
0x1800293e4  test    rdi, rdi
0x1800293e7  jz      loc_18002957F
0x1800293ed  mov     [rbp+57h+var_7C], ax
0x1800293f1  test    rsi, rsi
0x1800293f4  jz      loc_18002957A
0x1800293fa  lea     eax, [r14+3Fh]
0x1800293fe  mov     [rbp+57h+var_80], r14d
0x180029402  mov     [rbp+57h+var_7C], ax
0x180029406  lea     r15d, [r14+4Ah]
0x18002940a  mov     eax, 105h
0x18002940f  mov     [rsi], r14w
0x180029413  mov     [rbp+57h+cchReturnLength], eax
0x180029416  lea     r13d, [r14+54h]
0x18002941a  mov     edx, eax
0x18002941c  mov     rcx, rbx; pv
0x18002941f  add     rdx, rdx; cb
0x180029422  call    cs:__imp_CoTaskMemRealloc
0x180029428  mov     rbx, rax
0x18002942b  test    rax, rax
0x18002942e  jz      loc_18002956C
0x180029434  mov     r8d, [rbp+57h+cchReturnLength]; cchBufferLength
0x180029438  lea     r9, [rbp+57h+cchReturnLength]; lpcchReturnLength
0x18002943c  mov     rdx, rax; lpszVolumePathNames
0x18002943f  mov     [rbp+57h+var_80], r14d
0x180029443  mov     rcx, rdi; lpszVolumeName
0x180029446  mov     [rbp+57h+var_7C], r15w
0x18002944b  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180029451  test    eax, eax
0x180029453  jnz     loc_1800294D9
0x180029459  call    cs:__imp_GetLastError
0x18002945f  cmp     eax, 7Ah ; 'z'
0x180029462  jz      short loc_180029479
0x180029464  cmp     eax, 0EAh
0x180029469  jz      short loc_180029479
0x18002946b  test    eax, eax
0x18002946d  jle     short loc_18002947C
0x18002946f  movzx   eax, ax
0x180029472  or      eax, 80070000h
0x180029477  jmp     short loc_18002947C
0x180029479  mov     eax, r14d
0x18002947c  mov     [rbp+57h+var_80], eax
0x18002947f  test    eax, eax
0x180029481  js      short loc_18002948D
0x180029483  mov     eax, [rbp+57h+cchReturnLength]
0x180029486  mov     [rbp+57h+var_7C], r13w
0x18002948b  jmp     short loc_18002941A
0x18002948d  mov     [rbp+57h+var_7A], r13w
0x180029492  mov     rcx, cs:WPP_GLOBAL_Control
0x180029499  cmp     rcx, r12
0x18002949c  jz      loc_18002958A
0x1800294a2  test    dword ptr [rcx+1Ch], 2000000h
0x1800294a9  jz      loc_18002958A
0x1800294af  mov     rcx, [rcx+10h]
0x1800294b3  lea     r9, aDwerr; "dwErr"
0x1800294ba  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800294be  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800294c5  mov     edx, 0Bh
0x1800294ca  mov     [rsp+0C0h+var_A0], rdi
0x1800294cf  call    WPP_SF_sSd
0x1800294d4  jmp     loc_18002958A
0x1800294d9  or      r9d, 0FFFFFFFFh
0x1800294dd  mov     r8, rbx
0x1800294e0  mov     r11, rbx
0x1800294e3  cmp     [rbx], r14w
0x1800294e7  jz      short loc_180029518
0x1800294e9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800294ed  inc     rdx
0x1800294f0  cmp     [r8+rdx*2], r14w
0x1800294f5  jnz     short loc_1800294ED
0x1800294f7  cmp     edx, r9d
0x1800294fa  mov     rax, r8
0x1800294fd  cmovnb  rax, r11
0x180029501  mov     r11, rax
0x180029504  lea     eax, [rdx+1]
0x180029507  cmovnb  edx, r9d
0x18002950b  mov     r9d, edx
0x18002950e  lea     r8, [r8+rax*2]
0x180029512  cmp     [r8], r14w
0x180029516  jnz     short loc_1800294E9
0x180029518  mov     r8, r11; unsigned __int16 *
0x18002951b  mov     edx, 104h; unsigned __int64
0x180029520  mov     rcx, rsi; unsigned __int16 *
0x180029523  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029528  mov     [rbp+57h+var_80], eax
0x18002952b  mov     ecx, 70h ; 'p'
0x180029530  test    eax, eax
0x180029532  jns     short loc_180029566
0x180029534  mov     [rbp+57h+var_7A], cx
0x180029538  mov     rcx, cs:WPP_GLOBAL_Control
0x18002953f  cmp     rcx, r12
0x180029542  jz      short loc_18002958A
0x180029544  test    dword ptr [rcx+1Ch], 2000000h
0x18002954b  jz      short loc_18002958A
0x18002954d  mov     rcx, [rcx+10h]
0x180029551  mov     [rsp+0C0h+var_88], eax
0x180029555  mov     [rsp+0C0h+var_98], r11
0x18002955a  mov     [rsp+0C0h+var_A0], rdi
0x18002955f  call    WPP_SF_sSSdd
0x180029564  jmp     short loc_18002958A
0x180029566  mov     [rbp+57h+var_7C], cx
0x18002956a  jmp     short loc_18002958A
0x18002956c  mov     [rbp+57h+var_80], 8007000Eh
0x180029573  mov     [rbp+57h+var_7A], r15w
0x180029578  jmp     short loc_18002958A
0x18002957a  mov     eax, 3Eh ; '>'
0x18002957f  mov     [rbp+57h+var_7A], ax
0x180029583  mov     [rbp+57h+var_80], 80070057h
0x18002958a  mov     rcx, rbx; pv
0x18002958d  call    cs:__imp_CoTaskMemFree
0x180029593  mov     ebx, [rbp+57h+var_80]
0x180029596  lea     rcx, [rbp+57h+var_80]; this
0x18002959a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002959f  mov     eax, ebx
0x1800295a1  add     rsp, 88h
0x1800295a8  pop     r15
0x1800295aa  pop     r14
0x1800295ac  pop     r13
0x1800295ae  pop     r12
0x1800295b0  pop     rdi
0x1800295b1  pop     rsi
0x1800295b2  pop     rbx
0x1800295b3  pop     rbp
0x1800295b4  retn
```
