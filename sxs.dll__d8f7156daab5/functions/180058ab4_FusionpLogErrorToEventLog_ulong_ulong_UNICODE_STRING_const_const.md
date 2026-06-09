# FusionpLogErrorToEventLog(ulong,ulong,_UNICODE_STRING const * const *)

- ea: `0x180058ab4`
- end: `0x180058caf`
- name: `?FusionpLogErrorToEventLog@@YAJKKPEBQEBU_UNICODE_STRING@@@Z`
- size: `507`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, const struct _UNICODE_STRING *const *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002e4a0`
- `0x180058904`

## callees

- `0x18000c000`
- `0x180013af0`
- `0x180051a20`
- `0x180051d60`
- `0x180058ab4`
- `0x180058cb8`
- `0x180069f04`
- `0x18006a0c5`
- `0x18006a0f5`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058c75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058c75`
- `ADVAPI32!ReportEventW` at `0x180058c2c`
- `ADVAPI32!ReportEventW` at `0x180058c2c`

## string_xrefs

- `0x180058c46`: `SXS.DLL: FusionpLogError/ElfReportEventW failed %lx\n`

## pseudocode

```c
__int64 __fastcall FusionpLogErrorToEventLog(unsigned int a1, __int64 a2, const struct _UNICODE_STRING *const *a3)
{
  int v5; // eax
  DWORD v6; // esi
  unsigned int v7; // edi
  WORD v8; // bp
  unsigned int i; // r14d
  const struct _UNICODE_STRING *v10; // rax
  unsigned __int64 Length; // r8
  PWSTR *p_Buffer; // rdx
  const WCHAR *v13; // rax
  int v14; // eax
  LPCWSTR Strings[20]; // [rsp+50h] [rbp-2CA8h] BYREF
  _BYTE v17[11200]; // [rsp+F0h] [rbp-2C08h] BYREF

  v5 = FusionpEventIdToError(a1);
  v6 = v5;
  if ( v5 > 0 )
  {
    v7 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 == 1455 || v5 == 14 )
      goto LABEL_25;
  }
  else
  {
    v7 = v5;
  }
  if ( a1 >> 30 )
  {
    if ( a1 >> 30 == 1 )
    {
      v8 = 4;
    }
    else if ( a1 >> 30 == 2 )
    {
      v8 = 2;
    }
    else
    {
      v8 = 1;
    }
  }
  else
  {
    v8 = 0;
  }
  if ( FusionpOpenEventLog() )
  {
    memset_0(Strings, 0, sizeof(Strings));
    `vector constructor iterator'(
      v17,
      0x230u,
      0x14u,
      CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>);
    for ( i = 0; i < 0x14; ++i )
    {
      v10 = a3[i];
      Length = v10->Length;
      p_Buffer = &v10->Buffer;
      if ( v10->MaximumLength <= (unsigned __int16)Length || (*p_Buffer)[(unsigned __int64)v10->Length >> 1] )
      {
        CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(&v17[560 * i], *p_Buffer, Length >> 1);
        v13 = *(const WCHAR **)&v17[560 * i + 16];
        Strings[i] = v13;
        if ( !v13 )
          goto LABEL_24;
      }
      else
      {
        Strings[i] = *p_Buffer;
      }
    }
    v14 = ReportEventW(g_hEventLog, v8, 0, a1, 0, 0x14u, 0, Strings, 0);
    if ( v14 && v14 != 1722 )
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: FusionpLogError/ElfReportEventW failed %lx\n", v14);
LABEL_24:
    `vector destructor iterator'(
      v17,
      0x230u,
      0x14u,
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>);
  }
LABEL_25:
  SetLastError(v6);
  return v7;
}

```

## disassembly

