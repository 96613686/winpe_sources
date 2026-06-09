# IServerConfiguration::GetDynamicInt64Setting(wchar_t const *,wchar_t const *,__int64 *,bool,wchar_t const *)

- ea: `0x10044dbf0`
- end: `0x10044dd30`
- name: `?GetDynamicInt64Setting@IServerConfiguration@@QEAA_NPEB_W0PEA_J_N0@Z`
- size: `320`
- prototype: `bool(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, __int64 *, bool, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x100429dc0`
- `0x10042a380`

## callees

- `0x10044da80`
- `0x10044dbf0`

## import_xrefs

- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044dc35`
- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044dc35`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044dd0e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044dd0e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dcbc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044dcbc`
- `sqldk!SystemThread_TlsOffset` at `0x10044dca1`
- `sqldk!SystemThread_TlsIndex` at `0x10044dc98`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044dc5b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044dc5b`

## string_xrefs

- `0x10044dc4a`: `"serverconfig.cpp"`
- `0x10044dc51`: `(!fAutoUpdate) || !SOS_Task::IsOnStack(pllValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IServerConfiguration::GetDynamicInt64Setting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        __int64 *a4,
        bool a5,
        const wchar_t *a6)
{
  __int64 result; // rax
  __int64 v11; // rdi
  __int64 v12; // r9
  bool v13; // bl
  wchar_t *String[5]; // [rsp+30h] [rbp-28h] BYREF

  String[1] = (wchar_t *)-2LL;
  if ( !a5 )
    goto LABEL_5;
  if ( SOS_Task::IsOnStack(a4) )
    utassert_fail(1u, "(!fAutoUpdate) || !SOS_Task::IsOnStack(pllValue)", "\"serverconfig.cpp\"", 806, 0);
  result = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), __int64 *, const wchar_t *))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3,
             DynamicInt64SettingSubscriber,
             a4,
             a6);
  if ( (_BYTE)result )
  {
LABEL_5:
    String[0] = 0;
    v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    v13 = (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, wchar_t **, const wchar_t *))this
             + 3))(
            *((_QWORD *)this + 3),
            a2,
            a3,
            *(_QWORD *)(v12 + 1000),
            String,
            a6)
       && DynamicInt64SettingConverter(String[0], a4);
    operator delete[](String[0]);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x10044dbf0  push    rdi
0x10044dbf2  push    r14
0x10044dbf4  push    r15
0x10044dbf6  sub     rsp, 40h
0x10044dbfa  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x10044dc03  mov     [rsp+58h+arg_0], rbx
0x10044dc08  mov     [rsp+58h+arg_8], rbp
0x10044dc0d  mov     [rsp+58h+arg_10], rsi
0x10044dc12  mov     rbx, r9
0x10044dc15  mov     rsi, r8
0x10044dc18  mov     rbp, rdx
0x10044dc1b  mov     r14, rcx
0x10044dc1e  xor     edi, edi
0x10044dc20  mov     r15, [rsp+58h+arg_28]
0x10044dc28  cmp     [rsp+58h+arg_20], dil
0x10044dc30  jz      short loc_10044DC8A
0x10044dc32  mov     rcx, rbx
0x10044dc35  call    cs:__imp_?IsOnStack@SOS_Task@@SA_NPEBX@Z; SOS_Task::IsOnStack(void const *)
0x10044dc3b  test    al, al
0x10044dc3d  jz      short loc_10044DC61
0x10044dc3f  mov     [rsp+58h+var_38], rdi
0x10044dc44  mov     r9d, 326h
0x10044dc4a  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044dc51  lea     rdx, aFautoupdateSos_1; "(!fAutoUpdate) || !SOS_Task::IsOnStack("...
0x10044dc58  lea     ecx, [rdi+1]
0x10044dc5b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044dc61  mov     rcx, [r14+18h]
0x10044dc65  mov     rax, [rcx]
0x10044dc68  mov     [rsp+58h+var_30], r15
0x10044dc6d  mov     [rsp+58h+var_38], rbx
0x10044dc72  lea     r9, ?DynamicInt64SettingSubscriber@@YAXPEB_W00PEAX@Z; DynamicInt64SettingSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044dc79  mov     r8, rsi
0x10044dc7c  mov     rdx, rbp
0x10044dc7f  call    qword ptr [rax+8]
0x10044dc82  test    al, al
0x10044dc84  jz      loc_10044DD17
0x10044dc8a  mov     [rsp+58h+String], rdi
0x10044dc8f  mov     rdx, gs:58h
0x10044dc98  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044dc9f  mov     ecx, [rax]
0x10044dca1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044dca8  mov     edi, [rax]
0x10044dcaa  add     rdi, [rdx+rcx*8]
0x10044dcae  mov     r9, [rdi+100h]
0x10044dcb5  test    r9, r9
0x10044dcb8  jnz     short loc_10044DCC9
0x10044dcba  xor     ecx, ecx
0x10044dcbc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044dcc2  mov     r9, [rdi+100h]
0x10044dcc9  mov     rcx, [r14+18h]
0x10044dccd  mov     rax, [rcx]
0x10044dcd0  mov     [rsp+58h+var_30], r15
0x10044dcd5  lea     rdx, [rsp+58h+String]
0x10044dcda  mov     [rsp+58h+var_38], rdx
0x10044dcdf  mov     r9, [r9+3E8h]
0x10044dce6  mov     r8, rsi
0x10044dce9  mov     rdx, rbp
0x10044dcec  call    qword ptr [rax]
0x10044dcee  test    al, al
0x10044dcf0  jz      short loc_10044DD07
0x10044dcf2  mov     rdx, rbx; __int64 *
0x10044dcf5  mov     rcx, [rsp+58h+String]; String
0x10044dcfa  call    ?DynamicInt64SettingConverter@@YA_NPEB_WPEA_J@Z; DynamicInt64SettingConverter(wchar_t const *,__int64 *)
0x10044dcff  test    al, al
0x10044dd01  jz      short loc_10044DD07
0x10044dd03  mov     bl, 1
0x10044dd05  jmp     short loc_10044DD09
0x10044dd07  xor     bl, bl
0x10044dd09  mov     rcx, [rsp+58h+String]
0x10044dd0e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044dd14  movzx   eax, bl
0x10044dd17  mov     rbx, [rsp+58h+arg_0]
0x10044dd1c  mov     rbp, [rsp+58h+arg_8]
0x10044dd21  mov     rsi, [rsp+58h+arg_10]
0x10044dd26  add     rsp, 40h
0x10044dd2a  pop     r15
0x10044dd2c  pop     r14
0x10044dd2e  pop     rdi
0x10044dd2f  retn
```
