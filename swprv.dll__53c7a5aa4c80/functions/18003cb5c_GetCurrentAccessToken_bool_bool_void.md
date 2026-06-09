# GetCurrentAccessToken(bool,bool,void * *)

- ea: `0x18003cb5c`
- end: `0x18003cdec`
- name: `?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z`
- size: `656`
- prototype: `char __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003d78c`

## callees

- `0x18000212c`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x1800377c4`
- `0x18003cb5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cc54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cc54`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cc65`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cc65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ccfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003ccfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cd12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cd12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cd2f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cd2f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003cbe6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003cbe6`

## string_xrefs

- `0x18003cb8a`: `GetCurrentAccessToken`
- `0x18003cb7e`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003cc3b`: `CoImpersonateClient`
- `0x18003ccaa`: `OpenProcessToken`
- `0x18003cd7b`: `OpenThreadToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall GetCurrentAccessToken(__int64 a1, __int64 a2, void **a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  HANDLE CurrentProcess; // rax
  char v7; // dl
  char v8; // bl
  HANDLE CurrentThread; // rax
  BOOL v11; // edi
  signed int LastError; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v15; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v16; // [rsp+30h] [rbp-D0h]
  int v17; // [rsp+38h] [rbp-C8h]
  int v18; // [rsp+3Ch] [rbp-C4h]
  int v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+C0h] [rbp-40h]
  LPVOID v22; // [rsp+D0h] [rbp-30h] BYREF
  HRESULT v23; // [rsp+D8h] [rbp-28h]

  v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v15 = L"GetCurrentAccessToken";
  v16 = L"SECSECRC";
  v17 = 92;
  v18 = 11;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v22, (__int64)&v14, 0);
  v4 = CoImpersonateClient();
  v5 = v4;
  v23 = v4;
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    v11 = OpenThreadToken(CurrentThread, 8u, 1, a3);
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v23 = CoRevertToSelf();
    if ( v23 < 0 )
    {
      v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v15 = L"GetCurrentAccessToken";
      v16 = L"SECSECRC";
      v17 = 140;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::TranslateWin32Error(&v22, &v14, L"CoRevertToSelf");
    }
    if ( !v11 )
    {
      v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v15 = L"GetCurrentAccessToken";
      v16 = L"SECSECRC";
      v17 = 143;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::TranslateGenericError(&v22, &v14, v13, L"OpenThreadToken");
    }
    v7 = 1;
  }
  else
  {
    if ( v4 != -2147417833 )
    {
      v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v15 = L"GetCurrentAccessToken";
      v16 = L"SECSECRC";
      v17 = 107;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::TranslateGenericError(&v22, &v14, v5, L"CoImpersonateClient");
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, a3) )
    {
      v14 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v15 = L"GetCurrentAccessToken";
      v16 = L"SECSECRC";
      v17 = 112;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      CVssFunctionTracer::TranslateWin32Error(&v22, &v14, L"OpenProcessToken");
    }
    v23 = 0;
    v7 = 0;
  }
  v8 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v22, v7);
  CVssFunctionTracer::~CVssFunctionTracer(&v22);
  return v8;
}

```

## disassembly

