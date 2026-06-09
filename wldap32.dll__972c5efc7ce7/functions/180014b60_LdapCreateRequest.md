# LdapCreateRequest

- ea: `0x180014b60`
- end: `0x1800151a9`
- name: `LdapCreateRequest`
- size: `1609`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012ab0`
- `0x180015640`
- `0x1800164a0`
- `0x1800308f8`
- `0x180039f4c`
- `0x18003c254`
- `0x18003e250`
- `0x18003edf4`
- `0x180040440`
- `0x180046f48`
- `0x1800491d4`

## callees

- `0x1800037a8`
- `0x18000a280`
- `0x18000adb0`
- `0x18000b440`
- `0x180014b60`
- `0x1800151b0`
- `0x180015338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ff6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001504f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014cae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ff6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001504f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014fcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001501f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014fcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001501f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015151`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014c3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014bce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014bce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014d36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014d36`
- `ntdll!RtlReleaseResource` at `0x180014b9c`
- `ntdll!RtlReleaseResource` at `0x180014e73`
- `ntdll!RtlReleaseResource` at `0x180014ee9`
- `ntdll!RtlReleaseResource` at `0x1800150ab`
- `ntdll!RtlReleaseResource` at `0x180014b9c`
- `ntdll!RtlReleaseResource` at `0x180014e73`
- `ntdll!RtlReleaseResource` at `0x180014ee9`
- `ntdll!RtlReleaseResource` at `0x1800150ab`
- `ntdll!RtlAcquireResourceExclusive` at `0x180014b7c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180014dec`
- `ntdll!RtlAcquireResourceExclusive` at `0x180014b7c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180014dec`

## string_xrefs

- `0x180014f64`: `LdapCreateRequest could not allocate 0x%x bytes.\n`

## pseudocode

