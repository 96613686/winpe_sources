# Record_COMError_v

- ea: `0x14003f2f0`
- end: `0x14003f690`
- name: `Record_COMError_v`
- size: `928`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14003d784`
- `0x14003d9b4`
- `0x14003dda0`
- `0x14003de10`
- `0x14003e7c4`
- `0x14003f0e8`
- `0x14003f2f0`
- `0x140113220`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14003f547`
- `ADVAPI32!EventEnabled` at `0x14003f547`
- `KERNEL32!EnterCriticalSection` at `0x14003f3e8`
- `KERNEL32!EnterCriticalSection` at `0x14003f3e8`
- `KERNEL32!LeaveCriticalSection` at `0x14003f4cd`
- `KERNEL32!LeaveCriticalSection` at `0x14003f4cd`
- `KERNEL32!GetCurrentThreadId` at `0x14003f410`
- `KERNEL32!GetCurrentThreadId` at `0x14003f410`
- `msvcrt!_vsnwprintf_s` at `0x14003f3c7`
- `msvcrt!_vsnwprintf_s` at `0x14003f3c7`
- `msvcrt!memcpy_s` at `0x14003f60d`
- `msvcrt!memcpy_s` at `0x14003f65a`
- `msvcrt!memcpy_s` at `0x14003f60d`
- `msvcrt!memcpy_s` at `0x14003f65a`

## pseudocode

