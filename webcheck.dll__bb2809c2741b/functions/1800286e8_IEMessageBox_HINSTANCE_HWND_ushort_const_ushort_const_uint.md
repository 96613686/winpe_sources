# IEMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,uint,...)

- ea: `0x1800286e8`
- end: `0x180028973`
- name: `?IEMessageBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@PEBG2IZZ`
- size: `651`
- prototype: `__int64(HINSTANCE, HWND hWnd, const unsigned __int16 *, const unsigned __int16 *, unsigned int, ...)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019f80`

## callees

- `0x180028228`
- `0x1800286e8`
- `0x18002897c`
- `0x180028a30`
- `0x180028ae8`
- `0x180028ba4`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002879c`
- `KERNEL32!LocalFree` at `0x180028919`
- `KERNEL32!LocalFree` at `0x18002879c`
- `KERNEL32!LocalFree` at `0x180028919`
- `KERNEL32!FormatMessageW` at `0x180028793`
- `KERNEL32!FormatMessageW` at `0x180028793`
- `KERNEL32!SetLastError` at `0x180028946`
- `KERNEL32!SetLastError` at `0x180028946`
- `KERNEL32!ReleaseActCtx` at `0x180028910`
- `KERNEL32!ReleaseActCtx` at `0x180028910`
- `KERNEL32!DeactivateActCtx` at `0x180028907`
- `KERNEL32!DeactivateActCtx` at `0x180028907`
- `USER32!MessageBoxW` at `0x1800288eb`
- `USER32!MessageBoxW` at `0x1800288eb`

## string_xrefs

- `0x18002887a`: `TaskDialogIndirect`

## pseudocode

```c
__int64 IEMessageBox(HINSTANCE a1, HWND hWnd, const unsigned __int16 *a3, unsigned __int16 *a4, unsigned int a5, ...)
{
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  WCHAR *v11; // rdi
  char v12; // r14
  int v13; // ebx
  TASKDIALOG_FLAGS dwFlags; // ecx
  HICON v15; // r9
  unsigned int i; // edx
  void *v17; // rsi
  __int64 (__fastcall *v18)(_TASKDIALOGCONFIG *, unsigned int *, _QWORD, _QWORD); // rax
  DWORD v19; // ecx
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR ulCookie; // [rsp+58h] [rbp-A8h] BYREF
  _TASKDIALOGCONFIG v25; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[80]; // [rsp+100h] [rbp+0h] BYREF
  va_list va; // [rsp+228h] [rbp+128h] BYREF

  va_start(va, a5);
  v21 = 0;
  v8 = CIEMessageBoxHelper::s_ConstructTitleString(a1, hWnd, a4, v26);
  *(_QWORD *)Buffer = 0;
  va_copy(Arguments, va);
  v9 = CIEMessageBoxHelper::s_ResourceCStrToStr(a1, a3);
  v10 = v9;
  if ( v9 )
  {
    if ( *v9 )
    {
      FormatMessageW(0x500u, v9, 0, 0, Buffer, 0, &Arguments);
    }
    else
    {
      *(_QWORD *)Buffer = v9;
      v10 = 0;
    }
    LocalFree(v10);
  }
  v11 = *(WCHAR **)Buffer;
  Arguments = 0;
  if ( !*(_QWORD *)Buffer )
  {
    v13 = -2147024882;
LABEL_35:
    v21 = 0;
    goto LABEL_36;
  }
  v12 = 0;
  memset_0(&v25, 0, sizeof(v25));
  v25.cbSize = 160;
  v25.hwndParent = hWnd;
  v25.pszContent = v11;
  v25.pszWindowTitle = v8;
  v13 = CIEMessageBoxHelper::s_ConfigureDialogButtonsWithMessageBoxFlags(a5, &v25);
  if ( v13 >= 0 )
  {
    dwFlags = v25.dwFlags;
    if ( (a5 & 0x100000) != 0 )
    {
      dwFlags = v25.dwFlags | 0x2000;
      v25.dwFlags |= 0x2000u;
    }
    v15 = 0;
    v13 = -2147024809;
    for ( i = 0; i < 8; ++i )
    {
      if ( (a5 & 0xF0) == LODWORD(qword_18002EF80[2 * (int)i]) )
      {
        v15 = (HICON)qword_18002EF80[2 * (int)i + 1];
        v13 = 0;
        break;
      }
    }
    if ( (a5 & 0xF) == 0 )
      v25.dwFlags = dwFlags | 8;
    if ( v13 >= 0 )
    {
      v25.hMainIcon = v15;
      ulCookie = 0;
      v17 = (void *)CreateAndActivateContext(&ulCookie);
      v18 = (__int64 (__fastcall *)(_TASKDIALOGCONFIG *, unsigned int *, _QWORD, _QWORD))qword_180034198;
      if ( qword_180034198 == -1 )
      {
        GetProcFromComCtl32(&qword_180034198, "TaskDialogIndirect");
        v18 = (__int64 (__fastcall *)(_TASKDIALOGCONFIG *, unsigned int *, _QWORD, _QWORD))qword_180034198;
      }
      if ( v18 )
      {
        v13 = v18(&v25, &v21, 0, 0);
        if ( v13 >= 0 )
        {
          if ( (a5 & 0xF) == 0 && v21 == 2 )
            v21 = 1;
          goto LABEL_27;
        }
      }
      else
      {
        v13 = -2147467259;
      }
      v12 = 1;
      v21 = MessageBoxW(hWnd, v11, v8, a5 | 0x10000);
LABEL_27:
      if ( v17 != (void *)-1LL )
      {
        if ( ulCookie )
          DeactivateActCtx(0, ulCookie);
        ReleaseActCtx(v17);
      }
    }
  }
  LocalFree(v11);
  if ( v13 >= 0 )
    return v21;
  if ( !v12 )
    goto LABEL_35;
LABEL_36:
  v19 = (unsigned __int16)v13;
  if ( (v13 & 0x1FFF0000) != 0x70000 )
    v19 = v13;
  SetLastError(v19);
  return v21;
}

