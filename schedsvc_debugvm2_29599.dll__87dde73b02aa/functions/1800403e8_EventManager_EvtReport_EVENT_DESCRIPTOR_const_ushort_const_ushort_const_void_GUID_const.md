# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,void *,_GUID const *)

- ea: `0x1800403e8`
- end: `0x180040586`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEAXPEBU_GUID@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800213f8`
- `0x180045df0`
- `0x18004d868`

## callees

- `0x180015740`
- `0x1800403e8`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!fflush` at `0x180040543`
- `msvcrt!fflush` at `0x180040543`
- `msvcrt!fclose` at `0x18004054e`
- `msvcrt!fclose` at `0x18004054e`
- `msvcrt!fputws` at `0x180040538`
- `msvcrt!fputws` at `0x180040538`
- `msvcrt!fopen_s` at `0x1800404e9`
- `msvcrt!fopen_s` at `0x1800404e9`
- `ntdll!EtwEventEnabled` at `0x180040434`
- `ntdll!EtwEventEnabled` at `0x180040434`
- `ntdll!EtwEventWrite` at `0x1800404c1`
- `ntdll!EtwEventWrite` at `0x1800404c1`

## string_xrefs

- `0x1800404dd`: `TaskScheduler.log`
- `0x180040505`: `EventWrite error`

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
0x1800403e8  push    rbp
0x1800403ea  push    rbx
0x1800403eb  push    rsi
0x1800403ec  push    rdi
0x1800403ed  push    r14
0x1800403ef  push    r15
0x1800403f1  lea     rbp, [rsp-778h]
0x1800403f9  sub     rsp, 878h
0x180040400  mov     rax, cs:__security_cookie
0x180040407  xor     rax, rsp
0x18004040a  mov     [rbp+7A0h+var_40], rax
0x180040411  mov     r14, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180040418  xor     r15d, r15d
0x18004041b  mov     rdi, r9
0x18004041e  mov     rbx, r8
0x180040421  mov     rsi, rdx
0x180040424  mov     rcx, [r14]
0x180040427  test    rcx, rcx
0x18004042a  jnz     short loc_180040434
0x18004042c  lea     eax, [rcx+1]
0x18004042f  jmp     loc_180040567
0x180040434  call    cs:__imp_EtwEventEnabled
0x18004043a  test    al, al
0x18004043c  jz      loc_180040565
0x180040442  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040446  lea     rdx, ChannelPath
0x18004044d  mov     r8d, 2
0x180040453  test    rbx, rbx
0x180040456  jz      short loc_18004047C
0x180040458  mov     [rsp+8A0h+var_868], rbx
0x18004045d  mov     rax, rcx
0x180040460  inc     rax
0x180040463  cmp     [rbx+rax*2], r15w
0x180040468  jnz     short loc_180040460
0x18004046a  lea     eax, ds:2[rax*2]
0x180040471  mov     dword ptr [rsp+8A0h+var_860+4], r15d
0x180040476  mov     dword ptr [rsp+8A0h+var_860], eax
0x18004047a  jmp     short loc_180040486
0x18004047c  mov     [rsp+8A0h+var_868], rdx
0x180040481  mov     [rsp+8A0h+var_860], r8
0x180040486  test    rdi, rdi
0x180040489  jz      short loc_1800404AC
0x18004048b  mov     [rsp+8A0h+var_858], rdi
0x180040490  inc     rcx
0x180040493  cmp     [rdi+rcx*2], r15w
0x180040498  jnz     short loc_180040490
0x18004049a  lea     eax, ds:2[rcx*2]
0x1800404a1  mov     dword ptr [rsp+8A0h+var_850+4], r15d
0x1800404a6  mov     dword ptr [rsp+8A0h+var_850], eax
0x1800404aa  jmp     short loc_1800404B6
0x1800404ac  mov     [rsp+8A0h+var_858], rdx
0x1800404b1  mov     [rsp+8A0h+var_850], r8
0x1800404b6  mov     rcx, [r14]
0x1800404b9  lea     r9, [rsp+8A0h+var_868]
0x1800404be  mov     rdx, rsi
0x1800404c1  call    cs:__imp_EtwEventWrite
0x1800404c7  mov     ebx, eax
0x1800404c9  test    eax, eax
0x1800404cb  jz      loc_180040565
0x1800404d1  lea     r8, Mode; "a+"
0x1800404d8  mov     [rsp+8A0h+Stream], r15
0x1800404dd  lea     rdx, FileName; "TaskScheduler.log"
0x1800404e4  lea     rcx, [rsp+8A0h+Stream]; Stream
0x1800404e9  call    cs:__imp_fopen_s
0x1800404ef  test    eax, eax
0x1800404f1  jnz     short loc_180040554
0x1800404f3  xor     edx, edx; Val
0x1800404f5  lea     rcx, [rsp+8A0h+Buffer]; void *
0x1800404fa  mov     r8d, 800h; Size
0x180040500  call    memset_0
0x180040505  lea     r9, aEventwriteErro; "EventWrite error"
0x18004050c  mov     [rsp+8A0h+var_880], ebx
0x180040510  lea     r8, aSD; "%s, (%d)\n"
0x180040517  mov     edx, 400h; unsigned __int64
0x18004051c  lea     rcx, [rsp+8A0h+Buffer]; unsigned __int16 *
0x180040521  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040526  mov     rdx, [rsp+8A0h+Stream]; Stream
0x18004052b  lea     rcx, [rsp+8A0h+Buffer]; Buffer
0x180040530  mov     [rbp+7A0h+var_42], r15w
0x180040538  call    cs:__imp_fputws
0x18004053e  mov     rcx, [rsp+8A0h+Stream]; Stream
0x180040543  call    cs:__imp_fflush
0x180040549  mov     rcx, [rsp+8A0h+Stream]; Stream
0x18004054e  call    cs:__imp_fclose
0x180040554  test    ebx, ebx
0x180040556  jle     short loc_180040561
0x180040558  movzx   ebx, bx
0x18004055b  or      ebx, 80070000h
0x180040561  mov     eax, ebx
0x180040563  jmp     short loc_180040567
0x180040565  xor     eax, eax
0x180040567  mov     rcx, [rbp+7A0h+var_40]
0x18004056e  xor     rcx, rsp; StackCookie
0x180040571  call    __security_check_cookie
0x180040576  add     rsp, 878h
0x18004057d  pop     r15
0x18004057f  pop     r14
0x180040581  pop     rdi
0x180040582  pop     rsi
0x180040583  pop     rbx
0x180040584  pop     rbp
0x180040585  retn
```
