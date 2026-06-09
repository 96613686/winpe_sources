# IServerConfiguration::SubscribeAndGetDynamicInt64Setting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,__int64,void *),void *,wchar_t const *)

- ea: `0x10044dd40`
- end: `0x10044df24`
- name: `?SubscribeAndGetDynamicInt64Setting@IServerConfiguration@@QEAA_NPEB_W0P6AX00_JPEAX@Z20@Z`
- size: `484`
- prototype: `bool __fastcall(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, __int64, void *), void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044dd40`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10044decd`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044decd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dd9d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de57`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dd9d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044de57`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044de18`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044de18`
- `sqldk!SystemThread_TlsOffset` at `0x10044dd82`
- `sqldk!SystemThread_TlsOffset` at `0x10044de3c`
- `sqldk!SystemThread_TlsIndex` at `0x10044dd78`
- `sqldk!SystemThread_TlsIndex` at `0x10044de33`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044ddcf`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044ddcf`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044def0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044df05`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044def0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10044df05`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044deb0`
- `api-ms-win-crt-string-l1-1-0!iswcntrl` at `0x10044deb0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044dea3`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x10044dea3`
- `api-ms-win-crt-convert-l1-1-0!_wtoi64` at `0x10044defc`
- `api-ms-win-crt-convert-l1-1-0!_wtoi64` at `0x10044defc`

## string_xrefs

- `0x10044ddbc`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IServerConfiguration::SubscribeAndGetDynamicInt64Setting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (__fastcall *a4)(const wchar_t *, const wchar_t *, __int64, void *),
        void *a5)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  void (__fastcall **v11)(const wchar_t *, const wchar_t *, __int64, void *); // rbx
  void *v12; // r15
  __int64 v14; // rbx
  __int64 v15; // r9
  wchar_t *v16; // rdi
  wchar_t v17; // ax
  wchar_t *v18; // rbx
  char v19; // bl
  __int64 v20; // rbx
  wchar_t *String; // [rsp+70h] [rbp+8h] BYREF

  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v11 = (void (__fastcall **)(const wchar_t *, const wchar_t *, __int64, void *))operator new(
                                                                                   0x10u,
                                                                                   *(struct IMemObj **)(*(_QWORD *)(v10 + 992) + 320LL),
                                                                                   "sql\\ntdbms\\common\\serverconfig.cpp",
                                                                                   849,
                                                                                   6u);
  *v11 = a4;
  v12 = a5;
  v11[1] = (void (__fastcall *)(const wchar_t *, const wchar_t *, __int64, void *))a5;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), void (__fastcall **)(const wchar_t *, const wchar_t *, __int64, void *), _QWORD, __int64))(**((_QWORD **)this + 3) + 8LL))(
         *((_QWORD *)this + 3),
         a2,
         a3,
         DynamicInt64SettingCallbackSubscriber,
         v11,
         0,
         -2) )
  {
    String = 0;
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    if ( !(***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, _QWORD))this
             + 3))(
            *((_QWORD *)this + 3),
            a2,
            a3,
            *(_QWORD *)(v15 + 1000),
            &String,
            0) )
      goto LABEL_13;
    v16 = String;
    v17 = *String;
    if ( !*String )
      goto LABEL_13;
    v18 = String;
    while ( iswspace(v17) || iswcntrl(*v18) )
    {
      v17 = *++v18;
      if ( !*v18 )
        goto LABEL_13;
    }
    *_errno() = 0;
    v20 = _wtoi64(v16);
    if ( !*_errno() )
    {
      a4(a2, a3, v20, v12);
      v19 = 1;
    }
    else
    {
LABEL_13:
      v19 = 0;
    }
    operator delete[](String);
    return v19;
  }
  else
  {
    operator delete(v11, 0x10u);
    return 0;
  }
}

```

## disassembly

