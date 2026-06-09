# CTrace::Initialize(ushort const *,int)

- ea: `0x1800144e4`
- end: `0x180014656`
- name: `?Initialize@CTrace@@QEAAKPEBGH@Z`
- size: `370`
- prototype: `unsigned int __fastcall(CTrace *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008780`

## callees

- `0x18000752c`
- `0x1800085fc`
- `0x180013d50`
- `0x1800144e4`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`
- `0x180015c9d`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x1800145a4`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800145a4`
- `KERNEL32!GetLastError` at `0x1800145ae`
- `KERNEL32!GetLastError` at `0x1800145cd`
- `KERNEL32!GetLastError` at `0x1800145f2`
- `KERNEL32!GetLastError` at `0x1800145ae`
- `KERNEL32!GetLastError` at `0x1800145cd`
- `KERNEL32!GetLastError` at `0x1800145f2`
- `KERNEL32!GetCurrentProcessId` at `0x180014537`
- `KERNEL32!GetCurrentProcessId` at `0x180014537`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800145c3`
- `KERNEL32!SetEnvironmentVariableW` at `0x1800145c3`

## string_xrefs

- `0x18001455c`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`
- `0x1800145db`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`

## pseudocode

```c
__int64 __fastcall CTrace::Initialize(CTrace *this, const unsigned __int16 *a2)
{
  WCHAR *v2; // rsi
  unsigned int v3; // ebx
  DWORD CurrentProcessId; // eax
  int v5; // edi
  const char *v6; // rdx
  DWORD LastError; // eax
  const char *v8; // rdx
  unsigned int v9; // r9d
  WCHAR Name[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-228h] BYREF

  v2 = (WCHAR *)L"WDSDCMGR";
  v3 = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  CurrentProcessId = GetCurrentProcessId();
  v5 = StringCchPrintfW(Name, 0x104u, L"WDS_TRACING_%u", CurrentProcessId);
  if ( (int)ElValidateHr(v5, v6, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp", 0xE5u) < 0 )
  {
    if ( v5 < 0 && (v5 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v5;
    else
      return (unsigned int)v5;
  }
  if ( GetEnvironmentVariableW(Name, Buffer, 0x104u) )
  {
    v2 = Buffer;
  }
  else
  {
    if ( GetLastError() != 203 )
    {
      LastError = GetLastError();
      v9 = 249;
LABEL_10:
      v3 = ElValidateWin32(LastError, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp", v9);
      if ( !v3 )
        return 31;
      return v3;
    }
    if ( !SetEnvironmentVariableW(Name, L"WDSDCMGR") )
    {
      LastError = GetLastError();
      v9 = 244;
      goto LABEL_10;
    }
  }
  s_Trace = WcsDup(v2);
  if ( s_Trace )
  {
    if ( qword_18001DD80 )
      McGenEventRegister();
  }
  else
  {
    return 8;
  }
  return v3;
}

```

## disassembly

```asm
0x1800144e4  mov     [rsp+arg_0], rbx
0x1800144e9  mov     [rsp+arg_8], rsi
0x1800144ee  push    rdi
0x1800144ef  sub     rsp, 450h
0x1800144f6  mov     rax, cs:__security_cookie
0x1800144fd  xor     rax, rsp
0x180014500  mov     [rsp+458h+var_18], rax
0x180014508  mov     edi, 208h
0x18001450d  lea     rcx, [rsp+458h+Name]; void *
0x180014512  mov     r8d, edi; Size
0x180014515  lea     rsi, Src; "WDSDCMGR"
0x18001451c  xor     edx, edx; Val
0x18001451e  xor     ebx, ebx
0x180014520  call    memset_0
0x180014525  mov     r8d, edi; Size
0x180014528  lea     rcx, [rsp+458h+Buffer]; void *
0x180014530  xor     edx, edx; Val
0x180014532  call    memset_0
0x180014537  call    cs:__imp_GetCurrentProcessId
0x18001453d  lea     r8, aWdsTracingU; "WDS_TRACING_%u"
0x180014544  mov     edx, 104h; unsigned __int64
0x180014549  mov     r9d, eax
0x18001454c  lea     rcx, [rsp+458h+Name]; Buffer
0x180014551  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014556  mov     r9d, 0E5h; unsigned int
0x18001455c  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180014563  mov     ecx, eax; int
0x180014565  mov     edi, eax
0x180014567  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18001456c  test    eax, eax
0x18001456e  jns     short loc_180014591
0x180014570  test    edi, edi
0x180014572  jns     short loc_18001458A
0x180014574  mov     eax, edi
0x180014576  and     eax, 1FFF0000h
0x18001457b  cmp     eax, 70000h
0x180014580  jnz     short loc_18001458A
0x180014582  movzx   ebx, di
0x180014585  jmp     loc_18001462F
0x18001458a  mov     ebx, edi
0x18001458c  jmp     loc_18001462F
0x180014591  mov     r8d, 104h; nSize
0x180014597  lea     rdx, [rsp+458h+Buffer]; lpBuffer
0x18001459f  lea     rcx, [rsp+458h+Name]; lpName
0x1800145a4  call    cs:__imp_GetEnvironmentVariableW
0x1800145aa  test    eax, eax
0x1800145ac  jnz     short loc_180014600
0x1800145ae  call    cs:__imp_GetLastError
0x1800145b4  cmp     eax, 0CBh
0x1800145b9  jnz     short loc_1800145F2
0x1800145bb  mov     rdx, rsi; lpValue
0x1800145be  lea     rcx, [rsp+458h+Name]; lpName
0x1800145c3  call    cs:__imp_SetEnvironmentVariableW
0x1800145c9  test    eax, eax
0x1800145cb  jnz     short loc_180014608
0x1800145cd  call    cs:__imp_GetLastError
0x1800145d3  mov     r9d, 0F4h; unsigned int
0x1800145d9  mov     ecx, eax; unsigned int
0x1800145db  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800145e2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800145e7  mov     ebx, eax
0x1800145e9  test    eax, eax
0x1800145eb  jnz     short loc_18001462F
0x1800145ed  lea     ebx, [rax+1Fh]
0x1800145f0  jmp     short loc_18001462F
0x1800145f2  call    cs:__imp_GetLastError
0x1800145f8  mov     r9d, 0F9h
0x1800145fe  jmp     short loc_1800145D9
0x180014600  lea     rsi, [rsp+458h+Buffer]
0x180014608  mov     rcx, rsi; Src
0x18001460b  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x180014610  mov     cs:?s_Trace@@3VCTrace@@A, rax; CTrace s_Trace
0x180014617  test    rax, rax
0x18001461a  jnz     short loc_180014621
0x18001461c  lea     ebx, [rax+8]
0x18001461f  jmp     short loc_18001462F
0x180014621  cmp     cs:qword_18001DD80, rbx
0x180014628  jz      short loc_18001462F
0x18001462a  call    McGenEventRegister
0x18001462f  mov     eax, ebx
0x180014631  mov     rcx, [rsp+458h+var_18]
0x180014639  xor     rcx, rsp; StackCookie
0x18001463c  call    __security_check_cookie
0x180014641  lea     r11, [rsp+458h+var_8]
0x180014649  mov     rbx, [r11+10h]
0x18001464d  mov     rsi, [r11+18h]
0x180014651  mov     rsp, r11
0x180014654  pop     rdi
0x180014655  retn
```
