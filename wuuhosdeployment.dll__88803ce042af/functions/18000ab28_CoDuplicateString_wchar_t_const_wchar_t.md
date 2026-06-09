# CoDuplicateString(wchar_t const *,wchar_t * *)

- ea: `0x18000ab28`
- end: `0x18000ac12`
- name: `?CoDuplicateString@@YAJPEB_WPEAPEA_W@Z`
- size: `234`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022850`

## callees

- `0x180001cc8`
- `0x180003950`
- `0x18000a7b4`
- `0x18000aa74`
- `0x18000ab28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000abf0`

## pseudocode

```c
__int64 __fastcall CoDuplicateString(const wchar_t *a1, wchar_t **a2)
{
  wchar_t *v2; // rbx
  __int64 v5; // rdx
  signed int v6; // edi
  unsigned __int64 v7; // rbp
  unsigned __int64 v9[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v9[0] = 0;
  if ( !a1 )
  {
    v5 = 680;
LABEL_5:
    v6 = -2147024809;
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v5 = 681;
    goto LABEL_5;
  }
  *a2 = 0;
  v6 = SusStrCchLen(a1, 0x7FFFFFFEu, v9);
  if ( v6 >= 0 )
  {
    v7 = v9[0] + 1;
    if ( v9[0] == -1 || (v2 = (wchar_t *)SafeSusComAllocArray(v9[0] + 1, 2u), v6 = v2 == 0 ? 0x8007000E : 0, v2) )
    {
      v6 = StringCchCopyW(v2, v7, a1);
      if ( v6 >= 0 )
      {
        *a2 = v2;
        return 0;
      }
      v5 = 692;
    }
    else
    {
      v5 = 690;
    }
  }
  else
  {
    v5 = 685;
  }
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
    (const char *)(unsigned int)v6,
    v9[0]);
  if ( v2 )
    CoTaskMemFree(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ab28  mov     [rsp+arg_10], rbx
0x18000ab2d  mov     [rsp+arg_18], rbp
0x18000ab32  push    rsi
0x18000ab33  push    rdi
0x18000ab34  push    r14
0x18000ab36  sub     rsp, 30h
0x18000ab3a  xor     ebx, ebx
0x18000ab3c  mov     [rsp+48h+var_28], 0; int
0x18000ab45  mov     rsi, rdx
0x18000ab48  mov     r14, rcx
0x18000ab4b  test    rcx, rcx
0x18000ab4e  jnz     short loc_18000AB57
0x18000ab50  mov     edx, 2A8h
0x18000ab55  jmp     short loc_18000AB61
0x18000ab57  test    rsi, rsi
0x18000ab5a  jnz     short loc_18000AB68
0x18000ab5c  mov     edx, 2A9h
0x18000ab61  mov     edi, 80070057h
0x18000ab66  jmp     short loc_18000ABD4
0x18000ab68  mov     [rdx], rbx
0x18000ab6b  lea     r8, [rsp+48h+var_28]; unsigned __int64 *
0x18000ab70  mov     edx, 7FFFFFFEh; unsigned __int64
0x18000ab75  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000ab7a  mov     edi, eax
0x18000ab7c  test    eax, eax
0x18000ab7e  jns     short loc_18000AB87
0x18000ab80  mov     edx, 2ADh
0x18000ab85  jmp     short loc_18000ABD4
0x18000ab87  mov     rbp, [rsp+48h+var_28]
0x18000ab8c  add     rbp, 1
0x18000ab90  jz      short loc_18000ABBB
0x18000ab92  mov     edx, 2; unsigned __int64
0x18000ab97  mov     rcx, rbp; unsigned __int64
0x18000ab9a  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18000ab9f  mov     rbx, rax
0x18000aba2  neg     rax
0x18000aba5  sbb     edi, edi
0x18000aba7  not     edi
0x18000aba9  and     edi, 8007000Eh
0x18000abaf  test    rbx, rbx
0x18000abb2  jnz     short loc_18000ABBB
0x18000abb4  mov     edx, 2B2h
0x18000abb9  jmp     short loc_18000ABD4
0x18000abbb  mov     r8, r14; wchar_t *
0x18000abbe  mov     rdx, rbp; unsigned __int64
0x18000abc1  mov     rcx, rbx; wchar_t *
0x18000abc4  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000abc9  mov     edi, eax
0x18000abcb  test    eax, eax
0x18000abcd  jns     short loc_18000ABF8
0x18000abcf  mov     edx, 2B4h; void *
0x18000abd4  mov     rcx, [rsp+48h]; this
0x18000abd9  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000abe0  mov     r9d, edi; char *
0x18000abe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abe8  test    rbx, rbx
0x18000abeb  jz      short loc_18000ABFD
0x18000abed  mov     rcx, rbx; pv
0x18000abf0  call    cs:__imp_CoTaskMemFree
0x18000abf6  jmp     short loc_18000ABFD
0x18000abf8  mov     [rsi], rbx
0x18000abfb  xor     edi, edi
0x18000abfd  mov     rbx, [rsp+48h+arg_10]
0x18000ac02  mov     eax, edi
0x18000ac04  mov     rbp, [rsp+48h+arg_18]
0x18000ac09  add     rsp, 30h
0x18000ac0d  pop     r14
0x18000ac0f  pop     rdi
0x18000ac10  pop     rsi
0x18000ac11  retn
```
