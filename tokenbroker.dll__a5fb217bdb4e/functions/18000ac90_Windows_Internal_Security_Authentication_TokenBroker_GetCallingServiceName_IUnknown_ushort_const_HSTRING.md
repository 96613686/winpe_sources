# Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)

- ea: `0x18000ac90`
- end: `0x18000b05e`
- name: `?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct IUnknown *, const unsigned __int16 *, HSTRING *)`
- caller_count: `14`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d2b0`
- `0x18000e390`
- `0x180023910`
- `0x18008169c`
- `0x1800afd50`
- `0x1800aff38`
- `0x1800b048c`
- `0x1800c3708`
- `0x1800c38d8`
- `0x1800c42c8`
- `0x1800cf4f0`
- `0x1800cf66c`
- `0x1800cf824`
- `0x1800cf9dc`

## callees

- `0x18000ac90`
- `0x18000bd40`
- `0x1800565a0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ad50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000ad50`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000add0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000add0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ae4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000af6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ae4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000af6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ae3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000af5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ae3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000af5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af32`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000ad72`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000ad72`
- `combase!__imp_CoGetCallLocality` at `0x18000acd2`
- `combase!__imp_CoGetCallLocality` at `0x18000acd2`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000ae00`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000aefc`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000ae00`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000aefc`

## string_xrefs

