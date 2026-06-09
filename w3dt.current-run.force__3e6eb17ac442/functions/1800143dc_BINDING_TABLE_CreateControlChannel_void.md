# BINDING_TABLE::CreateControlChannel(void)

- ea: `0x1800143dc`
- end: `0x18001450e`
- name: `?CreateControlChannel@BINDING_TABLE@@AEAAJXZ`
- size: `306`
- prototype: `__int64 __fastcall(BINDING_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001060`

## callees

- `0x1800130e8`
- `0x1800132cc`
- `0x1800143dc`
- `0x180015e08`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180014448`
- `iisutil!PuDbgPrint` at `0x1800144e5`
- `iisutil!PuDbgPrint` at `0x180014448`
- `iisutil!PuDbgPrint` at `0x1800144e5`

## string_xrefs

- `0x18001443c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800144de`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180014431`: `BINDING_TABLE::CreateControlChannel`
- `0x1800144cc`: `BINDING_TABLE::CreateControlChannel`
- `0x180014480`: `CreateControlChannel() failed. Error = %08x. Returning\n`
- `0x1800144c1`: `CreateConfigGroup failed. Error=%08x. Returning\n`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::CreateControlChannel(BINDING_TABLE *this)
{
  HTTP_WRAPPER *v1; // rdi
  unsigned int ControlChannel; // ebx
  const char *v4; // rax
  __int64 v5; // r8
  int ConfigGroup; // edi
  unsigned int v8; // [rsp+28h] [rbp-10h]

  v1 = (BINDING_TABLE *)((char *)this + 352);
  if ( *((_DWORD *)this + 91) != 1 )
  {
    ControlChannel = HTTP_WRAPPER::Initialize(v1);
    if ( ControlChannel )
    {
      if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 8) == 0 )
        goto LABEL_6;
      v4 = "Initialize() failed. Error = %08x. Returning\n";
      v5 = 388;
      goto LABEL_5;
    }
  }
  ControlChannel = HTTP_WRAPPER::CreateControlChannel(v1);
  if ( ControlChannel )
  {
    if ( (g_dwDebugFlags & 3) == 0 || (g_dwDebugFlags & 8) == 0 )
    {
LABEL_6:
      if ( (int)ControlChannel > 0 )
      {
        ControlChannel = (unsigned __int16)ControlChannel;
LABEL_17:
        ControlChannel |= 0x80070000;
        return ControlChannel;
      }
      return ControlChannel;
    }
    v4 = "CreateControlChannel() failed. Error = %08x. Returning\n";
    v5 = 409;
LABEL_5:
    v8 = ControlChannel;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
      v5,
      "BINDING_TABLE::CreateControlChannel",
      v4,
      v8);
    goto LABEL_6;
  }
  ControlChannel = 0;
  ConfigGroup = HTTP_WRAPPER::CreateConfigGroup(v1, (unsigned __int64 *)this + 48);
  if ( ConfigGroup )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        428,
        "BINDING_TABLE::CreateControlChannel",
        "CreateConfigGroup failed. Error=%08x. Returning\n",
        ConfigGroup);
    if ( ConfigGroup > 0 )
    {
      ControlChannel = (unsigned __int16)ConfigGroup;
      goto LABEL_17;
    }
    return (unsigned int)ConfigGroup;
  }
  return ControlChannel;
}

```

## disassembly

```asm
0x1800143dc  mov     [rsp+arg_0], rbx
0x1800143e1  mov     [rsp+arg_8], rsi
0x1800143e6  push    rdi
0x1800143e7  sub     rsp, 30h
0x1800143eb  lea     rdi, [rcx+160h]
0x1800143f2  mov     rsi, rcx
0x1800143f5  cmp     dword ptr [rdi+0Ch], 1
0x1800143f9  jz      short loc_18001445E
0x1800143fb  mov     rcx, rdi; this
0x1800143fe  call    ?Initialize@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::Initialize(void)
0x180014403  mov     ebx, eax
0x180014405  test    eax, eax
0x180014407  jz      short loc_18001445E
0x180014409  mov     eax, cs:g_dwDebugFlags
0x18001440f  test    al, 3
0x180014411  setnz   cl
0x180014414  test    al, 8
0x180014416  setnz   al
0x180014419  test    al, cl
0x18001441b  jz      short loc_18001444E
0x18001441d  lea     rax, aInitializeFail_0; "Initialize() failed. Error = %08x. Retu"...
0x180014424  mov     r8d, 184h
0x18001442a  mov     rcx, cs:g_pDebug
0x180014431  lea     r9, aBindingTableCr; "BINDING_TABLE::CreateControlChannel"
0x180014438  mov     [rsp+38h+var_10], ebx
0x18001443c  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180014443  mov     [rsp+38h+var_18], rax
0x180014448  call    cs:__imp_PuDbgPrint
0x18001444e  test    ebx, ebx
0x180014450  jle     loc_1800144FC
0x180014456  movzx   ebx, bx
0x180014459  jmp     loc_1800144F6
0x18001445e  mov     rcx, rdi; this
0x180014461  call    ?CreateControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CreateControlChannel(void)
0x180014466  mov     ebx, eax
0x180014468  test    eax, eax
0x18001446a  jz      short loc_18001448F
0x18001446c  mov     eax, cs:g_dwDebugFlags
0x180014472  test    al, 3
0x180014474  setnz   cl
0x180014477  test    al, 8
0x180014479  setnz   al
0x18001447c  test    al, cl
0x18001447e  jz      short loc_18001444E
0x180014480  lea     rax, aCreatecontrolc; "CreateControlChannel() failed. Error = "...
0x180014487  mov     r8d, 199h
0x18001448d  jmp     short loc_18001442A
0x18001448f  lea     rdx, [rsi+180h]; unsigned __int64 *
0x180014496  mov     rcx, rdi; this
0x180014499  xor     ebx, ebx
0x18001449b  call    ?CreateConfigGroup@HTTP_WRAPPER@@QEAAKPEA_K@Z; HTTP_WRAPPER::CreateConfigGroup(unsigned __int64 *)
0x1800144a0  mov     edi, eax
0x1800144a2  test    eax, eax
0x1800144a4  jz      short loc_1800144FC
0x1800144a6  mov     eax, cs:g_dwDebugFlags
0x1800144ac  test    al, 3
0x1800144ae  setnz   cl
0x1800144b1  test    al, 8
0x1800144b3  setnz   al
0x1800144b6  test    al, cl
0x1800144b8  jz      short loc_1800144EB
0x1800144ba  mov     rcx, cs:g_pDebug
0x1800144c1  lea     rax, aCreateconfiggr; "CreateConfigGroup failed. Error=%08x. R"...
0x1800144c8  mov     [rsp+38h+var_10], edi
0x1800144cc  lea     r9, aBindingTableCr; "BINDING_TABLE::CreateControlChannel"
0x1800144d3  mov     r8d, 1ACh
0x1800144d9  mov     [rsp+38h+var_18], rax
0x1800144de  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800144e5  call    cs:__imp_PuDbgPrint
0x1800144eb  test    edi, edi
0x1800144ed  jg      short loc_1800144F3
0x1800144ef  mov     ebx, edi
0x1800144f1  jmp     short loc_1800144FC
0x1800144f3  movzx   ebx, di
0x1800144f6  or      ebx, 80070000h
0x1800144fc  mov     rsi, [rsp+38h+arg_8]
0x180014501  mov     eax, ebx
0x180014503  mov     rbx, [rsp+38h+arg_0]
0x180014508  add     rsp, 30h
0x18001450c  pop     rdi
0x18001450d  retn
```
