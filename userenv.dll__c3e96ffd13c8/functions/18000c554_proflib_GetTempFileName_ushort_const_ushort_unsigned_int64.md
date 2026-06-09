# proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)

- ea: `0x18000c554`
- end: `0x18000c718`
- name: `?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z`
- size: `452`
- prototype: `__int64 __fastcall(proflib *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000c25c`

## callees

- `0x1800072a0`
- `0x1800080b4`
- `0x18000c554`
- `0x18000cf1c`
- `0x18000d080`
- `0x18000d9b0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000c5dd`
- `RPCRT4!UuidCreate` at `0x18000c5dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c6a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c6a7`
- `ntdll!RtlStringFromGUID` at `0x18000c617`
- `ntdll!RtlStringFromGUID` at `0x18000c617`
- `ntdll!NtClose` at `0x18000c6b6`
- `ntdll!NtClose` at `0x18000c6b6`
- `ntdll!RtlFreeUnicodeString` at `0x18000c65a`
- `ntdll!RtlFreeUnicodeString` at `0x18000c65a`

## string_xrefs

- `0x18000c6c6`: `Unable to open Tempory File Name: <%ws>.`
- `0x18000c6cd`: `onecore\ds\security\gina\profile\proflib\dir.cpp`

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
0x18000c554  mov     [rsp+arg_18], rbx
0x18000c559  push    rbp
0x18000c55a  push    rsi
0x18000c55b  push    rdi
0x18000c55c  sub     rsp, 70h
0x18000c560  mov     rax, cs:__security_cookie
0x18000c567  xor     rax, rsp
0x18000c56a  mov     [rsp+88h+var_28], rax
0x18000c56f  mov     rbp, r8
0x18000c572  mov     rdi, rdx
0x18000c575  mov     r8, rcx; unsigned __int16 *
0x18000c578  mov     rdx, rbp; unsigned __int64
0x18000c57b  mov     rcx, rdi; unsigned __int16 *
0x18000c57e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c583  mov     ebx, eax
0x18000c585  test    eax, eax
0x18000c587  js      loc_18000C6F9
0x18000c58d  lea     r8, [rsp+88h+GuidString]; unsigned __int64 *
0x18000c592  mov     qword ptr [rsp+88h+GuidString.Length], 0
0x18000c59b  mov     rdx, rbp; unsigned __int64
0x18000c59e  mov     rcx, rdi; unsigned __int16 *
0x18000c5a1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c5a6  mov     ebx, eax
0x18000c5a8  test    eax, eax
0x18000c5aa  js      loc_18000C6F9
0x18000c5b0  mov     rax, qword ptr [rsp+88h+GuidString.Length]
0x18000c5b5  lea     rsi, [rdi+rax*2]
0x18000c5b9  cmp     rsi, rdi
0x18000c5bc  jbe     short loc_18000C5D0
0x18000c5be  lea     rax, [rsi-2]
0x18000c5c2  cmp     word ptr [rax], 5Ch ; '\'
0x18000c5c6  jz      short loc_18000C5D0
0x18000c5c8  mov     rsi, rax
0x18000c5cb  cmp     rax, rdi
0x18000c5ce  ja      short loc_18000C5BE
0x18000c5d0  xorps   xmm0, xmm0
0x18000c5d3  lea     rcx, [rsp+88h+Uuid]; Uuid
0x18000c5d8  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x18000c5dd  call    cs:__imp_UuidCreate
0x18000c5e3  cmp     eax, 720h
0x18000c5e8  jz      short loc_18000C5FD
0x18000c5ea  test    eax, eax
0x18000c5ec  jz      short loc_18000C5FD
0x18000c5ee  jg      short loc_18000C5F4
0x18000c5f0  mov     ebx, eax
0x18000c5f2  jmp     short loc_18000C5FD
0x18000c5f4  movzx   ebx, ax
0x18000c5f7  or      ebx, 80070000h
0x18000c5fd  test    ebx, ebx
0x18000c5ff  js      loc_18000C6F9
0x18000c605  xorps   xmm0, xmm0
0x18000c608  lea     rdx, [rsp+88h+GuidString]; GuidString
0x18000c60d  lea     rcx, [rsp+88h+Uuid]; Guid
0x18000c612  movups  xmmword ptr [rsp+88h+GuidString.Length], xmm0
0x18000c617  call    cs:__imp_RtlStringFromGUID
0x18000c61d  test    eax, eax
0x18000c61f  js      loc_18000C6F4
0x18000c625  mov     rax, rsi
0x18000c628  mov     ecx, ebp
0x18000c62a  sub     rax, rdi
0x18000c62d  sar     rax, 1
0x18000c630  sub     ecx, eax
0x18000c632  movzx   eax, [rsp+88h+GuidString.MaximumLength]
0x18000c637  shr     eax, 1
0x18000c639  cmp     eax, ecx
0x18000c63b  ja      short loc_18000C650
0x18000c63d  mov     r8, [rsp+88h+GuidString.Buffer]; unsigned __int16 *
0x18000c642  mov     edx, ecx; unsigned __int64
0x18000c644  mov     rcx, rsi; unsigned __int16 *
0x18000c647  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c64c  mov     ebx, eax
0x18000c64e  jmp     short loc_18000C655
0x18000c650  mov     ebx, 8000FFFFh
0x18000c655  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x18000c65a  call    cs:__imp_RtlFreeUnicodeString
0x18000c660  test    ebx, ebx
0x18000c662  js      loc_18000C6F9
0x18000c668  lea     r8, aTmp; ".tmp"
0x18000c66f  mov     rdx, rbp; unsigned __int64
0x18000c672  mov     rcx, rdi; unsigned __int16 *
0x18000c675  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c67a  mov     ebx, eax
0x18000c67c  test    eax, eax
0x18000c67e  js      short loc_18000C6F9
0x18000c680  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000c689  xor     r9d, r9d; lpSecurityAttributes
0x18000c68c  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c694  xor     r8d, r8d; dwShareMode
0x18000c697  mov     edx, 80000000h; dwDesiredAccess
0x18000c69c  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x18000c6a4  mov     rcx, rdi; lpFileName
0x18000c6a7  call    cs:__imp_CreateFileW
0x18000c6ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c6b1  jz      short loc_18000C6BE
0x18000c6b3  mov     rcx, rax; Handle
0x18000c6b6  call    cs:__imp_NtClose
0x18000c6bc  jmp     short loc_18000C6F9
0x18000c6be  mov     rcx, [rsp+88h]; this
0x18000c6c6  lea     r9, aUnableToOpenTe; "Unable to open Tempory File Name: <%ws>"...
0x18000c6cd  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c6d4  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; char *
0x18000c6d9  mov     edx, 0A6h; void *
0x18000c6de  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000c6e3  mov     ebx, eax
0x18000c6e5  test    eax, eax
0x18000c6e7  jle     short loc_18000C6F9
0x18000c6e9  movzx   ebx, ax
0x18000c6ec  or      ebx, 80070000h
0x18000c6f2  jmp     short loc_18000C6F9
0x18000c6f4  mov     ebx, 8000FFFFh
0x18000c6f9  mov     eax, ebx
0x18000c6fb  mov     rcx, [rsp+88h+var_28]
0x18000c700  xor     rcx, rsp; StackCookie
0x18000c703  call    __security_check_cookie
0x18000c708  mov     rbx, [rsp+88h+arg_18]
0x18000c710  add     rsp, 70h
0x18000c714  pop     rdi
0x18000c715  pop     rsi
0x18000c716  pop     rbp
0x18000c717  retn
```
