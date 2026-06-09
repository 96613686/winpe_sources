# CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension(IRemoteTerminal *,IUserName *,long * *,ulong *)

- ea: `0x1800660f4`
- end: `0x18006625a`
- name: `?EnumerateSessionsUsingProtocolExtension@CSessionArbitrationDesktop@@IEAAJPEAVIRemoteTerminal@@PEAUIUserName@@PEAPEAJPEAK@Z`
- size: `358`
- prototype: `__int64 __fastcall(CSessionArbitrationDesktop *__hidden this, struct IRemoteTerminal *, struct IUserName *, int **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800672c4`

## callees

- `0x18000a210`
- `0x180013d00`
- `0x1800660f4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006616e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006616e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800661e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800661e0`

## string_xrefs

- `0x18006618c`: `DuplicateTokenInPid failed: 0x%x in %s`
- `0x18006610a`: `CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension`

## pseudocode

```c
__int64 __fastcall CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension(
        CSessionArbitrationDesktop *this,
        struct IRemoteTerminal *a2,
        struct IUserName *a3,
        int **a4,
        unsigned int *a5)
{
  __int64 (__fastcall *v9)(struct IUserName *, _QWORD, HANDLE *); // rbx
  DWORD CurrentProcessId; // eax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int *v13; // rdi
  HANDLE v14; // rdx
  int *v15; // rax
  int v16; // eax
  unsigned int *v18; // [rsp+20h] [rbp-78h]
  HANDLE hObject; // [rsp+40h] [rbp-58h] BYREF
  const char *v20; // [rsp+48h] [rbp-50h] BYREF
  const char *v21; // [rsp+50h] [rbp-48h] BYREF
  int v22; // [rsp+B0h] [rbp+18h] BYREF

  hObject = 0;
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v22 = *((_DWORD *)this + 416);
    v21 = "Status";
    v20 = "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)word_180109F22,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v22);
  }
  v9 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, HANDLE *))(*(_QWORD *)a3 + 80LL);
  CurrentProcessId = GetCurrentProcessId();
  v11 = v9(a3, CurrentProcessId, &hObject);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = a5;
    v14 = hObject;
    v18 = a5;
    *a5 = 0;
    v12 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, HANDLE, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)a2 + 384LL))(
            a2,
            v14,
            *((unsigned int *)this + 415),
            0,
            v18);
    if ( v12 == -2147024774 && *v13 )
    {
      v15 = (int *)CoTaskMemAlloc(4LL * *v13);
      *a4 = v15;
      if ( v15 )
      {
        v16 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, HANDLE, _QWORD, int *, unsigned int *))(*(_QWORD *)a2 + 384LL))(
                a2,
                hObject,
                *((unsigned int *)this + 415),
                v15,
                v13);
        v12 = v16;
        if ( v16 < 0 )
          _DbgPrintMessage(
            8,
            "SessionArbitrationEnumeration failed: 0x%x in %s",
            (unsigned int)v16,
            "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension");
      }
      else
      {
        v12 = -2147024882;
        *v13 = 0;
      }
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "DuplicateTokenInPid failed: 0x%x in %s",
      (unsigned int)v11,
      "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension");
  }
  if ( hObject )
    CloseHandle(hObject);
  return v12;
}

```

## disassembly

