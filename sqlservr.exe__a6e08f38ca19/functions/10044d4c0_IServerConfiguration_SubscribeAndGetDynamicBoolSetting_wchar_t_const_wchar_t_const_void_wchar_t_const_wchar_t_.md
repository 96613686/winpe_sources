# IServerConfiguration::SubscribeAndGetDynamicBoolSetting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,bool,void *),void *,wchar_t const *)

- ea: `0x10044d4c0`
- end: `0x10044d66e`
- name: `?SubscribeAndGetDynamicBoolSetting@IServerConfiguration@@QEAA_NPEB_W0P6AX00_NPEAX@Z20@Z`
- size: `430`
- prototype: `bool __fastcall(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, bool, void *), void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044d210`
- `0x10044d4c0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10044d64b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d64b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d51d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d5e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d51d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d5e0`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044d59d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044d59d`
- `sqldk!SystemThread_TlsOffset` at `0x10044d502`
- `sqldk!SystemThread_TlsOffset` at `0x10044d5c5`
- `sqldk!SystemThread_TlsIndex` at `0x10044d4f8`
- `sqldk!SystemThread_TlsIndex` at `0x10044d5bc`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d54f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10044d54f`

## string_xrefs

- `0x10044d53c`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IServerConfiguration::SubscribeAndGetDynamicBoolSetting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (*a4)(const wchar_t *, const wchar_t *, bool, void *),
        void *a5,
        const wchar_t *a6)
{
  __int64 v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rbx
  void *v13; // r15
  const wchar_t *v14; // r12
  __int64 v16; // rbx
  __int64 v17; // r9
  char v18; // bl
  wchar_t *String1; // [rsp+70h] [rbp+8h] BYREF

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
          490,
          6u);
  *v12 = a4;
  v13 = a5;
  v12[1] = a5;
  v14 = a6;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), _QWORD *, const wchar_t *, __int64))(**((_QWORD **)this + 3) + 8LL))(
         *((_QWORD *)this + 3),
         a2,
         a3,
         DynamicBoolSettingCallbackSubscriber,
         v12,
         a6,
         -2) )
  {
    String1 = 0;
    v16 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v17 = *(_QWORD *)(v16 + 256);
    if ( !v17 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v17 = *(_QWORD *)(v16 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, const wchar_t *))this
            + 3))(
           *((_QWORD *)this + 3),
           a2,
           a3,
           *(_QWORD *)(v17 + 1000),
           &String1,
           v14)
      && DynamicBoolSettingConverter(String1, (bool *)&a5) )
    {
      ((void (__fastcall *)(const wchar_t *, const wchar_t *, _QWORD, void *))a4)(a2, a3, (unsigned __int8)a5, v13);
      v18 = 1;
    }
    else
    {
      v18 = 0;
    }
    operator delete[](String1);
    return v18;
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
0x10044d4c0  push    rsi
0x10044d4c2  push    rdi
0x10044d4c3  push    r12
0x10044d4c5  push    r14
0x10044d4c7  push    r15
0x10044d4c9  sub     rsp, 40h
0x10044d4cd  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10044d4d6  mov     [rsp+68h+arg_8], rbx
0x10044d4db  mov     [rsp+68h+arg_10], rbp
0x10044d4e3  mov     rbp, r9
0x10044d4e6  mov     rdi, r8
0x10044d4e9  mov     rsi, rdx
0x10044d4ec  mov     r14, rcx
0x10044d4ef  mov     r11, gs:58h
0x10044d4f8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d4ff  mov     r10d, [rax]
0x10044d502  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d509  mov     ebx, [rax]
0x10044d50b  add     rbx, [r11+r10*8]
0x10044d50f  mov     rax, [rbx+100h]
0x10044d516  test    rax, rax
0x10044d519  jnz     short loc_10044D52A
0x10044d51b  xor     ecx, ecx
0x10044d51d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d523  mov     rax, [rbx+100h]
0x10044d52a  mov     rax, [rax+3E0h]
0x10044d531  mov     byte ptr [rsp+68h+var_48], 6
0x10044d536  mov     r9d, 1EAh
0x10044d53c  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10044d543  mov     rdx, [rax+140h]
0x10044d54a  mov     ecx, 10h
0x10044d54f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10044d555  mov     rbx, rax
0x10044d558  mov     [rax], rbp
0x10044d55b  mov     r15, [rsp+68h+arg_20]
0x10044d563  mov     [rax+8], r15
0x10044d567  mov     rcx, [r14+18h]
0x10044d56b  mov     r10, [rcx]
0x10044d56e  mov     r12, [rsp+68h+arg_28]
0x10044d576  mov     [rsp+68h+var_40], r12
0x10044d57b  mov     [rsp+68h+var_48], rax
0x10044d580  lea     r9, ?DynamicBoolSettingCallbackSubscriber@@YAXPEB_W00PEAX@Z; DynamicBoolSettingCallbackSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044d587  mov     r8, rdi
0x10044d58a  mov     rdx, rsi
0x10044d58d  call    qword ptr [r10+8]
0x10044d591  test    al, al
0x10044d593  jnz     short loc_10044D5AA
0x10044d595  mov     edx, 10h
0x10044d59a  mov     rcx, rbx
0x10044d59d  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044d5a3  xor     al, al
0x10044d5a5  jmp     loc_10044D654
0x10044d5aa  mov     [rsp+68h+String1], 0
0x10044d5b3  mov     rdx, gs:58h
0x10044d5bc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d5c3  mov     ecx, [rax]
0x10044d5c5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d5cc  mov     ebx, [rax]
0x10044d5ce  add     rbx, [rdx+rcx*8]
0x10044d5d2  mov     r9, [rbx+100h]
0x10044d5d9  test    r9, r9
0x10044d5dc  jnz     short loc_10044D5ED
0x10044d5de  xor     ecx, ecx
0x10044d5e0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d5e6  mov     r9, [rbx+100h]
0x10044d5ed  mov     rcx, [r14+18h]
0x10044d5f1  mov     rax, [rcx]
0x10044d5f4  mov     [rsp+68h+var_40], r12
0x10044d5f9  lea     rdx, [rsp+68h+String1]
0x10044d5fe  mov     [rsp+68h+var_48], rdx
0x10044d603  mov     r9, [r9+3E8h]
0x10044d60a  mov     r8, rdi
0x10044d60d  mov     rdx, rsi
0x10044d610  call    qword ptr [rax]
0x10044d612  test    al, al
0x10044d614  jz      short loc_10044D644
0x10044d616  lea     rdx, [rsp+68h+arg_20]; bool *
0x10044d61e  mov     rcx, [rsp+68h+String1]; String1
0x10044d623  call    ?DynamicBoolSettingConverter@@YA_NPEB_WPEA_N@Z; DynamicBoolSettingConverter(wchar_t const *,bool *)
0x10044d628  test    al, al
0x10044d62a  jz      short loc_10044D644
0x10044d62c  mov     r9, r15
0x10044d62f  movzx   r8d, byte ptr [rsp+68h+arg_20]
0x10044d638  mov     rdx, rdi
0x10044d63b  mov     rcx, rsi
0x10044d63e  call    rbp
0x10044d640  mov     bl, 1
0x10044d642  jmp     short loc_10044D646
0x10044d644  xor     bl, bl
0x10044d646  mov     rcx, [rsp+68h+String1]
0x10044d64b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044d651  movzx   eax, bl
0x10044d654  mov     rbx, [rsp+68h+arg_8]
0x10044d659  mov     rbp, [rsp+68h+arg_10]
0x10044d661  add     rsp, 40h
0x10044d665  pop     r15
0x10044d667  pop     r14
0x10044d669  pop     r12
0x10044d66b  pop     rdi
0x10044d66c  pop     rsi
0x10044d66d  retn
```
