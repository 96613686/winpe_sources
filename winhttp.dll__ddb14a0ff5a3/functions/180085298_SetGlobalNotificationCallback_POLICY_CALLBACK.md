# SetGlobalNotificationCallback(_POLICY_CALLBACK *)

- ea: `0x180085298`
- end: `0x18008560a`
- name: `?SetGlobalNotificationCallback@@YAKPEAU_POLICY_CALLBACK@@@Z`
- size: `882`
- prototype: `unsigned int __fastcall(struct _POLICY_CALLBACK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180085218`

## callees

- `0x1800081a0`
- `0x180041eb0`
- `0x18005cfac`
- `0x18007fd6c`
- `0x180085298`
- `0x180085610`
- `0x18008597c`
- `0x1800a2660`
- `0x1800d3260`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800855f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800855f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800853cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800853cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800855e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800855e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180085467`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180085467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800853dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800853dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085471`
- `RPCRT4!UuidCreate` at `0x180085408`
- `RPCRT4!UuidCreate` at `0x180085408`

## pseudocode

```c
__int64 __fastcall SetGlobalNotificationCallback(struct _POLICY_CALLBACK *a1)
{
  int v1; // r14d
  int v2; // r13d
  RTL_SRWLOCK *v3; // r15
  signed int v5; // ebx
  int v6; // eax
  __int64 v7; // rax
  char *Heap; // rax
  char *v9; // r14
  HANDLE EventA; // rax
  signed int v11; // eax
  RPC_STATUS v12; // eax
  const WCHAR *v13; // rdx
  DWORD LastError; // eax
  bool v15; // sf
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rdx
  unsigned int v20; // ebx
  __int64 v22; // [rsp+20h] [rbp-28h]
  RTL_SRWLOCK *v23; // [rsp+28h] [rbp-20h] BYREF
  __int64 v24; // [rsp+30h] [rbp-18h]
  struct _POLICY_CALLBACK_ENTRY *v25; // [rsp+38h] [rbp-10h] BYREF

  v1 = 0;
  HIDWORD(v22) = 0;
  v2 = 0;
  v24 = 0;
  v3 = &g_PolicyCallbackLock;
  v25 = 0;
  v23 = &g_PolicyCallbackLock;
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_q(1038, 16, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids);
  if ( a1 )
  {
    if ( *(_QWORD *)a1 || *((_QWORD *)a1 + 1) )
    {
      v7 = *((_QWORD *)a1 + 5) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v7 )
        v7 = *((_QWORD *)a1 + 6) - *(_QWORD *)GUID_NULL.Data4;
      if ( v7 )
      {
        v5 = -2147023649;
        HIDWORD(v22) = 244;
      }
      else if ( g_cPolicyCallbacks + 1 < 0x20 )
      {
        HIDWORD(v22) = 0;
        Heap = (char *)WxAllocateHeapEx(a1, 80);
        v9 = Heap;
        if ( Heap )
        {
          memset_0(Heap, 0, 0x50u);
          v25 = (struct _POLICY_CALLBACK_ENTRY *)v9;
          EventA = CreateEventA(0, 0, 0, 0);
          *((_QWORD *)v9 + 8) = EventA;
          if ( EventA )
          {
            v12 = UuidCreate((UUID *)((char *)a1 + 40));
            v5 = v12;
            if ( v12 > 0 )
              v5 = (unsigned __int16)v12 | 0x80070000;
            if ( v5 >= 0 )
            {
              *(_OWORD *)v9 = *(_OWORD *)a1;
              *((_OWORD *)v9 + 1) = *((_OWORD *)a1 + 1);
              *((_OWORD *)v9 + 2) = *((_OWORD *)a1 + 2);
              *((_QWORD *)v9 + 6) = *((_QWORD *)a1 + 6);
              v13 = (const WCHAR *)*((_QWORD *)a1 + 1);
              if ( !v13 )
                v13 = *(const WCHAR **)a1;
              if ( GetModuleHandleExW(4u, v13, (HMODULE *)v9 + 9) )
                goto LABEL_39;
              LastError = GetLastError();
              v5 = LastError;
              if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
                WPP_SF_d(1053, 17, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids, LastError, v22);
              v15 = v5 < 0;
              if ( v5 > 0 )
              {
                v5 = (unsigned __int16)v5 | 0x80070000;
                v15 = v5 < 0;
              }
              if ( !v15 )
              {
LABEL_39:
                if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
                  WPP_SF_q(1038, 18, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids);
                AutoSrw::LockExclusive((AutoSrw *)&v23);
                v16 = g_cPolicyCallbacks;
                v17 = g_cPolicyCallbacks + 1;
                if ( (unsigned int)v17 < 0x20 )
                {
                  v5 = 0;
                  v18 = 0;
                  if ( g_cPolicyCallbacks )
                  {
                    do
                    {
                      if ( (unsigned __int64)(&g_rgPolicyCallbacks)[v18][4] < *((_QWORD *)v9 + 4) )
                        break;
                      v18 = (unsigned int)(v18 + 1);
                    }
                    while ( (unsigned int)v18 < g_cPolicyCallbacks );
                    if ( (unsigned int)v18 < g_cPolicyCallbacks && (unsigned int)v17 > (unsigned int)v18 )
                    {
                      do
                      {
                        v19 = (unsigned int)(v17 - 1);
                        (&g_rgPolicyCallbacks)[v17] = (&g_rgPolicyCallbacks)[v19];
                        v17 = v19;
                      }
                      while ( (unsigned int)v19 > (unsigned int)v18 );
                    }
                  }
                  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
                  {
                    WPP_SF__guid_(1038, 19, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids, v9 + 40);
                    v16 = g_cPolicyCallbacks;
                  }
                  (&g_rgPolicyCallbacks)[v18] = (struct _POLICY_CALLBACK_ENTRY * near *)v9;
                  g_dwNotifications |= *((_DWORD *)a1 + 4);
                  g_cPolicyCallbacks = v16 + 1;
                  v25 = 0;
                }
                else
                {
                  v5 = -2147024812;
                  HIDWORD(v22) = 299;
                }
                AutoSrw::UnlockExclusive((AutoSrw *)&v23);
                v2 = HIDWORD(v24);
                v3 = v23;
              }
              else
              {
                HIDWORD(v22) = 283;
              }
            }
            else
            {
              HIDWORD(v22) = 258;
            }
          }
          else
          {
            v11 = GetLastError();
            v5 = v11;
            if ( v11 > 0 )
              v5 = (unsigned __int16)v11 | 0x80070000;
            HIDWORD(v22) = 256;
            if ( v5 >= 0 )
              v5 = -2147418113;
          }
        }
        else
        {
          v5 = -2147024882;
          HIDWORD(v22) = 253;
        }
        v1 = v24;
      }
      else
      {
        v5 = -2147024812;
        HIDWORD(v22) = 247;
      }
    }
    else
    {
      v6 = ClearGlobalNotificationCallback(a1);
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
        v5 = 0;
      else
        HIDWORD(v22) = 239;
    }
  }
  else
  {
    v5 = -2147024809;
    HIDWORD(v22) = 234;
  }
  FreePolicyCallbackEntry(&v25);
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_d(1038, 20, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids, (unsigned int)v5, v22);
  v20 = WX_WIN32_FROM_HR((unsigned int)v5);
  if ( v1 )
    ReleaseSRWLockShared(v3);
  if ( v2 )
    ReleaseSRWLockExclusive(v3);
  return v20;
}

```