```

## disassembly

```asm
0x1800286e8  push    rbp
0x1800286ea  push    rbx
0x1800286eb  push    rsi
0x1800286ec  push    rdi
0x1800286ed  push    r12
0x1800286ef  push    r13
0x1800286f1  push    r14
0x1800286f3  push    r15
0x1800286f5  lea     rbp, [rsp-0B8h]
0x1800286fd  sub     rsp, 1B8h
0x180028704  mov     rax, cs:__security_cookie
0x18002870b  xor     rax, rsp
0x18002870e  mov     [rbp+0F0h+var_50], rax
0x180028715  mov     rax, r9
0x180028718  mov     rdi, r8
0x18002871b  xor     r13d, r13d
0x18002871e  lea     r9, [rbp+0F0h+var_F0]; unsigned __int16 *
0x180028722  mov     r8, rax; unsigned __int16 *
0x180028725  mov     [rsp+1F0h+var_1B0], r13d
0x18002872a  mov     r15, rdx
0x18002872d  mov     rbx, rcx
0x180028730  call    ?s_ConstructTitleString@CIEMessageBoxHelper@@SAPEBGPEAUHINSTANCE__@@PEAUHWND__@@PEBGPEAGH@Z; CIEMessageBoxHelper::s_ConstructTitleString(HINSTANCE__ *,HWND__ *,ushort const *,ushort *,int)
0x180028735  mov     r12, rax
0x180028738  mov     qword ptr [rsp+1F0h+Buffer], r13
0x18002873d  lea     rax, [rbp+0F0h+arg_28]
0x180028744  mov     rdx, rdi; unsigned __int16 *
0x180028747  mov     rcx, rbx; HINSTANCE
0x18002874a  mov     [rsp+1F0h+var_1A0], rax
0x18002874f  call    ?s_ResourceCStrToStr@CIEMessageBoxHelper@@SAPEAGPEAUHINSTANCE__@@PEBG@Z; CIEMessageBoxHelper::s_ResourceCStrToStr(HINSTANCE__ *,ushort const *)
0x180028754  mov     rbx, rax
0x180028757  test    rax, rax
0x18002875a  jz      short loc_1800287A2
0x18002875c  cmp     [rax], r13w
0x180028760  jnz     short loc_18002876C
0x180028762  mov     qword ptr [rsp+1F0h+Buffer], rax
0x180028767  mov     ebx, r13d
0x18002876a  jmp     short loc_180028799
0x18002876c  lea     rax, [rsp+1F0h+var_1A0]
0x180028771  xor     r9d, r9d; dwLanguageId
0x180028774  mov     [rsp+1F0h+Arguments], rax; Arguments
0x180028779  xor     r8d, r8d; dwMessageId
0x18002877c  lea     rax, [rsp+1F0h+Buffer]
0x180028781  mov     [rsp+1F0h+nSize], r13d; nSize
0x180028786  mov     rdx, rbx; lpSource
0x180028789  mov     [rsp+1F0h+lpBuffer], rax; lpBuffer
0x18002878e  mov     ecx, 500h; dwFlags
0x180028793  call    cs:__imp_FormatMessageW
0x180028799  mov     rcx, rbx; hMem
0x18002879c  call    cs:__imp_LocalFree
0x1800287a2  mov     rdi, qword ptr [rsp+1F0h+Buffer]
0x1800287a7  mov     [rsp+1F0h+var_1A0], r13
0x1800287ac  test    rdi, rdi
0x1800287af  jz      loc_18002892A
0x1800287b5  mov     ebx, 0A0h
0x1800287ba  lea     rcx, [rsp+1F0h+var_190]; void *
0x1800287bf  mov     r8d, ebx; Size
0x1800287c2  xor     edx, edx; Val
0x1800287c4  mov     r14b, r13b
0x1800287c7  call    memset_0
0x1800287cc  mov     esi, [rbp+0F0h+arg_20]
0x1800287d2  lea     rdx, [rsp+1F0h+var_190]; struct _TASKDIALOGCONFIG *
0x1800287d7  mov     ecx, esi; unsigned int
0x1800287d9  mov     [rsp+1F0h+var_190.cbSize], ebx
0x1800287dd  mov     [rsp+1F0h+var_190.hwndParent], r15
0x1800287e2  mov     [rbp+0F0h+var_190.pszContent], rdi
0x1800287e6  mov     [rsp+1F0h+var_190.pszWindowTitle], r12
0x1800287eb  call    ?s_ConfigureDialogButtonsWithMessageBoxFlags@CIEMessageBoxHelper@@CAJKPEAU_TASKDIALOGCONFIG@@@Z; CIEMessageBoxHelper::s_ConfigureDialogButtonsWithMessageBoxFlags(ulong,_TASKDIALOGCONFIG *)
0x1800287f0  mov     ebx, eax
0x1800287f2  test    eax, eax
0x1800287f4  js      loc_180028916
0x1800287fa  mov     ecx, [rsp+1F0h+var_190.dwFlags]
0x1800287fe  bt      esi, 14h
0x180028802  jnb     short loc_18002880C
0x180028804  bts     ecx, 0Dh
0x180028808  mov     [rsp+1F0h+var_190.dwFlags], ecx
0x18002880c  mov     r9, r13
0x18002880f  lea     r10, qword_18002EF80
0x180028816  mov     ebx, 80070057h
0x18002881b  mov     edx, r13d
0x18002881e  cmp     edx, 8
0x180028821  jnb     short loc_180028842
0x180028823  movsxd  r8, edx
0x180028826  mov     eax, esi
0x180028828  add     r8, r8
0x18002882b  and     eax, 0F0h
0x180028830  cmp     eax, [r10+r8*8]
0x180028834  jz      short loc_18002883A
0x180028836  inc     edx
0x180028838  jmp     short loc_18002881E
0x18002883a  mov     r9, [r10+r8*8+8]
0x18002883f  mov     ebx, r13d
0x180028842  test    sil, 0Fh
0x180028846  jnz     short loc_18002884F
0x180028848  or      ecx, 8
0x18002884b  mov     [rsp+1F0h+var_190.dwFlags], ecx
0x18002884f  test    ebx, ebx
0x180028851  js      loc_180028916
0x180028857  lea     rcx, [rsp+1F0h+ulCookie]; lpCookie
0x18002885c  mov     qword ptr [rbp+0F0h+var_190.24h], r9
0x180028860  mov     [rsp+1F0h+ulCookie], r13
0x180028865  call    CreateAndActivateContext
0x18002886a  mov     rsi, rax
0x18002886d  mov     rax, cs:qword_180034198
0x180028874  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028878  jnz     short loc_180028894
0x18002887a  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180028881  lea     rcx, qword_180034198
0x180028888  call    _GetProcFromComCtl32
0x18002888d  mov     rax, cs:qword_180034198
0x180028894  test    rax, rax
0x180028897  jz      short loc_1800288CE
0x180028899  xor     r9d, r9d
0x18002889c  lea     rdx, [rsp+1F0h+var_1B0]
0x1800288a1  xor     r8d, r8d
0x1800288a4  lea     rcx, [rsp+1F0h+var_190]
0x1800288a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288ae  mov     ebx, eax
0x1800288b0  test    eax, eax
0x1800288b2  js      short loc_1800288D3
0x1800288b4  test    byte ptr [rbp+0F0h+arg_20], 0Fh
0x1800288bb  jnz     short loc_1800288F5
0x1800288bd  cmp     [rsp+1F0h+var_1B0], 2
0x1800288c2  jnz     short loc_1800288F5
0x1800288c4  mov     [rsp+1F0h+var_1B0], 1
0x1800288cc  jmp     short loc_1800288F5
0x1800288ce  mov     ebx, 80004005h
0x1800288d3  mov     r9d, [rbp+0F0h+arg_20]
0x1800288da  mov     r8, r12; lpCaption
0x1800288dd  bts     r9d, 10h; uType
0x1800288e2  mov     rdx, rdi; lpText
0x1800288e5  mov     rcx, r15; hWnd
0x1800288e8  mov     r14b, 1
0x1800288eb  call    cs:__imp_MessageBoxW
0x1800288f1  mov     [rsp+1F0h+var_1B0], eax
0x1800288f5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800288f9  jz      short loc_180028916
0x1800288fb  mov     rdx, [rsp+1F0h+ulCookie]; ulCookie
0x180028900  test    rdx, rdx
0x180028903  jz      short loc_18002890D
0x180028905  xor     ecx, ecx; dwFlags
0x180028907  call    cs:__imp_DeactivateActCtx
0x18002890d  mov     rcx, rsi; hActCtx
0x180028910  call    cs:__imp_ReleaseActCtx
0x180028916  mov     rcx, rdi; hMem
0x180028919  call    cs:__imp_LocalFree
0x18002891f  test    ebx, ebx
0x180028921  jns     short loc_18002894C
0x180028923  test    r14b, r14b
0x180028926  jnz     short loc_180028934
0x180028928  jmp     short loc_18002892F
0x18002892a  mov     ebx, 8007000Eh
0x18002892f  mov     [rsp+1F0h+var_1B0], r13d
0x180028934  mov     eax, ebx
0x180028936  movzx   ecx, bx
0x180028939  and     eax, 1FFF0000h
0x18002893e  cmp     eax, 70000h
0x180028943  cmovnz  ecx, ebx; dwErrCode
0x180028946  call    cs:__imp_SetLastError
0x18002894c  mov     eax, [rsp+1F0h+var_1B0]
0x180028950  mov     rcx, [rbp+0F0h+var_50]
0x180028957  xor     rcx, rsp; StackCookie
0x18002895a  call    __security_check_cookie
0x18002895f  add     rsp, 1B8h
0x180028966  pop     r15
0x180028968  pop     r14
0x18002896a  pop     r13
0x18002896c  pop     r12
0x18002896e  pop     rdi
0x18002896f  pop     rsi
0x180028970  pop     rbx
0x180028971  pop     rbp
0x180028972  retn
```
