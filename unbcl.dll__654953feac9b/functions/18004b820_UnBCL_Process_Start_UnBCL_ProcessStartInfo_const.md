# UnBCL::Process::Start(UnBCL::ProcessStartInfo const *)

- ea: `0x18004b820`
- end: `0x18004bb77`
- name: `?Start@Process@UnBCL@@SAPEAV12@PEBVProcessStartInfo@2@@Z`
- size: `855`
- prototype: `struct UnBCL::Process *__fastcall(const struct UnBCL::ProcessStartInfo *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x18000225c`
- `0x180002276`
- `0x180002f90`
- `0x1800098b0`
- `0x1800099b0`
- `0x180009e7c`
- `0x18000afd0`
- `0x180011570`
- `0x180011940`
- `0x1800477d0`
- `0x18004b1c8`
- `0x18004b210`
- `0x18004b260`
- `0x18004b820`
- `0x18005c180`
- `0x1800646f0`
- `0x180068fe6`
- `0x18006f010`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x18004ba17`
- `KERNEL32!CreateProcessW` at `0x18004ba17`
- `SHELL32!ShellExecuteExW` at `0x18004b8bd`
- `SHELL32!ShellExecuteExW` at `0x18004b8bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct UnBCL::Process *__fastcall UnBCL::Process::Start(const struct UnBCL::ProcessStartInfo *a1)
{
  __int64 v2; // rdi
  UnBCL::Process *v4; // rax
  __int64 v5; // rax
  const unsigned __int16 *v6; // r8
  struct UnBCL::String *v7; // rax
  HANDLE hProcess; // rdi
  int v9; // ebx
  void *v10; // rax
  WCHAR *v11; // rax
  UnBCL::Process *v12; // rax
  __int64 v13; // rbx
  const struct UnBCL::String *v14; // rax
  UnBCL::ArgumentNullException *v15; // rax
  __int64 v16; // rax
  UnBCL::ArgumentException *v17; // rax
  __int64 v18; // rax
  const struct UnBCL::String *v19; // rax
  void **v20; // [rsp+58h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+78h] [rbp-90h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+88h] [rbp-80h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-10h]
  _BYTE v25[16]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v26; // [rsp+118h] [rbp+10h]
  void **v27; // [rsp+128h] [rbp+20h] BYREF
  __int64 pExceptionObject; // [rsp+1D8h] [rbp+D0h] BYREF
  UnBCL::ArgumentNullException *v29; // [rsp+1E0h] [rbp+D8h]

  v24 = -2;
  if ( !a1 )
  {
    v15 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v29 = v15;
    if ( v15 )
      v16 = UnBCL::ArgumentNullException::ArgumentNullException(v15, L"null startinfo to Process::Start");
    else
      v16 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v16,
                         "class UnBCL::Process *__cdecl UnBCL::Process::Start(const class UnBCL::ProcessStartInfo *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v2 = *(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 3) + 4LL) + 32);
  if ( !v2 )
  {
    v17 = (UnBCL::ArgumentException *)UnBCL::Object::operator new(0x38u);
    v29 = v17;
    if ( v17 )
      v18 = UnBCL::ArgumentException::ArgumentException(v17, L"null FileName to Process::Start");
    else
      v18 = 0;
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v18,
                         "class UnBCL::Process *__cdecl UnBCL::Process::Start(const class UnBCL::ProcessStartInfo *)");
    throw (UnBCL::ArgumentException **)&pExceptionObject;
  }
  if ( *((_DWORD *)a1 + 20) )
  {
    memset_0(&pExecInfo.hwnd, 0, 0x68u);
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 1088;
    pExecInfo.lpFile = *(LPCWSTR *)(v2 + 16);
    pExecInfo.lpVerb = 0;
    pExecInfo.lpParameters = *(LPCWSTR *)(*(_QWORD *)((char *)a1 + *(int *)(*((_QWORD *)a1 + 7) + 4LL) + 64) + 16LL);
    pExecInfo.lpDirectory = 0;
    pExecInfo.nShow = 1;
    if ( !ShellExecuteExW(&pExecInfo) )
    {
      v19 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_2__1();
      UnBCL::Win32Exception::ThrowLastError(v19, "base\\ntsetup\\unbcl\\src\\process.cpp", 90);
    }
    if ( pExecInfo.hProcess )
    {
      v4 = (UnBCL::Process *)UnBCL::Object::operator new(0x40u);
      pExceptionObject = (__int64)v4;
      if ( v4 )
        return (struct UnBCL::Process *)UnBCL::Process::Process(v4, pExecInfo.hProcess, 0);
      else
        return 0;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    memset_0(&pExecInfo, 0, 0x68u);
    pExecInfo.cbSize = 104;
    memset(&pExecInfo.hwnd, 0, 24);
    HIDWORD(pExecInfo.hInstApp) = 0;
    WORD1(pExecInfo.lpIDList) = 0;
    pExecInfo.lpClass = 0;
    v5 = *(int *)(*((_QWORD *)a1 + 7) + 4LL);
    if ( *(_QWORD *)((char *)a1 + v5 + 64) )
      v6 = *(const unsigned __int16 **)(*(_QWORD *)((char *)a1 + v5 + 64) + 16LL);
    else
      v6 = &qword_180089560;
    v7 = UnBCL::String::Format(L"\"%s\" %s", *(_QWORD *)(v2 + 16), v6);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v20, v7);
    hProcess = ProcessInformation.hProcess;
    UnBCL::Array<unsigned short>::Array<unsigned short>(
      v25,
      (unsigned int)(*(_DWORD *)(*((_QWORD *)ProcessInformation.hProcess + 2) - 16LL) + 1),
      0,
      1);
    v9 = *(_DWORD *)(*((_QWORD *)hProcess + 2) - 16LL);
    v10 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 112LL))(v26, 0);
    memcpy_0(v10, *((const void **)hProcess + 2), 2LL * (v9 + 1));
    *(_OWORD *)&ProcessInformation.hThread = 0;
    v22 = 0;
    v11 = (WCHAR *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 112LL))(v26, 0);
    if ( !CreateProcessW(
            0,
            v11,
            0,
            0,
            0,
            0,
            0,
            0,
            (LPSTARTUPINFOW)&pExecInfo,
            (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
    {
      v14 = (const struct UnBCL::String *)UnBCL::_::StringLiteral_3__0();
      UnBCL::Win32Exception::ThrowLastError(v14, "base\\ntsetup\\unbcl\\src\\process.cpp", 120);
    }
    v12 = (UnBCL::Process *)UnBCL::Object::operator new(0x40u);
    pExceptionObject = (__int64)v12;
    if ( v12 )
      v13 = UnBCL::Process::Process(v12, ProcessInformation.hThread, *(void **)&ProcessInformation.dwProcessId);
    else
      v13 = 0;
    UnBCL::Array<unsigned short>::~Array<unsigned short>(&v27);
    v27 = &UnBCL::Object::`vftable';
    v20 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v20);
    return (struct UnBCL::Process *)v13;
  }
}

```

## disassembly

```asm
0x18004b820  mov     rax, rsp
0x18004b823  push    rbp
0x18004b824  push    rdi
0x18004b825  push    r14
0x18004b827  lea     rbp, [rax-0C8h]
0x18004b82e  sub     rsp, 1B0h
0x18004b835  mov     [rbp+0C0h+var_D0], 0FFFFFFFFFFFFFFFEh
0x18004b83d  mov     [rax+18h], rbx
0x18004b841  mov     rbx, rcx
0x18004b844  xor     r14d, r14d
0x18004b847  test    rcx, rcx
0x18004b84a  jz      loc_18004BAB4
0x18004b850  mov     rax, [rcx+18h]
0x18004b854  movsxd  rcx, dword ptr [rax+4]
0x18004b858  mov     rdi, [rcx+rbx+20h]
0x18004b85d  test    rdi, rdi
0x18004b860  jz      loc_18004BB08
0x18004b866  xor     edx, edx; Val
0x18004b868  lea     r8d, [r14+68h]; Size
0x18004b86c  cmp     [rbx+50h], r14d
0x18004b870  jz      loc_18004B90D
0x18004b876  lea     rcx, [rbp+0C0h+pExecInfo.hwnd]; void *
0x18004b87a  call    memset_0
0x18004b87f  mov     [rbp+0C0h+pExecInfo.cbSize], 70h ; 'p'
0x18004b886  mov     [rbp+0C0h+pExecInfo.fMask], 440h
0x18004b88d  mov     rax, [rdi+10h]
0x18004b891  mov     [rbp+0C0h+pExecInfo.lpFile], rax
0x18004b895  mov     [rbp+0C0h+pExecInfo.lpVerb], r14
0x18004b899  mov     rax, [rbx+38h]
0x18004b89d  movsxd  rcx, dword ptr [rax+4]
0x18004b8a1  mov     rax, [rcx+rbx+40h]
0x18004b8a6  mov     rcx, [rax+10h]
0x18004b8aa  mov     [rbp+0C0h+pExecInfo.lpParameters], rcx
0x18004b8ae  mov     [rbp+0C0h+pExecInfo.lpDirectory], r14
0x18004b8b2  mov     [rbp+0C0h+pExecInfo.nShow], 1
0x18004b8b9  lea     rcx, [rbp+0C0h+pExecInfo]; pExecInfo
0x18004b8bd  call    cs:__imp_ShellExecuteExW
0x18004b8c3  test    eax, eax
0x18004b8c5  jz      loc_18004BB5C
0x18004b8cb  cmp     [rbp+0C0h+pExecInfo.hProcess], r14
0x18004b8cf  jnz     short loc_18004B8D8
0x18004b8d1  xor     eax, eax
0x18004b8d3  jmp     loc_18004BA84
0x18004b8d8  mov     ecx, 40h ; '@'; unsigned __int64
0x18004b8dd  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004b8e2  mov     [rbp+0C0h+pExceptionObject], rax
0x18004b8e9  test    rax, rax
0x18004b8ec  jz      short loc_18004B905
0x18004b8ee  mov     r9d, 1
0x18004b8f4  xor     r8d, r8d; void *
0x18004b8f7  mov     rdx, [rbp+0C0h+pExecInfo.hProcess]; void *
0x18004b8fb  mov     rcx, rax; this
0x18004b8fe  call    ??0Process@UnBCL@@IEAA@PEAX0@Z; UnBCL::Process::Process(void *,void *)
0x18004b903  jmp     short loc_18004B908
0x18004b905  mov     rax, r14
0x18004b908  jmp     loc_18004BA84
0x18004b90d  lea     rcx, [rbp+0C0h+pExecInfo]; void *
0x18004b911  call    memset_0
0x18004b916  mov     [rbp+0C0h+pExecInfo.cbSize], 68h ; 'h'
0x18004b91d  mov     [rbp+0C0h+pExecInfo.hwnd], r14
0x18004b921  xorps   xmm0, xmm0
0x18004b924  movdqa  xmmword ptr [rbp+0C0h+pExecInfo.lpVerb], xmm0
0x18004b929  mov     dword ptr [rbp+0C0h+pExecInfo.hInstApp+4], r14d
0x18004b92d  mov     word ptr [rbp+0C0h+pExecInfo.lpIDList+2], r14w
0x18004b932  mov     [rbp+0C0h+pExecInfo.lpClass], r14
0x18004b936  mov     rax, [rbx+38h]
0x18004b93a  movsxd  rax, dword ptr [rax+4]
0x18004b93e  cmp     [rax+rbx+40h], r14
0x18004b943  jz      short loc_18004B950
0x18004b945  mov     rax, [rax+rbx+40h]
0x18004b94a  mov     r8, [rax+10h]
0x18004b94e  jmp     short loc_18004B957
0x18004b950  lea     r8, qword_180089560
0x18004b957  mov     rdx, [rdi+10h]
0x18004b95b  lea     rcx, aSS_0; "\"%s\" %s"
0x18004b962  call    ?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18004b967  mov     rdx, rax
0x18004b96a  lea     rcx, [rsp+1C0h+var_170]
0x18004b96f  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18004b974  nop
0x18004b975  mov     rdi, [rsp+1C0h+ProcessInformation.hProcess]
0x18004b97a  mov     rax, [rdi+10h]
0x18004b97e  mov     edx, [rax-10h]
0x18004b981  inc     edx
0x18004b983  mov     r9d, 1
0x18004b989  xor     r8d, r8d
0x18004b98c  lea     rcx, [rbp+0C0h+var_C0]
0x18004b990  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18004b995  nop
0x18004b996  mov     rax, [rdi+10h]
0x18004b99a  mov     ebx, [rax-10h]
0x18004b99d  mov     rcx, [rbp+0C0h+var_B0]
0x18004b9a1  mov     rax, [rcx]
0x18004b9a4  xor     edx, edx
0x18004b9a6  mov     rax, [rax+70h]
0x18004b9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9af  lea     ecx, [rbx+1]
0x18004b9b2  movsxd  r8, ecx
0x18004b9b5  add     r8, r8; Size
0x18004b9b8  mov     rdx, [rdi+10h]; Src
0x18004b9bc  mov     rcx, rax; void *
0x18004b9bf  call    memcpy_0
0x18004b9c4  xorps   xmm0, xmm0
0x18004b9c7  xor     eax, eax
0x18004b9c9  movups  xmmword ptr [rsp+1C0h+ProcessInformation.hThread], xmm0
0x18004b9ce  mov     [rsp+1C0h+var_150], rax
0x18004b9d3  mov     rcx, [rbp+0C0h+var_B0]
0x18004b9d7  mov     rax, [rcx]
0x18004b9da  xor     edx, edx
0x18004b9dc  mov     rax, [rax+70h]
0x18004b9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9e5  lea     rcx, [rsp+1C0h+ProcessInformation.hThread]
0x18004b9ea  mov     [rsp+1C0h+lpProcessInformation], rcx; lpProcessInformation
0x18004b9ef  lea     rcx, [rbp+0C0h+pExecInfo]
0x18004b9f3  mov     [rsp+1C0h+lpStartupInfo], rcx; lpStartupInfo
0x18004b9f8  mov     [rsp+1C0h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18004b9fd  mov     [rsp+1C0h+lpEnvironment], r14; lpEnvironment
0x18004ba02  mov     [rsp+1C0h+dwCreationFlags], r14d; dwCreationFlags
0x18004ba07  mov     [rsp+1C0h+bInheritHandles], r14d; bInheritHandles
0x18004ba0c  xor     r9d, r9d; lpThreadAttributes
0x18004ba0f  xor     r8d, r8d; lpProcessAttributes
0x18004ba12  mov     rdx, rax; lpCommandLine
0x18004ba15  xor     ecx, ecx; lpApplicationName
0x18004ba17  call    cs:__imp_CreateProcessW
0x18004ba1d  test    eax, eax
0x18004ba1f  jz      short loc_18004BA98
0x18004ba21  mov     ecx, 40h ; '@'; unsigned __int64
0x18004ba26  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004ba2b  mov     [rbp+0C0h+pExceptionObject], rax
0x18004ba32  test    rax, rax
0x18004ba35  jz      short loc_18004BA54
0x18004ba37  mov     r9d, 1
0x18004ba3d  mov     r8, qword ptr [rsp+1C0h+ProcessInformation.dwProcessId]; void *
0x18004ba42  mov     rdx, [rsp+1C0h+ProcessInformation.hThread]; void *
0x18004ba47  mov     rcx, rax; this
0x18004ba4a  call    ??0Process@UnBCL@@IEAA@PEAX0@Z; UnBCL::Process::Process(void *,void *)
0x18004ba4f  mov     rbx, rax
0x18004ba52  jmp     short loc_18004BA57
0x18004ba54  mov     rbx, r14
0x18004ba57  lea     rcx, [rbp+0C0h+var_A0]
0x18004ba5b  call    ??1?$Array@G@UnBCL@@UEAA@XZ; UnBCL::Array<ushort>::~Array<ushort>(void)
0x18004ba60  lea     rax, ??_7Object@UnBCL@@6B@; const UnBCL::Object::`vftable'
0x18004ba67  mov     [rbp+0C0h+var_A0], rax
0x18004ba6b  lea     rax, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18004ba72  mov     [rsp+1C0h+var_170], rax
0x18004ba77  lea     rcx, [rsp+1C0h+var_170]
0x18004ba7c  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18004ba81  mov     rax, rbx
0x18004ba84  mov     rbx, [rsp+1C0h+arg_10]
0x18004ba8c  add     rsp, 1B0h
0x18004ba93  pop     r14
0x18004ba95  pop     rdi
0x18004ba96  pop     rbp
0x18004ba97  retn
0x18004ba98  call    UnBCL_____StringLiteral_3__0
0x18004ba9d  nop
0x18004ba9e  mov     rcx, rax; struct UnBCL::String *
0x18004baa1  mov     r8d, 78h ; 'x'; int
0x18004baa7  lea     rdx, aBaseNtsetupUnb_5; "base\\ntsetup\\unbcl\\src\\process.cpp"
0x18004baae  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
0x18004bab4  mov     ecx, 38h ; '8'; unsigned __int64
0x18004bab9  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004babe  mov     [rbp+0C0h+arg_8], rax
0x18004bac5  test    rax, rax
0x18004bac8  jz      short loc_18004BADB
0x18004baca  lea     rdx, aNullStartinfoT; "null startinfo to Process::Start"
0x18004bad1  mov     rcx, rax; this
0x18004bad4  call    ??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x18004bad9  jmp     short loc_18004BADE
0x18004badb  mov     rax, r14
0x18004bade  lea     rdx, aClassUnbclProc; "class UnBCL::Process *__cdecl UnBCL::Pr"...
0x18004bae5  mov     rcx, rax
0x18004bae8  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004baed  mov     [rbp+0C0h+pExceptionObject], rax
0x18004baf4  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x18004bafb  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x18004bb02  call    _CxxThrowException_0
0x18004bb08  mov     ecx, 38h ; '8'; unsigned __int64
0x18004bb0d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18004bb12  mov     [rbp+0C0h+arg_8], rax
0x18004bb19  test    rax, rax
0x18004bb1c  jz      short loc_18004BB2F
0x18004bb1e  lea     rdx, aNullFilenameTo; "null FileName to Process::Start"
0x18004bb25  mov     rcx, rax; this
0x18004bb28  call    ??0ArgumentException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentException::ArgumentException(ushort const *)
0x18004bb2d  jmp     short loc_18004BB32
0x18004bb2f  mov     rax, r14
0x18004bb32  lea     rdx, aClassUnbclProc; "class UnBCL::Process *__cdecl UnBCL::Pr"...
0x18004bb39  mov     rcx, rax
0x18004bb3c  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18004bb41  mov     [rbp+0C0h+pExceptionObject], rax
0x18004bb48  lea     rdx, _TI5PEAVArgumentException@UnBCL@@; pThrowInfo
0x18004bb4f  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x18004bb56  call    _CxxThrowException_0
0x18004bb5c  call    UnBCL_____StringLiteral_2__1
0x18004bb61  mov     rcx, rax; struct UnBCL::String *
0x18004bb64  mov     r8d, 5Ah ; 'Z'; int
0x18004bb6a  lea     rdx, aBaseNtsetupUnb_5; "base\\ntsetup\\unbcl\\src\\process.cpp"
0x18004bb71  call    ?ThrowLastError@Win32Exception@UnBCL@@SAXPEBVString@2@PEBDH@Z; UnBCL::Win32Exception::ThrowLastError(UnBCL::String const *,char const *,int)
```
