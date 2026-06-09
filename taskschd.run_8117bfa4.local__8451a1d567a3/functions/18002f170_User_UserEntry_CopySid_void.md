# User::UserEntry::CopySid(void *)

- ea: `0x18002f170`
- end: `0x18002f2fe`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `398`
- prototype: `void(User::UserEntry *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a1d0`

## callees

- `0x180007e90`
- `0x18002f170`
- `0x18003e88c`
- `0x18005224c`
- `0x180052284`

## import_xrefs

- `msvcrt!free` at `0x18002f1b5`
- `msvcrt!free` at `0x18002f1b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f278`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002f1d2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002f1d2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f194`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002f194`

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
      v12 = &qword_18007B2F0;
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
      v12 = &qword_18007B2F0;
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
0x18002f170  test    rdx, rdx
0x18002f173  jnz     short loc_18002F177
0x18002f175  retn
0x18002f177  mov     [rsp+arg_10], rbx
0x18002f17c  push    rdi
0x18002f17d  sub     rsp, 60h
0x18002f181  mov     rdi, rcx
0x18002f184  mov     [rsp+68h+arg_0], rbp
0x18002f189  mov     rcx, rdx; pSid
0x18002f18c  mov     [rsp+68h+arg_8], rsi
0x18002f191  mov     rbx, rdx
0x18002f194  call    cs:__imp_GetLengthSid
0x18002f19b  nop     dword ptr [rax+rax+00h]
0x18002f1a0  mov     ecx, eax; unsigned __int64
0x18002f1a2  mov     ebp, eax
0x18002f1a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f1a9  mov     rcx, [rdi+20h]; Block
0x18002f1ad  mov     rsi, rax
0x18002f1b0  test    rcx, rcx
0x18002f1b3  jz      short loc_18002F1C1
0x18002f1b5  call    cs:__imp_free
0x18002f1bc  nop     dword ptr [rax+rax+00h]
0x18002f1c1  mov     [rdi+20h], rsi
0x18002f1c5  test    rsi, rsi
0x18002f1c8  jz      short loc_18002F1FF
0x18002f1ca  mov     r8, rbx; pSourceSid
0x18002f1cd  mov     rdx, rsi; pDestinationSid
0x18002f1d0  mov     ecx, ebp; nDestinationSidLength
0x18002f1d2  call    cs:__imp_CopySid
0x18002f1d9  nop     dword ptr [rax+rax+00h]
0x18002f1de  test    eax, eax
0x18002f1e0  jz      loc_18002F278
0x18002f1e6  mov     rbp, [rsp+68h+arg_0]
0x18002f1eb  mov     rsi, [rsp+68h+arg_8]
0x18002f1f0  mov     rbx, [rsp+68h+arg_10]
0x18002f1f8  add     rsp, 60h
0x18002f1fc  pop     rdi
0x18002f1fd  retn
0x18002f1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f206  lea     rax, WPP_GLOBAL_Control
0x18002f20d  cmp     rcx, rax
0x18002f210  jz      short loc_18002F22C
0x18002f212  test    byte ptr [rcx+1Ch], 80h
0x18002f216  jz      short loc_18002F22C
0x18002f218  cmp     byte ptr [rcx+19h], 2
0x18002f21c  jb      short loc_18002F22C
0x18002f21e  mov     rcx, [rcx+10h]
0x18002f222  mov     edx, 11h
0x18002f227  call    WPP_SF_
0x18002f22c  lea     rax, qword_18007B2F0
0x18002f233  mov     [rsp+68h+var_40], 0
0x18002f238  mov     [rsp+68h+var_38], rax
0x18002f23d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18002f244  xor     eax, eax
0x18002f246  mov     [rsp+68h+var_20], 0Eh
0x18002f24e  mov     [rsp+68h+var_30], rax
0x18002f253  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002f258  mov     [rsp+68h+var_28], rax
0x18002f25d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002f264  mov     [rsp+68h+pExceptionObject], rax
0x18002f269  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002f272  call    _CxxThrowException_0
0x18002f278  call    cs:__imp_GetLastError
0x18002f27f  nop     dword ptr [rax+rax+00h]
0x18002f284  mov     ebx, eax
0x18002f286  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f28d  lea     rax, WPP_GLOBAL_Control
0x18002f294  cmp     rcx, rax
0x18002f297  jz      short loc_18002F2B6
0x18002f299  test    byte ptr [rcx+1Ch], 80h
0x18002f29d  jz      short loc_18002F2B6
0x18002f29f  cmp     byte ptr [rcx+19h], 2
0x18002f2a3  jb      short loc_18002F2B6
0x18002f2a5  mov     rcx, [rcx+10h]
0x18002f2a9  mov     edx, 12h
0x18002f2ae  mov     r9d, ebx
0x18002f2b1  call    WPP_SF_d
0x18002f2b6  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002f2bd  mov     [rsp+68h+var_40], 0
0x18002f2c2  mov     [rsp+68h+pExceptionObject], rax
0x18002f2c7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002f2ce  lea     rax, qword_18007B2F0
0x18002f2d5  mov     [rsp+68h+var_20], ebx
0x18002f2d9  mov     [rsp+68h+var_38], rax
0x18002f2de  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002f2e3  xor     eax, eax
0x18002f2e5  mov     [rsp+68h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18002f2ee  mov     [rsp+68h+var_30], rax
0x18002f2f3  mov     [rsp+68h+var_28], rax
0x18002f2f8  call    _CxxThrowException_0
```
