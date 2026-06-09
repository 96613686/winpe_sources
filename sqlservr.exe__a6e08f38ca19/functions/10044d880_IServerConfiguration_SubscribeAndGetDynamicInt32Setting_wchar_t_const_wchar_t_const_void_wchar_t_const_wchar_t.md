# IServerConfiguration::SubscribeAndGetDynamicInt32Setting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,int,void *),void *,wchar_t const *)

- ea: `0x10044d880`
- end: `0x10044da6c`
- name: `?SubscribeAndGetDynamicInt32Setting@IServerConfiguration@@QEAA_NPEB_W0P6AX00HPEAX@Z10@Z`
- size: `492`
- prototype: `bool __fastcall(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, int, void *), void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044d880`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10044da13`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044da13`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d8dd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d9a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d8dd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d9a0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044d95d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044d95d`
- `sqldk!SystemThread_TlsOffset` at `0x10044d8c2`
- `sqldk!SystemThread_TlsOffset` at `0x10044d985`
- `sqldk!SystemThread_TlsIndex` at `0x10044d8b8`
- `sqldk!SystemThread_TlsIndex` at `0x10044d97c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d90f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d90f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044da36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044da4d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044da36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044da4d`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044d9f6`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044d9f6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044d9e9`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044d9e9`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10044da45`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10044da45`

## string_xrefs

- `0x10044d8fc`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IServerConfiguration::SubscribeAndGetDynamicInt32Setting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (*a4)(const wchar_t *, const wchar_t *, int, void *),
        void *a5,
        const wchar_t *a6)
{
  __int64 v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rbx
  void *v13; // r12
  const wchar_t *v14; // r14
  __int64 v16; // rbx
  __int64 v17; // r9
  wchar_t *v18; // rdi
  wchar_t v19; // ax
  wchar_t *v20; // rbx
  char v21; // bl
  unsigned int v22; // ebx
  wchar_t *String; // [rsp+70h] [rbp+8h] BYREF

  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = operator new(
          0x10u,
          *(struct IMemObj **)(*(_QWORD *)(v11 + 992) + 320LL),
          "sql\\ntdbms\\common\\serverconfig.cpp",
          683,
          6u);
  *v12 = a4;
  v13 = a5;
  v12[1] = a5;
  v14 = a6;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), _QWORD *, const wchar_t *, __int64))(**((_QWORD **)this + 3) + 8LL))(
         *((_QWORD *)this + 3),
         a2,
         a3,
         DynamicInt32SettingCallbackSubscriber,
         v12,
         a6,
         -2) )
  {
    String = 0;
    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v17 = *(_QWORD *)(v16 + 256);
    if ( !v17 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v17 = *(_QWORD *)(v16 + 256);
    }
    if ( !(***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, const wchar_t *))this
             + 3))(
            *((_QWORD *)this + 3),
            a2,
            a3,
            *(_QWORD *)(v17 + 1000),
            &String,
            v14) )
      goto LABEL_13;
    v18 = String;
    v19 = *String;
    if ( !*String )
      goto LABEL_13;
    v20 = String;
    while ( iswspace(v19) || iswcntrl(*v20) )
    {
      v19 = *++v20;
      if ( !*v20 )
        goto LABEL_13;
    }
    *_errno() = 0;
    v22 = _wtoi(v18);
    if ( !*_errno() )
    {
      ((void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD, void *))a4)(a2, a3, v22, v13);
      v21 = 1;
    }
    else
    {
LABEL_13:
      v21 = 0;
    }
    operator delete[](String);
    return v21;
  }
  else
  {
    operator delete(v12, 0x10u);
    return 0;
  }
}