```asm
0x1800660f4  mov     r11, rsp
0x1800660f7  push    rbx
0x1800660f8  push    rsi
0x1800660f9  push    rdi
0x1800660fa  push    r12
0x1800660fc  push    r14
0x1800660fe  push    r15
0x180066100  sub     rsp, 68h
0x180066104  mov     eax, cs:dword_180128170
0x18006610a  lea     r12, aCsessionarbitr; "CSessionArbitrationDesktop::EnumerateSe"...
0x180066111  mov     qword ptr [r11-58h], 0
0x180066119  mov     r15, r9
0x18006611c  mov     rdi, r8
0x18006611f  mov     r14, rdx
0x180066122  mov     rsi, rcx
0x180066125  cmp     eax, 4
0x180066128  jbe     short loc_180066167
0x18006612a  mov     eax, [rcx+680h]
0x180066130  lea     rdx, word_180109F22
0x180066137  mov     [r11+18h], eax
0x18006613b  lea     rax, aStatus; "Status"
0x180066142  mov     [r11-48h], rax
0x180066146  lea     rax, [r11+18h]
0x18006614a  mov     [r11-68h], rax
0x18006614e  lea     rax, [r11-50h]
0x180066152  mov     [r11-70h], rax
0x180066156  lea     rax, [r11-48h]
0x18006615a  mov     [r11-78h], rax
0x18006615e  mov     [r11-50h], r12
0x180066162  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180066167  mov     rax, [rdi]
0x18006616a  mov     rbx, [rax+50h]
0x18006616e  call    cs:__imp_GetCurrentProcessId
0x180066174  lea     r8, [rsp+98h+hObject]
0x180066179  mov     rcx, rdi
0x18006617c  mov     edx, eax
0x18006617e  mov     rax, rbx
0x180066181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066186  mov     ebx, eax
0x180066188  test    eax, eax
0x18006618a  jns     short loc_180066198
0x18006618c  lea     rdx, aDuplicatetoken; "DuplicateTokenInPid failed: 0x%x in %s"
0x180066193  jmp     loc_18006622A
0x180066198  mov     rdi, [rsp+98h+arg_20]
0x1800661a0  xor     r9d, r9d
0x1800661a3  mov     rdx, [rsp+98h+hObject]
0x1800661a8  mov     rcx, r14
0x1800661ab  mov     [rsp+98h+var_78], rdi
0x1800661b0  mov     dword ptr [rdi], 0
0x1800661b6  mov     rax, [r14]
0x1800661b9  mov     r8d, [rsi+67Ch]
0x1800661c0  mov     rax, [rax+180h]
0x1800661c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661cc  mov     ebx, eax
0x1800661ce  cmp     eax, 8007007Ah
0x1800661d3  jnz     short loc_18006623A
0x1800661d5  cmp     dword ptr [rdi], 0
0x1800661d8  jz      short loc_18006623A
0x1800661da  mov     ecx, [rdi]
0x1800661dc  shl     rcx, 2; cb
0x1800661e0  call    cs:__imp_CoTaskMemAlloc
0x1800661e6  mov     [r15], rax
0x1800661e9  mov     r9, rax
0x1800661ec  test    rax, rax
0x1800661ef  jnz     short loc_1800661FA
0x1800661f1  mov     ebx, 8007000Eh
0x1800661f6  mov     [rdi], eax
0x1800661f8  jmp     short loc_18006623A
0x1800661fa  mov     rax, [r14]
0x1800661fd  mov     rcx, r14
0x180066200  mov     r8d, [rsi+67Ch]
0x180066207  mov     rdx, [rsp+98h+hObject]
0x18006620c  mov     [rsp+98h+var_78], rdi
0x180066211  mov     rax, [rax+180h]
0x180066218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006621d  mov     ebx, eax
0x18006621f  test    eax, eax
0x180066221  jns     short loc_18006623A
0x180066223  lea     rdx, aSessionarbitra_0; "SessionArbitrationEnumeration failed: 0"...
0x18006622a  mov     r9, r12
0x18006622d  mov     r8d, eax
0x180066230  mov     ecx, 8; int
0x180066235  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006623a  mov     rcx, [rsp+98h+hObject]; hObject
0x18006623f  test    rcx, rcx
0x180066242  jz      short loc_18006624A
0x180066244  call    cs:__imp_CloseHandle
0x18006624a  mov     eax, ebx
0x18006624c  add     rsp, 68h
0x180066250  pop     r15
0x180066252  pop     r14
0x180066254  pop     r12
0x180066256  pop     rdi
0x180066257  pop     rsi
0x180066258  pop     rbx
0x180066259  retn
```
