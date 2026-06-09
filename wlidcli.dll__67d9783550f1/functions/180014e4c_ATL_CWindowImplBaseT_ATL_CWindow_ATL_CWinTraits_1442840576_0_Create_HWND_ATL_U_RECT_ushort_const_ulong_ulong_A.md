# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x180014e4c`
- end: `0x180014fa6`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016800`
- `0x1800168a0`

## callees

- `0x18000c354`
- `0x18000c830`
- `0x180014e4c`
- `0x180042c18`
- `0x180042d2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014f9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014f9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ec3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014ec3`
- `USER32!CreateWindowExW` at `0x180014f85`
- `USER32!CreateWindowExW` at `0x180014f85`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU a1,
        __int64 a2,
        struct tagRECT *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        HMENU a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  HMENU hMenu; // rcx
  struct tagRECT *v14; // rax
  __int64 *v15; // [rsp+60h] [rbp-38h] BYREF
  char v16; // [rsp+68h] [rbp-30h]

  Data = (AtlThunkData_t *)*((_QWORD *)a1 + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)a1 + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == (HMENU)-16LL || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x180014FA5LL);
  }
  *((_QWORD *)a1 + 2) = a1;
  v16 = 0;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  v15 = qword_1800946C8;
  if ( (int)CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v15) >= 0 )
  {
    *((_QWORD *)a1 + 4) = qword_1800946F0;
    qword_1800946F0 = (__int64)(a1 + 4);
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v15);
  hMenu = a7;
  if ( !a7 && (dwStyle & 0x40000000) != 0 )
    hMenu = a1;
  v14 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v14 = a3;
  return CreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           v14->left,
           v14->top,
           v14->right - v14->left,
           v14->bottom - v14->top,
           0,
           hMenu,
           hModule,
           0);
}

```

## disassembly

```asm
0x180014e4c  push    rbx
0x180014e4e  push    rsi
0x180014e4f  push    rdi
0x180014e50  push    r14
0x180014e52  push    r15
0x180014e54  sub     rsp, 70h
0x180014e58  mov     rax, [rcx+28h]
0x180014e5c  xor     r15d, r15d
0x180014e5f  mov     r14, r9
0x180014e62  mov     rbx, r8
0x180014e65  mov     rdi, rcx
0x180014e68  test    rax, rax
0x180014e6b  jnz     short loc_180014E92
0x180014e6d  call    AtlThunk_AllocateData
0x180014e72  mov     [rdi+28h], rax
0x180014e76  test    rax, rax
0x180014e79  jnz     short loc_180014E92
0x180014e7b  lea     ecx, [rax+0Eh]; dwErrCode
0x180014e7e  call    cs:__imp_SetLastError
0x180014e84  xor     eax, eax
0x180014e86  add     rsp, 70h
0x180014e8a  pop     r15
0x180014e8c  pop     r14
0x180014e8e  pop     rdi
0x180014e8f  pop     rsi
0x180014e90  pop     rbx
0x180014e91  retn
0x180014e92  xor     r8d, r8d; FirstParameter
0x180014e95  xor     edx, edx; Proc
0x180014e97  mov     rcx, rax; Thunk
0x180014e9a  call    AtlThunk_InitData
0x180014e9f  cmp     [rsp+98h+arg_38], r15w
0x180014ea8  jz      short loc_180014E84
0x180014eaa  lea     rsi, [rdi+10h]
0x180014eae  test    rsi, rsi
0x180014eb1  jz      loc_180014F90
0x180014eb7  test    rdi, rdi
0x180014eba  jz      loc_180014F90
0x180014ec0  mov     [rsi], rdi
0x180014ec3  call    cs:__imp_GetCurrentThreadId
0x180014ec9  lea     rcx, [rsp+98h+var_38]
0x180014ece  mov     [rsp+98h+var_30], r15b
0x180014ed3  mov     [rsi+8], eax
0x180014ed6  lea     rax, qword_1800946C8
0x180014edd  mov     [rsp+98h+var_38], rax
0x180014ee2  call    ?Lock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(void)
0x180014ee7  test    eax, eax
0x180014ee9  js      short loc_180014EFD
0x180014eeb  mov     rax, cs:qword_1800946F0
0x180014ef2  mov     [rsi+10h], rax
0x180014ef6  mov     cs:qword_1800946F0, rsi
0x180014efd  lea     rcx, [rsp+98h+var_38]
0x180014f02  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180014f07  mov     rcx, [rsp+98h+arg_30]
0x180014f0f  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x180014f17  test    rcx, rcx
0x180014f1a  jnz     short loc_180014F25
0x180014f1c  bt      r9d, 1Eh
0x180014f21  cmovb   rcx, rdi
0x180014f25  mov     r10, cs:hModule
0x180014f2c  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x180014f33  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x180014f3b  test    rbx, rbx
0x180014f3e  mov     [rsp+98h+lpParam], r15; lpParam
0x180014f43  cmovnz  rax, rbx
0x180014f47  mov     [rsp+98h+hInstance], r10; hInstance
0x180014f4c  mov     [rsp+98h+hMenu], rcx; hMenu
0x180014f51  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x180014f58  mov     [rsp+98h+hWndParent], r15; hWndParent
0x180014f5d  mov     ebx, [rax+4]
0x180014f60  mov     r8d, [rax+8]
0x180014f64  mov     edi, [rax]
0x180014f66  sub     r8d, edi
0x180014f69  mov     r11d, [rax+0Ch]
0x180014f6d  sub     r11d, ebx
0x180014f70  mov     [rsp+98h+nHeight], r11d; nHeight
0x180014f75  mov     [rsp+98h+nWidth], r8d; nWidth
0x180014f7a  mov     r8, r14; lpWindowName
0x180014f7d  mov     [rsp+98h+Y], ebx; Y
0x180014f81  mov     [rsp+98h+X], edi; X
0x180014f85  call    cs:__imp_CreateWindowExW
0x180014f8b  jmp     loc_180014E86
0x180014f90  xor     r9d, r9d; lpArguments
0x180014f93  xor     r8d, r8d; nNumberOfArguments
0x180014f96  mov     ecx, 0C0000005h; dwExceptionCode
0x180014f9b  lea     edx, [r9+1]; dwExceptionFlags
0x180014f9f  call    cs:__imp_RaiseException
```
