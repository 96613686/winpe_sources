# NtpTimeProvOpen(ushort *,TimeProvSysCallbacks *,void * *)

- ea: `0x180030090`
- end: `0x1800301f2`
- name: `?NtpTimeProvOpen@@YAJPEAGPEAUTimeProvSysCallbacks@@PEAPEAX@Z`
- size: `354`
- prototype: `__int64 __fastcall(wchar_t *String1, struct TimeProvSysCallbacks *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180029bbc`
- `0x180030090`
- `0x1800301f8`
- `0x1800462f4`
- `0x1800468c0`
- `0x180063f44`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800300bc`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800300bc`

## string_xrefs

- `0x1800300d9`: `NtpTimeProvOpen("%s") called.\n`

## pseudocode

```c
__int64 __fastcall NtpTimeProvOpen(wchar_t *String1, struct TimeProvSysCallbacks *a2, void **a3)
{
  int started; // ebx

  RtlRunOnceExecuteOnce(&_runOnce, InitializeGlobals, 0, 0);
  if ( (unsigned __int8)FileLogAllowEntry(59) )
    FileLogAdd(L"NtpTimeProvOpen(\"%s\") called.\n", String1);
  if ( !wcscmp_0(String1, L"NtpServer") )
  {
    if ( !g_pnpstate )
      goto LABEL_8;
    if ( *((_BYTE *)g_pnpstate + 48) == 1 )
      return (unsigned int)-2147023649;
    if ( !*(_BYTE *)g_pnpstate )
    {
LABEL_8:
      started = StartNtpProv(a2);
      if ( started < 0 )
        return (unsigned int)started;
    }
    started = StartNtpServer();
    if ( started >= 0 )
    {
      *a3 = (void *)1;
      if ( (unsigned __int8)FileLogAllowEntry(59) )
        FileLogAdd(L"NtpServer started.\n");
      return 0;
    }
  }
  else
  {
    if ( wcscmp_0(String1, L"NtpClient") )
      return (unsigned int)-2147024809;
    if ( !g_pnpstate )
      goto LABEL_16;
    if ( *((_BYTE *)g_pnpstate + 49) == 1 )
      return (unsigned int)-2147023649;
    if ( !*(_BYTE *)g_pnpstate )
    {
LABEL_16:
      started = StartNtpProv(a2);
      if ( started < 0 )
        return (unsigned int)started;
    }
    started = StartNtpClient();
    if ( started >= 0 )
    {
      *a3 = (void *)2;
      if ( (unsigned __int8)FileLogAllowEntry(59) )
        FileLogAdd(L"NtpClient started.\n");
      return 0;
    }
  }
  if ( !*((_BYTE *)g_pnpstate + 48) && !*((_BYTE *)g_pnpstate + 49) )
    StopNtpProv();
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180030090  mov     [rsp+arg_0], rbx
0x180030095  mov     [rsp+arg_8], rsi
0x18003009a  push    rdi
0x18003009b  sub     rsp, 20h
0x18003009f  mov     rsi, r8
0x1800300a2  mov     rdi, rdx
0x1800300a5  mov     rbx, rcx
0x1800300a8  lea     rdx, ?InitializeGlobals@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitializeGlobals(_RTL_RUN_ONCE *,void *,void * *)
0x1800300af  xor     r8d, r8d
0x1800300b2  lea     rcx, ?_runOnce@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE _runOnce
0x1800300b9  xor     r9d, r9d
0x1800300bc  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800300c3  nop     dword ptr [rax+rax+00h]
0x1800300c8  mov     ecx, 3Bh ; ';'
0x1800300cd  call    FileLogAllowEntry
0x1800300d2  test    al, al
0x1800300d4  jz      short loc_1800300E5
0x1800300d6  mov     rdx, rbx
0x1800300d9  lea     rcx, aNtptimeprovope; "NtpTimeProvOpen(\"%s\") called.\n"
0x1800300e0  call    FileLogAdd
0x1800300e5  lea     rdx, aNtpserver; "NtpServer"
0x1800300ec  mov     rcx, rbx; String1
0x1800300ef  call    wcscmp_0
0x1800300f4  test    eax, eax
0x1800300f6  jnz     short loc_180030158
0x1800300f8  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800300ff  test    rax, rax
0x180030102  jz      short loc_180030119
0x180030104  cmp     byte ptr [rax+30h], 1
0x180030108  jnz     short loc_180030114
0x18003010a  mov     ebx, 800704DFh
0x18003010f  jmp     loc_1800301DF
0x180030114  cmp     byte ptr [rax], 0
0x180030117  jnz     short loc_18003012B
0x180030119  mov     rcx, rdi; struct TimeProvSysCallbacks *
0x18003011c  call    ?StartNtpProv@@YAJPEAUTimeProvSysCallbacks@@@Z; StartNtpProv(TimeProvSysCallbacks *)
0x180030121  mov     ebx, eax
0x180030123  test    eax, eax
0x180030125  js      loc_1800301DF
0x18003012b  call    ?StartNtpServer@@YAJXZ; StartNtpServer(void)
0x180030130  mov     ebx, eax
0x180030132  test    eax, eax
0x180030134  js      loc_1800301C0
0x18003013a  mov     ecx, 3Bh ; ';'
0x18003013f  mov     qword ptr [rsi], 1
0x180030146  call    FileLogAllowEntry
0x18003014b  test    al, al
0x18003014d  jz      short loc_1800301BC
0x18003014f  lea     rcx, aNtpserverStart; "NtpServer started.\n"
0x180030156  jmp     short loc_1800301B7
0x180030158  lea     rdx, aNtpclient; "NtpClient"
0x18003015f  mov     rcx, rbx; String1
0x180030162  call    wcscmp_0
0x180030167  test    eax, eax
0x180030169  jnz     short loc_1800301DA
0x18003016b  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180030172  test    rax, rax
0x180030175  jz      short loc_180030182
0x180030177  cmp     byte ptr [rax+31h], 1
0x18003017b  jz      short loc_18003010A
0x18003017d  cmp     byte ptr [rax], 0
0x180030180  jnz     short loc_180030190
0x180030182  mov     rcx, rdi; struct TimeProvSysCallbacks *
0x180030185  call    ?StartNtpProv@@YAJPEAUTimeProvSysCallbacks@@@Z; StartNtpProv(TimeProvSysCallbacks *)
0x18003018a  mov     ebx, eax
0x18003018c  test    eax, eax
0x18003018e  js      short loc_1800301DF
0x180030190  call    ?StartNtpClient@@YAJXZ; StartNtpClient(void)
0x180030195  mov     ebx, eax
0x180030197  test    eax, eax
0x180030199  js      short loc_1800301C0
0x18003019b  mov     ecx, 3Bh ; ';'
0x1800301a0  mov     qword ptr [rsi], 2
0x1800301a7  call    FileLogAllowEntry
0x1800301ac  test    al, al
0x1800301ae  jz      short loc_1800301BC
0x1800301b0  lea     rcx, aNtpclientStart; "NtpClient started.\n"
0x1800301b7  call    FileLogAdd
0x1800301bc  xor     ebx, ebx
0x1800301be  jmp     short loc_1800301DF
0x1800301c0  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x1800301c7  cmp     byte ptr [rax+30h], 0
0x1800301cb  jnz     short loc_1800301DF
0x1800301cd  cmp     byte ptr [rax+31h], 0
0x1800301d1  jnz     short loc_1800301DF
0x1800301d3  call    ?StopNtpProv@@YAJXZ; StopNtpProv(void)
0x1800301d8  jmp     short loc_1800301DF
0x1800301da  mov     ebx, 80070057h
0x1800301df  mov     rsi, [rsp+28h+arg_8]
0x1800301e4  mov     eax, ebx
0x1800301e6  mov     rbx, [rsp+28h+arg_0]
0x1800301eb  add     rsp, 20h
0x1800301ef  pop     rdi
0x1800301f0  retn
```