```

## disassembly

```asm
0x10044d880  push    rsi
0x10044d882  push    rdi
0x10044d883  push    r12
0x10044d885  push    r14
0x10044d887  push    r15
0x10044d889  sub     rsp, 40h
0x10044d88d  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10044d896  mov     [rsp+68h+arg_8], rbx
0x10044d89b  mov     [rsp+68h+arg_10], rbp
0x10044d8a3  mov     r15, r9
0x10044d8a6  mov     rsi, r8
0x10044d8a9  mov     rbp, rdx
0x10044d8ac  mov     rdi, rcx
0x10044d8af  mov     r11, gs:58h
0x10044d8b8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d8bf  mov     r10d, [rax]
0x10044d8c2  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d8c9  mov     ebx, [rax]
0x10044d8cb  add     rbx, [r11+r10*8]
0x10044d8cf  mov     rax, [rbx+100h]
0x10044d8d6  test    rax, rax
0x10044d8d9  jnz     short loc_10044D8EA
0x10044d8db  xor     ecx, ecx
0x10044d8dd  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d8e3  mov     rax, [rbx+100h]
0x10044d8ea  mov     rax, [rax+3E0h]
0x10044d8f1  mov     byte ptr [rsp+68h+var_48], 6
0x10044d8f6  mov     r9d, 2ABh
0x10044d8fc  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10044d903  mov     rdx, [rax+140h]
0x10044d90a  mov     ecx, 10h
0x10044d90f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10044d915  mov     rbx, rax
0x10044d918  mov     [rax], r15
0x10044d91b  mov     r12, [rsp+68h+arg_20]
0x10044d923  mov     [rax+8], r12
0x10044d927  mov     rcx, [rdi+18h]
0x10044d92b  mov     r10, [rcx]
0x10044d92e  mov     r14, [rsp+68h+arg_28]
0x10044d936  mov     [rsp+68h+var_40], r14
0x10044d93b  mov     [rsp+68h+var_48], rax
0x10044d940  lea     r9, ?DynamicInt32SettingCallbackSubscriber@@YAXPEB_W00PEAX@Z; DynamicInt32SettingCallbackSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044d947  mov     r8, rsi
0x10044d94a  mov     rdx, rbp
0x10044d94d  call    qword ptr [r10+8]
0x10044d951  test    al, al
0x10044d953  jnz     short loc_10044D96A
0x10044d955  mov     edx, 10h
0x10044d95a  mov     rcx, rbx
0x10044d95d  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044d963  xor     al, al
0x10044d965  jmp     loc_10044DA1C
0x10044d96a  mov     [rsp+68h+String], 0
0x10044d973  mov     rdx, gs:58h
0x10044d97c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d983  mov     ecx, [rax]
0x10044d985  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d98c  mov     ebx, [rax]
0x10044d98e  add     rbx, [rdx+rcx*8]
0x10044d992  mov     r9, [rbx+100h]
0x10044d999  test    r9, r9
0x10044d99c  jnz     short loc_10044D9AD
0x10044d99e  xor     ecx, ecx
0x10044d9a0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d9a6  mov     r9, [rbx+100h]
0x10044d9ad  mov     rcx, [rdi+18h]
0x10044d9b1  mov     rax, [rcx]
0x10044d9b4  mov     [rsp+68h+var_40], r14
0x10044d9b9  lea     rdx, [rsp+68h+String]
0x10044d9be  mov     [rsp+68h+var_48], rdx
0x10044d9c3  mov     r9, [r9+3E8h]
0x10044d9ca  mov     r8, rsi
0x10044d9cd  mov     rdx, rbp
0x10044d9d0  call    qword ptr [rax]
0x10044d9d2  test    al, al
0x10044d9d4  jz      short loc_10044DA0C
0x10044d9d6  mov     rdi, [rsp+68h+String]
0x10044d9db  movzx   eax, word ptr [rdi]
0x10044d9de  test    ax, ax
0x10044d9e1  jz      short loc_10044DA0C
0x10044d9e3  mov     rbx, rdi
0x10044d9e6  movzx   ecx, ax; C
0x10044d9e9  call    cs:__imp_iswspace
0x10044d9ef  test    eax, eax
0x10044d9f1  jnz     short loc_10044DA00
0x10044d9f3  movzx   ecx, word ptr [rbx]; C
0x10044d9f6  call    cs:__imp_iswcntrl
0x10044d9fc  test    eax, eax
0x10044d9fe  jz      short loc_10044DA36
0x10044da00  add     rbx, 2
0x10044da04  movzx   eax, word ptr [rbx]
0x10044da07  test    ax, ax
0x10044da0a  jnz     short loc_10044D9E6
0x10044da0c  xor     bl, bl
0x10044da0e  mov     rcx, [rsp+68h+String]
0x10044da13  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044da19  movzx   eax, bl
0x10044da1c  mov     rbx, [rsp+68h+arg_8]
0x10044da21  mov     rbp, [rsp+68h+arg_10]
0x10044da29  add     rsp, 40h
0x10044da2d  pop     r15
0x10044da2f  pop     r14
0x10044da31  pop     r12
0x10044da33  pop     rdi
0x10044da34  pop     rsi
0x10044da35  retn
0x10044da36  call    cs:__imp__errno
0x10044da3c  mov     dword ptr [rax], 0
0x10044da42  mov     rcx, rdi; String
0x10044da45  call    cs:__imp__wtoi
0x10044da4b  mov     ebx, eax
0x10044da4d  call    cs:__imp__errno
0x10044da53  cmp     dword ptr [rax], 0
0x10044da56  jnz     short loc_10044DA0C
0x10044da58  mov     r9, r12
0x10044da5b  mov     r8d, ebx
0x10044da5e  mov     rdx, rsi
0x10044da61  mov     rcx, rbp
0x10044da64  call    r15
0x10044da67  mov     bl, 1
0x10044da69  jmp     short loc_10044DA0E
```
