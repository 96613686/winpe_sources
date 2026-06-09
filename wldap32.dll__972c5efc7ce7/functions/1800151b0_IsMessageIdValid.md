# IsMessageIdValid

- ea: `0x1800151b0`
- end: `0x18001532f`
- name: `IsMessageIdValid`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014b60`

## callees

- `0x1800037a8`
- `0x180008660`
- `0x180008710`
- `0x1800151b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001527e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001527e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001524f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001526d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001524f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001526d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152e4`

## string_xrefs

- `0x180015313`: `Message Id 0x%x is already in use \n`

## pseudocode

```c
char __fastcall IsMessageIdValid(int a1)
{
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // rcx

  if ( a1 )
  {
    v2 = (__int64 *)GlobalListRequests;
    while ( 1 )
    {
      v3 = 0;
      do
      {
        if ( v2 == &GlobalListRequests || v3 )
          return 1;
        v4 = ReferenceLdapRequest(v2);
        v2 = (__int64 *)*v2;
        v3 = v4;
      }
      while ( !v4 );
      v5 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
      v6 = (struct _RTL_CRITICAL_SECTION *)(v4 + 48);
      if ( *(_DWORD *)(v4 + 108) == a1 )
        break;
      EnterCriticalSection(v6);
      --*(_DWORD *)(v3 + 16);
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
        LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v3, *(_DWORD *)(v3 + 16));
      if ( *(_DWORD *)(v3 + 16) )
      {
        LeaveCriticalSection(v5);
      }
      else
      {
        LeaveCriticalSection(v5);
        DereferenceLdapRequest2((__int64 *)v3, 1);
      }
    }
    EnterCriticalSection(v6);
    --*(_DWORD *)(v3 + 16);
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
      LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v3, *(_DWORD *)(v3 + 16));
    if ( *(_DWORD *)(v3 + 16) )
    {
      LeaveCriticalSection(v5);
    }
    else
    {
      LeaveCriticalSection(v5);
      DereferenceLdapRequest2((__int64 *)v3, 1);
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientPrint(0x10000000, "Message Id 0x%x is already in use \n", a1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800151b0  push    rbx
0x1800151b2  push    rbp
0x1800151b3  push    rsi
0x1800151b4  push    rdi
0x1800151b5  sub     rsp, 28h
0x1800151b9  mov     ebp, ecx
0x1800151bb  test    ecx, ecx
0x1800151bd  jz      loc_18001531F
0x1800151c3  mov     rsi, cs:GlobalListRequests
0x1800151ca  xor     ebx, ebx
0x1800151cc  lea     rax, GlobalListRequests
0x1800151d3  cmp     rsi, rax
0x1800151d6  jz      loc_18001532B
0x1800151dc  test    rbx, rbx
0x1800151df  jnz     loc_18001532B
0x1800151e5  mov     rcx, rsi
0x1800151e8  call    ReferenceLdapRequest
0x1800151ed  mov     rsi, [rsi]
0x1800151f0  mov     rbx, rax
0x1800151f3  test    rax, rax
0x1800151f6  jz      short loc_1800151CC
0x1800151f8  lea     rdi, [rax+30h]
0x1800151fc  mov     rcx, rdi; lpCriticalSection
0x1800151ff  cmp     [rax+6Ch], ebp
0x180015202  jz      short loc_18001527E
0x180015204  call    cs:__imp_EnterCriticalSection
0x18001520b  nop     dword ptr [rax+rax+00h]
0x180015210  dec     dword ptr [rbx+10h]
0x180015213  cmp     cs:g_fTracingOn, 0
0x18001521a  jz      short loc_180015246
0x18001521c  cmp     cs:g_fProviderEnabled, 0
0x180015223  jz      short loc_180015246
0x180015225  test    byte ptr cs:g_ulTraceFlags, 4
0x18001522c  jz      short loc_180015246
0x18001522e  mov     r9d, [rbx+10h]
0x180015232  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180015239  mov     r8, rbx
0x18001523c  mov     ecx, 4
0x180015241  call    LDAPClientPrint
0x180015246  cmp     dword ptr [rbx+10h], 0
0x18001524a  mov     rcx, rdi; lpCriticalSection
0x18001524d  jnz     short loc_18001526D
0x18001524f  call    cs:__imp_LeaveCriticalSection
0x180015256  nop     dword ptr [rax+rax+00h]
0x18001525b  mov     edx, 1
0x180015260  mov     rcx, rbx
0x180015263  call    DereferenceLdapRequest2
0x180015268  jmp     loc_1800151CA
0x18001526d  call    cs:__imp_LeaveCriticalSection
0x180015274  nop     dword ptr [rax+rax+00h]
0x180015279  jmp     loc_1800151CA
0x18001527e  call    cs:__imp_EnterCriticalSection
0x180015285  nop     dword ptr [rax+rax+00h]
0x18001528a  dec     dword ptr [rbx+10h]
0x18001528d  cmp     cs:g_fTracingOn, 0
0x180015294  jz      short loc_1800152C0
0x180015296  cmp     cs:g_fProviderEnabled, 0
0x18001529d  jz      short loc_1800152C0
0x18001529f  test    byte ptr cs:g_ulTraceFlags, 4
0x1800152a6  jz      short loc_1800152C0
0x1800152a8  mov     r9d, [rbx+10h]
0x1800152ac  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x1800152b3  mov     r8, rbx
0x1800152b6  mov     ecx, 4
0x1800152bb  call    LDAPClientPrint
0x1800152c0  cmp     dword ptr [rbx+10h], 0
0x1800152c4  mov     rcx, rdi; lpCriticalSection
0x1800152c7  jnz     short loc_1800152E4
0x1800152c9  call    cs:__imp_LeaveCriticalSection
0x1800152d0  nop     dword ptr [rax+rax+00h]
0x1800152d5  mov     edx, 1
0x1800152da  mov     rcx, rbx
0x1800152dd  call    DereferenceLdapRequest2
0x1800152e2  jmp     short loc_1800152F0
0x1800152e4  call    cs:__imp_LeaveCriticalSection
0x1800152eb  nop     dword ptr [rax+rax+00h]
0x1800152f0  cmp     cs:g_fTracingOn, 0
0x1800152f7  jz      short loc_18001531F
0x1800152f9  cmp     cs:g_fProviderEnabled, 0
0x180015300  jz      short loc_18001531F
0x180015302  mov     ecx, 10000000h
0x180015307  test    cs:g_ulTraceFlags, rcx
0x18001530e  jz      short loc_18001531F
0x180015310  mov     r8d, ebp
0x180015313  lea     rdx, aMessageId0xXIs; "Message Id 0x%x is already in use \n"
0x18001531a  call    LDAPClientPrint
0x18001531f  xor     al, al
0x180015321  add     rsp, 28h
0x180015325  pop     rdi
0x180015326  pop     rsi
0x180015327  pop     rbp
0x180015328  pop     rbx
0x180015329  retn
0x18001532b  mov     al, 1
0x18001532d  jmp     short loc_180015321
```
