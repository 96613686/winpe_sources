# CSyncSharePartnershipManagerInternal::GetUserSidFromContext(void)

- ea: `0x180019ba0`
- end: `0x180019daf`
- name: `?GetUserSidFromContext@CSyncSharePartnershipManagerInternal@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `527`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18001ab70`
- `0x18001ca90`
- `0x18001cc20`
- `0x18001ce30`

## callees

- `0x180002f98`
- `0x180003604`
- `0x18000444c`
- `0x180007b9c`
- `0x180007e10`
- `0x1800083b4`
- `0x180008bdc`
- `0x180009424`
- `0x1800110fc`
- `0x180011314`
- `0x1800155b8`
- `0x180019ba0`
- `0x180060bc4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180019d33`
- `ADVAPI32!GetTokenInformation` at `0x180019c9f`
- `ADVAPI32!GetTokenInformation` at `0x180019c9f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180019cf4`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180019cf4`

## string_xrefs

- `0x180019c26`: `CSyncSharePartnershipManagerInternal::GetUserSidFromContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSyncSharePartnershipManagerInternal::GetUserSidFromContext(__int64 a1, __int64 a2, char a3)
{
  _BYTE *v4; // rax
  char v5; // cl
  void *v6; // rax
  PSID *v7; // rbx
  DWORD ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  int v10; // [rsp+34h] [rbp-4Ch]
  LPWSTR StringSid; // [rsp+38h] [rbp-48h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-40h] BYREF
  LPVOID TokenInformation; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp-30h] BYREF
  int LastFailureAsHRESULT; // [rsp+60h] [rbp-20h] BYREF
  int v16; // [rsp+64h] [rbp-1Ch]
  char v17; // [rsp+68h] [rbp-18h]
  const char *v18; // [rsp+70h] [rbp-10h]
  __int64 v19; // [rsp+78h] [rbp-8h]
  __int64 pExceptionObject; // [rsp+90h] [rbp+10h] BYREF
  __int64 v21; // [rsp+98h] [rbp+18h]

  v21 = a2;
  pExceptionObject = a1;
  v10 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 92, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) != 0 && v4[65] >= 6u )
  {
    v5 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v5 = 0;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v16 = 1632;
  v17 = v5;
  v18 = "CSyncSharePartnershipManagerInternal::GetUserSidFromContext";
  v19 = 0;
  pExceptionObject = CTokenHelper::GetCurrentToken(0xCu, a2, a3);
  TokenHandle = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&TokenHandle, &pExceptionObject);
  v6 = operator new[](0x80u);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&TokenInformation, v6);
  ReturnLength = 0;
  v7 = (PSID *)TokenInformation;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x80u, &ReturnLength) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v16) = 1644;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v16) = 1644;
  StringSid = 0;
  LastFailureAsHRESULT = 0;
  if ( !ConvertSidToStringSidW(*v7, &StringSid) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v16) = 1652;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v16) = 1652;
  pExceptionObject = (__int64)LocalFree;
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(v14, StringSid, &pExceptionObject);
  std::wstring::wstring(a2, StringSid);
  v10 = 1;
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(v14);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&TokenInformation);
  pExceptionObject = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&TokenHandle, &pExceptionObject);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a2;
}

