# User::UserEntry::CopySid(void *)

- ea: `0x180046208`
- end: `0x180046387`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `383`
- prototype: `void(User::UserEntry *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002790`
- `0x1800460dc`

## callees

- `0x18000cc40`
- `0x180027910`
- `0x180046208`
- `0x180056954`
- `0x18005a2bc`
- `0x18005dcd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800462f0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180046227`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180046227`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800462dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800462dc`

## pseudocode

```c
void __fastcall User::UserEntry::CopySid(User::UserEntry *this, void *a2)
{
  DWORD LengthSid; // r14d
  void *v5; // rax
  void *v6; // rcx
  void *v7; // rbx
  DWORD LastError; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v10; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v11; // [rsp+30h] [rbp-30h]
  __int64 v12; // [rsp+38h] [rbp-28h]
  __int64 v13; // [rsp+40h] [rbp-20h]
  int v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+4Ch] [rbp-14h]

  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v5 = operator new(LengthSid);
    v6 = (void *)*((_QWORD *)this + 4);
    v7 = v5;
    if ( v6 )
      operator delete(v6);
    *((_QWORD *)this + 4) = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v10 = 0;
      v11 = &qword_1800A8718;
      v12 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v13 = 0;
      v14 = 14;
      v15 = -1;
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( !CopySid(LengthSid, v7, a2) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids, LastError);
      }
      v10 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v12 = 0;
      v11 = &qword_1800A8718;
      v13 = 0;
      v14 = LastError;
      v15 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180046208  test    rdx, rdx
0x18004620b  jz      locret_180046385
0x180046211  push    rbp
0x180046212  push    rbx
0x180046213  push    rsi
0x180046214  push    rdi
0x180046215  push    r14
0x180046217  mov     rbp, rsp
0x18004621a  sub     rsp, 60h
0x18004621e  mov     rsi, rcx
0x180046221  mov     rdi, rdx
0x180046224  mov     rcx, rdx; pSid
0x180046227  call    cs:__imp_GetLengthSid
0x18004622e  nop     dword ptr [rax+rax+00h]
0x180046233  mov     ecx, eax; dwBytes
0x180046235  mov     r14d, eax
0x180046238  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004623d  mov     rcx, [rsi+20h]; void *
0x180046241  mov     rbx, rax
0x180046244  test    rcx, rcx
0x180046247  jz      short loc_18004624E
0x180046249  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004624e  mov     [rsi+20h], rbx
0x180046252  test    rbx, rbx
0x180046255  jnz     short loc_1800462D3
0x180046257  mov     rcx, cs:WPP_GLOBAL_Control
0x18004625e  lea     rax, WPP_GLOBAL_Control
0x180046265  cmp     rcx, rax
0x180046268  jz      short loc_180046289
0x18004626a  test    byte ptr [rcx+1Ch], 80h
0x18004626e  jz      short loc_180046289
0x180046270  cmp     byte ptr [rcx+19h], 2
0x180046274  jb      short loc_180046289
0x180046276  mov     rcx, [rcx+10h]
0x18004627a  lea     edx, [rbx+11h]
0x18004627d  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180046284  call    WPP_SF_
0x180046289  lea     rax, qword_1800A8718
0x180046290  mov     [rbp+var_38], 0
0x180046294  mov     [rbp+var_30], rax
0x180046298  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18004629f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800462a6  mov     [rbp+var_28], 0
0x1800462ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800462b2  mov     [rbp+pExceptionObject], rax
0x1800462b6  mov     [rbp+var_20], 0
0x1800462be  mov     [rbp+var_18], 0Eh
0x1800462c5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800462cd  call    _CxxThrowException_0
0x1800462d3  mov     r8, rdi; pSourceSid
0x1800462d6  mov     rdx, rbx; pDestinationSid
0x1800462d9  mov     ecx, r14d; nDestinationSidLength
0x1800462dc  call    cs:__imp_CopySid
0x1800462e3  nop     dword ptr [rax+rax+00h]
0x1800462e8  test    eax, eax
0x1800462ea  jnz     loc_18004637B
0x1800462f0  call    cs:__imp_GetLastError
0x1800462f7  nop     dword ptr [rax+rax+00h]
0x1800462fc  mov     ebx, eax
0x1800462fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180046305  lea     rax, WPP_GLOBAL_Control
0x18004630c  cmp     rcx, rax
0x18004630f  jz      short loc_180046335
0x180046311  test    byte ptr [rcx+1Ch], 80h
0x180046315  jz      short loc_180046335
0x180046317  cmp     byte ptr [rcx+19h], 2
0x18004631b  jb      short loc_180046335
0x18004631d  mov     rcx, [rcx+10h]
0x180046321  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180046328  mov     edx, 12h
0x18004632d  mov     r9d, ebx
0x180046330  call    WPP_SF_d
0x180046335  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004633c  mov     [rbp+var_38], 0
0x180046340  mov     [rbp+pExceptionObject], rax
0x180046344  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18004634b  lea     rax, qword_1800A8718
0x180046352  mov     [rbp+var_28], 0
0x18004635a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004635e  mov     [rbp+var_30], rax
0x180046362  mov     [rbp+var_20], 0
0x18004636a  mov     [rbp+var_18], ebx
0x18004636d  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180046375  call    _CxxThrowException_0
0x18004637b  add     rsp, 60h
0x18004637f  pop     r14
0x180046381  pop     rdi
0x180046382  pop     rsi
0x180046383  pop     rbx
0x180046384  pop     rbp
0x180046385  retn
```
