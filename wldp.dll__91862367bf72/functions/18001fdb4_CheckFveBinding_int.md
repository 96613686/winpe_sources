# CheckFveBinding(int *)

- ea: `0x18001fdb4`
- end: `0x18001ff62`
- name: `?CheckFveBinding@@YAJPEAH@Z`
- size: `430`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ade4`
- `0x18002af60`

## callees

- `0x18001fdb4`
- `0x180020154`
- `0x1800201b4`
- `0x1800201d4`
- `0x180021ec0`
- `0x180022a10`
- `0x18002b670`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fe7e`

## string_xrefs

- `0x18001fe29`: `onecore\base\ngscb\wldp\dll\securitywatermark.cpp`
- `0x18001fe5a`: `onecore\base\ngscb\wldp\dll\securitywatermark.cpp`
- `0x18001fe8d`: `onecore\base\ngscb\wldp\dll\securitywatermark.cpp`
- `0x18001ff04`: `TEST FAIL: Failed to get WCOS Device Encryption Security Info: hr=0x%08lx\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckFveBinding(int *a1)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rdi
  const char *v5; // r9
  unsigned int v6; // eax
  FARPROC v7; // rax
  const char *v8; // r9
  int v9; // eax
  int v10; // eax
  int v12; // [rsp+30h] [rbp-49h] BYREF
  int v13; // [rsp+34h] [rbp-45h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-41h] BYREF
  __int64 v15; // [rsp+40h] [rbp-39h] BYREF
  int v16; // [rsp+48h] [rbp-31h]
  _BYTE v17[8]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v18; // [rsp+58h] [rbp-21h]
  __int64 v19; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v12 = -1;
  v15 = 786433;
  v16 = 0;
  memset_0(v17, 0, 0x40u);
  v13 = 64;
  *a1 = 0;
  LoadFveapi(&hModule);
  if ( !hModule )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x51A,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\securitywatermark.cpp",
                  v2);
    goto LABEL_19;
  }
  ProcAddress = GetProcAddress(hModule, "FveQuery");
  if ( !ProcAddress )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x51D,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\securitywatermark.cpp",
           v5);
LABEL_5:
    LastError = v6;
    goto LABEL_19;
  }
  v7 = GetProcAddress(hModule, "FveGetSecureBootBindingState");
  if ( !v7 )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x521,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\securitywatermark.cpp",
           v8);
    goto LABEL_5;
  }
  v9 = ((__int64 (__fastcall *)(int *))v7)(&v12);
  LastError = v9;
  if ( v9 >= 0 )
  {
    if ( (unsigned int)(v12 - 2) <= 1 )
    {
      v10 = ((__int64 (__fastcall *)(__int64, __int64 *, __int64, _BYTE *, int *))ProcAddress)(5, &v15, 12, v17, &v13);
      LastError = v10;
      if ( v10 >= 0 )
      {
        if ( (v18 || v19) && !v17[5] )
        {
          LogFormatOut("TEST FAIL: Device is not secure for WCOS Device Encryption\n");
        }
        else
        {
          *a1 = 1;
          LastError = 0;
        }
      }
      else
      {
        LogFormatOut("TEST FAIL: Failed to get WCOS Device Encryption Security Info: hr=0x%08lx\n", v10);
      }
    }
    else
    {
      LogFormatOut("TEST FAIL: Invalid SecureBoot Binding State: %d\n", v12);
    }
  }
  else
  {
    LogFormatOut("TEST FAIL: Failed to get SecureBoot Binding State: hr=0x%08lx\n", v9);
  }
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return LastError;
}

```

## disassembly

