# WDiagProcessAcmConnectSMTransition(_WD_INTERFACE_CONTEXT *,ulong,ulong,unsigned __int64)

- ea: `0x18001d5b4`
- end: `0x18001dabc`
- name: `?WDiagProcessAcmConnectSMTransition@@YAKPEAU_WD_INTERFACE_CONTEXT@@KK_K@Z`
- size: `1288`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180011d68`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18001d5b4`
- `0x18001e3dc`
- `0x18001e950`
- `0x18001ea10`
- `0x18002bde8`
- `0x18002f3d8`
- `0x1800469dc`
- `0x1800766d0`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d7b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d7b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d67d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d67d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d68a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d68a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d75d`

## pseudocode

```c
__int64 __fastcall WDiagProcessAcmConnectSMTransition(
        struct _WD_INTERFACE_CONTEXT *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int64 a4)
{
  __int64 v5; // rbx
  __int64 v6; // r15
  PVOID *v8; // r11
  __int64 v9; // r11
  DWORD CurrentThreadId; // r14d
  char v11; // al
  int v12; // r8d
  unsigned int v13; // r8d
  struct _FILETIME *v14; // rbx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  unsigned int v18; // eax
  char *v19; // rbx
  unsigned int v20; // r15d
  struct _WDIAG_RW_LOCK *v21; // rdx
  unsigned int v22; // edx
  int v24; // [rsp+28h] [rbp-80h]

