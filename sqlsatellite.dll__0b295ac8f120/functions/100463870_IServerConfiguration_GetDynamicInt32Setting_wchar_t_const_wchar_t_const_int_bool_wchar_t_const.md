# IServerConfiguration::GetDynamicInt32Setting(wchar_t const *,wchar_t const *,int *,bool,wchar_t const *)

- ea: `0x100463870`
- end: `0x1004639b0`
- name: `?GetDynamicInt32Setting@IServerConfiguration@@UEAA_NPEB_W0PEAH_N0@Z`
- size: `320`
- prototype: `bool(IServerConfiguration *__hidden this, const wchar_t *, const wchar_t *, int *, bool, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1004637b0`
- `0x100463870`

## import_xrefs

- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x1004638b5`
- `sqldk!?IsOnStack@SOS_Task@@SA_NPEBX@Z` at `0x1004638b5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004638db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004638db`
- `sqldk!??_V@YAXPEAX@Z` at `0x10046398e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10046398e`
- `sqldk!SystemThread_TlsIndex` at `0x100463918`
- `sqldk!SystemThread_TlsOffset` at `0x100463921`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10046393c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10046393c`

## string_xrefs

- `0x1004638ca`: `"serverconfig.cpp"`
- `0x1004638d1`: `(!fAutoUpdate) || !SOS_Task::IsOnStack(plValue)`

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
  __int64 result; // rax
  __int64 v11; // rdi
  __int64 v12; // r9
  bool v13; // bl
  wchar_t *String[5]; // [rsp+30h] [rbp-28h] BYREF

  String[1] = (wchar_t *)-2LL;
  if ( !a5 )
    goto LABEL_5;
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
       && DynamicInt32SettingConverter(String[0], a4);
    operator delete[](String[0]);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x100463870  push    rdi
0x100463872  push    r14
0x100463874  push    r15
0x100463876  sub     rsp, 40h
0x10046387a  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x100463883  mov     [rsp+58h+arg_0], rbx
0x100463888  mov     [rsp+58h+arg_8], rbp
0x10046388d  mov     [rsp+58h+arg_10], rsi
0x100463892  mov     rbx, r9
0x100463895  mov     rsi, r8
0x100463898  mov     rbp, rdx
0x10046389b  mov     r14, rcx
0x10046389e  xor     edi, edi
0x1004638a0  mov     r15, [rsp+58h+arg_28]
0x1004638a8  cmp     [rsp+58h+arg_20], dil
0x1004638b0  jz      short loc_10046390A
0x1004638b2  mov     rcx, rbx
0x1004638b5  call    cs:__imp_?IsOnStack@SOS_Task@@SA_NPEBX@Z; SOS_Task::IsOnStack(void const *)
0x1004638bb  test    al, al
0x1004638bd  jz      short loc_1004638E1
0x1004638bf  mov     [rsp+58h+var_38], rdi
0x1004638c4  mov     r9d, 280h
0x1004638ca  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x1004638d1  lea     rdx, aFautoupdateSos; "(!fAutoUpdate) || !SOS_Task::IsOnStack("...
0x1004638d8  lea     ecx, [rdi+1]
0x1004638db  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004638e1  mov     rcx, [r14+18h]
0x1004638e5  mov     rax, [rcx]
0x1004638e8  mov     [rsp+58h+var_30], r15
0x1004638ed  mov     [rsp+58h+var_38], rbx
0x1004638f2  lea     r9, ?DynamicInt32SettingSubscriber@@YAXPEB_W00PEAX@Z; DynamicInt32SettingSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x1004638f9  mov     r8, rsi
0x1004638fc  mov     rdx, rbp
0x1004638ff  call    qword ptr [rax+8]
0x100463902  test    al, al
0x100463904  jz      loc_100463997
0x10046390a  mov     [rsp+58h+String], rdi
0x10046390f  mov     rdx, gs:58h
0x100463918  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10046391f  mov     ecx, [rax]
0x100463921  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100463928  mov     edi, [rax]
0x10046392a  add     rdi, [rdx+rcx*8]
0x10046392e  mov     r9, [rdi+100h]
0x100463935  test    r9, r9
0x100463938  jnz     short loc_100463949
0x10046393a  xor     ecx, ecx
0x10046393c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100463942  mov     r9, [rdi+100h]
0x100463949  mov     rcx, [r14+18h]
0x10046394d  mov     rax, [rcx]
0x100463950  mov     [rsp+58h+var_30], r15
0x100463955  lea     rdx, [rsp+58h+String]
0x10046395a  mov     [rsp+58h+var_38], rdx
0x10046395f  mov     r9, [r9+3E8h]
0x100463966  mov     r8, rsi
0x100463969  mov     rdx, rbp
0x10046396c  call    qword ptr [rax]
0x10046396e  test    al, al
0x100463970  jz      short loc_100463987
0x100463972  mov     rdx, rbx; int *
0x100463975  mov     rcx, [rsp+58h+String]; String
0x10046397a  call    ?DynamicInt32SettingConverter@@YA_NPEB_WPEAH@Z; DynamicInt32SettingConverter(wchar_t const *,int *)
0x10046397f  test    al, al
0x100463981  jz      short loc_100463987
0x100463983  mov     bl, 1
0x100463985  jmp     short loc_100463989
0x100463987  xor     bl, bl
0x100463989  mov     rcx, [rsp+58h+String]
0x10046398e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100463994  movzx   eax, bl
0x100463997  mov     rbx, [rsp+58h+arg_0]
0x10046399c  mov     rbp, [rsp+58h+arg_8]
0x1004639a1  mov     rsi, [rsp+58h+arg_10]
0x1004639a6  add     rsp, 40h
0x1004639aa  pop     r15
0x1004639ac  pop     r14
0x1004639ae  pop     rdi
0x1004639af  retn
```
