# IServerConfiguration::GetDynamicDoubleSetting(wchar_t const *,wchar_t const *,double *,bool,wchar_t const *)

- ea: `0x10044e0b0`
- end: `0x10044e1f0`
- name: `?GetDynamicDoubleSetting@IServerConfiguration@@QEAA_NPEB_W0PEAN_N0@Z`
- size: `320`
- prototype: `bool(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, double *, bool, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x10042a380`

## callees

- `0x10044df30`
- `0x10044e0b0`

## import_xrefs

- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044e0f5`
- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x10044e0f5`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e1ce`
- `sqldk!??_V@YAXPEAX@Z` at `0x10044e1ce`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e17c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044e17c`
- `sqldk!SystemThread_TlsOffset` at `0x10044e161`
- `sqldk!SystemThread_TlsIndex` at `0x10044e158`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e11b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e11b`

## string_xrefs

- `0x10044e10a`: `"serverconfig.cpp"`
- `0x10044e111`: `(!fAutoUpdate) || !SOS_Task::IsOnStack(pdValue)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IServerConfiguration::GetDynamicDoubleSetting(
        IServerConfiguration *this,
        const wchar_t *a2,
        const wchar_t *a3,
        double *a4,
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
    utassert_fail(1u, "(!fAutoUpdate) || !SOS_Task::IsOnStack(pdValue)", "\"serverconfig.cpp\"", 973, 0);
  result = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), double *, const wchar_t *))(**((_QWORD **)this + 3) + 8LL))(
             *((_QWORD *)this + 3),
             a2,
             a3,
             DynamicDoubleSettingSubscriber,
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
       && DynamicDoubleSettingConverter(String[0], a4);
    operator delete[](String[0]);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x10044e0b0  push    rdi
0x10044e0b2  push    r14
0x10044e0b4  push    r15
0x10044e0b6  sub     rsp, 40h
0x10044e0ba  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x10044e0c3  mov     [rsp+58h+arg_0], rbx
0x10044e0c8  mov     [rsp+58h+arg_8], rbp
0x10044e0cd  mov     [rsp+58h+arg_10], rsi
0x10044e0d2  mov     rbx, r9
0x10044e0d5  mov     rsi, r8
0x10044e0d8  mov     rbp, rdx
0x10044e0db  mov     r14, rcx
0x10044e0de  xor     edi, edi
0x10044e0e0  mov     r15, [rsp+58h+arg_28]
0x10044e0e8  cmp     [rsp+58h+arg_20], dil
0x10044e0f0  jz      short loc_10044E14A
0x10044e0f2  mov     rcx, rbx
0x10044e0f5  call    cs:__imp_?IsOnStack@SOS_Task@@SA_NPEBX@Z; SOS_Task::IsOnStack(void const *)
0x10044e0fb  test    al, al
0x10044e0fd  jz      short loc_10044E121
0x10044e0ff  mov     [rsp+58h+var_38], rdi
0x10044e104  mov     r9d, 3CDh
0x10044e10a  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044e111  lea     rdx, aFautoupdateSos_2; "(!fAutoUpdate) || !SOS_Task::IsOnStack("...
0x10044e118  lea     ecx, [rdi+1]
0x10044e11b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044e121  mov     rcx, [r14+18h]
0x10044e125  mov     rax, [rcx]
0x10044e128  mov     [rsp+58h+var_30], r15
0x10044e12d  mov     [rsp+58h+var_38], rbx
0x10044e132  lea     r9, ?DynamicDoubleSettingSubscriber@@YAXPEB_W00PEAX@Z; DynamicDoubleSettingSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10044e139  mov     r8, rsi
0x10044e13c  mov     rdx, rbp
0x10044e13f  call    qword ptr [rax+8]
0x10044e142  test    al, al
0x10044e144  jz      loc_10044E1D7
0x10044e14a  mov     [rsp+58h+String], rdi
0x10044e14f  mov     rdx, gs:58h
0x10044e158  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044e15f  mov     ecx, [rax]
0x10044e161  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044e168  mov     edi, [rax]
0x10044e16a  add     rdi, [rdx+rcx*8]
0x10044e16e  mov     r9, [rdi+100h]
0x10044e175  test    r9, r9
0x10044e178  jnz     short loc_10044E189
0x10044e17a  xor     ecx, ecx
0x10044e17c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044e182  mov     r9, [rdi+100h]
0x10044e189  mov     rcx, [r14+18h]
0x10044e18d  mov     rax, [rcx]
0x10044e190  mov     [rsp+58h+var_30], r15
0x10044e195  lea     rdx, [rsp+58h+String]
0x10044e19a  mov     [rsp+58h+var_38], rdx
0x10044e19f  mov     r9, [r9+3E8h]
0x10044e1a6  mov     r8, rsi
0x10044e1a9  mov     rdx, rbp
0x10044e1ac  call    qword ptr [rax]
0x10044e1ae  test    al, al
0x10044e1b0  jz      short loc_10044E1C7
0x10044e1b2  mov     rdx, rbx; double *
0x10044e1b5  mov     rcx, [rsp+58h+String]; String
0x10044e1ba  call    ?DynamicDoubleSettingConverter@@YA_NPEB_WPEAN@Z; DynamicDoubleSettingConverter(wchar_t const *,double *)
0x10044e1bf  test    al, al
0x10044e1c1  jz      short loc_10044E1C7
0x10044e1c3  mov     bl, 1
0x10044e1c5  jmp     short loc_10044E1C9
0x10044e1c7  xor     bl, bl
0x10044e1c9  mov     rcx, [rsp+58h+String]
0x10044e1ce  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10044e1d4  movzx   eax, bl
0x10044e1d7  mov     rbx, [rsp+58h+arg_0]
0x10044e1dc  mov     rbp, [rsp+58h+arg_8]
0x10044e1e1  mov     rsi, [rsp+58h+arg_10]
0x10044e1e6  add     rsp, 40h
0x10044e1ea  pop     r15
0x10044e1ec  pop     r14
0x10044e1ee  pop     rdi
0x10044e1ef  retn
```