  v5 = a3;
  v6 = a2;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 63, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 225) >= 4u && (*((_BYTE *)v8 + 228) & 4) != 0 )
    {
      AceTriggerToName(a4);
      WPP_SF_SSS(*(_QWORD *)(v9 + 216), (__int64)(&g_strStateName)[v6], (__int64)(&g_strStateName)[v5]);
    }
  }
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
  WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
  if ( (*((_BYTE *)a1 + 3448) & 4) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    WPP_SF_qqdsddsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      *((_DWORD *)a1 + 864),
      *((_QWORD *)a1 + 433),
      *((_DWORD *)a1 + 865),
      CurrentThreadId,
      (__int64)"WDiagProcessAcmConnectSMTransition",
      18);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 1042;
  *((_QWORD *)a1 + 433) = "WDiagProcessAcmConnectSMTransition";
  *((_DWORD *)a1 + 32) = v6;
  *((_DWORD *)a1 + 33) = v5;
  *((_QWORD *)a1 + 17) = a4;
  if ( (*((_BYTE *)a1 + 3448) & 4) == 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
  {
    v11 = GetCurrentThreadId();
    WPP_SF_qqDsdDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_BYTE)a1 + 24,
      v24,
      *((_QWORD *)a1 + 435),
      *((_DWORD *)a1 + 868),
      v11,
      (__int64)"WDiagProcessAcmConnectSMTransition",
      22);
  }
  *((_DWORD *)a1 + 862) &= ~4u;
  *((_DWORD *)a1 + 868) = 1046;
  *((_DWORD *)a1 + 864) = 0;
  *((_QWORD *)a1 + 435) = "WDiagProcessAcmConnectSMTransition";
  LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
  if ( (_DWORD)v5 == 6 )
  {
    WDiagAcquireExLock(
      a1,
      (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352),
      "WDiagProcessAcmConnectSMTransition",
      0x41Cu);
    v12 = *((_DWORD *)a1 + 42);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 66, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
      }
      WDiagGetTime((LPFILETIME)a1 + 22);
      *((_DWORD *)a1 + 42) = 1;
      *((_DWORD *)a1 + 48) = 1;
      goto LABEL_55;
    }
    WDiagGetTime((LPFILETIME)a1 + 78 * ((v12 - 1) % 5u) + 23);
    v13 = *((_DWORD *)a1 + 42);
    *((_DWORD *)a1 + 42) = v13 + 1;
    v14 = (struct _FILETIME *)((char *)a1 + 624 * (v13 % 5) + 176);
    WDiagGetTime(v14);
    v14[1] = 0;
    v14[2].dwLowDateTime = *((_DWORD *)a1 + 42);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        65,
        &WPP_fec73b95d5a537674450248f38664378_Traceguids,
        *((unsigned int *)a1 + 42));
    }
    if ( a4 != 8 )
    {
      if ( a4 == 16 )
      {
        v14[2].dwHighDateTime = 1;
LABEL_35:
        v15 = (void *)v14[75];
        if ( v15 )
        {
          WDiagFreeMem(v15);
          v14[75] = 0;
        }
        v16 = (void *)v14[76];
        if ( v16 )
        {
          WDiagFreeMem(v16);
          v14[76] = 0;
        }
        v17 = (void *)v14[77];
        if ( v17 )
        {
          WDiagFreeMem(v17);
          v14[77] = 0;
        }
        v18 = *((_DWORD *)a1 + 42);
        if ( v18 > 5 )
        {
          v19 = (char *)*((_QWORD *)a1 + 8);
          v20 = v18 - 5;
          while ( v19 != (char *)a1 + 56 && *((_DWORD *)v19 + 294) <= v20 )
          {
            WDiagAcquireExLock(v19, (struct _WDIAG_RW_LOCK *)(v19 + 3920), "WDiagProcessAcmConnectSMTransition", 0x4A5u);
            v21 = (struct _WDIAG_RW_LOCK *)(v19 + 3920);
            if ( *((_DWORD *)v19 + 4) == 1313754947 )
            {
              *((_DWORD *)v19 + 4) = 843992899;
              WDiagReleaseExLock(v19, v21, "WDiagProcessAcmConnectSMTransition", 0x4ABu);
              WDiagReleaseExLock(
                a1,
                (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352),
                "WDiagProcessAcmConnectSMTransition",
                0x4ACu);
              WDiagDereferenceConnection((struct _WD_CONNECTION_CONTEXT *)v19, v22);
              WDiagAcquireExLock(
                a1,
                (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352),
                "WDiagProcessAcmConnectSMTransition",
                0x4B3u);
              v19 = (char *)a1 + 56;
            }
            else
            {
              WDiagReleaseExLock(v19, v21, "WDiagProcessAcmConnectSMTransition", 0x4B8u);
            }
            v19 = (char *)*((_QWORD *)v19 + 1);
          }
        }
LABEL_55:
        WDiagReleaseExLock(
          a1,
          (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352),
          "WDiagProcessAcmConnectSMTransition",
          0x4C8u);
        goto LABEL_56;
      }
      if ( a4 != 32 )
      {
        switch ( a4 )
        {
          case 0x10000000uLL:
            v14[2].dwHighDateTime = 7;
            break;
          case 0x40000000uLL:
            v14[2].dwHighDateTime = 3;
            break;
          case 0x80000000uLL:
            v14[2].dwHighDateTime = 6;
            break;
        }
        goto LABEL_35;
      }
    }
    v14[2].dwHighDateTime = 4;
    goto LABEL_35;
  }
