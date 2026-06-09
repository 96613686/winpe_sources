# IServerConfiguration::GetDynamicInt32Setting(wchar_t const *,wchar_t const *,int *,bool,wchar_t const *)

- ea: `0x100401d50`
- end: `0x100401e20`
- name: `?GetDynamicInt32Setting@IServerConfiguration@@UEAA_NPEB_W0PEAH_N0@Z`
- size: `208`
- prototype: `bool(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, int *, bool, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x100401d50`
- `0x10044d680`

## import_xrefs

- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044d7ea`
- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044d7ea`
- `sqldk!??_V@YAXPEAX@Z` at `0x100401dfe`
- `sqldk!??_V@YAXPEAX@Z` at `0x100401dfe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d847`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d847`
- `sqldk!SystemThread_TlsOffset` at `0x100401dad`
- `sqldk!SystemThread_TlsIndex` at `0x100401da4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044d810`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044d810`

## string_xrefs

- `0x10044d7ff`: `"serverconfig.cpp"`
- `0x10044d806`: `(!fAutoUpdate) || !SOS_Task::IsOnStack(plValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IServerConfiguration::GetDynamicInt32Setting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        int *a4,
        bool a5,
        const wchar_t *a6)
{
  __int64 v10; // rdi
  __int64 v11; // r9
  bool v12; // bl
  __int64 result; // rax
  wchar_t *String[5]; // [rsp+30h] [rbp-28h] BYREF

  String[1] = (wchar_t *)-2LL;
  if ( !a5 )
    goto LABEL_2;
  if ( SOS_Task::IsOnStack(a4) )
    utassert_fail(1u, "(!fAutoUpdate) || !SOS_Task::IsOnStack(plValue)", "\"serverconfig.cpp\"", 640, 0);
  result = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), int *, const wchar_t *))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3,
             DynamicInt32SettingSubscriber,
             a4,
             a6);
  if ( (_BYTE)result )
  {
LABEL_2:
    String[0] = 0;
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v11 = *(_QWORD *)(v10 + 256);
    if ( !v11 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v11 = *(_QWORD *)(v10 + 256);
    }
    v12 = (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, const wchar_t *))this
             + 3))(
            *((_QWORD *)this + 3),
            a2,
            a3,
            *(_QWORD *)(v11 + 1000),
            String,
            a6)
       && DynamicInt32SettingConverter(String[0], a4);
    operator delete[](String[0]);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x100401d50  push    rdi
0x100401d52  push    r14
0x100401d54  push    r15
0x100401d56  sub     rsp, 40h
0x100401d5a  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x100401d63  mov     [rsp+58h+arg_0], rbx
0x100401d68  mov     [rsp+58h+arg_8], rbp
0x100401d6d  mov     [rsp+58h+arg_10], rsi
0x100401d72  mov     rbx, r9
0x100401d75  mov     rsi, r8
0x100401d78  mov     rbp, rdx
0x100401d7b  mov     r14, rcx
0x100401d7e  xor     edi, edi
0x100401d80  mov     r15, [rsp+58h+arg_28]
0x100401d88  cmp     [rsp+58h+arg_20], dil
0x100401d90  jnz     loc_10044D7E7
0x100401d96  mov     [rsp+58h+String], rdi
0x100401d9b  mov     rdx, gs:58h
0x100401da4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100401dab  mov     ecx, [rax]
0x100401dad  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401db4  mov     edi, [rax]
0x100401db6  add     rdi, [rdx+rcx*8]
0x100401dba  mov     r9, [rdi+100h]
0x100401dc1  test    r9, r9
0x100401dc4  jz      loc_10044D845
0x100401dca  mov     rcx, [r14+18h]
0x100401dce  mov     rax, [rcx]
0x100401dd1  mov     [rsp+58h+var_30], r15
0x100401dd6  lea     rdx, [rsp+58h+String]
0x100401ddb  mov     [rsp+58h+var_38], rdx
0x100401de0  mov     r9, [r9+3E8h]
0x100401de7  mov     r8, rsi
0x100401dea  mov     rdx, rbp
0x100401ded  call    qword ptr [rax]
0x100401def  test    al, al
0x100401df1  jnz     loc_10044D85A
0x100401df7  xor     bl, bl
0x100401df9  mov     rcx, [rsp+58h+String]
0x100401dfe  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100401e04  movzx   eax, bl
0x100401e07  mov     rbx, [rsp+58h+arg_0]
0x100401e0c  mov     rbp, [rsp+58h+arg_8]
0x100401e11  mov     rsi, [rsp+58h+arg_10]
0x100401e16  add     rsp, 40h
0x100401e1a  pop     r15
0x100401e1c  pop     r14
0x100401e1e  pop     rdi
0x100401e1f  retn
0x10044d7e7  mov     rcx, rbx
0x10044d7ea  call    cs:__imp_?IsOnStack@SOS_Task@@SA_NPEBX@Z; SOS_Task::IsOnStack(void const *)
0x10044d7f0  test    al, al
0x10044d7f2  jz      short loc_10044D816
0x10044d7f4  mov     [rsp+58h+var_38], rdi
0x10044d7f9  mov     r9d, 280h
0x10044d7ff  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044d806  lea     rdx, aFautoupdateSos_0; "(!fAutoUpdate) || !SOS_Task::IsOnStack("...
0x10044d80d  lea     ecx, [rdi+1]
0x10044d810  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044d816  mov     rcx, [r14+18h]
0x10044d81a  mov     rax, [rcx]
0x10044d81d  mov     [rsp+58h+var_30], r15
0x10044d822  mov     [rsp+58h+var_38], rbx
0x10044d827  lea     r9, ?DynamicInt32SettingSubscriber@@YAXPEB_W00PEAX@Z; DynamicInt32SettingSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044d82e  mov     r8, rsi
0x10044d831  mov     rdx, rbp
0x10044d834  call    qword ptr [rax+8]
0x10044d837  test    al, al
0x10044d839  jnz     loc_100401D96
0x10044d83f  jmp     loc_100401E07
0x10044d845  xor     ecx, ecx
0x10044d847  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d84d  mov     r9, [rdi+100h]
0x10044d854  jmp     loc_100401DCA
0x10044d85a  mov     rdx, rbx; int *
0x10044d85d  mov     rcx, [rsp+58h+String]; String
0x10044d862  call    ?DynamicInt32SettingConverter@@YA_NPEB_WPEAH@Z; DynamicInt32SettingConverter(wchar_t const *,int *)
0x10044d867  test    al, al
0x10044d869  jz      loc_100401DF7
0x10044d86f  mov     bl, 1
0x10044d871  jmp     loc_100401DF9
```
