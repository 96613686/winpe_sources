# HrReturnContent(_EXTENSION_CONTROL_BLOCK *,IUPnPDynamicContentSource *,_GUID const &)

- ea: `0x180002f08`
- end: `0x1800034ce`
- name: `?HrReturnContent@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAUIUPnPDynamicContentSource@@AEBU_GUID@@@Z`
- size: `1478`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, struct IUPnPDynamicContentSource *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002af0`

## callees

- `0x180001400`
- `0x18000249c`
- `0x1800024c4`
- `0x180002884`
- `0x180002f08`
- `0x1800034d4`
- `0x180003728`
- `0x1800038ec`
- `0x180009c44`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800032c6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800032c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000339e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000339e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003183`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003183`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000342d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000342d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000301b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000301b`

## pseudocode

```c
__int64 __fastcall HrReturnContent(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        struct IUPnPDynamicContentSource *a2,
        const struct _GUID *a3)
{
  int v3; // r14d
  HCONN ConnID; // rcx
  BOOL (__stdcall *GetServerVariable)(HCONN, LPSTR, LPVOID, LPDWORD); // rax
  unsigned int v9; // ebx
  HCONN v10; // rcx
  BOOL (__stdcall *v11)(HCONN, LPSTR, LPVOID, LPDWORD); // rax
  int v12; // eax
  signed int Win32Error; // edi
  _QWORD *v15; // r10
  int v16; // esi
  unsigned int v17; // ebx
  _WORD *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r13d
  size_t v22; // rbx
  void *v23; // rax
  void *v24; // r15
  char *v25; // rsi
  __int64 v26; // rdx
  _WORD *v27; // rax
  __int64 v28; // r12
  signed int v29; // eax
  __int64 v30; // rax
  const char *v31; // rcx
  char *v32; // rax
  struct _EXTENSION_CONTROL_BLOCK *v33; // r12
  int v34; // eax
  DWORD LastError; // eax
  int i; // esi
  __int64 v37; // rbx
  _QWORD *v38; // rcx
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  int cbMultiByte[2]; // [rsp+68h] [rbp-98h] BYREF
  char *v43; // [rsp+70h] [rbp-90h] BYREF
  struct _EXTENSION_CONTROL_BLOCK *v44; // [rsp+78h] [rbp-88h]
  WCHAR WideCharStr[72]; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[80]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v47[1024]; // [rsp+160h] [rbp+60h] BYREF

  v3 = 0;
  v44 = a1;
  v39 = 0;
  ConnID = a1->ConnID;
  pv = 0;
  v41 = 0;
  GetServerVariable = a1->GetServerVariable;
  v43 = 0;
  cbMultiByte[0] = 1024;
  if ( ((unsigned int (__fastcall *)(HCONN, const char *, _BYTE *, int *))GetServerVariable)(
         ConnID,
         "HTTP_ACCEPTLANG",
         v47,
         cbMultiByte) != 1
    || (v9 = 1, !v47[0]) )
  {
    v9 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids, v9);
  v10 = a1->ConnID;
  v11 = a1->GetServerVariable;
  WideCharStr[0] = 0;
  cbMultiByte[0] = 65;
  if ( ((unsigned int (__fastcall *)(HCONN, const char *, CHAR *, int *))v11)(
         v10,
         "LOCAL_ADDR",
         MultiByteStr,
         cbMultiByte)
    && !MultiByteToWideChar(0, 0, MultiByteStr, cbMultiByte[0], WideCharStr, 65) )
  {
    WideCharStr[0] = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids, WideCharStr);
  v12 = (*(__int64 (__fastcall **)(struct IUPnPDynamicContentSource *, const struct _GUID *, WCHAR *, _QWORD, int *, LPVOID *, unsigned int *, char **))(*(_QWORD *)a2 + 24LL))(
          a2,
          a3,
          WideCharStr,
          v9,
          &v39,
          &pv,
          &v41,
          &v43);
  Win32Error = v12;
  if ( v12 >= 0 )
  {
    if ( !pv && v39 || !v43 && v41 )
      return 2147500037LL;
    v15 = WPP_GLOBAL_Control;
    v16 = 0;
    v17 = 0;
    do
    {
      if ( (int)v17 >= v39 )
        break;
      v18 = (_WORD *)*((_QWORD *)pv + (int)v17);
      if ( !v18 )
        goto LABEL_85;
      v19 = 0x7FFFFFFF;
      do
      {
        if ( !*v18 )
          break;
        ++v18;
        --v19;
      }
      while ( v19 );
      v20 = (0x7FFFFFFF - v19) & -(__int64)(v19 != 0);
      if ( v19 )
      {
        Win32Error = 0;
      }
      else
      {
LABEL_85:
        if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x400) != 0 )
        {
          WPP_SF_d(v15[2], 15, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids, v17);
          v15 = WPP_GLOBAL_Control;
        }
        Win32Error = -2147467259;
        LODWORD(v20) = 0;
      }
      ++v17;
      v16 += v20 + 2;
    }
    while ( Win32Error >= 0 );
    v21 = v16 + 2;
    v22 = (unsigned int)(v16 + 3);
    *(_QWORD *)cbMultiByte = v22;
    if ( Win32Error >= 0 )
    {
      v23 = malloc((unsigned int)v22);
      v24 = v23;
      if ( v23 )
      {
        v25 = (char *)v23;
        while ( v3 < v39 )
        {
          if ( *((_QWORD *)pv + v3) )
          {
            v26 = 0x7FFFFFFF;
            v27 = (_WORD *)*((_QWORD *)pv + v3);
            do
            {
              if ( !*v27 )
                break;
              ++v27;
              --v26;
            }
            while ( v26 );
            v28 = (0x7FFFFFFF - v26) & -(__int64)(v26 != 0);
            Win32Error = v26 == 0 ? 0x80070057 : 0;
            if ( v26 )
            {
              v29 = StringCchPrintfExA(
                      v25,
                      v22,
                      0,
                      (unsigned __int64 *)cbMultiByte,
                      0,
                      "%S\r\n",
                      *((const wchar_t **)pv + v3));
              v22 = *(_QWORD *)cbMultiByte;
              v25 += v28 + 2;
              Win32Error = v29;
            }
          }
          else
          {
            Win32Error = -2147024809;
          }
          ++v3;
          if ( Win32Error < 0 )
            goto LABEL_67;
        }
        if ( v22 )
        {
          if ( v22 > 0x7FFFFFFF )
          {
            *v25 = 0;
            Win32Error = -2147024809;
LABEL_67:
            free(v24);
            goto LABEL_71;
          }
          v30 = 2147483646;
          v31 = "\r\n";
          do
          {
            if ( !v30 )
              break;
            if ( !*v31 )
              break;
            *v25++ = *v31++;
            --v30;
            --v22;
          }
          while ( v22 );
          v32 = v25 - 1;
          if ( v22 )
            v32 = v25;
          Win32Error = v22 == 0 ? 0x8007007A : 0;
          *v32 = 0;
        }
        else
        {
          Win32Error = -2147024809;
        }
        if ( Win32Error >= 0 )
        {
          v33 = v44;
          if ( (unsigned int)_o__stricmp(v44->lpszMethod, "HEAD") )
            v34 = bSendResponseToClient(v33, "200 OK", v21, (const char *)v24, v41, v43);
          else
            v34 = bSendResponseToClient(v33, "200 OK", v21, (const char *)v24, 0, 0);
          if ( v34 )
          {
            v33->dwHttpStatusCode = 200;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids);
            }
          }
          else
          {
            Win32Error = HrFromLastWin32Error();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
                LastError);
            }
          }
        }
        goto LABEL_67;
      }
      Win32Error = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
          (unsigned int)"HrReturnContent(): Failed to allocate memory for headers",
          14);
    }
LABEL_71:
    for ( i = 0; i < v39; *((_QWORD *)pv + v37) = 0 )
    {
      v37 = i;
      CoTaskMemFree(*((LPVOID *)pv + i++));
    }
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v43);
    v43 = 0;
    if ( !Win32Error )
      return (unsigned int)Win32Error;
    goto LABEL_78;
  }
  v38 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_79;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
      (unsigned int)"HrReturnContent(): Failed to get content",
      v12);
LABEL_78:
    v38 = WPP_GLOBAL_Control;
LABEL_79:
    if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 )
      WPP_SF_sd(
        v38[2],
        20,
        (unsigned int)WPP_8a4b82c67137342c730f9db1111c400e_Traceguids,
        (unsigned int)"HrReturnContent(): Exiting",
        Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180002f08  mov     [rsp-8+arg_18], rbx
0x180002f0d  push    rbp
0x180002f0e  push    rsi
0x180002f0f  push    rdi
0x180002f10  push    r12
0x180002f12  push    r13
0x180002f14  push    r14
0x180002f16  push    r15
0x180002f18  lea     rbp, [rsp-470h]
0x180002f20  sub     rsp, 570h
0x180002f27  mov     rax, cs:__security_cookie
0x180002f2e  xor     rax, rsp
0x180002f31  mov     [rbp+4A0h+var_40], rax
0x180002f38  xor     r14d, r14d
0x180002f3b  mov     [rsp+5A0h+var_528], rcx
0x180002f40  mov     r12, rcx
0x180002f43  mov     [rsp+5A0h+var_550], r14d
0x180002f48  mov     rcx, [rcx+8]
0x180002f4c  lea     r9, [rsp+5A0h+cbMultiByte]
0x180002f51  mov     rsi, r8
0x180002f54  mov     [rsp+5A0h+pv], r14
0x180002f59  mov     rdi, rdx
0x180002f5c  mov     [rsp+5A0h+var_540], r14d
0x180002f61  mov     rax, [r12+0A0h]
0x180002f69  lea     r8, [rbp+4A0h+var_440]
0x180002f6d  mov     r13d, 400h
0x180002f73  mov     [rsp+5A0h+var_530], r14
0x180002f78  lea     rdx, aHttpAcceptlang; "HTTP_ACCEPTLANG"
0x180002f7f  mov     [rsp+5A0h+cbMultiByte], r13d
0x180002f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f89  cmp     eax, 1
0x180002f8c  jnz     short loc_180002F96
0x180002f8e  mov     ebx, eax
0x180002f90  cmp     [rbp+4A0h+var_440], r14b
0x180002f94  jnz     short loc_180002F99
0x180002f96  mov     ebx, r14d
0x180002f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fa0  lea     r15, WPP_GLOBAL_Control
0x180002fa7  cmp     rcx, r15
0x180002faa  jz      short loc_180002FCA
0x180002fac  test    [rcx+1Ch], r13d
0x180002fb0  jz      short loc_180002FCA
0x180002fb2  mov     rcx, [rcx+10h]
0x180002fb6  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180002fbd  mov     edx, 0Dh
0x180002fc2  mov     r9d, ebx
0x180002fc5  call    WPP_SF_d
0x180002fca  mov     rcx, [r12+8]
0x180002fcf  lea     r9, [rsp+5A0h+cbMultiByte]
0x180002fd4  mov     rax, [r12+0A0h]
0x180002fdc  lea     r8, [rbp+4A0h+MultiByteStr]
0x180002fe0  mov     r13d, 41h ; 'A'
0x180002fe6  mov     [rbp+4A0h+WideCharStr], r14w
0x180002feb  lea     rdx, aLocalAddr; "LOCAL_ADDR"
0x180002ff2  mov     [rsp+5A0h+cbMultiByte], r13d
0x180002ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffc  test    eax, eax
0x180002ffe  jz      short loc_18000302A
0x180003000  mov     r9d, [rsp+5A0h+cbMultiByte]; cbMultiByte
0x180003005  lea     rax, [rbp+4A0h+WideCharStr]
0x180003009  mov     [rsp+5A0h+cchWideChar], r13d; cchWideChar
0x18000300e  lea     r8, [rbp+4A0h+MultiByteStr]; lpMultiByteStr
0x180003012  xor     edx, edx; dwFlags
0x180003014  mov     [rsp+5A0h+lpWideCharStr], rax; lpWideCharStr
0x180003019  xor     ecx, ecx; CodePage
0x18000301b  call    cs:__imp_MultiByteToWideChar
0x180003021  test    eax, eax
0x180003023  jnz     short loc_18000302A
0x180003025  mov     [rbp+4A0h+WideCharStr], r14w
0x18000302a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003031  cmp     rcx, r15
0x180003034  jz      short loc_180003058
0x180003036  test    dword ptr [rcx+1Ch], 400h
0x18000303d  jz      short loc_180003058
0x18000303f  mov     rcx, [rcx+10h]
0x180003043  lea     r9, [rbp+4A0h+WideCharStr]
0x180003047  mov     edx, 0Eh
0x18000304c  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180003053  call    WPP_SF_S
0x180003058  mov     rax, [rdi]
0x18000305b  lea     rcx, [rsp+5A0h+var_530]
0x180003060  mov     [rsp+5A0h+var_568], rcx
0x180003065  lea     r8, [rbp+4A0h+WideCharStr]
0x180003069  lea     rcx, [rsp+5A0h+var_540]
0x18000306e  mov     r9d, ebx
0x180003071  mov     [rsp+5A0h+var_570], rcx
0x180003076  mov     rdx, rsi
0x180003079  mov     rax, [rax+18h]
0x18000307d  lea     rcx, [rsp+5A0h+pv]
0x180003082  mov     qword ptr [rsp+5A0h+cchWideChar], rcx
0x180003087  lea     rcx, [rsp+5A0h+var_550]
0x18000308c  mov     [rsp+5A0h+lpWideCharStr], rcx
0x180003091  mov     rcx, rdi
0x180003094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003099  mov     edi, eax
0x18000309b  test    eax, eax
0x18000309d  js      loc_18000343E
0x1800030a3  cmp     [rsp+5A0h+pv], r14
0x1800030a8  jnz     short loc_1800030B1
0x1800030aa  cmp     [rsp+5A0h+var_550], r14d
0x1800030af  jnz     short loc_1800030BF
0x1800030b1  cmp     [rsp+5A0h+var_530], r14
0x1800030b6  jnz     short loc_1800030C9
0x1800030b8  cmp     [rsp+5A0h+var_540], r14d
0x1800030bd  jz      short loc_1800030C9
0x1800030bf  mov     eax, 80004005h
0x1800030c4  jmp     loc_1800034A4
0x1800030c9  mov     r10, cs:WPP_GLOBAL_Control
0x1800030d0  mov     esi, r14d
0x1800030d3  mov     ebx, r14d
0x1800030d6  mov     r12d, 7FFFFFFFh
0x1800030dc  cmp     ebx, [rsp+5A0h+var_550]
0x1800030e0  jge     loc_18000316C
0x1800030e6  mov     rax, [rsp+5A0h+pv]
0x1800030eb  movsxd  rcx, ebx
0x1800030ee  mov     r8, [rax+rcx*8]
0x1800030f2  test    r8, r8
0x1800030f5  jz      short loc_180003126
0x1800030f7  mov     rdx, r12
0x1800030fa  cmp     [r8], r14w
0x1800030fe  jz      short loc_18000310A
0x180003100  add     r8, 2
0x180003104  sub     rdx, 1
0x180003108  jnz     short loc_1800030FA
0x18000310a  mov     rcx, r12
0x18000310d  mov     rax, rdx
0x180003110  sub     rcx, rdx
0x180003113  neg     rax
0x180003116  sbb     r8, r8
0x180003119  and     r8, rcx
0x18000311c  test    rdx, rdx
0x18000311f  jz      short loc_180003126
0x180003121  mov     edi, r14d
0x180003124  jmp     short loc_18000315C
0x180003126  cmp     r10, r15
0x180003129  jz      short loc_180003154
0x18000312b  test    dword ptr [r10+1Ch], 400h
0x180003133  jz      short loc_180003154
0x180003135  mov     rcx, [r10+10h]
0x180003139  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x180003140  mov     edx, 0Fh
0x180003145  mov     r9d, ebx
0x180003148  call    WPP_SF_d
0x18000314d  mov     r10, cs:WPP_GLOBAL_Control
0x180003154  mov     edi, 80004005h
0x180003159  mov     r8, r14
0x18000315c  add     esi, 2
0x18000315f  inc     ebx
0x180003161  add     esi, r8d
0x180003164  test    edi, edi
0x180003166  jns     loc_1800030DC
0x18000316c  lea     r13d, [rsi+2]
0x180003170  lea     ebx, [r13+1]
0x180003174  mov     qword ptr [rsp+5A0h+cbMultiByte], rbx
0x180003179  test    edi, edi
0x18000317b  js      loc_1800033EB
0x180003181  mov     ecx, ebx; Size
0x180003183  call    cs:__imp_malloc
0x180003189  mov     r15, rax
0x18000318c  test    rax, rax
0x18000318f  jz      loc_1800033AD
0x180003195  mov     rsi, rax
0x180003198  mov     r10d, 80070057h
0x18000319e  xor     r9d, r9d
0x1800031a1  cmp     r14d, [rsp+5A0h+var_550]
0x1800031a6  jge     loc_180003255
0x1800031ac  mov     rax, [rsp+5A0h+pv]
0x1800031b1  movsxd  rcx, r14d
0x1800031b4  mov     r8, [rax+rcx*8]
0x1800031b8  test    r8, r8
0x1800031bb  jz      short loc_180003239
0x1800031bd  mov     rdx, r12
0x1800031c0  mov     rax, r8
0x1800031c3  cmp     [rax], r9w
0x1800031c7  jz      short loc_1800031D3
0x1800031c9  add     rax, 2
0x1800031cd  sub     rdx, 1
0x1800031d1  jnz     short loc_1800031C3
0x1800031d3  mov     rcx, r12
0x1800031d6  mov     rax, rdx
0x1800031d9  sub     rcx, rdx
0x1800031dc  neg     rax
0x1800031df  mov     rax, rdx
0x1800031e2  sbb     r12, r12
0x1800031e5  and     r12, rcx
0x1800031e8  neg     rax
0x1800031eb  sbb     edi, edi
0x1800031ed  not     edi
0x1800031ef  and     edi, r10d
0x1800031f2  test    rdx, rdx
0x1800031f5  jz      short loc_18000323C
0x1800031f7  mov     [rsp+5A0h+var_570], r8
0x1800031fc  lea     rax, aS; "%S\r\n"
0x180003203  mov     qword ptr [rsp+5A0h+cchWideChar], rax; char *
0x180003208  xor     r8d, r8d; char **
0x18000320b  mov     [rsp+5A0h+lpWideCharStr], r9; DWORD
0x180003210  mov     rdx, rbx; cbDest
0x180003213  lea     r9, [rsp+5A0h+cbMultiByte]; unsigned __int64 *
0x180003218  mov     rcx, rsi; Buffer
0x18000321b  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180003220  mov     rbx, qword ptr [rsp+5A0h+cbMultiByte]
0x180003225  add     rsi, 2
0x180003229  add     rsi, r12
0x18000322c  mov     edi, eax
0x18000322e  xor     r9d, r9d
0x180003231  mov     r10d, 80070057h
0x180003237  jmp     short loc_18000323C
0x180003239  mov     edi, r10d
0x18000323c  inc     r14d
0x18000323f  mov     r12d, 7FFFFFFFh
0x180003245  test    edi, edi
0x180003247  jns     loc_1800031A1
0x18000324d  xor     r14d, r14d
0x180003250  jmp     loc_18000339B
0x180003255  xor     r14d, r14d
0x180003258  test    rbx, rbx
0x18000325b  jz      loc_1800032EC
0x180003261  cmp     rbx, r12
0x180003264  ja      loc_1800032F4
0x18000326a  mov     eax, 7FFFFFFEh
0x18000326f  lea     rcx, asc_18000D924; "\r\n"
0x180003276  test    rax, rax
0x180003279  jz      short loc_180003292
0x18000327b  mov     dl, [rcx]
0x18000327d  test    dl, dl
0x18000327f  jz      short loc_180003292
0x180003281  mov     [rsi], dl
0x180003283  inc     rcx
0x180003286  inc     rsi
0x180003289  dec     rax
0x18000328c  sub     rbx, 1
0x180003290  jnz     short loc_180003276
0x180003292  test    rbx, rbx
0x180003295  lea     rax, [rsi-1]
0x180003299  cmovnz  rax, rsi
0x18000329d  neg     rbx
0x1800032a0  sbb     edi, edi
0x1800032a2  not     edi
0x1800032a4  and     edi, 8007007Ah
0x1800032aa  mov     [rax], r14b
0x1800032ad  test    edi, edi
0x1800032af  js      loc_18000339B
0x1800032b5  mov     r12, [rsp+5A0h+var_528]
0x1800032ba  lea     rdx, aHead; "HEAD"
0x1800032c1  mov     rcx, [r12+68h]
0x1800032c6  call    cs:__imp__o__stricmp
0x1800032cc  mov     r9, r15; char *
0x1800032cf  lea     rdx, a200Ok; "200 OK"
0x1800032d6  mov     r8d, r13d; unsigned int
0x1800032d9  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x1800032dc  test    eax, eax
0x1800032de  jnz     short loc_1800032FF
0x1800032e0  mov     qword ptr [rsp+5A0h+cchWideChar], r14
0x1800032e5  mov     dword ptr [rsp+5A0h+lpWideCharStr], r14d
0x1800032ea  jmp     short loc_180003311
0x1800032ec  mov     edi, r10d
0x1800032ef  test    rbx, rbx
0x1800032f2  jz      short loc_1800032AD
0x1800032f4  mov     [rsi], r14b
0x1800032f7  mov     edi, r10d
0x1800032fa  jmp     loc_18000339B
0x1800032ff  mov     rax, [rsp+5A0h+var_530]
0x180003304  mov     qword ptr [rsp+5A0h+cchWideChar], rax; char *
0x180003309  mov     eax, [rsp+5A0h+var_540]
0x18000330d  mov     dword ptr [rsp+5A0h+lpWideCharStr], eax; unsigned int
0x180003311  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180003316  test    eax, eax
0x180003318  jz      short loc_180003356
0x18000331a  mov     dword ptr [r12+10h], 0C8h
0x180003323  mov     rcx, cs:WPP_GLOBAL_Control
0x18000332a  lea     rdx, WPP_GLOBAL_Control
0x180003331  cmp     rcx, rdx
0x180003334  jz      short loc_18000339B
0x180003336  test    dword ptr [rcx+1Ch], 400h
0x18000333d  jz      short loc_18000339B
0x18000333f  mov     rcx, [rcx+10h]
0x180003343  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x18000334a  mov     edx, 10h
0x18000334f  call    WPP_SF_
0x180003354  jmp     short loc_18000339B
0x180003356  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000335b  mov     edi, eax
0x18000335d  mov     rax, cs:WPP_GLOBAL_Control
0x180003364  lea     rdx, WPP_GLOBAL_Control
0x18000336b  cmp     rax, rdx
0x18000336e  jz      short loc_18000339B
0x180003370  test    byte ptr [rax+1Ch], 1
0x180003374  jz      short loc_18000339B
0x180003376  call    cs:__imp_GetLastError
0x18000337c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003383  lea     r8, WPP_8a4b82c67137342c730f9db1111c400e_Traceguids
0x18000338a  mov     edx, 11h
0x18000338f  mov     r9d, eax
0x180003392  mov     rcx, [rcx+10h]
0x180003396  call    WPP_SF_d
0x18000339b  mov     rcx, r15; Block
0x18000339e  call    cs:__imp_free
0x1800033a4  lea     r15, WPP_GLOBAL_Control
0x1800033ab  jmp     short loc_1800033EB
0x1800033ad  mov     edi, 8007000Eh
  ... truncated ...
```
