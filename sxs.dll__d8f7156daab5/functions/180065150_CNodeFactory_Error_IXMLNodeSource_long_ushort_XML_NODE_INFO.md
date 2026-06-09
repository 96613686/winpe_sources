# CNodeFactory::Error(IXMLNodeSource *,long,ushort,_XML_NODE_INFO * *)

- ea: `0x180065150`
- end: `0x18006523a`
- name: `?Error@CNodeFactory@@UEAAJPEAUIXMLNodeSource@@JGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, struct IXMLNodeSource *, int, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x180030148`
- `0x1800515ec`
- `0x180065150`
- `0x180068380`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065189`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800651c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800651c1`

## string_xrefs

- `0x1800651e5`: `SXS.DLL: Unknown XML parser error 0x%x in file %S line %d!!!\n`

## pseudocode

```c
__int64 __fastcall CNodeFactory::Error(const wchar_t **this, struct IXMLNodeSource *a2, int a3)
{
  DWORD LastError; // ebx
  int v6; // eax
  const struct _UNICODE_STRING *v8; // [rsp+30h] [rbp-A8h]
  const struct _UNICODE_STRING *v9; // [rsp+38h] [rbp-A0h]
  const struct _UNICODE_STRING *v10; // [rsp+40h] [rbp-98h]
  const struct _UNICODE_STRING *v11; // [rsp+48h] [rbp-90h]
  const struct _UNICODE_STRING *v12; // [rsp+50h] [rbp-88h]
  const struct _UNICODE_STRING *v13; // [rsp+58h] [rbp-80h]
  const struct _UNICODE_STRING *v14; // [rsp+60h] [rbp-78h]
  const struct _UNICODE_STRING *v15; // [rsp+68h] [rbp-70h]
  const struct _UNICODE_STRING *v16; // [rsp+70h] [rbp-68h]
  const struct _UNICODE_STRING *v17; // [rsp+78h] [rbp-60h]
  const struct _UNICODE_STRING *v18; // [rsp+80h] [rbp-58h]
  const struct _UNICODE_STRING *v19; // [rsp+88h] [rbp-50h]
  const struct _UNICODE_STRING *v20; // [rsp+90h] [rbp-48h]
  const struct _UNICODE_STRING *v21; // [rsp+98h] [rbp-40h]
  const struct _UNICODE_STRING *v22; // [rsp+A0h] [rbp-38h]
  const struct _UNICODE_STRING *v23; // [rsp+A8h] [rbp-30h]
  const struct _UNICODE_STRING *v24; // [rsp+B0h] [rbp-28h]
  int v25; // [rsp+C0h] [rbp-18h] BYREF

  v25 = a3;
  if ( (unsigned int)(a3 + 1072896768) > 0x87 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *))(*(_QWORD *)a2 + 48LL))(a2);
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Unknown XML parser error 0x%x in file %S line %d!!!\n", a3, this[56], v6);
  }
  else
  {
    LastError = GetLastError();
    CNodeFactory::LogParseError(
      (CNodeFactory *)this,
      0xC101003B,
      0x91u,
      0,
      0,
      0,
      v8,
      v9,
      v10,
      v11,
      v12,
      v13,
      v14,
      v15,
      v16,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23,
      v24);
    SetLastError(LastError);
  }
  FusionpConvertCOMFailure(&v25);
  FusionpSetLastErrorFromHRESULT(v25);
  return 0;
}

```

## disassembly

```asm
0x180065150  mov     r11, rsp
0x180065153  mov     [r11+20h], rbx
0x180065157  push    rdi
0x180065158  sub     rsp, 0D0h
0x18006515f  mov     rax, cs:__security_cookie
0x180065166  xor     rax, rsp
0x180065169  mov     [rsp+0D8h+var_10], rax
0x180065171  lea     eax, [r8+3FF31B00h]
0x180065178  mov     ebx, r8d
0x18006517b  mov     [r11-18h], ebx
0x18006517f  mov     rdi, rcx
0x180065182  cmp     eax, 87h
0x180065187  ja      short loc_1800651CF
0x180065189  call    cs:__imp_GetLastError
0x180065190  nop     dword ptr [rax+rax+00h]
0x180065195  xor     r9d, r9d; struct _UNICODE_STRING *
0x180065198  mov     [rsp+0D8h+var_B0], 0; struct _UNICODE_STRING *
0x1800651a1  mov     edx, 0C101003Bh; unsigned int
0x1800651a6  mov     [rsp+0D8h+var_B8], 0; struct _UNICODE_STRING *
0x1800651af  mov     r8d, 91h; unsigned int
0x1800651b5  mov     rcx, rdi; this
0x1800651b8  mov     ebx, eax
0x1800651ba  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800651bf  mov     ecx, ebx; dwErrCode
0x1800651c1  call    cs:__imp_SetLastError
0x1800651c8  nop     dword ptr [rax+rax+00h]
0x1800651cd  jmp     short loc_1800651FD
0x1800651cf  mov     rax, [rdx]
0x1800651d2  mov     rcx, rdx
0x1800651d5  mov     rax, [rax+30h]
0x1800651d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651de  mov     r9, [rdi+1C0h]
0x1800651e5  lea     rdx, aSxsDllUnknownX_0; "SXS.DLL: Unknown XML parser error 0x%x "...
0x1800651ec  mov     r8d, ebx
0x1800651ef  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1800651f3  mov     ecx, 0C0000000h; unsigned int
0x1800651f8  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800651fd  lea     rcx, [rsp+0D8h+var_18]; int *
0x180065205  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18006520a  mov     ecx, [rsp+0D8h+var_18]; int
0x180065211  call    ?FusionpSetLastErrorFromHRESULT@@YAXJ@Z; FusionpSetLastErrorFromHRESULT(long)
0x180065216  xor     eax, eax
0x180065218  mov     rcx, [rsp+0D8h+var_10]
0x180065220  xor     rcx, rsp; StackCookie
0x180065223  call    __security_check_cookie
0x180065228  mov     rbx, [rsp+0D8h+arg_18]
0x180065230  add     rsp, 0D0h
0x180065237  pop     rdi
0x180065238  retn
```
