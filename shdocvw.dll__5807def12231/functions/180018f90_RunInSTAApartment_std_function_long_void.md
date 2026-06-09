# RunInSTAApartment(std::function<long (void)>)

- ea: `0x180018f90`
- end: `0x180019113`
- name: `?RunInSTAApartment@@YAJV?$function@$$A6AJXZ@std@@@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001794c`

## callees

- `0x180008320`
- `0x18000b924`
- `0x180012db8`
- `0x18001570c`
- `0x180018730`
- `0x180018f90`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180018fce`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180018fce`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800190b4`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800190b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RunInSTAApartment(__int64 *a1)
{
  HRESULT ApartmentType; // eax
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 *v5; // rcx
  void (__fastcall *v6)(__int64 *, __int64); // rax
  __int64 *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // esi
  __int64 *v13; // rcx
  int v14; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v17[1] = a1;
  v16 = 0;
  LODWORD(v17[0]) = 0;
  ApartmentType = CoGetApartmentType((APTTYPE *)&v16, (APTTYPEQUALIFIER *)v17);
  v3 = ApartmentType;
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95B,
      (unsigned int)"shell\\shdocvw\\download.cpp",
      (const char *)(unsigned int)ApartmentType,
      v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x964,
      (unsigned int)"shell\\shdocvw\\download.cpp",
      (const char *)v3,
      v15);
    v5 = (__int64 *)a1[7];
    if ( !v5 )
      return v3;
    v6 = *(void (__fastcall **)(__int64 *, __int64))(*v5 + 32);
LABEL_4:
    LOBYTE(v4) = v5 != a1;
    v6(v5, v4);
    a1[7] = 0;
    return v3;
  }
  if ( !v16 || v16 == 3 )
  {
    v3 = std::_Func_class<long,>::operator()(a1);
    v5 = (__int64 *)a1[7];
    if ( !v5 )
      return v3;
    v4 = *v5;
    v6 = *(void (__fastcall **)(__int64 *, __int64))(*v5 + 32);
    goto LABEL_4;
  }
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>,std::function<long (void)> &>(
                    v17,
                    a1);
  v10 = *v9;
  *v9 = 0;
  if ( v17[0] )
  {
    v17[0] = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v12 = SHTaskPoolQueueTask(1, 32, 0);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v13 = (__int64 *)a1[7];
  if ( v13 )
  {
    LOBYTE(v11) = v13 != a1;
    (*(void (__fastcall **)(__int64 *, __int64))(*v13 + 32))(v13, v11);
    a1[7] = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180018f90  mov     r11, rsp
0x180018f93  mov     [r11+10h], rbx
0x180018f97  mov     [r11+18h], rsi
0x180018f9b  push    rdi
0x180018f9c  sub     rsp, 50h
0x180018fa0  mov     rax, cs:__security_cookie
0x180018fa7  xor     rax, rsp
0x180018faa  mov     [rsp+58h+var_10], rax
0x180018faf  mov     rbx, rcx
0x180018fb2  mov     [r11-18h], rcx
0x180018fb6  mov     [rsp+58h+var_28], 0
0x180018fbe  mov     dword ptr [rsp+58h+var_20], 0
0x180018fc6  lea     rdx, [r11-20h]; pAptQualifier
0x180018fca  lea     rcx, [r11-28h]; pAptType
0x180018fce  call    cs:__imp_CoGetApartmentType
0x180018fd4  mov     edi, eax
0x180018fd6  test    eax, eax
0x180018fd8  jns     short loc_180019037
0x180018fda  mov     rcx, [rsp+58h]; this
0x180018fdf  mov     r9d, eax; char *
0x180018fe2  lea     r8, aShellShdocvwDo_0; "shell\\shdocvw\\download.cpp"
0x180018fe9  mov     edx, 95Bh; void *
0x180018fee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ff3  mov     rcx, [rsp+58h]; this
0x180018ff8  mov     r9d, edi; char *
0x180018ffb  lea     r8, aShellShdocvwDo_0; "shell\\shdocvw\\download.cpp"
0x180019002  mov     edx, 964h; void *
0x180019007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001900c  nop
0x18001900d  mov     rcx, [rbx+38h]
0x180019011  test    rcx, rcx
0x180019014  jz      short loc_180019030
0x180019016  mov     rax, [rcx]
0x180019019  mov     rax, [rax+20h]
0x18001901d  cmp     rcx, rbx
0x180019020  setnz   dl
0x180019023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019028  mov     qword ptr [rbx+38h], 0
0x180019030  mov     eax, edi
0x180019032  jmp     loc_1800190F6
0x180019037  mov     eax, [rsp+58h+var_28]
0x18001903b  test    eax, eax
0x18001903d  jz      short loc_180019048
0x18001903f  cmp     eax, 3
0x180019042  jz      short loc_180019048
0x180019044  xor     al, al
0x180019046  jmp     short loc_18001904A
0x180019048  mov     al, 1
0x18001904a  test    al, al
0x18001904c  jz      short loc_18001906A
0x18001904e  mov     rcx, rbx
0x180019051  call    ??R?$_Func_class@J$$V@std@@QEBAJXZ; std::_Func_class<long,>::operator()(void)
0x180019056  mov     edi, eax
0x180019058  mov     rcx, [rbx+38h]
0x18001905c  test    rcx, rcx
0x18001905f  jz      short loc_180019030
0x180019061  mov     rdx, [rcx]
0x180019064  mov     rax, [rdx+20h]
0x180019068  jmp     short loc_18001901D
0x18001906a  mov     rdx, rbx
0x18001906d  lea     rcx, [rsp+58h+var_20]
0x180019072  call    ??$Make@V?$CTaskWrapper@AEAV?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@AEAV?$function@$$A6AJXZ@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@@12@AEAV?$function@$$A6AJXZ@std@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>,std::function<long (void)> &>(std::function<long (void)> &)
0x180019077  mov     rdi, [rax]
0x18001907a  mov     qword ptr [rax], 0
0x180019081  mov     rcx, [rsp+58h+var_20]
0x180019086  test    rcx, rcx
0x180019089  jz      short loc_180019099
0x18001908b  mov     [rsp+58h+var_20], 0
0x180019094  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180019099  mov     [rsp+58h+var_30], 0
0x1800190a2  mov     [rsp+58h+var_38], rdi
0x1800190a7  xor     r9d, r9d
0x1800190aa  xor     r8d, r8d
0x1800190ad  lea     edx, [r9+20h]
0x1800190b1  lea     ecx, [rdx-1Fh]
0x1800190b4  call    cs:__imp_SHTaskPoolQueueTask
0x1800190ba  mov     esi, eax
0x1800190bc  test    rdi, rdi
0x1800190bf  jz      short loc_1800190D1
0x1800190c1  mov     rdx, [rdi]
0x1800190c4  mov     rcx, rdi
0x1800190c7  mov     rax, [rdx+10h]
0x1800190cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d0  nop
0x1800190d1  mov     rcx, [rbx+38h]
0x1800190d5  test    rcx, rcx
0x1800190d8  jz      short loc_1800190F4
0x1800190da  mov     rax, [rcx]
0x1800190dd  cmp     rcx, rbx
0x1800190e0  setnz   dl
0x1800190e3  mov     rax, [rax+20h]
0x1800190e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190ec  mov     qword ptr [rbx+38h], 0
0x1800190f4  mov     eax, esi
0x1800190f6  mov     rcx, [rsp+58h+var_10]
0x1800190fb  xor     rcx, rsp; StackCookie
0x1800190fe  call    __security_check_cookie
0x180019103  mov     rbx, [rsp+58h+arg_8]
0x180019108  mov     rsi, [rsp+58h+arg_10]
0x18001910d  add     rsp, 50h
0x180019111  pop     rdi
0x180019112  retn
```
