# CFeatureSwitchesTsEs::SetupSwitch(CFeatureSwitchDescriptor const *,wchar_t const *)

- ea: `0x10049ea40`
- end: `0x10049ebf8`
- name: `?SetupSwitch@CFeatureSwitchesTsEs@@CAXPEBUCFeatureSwitchDescriptor@@PEB_W@Z`
- size: `440`
- prototype: `void __fastcall(const struct CFeatureSwitchDescriptor *, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x10049ec00`

## callees

- `0x10049ea40`
- `0x10083c650`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10049ea66`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10049ead0`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10049ead0`
- `sqldk!??_V@YAXPEAX@Z` at `0x10049ebdf`
- `sqldk!??_V@YAXPEAX@Z` at `0x10049ebdf`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10049eb19`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10049eb19`
- `sqldk!SystemThread_TlsIndex` at `0x10049ea79`
- `sqldk!SystemThread_TlsIndex` at `0x10049eb36`
- `sqldk!SystemThread_TlsOffset` at `0x10049ea83`
- `sqldk!SystemThread_TlsOffset` at `0x10049eb3f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049ea9e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049eb5a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049ea9e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10049eb5a`

## string_xrefs

- `0x10049eabd`: `sql\ntdbms\common\serverconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CFeatureSwitchesTsEs::SetupSwitch(const struct CFeatureSwitchDescriptor *a1, const wchar_t *a2)
{
  __int64 v4; // rbp
  __int64 v5; // rdi
  __int64 v6; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rdi
  __int64 v9; // r9
  unsigned __int8 v10; // al
  bool v11; // [rsp+60h] [rbp+8h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp+18h] BYREF

  v4 = *((_QWORD *)a1 + 5);
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  v7 = operator new(
         0x10u,
         *(struct IMemObj **)(*(_QWORD *)(v6 + 992) + 320LL),
         "sql\\ntdbms\\common\\serverconfig.cpp",
         490,
         6u);
  *v7 = CFeatureSwitchesTsEs::SettingSubscriber;
  v7[1] = a1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, __int64, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), _QWORD *, const wchar_t *, __int64))(**((_QWORD **)s_pServerConf + 3) + 8LL))(
         *((_QWORD *)s_pServerConf + 3),
         L"FeatureSwitches",
         v4,
         DynamicBoolSettingCallbackSubscriber,
         v7,
         a2,
         -2) )
  {
    String1 = 0;
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v9 = *(_QWORD *)(v8 + 256);
    if ( !v9 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v9 = *(_QWORD *)(v8 + 256);
    }
    if ( (***((unsigned __int8 (__fastcall ****)(_QWORD, const wchar_t *, __int64, _QWORD, wchar_t **, const wchar_t *))s_pServerConf
            + 3))(
           *((_QWORD *)s_pServerConf + 3),
           L"FeatureSwitches",
           v4,
           *(_QWORD *)(v9 + 1000),
           &String1,
           a2) )
    {
      if ( DynamicBoolSettingConverter(String1, &v11) )
      {
        *((_BYTE *)&g_featureSwitchesTsEs + *((int *)a1 + 6)) = v11;
        if ( byte_1008F10F9 )
        {
          if ( *((_QWORD *)a1 + 6) )
          {
            v10 = (*((__int64 (**)(void))a1 + 1))();
            (*((void (__fastcall **)(_QWORD, _QWORD))a1 + 6))(v10, (unsigned int)dword_1008F10DC);
          }
        }
      }
    }
    operator delete[](String1);
  }
  else
  {
    operator delete(v7, 0x10u);
  }
}

