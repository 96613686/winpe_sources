# WDiagMsmAssocComplete(_WD_INTERFACE_CONTEXT *,_WLAN_ASSOC_NOTIFICATION_DATA *)

- ea: `0x18002a7e8`
- end: `0x18002ac7d`
- name: `?WDiagMsmAssocComplete@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAU_WLAN_ASSOC_NOTIFICATION_DATA@@@Z`
- size: `1173`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *, struct _WLAN_ASSOC_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001226c`

## callees

- `0x180011530`
- `0x18001e950`
- `0x18002a7e8`
- `0x18002c96c`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a977`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a977`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a9a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a837`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a844`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a8b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a844`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a82b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a82b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a816`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002a816`

## string_xrefs

- `0x18002a84e`: `WDiagMsmAssocComplete`
- `0x18002a8cb`: `WDiagMsmAssocComplete`
- `0x18002a95e`: `WDiagMsmAssocComplete`
- `0x18002aaf3`: `WDiagMsmAssocComplete`
- `0x18002ab9c`: `WDiagMsmAssocComplete`

## pseudocode

```c
__int64 __fastcall WDiagMsmAssocComplete(struct _WD_INTERFACE_CONTEXT *a1, struct _WLAN_ASSOC_NOTIFICATION_DATA *a2)
{
  DWORD CurrentThreadId; // edi
  struct _PM_PROFILE *v5; // r8
  struct _DOT11_SSID *v6; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v8; // rsi
  char *v9; // rdi
  DWORD v10; // r15d
  int v11; // ecx
  PVOID *v12; // rcx
  unsigned int v13; // ebx
  char v15; // al
  char v16; // al
  enum _DOT11_BSS_TYPE v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+28h] [rbp-80h]
  ULONGLONG TickCount64; // [rsp+B0h] [rbp+8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 110, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  TickCount64 = GetTickCount64();
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
      (__int64)"WDiagMsmAssocComplete",
      103);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 2407;
  *((_QWORD *)a1 + 433) = "WDiagMsmAssocComplete";
  MatchingConnection = FindMatchingConnection(a1, *((void **)a1 + 6), v5, v6, v17, 1u, 2u);
  v8 = MatchingConnection;
  if ( MatchingConnection )
  {
    v9 = (char *)MatchingConnection + 3920;
    v10 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    WaitForSingleObject(*((HANDLE *)v9 + 11), 0xFFFFFFFF);
    if ( (v9[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v9,
        *((_DWORD *)v9 + 26),
        *((_QWORD *)v9 + 14),
        *((_DWORD *)v9 + 27),
        v10,
        (__int64)"WDiagMsmAssocComplete",
        122);
    }
    *((_DWORD *)v9 + 24) |= 4u;
    *((_QWORD *)v9 + 14) = "WDiagMsmAssocComplete";
    *((_DWORD *)v9 + 26) = v10;
    *((_DWORD *)v9 + 27) = 2426;
    ++*((_DWORD *)v8 + 371);
    *((_QWORD *)v8 + 183) = TickCount64;
    *(_DWORD *)((char *)v8 + 1478) = *((_DWORD *)a2 + 10);
    *((_WORD *)v8 + 741) = *((_WORD *)a2 + 22);
    *((_DWORD *)v8 + 372) = *((_DWORD *)a2 + 12);
    v11 = (_DWORD)zeroMac - *((_DWORD *)v8 + 368);
    if ( (_DWORD)zeroMac == *((_DWORD *)v8 + 368) )
      v11 = -*((unsigned __int16 *)v8 + 738);
    if ( !v11 )
    {
      *((_DWORD *)v8 + 368) = *((_DWORD *)a2 + 10);
      *((_WORD *)v8 + 738) = *((_WORD *)a2 + 22);
      *((_DWORD *)v8 + 373) = *((_DWORD *)a2 + 12);
    }
    if ( (v9[96] & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v15 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v9,
        v18,
        *((_QWORD *)v9 + 16),
        *((_DWORD *)v9 + 30),
        v15,
        (__int64)"WDiagMsmAssocComplete",
        137);
    }
    *((_DWORD *)v9 + 30) = 2441;
    *((_DWORD *)v9 + 24) &= ~4u;
    *((_QWORD *)v9 + 16) = "WDiagMsmAssocComplete";
    *((_DWORD *)v9 + 26) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v16 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v18,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v16,
        (__int64)"WDiagMsmAssocComplete",
        138);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 2442;
    *((_QWORD *)a1 + 435) = "WDiagMsmAssocComplete";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v13 = 0;
  }
  else
  {
    WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagMsmAssocComplete", 0x972u);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 111, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = 1168;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 57) & 0x200) != 0 )
    WPP_SF_(v12[27], 112, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v13;
}

```

