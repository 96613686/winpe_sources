# VhdmpiDeleteRctFiles

- ea: `0x14004def0`
- end: `0x14004e080`
- name: `VhdmpiDeleteRctFiles`
- size: `400`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14004c81c`
- `0x14004dc10`
- `0x14004e088`
- `0x14004e0e4`
- `0x14009e48c`
- `0x1400a1a6c`
- `0x1400af6d4`
- `0x1400b36d0`

## callees

- `0x140023980`
- `0x140036284`
- `0x14004c1f4`
- `0x14004def0`
- `0x14009e1c0`
- `0x1400ebcd0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dfaa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e047`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e057`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e067`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004dfaa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e047`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e057`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e067`

## string_xrefs

- `0x14004df78`: `VhdmpiDeleteRctFiles: Unable to delete RCT file, status = 0x%08x`
- `0x14004e00b`: `VhdmpiDeleteRctFiles: Unable to delete MRT file, status = 0x%08x`
- `0x14004df90`: `VhdmpiDeleteRctFiles`
- `0x14004e023`: `VhdmpiDeleteRctFiles`

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
      else if ( v3 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x20000) )
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
      else if ( v5 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x20000) )
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
0x14004def0  push    rbp
0x14004def2  push    rbx
0x14004def3  push    rdi
0x14004def4  push    r14
0x14004def6  mov     rbp, rsp
0x14004def9  sub     rsp, 68h
0x14004defd  xorps   xmm0, xmm0
0x14004df00  lea     r8, [rbp+var_28]; struct _UNICODE_STRING *
0x14004df04  xorps   xmm1, xmm1
0x14004df07  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x14004df0b  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x14004df0f  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x14004df13  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14004df17  call    ?VhdmpiGetRctFileNames@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; VhdmpiGetRctFileNames(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14004df1c  test    eax, eax
0x14004df1e  js      loc_14004E075
0x14004df24  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x14004df28  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING *
0x14004df2c  call    VhdmpiCreateNtFilePath
0x14004df31  mov     ebx, eax
0x14004df33  mov     r14d, 20000h
0x14004df39  test    eax, eax
0x14004df3b  js      short loc_14004DFA6
0x14004df3d  lea     rcx, [rbp+UnicodeString]; char
0x14004df41  call    VhdmpiDeleteFile
0x14004df46  mov     ebx, eax
0x14004df48  cmp     eax, 0C0000034h
0x14004df4d  jz      short loc_14004DFA4
0x14004df4f  cmp     eax, 0C000003Ah
0x14004df54  jz      short loc_14004DFA4
0x14004df56  test    eax, eax
0x14004df58  jns     short loc_14004DFA6
0x14004df5a  mov     eax, cs:dword_1400876D0
0x14004df60  cmp     eax, 2
0x14004df63  jbe     short loc_14004DFA6
0x14004df65  mov     edx, r14d
0x14004df68  lea     rcx, dword_1400876D0
0x14004df6f  call    _tlgKeywordOn
0x14004df74  test    al, al
0x14004df76  jz      short loc_14004DFA6
0x14004df78  lea     rax, aVhdmpideleterc; "VhdmpiDeleteRctFiles: Unable to delete "...
0x14004df7f  mov     dword ptr [rsp+68h+var_40], ebx; char
0x14004df83  mov     edx, 428h; int
0x14004df88  mov     [rsp+68h+var_48], rax; char *
0x14004df8d  mov     r9d, r14d; int
0x14004df90  lea     rcx, aVhdmpideleterc_1; "VhdmpiDeleteRctFiles"
0x14004df97  mov     r8d, 2; int
0x14004df9d  call    TraceEvents
0x14004dfa2  jmp     short loc_14004DFA6
0x14004dfa4  xor     ebx, ebx
0x14004dfa6  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14004dfaa  call    cs:__imp_RtlFreeUnicodeString
0x14004dfb1  nop     dword ptr [rax+rax+00h]
0x14004dfb6  xorps   xmm0, xmm0
0x14004dfb9  lea     rdx, [rbp+UnicodeString]; struct _UNICODE_STRING *
0x14004dfbd  lea     rcx, [rbp+var_28]; struct _UNICODE_STRING *
0x14004dfc1  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14004dfc5  call    VhdmpiCreateNtFilePath
0x14004dfca  mov     edi, eax
0x14004dfcc  test    eax, eax
0x14004dfce  js      short loc_14004E039
0x14004dfd0  lea     rcx, [rbp+UnicodeString]; char
0x14004dfd4  call    VhdmpiDeleteFile
0x14004dfd9  mov     edi, eax
0x14004dfdb  cmp     eax, 0C0000034h
0x14004dfe0  jz      short loc_14004E037
0x14004dfe2  cmp     eax, 0C000003Ah
0x14004dfe7  jz      short loc_14004E037
0x14004dfe9  test    eax, eax
0x14004dfeb  jns     short loc_14004E039
0x14004dfed  mov     eax, cs:dword_1400876D0
0x14004dff3  cmp     eax, 2
0x14004dff6  jbe     short loc_14004E039
0x14004dff8  mov     rdx, r14
0x14004dffb  lea     rcx, dword_1400876D0
0x14004e002  call    _tlgKeywordOn
0x14004e007  test    al, al
0x14004e009  jz      short loc_14004E039
0x14004e00b  lea     rax, aVhdmpideleterc_0; "VhdmpiDeleteRctFiles: Unable to delete "...
0x14004e012  mov     dword ptr [rsp+68h+var_40], edi; char
0x14004e016  mov     edx, 440h; int
0x14004e01b  mov     [rsp+68h+var_48], rax; char *
0x14004e020  mov     r9d, r14d; int
0x14004e023  lea     rcx, aVhdmpideleterc_1; "VhdmpiDeleteRctFiles"
0x14004e02a  mov     r8d, 2; int
0x14004e030  call    TraceEvents
0x14004e035  jmp     short loc_14004E039
0x14004e037  xor     edi, edi
0x14004e039  test    ebx, ebx
0x14004e03b  jns     short loc_14004E041
0x14004e03d  test    edi, edi
0x14004e03f  js      short loc_14004E043
0x14004e041  xor     ebx, ebx
0x14004e043  lea     rcx, [rbp+var_28]; UnicodeString
0x14004e047  call    cs:__imp_RtlFreeUnicodeString
0x14004e04e  nop     dword ptr [rax+rax+00h]
0x14004e053  lea     rcx, [rbp+var_18]; UnicodeString
0x14004e057  call    cs:__imp_RtlFreeUnicodeString
0x14004e05e  nop     dword ptr [rax+rax+00h]
0x14004e063  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14004e067  call    cs:__imp_RtlFreeUnicodeString
0x14004e06e  nop     dword ptr [rax+rax+00h]
0x14004e073  mov     eax, ebx
0x14004e075  add     rsp, 68h
0x14004e079  pop     r14
0x14004e07b  pop     rdi
0x14004e07c  pop     rbx
0x14004e07d  pop     rbp
0x14004e07e  retn
```