LABEL_56:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 67, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18001d5b4  push    rbx
0x18001d5b6  push    rbp
0x18001d5b7  push    rsi
0x18001d5b8  push    rdi
0x18001d5b9  push    r12
0x18001d5bb  push    r13
0x18001d5bd  push    r14
0x18001d5bf  push    r15
0x18001d5c1  sub     rsp, 68h
0x18001d5c5  mov     rbp, r9
0x18001d5c8  mov     ebx, r8d
0x18001d5cb  mov     r15d, edx
0x18001d5ce  mov     rsi, rcx
0x18001d5d1  mov     r11, cs:WPP_GLOBAL_Control
0x18001d5d8  lea     rdi, WPP_GLOBAL_Control
0x18001d5df  cmp     r11, rdi
0x18001d5e2  jz      loc_18001D669
0x18001d5e8  test    dword ptr [r11+0E4h], 200h
0x18001d5f3  jz      short loc_18001D614
0x18001d5f5  mov     rcx, [r11+0D8h]
0x18001d5fc  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001d603  mov     edx, 3Fh ; '?'
0x18001d608  call    WPP_SF_
0x18001d60d  mov     r11, cs:WPP_GLOBAL_Control
0x18001d614  cmp     r11, rdi
0x18001d617  jz      short loc_18001D669
0x18001d619  cmp     byte ptr [r11+0E1h], 4
0x18001d621  jb      short loc_18001D669
0x18001d623  test    byte ptr [r11+0E4h], 4
0x18001d62b  jz      short loc_18001D669
0x18001d62d  mov     rcx, rbp; unsigned __int64
0x18001d630  lea     rdi, ?g_strStateName@@3QBQEBGB; ushort const * const near * const g_strStateName
0x18001d637  call    ?AceTriggerToName@@YAPEBG_K@Z; AceTriggerToName(unsigned __int64)
0x18001d63c  mov     rcx, [r11+0D8h]; LoggerHandle
0x18001d643  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001d64a  mov     r9, rax
0x18001d64d  mov     edx, 40h ; '@'
0x18001d652  mov     rax, [rdi+rbx*8]
0x18001d656  mov     qword ptr [rsp+0A8h+var_80], rax; __int64
0x18001d65b  mov     rax, [rdi+r15*8]
0x18001d65f  mov     qword ptr [rsp+0A8h+var_88], rax; __int64
0x18001d664  call    WPP_SF_SSS
0x18001d669  lea     rdi, [rsi+0D18h]
0x18001d670  call    cs:__imp_GetCurrentThreadId
0x18001d676  lea     rcx, [rdi+8]; lpCriticalSection
0x18001d67a  mov     r14d, eax
0x18001d67d  call    cs:__imp_EnterCriticalSection
0x18001d683  mov     rcx, [rdi+58h]; hHandle
0x18001d687  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001d68a  call    cs:__imp_WaitForSingleObject
0x18001d690  test    byte ptr [rdi+60h], 4
0x18001d694  lea     r13, aWdiagprocessac_5; "WDiagProcessAcmConnectSMTransition"
0x18001d69b  jz      short loc_18001D6FF
0x18001d69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6a4  lea     rdx, WPP_GLOBAL_Control
0x18001d6ab  cmp     rcx, rdx
0x18001d6ae  jz      short loc_18001D706
0x18001d6b0  cmp     byte ptr [rcx+0E1h], 1
0x18001d6b7  jb      short loc_18001D706
0x18001d6b9  test    byte ptr [rcx+0E4h], 40h
0x18001d6c0  jz      short loc_18001D706
0x18001d6c2  mov     eax, [rdi+6Ch]
0x18001d6c5  mov     r9, rsi
0x18001d6c8  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001d6cf  mov     dword ptr [rsp+0A8h+var_58], 412h; char
0x18001d6d7  mov     [rsp+0A8h+var_60], r13; __int64
0x18001d6dc  mov     dword ptr [rsp+0A8h+var_68], r14d; char
0x18001d6e1  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18001d6e5  mov     rax, [rdi+70h]
0x18001d6e9  mov     [rsp+0A8h+var_78], rax; __int64
0x18001d6ee  mov     eax, [rdi+68h]
0x18001d6f1  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x18001d6f5  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18001d6fa  call    WPP_SF_qqdsddsd
0x18001d6ff  lea     rdx, WPP_GLOBAL_Control
0x18001d706  or      dword ptr [rdi+60h], 4
0x18001d70a  mov     [rdi+68h], r14d
0x18001d70e  mov     r14d, 416h
0x18001d714  mov     dword ptr [rdi+6Ch], 412h
0x18001d71b  mov     [rdi+70h], r13
0x18001d71f  mov     [rsi+80h], r15d
0x18001d726  mov     r15d, 4
0x18001d72c  mov     [rsi+84h], ebx
0x18001d732  mov     [rsi+88h], rbp
0x18001d739  test    [rdi+60h], r15b
0x18001d73d  jnz     short loc_18001D79F
0x18001d73f  mov     rax, cs:WPP_GLOBAL_Control
0x18001d746  cmp     rax, rdx
0x18001d749  jz      short loc_18001D79F
0x18001d74b  cmp     byte ptr [rax+0E1h], 1
0x18001d752  jb      short loc_18001D79F
0x18001d754  test    byte ptr [rax+0E4h], 40h
0x18001d75b  jz      short loc_18001D79F
0x18001d75d  call    cs:__imp_GetCurrentThreadId
0x18001d763  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d76a  mov     r9, rsi
0x18001d76d  mov     dword ptr [rsp+0A8h+var_58], r14d; char
0x18001d772  mov     [rsp+0A8h+var_60], r13; __int64
0x18001d777  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18001d77b  mov     eax, [rdi+78h]
0x18001d77e  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18001d785  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18001d789  mov     rax, [rdi+80h]
0x18001d790  mov     [rsp+0A8h+var_78], rax; __int64
0x18001d795  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18001d79a  call    WPP_SF_qqDsdDsd
0x18001d79f  and     dword ptr [rdi+60h], 0FFFFFFFBh
0x18001d7a3  lea     rcx, [rdi+8]; lpCriticalSection
0x18001d7a7  mov     [rdi+78h], r14d
0x18001d7ab  xor     r14d, r14d
0x18001d7ae  mov     [rdi+68h], r14d
0x18001d7b2  mov     [rdi+80h], r13
0x18001d7b9  call    cs:__imp_LeaveCriticalSection
0x18001d7bf  cmp     ebx, 6
0x18001d7c2  jnz     loc_18001DA72
0x18001d7c8  mov     r9d, 41Ch; unsigned int
0x18001d7ce  mov     r8, r13; char *
0x18001d7d1  mov     rdx, rdi; struct _WDIAG_RW_LOCK *
0x18001d7d4  mov     rcx, rsi; void *
0x18001d7d7  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d7dc  mov     r8d, [rsi+0A8h]
0x18001d7e3  test    r8d, r8d
0x18001d7e6  jz      loc_18001D9FF
0x18001d7ec  dec     r8d
0x18001d7ef  mov     ebx, 0CCCCCCCDh
0x18001d7f4  mov     eax, ebx
0x18001d7f6  mul     r8d
0x18001d7f9  shr     edx, 2
0x18001d7fc  lea     ecx, [rdx+rdx*4]
0x18001d7ff  sub     r8d, ecx
0x18001d802  mov     ecx, r8d
0x18001d805  imul    rcx, 270h
0x18001d80c  add     rcx, 0B8h
0x18001d813  add     rcx, rsi; lpFileTime
0x18001d816  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18001d81b  mov     r8d, [rsi+0A8h]
0x18001d822  mov     eax, ebx
0x18001d824  mul     r8d
0x18001d827  lea     ecx, [r8+1]
0x18001d82b  shr     edx, 2
0x18001d82e  mov     [rsi+0A8h], ecx
0x18001d834  lea     eax, [rdx+rdx*4]
0x18001d837  sub     r8d, eax
0x18001d83a  mov     eax, r8d
0x18001d83d  imul    rbx, rax, 270h
0x18001d844  add     rbx, 0B0h
0x18001d84b  add     rbx, rsi
0x18001d84e  mov     rcx, rbx; lpFileTime
0x18001d851  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18001d856  mov     [rbx+8], r14
0x18001d85a  mov     eax, [rsi+0A8h]
0x18001d860  mov     [rbx+10h], eax
0x18001d863  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d86a  lea     r12, WPP_GLOBAL_Control
0x18001d871  cmp     rcx, r12
0x18001d874  jz      short loc_18001D8A6
0x18001d876  cmp     byte ptr [rcx+0E1h], 3
0x18001d87d  jb      short loc_18001D8A6
0x18001d87f  test    [rcx+0E4h], r15b
0x18001d886  jz      short loc_18001D8A6
0x18001d888  mov     r9d, [rsi+0A8h]
0x18001d88f  lea     edx, [r14+41h]
0x18001d893  mov     rcx, [rcx+0D8h]
0x18001d89a  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001d8a1  call    WPP_SF_d
0x18001d8a6  cmp     rbp, 8
0x18001d8aa  jz      short loc_18001D8F8
0x18001d8ac  cmp     rbp, 10h
0x18001d8b0  jz      short loc_18001D8EF
0x18001d8b2  cmp     rbp, 20h ; ' '
0x18001d8b6  jz      short loc_18001D8F8
0x18001d8b8  cmp     rbp, 10000000h
0x18001d8bf  jz      short loc_18001D8E6
0x18001d8c1  cmp     rbp, 40000000h
0x18001d8c8  jz      short loc_18001D8DD
0x18001d8ca  mov     eax, 80000000h
0x18001d8cf  cmp     rbp, rax
0x18001d8d2  jnz     short loc_18001D8FC
0x18001d8d4  mov     dword ptr [rbx+14h], 6
0x18001d8db  jmp     short loc_18001D8FC
0x18001d8dd  mov     dword ptr [rbx+14h], 3
0x18001d8e4  jmp     short loc_18001D8FC
0x18001d8e6  mov     dword ptr [rbx+14h], 7
0x18001d8ed  jmp     short loc_18001D8FC
0x18001d8ef  mov     dword ptr [rbx+14h], 1
0x18001d8f6  jmp     short loc_18001D8FC
0x18001d8f8  mov     [rbx+14h], r15d
0x18001d8fc  mov     rcx, [rbx+258h]; lpMem
0x18001d903  test    rcx, rcx
0x18001d906  jz      short loc_18001D914
0x18001d908  call    ?WDiagFreeMem@@YAXPEAX@Z; WDiagFreeMem(void *)
0x18001d90d  mov     [rbx+258h], r14
0x18001d914  mov     rcx, [rbx+260h]; lpMem
0x18001d91b  test    rcx, rcx
0x18001d91e  jz      short loc_18001D92C
0x18001d920  call    ?WDiagFreeMem@@YAXPEAX@Z; WDiagFreeMem(void *)
0x18001d925  mov     [rbx+260h], r14
0x18001d92c  mov     rcx, [rbx+268h]; lpMem
0x18001d933  test    rcx, rcx
0x18001d936  jz      short loc_18001D944
0x18001d938  call    ?WDiagFreeMem@@YAXPEAX@Z; WDiagFreeMem(void *)
0x18001d93d  mov     [rbx+268h], r14
0x18001d944  mov     eax, [rsi+0A8h]
0x18001d94a  cmp     eax, 5
0x18001d94d  jbe     loc_18001DA5C
0x18001d953  mov     rbx, [rsi+40h]
0x18001d957  lea     r15d, [rax-5]
0x18001d95b  lea     rbp, [rsi+38h]
0x18001d95f  jmp     loc_18001D9F4
0x18001d964  cmp     [rbx+498h], r15d
0x18001d96b  ja      loc_18001DA5C
0x18001d971  lea     r14, [rbx+0F50h]
0x18001d978  mov     r9d, 4A5h; unsigned int
0x18001d97e  mov     rdx, r14; struct _WDIAG_RW_LOCK *
0x18001d981  mov     r8, r13; char *
0x18001d984  mov     rcx, rbx; void *
0x18001d987  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d98c  cmp     dword ptr [rbx+10h], 4E4E4F43h
0x18001d993  mov     r8, r13; char *
0x18001d996  mov     rdx, r14; struct _WDIAG_RW_LOCK *
0x18001d999  mov     rcx, rbx; void *
0x18001d99c  jnz     short loc_18001D9E5
0x18001d99e  mov     r9d, 4ABh; unsigned int
0x18001d9a4  mov     dword ptr [rbx+10h], 324E4F43h
0x18001d9ab  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d9b0  mov     r9d, 4ACh; unsigned int
0x18001d9b6  mov     r8, r13; char *
0x18001d9b9  mov     rdx, rdi; struct _WDIAG_RW_LOCK *
0x18001d9bc  mov     rcx, rsi; void *
0x18001d9bf  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d9c4  mov     rcx, rbx; struct _WD_CONNECTION_CONTEXT *
0x18001d9c7  call    ?WDiagDereferenceConnection@@YAXPEAU_WD_CONNECTION_CONTEXT@@K@Z; WDiagDereferenceConnection(_WD_CONNECTION_CONTEXT *,ulong)
0x18001d9cc  mov     r9d, 4B3h; unsigned int
0x18001d9d2  mov     r8, r13; char *
0x18001d9d5  mov     rdx, rdi; struct _WDIAG_RW_LOCK *
0x18001d9d8  mov     rcx, rsi; void *
0x18001d9db  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d9e0  mov     rbx, rbp
0x18001d9e3  jmp     short loc_18001D9F0
0x18001d9e5  mov     r9d, 4B8h; unsigned int
0x18001d9eb  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001d9f0  mov     rbx, [rbx+8]
0x18001d9f4  cmp     rbx, rbp
0x18001d9f7  jnz     loc_18001D964
0x18001d9fd  jmp     short loc_18001DA5C
0x18001d9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da06  lea     r12, WPP_GLOBAL_Control
0x18001da0d  cmp     rcx, r12
0x18001da10  jz      short loc_18001DA3C
0x18001da12  cmp     byte ptr [rcx+0E1h], 3
0x18001da19  jb      short loc_18001DA3C
0x18001da1b  test    [rcx+0E4h], r15b
0x18001da22  jz      short loc_18001DA3C
0x18001da24  mov     rcx, [rcx+0D8h]
0x18001da2b  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001da32  mov     edx, 42h ; 'B'
0x18001da37  call    WPP_SF_
0x18001da3c  lea     rbx, [rsi+0B0h]
0x18001da43  mov     rcx, rbx; lpFileTime
0x18001da46  call    ?WDiagGetTime@@YAKPEAU_FILETIME@@@Z; WDiagGetTime(_FILETIME *)
0x18001da4b  mov     dword ptr [rsi+0A8h], 1
0x18001da55  mov     dword ptr [rbx+10h], 1
0x18001da5c  mov     r9d, 4C8h; unsigned int
0x18001da62  mov     r8, r13; char *
0x18001da65  mov     rdx, rdi; struct _WDIAG_RW_LOCK *
0x18001da68  mov     rcx, rsi; void *
0x18001da6b  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18001da70  jmp     short loc_18001DA79
0x18001da72  lea     r12, WPP_GLOBAL_Control
0x18001da79  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da80  cmp     rcx, r12
0x18001da83  jz      short loc_18001DAA9
0x18001da85  test    dword ptr [rcx+0E4h], 200h
0x18001da8f  jz      short loc_18001DAA9
0x18001da91  mov     rcx, [rcx+0D8h]
0x18001da98  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001da9f  mov     edx, 43h ; 'C'
0x18001daa4  call    WPP_SF_
0x18001daa9  xor     eax, eax
0x18001daab  add     rsp, 68h
0x18001daaf  pop     r15
0x18001dab1  pop     r14
0x18001dab3  pop     r13
0x18001dab5  pop     r12
0x18001dab7  pop     rdi
0x18001dab8  pop     rsi
0x18001dab9  pop     rbp
0x18001daba  pop     rbx
0x18001dabb  retn
```
