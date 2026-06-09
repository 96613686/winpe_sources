# IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,double,void *),void *,wchar_t const *)

- ea: `0x10044e200`
- end: `0x10044e3fe`
- name: `?SubscribeAndGetDynamicDoubleSetting@IServerConfiguration@@QEAA_NPEB_W0P6AX00NPEAX@Z10@Z`
- size: `510`
- prototype: `bool __fastcall(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, double, void *), void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044e200`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10044e3a0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e3a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e25d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e323`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e25d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e323`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044e2dd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044e2dd`
- `sqldk!SystemThread_TlsOffset` at `0x10044e242`
- `sqldk!SystemThread_TlsOffset` at `0x10044e308`
- `sqldk!SystemThread_TlsIndex` at `0x10044e238`
- `sqldk!SystemThread_TlsIndex` at `0x10044e2ff`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044e28f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044e28f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044e3c7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044e3df`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044e3c7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044e3df`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044e380`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044e380`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044e373`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044e373`
- `api-ms-win-crt-convert-l1-1-0!_wtof` at `0x10044e3d6`
- `api-ms-win-crt-convert-l1-1-0!_wtof` at `0x10044e3d6`

## string_xrefs

- `0x10044e27c`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IServerConfiguration::SubscribeAndGetDynamicDoubleSetting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (__fastcall *a4)(const wchar_t *, const wchar_t *, __int64, void *),
        void *a5,
        const wchar_t *a6)
{
  __int64 v10; // rbx
  __int64 v11; // rax
  void (__fastcall **v12)(const wchar_t *, const wchar_t *, __int64, void *); // rbx
  void *v13; // r12
  const wchar_t *v14; // r14
  __int64 v16; // rbx
  __int64 v17; // r9
  wchar_t *v18; // rdi
  wchar_t v19; // ax
  wchar_t *v20; // rbx
  char v21; // bl
  __int64 v22; // r8
  wchar_t *String; // [rsp+80h] [rbp+8h] BYREF

  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = (void (__fastcall **)(const wchar_t *, const wchar_t *, __int64, void *))operator new(
                                                                                   0x10u,
                                                                                   *(struct IMemObj **)(*(_QWORD *)(v11 + 992) + 320LL),
                                                                                   "sql\\ntdbms\\common\\serverconfig.cpp",
                                                                                   1017,
                                                                                   6u);
  *v12 = a4;
  v13 = a5;
  v12[1] = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64, void *))a5;
  v14 = a6;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), void (__fastcall **)(const wchar_t *, const wchar_t *, __int64, void *), const wchar_t *, __int64))(**((_QWORD **)this + 3) + 8LL))(
         *((_QWORD *)this + 3),
         a2,
         a3,
         DynamicDoubleSettingCallbackSubscriber,
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
    _wtof(v18);
    if ( !*_errno() )
    {
      a4(a2, a3, v22, v13);
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
0x10044e200  mov     rax, rsp
0x10044e203  push    rsi
0x10044e204  push    rdi
0x10044e205  push    r12
0x10044e207  push    r14
0x10044e209  push    r15
0x10044e20b  sub     rsp, 50h
0x10044e20f  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10044e217  mov     [rax+10h], rbx
0x10044e21b  mov     [rax+18h], rbp
0x10044e21f  movaps  xmmword ptr [rax-38h], xmm6
0x10044e223  mov     r15, r9
0x10044e226  mov     rsi, r8
0x10044e229  mov     rbp, rdx
0x10044e22c  mov     rdi, rcx
0x10044e22f  mov     r11, gs:58h
0x10044e238  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044e23f  mov     r10d, [rax]
0x10044e242  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044e249  mov     ebx, [rax]
0x10044e24b  add     rbx, [r11+r10*8]
0x10044e24f  mov     rax, [rbx+100h]
0x10044e256  test    rax, rax
0x10044e259  jnz     short loc_10044E26A
0x10044e25b  xor     ecx, ecx
0x10044e25d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044e263  mov     rax, [rbx+100h]
0x10044e26a  mov     rax, [rax+3E0h]
0x10044e271  mov     byte ptr [rsp+78h+var_58], 6
0x10044e276  mov     r9d, 3F9h
0x10044e27c  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10044e283  mov     rdx, [rax+140h]
0x10044e28a  mov     ecx, 10h
0x10044e28f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10044e295  mov     rbx, rax
0x10044e298  mov     [rax], r15
0x10044e29b  mov     r12, [rsp+78h+arg_20]
0x10044e2a3  mov     [rax+8], r12
0x10044e2a7  mov     rcx, [rdi+18h]
0x10044e2ab  mov     r10, [rcx]
0x10044e2ae  mov     r14, [rsp+78h+arg_28]
0x10044e2b6  mov     [rsp+78h+var_50], r14
0x10044e2bb  mov     [rsp+78h+var_58], rax
0x10044e2c0  lea     r9, ?DynamicDoubleSettingCallbackSubscriber@@YAXPEB_W00PEAX@Z; DynamicDoubleSettingCallbackSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044e2c7  mov     r8, rsi
0x10044e2ca  mov     rdx, rbp
0x10044e2cd  call    qword ptr [r10+8]
0x10044e2d1  test    al, al
0x10044e2d3  jnz     short loc_10044E2EA
0x10044e2d5  mov     edx, 10h
0x10044e2da  mov     rcx, rbx
0x10044e2dd  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044e2e3  xor     al, al
0x10044e2e5  jmp     loc_10044E3A9
0x10044e2ea  mov     [rsp+78h+String], 0
0x10044e2f6  mov     rdx, gs:58h
0x10044e2ff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044e306  mov     ecx, [rax]
0x10044e308  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044e30f  mov     ebx, [rax]
0x10044e311  add     rbx, [rdx+rcx*8]
0x10044e315  mov     r9, [rbx+100h]
0x10044e31c  test    r9, r9
0x10044e31f  jnz     short loc_10044E330
0x10044e321  xor     ecx, ecx
0x10044e323  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044e329  mov     r9, [rbx+100h]
0x10044e330  mov     rcx, [rdi+18h]
0x10044e334  mov     rax, [rcx]
0x10044e337  mov     [rsp+78h+var_50], r14
0x10044e33c  lea     rdx, [rsp+78h+String]
0x10044e344  mov     [rsp+78h+var_58], rdx
0x10044e349  mov     r9, [r9+3E8h]
0x10044e350  mov     r8, rsi
0x10044e353  mov     rdx, rbp
0x10044e356  call    qword ptr [rax]
0x10044e358  test    al, al
0x10044e35a  jz      short loc_10044E396
0x10044e35c  mov     rdi, [rsp+78h+String]
0x10044e364  movzx   eax, word ptr [rdi]
0x10044e367  test    ax, ax
0x10044e36a  jz      short loc_10044E396
0x10044e36c  mov     rbx, rdi
0x10044e36f  nop
0x10044e370  movzx   ecx, ax; C
0x10044e373  call    cs:__imp_iswspace
0x10044e379  test    eax, eax
0x10044e37b  jnz     short loc_10044E38A
0x10044e37d  movzx   ecx, word ptr [rbx]; C
0x10044e380  call    cs:__imp_iswcntrl
0x10044e386  test    eax, eax
0x10044e388  jz      short loc_10044E3C7
0x10044e38a  add     rbx, 2
0x10044e38e  movzx   eax, word ptr [rbx]
0x10044e391  test    ax, ax
0x10044e394  jnz     short loc_10044E370
0x10044e396  xor     bl, bl
0x10044e398  mov     rcx, [rsp+78h+String]
0x10044e3a0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044e3a6  movzx   eax, bl
0x10044e3a9  lea     r11, [rsp+78h+var_28]
0x10044e3ae  mov     rbx, [r11+38h]
0x10044e3b2  mov     rbp, [r11+40h]
0x10044e3b6  movaps  xmm6, [rsp+78h+var_38]
0x10044e3bb  mov     rsp, r11
0x10044e3be  pop     r15
0x10044e3c0  pop     r14
0x10044e3c2  pop     r12
0x10044e3c4  pop     rdi
0x10044e3c5  pop     rsi
0x10044e3c6  retn
0x10044e3c7  call    cs:__imp__errno
0x10044e3cd  mov     dword ptr [rax], 0
0x10044e3d3  mov     rcx, rdi; String
0x10044e3d6  call    cs:__imp__wtof
0x10044e3dc  movaps  xmm6, xmm0
0x10044e3df  call    cs:__imp__errno
0x10044e3e5  cmp     dword ptr [rax], 0
0x10044e3e8  jnz     short loc_10044E396
0x10044e3ea  mov     r9, r12
0x10044e3ed  movaps  xmm2, xmm6
0x10044e3f0  mov     rdx, rsi
0x10044e3f3  mov     rcx, rbp
0x10044e3f6  call    r15
0x10044e3f9  mov     bl, 1
0x10044e3fb  jmp     short loc_10044E398
```
