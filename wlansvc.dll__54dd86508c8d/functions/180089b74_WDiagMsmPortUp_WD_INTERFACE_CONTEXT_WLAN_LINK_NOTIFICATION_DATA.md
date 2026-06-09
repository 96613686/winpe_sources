# WDiagMsmPortUp(_WD_INTERFACE_CONTEXT *,_WLAN_LINK_NOTIFICATION_DATA *)

- ea: `0x180089b74`
- end: `0x180089eef`
- name: `?WDiagMsmPortUp@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAU_WLAN_LINK_NOTIFICATION_DATA@@@Z`
- size: `891`
- prototype: `unsigned int __fastcall(struct _WD_INTERFACE_CONTEXT *, struct _WLAN_LINK_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001226c`

## callees

- `0x180011530`
- `0x18001e950`
- `0x18002c96c`
- `0x180089b74`
- `0x1801c81ac`
- `0x1801c82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089e1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089ea4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089e1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180089ea4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089bd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089cf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089bd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180089cf2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089be2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089cff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089be2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089ce5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089ce5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089e4b`

## pseudocode

```c
__int64 __fastcall WDiagMsmPortUp(struct _WD_INTERFACE_CONTEXT *a1, void **a2)
{
  DWORD CurrentThreadId; // edi
  struct _PM_PROFILE *v5; // r8
  struct _DOT11_SSID *v6; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rax
  struct _WD_CONNECTION_CONTEXT *v8; // rsi
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  char *v11; // rdi
  DWORD v12; // r14d
  char v13; // al
  char v14; // al
  enum _DOT11_BSS_TYPE v16; // [rsp+20h] [rbp-88h]
  int v17; // [rsp+28h] [rbp-80h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 99, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
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
      (__int64)"WDiagMsmPortUp",
      189);
  }
  *((_DWORD *)a1 + 862) |= 4u;
  *((_DWORD *)a1 + 864) = CurrentThreadId;
  *((_DWORD *)a1 + 865) = 2237;
  *((_QWORD *)a1 + 433) = "WDiagMsmPortUp";
  MatchingConnection = FindMatchingConnection(a1, a2[1], v5, v6, v16, 1u, 2u);
  v8 = MatchingConnection;
  if ( MatchingConnection )
  {
    v11 = (char *)MatchingConnection + 3920;
    v12 = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
    WaitForSingleObject(*((HANDLE *)v11 + 11), 0xFFFFFFFF);
    if ( (v11[96] & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v11,
        *((_DWORD *)v11 + 26),
        *((_QWORD *)v11 + 14),
        *((_DWORD *)v11 + 27),
        v12,
        (__int64)"WDiagMsmPortUp",
        206);
    }
    *((_DWORD *)v11 + 24) |= 4u;
    *((_DWORD *)v11 + 26) = v12;
    *((_QWORD *)v11 + 14) = "WDiagMsmPortUp";
    *((_DWORD *)v11 + 27) = 2254;
    *(_QWORD *)((char *)v8 + 44) = 0;
    *((_QWORD *)v8 + 216) = 0;
    if ( (v11[96] & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v13 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (char)v11,
        v17,
        *((_QWORD *)v11 + 16),
        *((_DWORD *)v11 + 30),
        v13,
        (__int64)"WDiagMsmPortUp",
        216);
    }
    *((_DWORD *)v11 + 26) = 0;
    *((_DWORD *)v11 + 24) &= ~4u;
    *((_DWORD *)v11 + 30) = 2264;
    *((_QWORD *)v11 + 16) = "WDiagMsmPortUp";
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v14 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v17,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v14,
        (__int64)"WDiagMsmPortUp",
        217);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 2265;
    *((_QWORD *)a1 + 435) = "WDiagMsmPortUp";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 0;
  }
  else
  {
    WDiagReleaseExLock(a1, (struct _WD_INTERFACE_CONTEXT *)((char *)a1 + 3352), "WDiagMsmPortUp", 0x8C6u);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 100, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = 1168;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 57) & 0x200) != 0 )
    WPP_SF_(v9[27], 101, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v10;
}

```

## disassembly

