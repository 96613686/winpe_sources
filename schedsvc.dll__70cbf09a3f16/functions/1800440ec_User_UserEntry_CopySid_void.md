# User::UserEntry::CopySid(void *)

- ea: `0x1800440ec`
- end: `0x180044258`
- name: `?CopySid@UserEntry@User@@QEAAXPEAX@Z`
- size: `364`
- prototype: `void __fastcall(User::UserEntry *this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002b690`
- `0x180043fcc`

## callees

- `0x18001a260`
- `0x180030f80`
- `0x1800440ec`
- `0x180054084`
- `0x18005790c`
- `0x18005b124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800441c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800441c8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004410b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004410b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800441ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800441ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall User::UserEntry::CopySid(User::UserEntry *this, void *a2)
{
  DWORD LengthSid; // r14d
  LPVOID v5; // rax
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
      v11 = &qword_1800A4718;
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
      v11 = &qword_1800A4718;
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
0x1800440ec  test    rdx, rdx
0x1800440ef  jz      locret_180044257
0x1800440f5  push    rbp
0x1800440f6  push    rbx
0x1800440f7  push    rsi
0x1800440f8  push    rdi
0x1800440f9  push    r14
0x1800440fb  mov     rbp, rsp
0x1800440fe  sub     rsp, 60h
0x180044102  mov     rsi, rcx
0x180044105  mov     rdi, rdx
0x180044108  mov     rcx, rdx; pSid
0x18004410b  call    cs:__imp_GetLengthSid
0x180044111  mov     ecx, eax; dwBytes
0x180044113  mov     r14d, eax
0x180044116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004411b  mov     rcx, [rsi+20h]; void *
0x18004411f  mov     rbx, rax
0x180044122  test    rcx, rcx
0x180044125  jz      short loc_18004412C
0x180044127  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004412c  mov     [rsi+20h], rbx
0x180044130  test    rbx, rbx
0x180044133  jnz     short loc_1800441B1
0x180044135  mov     rcx, cs:WPP_GLOBAL_Control
0x18004413c  lea     rax, WPP_GLOBAL_Control
0x180044143  cmp     rcx, rax
0x180044146  jz      short loc_180044167
0x180044148  test    byte ptr [rcx+1Ch], 80h
0x18004414c  jz      short loc_180044167
0x18004414e  cmp     byte ptr [rcx+19h], 2
0x180044152  jb      short loc_180044167
0x180044154  mov     rcx, [rcx+10h]
0x180044158  lea     edx, [rbx+11h]
0x18004415b  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180044162  call    WPP_SF_
0x180044167  lea     rax, qword_1800A4718
0x18004416e  mov     [rbp+var_38], 0
0x180044172  mov     [rbp+var_30], rax
0x180044176  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18004417d  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180044184  mov     [rbp+var_28], 0
0x18004418c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180044190  mov     [rbp+pExceptionObject], rax
0x180044194  mov     [rbp+var_20], 0
0x18004419c  mov     [rbp+var_18], 0Eh
0x1800441a3  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800441ab  call    _CxxThrowException_0
0x1800441b1  mov     r8, rdi; pSourceSid
0x1800441b4  mov     rdx, rbx; pDestinationSid
0x1800441b7  mov     ecx, r14d; nDestinationSidLength
0x1800441ba  call    cs:__imp_CopySid
0x1800441c0  test    eax, eax
0x1800441c2  jnz     loc_18004424D
0x1800441c8  call    cs:__imp_GetLastError
0x1800441ce  mov     ebx, eax
0x1800441d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800441d7  lea     rax, WPP_GLOBAL_Control
0x1800441de  cmp     rcx, rax
0x1800441e1  jz      short loc_180044207
0x1800441e3  test    byte ptr [rcx+1Ch], 80h
0x1800441e7  jz      short loc_180044207
0x1800441e9  cmp     byte ptr [rcx+19h], 2
0x1800441ed  jb      short loc_180044207
0x1800441ef  mov     rcx, [rcx+10h]
0x1800441f3  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x1800441fa  mov     edx, 12h
0x1800441ff  mov     r9d, ebx
0x180044202  call    WPP_SF_d
0x180044207  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004420e  mov     [rbp+var_38], 0
0x180044212  mov     [rbp+pExceptionObject], rax
0x180044216  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18004421d  lea     rax, qword_1800A4718
0x180044224  mov     [rbp+var_28], 0
0x18004422c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180044230  mov     [rbp+var_30], rax
0x180044234  mov     [rbp+var_20], 0
0x18004423c  mov     [rbp+var_18], ebx
0x18004423f  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180044247  call    _CxxThrowException_0
0x18004424d  add     rsp, 60h
0x180044251  pop     r14
0x180044253  pop     rdi
0x180044254  pop     rsi
0x180044255  pop     rbx
0x180044256  pop     rbp
0x180044257  retn
```
