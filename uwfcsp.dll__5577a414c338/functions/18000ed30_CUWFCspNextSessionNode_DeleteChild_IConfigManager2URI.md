# CUWFCspNextSessionNode::DeleteChild(IConfigManager2URI *)

- ea: `0x18000ed30`
- end: `0x18000eec9`
- name: `?DeleteChild@CUWFCspNextSessionNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CUWFCspNextSessionNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000745c`
- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000ed30`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `uwfcfgmgmt!UwfCfgRemoveRegExclusion` at `0x18000ee76`
- `uwfcfgmgmt!UwfCfgRemoveRegExclusion` at `0x18000ee76`
- `uwfcfgmgmt!UwfCfgRemoveFileExclusion` at `0x18000ee20`
- `uwfcfgmgmt!UwfCfgRemoveFileExclusion` at `0x18000ee20`
- `uwfcfgmgmt!UwfCfgRemoveVolume` at `0x18000ee4d`
- `uwfcfgmgmt!UwfCfgRemoveVolume` at `0x18000ee4d`

## string_xrefs

- `0x18000ed75`: `UWFCSPNextSessionNodeDelete`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::DeleteChild(CUWFCspNextSessionNode *this, struct IConfigManager2URI *a2)
{
  int *v4; // rbx
  int v5; // edi
  int v6; // eax
  const unsigned __int16 *v8; // [rsp+20h] [rbp-E0h] BYREF
  const unsigned __int16 *v9; // [rsp+28h] [rbp-D8h] BYREF
  const unsigned __int16 *v10; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-C0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v11);
  v11[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v11, L"UWFCSPNextSessionNodeDelete");
  v8 = 0;
  v4 = (int *)((char *)this + 44);
  v10 = 0;
  v9 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_15;
  }
  if ( *v4 == 37 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
           a2,
           0,
           &v10);
    if ( v5 < 0 )
      goto LABEL_15;
    v6 = UwfCfgRemoveRegExclusion(v10);
    goto LABEL_14;
  }
  if ( *v4 == 42 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
           *((_QWORD *)this + 3),
           3,
           &v8);
    if ( v5 < 0 )
      goto LABEL_15;
    v6 = UwfCfgRemoveVolume(v8);
LABEL_14:
    v5 = v6;
    goto LABEL_15;
  }
  if ( *v4 != 48 )
  {
    v5 = -2046820335;
    goto LABEL_15;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         3,
         &v8);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
           a2,
           0,
           &v9);
    if ( v5 >= 0 )
    {
      v6 = UwfCfgRemoveFileExclusion(v8, v9);
      goto LABEL_14;
    }
  }
LABEL_15:
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v11,
    (unsigned int)v5);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long>((__int64)v11, *v4);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ed30  mov     [rsp-8+arg_10], rbx
0x18000ed35  mov     [rsp-8+arg_18], rsi
0x18000ed3a  push    rbp
0x18000ed3b  push    rdi
0x18000ed3c  push    r14
0x18000ed3e  lea     rbp, [rsp-0A0h]
0x18000ed46  sub     rsp, 1A0h
0x18000ed4d  mov     rax, cs:__security_cookie
0x18000ed54  xor     rax, rsp
0x18000ed57  mov     [rbp+0B0h+var_20], rax
0x18000ed5e  mov     rsi, rcx
0x18000ed61  mov     r14, rdx
0x18000ed64  lea     rcx, [rsp+1B0h+var_170]
0x18000ed69  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ed6e  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000ed75  lea     rdx, aUwfcspnextsess; "UWFCSPNextSessionNodeDelete"
0x18000ed7c  mov     [rsp+1B0h+var_170], rax
0x18000ed81  lea     rcx, [rsp+1B0h+var_170]
0x18000ed86  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000ed8b  mov     [rsp+1B0h+var_190], 0
0x18000ed94  lea     rbx, [rsi+2Ch]
0x18000ed98  mov     [rsp+1B0h+var_180], 0
0x18000eda1  mov     [rsp+1B0h+var_188], 0
0x18000edaa  test    r14, r14
0x18000edad  jnz     short loc_18000EDB9
0x18000edaf  mov     edi, 80070057h
0x18000edb4  jmp     loc_18000EE7E
0x18000edb9  cmp     dword ptr [rbx], 25h ; '%'
0x18000edbc  jz      loc_18000EE55
0x18000edc2  cmp     dword ptr [rbx], 2Ah ; '*'
0x18000edc5  jz      short loc_18000EE28
0x18000edc7  cmp     dword ptr [rbx], 30h ; '0'
0x18000edca  jz      short loc_18000EDD6
0x18000edcc  mov     edi, 86000011h
0x18000edd1  jmp     loc_18000EE7E
0x18000edd6  mov     rcx, [rsi+18h]
0x18000edda  lea     r8, [rsp+1B0h+var_190]
0x18000eddf  mov     edx, 3
0x18000ede4  mov     rax, [rcx]
0x18000ede7  mov     rax, [rax+58h]
0x18000edeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf0  mov     edi, eax
0x18000edf2  test    eax, eax
0x18000edf4  js      loc_18000EE7E
0x18000edfa  mov     rax, [r14]
0x18000edfd  lea     r8, [rsp+1B0h+var_188]
0x18000ee02  xor     edx, edx
0x18000ee04  mov     rcx, r14
0x18000ee07  mov     rax, [rax+58h]
0x18000ee0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee10  mov     edi, eax
0x18000ee12  test    eax, eax
0x18000ee14  js      short loc_18000EE7E
0x18000ee16  mov     rdx, [rsp+1B0h+var_188]
0x18000ee1b  mov     rcx, [rsp+1B0h+var_190]
0x18000ee20  call    cs:__imp_?UwfCfgRemoveFileExclusion@@YAJPEBG0@Z; UwfCfgRemoveFileExclusion(ushort const *,ushort const *)
0x18000ee26  jmp     short loc_18000EE7C
0x18000ee28  mov     rcx, [rsi+18h]
0x18000ee2c  lea     r8, [rsp+1B0h+var_190]
0x18000ee31  mov     edx, 3
0x18000ee36  mov     rax, [rcx]
0x18000ee39  mov     rax, [rax+58h]
0x18000ee3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee42  mov     edi, eax
0x18000ee44  test    eax, eax
0x18000ee46  js      short loc_18000EE7E
0x18000ee48  mov     rcx, [rsp+1B0h+var_190]
0x18000ee4d  call    cs:__imp_?UwfCfgRemoveVolume@@YAJPEBG@Z; UwfCfgRemoveVolume(ushort const *)
0x18000ee53  jmp     short loc_18000EE7C
0x18000ee55  mov     rax, [r14]
0x18000ee58  lea     r8, [rsp+1B0h+var_180]
0x18000ee5d  xor     edx, edx
0x18000ee5f  mov     rcx, r14
0x18000ee62  mov     rax, [rax+58h]
0x18000ee66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee6b  mov     edi, eax
0x18000ee6d  test    eax, eax
0x18000ee6f  js      short loc_18000EE7E
0x18000ee71  mov     rcx, [rsp+1B0h+var_180]
0x18000ee76  call    cs:__imp_?UwfCfgRemoveRegExclusion@@YAJPEBG@Z; UwfCfgRemoveRegExclusion(ushort const *)
0x18000ee7c  mov     edi, eax
0x18000ee7e  mov     edx, edi
0x18000ee80  lea     rcx, [rsp+1B0h+var_170]
0x18000ee85  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000ee8a  mov     edx, [rbx]
0x18000ee8c  lea     rcx, [rsp+1B0h+var_170]
0x18000ee91  call    ??$Stop@K@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXK@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong>(ulong)
0x18000ee96  lea     rcx, [rsp+1B0h+var_170]
0x18000ee9b  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x18000eea0  mov     eax, edi
0x18000eea2  mov     rcx, [rbp+0B0h+var_20]
0x18000eea9  xor     rcx, rsp; StackCookie
0x18000eeac  call    __security_check_cookie
0x18000eeb1  lea     r11, [rsp+1B0h+var_10]
0x18000eeb9  mov     rbx, [r11+30h]
0x18000eebd  mov     rsi, [r11+38h]
0x18000eec1  mov     rsp, r11
0x18000eec4  pop     r14
0x18000eec6  pop     rdi
0x18000eec7  pop     rbp
0x18000eec8  retn
```
