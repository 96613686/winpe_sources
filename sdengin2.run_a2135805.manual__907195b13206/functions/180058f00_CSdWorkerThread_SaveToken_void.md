# CSdWorkerThread::_SaveToken(void)

- ea: `0x180058f00`
- end: `0x1800590cc`
- name: `?_SaveToken@CSdWorkerThread@@AEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(CSdWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800572c8`

## callees

- `0x180058f00`
- `0x180072e08`
- `0x180072f14`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180058f59`
- `KERNEL32!GetCurrentThread` at `0x180059029`
- `KERNEL32!GetCurrentThread` at `0x180058f59`
- `KERNEL32!GetCurrentThread` at `0x180059029`
- `KERNEL32!GetLastError` at `0x180058f9b`
- `KERNEL32!GetLastError` at `0x180059057`
- `KERNEL32!GetLastError` at `0x180058f9b`
- `KERNEL32!GetLastError` at `0x180059057`
- `KERNEL32!CloseHandle` at `0x180059015`
- `KERNEL32!CloseHandle` at `0x180059015`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058f77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059047`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180058f77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059047`
- `ole32!CoRevertToSelf` at `0x180059069`
- `ole32!CoRevertToSelf` at `0x180059069`
- `ole32!CoImpersonateClient` at `0x180058fd7`
- `ole32!CoImpersonateClient` at `0x180058fd7`

## string_xrefs

- `0x180058f21`: `CSdWorkerThread::_SaveToken`

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
0x180058f00  mov     [rsp-8+arg_0], rbx
0x180058f05  mov     [rsp-8+arg_8], rdi
0x180058f0a  push    rbp
0x180058f0b  mov     rbp, rsp
0x180058f0e  sub     rsp, 60h
0x180058f12  mov     rdi, rcx
0x180058f15  mov     r9d, 1; unsigned __int16
0x180058f1b  mov     r8d, 0F3h; unsigned __int16
0x180058f21  lea     rdx, aCsdworkerthrea_5; "CSdWorkerThread::_SaveToken"
0x180058f28  lea     rcx, [rbp+var_40]; this
0x180058f2c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180058f31  mov     eax, 0F7h
0x180058f36  cmp     qword ptr [rdi+20h], 0
0x180058f3b  jz      short loc_180058F4E
0x180058f3d  mov     ebx, 81000036h
0x180058f42  mov     [rbp+var_40], ebx
0x180058f45  mov     [rbp+var_3A], ax
0x180058f49  jmp     loc_1800590B0
0x180058f4e  mov     [rbp+var_40], 0
0x180058f55  mov     [rbp+var_3C], ax
0x180058f59  call    cs:__imp_GetCurrentThread
0x180058f60  nop     dword ptr [rax+rax+00h]
0x180058f65  lea     r9, [rdi+20h]; TokenHandle
0x180058f69  mov     edx, 2000Ch; DesiredAccess
0x180058f6e  mov     r8d, 1; OpenAsSelf
0x180058f74  mov     rcx, rax; ThreadHandle
0x180058f77  call    cs:__imp_OpenThreadToken
0x180058f7e  nop     dword ptr [rax+rax+00h]
0x180058f83  cmp     eax, 1
0x180058f86  jnz     short loc_180058F9B
0x180058f88  mov     eax, 0FCh
0x180058f8d  mov     [rbp+var_40], 0
0x180058f94  xor     ebx, ebx
0x180058f96  jmp     loc_1800590AC
0x180058f9b  call    cs:__imp_GetLastError
0x180058fa2  nop     dword ptr [rax+rax+00h]
0x180058fa7  mov     ebx, eax
0x180058fa9  cmp     eax, 3F0h
0x180058fae  jz      short loc_180058FC7
0x180058fb0  test    eax, eax
0x180058fb2  jle     short loc_180058FBD
0x180058fb4  movzx   ebx, ax
0x180058fb7  or      ebx, 80070000h
0x180058fbd  mov     eax, 100h
0x180058fc2  jmp     loc_180058F42
0x180058fc7  mov     [rbp+var_40], 0
0x180058fce  mov     eax, 100h
0x180058fd3  mov     [rbp+var_3C], ax
0x180058fd7  call    cs:__imp_CoImpersonateClient
0x180058fde  nop     dword ptr [rax+rax+00h]
0x180058fe3  mov     ebx, eax
0x180058fe5  mov     [rbp+var_40], eax
0x180058fe8  cmp     eax, 80010117h
0x180058fed  jnz     short loc_180058FF6
0x180058fef  mov     eax, 107h
0x180058ff4  jmp     short loc_180058F8D
0x180058ff6  test    eax, eax
0x180058ff8  mov     eax, 109h
0x180058ffd  js      loc_180058F45
0x180059003  mov     [rbp+var_3C], ax
0x180059007  mov     rcx, [rdi+20h]; hObject
0x18005900b  lea     rax, [rcx-1]
0x18005900f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180059013  ja      short loc_180059029
0x180059015  call    cs:__imp_CloseHandle
0x18005901c  nop     dword ptr [rax+rax+00h]
0x180059021  mov     qword ptr [rdi+20h], 0
0x180059029  call    cs:__imp_GetCurrentThread
0x180059030  nop     dword ptr [rax+rax+00h]
0x180059035  lea     r9, [rdi+20h]; TokenHandle
0x180059039  mov     edx, 2000Ch; DesiredAccess
0x18005903e  mov     r8d, 1; OpenAsSelf
0x180059044  mov     rcx, rax; ThreadHandle
0x180059047  call    cs:__imp_OpenThreadToken
0x18005904e  nop     dword ptr [rax+rax+00h]
0x180059053  test    eax, eax
0x180059055  jnz     short loc_180059067
0x180059057  call    cs:__imp_GetLastError
0x18005905e  nop     dword ptr [rax+rax+00h]
0x180059063  mov     edi, eax
0x180059065  jmp     short loc_180059069
0x180059067  xor     edi, edi
0x180059069  call    cs:__imp_CoRevertToSelf
0x180059070  nop     dword ptr [rax+rax+00h]
0x180059075  mov     ebx, eax
0x180059077  mov     [rbp+var_40], eax
0x18005907a  test    eax, eax
0x18005907c  mov     eax, 116h
0x180059081  js      loc_180058F45
0x180059087  mov     [rbp+var_3C], ax
0x18005908b  test    edi, edi
0x18005908d  jg      short loc_180059093
0x18005908f  mov     ebx, edi
0x180059091  jmp     short loc_18005909C
0x180059093  movzx   ebx, di
0x180059096  or      ebx, 80070000h
0x18005909c  mov     [rbp+var_40], ebx
0x18005909f  mov     eax, 117h
0x1800590a4  test    ebx, ebx
0x1800590a6  js      loc_180058F45
0x1800590ac  mov     [rbp+var_3C], ax
0x1800590b0  lea     rcx, [rbp+var_40]; this
0x1800590b4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800590b9  mov     eax, ebx
0x1800590bb  mov     rbx, [rsp+60h+arg_0]
0x1800590c0  mov     rdi, [rsp+60h+arg_8]
0x1800590c5  add     rsp, 60h
0x1800590c9  pop     rbp
0x1800590ca  retn
```
