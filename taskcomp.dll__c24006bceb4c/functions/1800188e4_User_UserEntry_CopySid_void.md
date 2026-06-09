# User::UserEntry::CopySid(void *)

- ea: `0x1800188e4`
- end: `0x180018a44`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `352`
- prototype: `void __fastcall(void **this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003b3c`
- `0x18001862c`

## callees

- `0x180004f88`
- `0x1800074d4`
- `0x18000878c`
- `0x18000c760`
- `0x18000fbb8`
- `0x1800188e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800189a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800189a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018901`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall User::UserEntry::CopySid(void **this, void *a2)
{
  DWORD LengthSid; // esi
  void *v5; // rax
  void *v6; // rdx
  DWORD LastError; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v9; // [rsp+28h] [rbp-40h]
  char *v10; // [rsp+30h] [rbp-38h]
  __int64 v11; // [rsp+38h] [rbp-30h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  int v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+4Ch] [rbp-1Ch]

  if ( a2 )
  {
    LengthSid = GetLengthSid(a2);
    v5 = operator new[](LengthSid);
    wmi::AutoVectorPtr<unsigned char>::operator=(this + 4, v5);
    v6 = this[4];
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v9 = 0;
      v10 = byte_1800505F8;
      v11 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v12 = 0;
      v13 = 14;
      v14 = -1;
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    if ( !CopySid(LengthSid, v6, a2) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids, LastError);
      }
      v9 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v11 = 0;
      v10 = byte_1800505F8;
      v12 = 0;
      v13 = LastError;
      v14 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800188e4  test    rdx, rdx
0x1800188e7  jz      locret_180018A43
0x1800188ed  push    rbp
0x1800188ee  push    rbx
0x1800188ef  push    rsi
0x1800188f0  push    rdi
0x1800188f1  mov     rbp, rsp
0x1800188f4  sub     rsp, 68h
0x1800188f8  mov     rbx, rcx
0x1800188fb  mov     rdi, rdx
0x1800188fe  mov     rcx, rdx; pSid
0x180018901  call    cs:__imp_GetLengthSid
0x180018907  mov     ecx, eax; unsigned __int64
0x180018909  mov     esi, eax
0x18001890b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018910  mov     rdx, rax
0x180018913  lea     rcx, [rbx+20h]
0x180018917  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18001891c  mov     rdx, [rbx+20h]; pDestinationSid
0x180018920  test    rdx, rdx
0x180018923  jnz     short loc_1800189A3
0x180018925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001892c  lea     rax, WPP_GLOBAL_Control
0x180018933  cmp     rcx, rax
0x180018936  jz      short loc_180018959
0x180018938  test    byte ptr [rcx+1Ch], 80h
0x18001893c  jz      short loc_180018959
0x18001893e  cmp     byte ptr [rcx+19h], 2
0x180018942  jb      short loc_180018959
0x180018944  mov     rcx, [rcx+10h]
0x180018948  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001894f  mov     edx, 11h
0x180018954  call    WPP_SF_
0x180018959  lea     rax, byte_1800505F8
0x180018960  mov     [rbp+var_40], 0
0x180018964  mov     [rbp+var_38], rax
0x180018968  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001896f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180018976  mov     [rbp+var_30], 0
0x18001897e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018982  mov     [rbp+pExceptionObject], rax
0x180018986  mov     [rbp+var_28], 0
0x18001898e  mov     [rbp+var_20], 0Eh
0x180018995  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x18001899d  call    _CxxThrowException_0
0x1800189a3  mov     r8, rdi; pSourceSid
0x1800189a6  mov     ecx, esi; nDestinationSidLength
0x1800189a8  call    cs:__imp_CopySid
0x1800189ae  test    eax, eax
0x1800189b0  jnz     loc_180018A3B
0x1800189b6  call    cs:__imp_GetLastError
0x1800189bc  mov     ebx, eax
0x1800189be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189c5  lea     rax, WPP_GLOBAL_Control
0x1800189cc  cmp     rcx, rax
0x1800189cf  jz      short loc_1800189F5
0x1800189d1  test    byte ptr [rcx+1Ch], 80h
0x1800189d5  jz      short loc_1800189F5
0x1800189d7  cmp     byte ptr [rcx+19h], 2
0x1800189db  jb      short loc_1800189F5
0x1800189dd  mov     rcx, [rcx+10h]
0x1800189e1  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800189e8  mov     edx, 12h
0x1800189ed  mov     r9d, ebx
0x1800189f0  call    WPP_SF_d
0x1800189f5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800189fc  mov     [rbp+var_40], 0
0x180018a00  mov     [rbp+pExceptionObject], rax
0x180018a04  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180018a0b  lea     rax, byte_1800505F8
0x180018a12  mov     [rbp+var_30], 0
0x180018a1a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018a1e  mov     [rbp+var_38], rax
0x180018a22  mov     [rbp+var_28], 0
0x180018a2a  mov     [rbp+var_20], ebx
0x180018a2d  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180018a35  call    _CxxThrowException_0
0x180018a3b  add     rsp, 68h
0x180018a3f  pop     rdi
0x180018a40  pop     rsi
0x180018a41  pop     rbx
0x180018a42  pop     rbp
0x180018a43  retn
```
