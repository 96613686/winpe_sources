# proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)

- ea: `0x18000d108`
- end: `0x18000d2ef`
- name: `?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z`
- size: `487`
- prototype: `__int64 __fastcall(proflib *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000cdc4`

## callees

- `0x18000778c`
- `0x180007f80`
- `0x18000d108`
- `0x18000db88`
- `0x18000dcec`
- `0x18000e640`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000d191`
- `RPCRT4!UuidCreate` at `0x18000d191`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d271`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d271`
- `ntdll!RtlStringFromGUID` at `0x18000d1d1`
- `ntdll!RtlStringFromGUID` at `0x18000d1d1`
- `ntdll!NtClose` at `0x18000d286`
- `ntdll!NtClose` at `0x18000d286`
- `ntdll!RtlFreeUnicodeString` at `0x18000d21a`
- `ntdll!RtlFreeUnicodeString` at `0x18000d21a`

## string_xrefs

- `0x18000d29c`: `Unable to open Tempory File Name: <%ws>.`
- `0x18000d2a3`: `onecore\ds\security\gina\profile\proflib\dir.cpp`

## pseudocode

```c
__int64 __fastcall proflib::_GetTempFileName(proflib *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  signed int v5; // ebx
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rax
  RPC_STATUS v8; // eax
  unsigned int v9; // ecx
  HANDLE FileW; // rax
  int LastErrorMsg; // eax
  _UNICODE_STRING GuidString; // [rsp+40h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v5 = StringCchCopyW(a2, (unsigned __int64)a3, (const unsigned __int16 *)this);
  if ( v5 >= 0 )
  {
    *(_QWORD *)&GuidString.Length = 0;
    v5 = StringCchLengthW(a2, (unsigned __int64)a3, (unsigned __int64 *)&GuidString.Length);
    if ( v5 >= 0 )
    {
      v6 = &a2[*(_QWORD *)&GuidString.Length];
      if ( v6 > a2 )
      {
        do
        {
          v7 = (unsigned __int64)(v6 - 1);
          if ( *(v6 - 1) == 92 )
            break;
          --v6;
        }
        while ( v7 > (unsigned __int64)a2 );
      }
      Uuid = 0;
      v8 = UuidCreate(&Uuid);
      if ( v8 != 1824 && v8 )
      {
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
        else
          v5 = v8;
      }
      if ( v5 >= 0 )
      {
        GuidString = 0;
        if ( RtlStringFromGUID(&Uuid, &GuidString) < 0 )
        {
          return (unsigned int)-2147418113;
        }
        else
        {
          v9 = (_DWORD)a3 - (v6 - a2);
          if ( GuidString.MaximumLength >> 1 > v9 )
            v5 = -2147418113;
          else
            v5 = StringCchCopyW(v6, v9, GuidString.Buffer);
          RtlFreeUnicodeString(&GuidString);
          if ( v5 >= 0 )
          {
            v5 = StringCchCatW(a2, (unsigned __int64)a3, L".tmp");
            if ( v5 >= 0 )
            {
              FileW = CreateFileW(a2, 0x80000000, 0, 0, 1u, 0x80u, 0);
              if ( FileW == (HANDLE)-1LL )
              {
                LastErrorMsg = wil::details::in1diag3::Log_GetLastErrorMsg(
                                 retaddr,
                                 (void *)0xA6,
                                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                 "Unable to open Tempory File Name: <%ws>.",
                                 (const char *)a2);
                v5 = LastErrorMsg;
                if ( LastErrorMsg > 0 )
                  return (unsigned __int16)LastErrorMsg | 0x80070000;
              }
              else
              {
                NtClose(FileW);
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d108  mov     [rsp+arg_18], rbx
0x18000d10d  push    rbp
0x18000d10e  push    rsi
0x18000d10f  push    rdi
0x18000d110  sub     rsp, 70h
0x18000d114  mov     rax, cs:__security_cookie
0x18000d11b  xor     rax, rsp
0x18000d11e  mov     [rsp+88h+var_28], rax
0x18000d123  mov     rbp, r8
0x18000d126  mov     rdi, rdx
0x18000d129  mov     r8, rcx; unsigned __int16 *
0x18000d12c  mov     rdx, rbp; unsigned __int64
0x18000d12f  mov     rcx, rdi; unsigned __int16 *
0x18000d132  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d137  mov     ebx, eax
0x18000d139  test    eax, eax
0x18000d13b  js      loc_18000D2CF
0x18000d141  lea     r8, [rsp+88h+GuidString]; unsigned __int64 *
0x18000d146  mov     qword ptr [rsp+88h+GuidString.Length], 0
0x18000d14f  mov     rdx, rbp; unsigned __int64
0x18000d152  mov     rcx, rdi; unsigned __int16 *
0x18000d155  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000d15a  mov     ebx, eax
0x18000d15c  test    eax, eax
0x18000d15e  js      loc_18000D2CF
0x18000d164  mov     rax, qword ptr [rsp+88h+GuidString.Length]
0x18000d169  lea     rsi, [rdi+rax*2]
0x18000d16d  cmp     rsi, rdi
0x18000d170  jbe     short loc_18000D184
0x18000d172  lea     rax, [rsi-2]
0x18000d176  cmp     word ptr [rax], 5Ch ; '\'
0x18000d17a  jz      short loc_18000D184
0x18000d17c  mov     rsi, rax
0x18000d17f  cmp     rax, rdi
0x18000d182  ja      short loc_18000D172
0x18000d184  xorps   xmm0, xmm0
0x18000d187  lea     rcx, [rsp+88h+Uuid]; Uuid
0x18000d18c  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x18000d191  call    cs:__imp_UuidCreate
0x18000d198  nop     dword ptr [rax+rax+00h]
0x18000d19d  cmp     eax, 720h
0x18000d1a2  jz      short loc_18000D1B7
0x18000d1a4  test    eax, eax
0x18000d1a6  jz      short loc_18000D1B7
0x18000d1a8  jg      short loc_18000D1AE
0x18000d1aa  mov     ebx, eax
0x18000d1ac  jmp     short loc_18000D1B7
0x18000d1ae  movzx   ebx, ax
0x18000d1b1  or      ebx, 80070000h
0x18000d1b7  test    ebx, ebx
0x18000d1b9  js      loc_18000D2CF
0x18000d1bf  xorps   xmm0, xmm0
0x18000d1c2  lea     rdx, [rsp+88h+GuidString]; GuidString
0x18000d1c7  lea     rcx, [rsp+88h+Uuid]; Guid
0x18000d1cc  movups  xmmword ptr [rsp+88h+GuidString.Length], xmm0
0x18000d1d1  call    cs:__imp_RtlStringFromGUID
0x18000d1d8  nop     dword ptr [rax+rax+00h]
0x18000d1dd  test    eax, eax
0x18000d1df  js      loc_18000D2CA
0x18000d1e5  mov     rax, rsi
0x18000d1e8  mov     ecx, ebp
0x18000d1ea  sub     rax, rdi
0x18000d1ed  sar     rax, 1
0x18000d1f0  sub     ecx, eax
0x18000d1f2  movzx   eax, [rsp+88h+GuidString.MaximumLength]
0x18000d1f7  shr     eax, 1
0x18000d1f9  cmp     eax, ecx
0x18000d1fb  ja      short loc_18000D210
0x18000d1fd  mov     r8, [rsp+88h+GuidString.Buffer]; unsigned __int16 *
0x18000d202  mov     edx, ecx; unsigned __int64
0x18000d204  mov     rcx, rsi; unsigned __int16 *
0x18000d207  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d20c  mov     ebx, eax
0x18000d20e  jmp     short loc_18000D215
0x18000d210  mov     ebx, 8000FFFFh
0x18000d215  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x18000d21a  call    cs:__imp_RtlFreeUnicodeString
0x18000d221  nop     dword ptr [rax+rax+00h]
0x18000d226  test    ebx, ebx
0x18000d228  js      loc_18000D2CF
0x18000d22e  lea     r8, aTmp; ".tmp"
0x18000d235  mov     rdx, rbp; unsigned __int64
0x18000d238  mov     rcx, rdi; unsigned __int16 *
0x18000d23b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d240  mov     ebx, eax
0x18000d242  test    eax, eax
0x18000d244  js      loc_18000D2CF
0x18000d24a  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000d253  xor     r9d, r9d; lpSecurityAttributes
0x18000d256  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000d25e  xor     r8d, r8d; dwShareMode
0x18000d261  mov     edx, 80000000h; dwDesiredAccess
0x18000d266  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x18000d26e  mov     rcx, rdi; lpFileName
0x18000d271  call    cs:__imp_CreateFileW
0x18000d278  nop     dword ptr [rax+rax+00h]
0x18000d27d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d281  jz      short loc_18000D294
0x18000d283  mov     rcx, rax; Handle
0x18000d286  call    cs:__imp_NtClose
0x18000d28d  nop     dword ptr [rax+rax+00h]
0x18000d292  jmp     short loc_18000D2CF
0x18000d294  mov     rcx, [rsp+88h]; this
0x18000d29c  lea     r9, aUnableToOpenTe; "Unable to open Tempory File Name: <%ws>"...
0x18000d2a3  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d2aa  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; char *
0x18000d2af  mov     edx, 0A6h; void *
0x18000d2b4  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000d2b9  mov     ebx, eax
0x18000d2bb  test    eax, eax
0x18000d2bd  jle     short loc_18000D2CF
0x18000d2bf  movzx   ebx, ax
0x18000d2c2  or      ebx, 80070000h
0x18000d2c8  jmp     short loc_18000D2CF
0x18000d2ca  mov     ebx, 8000FFFFh
0x18000d2cf  mov     eax, ebx
0x18000d2d1  mov     rcx, [rsp+88h+var_28]
0x18000d2d6  xor     rcx, rsp; StackCookie
0x18000d2d9  call    __security_check_cookie
0x18000d2de  mov     rbx, [rsp+88h+arg_18]
0x18000d2e6  add     rsp, 70h
0x18000d2ea  pop     rdi
0x18000d2eb  pop     rsi
0x18000d2ec  pop     rbp
0x18000d2ed  retn
```