```asm
0x18001fdb4  push    rbp
0x18001fdb6  push    rbx
0x18001fdb7  push    rsi
0x18001fdb8  push    rdi
0x18001fdb9  push    r12
0x18001fdbb  push    r15
0x18001fdbd  lea     rbp, [rsp-2Fh]
0x18001fdc2  sub     rsp, 0A8h
0x18001fdc9  mov     rax, cs:__security_cookie
0x18001fdd0  xor     rax, rsp
0x18001fdd3  mov     [rbp+57h+var_40], rax
0x18001fdd7  mov     rsi, rcx
0x18001fdda  mov     [rbp+57h+var_A0], 0FFFFFFFFh
0x18001fde1  mov     r15d, 1
0x18001fde7  mov     [rbp+57h+var_90], 0C0001h
0x18001fdef  xor     eax, eax
0x18001fdf1  lea     r12d, [r15+0Bh]
0x18001fdf5  mov     [rbp+57h+var_88], eax
0x18001fdf8  lea     ebx, [rax+40h]
0x18001fdfb  mov     r8d, ebx; Size
0x18001fdfe  xor     edx, edx; Val
0x18001fe00  lea     rcx, [rbp+57h+var_80]; void *
0x18001fe04  call    memset_0
0x18001fe09  mov     [rbp+57h+var_9C], ebx
0x18001fe0c  mov     dword ptr [rsi], 0
0x18001fe12  lea     rcx, [rbp+57h+hModule]
0x18001fe16  call    ?LoadFveapi@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; LoadFveapi(void)
0x18001fe1b  nop
0x18001fe1c  mov     rcx, [rbp+57h+hModule]; hModule
0x18001fe20  test    rcx, rcx
0x18001fe23  jnz     short loc_18001FE41
0x18001fe25  mov     rcx, [rbp+5Fh]; this
0x18001fe29  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\wldp\\dll\\securi"...
0x18001fe30  mov     edx, 51Ah; void *
0x18001fe35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fe3a  mov     ebx, eax
0x18001fe3c  jmp     loc_18001FF3B
0x18001fe41  lea     rdx, aFvequery; "FveQuery"
0x18001fe48  call    cs:__imp_GetProcAddress
0x18001fe4e  mov     rdi, rax
0x18001fe51  test    rax, rax
0x18001fe54  jnz     short loc_18001FE73
0x18001fe56  mov     rcx, [rbp+5Fh]; this
0x18001fe5a  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\wldp\\dll\\securi"...
0x18001fe61  mov     edx, 51Dh; void *
0x18001fe66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fe6b  nop
0x18001fe6c  mov     ebx, eax
0x18001fe6e  jmp     loc_18001FF3B
0x18001fe73  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x18001fe7a  mov     rcx, [rbp+57h+hModule]; hModule
0x18001fe7e  call    cs:__imp_GetProcAddress
0x18001fe84  test    rax, rax
0x18001fe87  jnz     short loc_18001FEA1
0x18001fe89  mov     rcx, [rbp+5Fh]; this
0x18001fe8d  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\wldp\\dll\\securi"...
0x18001fe94  mov     edx, 521h; void *
0x18001fe99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fe9e  nop
0x18001fe9f  jmp     short loc_18001FE6C
0x18001fea1  lea     rcx, [rbp+57h+var_A0]
0x18001fea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feaa  mov     ebx, eax
0x18001feac  test    eax, eax
0x18001feae  jns     short loc_18001FEC1
0x18001feb0  mov     edx, eax
0x18001feb2  lea     rcx, aTestFailFailed_0; "TEST FAIL: Failed to get SecureBoot Bin"...
0x18001feb9  call    LogFormatOut
0x18001febe  nop
0x18001febf  jmp     short loc_18001FF3B
0x18001fec1  mov     edx, [rbp+57h+var_A0]
0x18001fec4  lea     eax, [rdx-2]
0x18001fec7  cmp     eax, r15d
0x18001feca  jbe     short loc_18001FEDB
0x18001fecc  lea     rcx, aTestFailInvali; "TEST FAIL: Invalid SecureBoot Binding S"...
0x18001fed3  call    LogFormatOut
0x18001fed8  nop
0x18001fed9  jmp     short loc_18001FF3B
0x18001fedb  lea     rax, [rbp+57h+var_9C]
0x18001fedf  mov     [rsp+0D0h+var_B0], rax
0x18001fee4  lea     r9, [rbp+57h+var_80]
0x18001fee8  mov     r8d, r12d
0x18001feeb  lea     rdx, [rbp+57h+var_90]
0x18001feef  mov     ecx, 5
0x18001fef4  mov     rax, rdi
0x18001fef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fefc  mov     ebx, eax
0x18001fefe  test    eax, eax
0x18001ff00  jns     short loc_18001FF13
0x18001ff02  mov     edx, eax
0x18001ff04  lea     rcx, aTestFailFailed; "TEST FAIL: Failed to get WCOS Device En"...
0x18001ff0b  call    LogFormatOut
0x18001ff10  nop
0x18001ff11  jmp     short loc_18001FF3B
0x18001ff13  cmp     [rbp+57h+var_78], 0
0x18001ff18  jnz     short loc_18001FF21
0x18001ff1a  cmp     [rbp+57h+var_50], 0
0x18001ff1f  jz      short loc_18001FF36
0x18001ff21  cmp     [rbp+57h+var_7B], 0
0x18001ff25  jnz     short loc_18001FF36
0x18001ff27  lea     rcx, aTestFailDevice; "TEST FAIL: Device is not secure for WCO"...
0x18001ff2e  call    LogFormatOut
0x18001ff33  nop
0x18001ff34  jmp     short loc_18001FF3B
0x18001ff36  mov     [rsi], r15d
0x18001ff39  xor     ebx, ebx
0x18001ff3b  lea     rcx, [rbp+57h+hModule]
0x18001ff3f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001ff44  mov     eax, ebx
0x18001ff46  mov     rcx, [rbp+57h+var_40]
0x18001ff4a  xor     rcx, rsp; StackCookie
0x18001ff4d  call    __security_check_cookie
0x18001ff52  add     rsp, 0A8h
0x18001ff59  pop     r15
0x18001ff5b  pop     r12
0x18001ff5d  pop     rdi
0x18001ff5e  pop     rsi
0x18001ff5f  pop     rbx
0x18001ff60  pop     rbp
0x18001ff61  retn
```
