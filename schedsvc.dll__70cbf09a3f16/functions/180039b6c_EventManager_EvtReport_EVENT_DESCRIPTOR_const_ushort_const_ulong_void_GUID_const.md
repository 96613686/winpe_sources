# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)

- ea: `0x180039b6c`
- end: `0x180039cfa`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, unsigned int, void *, const struct _GUID *)`
- caller_count: `26`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180009010`
- `0x18000b5a0`
- `0x18001b0d0`
- `0x1800213f8`
- `0x180021ca0`
- `0x180022b80`
- `0x180024ce0`
- `0x180029978`
- `0x18002f040`
- `0x1800329cc`
- `0x1800349c0`
- `0x180038890`
- `0x180039ad0`
- `0x180039d30`
- `0x180040590`
- `0x180045df0`
- `0x18004f190`
- `0x18005331c`
- `0x180053c10`
- `0x1800654bc`
- `0x180065680`
- `0x18006d418`
- `0x180072430`
- `0x1800727b0`
- `0x180072900`
- `0x180072ad0`

## callees

- `0x180015740`
- `0x180039b6c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!fflush` at `0x180039caf`
- `msvcrt!fflush` at `0x180039caf`
- `msvcrt!fclose` at `0x180039cba`
- `msvcrt!fclose` at `0x180039cba`
- `msvcrt!fputws` at `0x180039ca4`
- `msvcrt!fputws` at `0x180039ca4`
- `msvcrt!fopen_s` at `0x180039c55`
- `msvcrt!fopen_s` at `0x180039c55`
- `ntdll!EtwEventEnabled` at `0x180039bbe`
- `ntdll!EtwEventEnabled` at `0x180039bbe`
- `ntdll!EtwEventWrite` at `0x180039c2d`
- `ntdll!EtwEventWrite` at `0x180039c2d`

## string_xrefs

