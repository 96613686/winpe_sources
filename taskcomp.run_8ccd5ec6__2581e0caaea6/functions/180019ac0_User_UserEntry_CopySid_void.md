# User::UserEntry::CopySid(void *)

- ea: `0x180019ac0`
- end: `0x180019c33`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `371`
- prototype: `void(User::UserEntry *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003cec`
- `0x1800197c4`

## callees

- `0x180005224`
- `0x180007994`
- `0x180008c4c`
- `0x18000cf80`
- `0x180010570`
- `0x180019ac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180019b8a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180019b8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019add`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b9e`

## pseudocode

```c
void __fastcall User::UserEntry::CopySid(User::UserEntry *this, void *a2)
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
    wmi::AutoVectorPtr<unsigned char>::operator=((char *)this + 32, v5);
    v6 = (void *)*((_QWORD *)this + 4);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v9 = 0;
      v10 = byte_180052608;
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
      v10 = byte_180052608;
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
0x180019ac0  test    rdx, rdx
0x180019ac3  jz      locret_180019C31
0x180019ac9  push    rbp
0x180019aca  push    rbx
0x180019acb  push    rsi
0x180019acc  push    rdi
0x180019acd  mov     rbp, rsp
0x180019ad0  sub     rsp, 68h
0x180019ad4  mov     rbx, rcx
0x180019ad7  mov     rdi, rdx
0x180019ada  mov     rcx, rdx; pSid
0x180019add  call    cs:__imp_GetLengthSid
0x180019ae4  nop     dword ptr [rax+rax+00h]
0x180019ae9  mov     ecx, eax; unsigned __int64
0x180019aeb  mov     esi, eax
0x180019aed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019af2  mov     rdx, rax
0x180019af5  lea     rcx, [rbx+20h]
0x180019af9  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x180019afe  mov     rdx, [rbx+20h]; pDestinationSid
0x180019b02  test    rdx, rdx
0x180019b05  jnz     short loc_180019B85
0x180019b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b0e  lea     rax, WPP_GLOBAL_Control
0x180019b15  cmp     rcx, rax
0x180019b18  jz      short loc_180019B3B
0x180019b1a  test    byte ptr [rcx+1Ch], 80h
0x180019b1e  jz      short loc_180019B3B
0x180019b20  cmp     byte ptr [rcx+19h], 2
0x180019b24  jb      short loc_180019B3B
0x180019b26  mov     rcx, [rcx+10h]
0x180019b2a  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019b31  mov     edx, 11h
0x180019b36  call    WPP_SF_
0x180019b3b  lea     rax, byte_180052608
0x180019b42  mov     [rbp+var_40], 0
0x180019b46  mov     [rbp+var_38], rax
0x180019b4a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180019b51  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019b58  mov     [rbp+var_30], 0
0x180019b60  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019b64  mov     [rbp+pExceptionObject], rax
0x180019b68  mov     [rbp+var_28], 0
0x180019b70  mov     [rbp+var_20], 0Eh
0x180019b77  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180019b7f  call    _CxxThrowException_0
0x180019b85  mov     r8, rdi; pSourceSid
0x180019b88  mov     ecx, esi; nDestinationSidLength
0x180019b8a  call    cs:__imp_CopySid
0x180019b91  nop     dword ptr [rax+rax+00h]
0x180019b96  test    eax, eax
0x180019b98  jnz     loc_180019C29
0x180019b9e  call    cs:__imp_GetLastError
0x180019ba5  nop     dword ptr [rax+rax+00h]
0x180019baa  mov     ebx, eax
0x180019bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bb3  lea     rax, WPP_GLOBAL_Control
0x180019bba  cmp     rcx, rax
0x180019bbd  jz      short loc_180019BE3
0x180019bbf  test    byte ptr [rcx+1Ch], 80h
0x180019bc3  jz      short loc_180019BE3
0x180019bc5  cmp     byte ptr [rcx+19h], 2
0x180019bc9  jb      short loc_180019BE3
0x180019bcb  mov     rcx, [rcx+10h]
0x180019bcf  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019bd6  mov     edx, 12h
0x180019bdb  mov     r9d, ebx
0x180019bde  call    WPP_SF_d
0x180019be3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019bea  mov     [rbp+var_40], 0
0x180019bee  mov     [rbp+pExceptionObject], rax
0x180019bf2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180019bf9  lea     rax, byte_180052608
0x180019c00  mov     [rbp+var_30], 0
0x180019c08  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019c0c  mov     [rbp+var_38], rax
0x180019c10  mov     [rbp+var_28], 0
0x180019c18  mov     [rbp+var_20], ebx
0x180019c1b  mov     [rbp+var_1C], 0FFFFFFFFFFFFFFFFh
0x180019c23  call    _CxxThrowException_0
0x180019c29  add     rsp, 68h
0x180019c2d  pop     rdi
0x180019c2e  pop     rsi
0x180019c2f  pop     rbx
0x180019c30  pop     rbp
0x180019c31  retn
```
