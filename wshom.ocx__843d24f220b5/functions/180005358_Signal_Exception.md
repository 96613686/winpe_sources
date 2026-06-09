# Signal_Exception

- ea: `0x180005358`
- end: `0x180005645`
- name: `Signal_Exception`
- size: `749`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005d20`
- `0x180009c04`

## callees

- `0x180005358`
- `0x180009a68`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000562e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000562e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800055ce`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800055ce`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800053a0`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800053a0`
- `KERNEL32!GetLastError` at `0x18000542c`
- `KERNEL32!GetLastError` at `0x18000542c`
- `KERNEL32!MultiByteToWideChar` at `0x1800054d9`
- `KERNEL32!MultiByteToWideChar` at `0x180005519`
- `KERNEL32!MultiByteToWideChar` at `0x1800054d9`
- `KERNEL32!MultiByteToWideChar` at `0x180005519`
- `KERNEL32!LocalAlloc` at `0x1800054f2`
- `KERNEL32!LocalAlloc` at `0x1800054f2`
- `KERNEL32!FormatMessageW` at `0x18000541e`
- `KERNEL32!FormatMessageW` at `0x18000541e`
- `KERNEL32!LocalFree` at `0x180005616`
- `KERNEL32!LocalFree` at `0x180005625`
- `KERNEL32!LocalFree` at `0x180005616`
- `KERNEL32!LocalFree` at `0x180005625`
- `KERNEL32!FormatMessageA` at `0x1800054ac`
- `KERNEL32!FormatMessageA` at `0x1800054ac`

## pseudocode

```c
__int64 __fastcall Signal_Exception(__int64 a1, __int64 a2, signed int a3, unsigned int a4, va_list *Arguments)
{
  unsigned __int16 *v6; // rsi
  int v10; // ebx
  DWORD v11; // eax
  signed int LastError; // eax
  DWORD v13; // eax
  int v14; // eax
  int v15; // ebx
  WCHAR *v16; // rax
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-28h] BYREF
  WCHAR Buffer[4]; // [rsp+50h] [rbp-20h] BYREF
  CHAR lpBuffer[8]; // [rsp+58h] [rbp-18h] BYREF
  IErrorInfo *perrinfo; // [rsp+60h] [rbp-10h] BYREF

  pperrinfo = 0;
  v6 = 0;
  perrinfo = 0;
  v19 = 0;
  *(_QWORD *)Buffer = 0;
  *(_QWORD *)lpBuffer = 0;
  v10 = CreateErrorInfo(&pperrinfo);
  if ( v10 < 0 )
    goto LABEL_28;
  v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a1);
  if ( v10 < 0 )
    goto LABEL_28;
  v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetSource)(pperrinfo, a2);
  if ( v10 < 0 )
    goto LABEL_28;
  if ( Global::g_fWindowsNT )
  {
    if ( a3 < 0 )
    {
      v11 = FormatMessageW(0x1100u, 0, a3, 0, Buffer, 0, Arguments);
      goto LABEL_7;
    }
    v10 = LoadBstr(a4, &v19);
    if ( v10 >= 0 )
    {
      v6 = v19;
      v11 = FormatMessageW(0x500u, v19, 0, 0, Buffer, 0, Arguments);
      goto LABEL_7;
    }
LABEL_27:
    v6 = v19;
    goto LABEL_28;
  }
  if ( a3 >= 0 )
  {
    v10 = LoadBstr(a4, &v19);
    if ( v10 < 0 )
      goto LABEL_27;
    v6 = v19;
    v13 = FormatMessageA(0x500u, v19, 0, 0, lpBuffer, 0, Arguments);
  }
  else
  {
    v13 = FormatMessageA(0x1100u, 0, a3, 0, lpBuffer, 0, Arguments);
  }
  if ( !v13
    || (v14 = MultiByteToWideChar(0, 0, *(LPCCH *)lpBuffer, -1, 0, 0), (v15 = v14) == 0)
    || (v16 = (WCHAR *)LocalAlloc(0, 2LL * v14), (*(_QWORD *)Buffer = v16) == 0) )
  {
LABEL_8:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_28;
  }
  v11 = MultiByteToWideChar(0, 0, *(LPCCH *)lpBuffer, -1, v16, v15);
LABEL_7:
  if ( !v11 )
    goto LABEL_8;
  v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetDescription)(
          pperrinfo,
          *(_QWORD *)Buffer);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, 0);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, 0);
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                pperrinfo,
                &IID_IErrorInfo,
                &perrinfo);
        if ( v10 >= 0 )
        {
          v10 = SetErrorInfo(0, perrinfo);
          if ( v10 >= 0 )
            v10 = 0;
        }
      }
    }
  }