```

## disassembly

```asm
0x180019ba0  mov     rax, rsp
0x180019ba3  mov     [rax+18h], rbx
0x180019ba7  mov     [rax+20h], rdi
0x180019bab  mov     [rax+10h], rdx
0x180019baf  mov     [rax+8], rcx
0x180019bb3  push    rbp
0x180019bb4  mov     rbp, rsp
0x180019bb7  sub     rsp, 80h
0x180019bbe  mov     rdi, rdx
0x180019bc1  mov     [rbp+var_4C], 0
0x180019bc8  lea     rcx, WPP_GLOBAL_Control
0x180019bcf  mov     rax, cs:WPP_GLOBAL_Control
0x180019bd6  cmp     rax, rcx
0x180019bd9  jz      short loc_180019C03
0x180019bdb  test    byte ptr [rax+44h], 8
0x180019bdf  jz      short loc_180019C13
0x180019be1  cmp     byte ptr [rax+41h], 6
0x180019be5  jb      short loc_180019C03
0x180019be7  mov     edx, 5Ch ; '\'
0x180019bec  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180019bf3  mov     rcx, [rax+38h]
0x180019bf7  call    WPP_SF_
0x180019bfc  mov     rax, cs:WPP_GLOBAL_Control
0x180019c03  test    byte ptr [rax+44h], 8
0x180019c07  jz      short loc_180019C13
0x180019c09  cmp     byte ptr [rax+41h], 6
0x180019c0d  jb      short loc_180019C13
0x180019c0f  mov     cl, 1
0x180019c11  jmp     short loc_180019C15
0x180019c13  xor     cl, cl
0x180019c15  mov     [rbp+var_20], 0
0x180019c1c  mov     [rbp+var_1C], 660h
0x180019c23  mov     [rbp+var_18], cl
0x180019c26  lea     rax, aCsyncsharepart_22; "CSyncSharePartnershipManagerInternal::G"...
0x180019c2d  mov     [rbp+var_10], rax
0x180019c31  mov     [rbp+var_8], 0
0x180019c39  mov     ecx, 0Ch; DesiredAccess
0x180019c3e  call    ?GetCurrentToken@CTokenHelper@@SAPEAXK_N0@Z; CTokenHelper::GetCurrentToken(ulong,bool,bool)
0x180019c43  mov     [rbp+pExceptionObject], rax
0x180019c47  mov     [rbp+TokenHandle], 0
0x180019c4f  lea     rdx, [rbp+pExceptionObject]
0x180019c53  lea     rcx, [rbp+TokenHandle]
0x180019c57  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x180019c5c  nop
0x180019c5d  mov     ebx, 80h
0x180019c62  mov     ecx, ebx; unsigned __int64
0x180019c64  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019c69  mov     rdx, rax
0x180019c6c  lea     rcx, [rbp+TokenInformation]
0x180019c70  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180019c75  nop
0x180019c76  mov     [rbp+var_50], 0
0x180019c7d  mov     eax, [rbp+var_20]
0x180019c80  mov     [rbp+var_20], eax
0x180019c83  lea     rax, [rbp+var_50]
0x180019c87  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180019c8c  mov     r9d, ebx; TokenInformationLength
0x180019c8f  mov     rbx, [rbp+TokenInformation]
0x180019c93  mov     r8, rbx; TokenInformation
0x180019c96  mov     edx, 1; TokenInformationClass
0x180019c9b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180019c9f  call    cs:__imp_GetTokenInformation
0x180019ca5  test    eax, eax
0x180019ca7  jnz     short loc_180019CCE
0x180019ca9  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180019cae  mov     [rbp+var_20], eax
0x180019cb1  mov     ecx, 66Ch
0x180019cb6  mov     word ptr [rbp+var_1C+2], cx
0x180019cba  mov     dword ptr [rbp+pExceptionObject], eax
0x180019cbd  lea     rdx, _TI1J; pThrowInfo
0x180019cc4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019cc8  call    _CxxThrowException_0
0x180019cce  mov     [rbp+var_20], 0
0x180019cd5  mov     ecx, 66Ch
0x180019cda  mov     word ptr [rbp+var_1C], cx
0x180019cde  mov     [rbp+StringSid], 0
0x180019ce6  mov     [rbp+var_20], 0
0x180019ced  lea     rdx, [rbp+StringSid]; StringSid
0x180019cf1  mov     rcx, [rbx]; Sid
0x180019cf4  call    cs:__imp_ConvertSidToStringSidW
0x180019cfa  test    eax, eax
0x180019cfc  jnz     short loc_180019D23
0x180019cfe  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180019d03  mov     [rbp+var_20], eax
0x180019d06  mov     ecx, 674h
0x180019d0b  mov     word ptr [rbp+var_1C+2], cx
0x180019d0f  mov     dword ptr [rbp+pExceptionObject], eax
0x180019d12  lea     rdx, _TI1J; pThrowInfo
0x180019d19  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019d1d  call    _CxxThrowException_0
0x180019d23  mov     [rbp+var_20], 0
0x180019d2a  mov     ecx, 674h
0x180019d2f  mov     word ptr [rbp+var_1C], cx
0x180019d33  mov     rax, cs:__imp_LocalFree
0x180019d3a  mov     [rbp+pExceptionObject], rax
0x180019d3e  lea     r8, [rbp+pExceptionObject]
0x180019d42  mov     rdx, [rbp+StringSid]
0x180019d46  lea     rcx, [rbp+var_30]
0x180019d4a  call    ??$?0P6AXPEAX@Z$0A@@?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@PEAU_WTSINFOW@@$$QEAP6AXPEAX@Z@Z; std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(_WTSINFOW *,void (*&&)(void *))
0x180019d4f  nop
0x180019d50  mov     rdx, [rbp+StringSid]
0x180019d54  mov     rcx, rdi
0x180019d57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019d5c  mov     [rbp+var_4C], 1
0x180019d63  lea     rcx, [rbp+var_30]
0x180019d67  call    ??1?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(void)
0x180019d6c  nop
0x180019d6d  lea     rcx, [rbp+TokenInformation]
0x180019d71  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180019d76  nop
0x180019d77  mov     [rbp+pExceptionObject], 0
0x180019d7f  lea     rdx, [rbp+pExceptionObject]
0x180019d83  lea     rcx, [rbp+TokenHandle]
0x180019d87  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x180019d8c  nop
0x180019d8d  lea     rcx, [rbp+var_20]; this
0x180019d91  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180019d96  mov     rax, rdi
0x180019d99  lea     r11, [rsp+80h+var_s0]
0x180019da1  mov     rbx, [r11+20h]
0x180019da5  mov     rdi, [r11+28h]
0x180019da9  mov     rsp, r11
0x180019dac  pop     rbp
0x180019dad  retn
```
