# CSdWorkerThread::_SaveToken(void)

- ea: `0x180056acc`
- end: `0x180056c5e`
- name: `?_SaveToken@CSdWorkerThread@@AEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(CSdWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180054fc8`

## callees

- `0x180056acc`
- `0x18006fe84`
- `0x18006ff8c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180056b25`
- `KERNEL32!GetCurrentThread` at `0x180056bd4`
- `KERNEL32!GetCurrentThread` at `0x180056b25`
- `KERNEL32!GetCurrentThread` at `0x180056bd4`
- `KERNEL32!GetLastError` at `0x180056b5b`
- `KERNEL32!GetLastError` at `0x180056bf6`
- `KERNEL32!GetLastError` at `0x180056b5b`
- `KERNEL32!GetLastError` at `0x180056bf6`
- `KERNEL32!CloseHandle` at `0x180056bc6`
- `KERNEL32!CloseHandle` at `0x180056bc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056b3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056bec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056b3d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056bec`
- `ole32!CoRevertToSelf` at `0x180056c02`
- `ole32!CoRevertToSelf` at `0x180056c02`
- `ole32!CoImpersonateClient` at `0x180056b8e`
- `ole32!CoImpersonateClient` at `0x180056b8e`

## string_xrefs

- `0x180056aed`: `CSdWorkerThread::_SaveToken`

## pseudocode