LABEL_28:
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  if ( *(_QWORD *)lpBuffer )
    LocalFree(*(HLOCAL *)lpBuffer);
  SysFreeString(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005358  push    rbp
0x18000535a  push    rbx
0x18000535b  push    rsi
0x18000535c  push    rdi
0x18000535d  push    r12
0x18000535f  push    r14
0x180005361  push    r15
0x180005363  mov     rbp, rsp
0x180005366  sub     rsp, 70h
0x18000536a  mov     r15, rcx
0x18000536d  mov     [rbp+pperrinfo], 0
0x180005375  xor     esi, esi
0x180005377  mov     [rbp+perrinfo], 0
0x18000537f  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x180005383  mov     [rbp+var_28], rsi
0x180005387  mov     r14d, r9d
0x18000538a  mov     qword ptr [rbp+Buffer], 0
0x180005392  mov     edi, r8d
0x180005395  mov     qword ptr [rbp+var_18], 0
0x18000539d  mov     r12, rdx
0x1800053a0  call    cs:__imp_CreateErrorInfo
0x1800053a6  mov     ebx, eax
0x1800053a8  test    eax, eax
0x1800053aa  js      loc_1800055E3
0x1800053b0  mov     rcx, [rbp+pperrinfo]
0x1800053b4  mov     rdx, r15
0x1800053b7  mov     rax, [rcx]
0x1800053ba  mov     rax, [rax+18h]
0x1800053be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c3  mov     ebx, eax
0x1800053c5  test    eax, eax
0x1800053c7  js      loc_1800055E3
0x1800053cd  mov     rcx, [rbp+pperrinfo]
0x1800053d1  mov     rdx, r12
0x1800053d4  mov     rax, [rcx]
0x1800053d7  mov     rax, [rax+20h]
0x1800053db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e0  mov     ebx, eax
0x1800053e2  test    eax, eax
0x1800053e4  js      loc_1800055E3
0x1800053ea  cmp     cs:?g_fWindowsNT@Global@@2_NA, sil; bool Global::g_fWindowsNT
0x1800053f1  jz      loc_180005481
0x1800053f7  test    edi, edi
0x1800053f9  jns     short loc_18000544A
0x1800053fb  mov     rax, [rbp+arg_20]
0x1800053ff  xor     r9d, r9d; dwLanguageId
0x180005402  mov     [rsp+70h+Arguments], rax; Arguments
0x180005407  mov     r8d, edi; dwMessageId
0x18000540a  mov     [rsp+70h+nSize], esi; nSize
0x18000540e  xor     edx, edx; lpSource
0x180005410  mov     ecx, 1100h; dwFlags
0x180005415  lea     rax, [rbp+Buffer]
0x180005419  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x18000541e  call    cs:__imp_FormatMessageW
0x180005424  test    eax, eax
0x180005426  jnz     loc_18000555E
0x18000542c  call    cs:__imp_GetLastError
0x180005432  mov     ebx, eax
0x180005434  test    eax, eax
0x180005436  jle     loc_1800055E3
0x18000543c  movzx   ebx, ax
0x18000543f  or      ebx, 80070000h
0x180005445  jmp     loc_1800055E3
0x18000544a  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000544e  mov     ecx, r14d; unsigned int
0x180005451  call    ?LoadBstr@@YAJIPEAPEAG@Z; LoadBstr(uint,ushort * *)
0x180005456  mov     ebx, eax
0x180005458  test    eax, eax
0x18000545a  js      loc_1800055DF
0x180005460  mov     rax, [rbp+arg_20]
0x180005464  xor     r9d, r9d
0x180005467  mov     [rsp+70h+Arguments], rax
0x18000546c  xor     r8d, r8d
0x18000546f  mov     [rsp+70h+nSize], esi
0x180005473  mov     ecx, 500h
0x180005478  mov     rsi, [rbp+var_28]
0x18000547c  mov     rdx, rsi
0x18000547f  jmp     short loc_180005415
0x180005481  test    edi, edi
0x180005483  jns     loc_180005524
0x180005489  mov     rax, [rbp+arg_20]
0x18000548d  xor     r9d, r9d; dwLanguageId
0x180005490  mov     [rsp+70h+Arguments], rax; Arguments
0x180005495  mov     r8d, edi; dwMessageId
0x180005498  mov     [rsp+70h+nSize], esi; nSize
0x18000549c  xor     edx, edx; lpSource
0x18000549e  mov     ecx, 1100h; dwFlags
0x1800054a3  lea     rax, [rbp+var_18]
0x1800054a7  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x1800054ac  call    cs:__imp_FormatMessageA
0x1800054b2  test    eax, eax
0x1800054b4  jz      loc_18000542C
0x1800054ba  mov     r8, qword ptr [rbp+var_18]; lpMultiByteStr
0x1800054be  or      edi, 0FFFFFFFFh
0x1800054c1  mov     r9d, edi; cbMultiByte
0x1800054c4  mov     [rsp+70h+nSize], 0; cchWideChar
0x1800054cc  xor     edx, edx; dwFlags
0x1800054ce  mov     [rsp+70h+lpBuffer], 0; lpWideCharStr
0x1800054d7  xor     ecx, ecx; CodePage
0x1800054d9  call    cs:__imp_MultiByteToWideChar
0x1800054df  movsxd  rbx, eax
0x1800054e2  test    eax, eax
0x1800054e4  jz      loc_18000542C
0x1800054ea  mov     rdx, rbx
0x1800054ed  xor     ecx, ecx; uFlags
0x1800054ef  add     rdx, rdx; uBytes
0x1800054f2  call    cs:__imp_LocalAlloc
0x1800054f8  mov     qword ptr [rbp+Buffer], rax
0x1800054fc  test    rax, rax
0x1800054ff  jz      loc_18000542C
0x180005505  mov     r8, qword ptr [rbp+var_18]; lpMultiByteStr
0x180005509  mov     r9d, edi; cbMultiByte
0x18000550c  mov     [rsp+70h+nSize], ebx; cchWideChar
0x180005510  xor     edx, edx; dwFlags
0x180005512  xor     ecx, ecx; CodePage
0x180005514  mov     [rsp+70h+lpBuffer], rax; lpWideCharStr
0x180005519  call    cs:__imp_MultiByteToWideChar
0x18000551f  jmp     loc_180005424
0x180005524  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x180005528  mov     ecx, r14d; unsigned int
0x18000552b  call    ?LoadBstr@@YAJIPEAPEAG@Z; LoadBstr(uint,ushort * *)
0x180005530  mov     ebx, eax
0x180005532  test    eax, eax
0x180005534  js      loc_1800055DF
0x18000553a  mov     rax, [rbp+arg_20]
0x18000553e  xor     r9d, r9d
0x180005541  mov     [rsp+70h+Arguments], rax
0x180005546  xor     r8d, r8d
0x180005549  mov     [rsp+70h+nSize], esi
0x18000554d  mov     ecx, 500h
0x180005552  mov     rsi, [rbp+var_28]
0x180005556  mov     rdx, rsi
0x180005559  jmp     loc_1800054A3
0x18000555e  mov     rcx, [rbp+pperrinfo]
0x180005562  mov     rdx, qword ptr [rbp+Buffer]
0x180005566  mov     rax, [rcx]
0x180005569  mov     rax, [rax+28h]
0x18000556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005572  mov     ebx, eax
0x180005574  test    eax, eax
0x180005576  js      short loc_1800055E3
0x180005578  mov     rcx, [rbp+pperrinfo]
0x18000557c  xor     edx, edx
0x18000557e  mov     rax, [rcx]
0x180005581  mov     rax, [rax+30h]
0x180005585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558a  mov     ebx, eax
0x18000558c  test    eax, eax
0x18000558e  js      short loc_1800055E3
0x180005590  mov     rcx, [rbp+pperrinfo]
0x180005594  xor     edx, edx
0x180005596  mov     rax, [rcx]
0x180005599  mov     rax, [rax+38h]
0x18000559d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a2  mov     ebx, eax
0x1800055a4  test    eax, eax
0x1800055a6  js      short loc_1800055E3
0x1800055a8  mov     rcx, [rbp+pperrinfo]
0x1800055ac  lea     r8, [rbp+perrinfo]
0x1800055b0  lea     rdx, IID_IErrorInfo
0x1800055b7  mov     rax, [rcx]
0x1800055ba  mov     rax, [rax]
0x1800055bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c2  mov     ebx, eax
0x1800055c4  test    eax, eax
0x1800055c6  js      short loc_1800055E3
0x1800055c8  mov     rdx, [rbp+perrinfo]; perrinfo
0x1800055cc  xor     ecx, ecx; dwReserved
0x1800055ce  call    cs:__imp_SetErrorInfo
0x1800055d4  mov     ebx, eax
0x1800055d6  xor     eax, eax
0x1800055d8  test    ebx, ebx
0x1800055da  cmovns  ebx, eax
0x1800055dd  jmp     short loc_1800055E3
0x1800055df  mov     rsi, [rbp+var_28]
0x1800055e3  mov     rcx, [rbp+pperrinfo]
0x1800055e7  test    rcx, rcx
0x1800055ea  jz      short loc_1800055F8
0x1800055ec  mov     rax, [rcx]
0x1800055ef  mov     rax, [rax+10h]
0x1800055f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f8  mov     rcx, [rbp+perrinfo]
0x1800055fc  test    rcx, rcx
0x1800055ff  jz      short loc_18000560D
0x180005601  mov     rax, [rcx]
0x180005604  mov     rax, [rax+10h]
0x180005608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000560d  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180005611  test    rcx, rcx
0x180005614  jz      short loc_18000561C
0x180005616  call    cs:__imp_LocalFree
0x18000561c  mov     rcx, qword ptr [rbp+var_18]; hMem
0x180005620  test    rcx, rcx
0x180005623  jz      short loc_18000562B
0x180005625  call    cs:__imp_LocalFree
0x18000562b  mov     rcx, rsi; bstrString
0x18000562e  call    cs:__imp_SysFreeString
0x180005634  mov     eax, ebx
0x180005636  add     rsp, 70h
0x18000563a  pop     r15
0x18000563c  pop     r14
0x18000563e  pop     r12
0x180005640  pop     rdi
0x180005641  pop     rsi
0x180005642  pop     rbx
0x180005643  pop     rbp
0x180005644  retn
```