```c
struct _FILETIME __fastcall LdapCreateRequest(__int64 a1, char a2)
{
  _DWORD *v4; // rdi
  LPVOID v5; // rax
  struct _FILETIME v6; // rbx
  int v7; // ecx
  unsigned int v8; // eax
  int v9; // eax
  char v10; // al
  signed __int32 v11; // eax
  int v12; // esi
  struct _FILETIME *v13; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  signed __int32 v16; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+18h] BYREF

  RtlAcquireResourceExclusive(&RequestListLock, 1u);
  if ( GlobalRejectNewRequests )
  {
    RtlReleaseResource(&RequestListLock);
  }
  else
  {
    RtlReleaseResource(&RequestListLock);
    v4 = (_DWORD *)ReferenceLdapConnection(a1);
    if ( v4 )
    {
      v5 = HeapAlloc(LdapHeap, 8u, 0x120u);
      v6 = (struct _FILETIME)v5;
      SystemTimeAsFileTime = (struct _FILETIME)v5;
      v7 = g_fTracingOn;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      {
        LDAPClientPrint(
          8,
          "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
          288,
          (_DWORD)v5,
          1902465612);
        v7 = g_fTracingOn;
      }
      v8 = LdapAllocatedHeap;
      if ( v6 )
      {
        *(_DWORD *)v6.dwLowDateTime = 1902465612;
        *(_DWORD *)(*(_QWORD *)&v6 + 4LL) = 280;
        *(_QWORD *)&v6 += 8LL;
        SystemTimeAsFileTime = v6;
        v8 += 280;
        LdapAllocatedHeap = v8;
      }
      if ( v7 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      {
        LDAPClientPrint(
          8,
          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          280,
          v6.dwLowDateTime,
          1902465612,
          v8);
        v7 = g_fTracingOn;
      }
      if ( v6 )
      {
        *(_DWORD *)(*(_QWORD *)&v6 + 16LL) = 2;
        InitializeCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&v6 + 48LL));
        *(_QWORD *)(*(_QWORD *)&v6 + 32LL) = v4;
        *(_BYTE *)(*(_QWORD *)&v6 + 186LL) = a2;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(_QWORD *)(*(_QWORD *)&v6 + 88LL) = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x2710;
        *(_DWORD *)(*(_QWORD *)&v6 + 96LL) = v4[253];
        *(_DWORD *)(*(_QWORD *)&v6 + 100LL) = v4[254];
        *(_WORD *)(*(_QWORD *)&v6 + 178LL) = *((_WORD *)v4 + 540);
        *(_DWORD *)(*(_QWORD *)&v6 + 276LL) = 0;
        *(_BYTE *)(*(_QWORD *)&v6 + 189LL) = *((_BYTE *)v4 + 680);
        v9 = v4[271];
        if ( (v9 & 2) != 0 )
        {
          v10 = 96;
        }
        else if ( (v9 & 4) != 0 )
        {
          v10 = 0;
        }
        else
        {
          v10 = v9 & 0x60;
        }
        *(_BYTE *)(*(_QWORD *)&v6 + 185LL) = v10;
        *(_DWORD *)(*(_QWORD *)&v6 + 108LL) = 0;
        do
        {
          if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
          {
            EnterCriticalSection(&MessageNumberLock);
            if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
              GlobalMessageNumber = 0;
            LeaveCriticalSection(&MessageNumberLock);
          }
          v11 = _InterlockedIncrement(&GlobalMessageNumber);
          *(_DWORD *)(*(_QWORD *)&v6 + 108LL) = v11;
        }
        while ( (v11 & 0xFE000000) != 0 );
        v12 = 0;
        RtlAcquireResourceExclusive(&RequestListLock, 1u);
        while ( 1 )
        {
          if ( (unsigned __int8)IsMessageIdValid(*(unsigned int *)(*(_QWORD *)&v6 + 108LL)) )
          {
            StringCchPrintfA(
              (STRSAFE_LPSTR)(*(_QWORD *)&v6 + 112LL),
              0x25u,
              "MessageID_%lu",
              *(_DWORD *)(*(_QWORD *)&v6 + 108LL));
            v4[260] = *(_DWORD *)(*(_QWORD *)&v6 + 108LL);
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
              LDAPClientPrint(
                0x1000000,
                "LDAP creating request at 0x%x, connection is 0x%x.\n",
                v6.dwLowDateTime,
                (_DWORD)v4);
            v13 = (struct _FILETIME *)qword_180065BE8;
            **(_QWORD **)&v6 = &GlobalListRequests;
            *(_QWORD *)(*(_QWORD *)&v6 + 8LL) = v13;
            *v13 = v6;
            qword_180065BE8 = (__int64)v6;
            ++GlobalRequestCount;
            _InterlockedIncrement64(&qword_180066088);
            _InterlockedIncrement64(&qword_180066098);
            RtlReleaseResource(&RequestListLock);
            return v6;
          }
          if ( v12 >= 10 )
            break;
          *(_DWORD *)(*(_QWORD *)&v6 + 108LL) = 0;
          do
          {
            if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
            {
              EnterCriticalSection(&MessageNumberLock);
              if ( ((GlobalMessageNumber + 1) & 0xFE000000) != 0 )
                GlobalMessageNumber = 0;
              LeaveCriticalSection(&MessageNumberLock);
            }
            v16 = _InterlockedIncrement(&GlobalMessageNumber);
            *(_DWORD *)(*(_QWORD *)&v6 + 108LL) = v16;
          }
          while ( (v16 & 0xFE000000) != 0 );
          ++v12;
        }
        RtlReleaseResource(&RequestListLock);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x1000000) != 0 )
          LDAPClientPrint(
            0x1000000,
            "LDAP failed to allocate message number for request 0x%x, connection is 0x%x.\n",
            v6.dwLowDateTime,
            (_DWORD)v4);
        ((void (__fastcall *)(_QWORD, _QWORD))ldapFree)(v6, 1902465612);
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
        --*v4;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v4, *v4);
        v15 = (struct _RTL_CRITICAL_SECTION *)(v4 + 128);
        if ( !*v4 )
          goto LABEL_58;
      }
      else
      {
        if ( v7 && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
          LDAPClientPrint(0x4000, "LdapCreateRequest could not allocate 0x%x bytes.\n", 280);
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 128));
        --*v4;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
          LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v4, *v4);
        v15 = (struct _RTL_CRITICAL_SECTION *)(v4 + 128);
        if ( !*v4 )
        {
LABEL_58:
          LeaveCriticalSection(v15);
          DereferenceLdapConnection2((__int64)v4, 1);
          return 0;
        }
      }
      LeaveCriticalSection(v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014b60  mov     [rsp+arg_8], rbx
0x180014b65  push    rsi
0x180014b66  push    rdi
0x180014b67  push    r14
0x180014b69  sub     rsp, 30h
0x180014b6d  movzx   esi, dl
0x180014b70  mov     rbx, rcx
0x180014b73  mov     dl, 1; Wait
0x180014b75  lea     rcx, RequestListLock; Resource
0x180014b7c  call    cs:__imp_RtlAcquireResourceExclusive
0x180014b83  nop     dword ptr [rax+rax+00h]
0x180014b88  lea     rcx, RequestListLock; Resource
0x180014b8f  cmp     cs:GlobalRejectNewRequests, 0
0x180014b96  jnz     loc_180014EE9
0x180014b9c  call    cs:__imp_RtlReleaseResource
0x180014ba3  nop     dword ptr [rax+rax+00h]
0x180014ba8  mov     rcx, rbx
0x180014bab  call    ReferenceLdapConnection
0x180014bb0  mov     rdi, rax
0x180014bb3  test    rax, rax
0x180014bb6  jz      loc_180014EF5
0x180014bbc  mov     edx, 8; dwFlags
0x180014bc1  mov     r8d, 120h; dwBytes
0x180014bc7  mov     rcx, cs:LdapHeap; hHeap
0x180014bce  call    cs:__imp_HeapAlloc
0x180014bd5  nop     dword ptr [rax+rax+00h]
0x180014bda  mov     rbx, rax
0x180014bdd  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180014be2  mov     ecx, cs:g_fTracingOn
0x180014be8  test    ecx, ecx
0x180014bea  jnz     loc_180014EA2
0x180014bf0  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180014bf6  test    rbx, rbx
0x180014bf9  jz      short loc_180014C1C
0x180014bfb  mov     dword ptr [rbx], 7165524Ch
0x180014c01  mov     dword ptr [rbx+4], 118h
0x180014c08  add     rbx, 8
0x180014c0c  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180014c11  add     eax, 118h
0x180014c16  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180014c1c  test    ecx, ecx
0x180014c1e  jnz     loc_180014EF9
0x180014c24  test    rbx, rbx
0x180014c27  jz      loc_180014F44
0x180014c2d  mov     [rsp+48h+arg_0], rdi
0x180014c32  mov     dword ptr [rbx+10h], 2
0x180014c39  lea     rcx, [rbx+30h]; lpCriticalSection
0x180014c3d  call    cs:__imp_InitializeCriticalSection
0x180014c44  nop     dword ptr [rax+rax+00h]
0x180014c49  jmp     loc_180014D1E
0x180014c4e  cmp     cs:g_fTracingOn, 0
0x180014c55  jz      short loc_180014C90
0x180014c57  cmp     cs:g_fProviderEnabled, 0
0x180014c5e  jz      short loc_180014C90
0x180014c60  test    cs:g_ulTraceFlags, 1000000h
0x180014c6b  jz      short loc_180014C90
0x180014c6d  mov     rbx, [rsp+48h+arg_0]
0x180014c72  mov     r9, rbx
0x180014c75  mov     rdi, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180014c7a  mov     r8, rdi
0x180014c7d  lea     rdx, aLdapFailedToIn; "LDAP failed to initialize critical sect"...
0x180014c84  mov     ecx, 1000000h
0x180014c89  call    LDAPClientPrint
0x180014c8e  jmp     short loc_180014C9A
0x180014c90  mov     rbx, [rsp+48h+arg_0]
0x180014c95  mov     rdi, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180014c9a  mov     edx, 7165524Ch
0x180014c9f  mov     rcx, rdi
0x180014ca2  call    ldapFree
0x180014ca7  lea     rcx, [rbx+200h]; lpCriticalSection
0x180014cae  call    cs:__imp_EnterCriticalSection
0x180014cb5  nop     dword ptr [rax+rax+00h]
0x180014cba  dec     dword ptr [rbx]
0x180014cbc  cmp     cs:g_fTracingOn, 0
0x180014cc3  jz      short loc_180014CEE
0x180014cc5  cmp     cs:g_fProviderEnabled, 0
0x180014ccc  jz      short loc_180014CEE
0x180014cce  test    byte ptr cs:g_ulTraceFlags, 4
0x180014cd5  jz      short loc_180014CEE
0x180014cd7  mov     r9d, [rbx]
0x180014cda  mov     r8, rbx
0x180014cdd  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180014ce4  mov     ecx, 4
0x180014ce9  call    LDAPClientPrint
0x180014cee  lea     rcx, [rbx+200h]; lpCriticalSection
0x180014cf5  cmp     dword ptr [rbx], 0
0x180014cf8  jnz     loc_180014E91
0x180014cfe  call    cs:__imp_LeaveCriticalSection
0x180014d05  nop     dword ptr [rax+rax+00h]
0x180014d0a  mov     edx, 1
0x180014d0f  mov     rcx, rbx
0x180014d12  call    DereferenceLdapConnection2
0x180014d17  xor     eax, eax
0x180014d19  jmp     loc_180014E82
0x180014d1e  mov     [rbx+20h], rdi
0x180014d22  mov     [rbx+0BAh], sil
0x180014d29  xor     r14d, r14d
0x180014d2c  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180014d31  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014d36  call    cs:__imp_GetSystemTimeAsFileTime
0x180014d3d  nop     dword ptr [rax+rax+00h]
0x180014d42  mov     ecx, [rsp+48h+SystemTimeAsFileTime.dwHighDateTime]
0x180014d46  shl     rcx, 20h
0x180014d4a  mov     eax, [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x180014d4e  or      rcx, rax
0x180014d51  mov     rax, 346DC5D63886594Bh
0x180014d5b  mul     rcx
0x180014d5e  shr     rdx, 0Bh
0x180014d62  mov     [rbx+58h], rdx
0x180014d66  mov     eax, [rdi+3F4h]
0x180014d6c  mov     [rbx+60h], eax
0x180014d6f  mov     eax, [rdi+3F8h]
0x180014d75  mov     [rbx+64h], eax
0x180014d78  movzx   eax, word ptr [rdi+438h]
0x180014d7f  mov     [rbx+0B2h], ax
0x180014d86  mov     [rbx+114h], r14d
0x180014d8d  movzx   eax, byte ptr [rdi+2A8h]
0x180014d94  mov     [rbx+0BDh], al
0x180014d9a  mov     eax, [rdi+43Ch]
0x180014da0  test    al, 2
0x180014da2  jz      loc_180014FDD
0x180014da8  mov     al, 60h ; '`'
0x180014daa  mov     [rbx+0B9h], al
0x180014db0  mov     [rbx+6Ch], r14d
0x180014db4  mov     eax, cs:GlobalMessageNumber
0x180014dba  inc     eax
0x180014dbc  test    eax, 0FE000000h
0x180014dc1  jnz     loc_180014FEF
0x180014dc7  mov     eax, 1
0x180014dcc  lock xadd cs:GlobalMessageNumber, eax
0x180014dd4  inc     eax
0x180014dd6  mov     [rbx+6Ch], eax
0x180014dd9  test    eax, 0FE000000h
0x180014dde  jnz     short loc_180014DB4
0x180014de0  mov     esi, r14d
0x180014de3  mov     dl, 1; Wait
0x180014de5  lea     rcx, RequestListLock; Resource
0x180014dec  call    cs:__imp_RtlAcquireResourceExclusive
0x180014df3  nop     dword ptr [rax+rax+00h]
0x180014df8  mov     ecx, [rbx+6Ch]
0x180014dfb  call    IsMessageIdValid
0x180014e00  test    al, al
0x180014e02  jz      loc_180015030
0x180014e08  lea     rcx, [rbx+70h]; pszDest
0x180014e0c  mov     r9d, [rbx+6Ch]
0x180014e10  lea     r8, pszFormat; "MessageID_%lu"
0x180014e17  mov     edx, 25h ; '%'; cchDest
0x180014e1c  call    StringCchPrintfA
0x180014e21  mov     eax, [rbx+6Ch]
0x180014e24  mov     [rdi+410h], eax
0x180014e2a  cmp     cs:g_fTracingOn, r14d
0x180014e31  jnz     loc_18001516F
0x180014e37  mov     rax, cs:qword_180065BE8
0x180014e3e  lea     rcx, GlobalListRequests
0x180014e45  mov     [rbx], rcx
0x180014e48  mov     [rbx+8], rax
0x180014e4c  mov     [rax], rbx
0x180014e4f  mov     cs:qword_180065BE8, rbx
0x180014e56  inc     cs:GlobalRequestCount
0x180014e5c  lock inc cs:qword_180066088
0x180014e64  lock inc cs:qword_180066098
0x180014e6c  lea     rcx, RequestListLock; Resource
0x180014e73  call    cs:__imp_RtlReleaseResource
0x180014e7a  nop     dword ptr [rax+rax+00h]
0x180014e7f  mov     rax, rbx
0x180014e82  mov     rbx, [rsp+48h+arg_8]
0x180014e87  add     rsp, 30h
0x180014e8b  pop     r14
0x180014e8d  pop     rdi
0x180014e8e  pop     rsi
0x180014e8f  retn
0x180014e91  call    cs:__imp_LeaveCriticalSection
0x180014e98  nop     dword ptr [rax+rax+00h]
0x180014e9d  jmp     loc_180014D17
0x180014ea2  cmp     cs:g_fProviderEnabled, 0
0x180014ea9  jz      loc_180014BF0
0x180014eaf  test    byte ptr cs:g_ulTraceFlags, 8
0x180014eb6  jz      loc_180014BF0
0x180014ebc  mov     [rsp+48h+var_28], 7165524Ch
0x180014ec4  mov     r9, rbx
0x180014ec7  mov     r8d, 120h
0x180014ecd  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180014ed4  mov     ecx, 8
0x180014ed9  call    LDAPClientPrint
0x180014ede  mov     ecx, cs:g_fTracingOn
0x180014ee4  jmp     loc_180014BF0
0x180014ee9  call    cs:__imp_RtlReleaseResource
0x180014ef0  nop     dword ptr [rax+rax+00h]
0x180014ef5  xor     eax, eax
0x180014ef7  jmp     short loc_180014E82
0x180014ef9  cmp     cs:g_fProviderEnabled, 0
0x180014f00  jz      loc_180014C24
0x180014f06  test    byte ptr cs:g_ulTraceFlags, 8
0x180014f0d  jz      loc_180014C24
0x180014f13  mov     [rsp+48h+var_20], eax
0x180014f17  mov     [rsp+48h+var_28], 7165524Ch
0x180014f1f  mov     r9, rbx
0x180014f22  mov     r8d, 118h
0x180014f28  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180014f2f  mov     ecx, 8
0x180014f34  call    LDAPClientPrint
0x180014f39  mov     ecx, cs:g_fTracingOn
0x180014f3f  jmp     loc_180014C24
0x180014f44  test    ecx, ecx
0x180014f46  jz      short loc_180014F75
0x180014f48  cmp     cs:g_fProviderEnabled, 0
0x180014f4f  jz      short loc_180014F75
0x180014f51  test    cs:g_ulTraceFlags, 4000h
0x180014f5c  jz      short loc_180014F75
0x180014f5e  mov     r8d, 118h
0x180014f64  lea     rdx, aLdapcreaterequ; "LdapCreateRequest could not allocate 0x"...
0x180014f6b  mov     ecx, 4000h
0x180014f70  call    LDAPClientPrint
0x180014f75  lea     rcx, [rdi+200h]; lpCriticalSection
0x180014f7c  call    cs:__imp_EnterCriticalSection
0x180014f83  nop     dword ptr [rax+rax+00h]
0x180014f88  dec     dword ptr [rdi]
0x180014f8a  cmp     cs:g_fTracingOn, 0
0x180014f91  jz      short loc_180014FBC
0x180014f93  cmp     cs:g_fProviderEnabled, 0
0x180014f9a  jz      short loc_180014FBC
0x180014f9c  test    byte ptr cs:g_ulTraceFlags, 4
0x180014fa3  jz      short loc_180014FBC
0x180014fa5  mov     r9d, [rdi]
0x180014fa8  mov     r8, rdi
0x180014fab  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180014fb2  mov     ecx, 4
0x180014fb7  call    LDAPClientPrint
0x180014fbc  lea     rcx, [rdi+200h]; lpCriticalSection
0x180014fc3  cmp     dword ptr [rdi], 0
0x180014fc6  jz      loc_180015151
0x180014fcc  call    cs:__imp_LeaveCriticalSection
0x180014fd3  nop     dword ptr [rax+rax+00h]
0x180014fd8  jmp     loc_180014EF5
0x180014fdd  test    al, 4
0x180014fdf  jz      short loc_180014FE8
0x180014fe1  xor     al, al
0x180014fe3  jmp     loc_180014DAA
0x180014fe8  and     al, 60h
0x180014fea  jmp     loc_180014DAA
0x180014fef  lea     rcx, MessageNumberLock; lpCriticalSection
0x180014ff6  call    cs:__imp_EnterCriticalSection
0x180014ffd  nop     dword ptr [rax+rax+00h]
0x180015002  mov     eax, cs:GlobalMessageNumber
0x180015008  inc     eax
0x18001500a  test    eax, 0FE000000h
0x18001500f  jz      short loc_180015018
0x180015011  mov     cs:GlobalMessageNumber, r14d
0x180015018  lea     rcx, MessageNumberLock; lpCriticalSection
0x18001501f  call    cs:__imp_LeaveCriticalSection
0x180015026  nop     dword ptr [rax+rax+00h]
0x18001502b  jmp     loc_180014DC7
0x180015030  cmp     esi, 0Ah
0x180015033  jge     short loc_1800150A4
0x180015035  mov     [rbx+6Ch], r14d
0x180015039  mov     eax, cs:GlobalMessageNumber
0x18001503f  inc     eax
0x180015041  test    eax, 0FE000000h
0x180015046  jz      short loc_180015084
0x180015048  lea     rcx, MessageNumberLock; lpCriticalSection
0x18001504f  call    cs:__imp_EnterCriticalSection
0x180015056  nop     dword ptr [rax+rax+00h]
0x18001505b  mov     eax, cs:GlobalMessageNumber
0x180015061  inc     eax
0x180015063  test    eax, 0FE000000h
0x180015068  jz      short loc_180015071
0x18001506a  mov     cs:GlobalMessageNumber, r14d
0x180015071  lea     rcx, MessageNumberLock; lpCriticalSection
0x180015078  call    cs:__imp_LeaveCriticalSection
0x18001507f  nop     dword ptr [rax+rax+00h]
0x180015084  mov     eax, 1
0x180015089  lock xadd cs:GlobalMessageNumber, eax
0x180015091  inc     eax
0x180015093  mov     [rbx+6Ch], eax
0x180015096  test    eax, 0FE000000h
0x18001509b  jnz     short loc_180015039
0x18001509d  inc     esi
0x18001509f  jmp     loc_180014DF8
0x1800150a4  lea     rcx, RequestListLock; Resource
0x1800150ab  call    cs:__imp_RtlReleaseResource
0x1800150b2  nop     dword ptr [rax+rax+00h]
0x1800150b7  cmp     cs:g_fTracingOn, r14d
0x1800150be  jz      short loc_1800150ED
0x1800150c0  cmp     cs:g_fProviderEnabled, r14d
0x1800150c7  jz      short loc_1800150ED
0x1800150c9  test    cs:g_ulTraceFlags, 1000000h
0x1800150d4  jz      short loc_1800150ED
0x1800150d6  mov     r9, rdi
0x1800150d9  mov     r8, rbx
0x1800150dc  lea     rdx, aLdapFailedToAl; "LDAP failed to allocate message number "...
0x1800150e3  mov     ecx, 1000000h
0x1800150e8  call    LDAPClientPrint
0x1800150ed  mov     edx, 7165524Ch
0x1800150f2  mov     rcx, rbx
0x1800150f5  call    ldapFree
0x1800150fa  lea     rcx, [rdi+200h]; lpCriticalSection
0x180015101  call    cs:__imp_EnterCriticalSection
0x180015108  nop     dword ptr [rax+rax+00h]
0x18001510d  dec     dword ptr [rdi]
0x18001510f  cmp     cs:g_fTracingOn, r14d
  ... truncated ...
```
