# ApplySettings::CleanConfig(void)

- ea: `0x1800430f8`
- end: `0x1800435ef`
- name: `?CleanConfig@ApplySettings@@AEAAJXZ`
- size: `1271`
- prototype: `__int64 __fastcall(ApplySettings *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x180042a80`
- `0x1800430f8`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004312c`
- `KERNEL32!GetLastError` at `0x1800431b5`
- `KERNEL32!GetLastError` at `0x180043262`
- `KERNEL32!GetLastError` at `0x1800432eb`
- `KERNEL32!GetLastError` at `0x180043398`
- `KERNEL32!GetLastError` at `0x180043421`
- `KERNEL32!GetLastError` at `0x1800434ce`
- `KERNEL32!GetLastError` at `0x180043554`
- `KERNEL32!GetLastError` at `0x18004312c`
- `KERNEL32!GetLastError` at `0x1800431b5`
- `KERNEL32!GetLastError` at `0x180043262`
- `KERNEL32!GetLastError` at `0x1800432eb`
- `KERNEL32!GetLastError` at `0x180043398`
- `KERNEL32!GetLastError` at `0x180043421`
- `KERNEL32!GetLastError` at `0x1800434ce`
- `KERNEL32!GetLastError` at `0x180043554`

## string_xrefs

- `0x180043189`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180043212`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800432bf`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180043348`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800433f5`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004347e`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004352b`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x1800435a5`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180043175`: `g_pService->get_Clients`
- `0x1800432ab`: `g_pService->get_RAPolicies`
- `0x1800433e1`: `g_pService->get_CRPolicies`
- `0x180043517`: `g_pService->get_RemoteServers`

## pseudocode

```c
__int64 __fastcall ApplySettings::CleanConfig(ApplySettings *this)
{
  unsigned int v2; // edi
  signed int LastError; // eax
  char v4; // bl
  const char *v5; // rsi
  int v6; // r8d
  int v7; // r9d
  int v8; // edx
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  __int64 v17; // [rsp+60h] [rbp+28h] BYREF

  v17 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 208LL))(*((_QWORD *)this + 1), &v17);
  if ( v2 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = LastError;
    }
    else
    {
      v4 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v5 = "g_pService->get_Clients";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v8 = 15;
LABEL_79:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v6, v7, (__int64)v5, v4);
    }
  }
  else
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
    if ( v2 )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v4 = v9;
      }
      else
      {
        v4 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v5 = "pColl->Clear";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v8 = 16;
        goto LABEL_79;
      }
    }
    else
    {
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 224LL))(*((_QWORD *)this + 1), &v17);
      if ( v2 )
      {
        v10 = GetLastError();
        v4 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            v4 = v10;
        }
        else
        {
          v4 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v5 = "g_pService->get_RAPolicies";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v8 = 17;
          goto LABEL_79;
        }
      }
      else
      {
        v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
        if ( v2 )
        {
          v11 = GetLastError();
          v4 = v11;
          if ( v11 )
          {
            if ( v11 > 0 )
              v4 = v11;
          }
          else
          {
            v4 = 5;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v5 = "pColl->Clear";
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
            v8 = 18;
            goto LABEL_79;
          }
        }
        else
        {
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v17 = 0;
          }
          v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 232LL))(
                 *((_QWORD *)this + 1),
                 &v17);
          if ( v2 )
          {
            v12 = GetLastError();
            v4 = v12;
            if ( v12 )
            {
              if ( v12 > 0 )
                v4 = v12;
            }
            else
            {
              v4 = 5;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v5 = "g_pService->get_CRPolicies";
              WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
              v8 = 19;
              goto LABEL_79;
            }
          }
          else
          {
            v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
            if ( v2 )
            {
              v13 = GetLastError();
              v4 = v13;
              if ( v13 )
              {
                if ( v13 > 0 )
                  v4 = v13;
              }
              else
              {
                v4 = 5;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v5 = "pColl->Clear";
                WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returne"
                            "d hr = %!HRESULT!");
                v8 = 20;
                goto LABEL_79;
              }
            }
            else
            {
              if ( v17 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v17 = 0;
              }
              v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 216LL))(
                     *((_QWORD *)this + 1),
                     &v17);
              if ( v2 )
              {
                v14 = GetLastError();
                v4 = v14;
                if ( v14 )
                {
                  if ( v14 > 0 )
                    v4 = v14;
                }
                else
                {
                  v4 = 5;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v5 = "g_pService->get_RemoteServers";
                  WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s retur"
                              "ned hr = %!HRESULT!");
                  v8 = 21;
                  goto LABEL_79;
                }
              }
              else
              {
                v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
                if ( v2 )
                {
                  v15 = GetLastError();
                  v4 = v15;
                  if ( v15 )
                  {
                    if ( v15 > 0 )
                      v4 = v15;
                  }
                  else
                  {
                    v4 = 5;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v5 = "pColl->Clear";
                    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s ret"
                                "urned hr = %!HRESULT!");
                    v8 = 22;
                    goto LABEL_79;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return v2;
}

```

## disassembly

```asm
0x1800430f8  push    rbp
0x1800430fa  push    rbx
0x1800430fb  push    rsi
0x1800430fc  push    rdi
0x1800430fd  mov     rbp, rsp
0x180043100  sub     rsp, 38h
0x180043104  mov     rbx, rcx
0x180043107  mov     [rbp+arg_0], 0
0x18004310f  mov     rcx, [rcx+8]
0x180043113  lea     rdx, [rbp+arg_0]
0x180043117  mov     rax, [rcx]
0x18004311a  mov     rax, [rax+0D0h]
0x180043121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043126  mov     edi, eax
0x180043128  test    eax, eax
0x18004312a  jz      short loc_18004319F
0x18004312c  call    cs:__imp_GetLastError
0x180043132  mov     ebx, eax
0x180043134  test    eax, eax
0x180043136  jz      short loc_180043145
0x180043138  jle     short loc_18004314A
0x18004313a  movzx   ebx, ax
0x18004313d  or      ebx, 80070000h
0x180043143  jmp     short loc_18004314A
0x180043145  mov     ebx, 80004005h
0x18004314a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043151  lea     rax, WPP_GLOBAL_Control
0x180043158  cmp     rcx, rax
0x18004315b  jz      loc_1800435CF
0x180043161  cmp     byte ptr [rcx+19h], 2
0x180043165  jb      loc_1800435CF
0x18004316b  test    byte ptr [rcx+1Ch], 10h
0x18004316f  jz      loc_1800435CF
0x180043175  lea     rsi, aGPserviceGetCl; "g_pService->get_Clients"
0x18004317c  mov     r9d, ebx
0x18004317f  mov     r8, rsi
0x180043182  lea     rdx, aNpsds; "NPSDS"
0x180043189  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180043190  call    WppDbgPrint
0x180043195  mov     edx, 0Fh
0x18004319a  jmp     loc_1800435B6
0x18004319f  mov     rcx, [rbp+arg_0]
0x1800431a3  mov     rax, [rcx]
0x1800431a6  mov     rax, [rax+40h]
0x1800431aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431af  mov     edi, eax
0x1800431b1  test    eax, eax
0x1800431b3  jz      short loc_180043228
0x1800431b5  call    cs:__imp_GetLastError
0x1800431bb  mov     ebx, eax
0x1800431bd  test    eax, eax
0x1800431bf  jz      short loc_1800431CE
0x1800431c1  jle     short loc_1800431D3
0x1800431c3  movzx   ebx, ax
0x1800431c6  or      ebx, 80070000h
0x1800431cc  jmp     short loc_1800431D3
0x1800431ce  mov     ebx, 80004005h
0x1800431d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431da  lea     rax, WPP_GLOBAL_Control
0x1800431e1  cmp     rcx, rax
0x1800431e4  jz      loc_1800435CF
0x1800431ea  cmp     byte ptr [rcx+19h], 2
0x1800431ee  jb      loc_1800435CF
0x1800431f4  test    byte ptr [rcx+1Ch], 10h
0x1800431f8  jz      loc_1800435CF
0x1800431fe  lea     rsi, aPcollClear; "pColl->Clear"
0x180043205  mov     r9d, ebx
0x180043208  mov     r8, rsi
0x18004320b  lea     rdx, aNpsds; "NPSDS"
0x180043212  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180043219  call    WppDbgPrint
0x18004321e  mov     edx, 10h
0x180043223  jmp     loc_1800435B6
0x180043228  mov     rcx, [rbp+arg_0]
0x18004322c  test    rcx, rcx
0x18004322f  jz      short loc_180043245
0x180043231  mov     rax, [rcx]
0x180043234  mov     rax, [rax+10h]
0x180043238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004323d  mov     [rbp+arg_0], 0
0x180043245  mov     rcx, [rbx+8]
0x180043249  lea     rdx, [rbp+arg_0]
0x18004324d  mov     rax, [rcx]
0x180043250  mov     rax, [rax+0E0h]
0x180043257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004325c  mov     edi, eax
0x18004325e  test    eax, eax
0x180043260  jz      short loc_1800432D5
0x180043262  call    cs:__imp_GetLastError
0x180043268  mov     ebx, eax
0x18004326a  test    eax, eax
0x18004326c  jz      short loc_18004327B
0x18004326e  jle     short loc_180043280
0x180043270  movzx   ebx, ax
0x180043273  or      ebx, 80070000h
0x180043279  jmp     short loc_180043280
0x18004327b  mov     ebx, 80004005h
0x180043280  mov     rcx, cs:WPP_GLOBAL_Control
0x180043287  lea     rax, WPP_GLOBAL_Control
0x18004328e  cmp     rcx, rax
0x180043291  jz      loc_1800435CF
0x180043297  cmp     byte ptr [rcx+19h], 2
0x18004329b  jb      loc_1800435CF
0x1800432a1  test    byte ptr [rcx+1Ch], 10h
0x1800432a5  jz      loc_1800435CF
0x1800432ab  lea     rsi, aGPserviceGetRa; "g_pService->get_RAPolicies"
0x1800432b2  mov     r9d, ebx
0x1800432b5  mov     r8, rsi
0x1800432b8  lea     rdx, aNpsds; "NPSDS"
0x1800432bf  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800432c6  call    WppDbgPrint
0x1800432cb  mov     edx, 11h
0x1800432d0  jmp     loc_1800435B6
0x1800432d5  mov     rcx, [rbp+arg_0]
0x1800432d9  mov     rax, [rcx]
0x1800432dc  mov     rax, [rax+40h]
0x1800432e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432e5  mov     edi, eax
0x1800432e7  test    eax, eax
0x1800432e9  jz      short loc_18004335E
0x1800432eb  call    cs:__imp_GetLastError
0x1800432f1  mov     ebx, eax
0x1800432f3  test    eax, eax
0x1800432f5  jz      short loc_180043304
0x1800432f7  jle     short loc_180043309
0x1800432f9  movzx   ebx, ax
0x1800432fc  or      ebx, 80070000h
0x180043302  jmp     short loc_180043309
0x180043304  mov     ebx, 80004005h
0x180043309  mov     rcx, cs:WPP_GLOBAL_Control
0x180043310  lea     rax, WPP_GLOBAL_Control
0x180043317  cmp     rcx, rax
0x18004331a  jz      loc_1800435CF
0x180043320  cmp     byte ptr [rcx+19h], 2
0x180043324  jb      loc_1800435CF
0x18004332a  test    byte ptr [rcx+1Ch], 10h
0x18004332e  jz      loc_1800435CF
0x180043334  lea     rsi, aPcollClear; "pColl->Clear"
0x18004333b  mov     r9d, ebx
0x18004333e  mov     r8, rsi
0x180043341  lea     rdx, aNpsds; "NPSDS"
0x180043348  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004334f  call    WppDbgPrint
0x180043354  mov     edx, 12h
0x180043359  jmp     loc_1800435B6
0x18004335e  mov     rcx, [rbp+arg_0]
0x180043362  test    rcx, rcx
0x180043365  jz      short loc_18004337B
0x180043367  mov     rax, [rcx]
0x18004336a  mov     rax, [rax+10h]
0x18004336e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043373  mov     [rbp+arg_0], 0
0x18004337b  mov     rcx, [rbx+8]
0x18004337f  lea     rdx, [rbp+arg_0]
0x180043383  mov     rax, [rcx]
0x180043386  mov     rax, [rax+0E8h]
0x18004338d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043392  mov     edi, eax
0x180043394  test    eax, eax
0x180043396  jz      short loc_18004340B
0x180043398  call    cs:__imp_GetLastError
0x18004339e  mov     ebx, eax
0x1800433a0  test    eax, eax
0x1800433a2  jz      short loc_1800433B1
0x1800433a4  jle     short loc_1800433B6
0x1800433a6  movzx   ebx, ax
0x1800433a9  or      ebx, 80070000h
0x1800433af  jmp     short loc_1800433B6
0x1800433b1  mov     ebx, 80004005h
0x1800433b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433bd  lea     rax, WPP_GLOBAL_Control
0x1800433c4  cmp     rcx, rax
0x1800433c7  jz      loc_1800435CF
0x1800433cd  cmp     byte ptr [rcx+19h], 2
0x1800433d1  jb      loc_1800435CF
0x1800433d7  test    byte ptr [rcx+1Ch], 10h
0x1800433db  jz      loc_1800435CF
0x1800433e1  lea     rsi, aGPserviceGetCr; "g_pService->get_CRPolicies"
0x1800433e8  mov     r9d, ebx
0x1800433eb  mov     r8, rsi
0x1800433ee  lea     rdx, aNpsds; "NPSDS"
0x1800433f5  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800433fc  call    WppDbgPrint
0x180043401  mov     edx, 13h
0x180043406  jmp     loc_1800435B6
0x18004340b  mov     rcx, [rbp+arg_0]
0x18004340f  mov     rax, [rcx]
0x180043412  mov     rax, [rax+40h]
0x180043416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004341b  mov     edi, eax
0x18004341d  test    eax, eax
0x18004341f  jz      short loc_180043494
0x180043421  call    cs:__imp_GetLastError
0x180043427  mov     ebx, eax
0x180043429  test    eax, eax
0x18004342b  jz      short loc_18004343A
0x18004342d  jle     short loc_18004343F
0x18004342f  movzx   ebx, ax
0x180043432  or      ebx, 80070000h
0x180043438  jmp     short loc_18004343F
0x18004343a  mov     ebx, 80004005h
0x18004343f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043446  lea     rax, WPP_GLOBAL_Control
0x18004344d  cmp     rcx, rax
0x180043450  jz      loc_1800435CF
0x180043456  cmp     byte ptr [rcx+19h], 2
0x18004345a  jb      loc_1800435CF
0x180043460  test    byte ptr [rcx+1Ch], 10h
0x180043464  jz      loc_1800435CF
0x18004346a  lea     rsi, aPcollClear; "pColl->Clear"
0x180043471  mov     r9d, ebx
0x180043474  mov     r8, rsi
0x180043477  lea     rdx, aNpsds; "NPSDS"
0x18004347e  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180043485  call    WppDbgPrint
0x18004348a  mov     edx, 14h
0x18004348f  jmp     loc_1800435B6
0x180043494  mov     rcx, [rbp+arg_0]
0x180043498  test    rcx, rcx
0x18004349b  jz      short loc_1800434B1
0x18004349d  mov     rax, [rcx]
0x1800434a0  mov     rax, [rax+10h]
0x1800434a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434a9  mov     [rbp+arg_0], 0
0x1800434b1  mov     rcx, [rbx+8]
0x1800434b5  lea     rdx, [rbp+arg_0]
0x1800434b9  mov     rax, [rcx]
0x1800434bc  mov     rax, [rax+0D8h]
0x1800434c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434c8  mov     edi, eax
0x1800434ca  test    eax, eax
0x1800434cc  jz      short loc_18004353E
0x1800434ce  call    cs:__imp_GetLastError
0x1800434d4  mov     ebx, eax
0x1800434d6  test    eax, eax
0x1800434d8  jz      short loc_1800434E7
0x1800434da  jle     short loc_1800434EC
0x1800434dc  movzx   ebx, ax
0x1800434df  or      ebx, 80070000h
0x1800434e5  jmp     short loc_1800434EC
0x1800434e7  mov     ebx, 80004005h
0x1800434ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434f3  lea     rax, WPP_GLOBAL_Control
0x1800434fa  cmp     rcx, rax
0x1800434fd  jz      loc_1800435CF
0x180043503  cmp     byte ptr [rcx+19h], 2
0x180043507  jb      loc_1800435CF
0x18004350d  test    byte ptr [rcx+1Ch], 10h
0x180043511  jz      loc_1800435CF
0x180043517  lea     rsi, aGPserviceGetRe; "g_pService->get_RemoteServers"
0x18004351e  mov     r9d, ebx
0x180043521  mov     r8, rsi
0x180043524  lea     rdx, aNpsds; "NPSDS"
0x18004352b  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180043532  call    WppDbgPrint
0x180043537  mov     edx, 15h
0x18004353c  jmp     short loc_1800435B6
0x18004353e  mov     rcx, [rbp+arg_0]
0x180043542  mov     rax, [rcx]
0x180043545  mov     rax, [rax+40h]
0x180043549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004354e  mov     edi, eax
0x180043550  test    eax, eax
0x180043552  jz      short loc_1800435CF
0x180043554  call    cs:__imp_GetLastError
0x18004355a  mov     ebx, eax
0x18004355c  test    eax, eax
0x18004355e  jz      short loc_18004356D
0x180043560  jle     short loc_180043572
0x180043562  movzx   ebx, ax
0x180043565  or      ebx, 80070000h
0x18004356b  jmp     short loc_180043572
0x18004356d  mov     ebx, 80004005h
0x180043572  mov     rcx, cs:WPP_GLOBAL_Control
0x180043579  lea     rax, WPP_GLOBAL_Control
0x180043580  cmp     rcx, rax
0x180043583  jz      short loc_1800435CF
0x180043585  cmp     byte ptr [rcx+19h], 2
0x180043589  jb      short loc_1800435CF
0x18004358b  test    byte ptr [rcx+1Ch], 10h
0x18004358f  jz      short loc_1800435CF
0x180043591  lea     rsi, aPcollClear; "pColl->Clear"
0x180043598  mov     r9d, ebx
0x18004359b  mov     r8, rsi
0x18004359e  lea     rdx, aNpsds; "NPSDS"
0x1800435a5  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800435ac  call    WppDbgPrint
0x1800435b1  mov     edx, 16h
0x1800435b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435bd  mov     [rsp+38h+var_10], ebx
0x1800435c1  mov     [rsp+38h+var_18], rsi
0x1800435c6  mov     rcx, [rcx+10h]
0x1800435ca  call    WPP_SF_ssd
0x1800435cf  mov     rcx, [rbp+arg_0]
0x1800435d3  test    rcx, rcx
0x1800435d6  jz      short loc_1800435E4
0x1800435d8  mov     rax, [rcx]
0x1800435db  mov     rax, [rax+10h]
0x1800435df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435e4  mov     eax, edi
  ... truncated ...
```