```asm
0x180089b74  push    rbx
0x180089b76  push    rbp
0x180089b77  push    rsi
0x180089b78  push    rdi
0x180089b79  push    r12
0x180089b7b  push    r13
0x180089b7d  push    r14
0x180089b7f  push    r15
0x180089b81  sub     rsp, 68h
0x180089b85  mov     rsi, rdx
0x180089b88  mov     rbp, rcx
0x180089b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b92  lea     r13, WPP_GLOBAL_Control
0x180089b99  cmp     rcx, r13
0x180089b9c  jz      short loc_180089BC2
0x180089b9e  test    dword ptr [rcx+0E4h], 200h
0x180089ba8  jz      short loc_180089BC2
0x180089baa  mov     rcx, [rcx+0D8h]
0x180089bb1  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x180089bb8  mov     edx, 63h ; 'c'
0x180089bbd  call    WPP_SF_
0x180089bc2  lea     rbx, [rbp+0D18h]
0x180089bc9  call    cs:__imp_GetCurrentThreadId
0x180089bcf  lea     rcx, [rbx+8]; lpCriticalSection
0x180089bd3  mov     edi, eax
0x180089bd5  call    cs:__imp_EnterCriticalSection
0x180089bdb  mov     rcx, [rbx+58h]; hHandle
0x180089bdf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180089be2  call    cs:__imp_WaitForSingleObject
0x180089be8  test    byte ptr [rbx+60h], 4
0x180089bec  lea     r14, aWdiagmsmportup; "WDiagMsmPortUp"
0x180089bf3  mov     r15d, 8BDh
0x180089bf9  jz      short loc_180089C52
0x180089bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180089c02  cmp     rcx, r13
0x180089c05  jz      short loc_180089C52
0x180089c07  cmp     byte ptr [rcx+0E1h], 1
0x180089c0e  jb      short loc_180089C52
0x180089c10  test    byte ptr [rcx+0E4h], 40h
0x180089c17  jz      short loc_180089C52
0x180089c19  mov     eax, [rbx+6Ch]
0x180089c1c  mov     r9, rbp
0x180089c1f  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180089c26  mov     dword ptr [rsp+0A8h+var_58], r15d; char
0x180089c2b  mov     [rsp+0A8h+var_60], r14; __int64
0x180089c30  mov     dword ptr [rsp+0A8h+var_68], edi; char
0x180089c34  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180089c38  mov     rax, [rbx+70h]
0x180089c3c  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180089c41  mov     eax, [rbx+68h]
0x180089c44  mov     dword ptr [rsp+0A8h+var_80], eax; char
0x180089c48  mov     qword ptr [rsp+0A8h+var_88], rbx; enum _DOT11_BSS_TYPE
0x180089c4d  call    WPP_SF_qqdsddsd
0x180089c52  or      dword ptr [rbx+60h], 4
0x180089c56  mov     rcx, rbp; struct _WD_INTERFACE_CONTEXT *
0x180089c59  mov     [rbx+68h], edi
0x180089c5c  mov     [rbx+6Ch], r15d
0x180089c60  mov     [rbx+70h], r14
0x180089c64  mov     rdx, [rsi+8]; void *
0x180089c68  mov     [rsp+0A8h+var_78], 2; unsigned int
0x180089c70  mov     dword ptr [rsp+0A8h+var_80], 1; unsigned int
0x180089c78  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x180089c7d  mov     rsi, rax
0x180089c80  test    rax, rax
0x180089c83  jnz     short loc_180089CDE
0x180089c85  mov     r9d, 8C6h; unsigned int
0x180089c8b  mov     r8, r14; char *
0x180089c8e  mov     rdx, rbx; struct _WDIAG_RW_LOCK *
0x180089c91  mov     rcx, rbp; void *
0x180089c94  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x180089c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180089ca0  cmp     rcx, r13
0x180089ca3  jz      short loc_180089CD4
0x180089ca5  cmp     byte ptr [rcx+0E1h], 1
0x180089cac  jb      short loc_180089CD4
0x180089cae  test    byte ptr [rcx+0E4h], 10h
0x180089cb5  jz      short loc_180089CD4
0x180089cb7  mov     rcx, [rcx+0D8h]
0x180089cbe  lea     edx, [rsi+64h]
0x180089cc1  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x180089cc8  call    WPP_SF_
0x180089ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180089cd4  mov     ebx, 490h
0x180089cd9  jmp     loc_180089EB3
0x180089cde  lea     rdi, [rax+0F50h]
0x180089ce5  call    cs:__imp_GetCurrentThreadId
0x180089ceb  lea     rcx, [rdi+8]; lpCriticalSection
0x180089cef  mov     r14d, eax
0x180089cf2  call    cs:__imp_EnterCriticalSection
0x180089cf8  mov     rcx, [rdi+58h]; hHandle
0x180089cfc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180089cff  call    cs:__imp_WaitForSingleObject
0x180089d05  test    byte ptr [rdi+60h], 4
0x180089d09  jz      short loc_180089D6D
0x180089d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180089d12  cmp     rcx, r13
0x180089d15  jz      short loc_180089D6D
0x180089d17  cmp     byte ptr [rcx+0E1h], 1
0x180089d1e  jb      short loc_180089D6D
0x180089d20  test    byte ptr [rcx+0E4h], 40h
0x180089d27  jz      short loc_180089D6D
0x180089d29  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180089d30  lea     rax, aWdiagmsmportup; "WDiagMsmPortUp"
0x180089d37  mov     dword ptr [rsp+0A8h+var_58], 8CEh; char
0x180089d3f  mov     r9, rsi
0x180089d42  mov     [rsp+0A8h+var_60], rax; __int64
0x180089d47  mov     eax, [rdi+6Ch]
0x180089d4a  mov     dword ptr [rsp+0A8h+var_68], r14d; char
0x180089d4f  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180089d53  mov     rax, [rdi+70h]
0x180089d57  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180089d5c  mov     eax, [rdi+68h]
0x180089d5f  mov     dword ptr [rsp+0A8h+var_80], eax; int
0x180089d63  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x180089d68  call    WPP_SF_qqdsddsd
0x180089d6d  or      dword ptr [rdi+60h], 4
0x180089d71  xor     ecx, ecx
0x180089d73  mov     [rdi+68h], r14d
0x180089d77  lea     r14, aWdiagmsmportup; "WDiagMsmPortUp"
0x180089d7e  mov     [rdi+70h], r14
0x180089d82  mov     dword ptr [rdi+6Ch], 8CEh
0x180089d89  mov     [rsi+2Ch], rcx
0x180089d8d  mov     [rsi+6C0h], rcx
0x180089d94  test    byte ptr [rdi+60h], 4
0x180089d98  jnz     short loc_180089DFF
0x180089d9a  mov     rax, cs:WPP_GLOBAL_Control
0x180089da1  cmp     rax, r13
0x180089da4  jz      short loc_180089DFF
0x180089da6  cmp     byte ptr [rax+0E1h], 1
0x180089dad  jb      short loc_180089DFF
0x180089daf  test    byte ptr [rax+0E4h], 40h
0x180089db6  jz      short loc_180089DFF
0x180089db8  call    cs:__imp_GetCurrentThreadId
0x180089dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180089dc5  mov     r9, rsi
0x180089dc8  mov     dword ptr [rsp+0A8h+var_58], 8D8h; char
0x180089dd0  mov     [rsp+0A8h+var_60], r14; __int64
0x180089dd5  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180089dd9  mov     eax, [rdi+78h]
0x180089ddc  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180089de3  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180089de7  mov     rax, [rdi+80h]
0x180089dee  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180089df3  mov     qword ptr [rsp+0A8h+var_88], rdi; char
0x180089df8  call    WPP_SF_qqDsdDsd
0x180089dfd  xor     ecx, ecx
0x180089dff  mov     [rdi+68h], ecx
0x180089e02  mov     esi, 0FFFFFFFBh
0x180089e07  and     [rdi+60h], esi
0x180089e0a  lea     rcx, [rdi+8]; lpCriticalSection
0x180089e0e  mov     dword ptr [rdi+78h], 8D8h
0x180089e15  mov     [rdi+80h], r14
0x180089e1c  call    cs:__imp_LeaveCriticalSection
0x180089e22  test    byte ptr [rbx+60h], 4
0x180089e26  mov     edi, 8D9h
0x180089e2b  jnz     short loc_180089E8C
0x180089e2d  mov     rax, cs:WPP_GLOBAL_Control
0x180089e34  cmp     rax, r13
0x180089e37  jz      short loc_180089E8C
0x180089e39  cmp     byte ptr [rax+0E1h], 1
0x180089e40  jb      short loc_180089E8C
0x180089e42  test    byte ptr [rax+0E4h], 40h
0x180089e49  jz      short loc_180089E8C
0x180089e4b  call    cs:__imp_GetCurrentThreadId
0x180089e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180089e58  mov     r9, rbp
0x180089e5b  mov     dword ptr [rsp+0A8h+var_58], edi; char
0x180089e5f  mov     [rsp+0A8h+var_60], r14; __int64
0x180089e64  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180089e68  mov     eax, [rbx+78h]
0x180089e6b  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180089e72  mov     dword ptr [rsp+0A8h+var_70], eax; char
0x180089e76  mov     rax, [rbx+80h]
0x180089e7d  mov     qword ptr [rsp+0A8h+var_78], rax; __int64
0x180089e82  mov     qword ptr [rsp+0A8h+var_88], rbx; char
0x180089e87  call    WPP_SF_qqDsdDsd
0x180089e8c  and     [rbx+60h], esi
0x180089e8f  lea     rcx, [rbx+8]; lpCriticalSection
0x180089e93  mov     [rbx+78h], edi
0x180089e96  mov     [rbx+80h], r14
0x180089e9d  mov     dword ptr [rbx+68h], 0
0x180089ea4  call    cs:__imp_LeaveCriticalSection
0x180089eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180089eb1  xor     ebx, ebx
0x180089eb3  cmp     rcx, r13
0x180089eb6  jz      short loc_180089EDC
0x180089eb8  test    dword ptr [rcx+0E4h], 200h
0x180089ec2  jz      short loc_180089EDC
0x180089ec4  mov     rcx, [rcx+0D8h]
0x180089ecb  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x180089ed2  mov     edx, 65h ; 'e'
0x180089ed7  call    WPP_SF_
0x180089edc  mov     eax, ebx
0x180089ede  add     rsp, 68h
0x180089ee2  pop     r15
0x180089ee4  pop     r14
0x180089ee6  pop     r13
0x180089ee8  pop     r12
0x180089eea  pop     rdi
0x180089eeb  pop     rsi
0x180089eec  pop     rbp
0x180089eed  pop     rbx
0x180089eee  retn
```
