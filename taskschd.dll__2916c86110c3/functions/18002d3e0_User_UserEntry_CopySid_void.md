# User::UserEntry::CopySid(void *)

- ea: `0x18002d3e0`
- end: `0x18002d554`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `372`
- prototype: `void(User::UserEntry *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009b1c`

## callees

- `0x180007aa0`
- `0x18002d3e0`
- `0x18003b51c`
- `0x18004e590`
- `0x18004e5c0`

## import_xrefs

- `msvcrt!free` at `0x18002d41e`
- `msvcrt!free` at `0x18002d41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4d4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002d435`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002d435`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d403`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d403`

## pseudocode

```c
void __fastcall User::UserEntry::CopySid(User::UserEntry *this, void *a2)
{
  DWORD LengthSid; // ebp
  void *v5; // rax
  void *v6; // rcx
  void *v7; // rsi
  DWORD LastError; // ebx
  __int64 v9; // r8
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h]
  __int64 *v12; // [rsp+30h] [rbp-38h]
  __int64 v13; // [rsp+38h] [rbp-30h]
  __int64 v14; // [rsp+40h] [rbp-28h]
  int v15; // [rsp+48h] [rbp-20h]
  __int64 v16; // [rsp+4Ch] [rbp-1Ch]

  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v5 = operator new(LengthSid);
    v6 = (void *)*((_QWORD *)this + 4);
    v7 = v5;
    if ( v6 )
      free(v6);
    *((_QWORD *)this + 4) = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17);
      }
      v11 = 0;
      v12 = &qword_180077320;
      v15 = 14;
      v13 = 0;
      v14 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v16 = -1;
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( !CopySid(LengthSid, v7, a2) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, v9, LastError);
      }
      v11 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v15 = LastError;
      v12 = &qword_180077320;
      v16 = -1;
      v13 = 0;
      v14 = 0;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18002d3e0  test    rdx, rdx
0x18002d3e3  jnz     short loc_18002D3E6
0x18002d3e5  retn
0x18002d3e6  mov     [rsp+arg_10], rbx
0x18002d3eb  push    rdi
0x18002d3ec  sub     rsp, 60h
0x18002d3f0  mov     rdi, rcx
0x18002d3f3  mov     [rsp+68h+arg_0], rbp
0x18002d3f8  mov     rcx, rdx; pSid
0x18002d3fb  mov     [rsp+68h+arg_8], rsi
0x18002d400  mov     rbx, rdx
0x18002d403  call    cs:__imp_GetLengthSid
0x18002d409  mov     ecx, eax; unsigned __int64
0x18002d40b  mov     ebp, eax
0x18002d40d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d412  mov     rcx, [rdi+20h]; Block
0x18002d416  mov     rsi, rax
0x18002d419  test    rcx, rcx
0x18002d41c  jz      short loc_18002D424
0x18002d41e  call    cs:__imp_free
0x18002d424  mov     [rdi+20h], rsi
0x18002d428  test    rsi, rsi
0x18002d42b  jz      short loc_18002D45B
0x18002d42d  mov     r8, rbx; pSourceSid
0x18002d430  mov     rdx, rsi; pDestinationSid
0x18002d433  mov     ecx, ebp; nDestinationSidLength
0x18002d435  call    cs:__imp_CopySid
0x18002d43b  test    eax, eax
0x18002d43d  jz      loc_18002D4D4
0x18002d443  mov     rbp, [rsp+68h+arg_0]
0x18002d448  mov     rsi, [rsp+68h+arg_8]
0x18002d44d  mov     rbx, [rsp+68h+arg_10]
0x18002d455  add     rsp, 60h
0x18002d459  pop     rdi
0x18002d45a  retn
0x18002d45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d462  lea     rax, WPP_GLOBAL_Control
0x18002d469  cmp     rcx, rax
0x18002d46c  jz      short loc_18002D488
0x18002d46e  test    byte ptr [rcx+1Ch], 80h
0x18002d472  jz      short loc_18002D488
0x18002d474  cmp     byte ptr [rcx+19h], 2
0x18002d478  jb      short loc_18002D488
0x18002d47a  mov     rcx, [rcx+10h]
0x18002d47e  mov     edx, 11h
0x18002d483  call    WPP_SF_
0x18002d488  lea     rax, qword_180077320
0x18002d48f  mov     [rsp+68h+var_40], 0
0x18002d494  mov     [rsp+68h+var_38], rax
0x18002d499  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002d4a0  xor     eax, eax
0x18002d4a2  mov     [rsp+68h+var_20], 0Eh
0x18002d4aa  mov     [rsp+68h+var_30], rax
0x18002d4af  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002d4b4  mov     [rsp+68h+var_28], rax
0x18002d4b9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002d4c0  mov     [rsp+68h+pExceptionObject], rax
0x18002d4c5  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d4ce  call    _CxxThrowException_0
0x18002d4d4  call    cs:__imp_GetLastError
0x18002d4da  mov     ebx, eax
0x18002d4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4e3  lea     rax, WPP_GLOBAL_Control
0x18002d4ea  cmp     rcx, rax
0x18002d4ed  jz      short loc_18002D50C
0x18002d4ef  test    byte ptr [rcx+1Ch], 80h
0x18002d4f3  jz      short loc_18002D50C
0x18002d4f5  cmp     byte ptr [rcx+19h], 2
0x18002d4f9  jb      short loc_18002D50C
0x18002d4fb  mov     rcx, [rcx+10h]
0x18002d4ff  mov     edx, 12h
0x18002d504  mov     r9d, ebx
0x18002d507  call    WPP_SF_d
0x18002d50c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002d513  mov     [rsp+68h+var_40], 0
0x18002d518  mov     [rsp+68h+pExceptionObject], rax
0x18002d51d  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002d524  lea     rax, qword_180077320
0x18002d52b  mov     [rsp+68h+var_20], ebx
0x18002d52f  mov     [rsp+68h+var_38], rax
0x18002d534  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002d539  xor     eax, eax
0x18002d53b  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002d544  mov     [rsp+68h+var_30], rax
0x18002d549  mov     [rsp+68h+var_28], rax
0x18002d54e  call    _CxxThrowException_0
```