- `0x180039c49`: `TaskScheduler.log`
- `0x180039c71`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        int a4)
{
  EventManager *v4; // rsi
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  FILE *Stream; // [rsp+38h] [rbp-D0h] BYREF
  const OLECHAR *v12; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+48h] [rbp-C0h]
  int *v14; // [rsp+50h] [rbp-B8h]
  __int64 v15; // [rsp+58h] [rbp-B0h]
  wchar_t Buffer[1024]; // [rsp+68h] [rbp-A0h] BYREF
  int v17; // [rsp+8B0h] [rbp+7A8h] BYREF

  v17 = a4;
  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled() )
    return 0;
  if ( a3 )
  {
    v12 = a3;
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v13 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v13 = 2;
    v12 = &ChannelPath;
  }
  v9 = *(_QWORD *)v4;
  v14 = &v17;
  v15 = 4;
  v10 = EtwEventWrite(v9, a2, 2, &v12);
  if ( !v10 )
    return 0;
  Stream = 0;
  if ( !fopen_s(&Stream, "TaskScheduler.log", "a+") )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    StringCchPrintfW(Buffer, 0x400u, L"%s, (%d)\n", L"EventWrite error", v10);
    Buffer[1023] = 0;
    fputws(Buffer, Stream);
    fflush(Stream);
    fclose(Stream);
  }
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180039b6c  mov     rax, rsp
0x180039b6f  mov     [rax+8], rbx
0x180039b73  mov     [rax+18h], rsi
0x180039b77  mov     [rax+20h], r9d
0x180039b7b  push    rbp
0x180039b7c  push    rdi
0x180039b7d  push    r14
0x180039b7f  lea     rbp, [rax-788h]
0x180039b86  sub     rsp, 870h
0x180039b8d  mov     rax, cs:__security_cookie
0x180039b94  xor     rax, rsp
0x180039b97  mov     [rbp+780h+var_20], rax
0x180039b9e  mov     rsi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180039ba5  xor     r14d, r14d
0x180039ba8  mov     rbx, r8
0x180039bab  mov     rdi, rdx
0x180039bae  mov     rcx, [rsi]
0x180039bb1  test    rcx, rcx
0x180039bb4  jnz     short loc_180039BBE
0x180039bb6  lea     eax, [rcx+1]
0x180039bb9  jmp     loc_180039CD3
0x180039bbe  call    cs:__imp_EtwEventEnabled
0x180039bc4  test    al, al
0x180039bc6  jz      loc_180039CD1
0x180039bcc  mov     r8d, 2
0x180039bd2  test    rbx, rbx
0x180039bd5  jz      short loc_180039BFC
0x180039bd7  mov     [rsp+880h+var_848], rbx
0x180039bdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039be0  inc     rax
0x180039be3  cmp     [rbx+rax*2], r14w
0x180039be8  jnz     short loc_180039BE0
0x180039bea  lea     eax, ds:2[rax*2]
0x180039bf1  mov     dword ptr [rsp+880h+var_840+4], r14d
0x180039bf6  mov     dword ptr [rsp+880h+var_840], eax
0x180039bfa  jmp     short loc_180039C0D
0x180039bfc  lea     rax, ChannelPath
0x180039c03  mov     [rsp+880h+var_840], r8
0x180039c08  mov     [rsp+880h+var_848], rax
0x180039c0d  mov     rcx, [rsi]
0x180039c10  lea     rax, [rbp+780h+arg_18]
0x180039c17  lea     r9, [rsp+880h+var_848]
0x180039c1c  mov     [rsp+880h+var_838], rax
0x180039c21  mov     rdx, rdi
0x180039c24  mov     [rsp+880h+var_830], 4
0x180039c2d  call    cs:__imp_EtwEventWrite
0x180039c33  mov     ebx, eax
0x180039c35  test    eax, eax
0x180039c37  jz      loc_180039CD1
0x180039c3d  lea     r8, Mode; "a+"
0x180039c44  mov     [rsp+880h+Stream], r14
0x180039c49  lea     rdx, FileName; "TaskScheduler.log"
0x180039c50  lea     rcx, [rsp+880h+Stream]; Stream
0x180039c55  call    cs:__imp_fopen_s
0x180039c5b  test    eax, eax
0x180039c5d  jnz     short loc_180039CC0
0x180039c5f  xor     edx, edx; Val
0x180039c61  lea     rcx, [rsp+880h+Buffer]; void *
0x180039c66  mov     r8d, 800h; Size
0x180039c6c  call    memset_0
0x180039c71  lea     r9, aEventwriteErro; "EventWrite error"
0x180039c78  mov     [rsp+880h+var_860], ebx
0x180039c7c  lea     r8, aSD; "%s, (%d)\n"
0x180039c83  mov     edx, 400h; unsigned __int64
0x180039c88  lea     rcx, [rsp+880h+Buffer]; unsigned __int16 *
0x180039c8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039c92  mov     rdx, [rsp+880h+Stream]; Stream
0x180039c97  lea     rcx, [rsp+880h+Buffer]; Buffer
0x180039c9c  mov     [rbp+780h+var_22], r14w
0x180039ca4  call    cs:__imp_fputws
0x180039caa  mov     rcx, [rsp+880h+Stream]; Stream
0x180039caf  call    cs:__imp_fflush
0x180039cb5  mov     rcx, [rsp+880h+Stream]; Stream
0x180039cba  call    cs:__imp_fclose
0x180039cc0  test    ebx, ebx
0x180039cc2  jle     short loc_180039CCD
0x180039cc4  movzx   ebx, bx
0x180039cc7  or      ebx, 80070000h
0x180039ccd  mov     eax, ebx
0x180039ccf  jmp     short loc_180039CD3
0x180039cd1  xor     eax, eax
0x180039cd3  mov     rcx, [rbp+780h+var_20]
0x180039cda  xor     rcx, rsp; StackCookie
0x180039cdd  call    __security_check_cookie
0x180039ce2  lea     r11, [rsp+880h+var_10]
0x180039cea  mov     rbx, [r11+20h]
0x180039cee  mov     rsi, [r11+30h]
0x180039cf2  mov     rsp, r11
0x180039cf5  pop     r14
0x180039cf7  pop     rdi
0x180039cf8  pop     rbp
0x180039cf9  retn
```