- `0x18000acf0`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000af7e`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000afd4`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b005`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18000b02a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        HSTRING *a4)
{
  int v7; // eax
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rax
  int v11; // eax
  int v12; // ebx
  HSTRING v13; // r9
  HANDLE CurrentProcess; // rbx
  HSTRING v15; // rbx
  DWORD ProcessId; // r15d
  void *v17; // rcx
  __int64 (__fastcall *v18)(HSTRING, __int64, HANDLE *); // rbx
  int v19; // eax
  HLOCAL v20; // r15
  __int64 v21; // rcx
  const WCHAR *v22; // rcx
  int v23[2]; // [rsp+20h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-28h]
  _DWORD v25[8]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Process; // [rsp+98h] [rbp+48h] BYREF

  if ( !this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v23[0]);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v23[0]);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v23[0]);
    return 2147942487LL;
  }
  LODWORD(string) = 1;
  v7 = CoGetCallLocality(this, &string);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v7,
      v23[0]);
  }
  else if ( (_DWORD)string == 2 )
  {
LABEL_11:
    *(_QWORD *)a3 = 0;
    return 0;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)&a2->lpVtbl + v9) );
  if ( v9 < 0xB || (unsigned int)_o__wcsnicmp((char *)&a2[-2] + 2 * v9 - 6, L"svchost.exe", 11) )
    goto LABEL_11;
  Process = 0;
  string = 0;
  v11 = CoGetCallContextOfObject(this, &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &string);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v11,
      v23[0]);
    if ( string )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
    goto LABEL_22;
  }
  v13 = string;
  if ( string )
  {
    v18 = *(__int64 (__fastcall **)(HSTRING, __int64, HANDLE *))(*(_QWORD *)string + 24LL);
    if ( Process )
    {
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(Process);
      v13 = string;
    }
    Process = 0;
    v19 = v18(v13, 4096, &Process);
    v12 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v19,
        v23[0]);
      if ( string )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
      goto LABEL_22;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    if ( Process )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(Process);
    Process = CurrentProcess;
  }
  if ( string )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
  v12 = 0;
LABEL_22:
  if ( v12 >= 0 )
  {
    v15 = 0;
    ProcessId = GetProcessId(Process);
    memset(&v25[1], 0, 20);
    v25[0] = ProcessId;
    v25[1] = NtCurrentTeb()->SubProcessTag;
    if ( (unsigned int)I_QueryTagInformation(0, 1, v25) )
    {
      v23[1] = 0;
      hMem = 0;
      v23[0] = ProcessId;
      if ( !(unsigned int)I_QueryTagInformation(0, 3, v23) )
      {
        v20 = hMem;
        if ( hMem )
        {
          if ( *(_DWORD *)hMem == 1 )
          {
            v21 = *((_QWORD *)hMem + 1);
            if ( *(_DWORD *)v21 == 1 )
            {
              v22 = *(const WCHAR **)(v21 + 8);
              if ( v22 )
              {
                string = 0;
                do
                  ++v8;
                while ( v22[v8] );
                if ( v8 <= 0xFFFFFFFF && WindowsCreateString(v22, v8, &string) >= 0 )
                {
                  v15 = string;
                  WindowsDeleteString(0);
                }
              }
            }
          }
          LocalFree(v20);
        }
      }
    }
    else
    {
      v17 = *(void **)&v25[4];
      if ( *(_QWORD *)&v25[4] )
      {
        string = 0;
        do
          ++v8;
        while ( *(_WORD *)(*(_QWORD *)&v25[4] + 2 * v8) );
        if ( v8 <= 0xFFFFFFFF )
        {
          if ( WindowsCreateString(*(PCNZWCH *)&v25[4], v8, &string) >= 0 )
          {
            v15 = string;
            WindowsDeleteString(0);
          }
          v17 = *(void **)&v25[4];
        }
        LocalFree(v17);
        *(_QWORD *)&v25[4] = 0;
      }
    }
    *(_QWORD *)a3 = v15;
    if ( Process )
      CloseHandle(Process);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x818,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)(unsigned int)v12,
    v23[0]);
  if ( Process )
    CloseHandle(Process);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000ac90  mov     [rsp-28h+arg_8], rbx
0x18000ac95  push    rbp
0x18000ac96  push    rsi
0x18000ac97  push    rdi
0x18000ac98  push    r14
0x18000ac9a  push    r15
0x18000ac9c  mov     rbp, rsp
0x18000ac9f  sub     rsp, 50h
0x18000aca3  mov     rsi, r8
0x18000aca6  mov     rbx, rdx
0x18000aca9  mov     r15, rcx
0x18000acac  test    rcx, rcx
0x18000acaf  jz      loc_18000AFFB
0x18000acb5  test    rdx, rdx
0x18000acb8  jz      loc_18000AF74
0x18000acbe  test    r8, r8
0x18000acc1  jz      loc_18000B020
0x18000acc7  mov     dword ptr [rbp+string], 1
0x18000acce  lea     rdx, [rbp+string]
0x18000acd2  call    cs:__imp_CoGetCallLocality
0x18000acd8  test    eax, eax
0x18000acda  js      short loc_18000ACE9
0x18000acdc  cmp     dword ptr [rbp+string], 2
0x18000ace0  setz    al
0x18000ace3  test    al, al
0x18000ace5  jnz     short loc_18000AD20
0x18000ace7  jmp     short loc_18000AD01
0x18000ace9  mov     rcx, [rbp+28h]; this
0x18000aced  mov     r9d, eax; char *
0x18000acf0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000acf7  mov     edx, 748h; void *
0x18000acfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad01  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000ad08  mov     rax, r14
0x18000ad0b  nop     dword ptr [rax+rax+00h]
0x18000ad10  inc     rax
0x18000ad13  cmp     word ptr [rbx+rax*2], 0
0x18000ad18  jnz     short loc_18000AD10
0x18000ad1a  cmp     rax, 0Bh
0x18000ad1e  jnb     short loc_18000AD3B
0x18000ad20  xor     edi, edi
0x18000ad22  mov     [rsi], rdi
0x18000ad25  xor     eax, eax
0x18000ad27  mov     rbx, [rsp+50h+arg_8]
0x18000ad2f  add     rsp, 50h
0x18000ad33  pop     r15
0x18000ad35  pop     r14
0x18000ad37  pop     rdi
0x18000ad38  pop     rsi
0x18000ad39  pop     rbp
0x18000ad3a  retn
0x18000ad3b  add     rax, 0FFFFFFFFFFFFFFF5h
0x18000ad3f  lea     rcx, [rbx+rax*2]
0x18000ad43  mov     r8d, 0Bh
0x18000ad49  lea     rdx, aSvchostExe; "svchost.exe"
0x18000ad50  call    cs:__imp__o__wcsnicmp
0x18000ad56  test    eax, eax
0x18000ad58  jnz     short loc_18000AD20
0x18000ad5a  xor     edi, edi
0x18000ad5c  mov     [rbp+Process], rdi
0x18000ad60  mov     [rbp+string], rdi
0x18000ad64  lea     r8, [rbp+string]
0x18000ad68  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x18000ad6f  mov     rcx, r15
0x18000ad72  call    cs:__imp_CoGetCallContextOfObject
0x18000ad78  mov     ebx, eax
0x18000ad7a  test    eax, eax
0x18000ad7c  js      loc_18000AF99
0x18000ad82  mov     r9, [rbp+string]
0x18000ad86  test    r9, r9
0x18000ad89  jnz     loc_18000AE7A
0x18000ad8f  call    cs:__imp_GetCurrentProcess
0x18000ad95  mov     rbx, rax
0x18000ad98  mov     rcx, [rbp+Process]; hObject
0x18000ad9c  test    rcx, rcx
0x18000ad9f  jnz     loc_18000B053
0x18000ada5  mov     [rbp+Process], rbx
0x18000ada9  mov     rcx, [rbp+string]
0x18000adad  test    rcx, rcx
0x18000adb0  jz      short loc_18000ADBF
0x18000adb2  mov     rax, [rcx]
0x18000adb5  mov     rax, [rax+10h]
0x18000adb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adbe  nop
0x18000adbf  mov     ebx, edi
0x18000adc1  test    ebx, ebx
0x18000adc3  js      loc_18000AFCD
0x18000adc9  mov     rbx, rdi
0x18000adcc  mov     rcx, [rbp+Process]; Process
0x18000add0  call    cs:__imp_GetProcessId
0x18000add6  mov     r15d, eax
0x18000add9  xorps   xmm0, xmm0
0x18000addc  xor     eax, eax
0x18000adde  movups  xmmword ptr [rbp+sourceString], xmm0
0x18000ade2  mov     [rbp+var_C], eax
0x18000ade5  mov     [rbp+var_20], r15d
0x18000ade9  mov     rcx, gs:1720h
0x18000adf2  mov     dword ptr [rbp+sourceString], ecx
0x18000adf5  lea     r8, [rbp+var_20]
0x18000adf9  mov     edx, 1
0x18000adfe  xor     ecx, ecx
0x18000ae00  call    cs:__imp_I_QueryTagInformation
0x18000ae06  test    eax, eax
0x18000ae08  jnz     loc_18000AEE4
0x18000ae0e  mov     rcx, [rbp+sourceString+0Ch]; sourceString
0x18000ae12  test    rcx, rcx
0x18000ae15  jz      short loc_18000AE5F
0x18000ae17  mov     [rbp+string], rdi
0x18000ae1b  nop     dword ptr [rax+rax+00h]
0x18000ae20  inc     r14
0x18000ae23  cmp     [rcx+r14*2], bx
0x18000ae28  jnz     short loc_18000AE20
0x18000ae2a  mov     eax, 0FFFFFFFFh
0x18000ae2f  cmp     r14, rax
0x18000ae32  ja      short loc_18000AE55
0x18000ae34  mov     edx, r14d; length
0x18000ae37  lea     r8, [rbp+string]; string
0x18000ae3b  call    cs:__imp_WindowsCreateString
0x18000ae41  test    eax, eax
0x18000ae43  js      short loc_18000AE51
0x18000ae45  mov     rbx, [rbp+string]
0x18000ae49  xor     ecx, ecx; string
0x18000ae4b  call    cs:__imp_WindowsDeleteString
0x18000ae51  mov     rcx, [rbp+sourceString+0Ch]; hMem
0x18000ae55  call    cs:__imp_LocalFree
0x18000ae5b  mov     [rbp+sourceString+0Ch], rdi
0x18000ae5f  mov     [rsi], rbx
0x18000ae62  mov     rcx, [rbp+Process]; hObject
0x18000ae66  test    rcx, rcx
0x18000ae69  jz      loc_18000AD25
0x18000ae6f  call    cs:__imp_CloseHandle
0x18000ae75  jmp     loc_18000AD25
0x18000ae7a  mov     rax, [r9]
0x18000ae7d  mov     rbx, [rax+18h]
0x18000ae81  mov     rcx, [rbp+Process]; hObject
0x18000ae85  test    rcx, rcx
0x18000ae88  jnz     loc_18000B045
0x18000ae8e  mov     [rbp+Process], rdi
0x18000ae92  lea     r8, [rbp+Process]
0x18000ae96  mov     edx, 1000h
0x18000ae9b  mov     rcx, r9
0x18000ae9e  mov     rax, rbx
0x18000aea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aea6  mov     ebx, eax
0x18000aea8  test    eax, eax
0x18000aeaa  jns     loc_18000ADA9
0x18000aeb0  mov     rcx, [rbp+28h]; this
0x18000aeb4  mov     r9d, eax; char *
0x18000aeb7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000aebe  mov     edx, 1C4h; void *
0x18000aec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aec8  nop
0x18000aec9  mov     rcx, [rbp+string]
0x18000aecd  test    rcx, rcx
0x18000aed0  jz      short loc_18000AEDF
0x18000aed2  mov     rax, [rcx]
0x18000aed5  mov     rax, [rax+10h]
0x18000aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aede  nop
0x18000aedf  jmp     loc_18000ADC1
0x18000aee4  xor     eax, eax
0x18000aee6  mov     [rbp+var_2C], eax
0x18000aee9  mov     [rbp+hMem], rax
0x18000aeed  mov     [rbp+var_30], r15d
0x18000aef1  lea     r8, [rbp+var_30]
0x18000aef5  mov     edx, 3
0x18000aefa  xor     ecx, ecx
0x18000aefc  call    cs:__imp_I_QueryTagInformation
0x18000af02  test    eax, eax
0x18000af04  jnz     loc_18000AE5F
0x18000af0a  mov     r15, [rbp+hMem]
0x18000af0e  test    r15, r15
0x18000af11  jz      loc_18000AE5F
0x18000af17  cmp     dword ptr [r15], 1
0x18000af1b  jnz     short loc_18000AF2F
0x18000af1d  mov     rcx, [r15+8]
0x18000af21  cmp     dword ptr [rcx], 1
0x18000af24  jnz     short loc_18000AF2F
0x18000af26  mov     rcx, [rcx+8]; sourceString
0x18000af2a  test    rcx, rcx
0x18000af2d  jnz     short loc_18000AF3D
0x18000af2f  mov     rcx, r15; hMem
0x18000af32  call    cs:__imp_LocalFree
0x18000af38  jmp     loc_18000AE5F
0x18000af3d  mov     [rbp+string], rdi
0x18000af41  inc     r14
0x18000af44  cmp     [rcx+r14*2], bx
0x18000af49  jnz     short loc_18000AF41
0x18000af4b  mov     eax, 0FFFFFFFFh
0x18000af50  cmp     r14, rax
0x18000af53  ja      short loc_18000AF2F
0x18000af55  mov     edx, r14d; length
0x18000af58  lea     r8, [rbp+string]; string
0x18000af5c  call    cs:__imp_WindowsCreateString
0x18000af62  test    eax, eax
0x18000af64  js      short loc_18000AF2F
0x18000af66  mov     rbx, [rbp+string]
0x18000af6a  xor     ecx, ecx; string
0x18000af6c  call    cs:__imp_WindowsDeleteString
0x18000af72  jmp     short loc_18000AF2F
0x18000af74  mov     rcx, [rbp+28h]; this
0x18000af78  mov     r9d, 80070057h; char *
0x18000af7e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000af85  mov     edx, 7F3h; void *
0x18000af8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af8f  mov     eax, 80070057h
0x18000af94  jmp     loc_18000AD27
0x18000af99  mov     rcx, [rbp+28h]; this
0x18000af9d  mov     r9d, eax; char *
0x18000afa0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18000afa7  mov     edx, 1C1h; void *
0x18000afac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afb1  nop
0x18000afb2  mov     rcx, [rbp+string]
0x18000afb6  test    rcx, rcx
0x18000afb9  jz      short loc_18000AFC8
0x18000afbb  mov     rax, [rcx]
0x18000afbe  mov     rax, [rax+10h]
0x18000afc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afc7  nop
0x18000afc8  jmp     loc_18000ADC1
0x18000afcd  mov     rcx, [rbp+28h]; this
0x18000afd1  mov     r9d, ebx; char *
0x18000afd4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000afdb  mov     edx, 818h; void *
0x18000afe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afe5  mov     rcx, [rbp+Process]; hObject
0x18000afe9  test    rcx, rcx
0x18000afec  jz      short loc_18000AFF4
0x18000afee  call    cs:__imp_CloseHandle
0x18000aff4  mov     eax, ebx
0x18000aff6  jmp     loc_18000AD27
0x18000affb  mov     rcx, [rbp+28h]; this
0x18000afff  mov     r9d, 80070057h; char *
0x18000b005  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b00c  mov     edx, 7F2h; void *
0x18000b011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b016  mov     eax, 80070057h
0x18000b01b  jmp     loc_18000AD27
0x18000b020  mov     rcx, [rbp+28h]; this
0x18000b024  mov     r9d, 80070057h; char *
0x18000b02a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18000b031  mov     edx, 7F4h; void *
0x18000b036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b03b  mov     eax, 80070057h
0x18000b040  jmp     loc_18000AD27
0x18000b045  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b04a  mov     r9, [rbp+string]
0x18000b04e  jmp     loc_18000AE8E
0x18000b053  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000b058  jmp     loc_18000ADA5
```