## disassembly

```asm
0x18002a7e8  push    rbx
0x18002a7ea  push    rbp
0x18002a7eb  push    rsi
0x18002a7ec  push    rdi
0x18002a7ed  push    r12
0x18002a7ef  push    r13
0x18002a7f1  push    r14
0x18002a7f3  push    r15
0x18002a7f5  sub     rsp, 68h
0x18002a7f9  mov     r14, rdx
0x18002a7fc  mov     rbp, rcx
0x18002a7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a806  lea     r15, WPP_GLOBAL_Control
0x18002a80d  cmp     rcx, r15
0x18002a810  jnz     loc_18002A9D0
0x18002a816  call    cs:__imp_GetTickCount64
0x18002a81c  mov     [rsp+0A8h+arg_0], rax
0x18002a824  lea     rbx, [rbp+0D18h]
0x18002a82b  call    cs:__imp_GetCurrentThreadId
0x18002a831  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a835  mov     edi, eax
0x18002a837  call    cs:__imp_EnterCriticalSection
0x18002a83d  mov     rcx, [rbx+58h]; hHandle
0x18002a841  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a844  call    cs:__imp_WaitForSingleObject
0x18002a84a  test    byte ptr [rbx+60h], 4
0x18002a84e  lea     r12, aWdiagmsmassocc; "WDiagMsmAssocComplete"
0x18002a855  mov     esi, 967h
0x18002a85a  jnz     loc_18002A9FD
0x18002a860  or      dword ptr [rbx+60h], 4
0x18002a864  mov     rcx, rbp; struct _WD_INTERFACE_CONTEXT *
0x18002a867  mov     [rbx+68h], edi
0x18002a86a  mov     [rbx+6Ch], esi
0x18002a86d  mov     [rbx+70h], r12
0x18002a871  mov     rdx, [rbp+30h]; void *
0x18002a875  mov     [rsp+0A8h+var_78], 2; unsigned int
0x18002a87d  mov     dword ptr [rsp+0A8h+var_80], 1; int
0x18002a885  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x18002a88a  mov     rsi, rax
0x18002a88d  test    rax, rax
0x18002a890  jz      loc_18002AA64
0x18002a896  lea     rdi, [rax+0F50h]
0x18002a89d  call    cs:__imp_GetCurrentThreadId
0x18002a8a3  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a8a7  mov     r15d, eax
0x18002a8aa  call    cs:__imp_EnterCriticalSection
0x18002a8b0  mov     rcx, [rdi+58h]; hHandle
0x18002a8b4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a8b7  call    cs:__imp_WaitForSingleObject
0x18002a8bd  test    byte ptr [rdi+60h], 4
0x18002a8c1  jnz     loc_18002AABF
0x18002a8c7  or      dword ptr [rdi+60h], 4
0x18002a8cb  lea     rax, aWdiagmsmassocc; "WDiagMsmAssocComplete"
0x18002a8d2  mov     [rdi+70h], rax
0x18002a8d6  mov     rax, [rsp+0A8h+arg_0]
0x18002a8de  mov     [rdi+68h], r15d
0x18002a8e2  mov     dword ptr [rdi+6Ch], 97Ah
0x18002a8e9  inc     dword ptr [rsi+5CCh]
0x18002a8ef  mov     [rsi+5B8h], rax
0x18002a8f6  mov     eax, [r14+28h]
0x18002a8fa  mov     [rsi+5C6h], eax
0x18002a900  movzx   eax, word ptr [r14+2Ch]
0x18002a905  mov     [rsi+5CAh], ax
0x18002a90c  mov     eax, [r14+30h]
0x18002a910  mov     [rsi+5D0h], eax
0x18002a916  mov     ecx, cs:?zeroMac@@3QBEB; uchar const near * const zeroMac
0x18002a91c  sub     ecx, [rsi+5C0h]
0x18002a922  jnz     short loc_18002A934
0x18002a924  movzx   ecx, cs:word_180244238
0x18002a92b  movzx   eax, word ptr [rsi+5C4h]
0x18002a932  sub     ecx, eax
0x18002a934  test    ecx, ecx
0x18002a936  jz      loc_18002AB39
0x18002a93c  test    byte ptr [rdi+60h], 4
0x18002a940  jz      loc_18002AB5E
0x18002a946  lea     r15, WPP_GLOBAL_Control
0x18002a94d  mov     r14d, 0FFFFFFFBh
0x18002a953  mov     dword ptr [rdi+78h], 989h
0x18002a95a  and     [rdi+60h], r14d
0x18002a95e  lea     rsi, aWdiagmsmassocc; "WDiagMsmAssocComplete"
0x18002a965  lea     rcx, [rdi+8]; lpCriticalSection
0x18002a969  mov     [rdi+80h], rsi
0x18002a970  mov     dword ptr [rdi+68h], 0
0x18002a977  call    cs:__imp_LeaveCriticalSection
0x18002a97d  test    byte ptr [rbx+60h], 4
0x18002a981  mov     edi, 98Ah
0x18002a986  jz      loc_18002ABE0
0x18002a98c  and     [rbx+60h], r14d
0x18002a990  lea     rcx, [rbx+8]; lpCriticalSection
0x18002a994  mov     [rbx+78h], edi
0x18002a997  mov     [rbx+80h], rsi
0x18002a99e  mov     dword ptr [rbx+68h], 0
0x18002a9a5  call    cs:__imp_LeaveCriticalSection
0x18002a9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9b2  xor     ebx, ebx
0x18002a9b4  cmp     rcx, r15
0x18002a9b7  jnz     loc_18002AC50
0x18002a9bd  mov     eax, ebx
0x18002a9bf  add     rsp, 68h
0x18002a9c3  pop     r15
0x18002a9c5  pop     r14
0x18002a9c7  pop     r13
0x18002a9c9  pop     r12
0x18002a9cb  pop     rdi
0x18002a9cc  pop     rsi
0x18002a9cd  pop     rbp
0x18002a9ce  pop     rbx
0x18002a9cf  retn
0x18002a9d0  test    dword ptr [rcx+0E4h], 200h
0x18002a9da  jz      loc_18002A816
0x18002a9e0  mov     rcx, [rcx+0D8h]
0x18002a9e7  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002a9ee  mov     edx, 6Eh ; 'n'
0x18002a9f3  call    WPP_SF_
0x18002a9f8  jmp     loc_18002A816
0x18002a9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa04  cmp     rcx, r15
0x18002aa07  jz      loc_18002A860
0x18002aa0d  cmp     byte ptr [rcx+0E1h], 1
0x18002aa14  jb      loc_18002A860
0x18002aa1a  test    byte ptr [rcx+0E4h], 40h
0x18002aa21  jz      loc_18002A860
0x18002aa27  mov     eax, [rbx+6Ch]
0x18002aa2a  mov     r9, rbp
0x18002aa2d  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002aa34  mov     dword ptr [rsp+0A8h+var_58], esi; char
0x18002aa38  mov     [rsp+0A8h+var_60], r12; __int64
0x18002aa3d  mov     dword ptr [rsp+0A8h+var_68], edi; char
0x18002aa41  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002aa45  mov     rax, [rbx+70h]
0x18002aa49  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002aa4e  mov     eax, [rbx+68h]
0x18002aa51  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x18002aa55  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x18002aa5a  call    WPP_SF_qqdsddsd
0x18002aa5f  jmp     loc_18002A860
0x18002aa64  mov     r9d, 972h; unsigned int
0x18002aa6a  mov     r8, r12; char *
0x18002aa6d  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x18002aa70  mov     rcx, rbp; void *
0x18002aa73  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002aa78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa7f  cmp     rcx, r15
0x18002aa82  jz      short loc_18002AAB5
0x18002aa84  cmp     byte ptr [rcx+0E1h], 1
0x18002aa8b  jb      short loc_18002AAB5
0x18002aa8d  test    byte ptr [rcx+0E4h], 10h
0x18002aa94  jz      short loc_18002AAB5
0x18002aa96  mov     rcx, [rcx+0D8h]
0x18002aa9d  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002aaa4  mov     edx, 6Fh ; 'o'
0x18002aaa9  call    WPP_SF_
0x18002aaae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aab5  mov     ebx, 490h
0x18002aaba  jmp     loc_18002A9B4
0x18002aabf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aac6  lea     rax, WPP_GLOBAL_Control
0x18002aacd  cmp     rcx, rax
0x18002aad0  jz      loc_18002A8C7
0x18002aad6  cmp     byte ptr [rcx+0E1h], 1
0x18002aadd  jb      loc_18002A8C7
0x18002aae3  test    byte ptr [rcx+0E4h], 40h
0x18002aaea  jz      loc_18002A8C7
0x18002aaf0  mov     eax, [rdi+6Ch]
0x18002aaf3  lea     rdx, aWdiagmsmassocc; "WDiagMsmAssocComplete"
0x18002aafa  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002ab01  mov     r9, rsi
0x18002ab04  mov     dword ptr [rsp+0A8h+var_58], 97Ah; char
0x18002ab0c  mov     [rsp+0A8h+var_60], rdx; __int64
0x18002ab11  mov     dword ptr [rsp+0A8h+var_68], r15d; char
0x18002ab16  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002ab1a  mov     rax, [rdi+70h]
0x18002ab1e  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002ab23  mov     eax, [rdi+68h]
0x18002ab26  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x18002ab2a  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18002ab2f  call    WPP_SF_qqdsddsd
0x18002ab34  jmp     loc_18002A8C7
0x18002ab39  mov     eax, [r14+28h]
0x18002ab3d  mov     [rsi+5C0h], eax
0x18002ab43  movzx   eax, word ptr [r14+2Ch]
0x18002ab48  mov     [rsi+5C4h], ax
0x18002ab4f  mov     eax, [r14+30h]
0x18002ab53  mov     [rsi+5D4h], eax
0x18002ab59  jmp     loc_18002A93C
0x18002ab5e  mov     rax, cs:WPP_GLOBAL_Control
0x18002ab65  lea     r15, WPP_GLOBAL_Control
0x18002ab6c  cmp     rax, r15
0x18002ab6f  jz      loc_18002A94D
0x18002ab75  cmp     byte ptr [rax+0E1h], 1
0x18002ab7c  jb      loc_18002A94D
0x18002ab82  test    byte ptr [rax+0E4h], 40h
0x18002ab89  jz      loc_18002A94D
0x18002ab8f  call    cs:__imp_GetCurrentThreadId
0x18002ab95  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab9c  lea     rdx, aWdiagmsmassocc; "WDiagMsmAssocComplete"
0x18002aba3  mov     dword ptr [rsp+0A8h+var_58], 989h; char
0x18002abab  mov     r9, rsi
0x18002abae  mov     [rsp+0A8h+var_60], rdx; __int64
0x18002abb3  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002abb7  mov     eax, [rdi+78h]
0x18002abba  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002abc1  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002abc5  mov     rax, [rdi+80h]
0x18002abcc  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002abd1  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x18002abd6  call    WPP_SF_qqDsdDsd
0x18002abdb  jmp     loc_18002A94D
0x18002abe0  mov     rax, cs:WPP_GLOBAL_Control
0x18002abe7  cmp     rax, r15
0x18002abea  jz      loc_18002A98C
0x18002abf0  cmp     byte ptr [rax+0E1h], 1
0x18002abf7  jb      loc_18002A98C
0x18002abfd  test    byte ptr [rax+0E4h], 40h
0x18002ac04  jz      loc_18002A98C
0x18002ac0a  call    cs:__imp_GetCurrentThreadId
0x18002ac10  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac17  mov     r9, rbp
0x18002ac1a  mov     dword ptr [rsp+0A8h+var_58], edi; char
0x18002ac1e  mov     [rsp+0A8h+var_60], rsi; __int64
0x18002ac23  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002ac27  mov     eax, [rbx+78h]
0x18002ac2a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18002ac31  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x18002ac35  mov     rax, [rbx+80h]
0x18002ac3c  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x18002ac41  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x18002ac46  call    WPP_SF_qqDsdDsd
0x18002ac4b  jmp     loc_18002A98C
0x18002ac50  test    dword ptr [rcx+0E4h], 200h
0x18002ac5a  jz      loc_18002A9BD
0x18002ac60  mov     rcx, [rcx+0D8h]
0x18002ac67  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18002ac6e  mov     edx, 70h ; 'p'
0x18002ac73  call    WPP_SF_
0x18002ac78  jmp     loc_18002A9BD
```
