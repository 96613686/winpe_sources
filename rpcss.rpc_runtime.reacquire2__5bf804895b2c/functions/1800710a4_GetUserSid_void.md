# GetUserSid(void *)

- ea: `0x1800710a4`
- end: `0x180071311`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `621`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800065e4`
- `0x18004c1ac`
- `0x18004e578`
- `0x180061fc0`
- `0x180075b1c`
- `0x1800861e8`
- `0x1800871cc`
- `0x1800eff98`
- `0x1800f759c`
- `0x180103c08`

## callees

- `0x180034260`
- `0x1800710a4`
- `0x18008172c`
- `0x1800b7ac0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180071261`
- `ntdll!RtlCopySid` at `0x180071261`
- `ntdll!RtlLengthSid` at `0x18007121f`
- `ntdll!RtlLengthSid` at `0x18007121f`
- `ntdll!NtQueryInformationToken` at `0x1800710e6`
- `ntdll!NtQueryInformationToken` at `0x18007119b`
- `ntdll!NtQueryInformationToken` at `0x1800710e6`
- `ntdll!NtQueryInformationToken` at `0x18007119b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071280`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800712e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071202`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071280`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800712e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071167`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007123c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071167`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007123c`

## string_xrefs

- `0x180071148`: `onecore\com\combase\catalog\services.cxx`
- `0x1800711ea`: `onecore\com\combase\catalog\services.cxx`
- `0x1800712cb`: `onecore\com\combase\catalog\services.cxx`
- `0x180071141`: `GetUserSid`
- `0x1800711e3`: `GetUserSid`
- `0x1800712c4`: `GetUserSid`

## pseudocode

