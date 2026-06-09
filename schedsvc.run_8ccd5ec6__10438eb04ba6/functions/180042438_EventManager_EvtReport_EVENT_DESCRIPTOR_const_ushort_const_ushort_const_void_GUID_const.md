# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,void *,_GUID const *)

- ea: `0x180042438`
- end: `0x1800425fb`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEAXPEBU_GUID@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18001d7ac`
- `0x180047ee0`
- `0x18004fc18`

## callees

- `0x18000a460`
- `0x180042438`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!fflush` at `0x1800425ab`
- `msvcrt!fflush` at `0x1800425ab`
- `msvcrt!fclose` at `0x1800425bc`
- `msvcrt!fclose` at `0x1800425bc`
- `msvcrt!fputws` at `0x18004259a`
- `msvcrt!fputws` at `0x18004259a`
- `msvcrt!fopen_s` at `0x180042545`
- `msvcrt!fopen_s` at `0x180042545`
- `ntdll!EtwEventEnabled` at `0x180042484`
- `ntdll!EtwEventEnabled` at `0x180042484`
- `ntdll!EtwEventWrite` at `0x180042517`
- `ntdll!EtwEventWrite` at `0x180042517`

## string_xrefs

- `0x180042539`: `TaskScheduler.log`
- `0x180042567`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  EventManager *v4; // r14
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // ebx
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  const OLECHAR *v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const OLECHAR *v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  wchar_t Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled() )
    return 0;
  v9 = -1;
  if ( a3 )
  {
    v13 = a3;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v14 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v13 = &ChannelPath;
    v14 = 2;
  }
  if ( a4 )
  {
    v15 = a4;
    do
      ++v9;
    while ( a4[v9] );
    v16 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
    v15 = &ChannelPath;
    v16 = 2;
  }
  v11 = EtwEventWrite(*(_QWORD *)v4, a2, 2, &v13);
  if ( !v11 )
    return 0;
  Stream = 0;
  if ( !fopen_s(&Stream, "TaskScheduler.log", "a+") )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    StringCchPrintfW(Buffer, 0x400u, L"%s, (%d)\n", L"EventWrite error", v11);
    Buffer[1023] = 0;
    fputws(Buffer, Stream);
    fflush(Stream);
    fclose(Stream);
  }
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180042438  push    rbp
0x18004243a  push    rbx
0x18004243b  push    rsi
0x18004243c  push    rdi
0x18004243d  push    r14
0x18004243f  push    r15
0x180042441  lea     rbp, [rsp-778h]
0x180042449  sub     rsp, 878h
0x180042450  mov     rax, cs:__security_cookie
0x180042457  xor     rax, rsp
0x18004245a  mov     [rbp+7A0h+var_40], rax
0x180042461  mov     r14, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180042468  xor     r15d, r15d
0x18004246b  mov     rdi, r9
0x18004246e  mov     rbx, r8
0x180042471  mov     rsi, rdx
0x180042474  mov     rcx, [r14]
0x180042477  test    rcx, rcx
0x18004247a  jnz     short loc_180042484
0x18004247c  lea     eax, [rcx+1]
0x18004247f  jmp     loc_1800425DB
0x180042484  call    cs:__imp_EtwEventEnabled
0x18004248b  nop     dword ptr [rax+rax+00h]
0x180042490  test    al, al
0x180042492  jz      loc_1800425D9
0x180042498  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004249c  lea     rdx, ChannelPath
0x1800424a3  mov     r8d, 2
0x1800424a9  test    rbx, rbx
0x1800424ac  jz      short loc_1800424D2
0x1800424ae  mov     [rsp+8A0h+var_868], rbx
0x1800424b3  mov     rax, rcx
0x1800424b6  inc     rax
0x1800424b9  cmp     [rbx+rax*2], r15w
0x1800424be  jnz     short loc_1800424B6
0x1800424c0  lea     eax, ds:2[rax*2]
0x1800424c7  mov     dword ptr [rsp+8A0h+var_860+4], r15d
0x1800424cc  mov     dword ptr [rsp+8A0h+var_860], eax
0x1800424d0  jmp     short loc_1800424DC
0x1800424d2  mov     [rsp+8A0h+var_868], rdx
0x1800424d7  mov     [rsp+8A0h+var_860], r8
0x1800424dc  test    rdi, rdi
0x1800424df  jz      short loc_180042502
0x1800424e1  mov     [rsp+8A0h+var_858], rdi
0x1800424e6  inc     rcx
0x1800424e9  cmp     [rdi+rcx*2], r15w
0x1800424ee  jnz     short loc_1800424E6
0x1800424f0  lea     eax, ds:2[rcx*2]
0x1800424f7  mov     dword ptr [rsp+8A0h+var_850+4], r15d
0x1800424fc  mov     dword ptr [rsp+8A0h+var_850], eax
0x180042500  jmp     short loc_18004250C
0x180042502  mov     [rsp+8A0h+var_858], rdx
0x180042507  mov     [rsp+8A0h+var_850], r8
0x18004250c  mov     rcx, [r14]
0x18004250f  lea     r9, [rsp+8A0h+var_868]
0x180042514  mov     rdx, rsi
0x180042517  call    cs:__imp_EtwEventWrite
0x18004251e  nop     dword ptr [rax+rax+00h]
0x180042523  mov     ebx, eax
0x180042525  test    eax, eax
0x180042527  jz      loc_1800425D9
0x18004252d  lea     r8, Mode; "a+"
0x180042534  mov     [rsp+8A0h+Stream], r15
0x180042539  lea     rdx, FileName; "TaskScheduler.log"
0x180042540  lea     rcx, [rsp+8A0h+Stream]; Stream
0x180042545  call    cs:__imp_fopen_s
0x18004254c  nop     dword ptr [rax+rax+00h]
0x180042551  test    eax, eax
0x180042553  jnz     short loc_1800425C8
0x180042555  xor     edx, edx; Val
0x180042557  lea     rcx, [rsp+8A0h+Buffer]; void *
0x18004255c  mov     r8d, 800h; Size
0x180042562  call    memset_0
0x180042567  lea     r9, aEventwriteErro; "EventWrite error"
0x18004256e  mov     [rsp+8A0h+var_880], ebx
0x180042572  lea     r8, aSD; "%s, (%d)\n"
0x180042579  mov     edx, 400h; unsigned __int64
0x18004257e  lea     rcx, [rsp+8A0h+Buffer]; unsigned __int16 *
0x180042583  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042588  mov     rdx, [rsp+8A0h+Stream]; Stream
0x18004258d  lea     rcx, [rsp+8A0h+Buffer]; Buffer
0x180042592  mov     [rbp+7A0h+var_42], r15w
0x18004259a  call    cs:__imp_fputws
0x1800425a1  nop     dword ptr [rax+rax+00h]
0x1800425a6  mov     rcx, [rsp+8A0h+Stream]; Stream
0x1800425ab  call    cs:__imp_fflush
0x1800425b2  nop     dword ptr [rax+rax+00h]
0x1800425b7  mov     rcx, [rsp+8A0h+Stream]; Stream
0x1800425bc  call    cs:__imp_fclose
0x1800425c3  nop     dword ptr [rax+rax+00h]
0x1800425c8  test    ebx, ebx
0x1800425ca  jle     short loc_1800425D5
0x1800425cc  movzx   ebx, bx
0x1800425cf  or      ebx, 80070000h
0x1800425d5  mov     eax, ebx
0x1800425d7  jmp     short loc_1800425DB
0x1800425d9  xor     eax, eax
0x1800425db  mov     rcx, [rbp+7A0h+var_40]
0x1800425e2  xor     rcx, rsp; StackCookie
0x1800425e5  call    __security_check_cookie
0x1800425ea  add     rsp, 878h
0x1800425f1  pop     r15
0x1800425f3  pop     r14
0x1800425f5  pop     rdi
0x1800425f6  pop     rsi
0x1800425f7  pop     rbx
0x1800425f8  pop     rbp
0x1800425f9  retn
```