```asm
0x18003cb5c  mov     [rsp-8+arg_0], rbx
0x18003cb61  mov     [rsp-8+arg_8], rdi
0x18003cb66  push    rbp
0x18003cb67  push    r12
0x18003cb69  push    r13
0x18003cb6b  push    r14
0x18003cb6d  push    r15
0x18003cb6f  lea     rbp, [rsp-40h]
0x18003cb74  sub     rsp, 140h
0x18003cb7b  mov     rdi, r8
0x18003cb7e  lea     r14, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003cb85  mov     [rsp+160h+var_140], r14
0x18003cb8a  lea     r15, aGetcurrentacce; "GetCurrentAccessToken"
0x18003cb91  mov     [rsp+160h+var_138], r15
0x18003cb96  lea     r12, aSecsecrc; "SECSECRC"
0x18003cb9d  mov     [rsp+160h+var_130], r12
0x18003cba2  mov     [rsp+160h+var_128], 5Ch ; '\'
0x18003cbaa  mov     r13d, 0Bh
0x18003cbb0  mov     [rsp+160h+var_124], r13d
0x18003cbb5  mov     [rsp+160h+var_120], 0FFh
0x18003cbbd  mov     [rbp+60h+var_A0], 1000000h
0x18003cbc4  xor     edx, edx; Val
0x18003cbc6  lea     r8d, [r13+6Dh]; Size
0x18003cbca  lea     rcx, [rsp+160h+var_118]; void *
0x18003cbcf  call    memset_0
0x18003cbd4  xor     r8d, r8d
0x18003cbd7  lea     rdx, [rsp+160h+var_140]
0x18003cbdc  lea     rcx, [rbp+60h+var_90]
0x18003cbe0  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003cbe5  nop
0x18003cbe6  call    cs:__imp_CoImpersonateClient
0x18003cbec  mov     ebx, eax
0x18003cbee  mov     [rbp+60h+var_88], eax
0x18003cbf1  test    eax, eax
0x18003cbf3  jns     loc_18003CCFC
0x18003cbf9  cmp     eax, 80010117h
0x18003cbfe  jz      short loc_18003CC54
0x18003cc00  mov     [rsp+160h+var_140], r14
0x18003cc05  mov     [rsp+160h+var_138], r15
0x18003cc0a  mov     [rsp+160h+var_130], r12
0x18003cc0f  mov     [rsp+160h+var_128], 6Bh ; 'k'
0x18003cc17  mov     [rsp+160h+var_124], r13d
0x18003cc1c  mov     [rsp+160h+var_120], 0FFh
0x18003cc24  mov     [rbp+60h+var_A0], 1000000h
0x18003cc2b  xor     edx, edx; Val
0x18003cc2d  lea     r8d, [r13+6Dh]; Size
0x18003cc31  lea     rcx, [rsp+160h+var_118]; void *
0x18003cc36  call    memset_0
0x18003cc3b  lea     r9, aCoimpersonatec_0; "CoImpersonateClient"
0x18003cc42  mov     r8d, ebx
0x18003cc45  lea     rdx, [rsp+160h+var_140]
0x18003cc4a  lea     rcx, [rbp+60h+var_90]
0x18003cc4e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003cc54  call    cs:__imp_GetCurrentProcess
0x18003cc5a  mov     rcx, rax; ProcessHandle
0x18003cc5d  mov     r8, rdi; TokenHandle
0x18003cc60  mov     edx, 0Ah; DesiredAccess
0x18003cc65  call    cs:__imp_OpenProcessToken
0x18003cc6b  test    eax, eax
0x18003cc6d  jnz     short loc_18003CCC0
0x18003cc6f  mov     [rsp+160h+var_140], r14
0x18003cc74  mov     [rsp+160h+var_138], r15
0x18003cc79  mov     [rsp+160h+var_130], r12
0x18003cc7e  mov     [rsp+160h+var_128], 70h ; 'p'
0x18003cc86  mov     [rsp+160h+var_124], r13d
0x18003cc8b  mov     [rsp+160h+var_120], 0FFh
0x18003cc93  mov     [rbp+60h+var_A0], 1000000h
0x18003cc9a  xor     edx, edx; Val
0x18003cc9c  lea     r8d, [rax+78h]; Size
0x18003cca0  lea     rcx, [rsp+160h+var_118]; void *
0x18003cca5  call    memset_0
0x18003ccaa  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x18003ccb1  lea     rdx, [rsp+160h+var_140]
0x18003ccb6  lea     rcx, [rbp+60h+var_90]
0x18003ccba  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18003ccc0  mov     [rbp+60h+var_88], 0
0x18003ccc7  xor     edx, edx; bool
0x18003ccc9  lea     rcx, [rbp+60h+var_90]; this
0x18003cccd  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003ccd2  mov     bl, al
0x18003ccd4  lea     rcx, [rbp+60h+var_90]; this
0x18003ccd8  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003ccdd  mov     al, bl
0x18003ccdf  lea     r11, [rsp+160h+var_20]
0x18003cce7  mov     rbx, [r11+30h]
0x18003cceb  mov     rdi, [r11+38h]
0x18003ccef  mov     rsp, r11
0x18003ccf2  pop     r15
0x18003ccf4  pop     r14
0x18003ccf6  pop     r13
0x18003ccf8  pop     r12
0x18003ccfa  pop     rbp
0x18003ccfb  retn
0x18003ccfc  call    cs:__imp_GetCurrentThread
0x18003cd02  nop
0x18003cd03  mov     rcx, rax; ThreadHandle
0x18003cd06  mov     r9, rdi; TokenHandle
0x18003cd09  mov     edx, 8; DesiredAccess
0x18003cd0e  lea     r8d, [rdx-7]; OpenAsSelf
0x18003cd12  call    cs:__imp_OpenThreadToken
0x18003cd18  mov     edi, eax
0x18003cd1a  call    cs:__imp_GetLastError
0x18003cd20  mov     ebx, eax
0x18003cd22  test    eax, eax
0x18003cd24  jle     short loc_18003CD2F
0x18003cd26  movzx   ebx, ax
0x18003cd29  or      ebx, 80070000h
0x18003cd2f  call    cs:__imp_CoRevertToSelf
0x18003cd35  mov     [rbp+60h+var_88], eax
0x18003cd38  test    eax, eax
0x18003cd3a  js      short loc_18003CD9B
0x18003cd3c  test    edi, edi
0x18003cd3e  jnz     short loc_18003CD94
0x18003cd40  mov     [rsp+160h+var_140], r14
0x18003cd45  mov     [rsp+160h+var_138], r15
0x18003cd4a  mov     [rsp+160h+var_130], r12
0x18003cd4f  mov     [rsp+160h+var_128], 8Fh
0x18003cd57  mov     [rsp+160h+var_124], r13d
0x18003cd5c  mov     [rsp+160h+var_120], 0FFh
0x18003cd64  mov     [rbp+60h+var_A0], 1000000h
0x18003cd6b  xor     edx, edx; Val
0x18003cd6d  lea     r8d, [rdi+78h]; Size
0x18003cd71  lea     rcx, [rsp+160h+var_118]; void *
0x18003cd76  call    memset_0
0x18003cd7b  lea     r9, aOpenthreadtoke; "OpenThreadToken"
0x18003cd82  mov     r8d, ebx
0x18003cd85  lea     rdx, [rsp+160h+var_140]
0x18003cd8a  lea     rcx, [rbp+60h+var_90]
0x18003cd8e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003cd94  mov     dl, 1
0x18003cd96  jmp     loc_18003CCC9
0x18003cd9b  mov     [rsp+160h+var_140], r14
0x18003cda0  mov     [rsp+160h+var_138], r15
0x18003cda5  mov     [rsp+160h+var_130], r12
0x18003cdaa  mov     [rsp+160h+var_128], 8Ch
0x18003cdb2  mov     [rsp+160h+var_124], r13d
0x18003cdb7  mov     [rsp+160h+var_120], 0FFh
0x18003cdbf  mov     [rbp+60h+var_A0], 1000000h
0x18003cdc6  xor     edx, edx; Val
0x18003cdc8  lea     r8d, [rdx+78h]; Size
0x18003cdcc  lea     rcx, [rsp+160h+var_118]; void *
0x18003cdd1  call    memset_0
0x18003cdd6  lea     r8, aCoreverttoself_0; "CoRevertToSelf"
0x18003cddd  lea     rdx, [rsp+160h+var_140]
0x18003cde2  lea     rcx, [rbp+60h+var_90]
0x18003cde6  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
```
