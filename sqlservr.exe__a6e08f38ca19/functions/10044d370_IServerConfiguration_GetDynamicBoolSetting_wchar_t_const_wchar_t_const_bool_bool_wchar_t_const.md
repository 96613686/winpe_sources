# IServerConfiguration::GetDynamicBoolSetting(wchar_t const *,wchar_t const *,bool *,bool,wchar_t const *)

- ea: `0x10044d370`
- end: `0x10044d4b0`
- name: `?GetDynamicBoolSetting@IServerConfiguration@@QEAA_NPEB_W0PEA_N_N0@Z`
- size: `320`
- prototype: `bool(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, bool *, bool, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044d210`
- `0x10044d370`

## import_xrefs

- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044d3b5`
- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044d3b5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d48e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044d48e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d43c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044d43c`
- `sqldk!SystemThread_TlsOffset` at `0x10044d421`
- `sqldk!SystemThread_TlsIndex` at `0x10044d418`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044d3db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044d3db`

## string_xrefs

- `0x10044d3ca`: `"serverconfig.cpp"`
- `0x10044d3d1`: `(!fAutoUpdate) || !SOS_Task::IsOnStack(pfValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IServerConfiguration::GetDynamicBoolSetting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        bool *a4,
        bool a5,
        const wchar_t *a6)
{
  __int64 result; // rax
  __int64 v11; // rdi
  __int64 v12; // r9
  bool v13; // bl
  wchar_t *String1[5]; // [rsp+30h] [rbp-28h] BYREF

  String1[1] = (wchar_t *)-2LL;
  if ( !a5 )
    goto LABEL_5;
  if ( SOS_Task::IsOnStack(a4) )
    utassert_fail(1u, "(!fAutoUpdate) || !SOS_Task::IsOnStack(pfValue)", "\"serverconfig.cpp\"", 449, 0);
  result = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), bool *, const wchar_t *))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3,
             DynamicBoolSettingSubscriber,
             a4,
             a6);
  if ( (_BYTE)result )
  {
LABEL_5:
    String1[0] = 0;
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
            String1,
            a6)
       && DynamicBoolSettingConverter(String1[0], a4);
    operator delete[](String1[0]);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x10044d370  push    rdi
0x10044d372  push    r14
0x10044d374  push    r15
0x10044d376  sub     rsp, 40h
0x10044d37a  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x10044d383  mov     [rsp+58h+arg_0], rbx
0x10044d388  mov     [rsp+58h+arg_8], rbp
0x10044d38d  mov     [rsp+58h+arg_10], rsi
0x10044d392  mov     rbx, r9
0x10044d395  mov     rsi, r8
0x10044d398  mov     rbp, rdx
0x10044d39b  mov     r14, rcx
0x10044d39e  xor     edi, edi
0x10044d3a0  mov     r15, [rsp+58h+arg_28]
0x10044d3a8  cmp     [rsp+58h+arg_20], dil
0x10044d3b0  jz      short loc_10044D40A
0x10044d3b2  mov     rcx, rbx
0x10044d3b5  call    cs:__imp_?IsOnStack@SOS_Task@@SA_NPEBX@Z; SOS_Task::IsOnStack(void const *)
0x10044d3bb  test    al, al
0x10044d3bd  jz      short loc_10044D3E1
0x10044d3bf  mov     [rsp+58h+var_38], rdi
0x10044d3c4  mov     r9d, 1C1h
0x10044d3ca  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044d3d1  lea     rdx, aFautoupdateSos; "(!fAutoUpdate) || !SOS_Task::IsOnStack("...
0x10044d3d8  lea     ecx, [rdi+1]
0x10044d3db  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044d3e1  mov     rcx, [r14+18h]
0x10044d3e5  mov     rax, [rcx]
0x10044d3e8  mov     [rsp+58h+var_30], r15
0x10044d3ed  mov     [rsp+58h+var_38], rbx
0x10044d3f2  lea     r9, ?DynamicBoolSettingSubscriber@@YAXPEB_W00PEAX@Z; DynamicBoolSettingSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044d3f9  mov     r8, rsi
0x10044d3fc  mov     rdx, rbp
0x10044d3ff  call    qword ptr [rax+8]
0x10044d402  test    al, al
0x10044d404  jz      loc_10044D497
0x10044d40a  mov     [rsp+58h+String1], rdi
0x10044d40f  mov     rdx, gs:58h
0x10044d418  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044d41f  mov     ecx, [rax]
0x10044d421  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044d428  mov     edi, [rax]
0x10044d42a  add     rdi, [rdx+rcx*8]
0x10044d42e  mov     r9, [rdi+100h]
0x10044d435  test    r9, r9
0x10044d438  jnz     short loc_10044D449
0x10044d43a  xor     ecx, ecx
0x10044d43c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044d442  mov     r9, [rdi+100h]
0x10044d449  mov     rcx, [r14+18h]
0x10044d44d  mov     rax, [rcx]
0x10044d450  mov     [rsp+58h+var_30], r15
0x10044d455  lea     rdx, [rsp+58h+String1]
0x10044d45a  mov     [rsp+58h+var_38], rdx
0x10044d45f  mov     r9, [r9+3E8h]
0x10044d466  mov     r8, rsi
0x10044d469  mov     rdx, rbp
0x10044d46c  call    qword ptr [rax]
0x10044d46e  test    al, al
0x10044d470  jz      short loc_10044D487
0x10044d472  mov     rdx, rbx; bool *
0x10044d475  mov     rcx, [rsp+58h+String1]; String1
0x10044d47a  call    ?DynamicBoolSettingConverter@@YA_NPEB_WPEA_N@Z; DynamicBoolSettingConverter(wchar_t const *,bool *)
0x10044d47f  test    al, al
0x10044d481  jz      short loc_10044D487
0x10044d483  mov     bl, 1
0x10044d485  jmp     short loc_10044D489
0x10044d487  xor     bl, bl
0x10044d489  mov     rcx, [rsp+58h+String1]
0x10044d48e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044d494  movzx   eax, bl
0x10044d497  mov     rbx, [rsp+58h+arg_0]
0x10044d49c  mov     rbp, [rsp+58h+arg_8]
0x10044d4a1  mov     rsi, [rsp+58h+arg_10]
0x10044d4a6  add     rsp, 40h
0x10044d4aa  pop     r15
0x10044d4ac  pop     r14
0x10044d4ae  pop     rdi
0x10044d4af  retn
```