```c
__int64 __fastcall CSdWorkerThread::_SaveToken(CSdWorkerThread *this)
{
  __int16 v2; // ax
  signed int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HRESULT v6; // eax
  bool v7; // sf
  char *v8; // rcx
  HANDLE v9; // rax
  signed int v10; // edi
  HRESULT v12; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSdWorkerThread::_SaveToken", 0xF3u, 1u);
  v2 = 247;
  if ( !*((_QWORD *)this + 4) )
  {
    v12 = 0;
    v13 = 247;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, (PHANDLE)this + 4) )
    {
      v2 = 252;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError != 1008 )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v2 = 256;
        goto LABEL_3;
      }
      v12 = 0;
      v13 = 256;
      v6 = CoImpersonateClient();
      v3 = v6;
      v12 = v6;
      if ( v6 != -2147417833 )
      {
        v7 = v6 < 0;
        v2 = 265;
        if ( v7 )
          goto LABEL_4;
        v13 = 265;
        v8 = (char *)*((_QWORD *)this + 4);
        if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(v8);
          *((_QWORD *)this + 4) = 0;
        }
        v9 = GetCurrentThread();
        v10 = OpenThreadToken(v9, 0x2000Cu, 1, (PHANDLE)this + 4) ? 0 : GetLastError();
        v3 = CoRevertToSelf();
        v12 = v3;
        v2 = 278;
        if ( v3 < 0 )
          goto LABEL_4;
        v13 = 278;
        v3 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
        v12 = v3;
        v2 = 279;
        if ( v3 < 0 )
          goto LABEL_4;
LABEL_25:
        v13 = v2;
        goto LABEL_26;
      }
      v2 = 263;
    }
    v12 = 0;
    v3 = 0;
    goto LABEL_25;
  }
  v3 = -2130706378;
LABEL_3:
  v12 = v3;
LABEL_4:
  v14 = v2;
LABEL_26:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180056acc  mov     [rsp-8+arg_0], rbx
0x180056ad1  mov     [rsp-8+arg_8], rdi
0x180056ad6  push    rbp
0x180056ad7  mov     rbp, rsp
0x180056ada  sub     rsp, 60h
0x180056ade  mov     rdi, rcx
0x180056ae1  mov     r9d, 1; unsigned __int16
0x180056ae7  mov     r8d, 0F3h; unsigned __int16
0x180056aed  lea     rdx, aCsdworkerthrea_5; "CSdWorkerThread::_SaveToken"
0x180056af4  lea     rcx, [rbp+var_40]; this
0x180056af8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180056afd  mov     eax, 0F7h
0x180056b02  cmp     qword ptr [rdi+20h], 0
0x180056b07  jz      short loc_180056B1A
0x180056b09  mov     ebx, 81000036h
0x180056b0e  mov     [rbp+var_40], ebx
0x180056b11  mov     [rbp+var_3A], ax
0x180056b15  jmp     loc_180056C43
0x180056b1a  mov     [rbp+var_40], 0
0x180056b21  mov     [rbp+var_3C], ax
0x180056b25  call    cs:__imp_GetCurrentThread
0x180056b2b  lea     r9, [rdi+20h]; TokenHandle
0x180056b2f  mov     edx, 2000Ch; DesiredAccess
0x180056b34  mov     r8d, 1; OpenAsSelf
0x180056b3a  mov     rcx, rax; ThreadHandle
0x180056b3d  call    cs:__imp_OpenThreadToken
0x180056b43  cmp     eax, 1
0x180056b46  jnz     short loc_180056B5B
0x180056b48  mov     eax, 0FCh
0x180056b4d  mov     [rbp+var_40], 0
0x180056b54  xor     ebx, ebx
0x180056b56  jmp     loc_180056C3F
0x180056b5b  call    cs:__imp_GetLastError
0x180056b61  mov     ebx, eax
0x180056b63  cmp     eax, 3F0h
0x180056b68  jz      short loc_180056B7E
0x180056b6a  test    eax, eax
0x180056b6c  jle     short loc_180056B77
0x180056b6e  movzx   ebx, ax
0x180056b71  or      ebx, 80070000h
0x180056b77  mov     eax, 100h
0x180056b7c  jmp     short loc_180056B0E
0x180056b7e  mov     [rbp+var_40], 0
0x180056b85  mov     eax, 100h
0x180056b8a  mov     [rbp+var_3C], ax
0x180056b8e  call    cs:__imp_CoImpersonateClient
0x180056b94  mov     ebx, eax
0x180056b96  mov     [rbp+var_40], eax
0x180056b99  cmp     eax, 80010117h
0x180056b9e  jnz     short loc_180056BA7
0x180056ba0  mov     eax, 107h
0x180056ba5  jmp     short loc_180056B4D
0x180056ba7  test    eax, eax
0x180056ba9  mov     eax, 109h
0x180056bae  js      loc_180056B11
0x180056bb4  mov     [rbp+var_3C], ax
0x180056bb8  mov     rcx, [rdi+20h]; hObject
0x180056bbc  lea     rax, [rcx-1]
0x180056bc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180056bc4  ja      short loc_180056BD4
0x180056bc6  call    cs:__imp_CloseHandle
0x180056bcc  mov     qword ptr [rdi+20h], 0
0x180056bd4  call    cs:__imp_GetCurrentThread
0x180056bda  lea     r9, [rdi+20h]; TokenHandle
0x180056bde  mov     edx, 2000Ch; DesiredAccess
0x180056be3  mov     r8d, 1; OpenAsSelf
0x180056be9  mov     rcx, rax; ThreadHandle
0x180056bec  call    cs:__imp_OpenThreadToken
0x180056bf2  test    eax, eax
0x180056bf4  jnz     short loc_180056C00
0x180056bf6  call    cs:__imp_GetLastError
0x180056bfc  mov     edi, eax
0x180056bfe  jmp     short loc_180056C02
0x180056c00  xor     edi, edi
0x180056c02  call    cs:__imp_CoRevertToSelf
0x180056c08  mov     ebx, eax
0x180056c0a  mov     [rbp+var_40], eax
0x180056c0d  test    eax, eax
0x180056c0f  mov     eax, 116h
0x180056c14  js      loc_180056B11
0x180056c1a  mov     [rbp+var_3C], ax
0x180056c1e  test    edi, edi
0x180056c20  jg      short loc_180056C26
0x180056c22  mov     ebx, edi
0x180056c24  jmp     short loc_180056C2F
0x180056c26  movzx   ebx, di
0x180056c29  or      ebx, 80070000h
0x180056c2f  mov     [rbp+var_40], ebx
0x180056c32  mov     eax, 117h
0x180056c37  test    ebx, ebx
0x180056c39  js      loc_180056B11
0x180056c3f  mov     [rbp+var_3C], ax
0x180056c43  lea     rcx, [rbp+var_40]; this
0x180056c47  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180056c4c  mov     eax, ebx
0x180056c4e  mov     rbx, [rsp+60h+arg_0]
0x180056c53  mov     rdi, [rsp+60h+arg_8]
0x180056c58  add     rsp, 60h
0x180056c5c  pop     rbp
0x180056c5d  retn
```