```c
__int64 __fastcall Record_COMError_v(
        const char *a1,
        int a2,
        int a3,
        _WORD *a4,
        unsigned __int64 a5,
        _WORD *Destination,
        unsigned __int64 a7,
        __int64 a8,
        IID *rclsid,
        wchar_t *Format,
        va_list ArgList)
{
  _WORD *v11; // r14
  _WORD *v12; // rsi
  __int64 result; // rax
  __int64 v14; // r15
  int v15; // r13d
  __int64 v16; // rcx
  __int64 v17; // rbx
  unsigned __int64 v18; // r8
  const unsigned __int16 *v19; // r12
  const unsigned __int16 *v20; // rax
  __int64 v21; // rbx
  const unsigned __int16 *v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  const unsigned __int16 *v25; // r13
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int16 v30; // [rsp+50h] [rbp-898h]
  unsigned int v31; // [rsp+60h] [rbp-888h]
  const unsigned __int16 *Sourcea; // [rsp+70h] [rbp-878h]
  char *v36; // [rsp+80h] [rbp-868h]
  int v37; // [rsp+88h] [rbp-860h]
  wchar_t Buffer[1024]; // [rsp+A0h] [rbp-848h] BYREF

  v11 = a4;
  v31 = a3;
  v12 = Destination;
  result = (unsigned int)a3;
  if ( a3 < 0 )
  {
    v14 = -1;
    v15 = _vsnwprintf_s(Buffer, 0x400u, 0xFFFFFFFFFFFFFFFFuLL, Format, ArgList);
    if ( v15 == -1 )
      v15 = 1023;
    EnterCriticalSection(&CriticalSection);
    try
    {
      try
      {
        std::vector<ErrorRecord>::resize(v16, ((qword_1401C65E0 - (__int64)qword_1401C65D8) >> 6) + 1);
        v17 = qword_1401C65E0;
        *(_DWORD *)(v17 - 64) = GetCurrentThreadId();
        *(_BYTE *)(v17 - 60) = 0;
        *(_DWORD *)(v17 - 56) = -1;
        *(_DWORD *)(v17 - 52) = v31;
        *(_DWORD *)(v17 - 40) = a2;
        ErrorRecord::MakeDeepStringCopy((char **)(v17 - 48), a1, v18);
        ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v17 - 24), Buffer, v15);
        *(_QWORD *)(v17 - 16) = GetInterfaceTextName(rclsid);
        GetCOMExtendedErrorInfo(a8, rclsid, v17 - 32, v17 - 8);
      }
      catch ( std::bad_alloc )
      {
        Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1358, "ERROR: cannot allocate memory for error record");
        v14 = -1;
        v11 = a4;
        v31 = a3;
        v12 = Destination;
      }
    }
    catch ( ... )
    {
      Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1362, "ERROR: unhandled general exception");
      v14 = -1;
      v11 = a4;
      v31 = a3;
      v12 = Destination;
    }
    LeaveCriticalSection(&CriticalSection);
    v19 = &qword_14012B318;
    v20 = &qword_14012B318;
    if ( *(_QWORD *)(qword_1401C65E0 - 8) )
      v20 = *(const unsigned __int16 **)(qword_1401C65E0 - 8);
    Sourcea = v20;
    v21 = -1;
    do
      ++v21;
    while ( v20[v21] );
    v22 = &qword_14012B318;
    if ( *(_QWORD *)(qword_1401C65E0 - 16) )
      v22 = *(const unsigned __int16 **)(qword_1401C65E0 - 16);
    v36 = (char *)v22;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v37 = v23;
    if ( *(_QWORD *)(qword_1401C65E0 - 32) )
      v19 = *(const unsigned __int16 **)(qword_1401C65E0 - 32);
    do
      ++v14;
    while ( v19[v14] );
    if ( EventEnabled(WINSAT_ETW_PROVIDER_Context, &COMErrorEv)
      && (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 2) != 0 )
    {
      HIWORD(v24) = HIWORD(v37);
      LOWORD(v24) = v37 + 1;
      v30 = v15 + 1;
      v25 = Sourcea;
      McTemplateU0djhzr2hzr4hzr6hzr8_EventWriteTransfer(
        (unsigned int)&WINSAT_ETW_PROVIDER_Context,
        v24,
        v31,
        (_DWORD)rclsid,
        v21 + 1,
        (__int64)Sourcea,
        v37 + 1,
        (__int64)v36,
        v14 + 1,
        (__int64)v19,
        v30,
        (__int64)Buffer);
    }
    else
    {
      v25 = Sourcea;
    }
    if ( v11 && a5 )
    {
      if ( v25 && (_WORD)v21 )
      {
        v26 = a5 - 1;
        if ( (unsigned __int16)v21 < a5 )
          v26 = (unsigned __int16)v21;
        v27 = v26;
        memcpy_s(v11, 2 * a5, v25, 2 * v26);
        v11[v27] = 0;
      }
      else
      {
        *v11 = 0;
      }
    }
    if ( v12 && a7 )
    {
      if ( v19 && (_WORD)v14 )
      {
        v28 = a7 - 1;
        if ( (unsigned __int16)v14 < a7 )
          v28 = (unsigned __int16)v14;
        v29 = v28;
        memcpy_s(v12, 2 * a7, v19, 2 * v28);
        v12[v29] = 0;
      }
      else
      {
        *v12 = 0;
      }
    }
    return v31;
  }
  else
  {
    if ( a4 && a5 )
      *a4 = 0;
    if ( Destination )
    {
      if ( a7 )
        *Destination = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003f2f0  push    rbx
0x14003f2f2  push    rsi
0x14003f2f3  push    rdi
0x14003f2f4  push    r12
0x14003f2f6  push    r13
0x14003f2f8  push    r14
0x14003f2fa  push    r15
0x14003f2fc  sub     rsp, 8B0h
0x14003f303  mov     rax, cs:__security_cookie
0x14003f30a  xor     rax, rsp
0x14003f30d  mov     [rsp+8E8h+var_48], rax
0x14003f315  mov     r14, r9
0x14003f318  mov     [rsp+8E8h+var_888], r8d
0x14003f31d  mov     dword ptr [rsp+8E8h+Source], edx
0x14003f321  mov     [rsp+8E8h+var_868], rcx
0x14003f329  mov     [rsp+8E8h+var_880], r8d
0x14003f32e  mov     [rsp+8E8h+var_858], r9
0x14003f336  mov     rsi, [rsp+8E8h+Destination]
0x14003f33e  mov     [rsp+8E8h+var_850], rsi
0x14003f346  mov     rax, [rsp+8E8h+arg_38]
0x14003f34e  mov     [rsp+8E8h+var_860], rax
0x14003f356  mov     r12, [rsp+8E8h+rclsid]
0x14003f35e  mov     [rsp+8E8h+var_870], r12
0x14003f363  mov     r9, [rsp+8E8h+Format]; Format
0x14003f36b  mov     rcx, [rsp+8E8h+arg_50]
0x14003f373  xor     edi, edi
0x14003f375  mov     eax, r8d
0x14003f378  test    eax, eax
0x14003f37a  js      short loc_14003F3AE
0x14003f37c  test    r14, r14
0x14003f37f  jz      short loc_14003F38F
0x14003f381  cmp     [rsp+8E8h+arg_20], rdi
0x14003f389  jbe     short loc_14003F38F
0x14003f38b  mov     [r14], di
0x14003f38f  test    rsi, rsi
0x14003f392  jz      loc_14003F66D
0x14003f398  cmp     [rsp+8E8h+arg_30], rdi
0x14003f3a0  jbe     loc_14003F66D
0x14003f3a6  mov     [rsi], di
0x14003f3a9  jmp     loc_14003F66D
0x14003f3ae  mov     [rsp+8E8h+ArgList], rcx; ArgList
0x14003f3b3  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003f3b7  mov     r8, r15; MaxCount
0x14003f3ba  mov     edx, 400h; BufferCount
0x14003f3bf  lea     rcx, [rsp+8E8h+Buffer]; Buffer
0x14003f3c7  call    cs:__imp__vsnwprintf_s
0x14003f3cd  mov     r13d, eax
0x14003f3d0  mov     eax, 3FFh
0x14003f3d5  cmp     r13d, r15d
0x14003f3d8  cmovz   r13d, eax
0x14003f3dc  mov     [rsp+8E8h+var_884], r13d
0x14003f3e1  lea     rcx, CriticalSection; lpCriticalSection
0x14003f3e8  call    cs:__imp_EnterCriticalSection
0x14003f3ee  nop
0x14003f3ef  mov     rdx, cs:qword_1401C65E0
0x14003f3f6  sub     rdx, cs:qword_1401C65D8
0x14003f3fd  sar     rdx, 6
0x14003f401  inc     rdx
0x14003f404  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x14003f409  mov     rbx, cs:qword_1401C65E0
0x14003f410  call    cs:__imp_GetCurrentThreadId
0x14003f416  mov     [rbx-40h], eax
0x14003f419  mov     [rbx-3Ch], dil
0x14003f41d  mov     dword ptr [rbx-38h], 0FFFFFFFFh
0x14003f424  mov     eax, [rsp+8E8h+var_888]
0x14003f428  mov     [rbx-34h], eax
0x14003f42b  mov     eax, dword ptr [rsp+8E8h+Source]
0x14003f42f  mov     [rbx-28h], eax
0x14003f432  lea     rcx, [rbx-30h]; char **
0x14003f436  mov     rdx, [rsp+8E8h+var_868]; char *
0x14003f43e  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x14003f443  movsxd  r8, r13d; unsigned __int64
0x14003f446  lea     rcx, [rbx-18h]; unsigned __int16 **
0x14003f44a  lea     rdx, [rsp+8E8h+Buffer]; unsigned __int16 *
0x14003f452  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x14003f457  mov     rcx, r12; rclsid
0x14003f45a  call    GetInterfaceTextName
0x14003f45f  mov     [rbx-10h], rax
0x14003f463  lea     r9, [rbx-8]
0x14003f467  lea     r8, [rbx-20h]
0x14003f46b  mov     rdx, r12
0x14003f46e  mov     rcx, [rsp+8E8h+var_860]
0x14003f476  call    GetCOMExtendedErrorInfo
0x14003f47b  nop
0x14003f47c  jmp     short loc_14003F4A1
0x14003f47e  xor     edi, edi
0x14003f480  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003f484  mov     r13d, [rsp+8E8h+var_884]
0x14003f489  mov     r14, [rsp+8E8h+var_858]
0x14003f491  mov     eax, [rsp+8E8h+var_880]
0x14003f495  mov     [rsp+8E8h+var_888], eax
0x14003f499  mov     rsi, [rsp+8E8h+var_850]
0x14003f4a1  jmp     short loc_14003F4C6
0x14003f4a3  xor     edi, edi
0x14003f4a5  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003f4a9  mov     r13d, [rsp+8E8h+var_884]
0x14003f4ae  mov     r14, [rsp+8E8h+var_858]
0x14003f4b6  mov     eax, [rsp+8E8h+var_880]
0x14003f4ba  mov     [rsp+8E8h+var_888], eax
0x14003f4be  mov     rsi, [rsp+8E8h+var_850]
0x14003f4c6  lea     rcx, CriticalSection; lpCriticalSection
0x14003f4cd  call    cs:__imp_LeaveCriticalSection
0x14003f4d3  mov     rdx, cs:qword_1401C65E0
0x14003f4da  lea     r12, qword_14012B318
0x14003f4e1  mov     rax, r12
0x14003f4e4  cmp     [rdx-8], rdi
0x14003f4e8  cmovnz  rax, [rdx-8]
0x14003f4ed  mov     [rsp+8E8h+Source], rax
0x14003f4f2  mov     rbx, r15
0x14003f4f5  inc     rbx
0x14003f4f8  cmp     [rax+rbx*2], di
0x14003f4fc  jnz     short loc_14003F4F5
0x14003f4fe  mov     rcx, r12
0x14003f501  cmp     [rdx-10h], rdi
0x14003f505  cmovnz  rcx, [rdx-10h]
0x14003f50a  mov     [rsp+8E8h+var_868], rcx
0x14003f512  mov     rax, r15
0x14003f515  inc     rax
0x14003f518  cmp     [rcx+rax*2], di
0x14003f51c  jnz     short loc_14003F515
0x14003f51e  mov     [rsp+8E8h+var_860], rax
0x14003f526  cmp     [rdx-20h], rdi
0x14003f52a  cmovnz  r12, [rdx-20h]
0x14003f52f  inc     r15
0x14003f532  cmp     [r12+r15*2], di
0x14003f537  jnz     short loc_14003F52F
0x14003f539  lea     rdx, COMErrorEv; EventDescriptor
0x14003f540  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003f547  call    cs:__imp_EventEnabled
0x14003f54d  test    al, al
0x14003f54f  jz      short loc_14003F5CE
0x14003f551  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, 2
0x14003f558  jz      short loc_14003F5CE
0x14003f55a  mov     r8d, 1
0x14003f560  add     r13w, r8w
0x14003f564  lea     eax, [r8+r15]
0x14003f568  mov     rdx, [rsp+8E8h+var_860]
0x14003f570  add     dx, r8w
0x14003f574  lea     ecx, [r8+rbx]
0x14003f578  lea     r8, [rsp+8E8h+Buffer]
0x14003f580  mov     [rsp+8E8h+var_890], r8
0x14003f585  mov     [rsp+8E8h+var_898], r13w
0x14003f58b  mov     [rsp+8E8h+var_8A0], r12
0x14003f590  mov     [rsp+8E8h+var_8A8], ax
0x14003f595  mov     rax, [rsp+8E8h+var_868]
0x14003f59d  mov     [rsp+8E8h+var_8B0], rax
0x14003f5a2  mov     [rsp+8E8h+var_8B8], dx
0x14003f5a7  mov     r13, [rsp+8E8h+Source]
0x14003f5ac  mov     [rsp+8E8h+var_8C0], r13
0x14003f5b1  mov     word ptr [rsp+8E8h+ArgList], cx
0x14003f5b6  mov     r9, [rsp+8E8h+var_870]
0x14003f5bb  mov     r8d, [rsp+8E8h+var_888]
0x14003f5c0  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x14003f5c7  call    McTemplateU0djhzr2hzr4hzr6hzr8_EventWriteTransfer
0x14003f5cc  jmp     short loc_14003F5D3
0x14003f5ce  mov     r13, [rsp+8E8h+Source]
0x14003f5d3  test    r14, r14
0x14003f5d6  jz      short loc_14003F61E
0x14003f5d8  mov     rdx, [rsp+8E8h+arg_20]
0x14003f5e0  test    rdx, rdx
0x14003f5e3  jz      short loc_14003F61E
0x14003f5e5  test    r13, r13
0x14003f5e8  jz      short loc_14003F61A
0x14003f5ea  test    bx, bx
0x14003f5ed  jz      short loc_14003F61A
0x14003f5ef  movzx   ecx, bx
0x14003f5f2  lea     rax, [rdx-1]
0x14003f5f6  cmp     rcx, rdx
0x14003f5f9  cmovb   rax, rcx
0x14003f5fd  lea     rbx, [rax+rax]
0x14003f601  add     rdx, rdx; DestinationSize
0x14003f604  mov     r9, rbx; SourceSize
0x14003f607  mov     r8, r13; Source
0x14003f60a  mov     rcx, r14; Destination
0x14003f60d  call    cs:__imp_memcpy_s
0x14003f613  mov     [rbx+r14], di
0x14003f618  jmp     short loc_14003F61E
0x14003f61a  mov     [r14], di
0x14003f61e  test    rsi, rsi
0x14003f621  jz      short loc_14003F669
0x14003f623  mov     rdx, [rsp+8E8h+arg_30]
0x14003f62b  test    rdx, rdx
0x14003f62e  jz      short loc_14003F669
0x14003f630  test    r12, r12
0x14003f633  jz      short loc_14003F666
0x14003f635  test    r15w, r15w
0x14003f639  jz      short loc_14003F666
0x14003f63b  movzx   ecx, r15w
0x14003f63f  lea     rax, [rdx-1]
0x14003f643  cmp     rcx, rdx
0x14003f646  cmovb   rax, rcx
0x14003f64a  lea     rbx, [rax+rax]
0x14003f64e  add     rdx, rdx; DestinationSize
0x14003f651  mov     r9, rbx; SourceSize
0x14003f654  mov     r8, r12; Source
0x14003f657  mov     rcx, rsi; Destination
0x14003f65a  call    cs:__imp_memcpy_s
0x14003f660  mov     [rbx+rsi], di
0x14003f664  jmp     short loc_14003F669
0x14003f666  mov     [rsi], di
0x14003f669  mov     eax, [rsp+8E8h+var_888]
0x14003f66d  mov     rcx, [rsp+8E8h+var_48]
0x14003f675  xor     rcx, rsp; StackCookie
0x14003f678  call    __security_check_cookie
0x14003f67d  add     rsp, 8B0h
0x14003f684  pop     r15
0x14003f686  pop     r14
0x14003f688  pop     r13
0x14003f68a  pop     r12
0x14003f68c  pop     rdi
0x14003f68d  pop     rsi
0x14003f68e  pop     rbx
0x14003f68f  retn
```