## disassembly

```asm
0x180085298  push    rbp
0x18008529a  push    rbx
0x18008529b  push    rsi
0x18008529c  push    rdi
0x18008529d  push    r12
0x18008529f  push    r13
0x1800852a1  push    r14
0x1800852a3  push    r15
0x1800852a5  mov     rbp, rsp
0x1800852a8  sub     rsp, 48h
0x1800852ac  xor     r14d, r14d
0x1800852af  mov     [rbp+var_24], 0
0x1800852b6  xor     r13d, r13d
0x1800852b9  mov     [rbp+var_18], r14
0x1800852bd  lea     r15, ?g_PolicyCallbackLock@@3VWxSrw@@A; WxSrw g_PolicyCallbackLock
0x1800852c4  mov     [rbp+var_10], r13
0x1800852c8  mov     rdi, rcx
0x1800852cb  mov     [rbp+var_20], r15
0x1800852cf  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800852d6  jz      short loc_1800852F0
0x1800852d8  lea     edx, [r14+10h]
0x1800852dc  mov     ecx, 40Eh
0x1800852e1  mov     r9, rdi
0x1800852e4  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x1800852eb  call    WPP_SF_q
0x1800852f0  test    rdi, rdi
0x1800852f3  jnz     short loc_180085306
0x1800852f5  mov     ebx, 80070057h
0x1800852fa  mov     [rbp+var_24], 0EAh
0x180085301  jmp     loc_1800855A7
0x180085306  cmp     [rdi], r13
0x180085309  jnz     short loc_18008533F
0x18008530b  cmp     [rdi+8], r13
0x18008530f  jnz     short loc_18008533F
0x180085311  mov     rcx, rdi; struct _POLICY_CALLBACK *
0x180085314  call    ?ClearGlobalNotificationCallback@@YAKPEAU_POLICY_CALLBACK@@@Z; ClearGlobalNotificationCallback(_POLICY_CALLBACK *)
0x180085319  mov     ebx, eax
0x18008531b  test    eax, eax
0x18008531d  jle     short loc_180085328
0x18008531f  movzx   ebx, ax
0x180085322  or      ebx, 80070000h
0x180085328  test    ebx, ebx
0x18008532a  jns     short loc_180085338
0x18008532c  mov     [rbp+var_24], 0EFh
0x180085333  jmp     loc_1800855A7
0x180085338  xor     ebx, ebx
0x18008533a  jmp     loc_1800855A7
0x18008533f  mov     rax, [rdi+28h]
0x180085343  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18008534a  jnz     short loc_180085357
0x18008534c  mov     rax, [rdi+30h]
0x180085350  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180085357  test    rax, rax
0x18008535a  jnz     loc_18008559B
0x180085360  mov     eax, cs:?g_cPolicyCallbacks@@3KA; ulong g_cPolicyCallbacks
0x180085366  inc     eax
0x180085368  cmp     eax, 20h ; ' '
0x18008536b  jb      short loc_18008537E
0x18008536d  mov     ebx, 80070054h
0x180085372  mov     [rbp+var_24], 0F7h
0x180085379  jmp     loc_1800855A7
0x18008537e  mov     esi, 50h ; 'P'
0x180085383  mov     [rbp+var_24], r13d
0x180085387  mov     edx, esi
0x180085389  call    WxAllocateHeapEx
0x18008538e  mov     r14, rax
0x180085391  test    rax, rax
0x180085394  jnz     short loc_1800853B2
0x180085396  mov     [rbp+var_24], 4Ch ; 'L'
0x18008539d  mov     ebx, 8007000Eh
0x1800853a2  mov     [rbp+var_24], 0FDh
0x1800853a9  mov     r14d, dword ptr [rbp+var_18]
0x1800853ad  jmp     loc_1800855A7
0x1800853b2  mov     r8, rsi; Size
0x1800853b5  xor     edx, edx; Val
0x1800853b7  mov     rcx, r14; void *
0x1800853ba  call    memset_0
0x1800853bf  mov     [rbp+var_10], r14
0x1800853c3  xor     r9d, r9d; lpName
0x1800853c6  xor     r8d, r8d; bInitialState
0x1800853c9  xor     edx, edx; bManualReset
0x1800853cb  xor     ecx, ecx; lpEventAttributes
0x1800853cd  call    cs:__imp_CreateEventA
0x1800853d3  mov     [r14+40h], rax
0x1800853d7  test    rax, rax
0x1800853da  jnz     short loc_180085404
0x1800853dc  call    cs:__imp_GetLastError
0x1800853e2  mov     ebx, eax
0x1800853e4  test    eax, eax
0x1800853e6  jle     short loc_1800853F1
0x1800853e8  movzx   ebx, ax
0x1800853eb  or      ebx, 80070000h
0x1800853f1  test    ebx, ebx
0x1800853f3  mov     [rbp+var_24], 100h
0x1800853fa  mov     eax, 8000FFFFh
0x1800853ff  cmovns  ebx, eax
0x180085402  jmp     short loc_1800853A9
0x180085404  lea     rcx, [rdi+28h]; Uuid
0x180085408  call    cs:__imp_UuidCreate
0x18008540e  mov     ebx, eax
0x180085410  mov     esi, 80070000h
0x180085415  test    eax, eax
0x180085417  jle     short loc_18008541E
0x180085419  movzx   ebx, ax
0x18008541c  or      ebx, esi
0x18008541e  test    ebx, ebx
0x180085420  jns     short loc_18008542E
0x180085422  mov     [rbp+var_24], 102h
0x180085429  jmp     loc_1800853A9
0x18008542e  movups  xmm0, xmmword ptr [rdi]
0x180085431  movups  xmmword ptr [r14], xmm0
0x180085435  movups  xmm1, xmmword ptr [rdi+10h]
0x180085439  movups  xmmword ptr [r14+10h], xmm1
0x18008543e  movups  xmm0, xmmword ptr [rdi+20h]
0x180085442  movups  xmmword ptr [r14+20h], xmm0
0x180085447  movsd   xmm1, qword ptr [rdi+30h]
0x18008544c  movsd   qword ptr [r14+30h], xmm1
0x180085452  mov     rdx, [rdi+8]
0x180085456  test    rdx, rdx
0x180085459  jnz     short loc_18008545E
0x18008545b  mov     rdx, [rdi]; lpModuleName
0x18008545e  lea     r8, [r14+48h]; phModule
0x180085462  mov     ecx, 4; dwFlags
0x180085467  call    cs:__imp_GetModuleHandleExW
0x18008546d  test    eax, eax
0x18008546f  jnz     short loc_1800854B4
0x180085471  call    cs:__imp_GetLastError
0x180085477  mov     ebx, eax
0x180085479  test    byte ptr cs:xmmword_180107A60+3, 20h
0x180085480  jz      short loc_18008549B
0x180085482  mov     edx, 11h
0x180085487  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x18008548e  mov     ecx, 41Dh
0x180085493  mov     r9d, eax
0x180085496  call    WPP_SF_d
0x18008549b  test    ebx, ebx
0x18008549d  jle     short loc_1800854A6
0x18008549f  movzx   ebx, bx
0x1800854a2  or      ebx, esi
0x1800854a4  test    ebx, ebx
0x1800854a6  jns     short loc_1800854B4
0x1800854a8  mov     [rbp+var_24], 11Bh
0x1800854af  jmp     loc_1800853A9
0x1800854b4  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800854bb  jz      short loc_1800854D7
0x1800854bd  mov     r9, [r14+48h]
0x1800854c1  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x1800854c8  mov     edx, 12h
0x1800854cd  mov     ecx, 40Eh
0x1800854d2  call    WPP_SF_q
0x1800854d7  lea     rcx, [rbp+var_20]; this
0x1800854db  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x1800854e0  mov     r8d, cs:?g_cPolicyCallbacks@@3KA; ulong g_cPolicyCallbacks
0x1800854e7  lea     ecx, [r8+1]
0x1800854eb  cmp     ecx, 20h ; ' '
0x1800854ee  jb      short loc_180085501
0x1800854f0  mov     ebx, 80070054h
0x1800854f5  mov     [rbp+var_24], 12Bh
0x1800854fc  jmp     loc_180085585
0x180085501  xor     ebx, ebx
0x180085503  lea     r15, ?g_rgPolicyCallbacks@@3PAPEAU_POLICY_CALLBACK_ENTRY@@A; _POLICY_CALLBACK_ENTRY * near * g_rgPolicyCallbacks
0x18008550a  xor     esi, esi
0x18008550c  test    r8d, r8d
0x18008550f  jz      short loc_180085540
0x180085511  mov     rdx, [r14+20h]
0x180085515  mov     rax, [r15+rsi*8]
0x180085519  cmp     [rax+20h], rdx
0x18008551d  jb      short loc_180085526
0x18008551f  inc     esi
0x180085521  cmp     esi, r8d
0x180085524  jb      short loc_180085515
0x180085526  cmp     esi, r8d
0x180085529  jnb     short loc_180085540
0x18008552b  cmp     ecx, esi
0x18008552d  jbe     short loc_180085540
0x18008552f  lea     edx, [rcx-1]
0x180085532  mov     rax, [r15+rdx*8]
0x180085536  mov     [r15+rcx*8], rax
0x18008553a  mov     ecx, edx
0x18008553c  cmp     edx, esi
0x18008553e  ja      short loc_18008552F
0x180085540  test    byte ptr cs:xmmword_180107A60+1, 40h
0x180085547  jz      short loc_18008556A
0x180085549  lea     r9, [r14+28h]
0x18008554d  mov     edx, 13h
0x180085552  mov     ecx, 40Eh
0x180085557  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x18008555e  call    WPP_SF__guid_
0x180085563  mov     r8d, cs:?g_cPolicyCallbacks@@3KA; ulong g_cPolicyCallbacks
0x18008556a  inc     r8d
0x18008556d  mov     [r15+rsi*8], r14
0x180085571  mov     eax, [rdi+10h]
0x180085574  or      cs:?g_dwNotifications@@3KA, eax; ulong g_dwNotifications
0x18008557a  mov     cs:?g_cPolicyCallbacks@@3KA, r8d; ulong g_cPolicyCallbacks
0x180085581  mov     [rbp+var_10], rbx
0x180085585  lea     rcx, [rbp+var_20]; this
0x180085589  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x18008558e  mov     r13d, dword ptr [rbp+var_18+4]
0x180085592  mov     r15, [rbp+var_20]
0x180085596  jmp     loc_1800853A9
0x18008559b  mov     ebx, 800704DFh
0x1800855a0  mov     [rbp+var_24], 0F4h
0x1800855a7  lea     rcx, [rbp+var_10]; struct _POLICY_CALLBACK_ENTRY **
0x1800855ab  call    ?FreePolicyCallbackEntry@@YAXPEAPEAU_POLICY_CALLBACK_ENTRY@@@Z; FreePolicyCallbackEntry(_POLICY_CALLBACK_ENTRY * *)
0x1800855b0  test    byte ptr cs:xmmword_180107A60+1, 40h
0x1800855b7  jz      short loc_1800855D2
0x1800855b9  mov     edx, 14h
0x1800855be  lea     r8, WPP_2de40998c5db34be4ac1b096b1e50e34_Traceguids
0x1800855c5  mov     ecx, 40Eh
0x1800855ca  mov     r9d, ebx
0x1800855cd  call    WPP_SF_d
0x1800855d2  mov     ecx, ebx
0x1800855d4  call    WX_WIN32_FROM_HR
0x1800855d9  mov     ebx, eax
0x1800855db  test    r14d, r14d
0x1800855de  jz      short loc_1800855E9
0x1800855e0  mov     rcx, r15; SRWLock
0x1800855e3  call    cs:__imp_ReleaseSRWLockShared
0x1800855e9  test    r13d, r13d
0x1800855ec  jz      short loc_1800855F7
0x1800855ee  mov     rcx, r15; SRWLock
0x1800855f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800855f7  mov     eax, ebx
0x1800855f9  add     rsp, 48h
0x1800855fd  pop     r15
0x1800855ff  pop     r14
0x180085601  pop     r13
0x180085603  pop     r12
0x180085605  pop     rdi
0x180085606  pop     rsi
0x180085607  pop     rbx
0x180085608  pop     rbp
0x180085609  retn
```
