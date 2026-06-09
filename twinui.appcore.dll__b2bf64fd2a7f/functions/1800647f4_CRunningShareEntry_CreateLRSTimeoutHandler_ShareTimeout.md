# CRunningShareEntry::_CreateLRSTimeoutHandler(ShareTimeout)

- ea: `0x1800647f4`
- end: `0x18006495d`
- name: `?_CreateLRSTimeoutHandler@CRunningShareEntry@@AEAAJW4ShareTimeout@@@Z`
- size: `361`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800635e0`
- `0x180064080`
- `0x1800642e0`

## callees

- `0x180003d24`
- `0x1800040e0`
- `0x1800160c0`
- `0x18002b1b0`
- `0x1800622b0`
- `0x1800647f4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006489b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006489b`
- `ntdll!RtlQueryResourcePolicy` at `0x180064822`
- `ntdll!RtlQueryResourcePolicy` at `0x180064822`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180064905`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180064905`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800648ba`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800648ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRunningShareEntry::_CreateLRSTimeoutHandler(__int64 a1, __int64 a2)
{
  int v3; // eax
  __int64 *v4; // rax
  __int64 v5; // rsi
  DWORD CurrentThreadId; // eax
  int AgileReference; // ebx
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h] BYREF
  __int128 v14; // [rsp+48h] [rbp-30h] BYREF
  int v15; // [rsp+58h] [rbp-20h]

  if ( !(_DWORD)a2 )
  {
    LODWORD(v11) = 0;
    RtlQueryResourcePolicy(0, a2, &v11, 4);
  }
  v3 = ++*(_DWORD *)(a1 + 136);
  v12 = 0;
  v14 = *(_OWORD *)(a1 + 48);
  v15 = v3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v4 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_bf567398130a370b78f09b518f6867d6_____lambda_bf567398130a370b78f09b518f6867d6___(
                    &v11,
                    &v14);
  v5 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  AgileReference = SHTaskPoolQueueTask(5, 0, CurrentThreadId);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( AgileReference >= 0 )
  {
    v8 = v12;
    v9 = 0;
    v11 = 0;
    AgileReference = 0;
    if ( v12 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
      AgileReference = RoGetAgileReference(0, &GUID_00000000_0000_0000_c000_000000000046, v8, &v11);
      v9 = v11;
    }
    v11 = 0;
    v13 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 144) = v9;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x1800647f4  push    rbp
0x1800647f6  push    rbx
0x1800647f7  push    rsi
0x1800647f8  push    rdi
0x1800647f9  mov     rbp, rsp
0x1800647fc  sub     rsp, 78h
0x180064800  mov     rax, cs:__security_cookie
0x180064807  xor     rax, rsp
0x18006480a  mov     [rbp+var_18], rax
0x18006480e  mov     rdi, rcx
0x180064811  test    edx, edx
0x180064813  jnz     short loc_180064840
0x180064815  mov     dword ptr [rbp+var_48], edx
0x180064818  lea     r9d, [rdx+4]
0x18006481c  lea     r8, [rbp+var_48]
0x180064820  xor     ecx, ecx
0x180064822  call    cs:__imp_RtlQueryResourcePolicy
0x180064828  test    eax, eax
0x18006482a  js      short loc_180064839
0x18006482c  cmp     dword ptr [rbp+var_48], 0Ah
0x180064830  jg      short loc_180064839
0x180064832  mov     ebx, 7530h
0x180064837  jmp     short loc_180064845
0x180064839  mov     ebx, 0EA60h
0x18006483e  jmp     short loc_180064845
0x180064840  mov     ebx, 1B7740h
0x180064845  inc     dword ptr [rdi+88h]
0x18006484b  mov     eax, [rdi+88h]
0x180064851  mov     [rbp+var_40], 0
0x180064859  movups  xmm0, xmmword ptr [rdi+30h]
0x18006485d  movdqu  [rbp+var_30], xmm0
0x180064862  mov     [rbp+var_20], eax
0x180064865  lea     rcx, [rbp+var_40]
0x180064869  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006486e  lea     rdx, [rbp+var_30]
0x180064872  lea     rcx, [rbp+var_48]
0x180064876  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_bf567398130a370b78f09b518f6867d6_____lambda_bf567398130a370b78f09b518f6867d6___
0x18006487b  mov     rsi, [rax]
0x18006487e  mov     qword ptr [rax], 0
0x180064885  mov     rcx, [rbp+var_48]
0x180064889  test    rcx, rcx
0x18006488c  jz      short loc_18006489B
0x18006488e  mov     [rbp+var_48], 0
0x180064896  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18006489b  call    cs:__imp_GetCurrentThreadId
0x1800648a1  lea     rcx, [rbp+var_40]
0x1800648a5  mov     [rsp+78h+var_50], rcx
0x1800648aa  mov     [rsp+78h+var_58], rsi
0x1800648af  mov     r9d, ebx
0x1800648b2  mov     r8d, eax
0x1800648b5  xor     edx, edx
0x1800648b7  lea     ecx, [rdx+5]
0x1800648ba  call    cs:__imp_SHTaskPoolQueueTask
0x1800648c0  mov     ebx, eax
0x1800648c2  test    rsi, rsi
0x1800648c5  jz      short loc_1800648D7
0x1800648c7  mov     rax, [rsi]
0x1800648ca  mov     rcx, rsi
0x1800648cd  mov     rax, [rax+10h]
0x1800648d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648d6  nop
0x1800648d7  test    ebx, ebx
0x1800648d9  js      short loc_18006493D
0x1800648db  mov     rsi, [rbp+var_40]
0x1800648df  xor     eax, eax
0x1800648e1  mov     [rbp+var_48], rax
0x1800648e5  xor     ebx, ebx
0x1800648e7  test    rsi, rsi
0x1800648ea  jz      short loc_180064911
0x1800648ec  lea     rcx, [rbp+var_48]
0x1800648f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800648f5  lea     r9, [rbp+var_48]
0x1800648f9  mov     r8, rsi
0x1800648fc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180064903  xor     ecx, ecx
0x180064905  call    cs:__imp_RoGetAgileReference
0x18006490b  mov     ebx, eax
0x18006490d  mov     rax, [rbp+var_48]
0x180064911  mov     [rbp+var_48], 0
0x180064919  mov     rcx, [rdi+90h]
0x180064920  mov     [rbp+var_38], rcx
0x180064924  mov     [rdi+90h], rax
0x18006492b  lea     rcx, [rbp+var_38]
0x18006492f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064934  lea     rcx, [rbp+var_48]
0x180064938  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006493d  lea     rcx, [rbp+var_40]
0x180064941  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180064946  mov     eax, ebx
0x180064948  mov     rcx, [rbp+var_18]
0x18006494c  xor     rcx, rsp; StackCookie
0x18006494f  call    __security_check_cookie
0x180064954  add     rsp, 78h
0x180064958  pop     rdi
0x180064959  pop     rsi
0x18006495a  pop     rbx
0x18006495b  pop     rbp
0x18006495c  retn
```
