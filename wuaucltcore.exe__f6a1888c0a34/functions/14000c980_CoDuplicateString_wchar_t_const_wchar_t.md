# CoDuplicateString(wchar_t const *,wchar_t * *)

- ea: `0x14000c980`
- end: `0x14000ca65`
- name: `?CoDuplicateString@@YAJPEB_WPEAPEA_W@Z`
- size: `229`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012be0`

## callees

- `0x140002ac0`
- `0x140002c30`
- `0x14000c8cc`
- `0x14000c980`
- `0x14000d598`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ca43`

## pseudocode

```c
__int64 __fastcall CoDuplicateString(const wchar_t *a1, wchar_t **a2)
{
  wchar_t *v2; // rbx
  __int64 v5; // rdx
  signed int v6; // edi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rbp
  unsigned __int64 v10[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v10[0] = 0;
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
  v6 = SusStrCchLen(a1, 0x7FFFFFFEu, v10);
  if ( v6 >= 0 )
  {
    v8 = v10[0] + 1;
    if ( v10[0] == -1 || (v2 = (wchar_t *)SafeSusComAllocArray(v10[0] + 1, v7), v6 = v2 == 0 ? 0x8007000E : 0, v2) )
    {
      v6 = StringCchCopyW(v2, v8, a1);
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
    v10[0]);
  if ( v2 )
    CoTaskMemFree(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c980  mov     [rsp+arg_10], rbx
0x14000c985  mov     [rsp+arg_18], rbp
0x14000c98a  push    rsi
0x14000c98b  push    rdi
0x14000c98c  push    r14
0x14000c98e  sub     rsp, 30h
0x14000c992  xor     ebx, ebx
0x14000c994  mov     [rsp+48h+var_28], 0; int
0x14000c99d  mov     rsi, rdx
0x14000c9a0  mov     r14, rcx
0x14000c9a3  test    rcx, rcx
0x14000c9a6  jnz     short loc_14000C9AF
0x14000c9a8  mov     edx, 2A8h
0x14000c9ad  jmp     short loc_14000C9B9
0x14000c9af  test    rsi, rsi
0x14000c9b2  jnz     short loc_14000C9C0
0x14000c9b4  mov     edx, 2A9h
0x14000c9b9  mov     edi, 80070057h
0x14000c9be  jmp     short loc_14000CA27
0x14000c9c0  mov     [rdx], rbx
0x14000c9c3  lea     r8, [rsp+48h+var_28]; unsigned __int64 *
0x14000c9c8  mov     edx, 7FFFFFFEh; unsigned __int64
0x14000c9cd  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x14000c9d2  mov     edi, eax
0x14000c9d4  test    eax, eax
0x14000c9d6  jns     short loc_14000C9DF
0x14000c9d8  mov     edx, 2ADh
0x14000c9dd  jmp     short loc_14000CA27
0x14000c9df  mov     rbp, [rsp+48h+var_28]
0x14000c9e4  add     rbp, 1
0x14000c9e8  jz      short loc_14000CA0E
0x14000c9ea  mov     rcx, rbp; unsigned __int64
0x14000c9ed  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x14000c9f2  mov     rbx, rax
0x14000c9f5  neg     rax
0x14000c9f8  sbb     edi, edi
0x14000c9fa  not     edi
0x14000c9fc  and     edi, 8007000Eh
0x14000ca02  test    rbx, rbx
0x14000ca05  jnz     short loc_14000CA0E
0x14000ca07  mov     edx, 2B2h
0x14000ca0c  jmp     short loc_14000CA27
0x14000ca0e  mov     r8, r14; wchar_t *
0x14000ca11  mov     rdx, rbp; unsigned __int64
0x14000ca14  mov     rcx, rbx; wchar_t *
0x14000ca17  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000ca1c  mov     edi, eax
0x14000ca1e  test    eax, eax
0x14000ca20  jns     short loc_14000CA4B
0x14000ca22  mov     edx, 2B4h; void *
0x14000ca27  mov     rcx, [rsp+48h]; this
0x14000ca2c  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000ca33  mov     r9d, edi; char *
0x14000ca36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ca3b  test    rbx, rbx
0x14000ca3e  jz      short loc_14000CA50
0x14000ca40  mov     rcx, rbx; pv
0x14000ca43  call    cs:__imp_CoTaskMemFree
0x14000ca49  jmp     short loc_14000CA50
0x14000ca4b  mov     [rsi], rbx
0x14000ca4e  xor     edi, edi
0x14000ca50  mov     rbx, [rsp+48h+arg_10]
0x14000ca55  mov     eax, edi
0x14000ca57  mov     rbp, [rsp+48h+arg_18]
0x14000ca5c  add     rsp, 30h
0x14000ca60  pop     r14
0x14000ca62  pop     rdi
0x14000ca63  pop     rsi
0x14000ca64  retn
```