```c
void *__fastcall GetUserSid(HANDLE TokenHandle)
{
  NTSTATUS InformationToken; // eax
  NTSTATUS v3; // r8d
  PSID *v4; // rbx
  int v5; // esi
  NTSTATUS v6; // r8d
  void *v8; // rax
  void *v9; // rdi
  NTSTATUS v10; // ebp
  ULONG TokenInformationLength[4]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE TokenInformation[112]; // [rsp+40h] [rbp-A8h] BYREF

  TokenInformationLength[0] = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x64u, TokenInformationLength);
  v3 = InformationToken;
  if ( InformationToken >= 0 )
  {
    v5 = 0;
    v4 = (PSID *)TokenInformation;
  }
  else
  {
    if ( InformationToken != -1073741789 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (unsigned int)"GetUserSid",
          1809,
          0,
          (__int64)L"%!STATUS!",
          v3);
      return 0;
    }
    v4 = (PSID *)HeapAlloc(g_hHeap, 0, TokenInformationLength[0]);
    if ( !v4 )
      return 0;
    v5 = 1;
    v6 = NtQueryInformationToken(TokenHandle, TokenUser, v4, TokenInformationLength[0], TokenInformationLength);
    if ( v6 < 0 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (unsigned int)"GetUserSid",
          1842,
          0,
          (__int64)L"%!STATUS!",
          v6);
LABEL_13:
      HeapFree(g_hHeap, 0, v4);
      return 0;
    }
  }
  TokenInformationLength[0] = RtlLengthSid(*v4);
  v8 = HeapAlloc(g_hHeap, 0, TokenInformationLength[0]);
  v9 = v8;
  if ( !v8 )
  {
    if ( v5 != 1 )
      return 0;
    goto LABEL_13;
  }
  v10 = RtlCopySid(TokenInformationLength[0], v8, *v4);
  if ( v5 == 1 )
    HeapFree(g_hHeap, 0, v4);
  if ( v10 < 0 )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (unsigned int)"GetUserSid",
        1876,
        0,
        (__int64)L"%!STATUS!",
        v10);
    HeapFree(g_hHeap, 0, v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800710a4  push    rbx
0x1800710a6  push    rbp
0x1800710a7  push    rsi
0x1800710a8  push    rdi
0x1800710a9  sub     rsp, 0C8h
0x1800710b0  mov     rax, cs:__security_cookie
0x1800710b7  xor     rax, rsp
0x1800710ba  mov     [rsp+0E8h+var_38], rax
0x1800710c2  mov     r9d, 64h ; 'd'; TokenInformationLength
0x1800710c8  mov     [rsp+0E8h+TokenInformationLength], 0
0x1800710d0  lea     rax, [rsp+0E8h+TokenInformationLength]
0x1800710d5  mov     rdi, rcx
0x1800710d8  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x1800710dd  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x1800710e2  lea     edx, [r9-63h]; TokenInformationClass
0x1800710e6  call    cs:__imp_NtQueryInformationToken
0x1800710ed  nop     dword ptr [rax+rax+00h]
0x1800710f2  mov     r8d, eax
0x1800710f5  test    eax, eax
0x1800710f7  jns     loc_180071215
0x1800710fd  cmp     eax, 0C0000023h
0x180071102  jz      short loc_180071159
0x180071104  mov     ecx, cs:dword_1801574B8
0x18007110a  test    ecx, ecx
0x18007110c  jnz     short loc_180071127
0x18007110e  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180071114  jz      loc_18007120E
0x18007111a  call    IsWppLevelEnabled
0x18007111f  test    al, al
0x180071121  jz      loc_18007120E
0x180071127  mov     [rsp+0E8h+var_C0], r8d
0x18007112c  lea     rax, aStatus; "%!STATUS!"
0x180071133  mov     r8d, 711h
0x180071139  mov     [rsp+0E8h+ReturnLength], rax
0x18007113e  xor     r9d, r9d
0x180071141  lea     rdx, aGetusersid; "GetUserSid"
0x180071148  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18007114f  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180071154  jmp     loc_18007120E
0x180071159  mov     r8d, [rsp+0E8h+TokenInformationLength]; dwBytes
0x18007115e  xor     edx, edx; dwFlags
0x180071160  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180071167  call    cs:__imp_HeapAlloc
0x18007116e  nop     dword ptr [rax+rax+00h]
0x180071173  mov     rbx, rax
0x180071176  test    rax, rax
0x180071179  jz      loc_18007120E
0x18007117f  mov     r9d, [rsp+0E8h+TokenInformationLength]; TokenInformationLength
0x180071184  lea     rax, [rsp+0E8h+TokenInformationLength]
0x180071189  mov     esi, 1
0x18007118e  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x180071193  mov     edx, esi; TokenInformationClass
0x180071195  mov     r8, rbx; TokenInformation
0x180071198  mov     rcx, rdi; TokenHandle
0x18007119b  call    cs:__imp_NtQueryInformationToken
0x1800711a2  nop     dword ptr [rax+rax+00h]
0x1800711a7  mov     r8d, eax
0x1800711aa  test    eax, eax
0x1800711ac  jns     short loc_18007121C
0x1800711ae  mov     ecx, cs:dword_1801574B8
0x1800711b4  test    ecx, ecx
0x1800711b6  jnz     short loc_1800711C9
0x1800711b8  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800711be  jz      short loc_1800711F6
0x1800711c0  call    IsWppLevelEnabled
0x1800711c5  test    al, al
0x1800711c7  jz      short loc_1800711F6
0x1800711c9  mov     [rsp+0E8h+var_C0], r8d
0x1800711ce  lea     rax, aStatus; "%!STATUS!"
0x1800711d5  mov     r8d, 732h
0x1800711db  mov     [rsp+0E8h+ReturnLength], rax
0x1800711e0  xor     r9d, r9d
0x1800711e3  lea     rdx, aGetusersid; "GetUserSid"
0x1800711ea  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800711f1  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800711f6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800711fd  mov     r8, rbx; lpMem
0x180071200  xor     edx, edx; dwFlags
0x180071202  call    cs:__imp_HeapFree
0x180071209  nop     dword ptr [rax+rax+00h]
0x18007120e  xor     eax, eax
0x180071210  jmp     loc_1800712F4
0x180071215  xor     esi, esi
0x180071217  lea     rbx, [rsp+0E8h+TokenInformation]
0x18007121c  mov     rcx, [rbx]; Sid
0x18007121f  call    cs:__imp_RtlLengthSid
0x180071226  nop     dword ptr [rax+rax+00h]
0x18007122b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180071232  xor     edx, edx; dwFlags
0x180071234  mov     r8d, eax; dwBytes
0x180071237  mov     [rsp+0E8h+TokenInformationLength], r8d
0x18007123c  call    cs:__imp_HeapAlloc
0x180071243  nop     dword ptr [rax+rax+00h]
0x180071248  mov     rdi, rax
0x18007124b  test    rax, rax
0x18007124e  jnz     short loc_180071257
0x180071250  cmp     esi, 1
0x180071253  jnz     short loc_18007120E
0x180071255  jmp     short loc_1800711F6
0x180071257  mov     r8, [rbx]; SourceSid
0x18007125a  mov     rdx, rdi; DestinationSid
0x18007125d  mov     ecx, [rsp+0E8h+TokenInformationLength]; DestinationSidLength
0x180071261  call    cs:__imp_RtlCopySid
0x180071268  nop     dword ptr [rax+rax+00h]
0x18007126d  mov     ebp, eax
0x18007126f  cmp     esi, 1
0x180071272  jnz     short loc_18007128C
0x180071274  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007127b  mov     r8, rbx; lpMem
0x18007127e  xor     edx, edx; dwFlags
0x180071280  call    cs:__imp_HeapFree
0x180071287  nop     dword ptr [rax+rax+00h]
0x18007128c  test    ebp, ebp
0x18007128e  jns     short loc_1800712F1
0x180071290  mov     ecx, cs:dword_1801574B8
0x180071296  test    ecx, ecx
0x180071298  jnz     short loc_1800712AB
0x18007129a  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800712a0  jz      short loc_1800712D7
0x1800712a2  call    IsWppLevelEnabled
0x1800712a7  test    al, al
0x1800712a9  jz      short loc_1800712D7
0x1800712ab  lea     rax, aStatus; "%!STATUS!"
0x1800712b2  mov     [rsp+0E8h+var_C0], ebp
0x1800712b6  xor     r9d, r9d
0x1800712b9  mov     [rsp+0E8h+ReturnLength], rax
0x1800712be  mov     r8d, 754h
0x1800712c4  lea     rdx, aGetusersid; "GetUserSid"
0x1800712cb  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800712d2  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800712d7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800712de  mov     r8, rdi; lpMem
0x1800712e1  xor     edx, edx; dwFlags
0x1800712e3  call    cs:__imp_HeapFree
0x1800712ea  nop     dword ptr [rax+rax+00h]
0x1800712ef  xor     edi, edi
0x1800712f1  mov     rax, rdi
0x1800712f4  mov     rcx, [rsp+0E8h+var_38]
0x1800712fc  xor     rcx, rsp; StackCookie
0x1800712ff  call    __security_check_cookie
0x180071304  add     rsp, 0C8h
0x18007130b  pop     rdi
0x18007130c  pop     rsi
0x18007130d  pop     rbp
0x18007130e  pop     rbx
0x18007130f  retn
```