```asm
0x10044dd40  push    rsi
0x10044dd42  push    rdi
0x10044dd43  push    r12
0x10044dd45  push    r14
0x10044dd47  push    r15
0x10044dd49  sub     rsp, 40h
0x10044dd4d  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10044dd56  mov     [rsp+68h+arg_8], rbx
0x10044dd5b  mov     [rsp+68h+arg_10], rbp
0x10044dd63  mov     r14, r9
0x10044dd66  mov     rsi, r8
0x10044dd69  mov     rbp, rdx
0x10044dd6c  mov     rdi, rcx
0x10044dd6f  mov     r11, gs:58h
0x10044dd78  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044dd7f  mov     r10d, [rax]
0x10044dd82  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044dd89  mov     ebx, [rax]
0x10044dd8b  add     rbx, [r11+r10*8]
0x10044dd8f  mov     rax, [rbx+100h]
0x10044dd96  test    rax, rax
0x10044dd99  jnz     short loc_10044DDAA
0x10044dd9b  xor     ecx, ecx
0x10044dd9d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044dda3  mov     rax, [rbx+100h]
0x10044ddaa  mov     rax, [rax+3E0h]
0x10044ddb1  mov     byte ptr [rsp+68h+var_48], 6
0x10044ddb6  mov     r9d, 351h
0x10044ddbc  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10044ddc3  mov     rdx, [rax+140h]
0x10044ddca  mov     ecx, 10h
0x10044ddcf  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10044ddd5  mov     rbx, rax
0x10044ddd8  mov     [rax], r14
0x10044dddb  mov     r15, [rsp+68h+arg_20]
0x10044dde3  mov     [rax+8], r15
0x10044dde7  mov     rcx, [rdi+18h]
0x10044ddeb  mov     r10, [rcx]
0x10044ddee  xor     r12d, r12d
0x10044ddf1  mov     [rsp+68h+var_40], r12
0x10044ddf6  mov     [rsp+68h+var_48], rax
0x10044ddfb  lea     r9, ?DynamicInt64SettingCallbackSubscriber@@YAXPEB_W00PEAX@Z; DynamicInt64SettingCallbackSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044de02  mov     r8, rsi
0x10044de05  mov     rdx, rbp
0x10044de08  call    qword ptr [r10+8]
0x10044de0c  test    al, al
0x10044de0e  jnz     short loc_10044DE25
0x10044de10  lea     edx, [r12+10h]
0x10044de15  mov     rcx, rbx
0x10044de18  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044de1e  xor     al, al
0x10044de20  jmp     loc_10044DED6
0x10044de25  mov     [rsp+68h+String], r12
0x10044de2a  mov     rdx, gs:58h
0x10044de33  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044de3a  mov     ecx, [rax]
0x10044de3c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044de43  mov     ebx, [rax]
0x10044de45  add     rbx, [rdx+rcx*8]
0x10044de49  mov     r9, [rbx+100h]
0x10044de50  test    r9, r9
0x10044de53  jnz     short loc_10044DE64
0x10044de55  xor     ecx, ecx
0x10044de57  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044de5d  mov     r9, [rbx+100h]
0x10044de64  mov     rcx, [rdi+18h]
0x10044de68  mov     rax, [rcx]
0x10044de6b  mov     [rsp+68h+var_40], r12
0x10044de70  lea     rdx, [rsp+68h+String]
0x10044de75  mov     [rsp+68h+var_48], rdx
0x10044de7a  mov     r9, [r9+3E8h]
0x10044de81  mov     r8, rsi
0x10044de84  mov     rdx, rbp
0x10044de87  call    qword ptr [rax]
0x10044de89  test    al, al
0x10044de8b  jz      short loc_10044DEC6
0x10044de8d  mov     rdi, [rsp+68h+String]
0x10044de92  movzx   eax, word ptr [rdi]
0x10044de95  test    ax, ax
0x10044de98  jz      short loc_10044DEC6
0x10044de9a  mov     rbx, rdi
0x10044de9d  nop     dword ptr [rax]
0x10044dea0  movzx   ecx, ax; C
0x10044dea3  call    cs:__imp_iswspace
0x10044dea9  test    eax, eax
0x10044deab  jnz     short loc_10044DEBA
0x10044dead  movzx   ecx, word ptr [rbx]; C
0x10044deb0  call    cs:__imp_iswcntrl
0x10044deb6  test    eax, eax
0x10044deb8  jz      short loc_10044DEF0
0x10044deba  add     rbx, 2
0x10044debe  movzx   eax, word ptr [rbx]
0x10044dec1  test    ax, ax
0x10044dec4  jnz     short loc_10044DEA0
0x10044dec6  xor     bl, bl
0x10044dec8  mov     rcx, [rsp+68h+String]
0x10044decd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044ded3  movzx   eax, bl
0x10044ded6  mov     rbx, [rsp+68h+arg_8]
0x10044dedb  mov     rbp, [rsp+68h+arg_10]
0x10044dee3  add     rsp, 40h
0x10044dee7  pop     r15
0x10044dee9  pop     r14
0x10044deeb  pop     r12
0x10044deed  pop     rdi
0x10044deee  pop     rsi
0x10044deef  retn
0x10044def0  call    cs:__imp__errno
0x10044def6  mov     [rax], r12d
0x10044def9  mov     rcx, rdi; String
0x10044defc  call    cs:__imp__wtoi64
0x10044df02  mov     rbx, rax
0x10044df05  call    cs:__imp__errno
0x10044df0b  cmp     dword ptr [rax], 0
0x10044df0e  jnz     short loc_10044DEC6
0x10044df10  mov     r9, r15
0x10044df13  mov     r8, rbx
0x10044df16  mov     rdx, rsi
0x10044df19  mov     rcx, rbp
0x10044df1c  call    r14
0x10044df1f  mov     bl, 1
0x10044df21  jmp     short loc_10044DEC8
```
