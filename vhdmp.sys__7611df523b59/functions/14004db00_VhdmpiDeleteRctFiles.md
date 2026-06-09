# VhdmpiDeleteRctFiles

- ea: `0x14004db00`
- end: `0x14004dc90`
- name: `VhdmpiDeleteRctFiles`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14004c42c`
- `0x14004d820`
- `0x14004dc98`
- `0x14004dcf4`
- `0x14009e48c`
- `0x1400a1a6c`
- `0x1400af6d4`
- `0x1400b36d0`

## callees

- `0x140023560`
- `0x140035e94`
- `0x14004be04`
- `0x14004db00`
- `0x14009e1c0`
- `0x1400ebd40`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dbba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc57`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc67`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc77`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dbba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc57`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc67`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dc77`

## string_xrefs

- `0x14004dba0`: `VhdmpiDeleteRctFiles`
- `0x14004dc33`: `VhdmpiDeleteRctFiles`
- `0x14004db88`: `VhdmpiDeleteRctFiles: Unable to delete RCT file, status = 0x%08x`
- `0x14004dc1b`: `VhdmpiDeleteRctFiles: Unable to delete MRT file, status = 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiDeleteRctFiles(const UNICODE_STRING *a1)
{
  __int64 result; // rax
  int v2; // ebx
  int v3; // eax
  int v4; // edi
  int v5; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING v7; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING v8; // [rsp+50h] [rbp-18h] BYREF

  v8 = 0;
  v7 = 0;
  UnicodeString = 0;
  result = VhdmpiGetRctFileNames(a1, &v8, &v7);
  if ( (int)result >= 0 )
  {
    v2 = VhdmpiCreateNtFilePath(&v8, &UnicodeString);
    if ( v2 >= 0 )
    {
      v3 = VhdmpiDeleteFile(&UnicodeString);
      v2 = v3;
      if ( v3 == -1073741772 || v3 == -1073741766 )
      {
        v2 = 0;
      }
      else if ( v3 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x20000) )
      {
        TraceEvents(
          "VhdmpiDeleteRctFiles",
          0x428u,
          2u,
          0x20000u,
          "VhdmpiDeleteRctFiles: Unable to delete RCT file, status = 0x%08x",
          v2);
      }
    }
    RtlFreeUnicodeString(&UnicodeString);
    UnicodeString = 0;
    v4 = VhdmpiCreateNtFilePath(&v7, &UnicodeString);
    if ( v4 >= 0 )
    {
      v5 = VhdmpiDeleteFile(&UnicodeString);
      v4 = v5;
      if ( v5 == -1073741772 || v5 == -1073741766 )
      {
        v4 = 0;
      }
      else if ( v5 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x20000) )
      {
        TraceEvents(
          "VhdmpiDeleteRctFiles",
          0x440u,
          2u,
          0x20000u,
          "VhdmpiDeleteRctFiles: Unable to delete MRT file, status = 0x%08x",
          v4);
      }
    }
    if ( v2 >= 0 || v4 >= 0 )
      v2 = 0;
    RtlFreeUnicodeString(&v7);
    RtlFreeUnicodeString(&v8);
    RtlFreeUnicodeString(&UnicodeString);
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x14004db00  push    rbp
0x14004db02  push    rbx
0x14004db03  push    rdi
0x14004db04  push    r14
0x14004db06  mov     rbp, rsp
0x14004db09  sub     rsp, 68h
0x14004db0d  xorps   xmm0, xmm0
0x14004db10  lea     r8, [rbp+var_28]; struct _UNICODE_STRING *
0x14004db14  xorps   xmm1, xmm1
0x14004db17  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x14004db1b  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x14004db1f  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x14004db23  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14004db27  call    ?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14004db2c  test    eax, eax
0x14004db2e  js      loc_14004DC85
0x14004db34  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x14004db38  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING *
0x14004db3c  call    VhdmpiCreateNtFilePath
0x14004db41  mov     ebx, eax
0x14004db43  mov     r14d, 20000h
0x14004db49  test    eax, eax
0x14004db4b  js      short loc_14004DBB6
0x14004db4d  lea     rcx, [rbp+UnicodeString]; char
0x14004db51  call    VhdmpiDeleteFile
0x14004db56  mov     ebx, eax
0x14004db58  cmp     eax, 0C0000034h
0x14004db5d  jz      short loc_14004DBB4
0x14004db5f  cmp     eax, 0C000003Ah
0x14004db64  jz      short loc_14004DBB4
0x14004db66  test    eax, eax
0x14004db68  jns     short loc_14004DBB6
0x14004db6a  mov     eax, cs:dword_140087708
0x14004db70  cmp     eax, 2
0x14004db73  jbe     short loc_14004DBB6
0x14004db75  mov     edx, r14d
0x14004db78  lea     rcx, dword_140087708
0x14004db7f  call    _tlgKeywordOn
0x14004db84  test    al, al
0x14004db86  jz      short loc_14004DBB6
0x14004db88  lea     rax, aVhdmpideleterc; "VhdmpiDeleteRctFiles: Unable to delete "...
0x14004db8f  mov     dword ptr [rsp+68h+var_40], ebx; char
0x14004db93  mov     edx, 428h; int
0x14004db98  mov     [rsp+68h+var_48], rax; char *
0x14004db9d  mov     r9d, r14d; int
0x14004dba0  lea     rcx, aVhdmpideleterc_1; "VhdmpiDeleteRctFiles"
0x14004dba7  mov     r8d, 2; int
0x14004dbad  call    TraceEvents
0x14004dbb2  jmp     short loc_14004DBB6
0x14004dbb4  xor     ebx, ebx
0x14004dbb6  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14004dbba  call    cs:__imp_RtlFreeUnicodeString
0x14004dbc1  nop     dword ptr [rax+rax+00h]
0x14004dbc6  xorps   xmm0, xmm0
0x14004dbc9  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x14004dbcd  lea     rcx, [rbp+var_28]; struct _UNICODE_STRING *
0x14004dbd1  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14004dbd5  call    VhdmpiCreateNtFilePath
0x14004dbda  mov     edi, eax
0x14004dbdc  test    eax, eax
0x14004dbde  js      short loc_14004DC49
0x14004dbe0  lea     rcx, [rbp+UnicodeString]; char
0x14004dbe4  call    VhdmpiDeleteFile
0x14004dbe9  mov     edi, eax
0x14004dbeb  cmp     eax, 0C0000034h
0x14004dbf0  jz      short loc_14004DC47
0x14004dbf2  cmp     eax, 0C000003Ah
0x14004dbf7  jz      short loc_14004DC47
0x14004dbf9  test    eax, eax
0x14004dbfb  jns     short loc_14004DC49
0x14004dbfd  mov     eax, cs:dword_140087708
0x14004dc03  cmp     eax, 2
0x14004dc06  jbe     short loc_14004DC49
0x14004dc08  mov     rdx, r14
0x14004dc0b  lea     rcx, dword_140087708
0x14004dc12  call    _tlgKeywordOn
0x14004dc17  test    al, al
0x14004dc19  jz      short loc_14004DC49
0x14004dc1b  lea     rax, aVhdmpideleterc_0; "VhdmpiDeleteRctFiles: Unable to delete "...
0x14004dc22  mov     dword ptr [rsp+68h+var_40], edi; char
0x14004dc26  mov     edx, 440h; int
0x14004dc2b  mov     [rsp+68h+var_48], rax; char *
0x14004dc30  mov     r9d, r14d; int
0x14004dc33  lea     rcx, aVhdmpideleterc_1; "VhdmpiDeleteRctFiles"
0x14004dc3a  mov     r8d, 2; int
0x14004dc40  call    TraceEvents
0x14004dc45  jmp     short loc_14004DC49
0x14004dc47  xor     edi, edi
0x14004dc49  test    ebx, ebx
0x14004dc4b  jns     short loc_14004DC51
0x14004dc4d  test    edi, edi
0x14004dc4f  js      short loc_14004DC53
0x14004dc51  xor     ebx, ebx
0x14004dc53  lea     rcx, [rbp+var_28]; UnicodeString
0x14004dc57  call    cs:__imp_RtlFreeUnicodeString
0x14004dc5e  nop     dword ptr [rax+rax+00h]
0x14004dc63  lea     rcx, [rbp+var_18]; UnicodeString
0x14004dc67  call    cs:__imp_RtlFreeUnicodeString
0x14004dc6e  nop     dword ptr [rax+rax+00h]
0x14004dc73  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14004dc77  call    cs:__imp_RtlFreeUnicodeString
0x14004dc7e  nop     dword ptr [rax+rax+00h]
0x14004dc83  mov     eax, ebx
0x14004dc85  add     rsp, 68h
0x14004dc89  pop     r14
0x14004dc8b  pop     rdi
0x14004dc8c  pop     rbx
0x14004dc8d  pop     rbp
0x14004dc8e  retn
```