```

## disassembly

```asm
0x10049ea40  push    rsi
0x10049ea42  push    rdi
0x10049ea43  push    r14
0x10049ea45  sub     rsp, 40h
0x10049ea49  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x10049ea52  mov     [rsp+58h+arg_8], rbx
0x10049ea57  mov     [rsp+58h+arg_18], rbp
0x10049ea5c  mov     rsi, rdx
0x10049ea5f  mov     rbx, rcx
0x10049ea62  mov     rbp, [rcx+28h]
0x10049ea66  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10049ea6d  mov     r14, [rax]
0x10049ea70  mov     r9, gs:58h
0x10049ea79  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049ea80  mov     r8d, [rax]
0x10049ea83  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049ea8a  mov     edi, [rax]
0x10049ea8c  add     rdi, [r9+r8*8]
0x10049ea90  mov     rax, [rdi+100h]
0x10049ea97  test    rax, rax
0x10049ea9a  jnz     short loc_10049EAAB
0x10049ea9c  xor     ecx, ecx
0x10049ea9e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049eaa4  mov     rax, [rdi+100h]
0x10049eaab  mov     rax, [rax+3E0h]
0x10049eab2  mov     byte ptr [rsp+58h+var_38], 6
0x10049eab7  mov     r9d, 1EAh
0x10049eabd  lea     r8, aSqlNtdbmsCommo; "sql\\ntdbms\\common\\serverconfig.cpp"
0x10049eac4  mov     rdx, [rax+140h]
0x10049eacb  mov     ecx, 10h
0x10049ead0  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new(unsigned __int64,IMemObj *,char const *,int,uchar)
0x10049ead6  mov     rdi, rax
0x10049ead9  lea     rax, ?SettingSubscriber@CFeatureSwitchesTsEs@@CAXPEB_W0_NPEAX@Z; CFeatureSwitchesTsEs::SettingSubscriber(wchar_t const *,wchar_t const *,bool,void *)
0x10049eae0  mov     [rdi], rax
0x10049eae3  mov     [rdi+8], rbx
0x10049eae7  mov     rcx, [r14+18h]
0x10049eaeb  mov     r10, [rcx]
0x10049eaee  mov     [rsp+58h+var_30], rsi
0x10049eaf3  mov     [rsp+58h+var_38], rdi
0x10049eaf8  lea     r9, ?DynamicBoolSettingCallbackSubscriber@@YAXPEB_W00PEAX@Z; DynamicBoolSettingCallbackSubscriber(wchar_t const *,wchar_t const *,wchar_t const *,void *)
0x10049eaff  mov     r8, rbp
0x10049eb02  lea     rdx, aFeatureswitche; "FeatureSwitches"
0x10049eb09  call    qword ptr [r10+8]
0x10049eb0d  test    al, al
0x10049eb0f  jnz     short loc_10049EB24
0x10049eb11  mov     edx, 10h
0x10049eb16  mov     rcx, rdi
0x10049eb19  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10049eb1f  jmp     loc_10049EBE5
0x10049eb24  mov     [rsp+58h+String1], 0
0x10049eb2d  mov     rdx, gs:58h
0x10049eb36  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049eb3d  mov     ecx, [rax]
0x10049eb3f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049eb46  mov     edi, [rax]
0x10049eb48  add     rdi, [rdx+rcx*8]
0x10049eb4c  mov     r9, [rdi+100h]
0x10049eb53  test    r9, r9
0x10049eb56  jnz     short loc_10049EB67
0x10049eb58  xor     ecx, ecx
0x10049eb5a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10049eb60  mov     r9, [rdi+100h]
0x10049eb67  mov     rcx, [r14+18h]
0x10049eb6b  mov     rax, [rcx]
0x10049eb6e  mov     [rsp+58h+var_30], rsi
0x10049eb73  lea     r8, [rsp+58h+String1]
0x10049eb78  mov     [rsp+58h+var_38], r8
0x10049eb7d  mov     r9, [r9+3E8h]
0x10049eb84  mov     r8, rbp
0x10049eb87  lea     rdx, aFeatureswitche; "FeatureSwitches"
0x10049eb8e  call    qword ptr [rax]
0x10049eb90  test    al, al
0x10049eb92  jz      short loc_10049EBDA
0x10049eb94  lea     rdx, [rsp+58h+arg_0]; bool *
0x10049eb99  mov     rcx, [rsp+58h+String1]; String1
0x10049eb9e  call    ?DynamicBoolSettingConverter@@YA_NPEB_WPEA_N@Z; DynamicBoolSettingConverter(wchar_t const *,bool *)
0x10049eba3  test    al, al
0x10049eba5  jz      short loc_10049EBDA
0x10049eba7  movsxd  rdx, dword ptr [rbx+18h]
0x10049ebab  lea     rcx, ?g_featureSwitchesTsEs@@3VCFeatureSwitchesTsEs@@A; CFeatureSwitchesTsEs g_featureSwitchesTsEs
0x10049ebb2  movzx   eax, [rsp+58h+arg_0]
0x10049ebb7  mov     [rdx+rcx], al
0x10049ebba  cmp     cs:byte_1008F10F9, 0
0x10049ebc1  jz      short loc_10049EBDA
0x10049ebc3  cmp     qword ptr [rbx+30h], 0
0x10049ebc8  jz      short loc_10049EBDA
0x10049ebca  call    qword ptr [rbx+8]
0x10049ebcd  movzx   ecx, al
0x10049ebd0  mov     edx, cs:dword_1008F10DC
0x10049ebd6  call    qword ptr [rbx+30h]
0x10049ebd9  nop
0x10049ebda  mov     rcx, [rsp+58h+String1]
0x10049ebdf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10049ebe5  mov     rbx, [rsp+58h+arg_8]
0x10049ebea  mov     rbp, [rsp+58h+arg_18]
0x10049ebef  add     rsp, 40h
0x10049ebf3  pop     r14
0x10049ebf5  pop     rdi
0x10049ebf6  pop     rsi
0x10049ebf7  retn
```
