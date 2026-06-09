# CNtSecurityDescriptor::GetGroup(void)

- ea: `0x18003cef0`
- end: `0x18003d025`
- name: `?GetGroup@CNtSecurityDescriptor@@QEAAPEAVCNtSid@@XZ`
- size: `309`
- prototype: `struct CNtSid *__fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b580`

## callees

- `0x18000a290`
- `0x180014120`
- `0x18001c340`
- `0x18001c4d0`
- `0x18001c4fc`
- `0x18001c56c`
- `0x18001d19c`
- `0x180033f20`
- `0x18003cef0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cf3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cf50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cf50`

## string_xrefs

- `0x18003cf42`: `GetSecurityDescriptorGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CNtSid *__fastcall CNtSecurityDescriptor::GetGroup(CNtSecurityDescriptor *this)
{
  __int64 v1; // rdi
  FARPROC ProcAddress; // rax
  int v3; // ebx
  DWORD SecurityDll; // eax
  CNtSid *v6; // rax
  CNtSid *v7; // rbx
  unsigned int v8; // edx
  int v9; // [rsp+30h] [rbp+8h] BYREF
  void *v10; // [rsp+38h] [rbp+10h] BYREF
  CNtSid *v11; // [rsp+40h] [rbp+18h]

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this || *((_DWORD *)this + 2) )
    return 0;
  v10 = 0;
  v9 = 0;
  ProcAddress = (FARPROC)qword_180070398;
  if ( qword_180070398 )
    goto LABEL_7;
  v3 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorGroup");
  qword_180070398 = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_7:
    v3 = ((__int64 (__fastcall *)(__int64, void **, int *))ProcAddress)(v1, &v10, &v9);
LABEL_8:
  if ( !v10 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids);
    }
    return 0;
  }
  if ( !v3 || !(unsigned int)DLIsValidSid(v10) )
    return 0;
  v6 = (CNtSid *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  v11 = v6;
  if ( v6 )
    v7 = CNtSid::CNtSid(v6, v10);
  else
    v7 = 0;
  if ( v7 && !(unsigned int)CNtSid::IsValid(v7) )
  {
    CNtSid::`scalar deleting destructor'(v7, v8);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18003cef0  mov     [rsp+arg_18], rbx
0x18003cef5  push    rdi
0x18003cef6  sub     rsp, 20h
0x18003cefa  mov     rdi, [rcx]
0x18003cefd  test    rdi, rdi
0x18003cf00  jz      loc_18003CFC3
0x18003cf06  cmp     dword ptr [rcx+8], 0
0x18003cf0a  jnz     loc_18003CFC3
0x18003cf10  mov     [rsp+28h+arg_8], 0
0x18003cf19  mov     [rsp+28h+arg_0], 0
0x18003cf21  mov     rax, cs:qword_180070398
0x18003cf28  test    rax, rax
0x18003cf2b  jnz     short loc_18003CF62
0x18003cf2d  xor     ebx, ebx
0x18003cf2f  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18003cf34  test    eax, eax
0x18003cf36  jz      short loc_18003CF42
0x18003cf38  mov     ecx, eax; dwErrCode
0x18003cf3a  call    cs:__imp_SetLastError
0x18003cf40  jmp     short loc_18003CF76
0x18003cf42  lea     rdx, aGetsecuritydes_4; "GetSecurityDescriptorGroup"
0x18003cf49  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003cf50  call    cs:__imp_GetProcAddress
0x18003cf56  mov     cs:qword_180070398, rax
0x18003cf5d  test    rax, rax
0x18003cf60  jz      short loc_18003CF76
0x18003cf62  lea     r8, [rsp+28h+arg_0]
0x18003cf67  lea     rdx, [rsp+28h+arg_8]
0x18003cf6c  mov     rcx, rdi
0x18003cf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf74  mov     ebx, eax
0x18003cf76  mov     rcx, [rsp+28h+arg_8]; void *
0x18003cf7b  test    rcx, rcx
0x18003cf7e  jnz     short loc_18003CFD0
0x18003cf80  or      edx, 0FFFFFFFFh; int
0x18003cf83  lea     rcx, unk_18006A9C0; this
0x18003cf8a  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003cf8f  lea     rax, WPP_GLOBAL_Control
0x18003cf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf9d  cmp     rcx, rax
0x18003cfa0  jz      short loc_18003CFC3
0x18003cfa2  test    byte ptr [rcx+1Ch], 1
0x18003cfa6  jz      short loc_18003CFC3
0x18003cfa8  cmp     byte ptr [rcx+19h], 2
0x18003cfac  jb      short loc_18003CFC3
0x18003cfae  mov     edx, 0Eh
0x18003cfb3  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003cfba  mov     rcx, [rcx+10h]
0x18003cfbe  call    WPP_SF_
0x18003cfc3  xor     eax, eax
0x18003cfc5  mov     rbx, [rsp+28h+arg_18]
0x18003cfca  add     rsp, 20h
0x18003cfce  pop     rdi
0x18003cfcf  retn
0x18003cfd0  test    ebx, ebx
0x18003cfd2  jz      short loc_18003CFC3
0x18003cfd4  call    ?DLIsValidSid@@YAHPEAX@Z; DLIsValidSid(void *)
0x18003cfd9  test    eax, eax
0x18003cfdb  jz      short loc_18003CFC3
0x18003cfdd  mov     ecx, 10h; unsigned __int64
0x18003cfe2  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003cfe7  mov     [rsp+28h+arg_10], rax
0x18003cfec  test    rax, rax
0x18003cfef  jz      short loc_18003D003
0x18003cff1  mov     rdx, [rsp+28h+arg_8]; void *
0x18003cff6  mov     rcx, rax; this
0x18003cff9  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18003cffe  mov     rbx, rax
0x18003d001  jmp     short loc_18003D005
0x18003d003  xor     ebx, ebx
0x18003d005  test    rbx, rbx
0x18003d008  jz      short loc_18003D020
0x18003d00a  mov     rcx, rbx; this
0x18003d00d  call    ?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18003d012  test    eax, eax
0x18003d014  jnz     short loc_18003D020
0x18003d016  mov     rcx, rbx; this
0x18003d019  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18003d01e  xor     ebx, ebx
0x18003d020  mov     rax, rbx
0x18003d023  jmp     short loc_18003CFC5
```