```asm
0x180058ab4  mov     [rsp+arg_8], rbx
0x180058ab9  push    rbp
0x180058aba  push    rsi
0x180058abb  push    rdi
0x180058abc  push    r12
0x180058abe  push    r13
0x180058ac0  push    r14
0x180058ac2  push    r15
0x180058ac4  mov     eax, 2CC0h
0x180058ac9  call    __chkstk_0
0x180058ace  sub     rsp, rax
0x180058ad1  mov     rax, cs:__security_cookie
0x180058ad8  xor     rax, rsp
0x180058adb  mov     [rsp+2CF8h+var_48], rax
0x180058ae3  mov     r13, r8
0x180058ae6  mov     r12d, ecx
0x180058ae9  call    ?FusionpEventIdToError@@YAKK@Z; FusionpEventIdToError(ulong)
0x180058aee  xor     ebx, ebx
0x180058af0  mov     esi, eax
0x180058af2  test    eax, eax
0x180058af4  jg      short loc_180058AFA
0x180058af6  mov     edi, eax
0x180058af8  jmp     short loc_180058B18
0x180058afa  movzx   edi, si
0x180058afd  or      edi, 80070000h
0x180058b03  cmp     esi, 5AFh
0x180058b09  jz      loc_180058C73
0x180058b0f  cmp     esi, 0Eh
0x180058b12  jz      loc_180058C73
0x180058b18  mov     eax, r12d
0x180058b1b  mov     ecx, 1
0x180058b20  shr     eax, 1Eh
0x180058b23  test    eax, eax
0x180058b25  jz      short loc_180058B42
0x180058b27  sub     eax, ecx
0x180058b29  jz      short loc_180058B3B
0x180058b2b  cmp     eax, ecx
0x180058b2d  jz      short loc_180058B34
0x180058b2f  movzx   ebp, cx
0x180058b32  jmp     short loc_180058B44
0x180058b34  mov     ebp, 2
0x180058b39  jmp     short loc_180058B44
0x180058b3b  mov     ebp, 4
0x180058b40  jmp     short loc_180058B44
0x180058b42  mov     ebp, ebx
0x180058b44  call    ?FusionpOpenEventLog@@YAHXZ; FusionpOpenEventLog(void)
0x180058b49  test    eax, eax
0x180058b4b  jz      loc_180058C73
0x180058b51  xor     edx, edx; Val
0x180058b53  lea     rcx, [rsp+2CF8h+Strings]; void *
0x180058b58  mov     r8d, 0A0h; Size
0x180058b5e  call    memset_0
0x180058b63  mov     r15d, 14h
0x180058b69  lea     r9, ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; void *(*)(void *)
0x180058b70  mov     r8d, r15d; unsigned __int64
0x180058b73  lea     rcx, [rsp+2CF8h+var_2C08]; void *
0x180058b7b  mov     edx, 230h; unsigned __int64
0x180058b80  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180058b85  mov     r14d, ebx
0x180058b88  cmp     r14d, r15d
0x180058b8b  jnb     short loc_180058BFE
0x180058b8d  mov     r15d, r14d
0x180058b90  mov     rax, [r13+r15*8+0]
0x180058b95  movzx   r8d, word ptr [rax]
0x180058b99  lea     rdx, [rax+8]
0x180058b9d  cmp     [rax+2], r8w
0x180058ba2  jbe     short loc_180058BBA
0x180058ba4  mov     rcx, [rdx]
0x180058ba7  mov     eax, r8d
0x180058baa  shr     rax, 1
0x180058bad  cmp     [rcx+rax*2], bx
0x180058bb1  jnz     short loc_180058BBA
0x180058bb3  mov     [rsp+r15*8+2CF8h+Strings], rcx
0x180058bb8  jmp     short loc_180058BEB
0x180058bba  mov     rdx, [rdx]
0x180058bbd  lea     rcx, [rsp+2CF8h+var_2C08]
0x180058bc5  imul    rbx, r15, 230h
0x180058bcc  shr     r8, 1
0x180058bcf  add     rcx, rbx
0x180058bd2  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x180058bd7  mov     rax, [rsp+rbx+2CF8h+var_2BF8]
0x180058bdf  xor     ebx, ebx
0x180058be1  mov     [rsp+r15*8+2CF8h+Strings], rax
0x180058be6  test    rax, rax
0x180058be9  jz      short loc_180058BF6
0x180058beb  inc     r14d
0x180058bee  mov     r15d, 14h
0x180058bf4  jmp     short loc_180058B88
0x180058bf6  mov     r8d, 14h
0x180058bfc  jmp     short loc_180058C5A
0x180058bfe  mov     rcx, cs:?g_hEventLog@@3PEAXEA; hEventLog
0x180058c05  lea     rax, [rsp+2CF8h+Strings]
0x180058c0a  mov     [rsp+2CF8h+lpRawData], rbx; lpRawData
0x180058c0f  xor     r8d, r8d; wCategory
0x180058c12  mov     [rsp+2CF8h+lpStrings], rax; lpStrings
0x180058c17  mov     r9d, r12d; dwEventID
0x180058c1a  mov     [rsp+2CF8h+dwDataSize], ebx; dwDataSize
0x180058c1e  movzx   edx, bp; wType
0x180058c21  mov     [rsp+2CF8h+wNumStrings], r15w; wNumStrings
0x180058c27  mov     [rsp+2CF8h+lpUserSid], rbx; lpUserSid
0x180058c2c  call    cs:__imp_ReportEventW
0x180058c33  nop     dword ptr [rax+rax+00h]
0x180058c38  test    eax, eax
0x180058c3a  jz      short loc_180058C57
0x180058c3c  cmp     eax, 6BAh
0x180058c41  jz      short loc_180058C57
0x180058c43  mov     r8d, eax
0x180058c46  lea     rdx, aSxsDllFusionpl_0; "SXS.DLL: FusionpLogError/ElfReportEvent"...
0x180058c4d  mov     ecx, 0C0000000h; unsigned int
0x180058c52  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180058c57  mov     r8, r15; unsigned __int64
0x180058c5a  lea     r9, ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; void (*)(void *)
0x180058c61  mov     edx, 230h; unsigned __int64
0x180058c66  lea     rcx, [rsp+2CF8h+var_2C08]; void *
0x180058c6e  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180058c73  mov     ecx, esi; dwErrCode
0x180058c75  call    cs:__imp_SetLastError
0x180058c7c  nop     dword ptr [rax+rax+00h]
0x180058c81  mov     eax, edi
0x180058c83  mov     rcx, [rsp+2CF8h+var_48]
0x180058c8b  xor     rcx, rsp; StackCookie
0x180058c8e  call    __security_check_cookie
0x180058c93  mov     rbx, [rsp+2CF8h+arg_8]
0x180058c9b  add     rsp, 2CC0h
0x180058ca2  pop     r15
0x180058ca4  pop     r14
0x180058ca6  pop     r13
0x180058ca8  pop     r12
0x180058caa  pop     rdi
0x180058cab  pop     rsi
0x180058cac  pop     rbp
0x180058cad  retn
```
