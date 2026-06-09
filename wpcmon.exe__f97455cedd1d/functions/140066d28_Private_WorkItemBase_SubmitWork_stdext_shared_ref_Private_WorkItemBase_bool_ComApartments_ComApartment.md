# Private::WorkItemBase::SubmitWork(stdext::shared_ref<Private::WorkItemBase>,bool,ComApartments::ComApartment)

- ea: `0x140066d28`
- end: `0x140066f9f`
- name: `?SubmitWork@WorkItemBase@Private@@SAXV?$shared_ref@VWorkItemBase@Private@@@stdext@@_NW4ComApartment@ComApartments@@@Z`
- size: `631`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14006226c`
- `0x14006239c`
- `0x14006b180`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001f6b4`
- `0x14005bbac`
- `0x14005bc1c`
- `0x140060f58`
- `0x1400658b0`
- `0x140066d28`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!TrySubmitThreadpoolCallback` at `0x140066e81`
- `KERNEL32!TrySubmitThreadpoolCallback` at `0x140066e81`
- `KERNEL32!GetLastError` at `0x140066f3c`
- `KERNEL32!GetLastError` at `0x140066f3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Private::WorkItemBase::SubmitWork(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  unsigned __int128 v10; // kr00_16
  __int64 v11; // r14
  _QWORD *v12; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v13; // r8
  unsigned __int64 v14; // rsi
  volatile signed __int32 *v15; // rbx
  signed int LastError; // eax
  unsigned int v17; // ebx
  unsigned __int128 v18; // [rsp+20h] [rbp-79h] BYREF
  __int64 v19; // [rsp+30h] [rbp-69h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-61h]
  _QWORD *v21; // [rsp+40h] [rbp-59h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v23[64]; // [rsp+70h] [rbp-29h] BYREF

  v21 = a1;
  *(_BYTE *)(*a1 + 24LL) = 1;
  *(_DWORD *)(*a1 + 28LL) = 0;
  v2 = a1[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v3 = *a1;
  v4 = a1[1];
  *(_QWORD *)(v3 + 48) = v3;
  v5 = *(volatile signed __int32 **)(v3 + 56);
  *(_QWORD *)(v3 + 56) = v4;
  if ( v5 )
  {
    if ( !_InterlockedDecrement(v5 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  *(_QWORD *)&v18 = a1;
  ScopeGuard::ScopeGuard__lambda_db7cd3f6d2f340133d3914887c407899___(v23, &v18);
  v6 = *a1;
  v18 = 0;
  v7 = *(_QWORD *)(v6 + 40);
  if ( v7 )
  {
    v8 = *(_DWORD *)(v7 + 8);
    while ( v8 )
    {
      v9 = v8;
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      if ( v9 == v8 )
      {
        v14 = *(_QWORD *)(v6 + 32);
        *(_QWORD *)&v18 = v14;
        *((_QWORD *)&v18 + 1) = *(_QWORD *)(v6 + 40);
        v10 = __PAIR128__(*((unsigned __int64 *)&v18 + 1), v14);
        goto LABEL_12;
      }
    }
  }
  v10 = v18;
LABEL_12:
  if ( (_QWORD)v10 )
  {
    v11 = *a1;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v10 + 88) + 48LL))(v10 + 88, &v19);
    v12 = v20;
    if ( *v20 )
    {
      *(_QWORD *)(*v20 + 80LL) = v11;
      v12 = v20;
    }
    *(_QWORD *)(v11 + 80) = 0;
    *(_QWORD *)(v11 + 88) = *v12;
    *v12 = v11;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19);
    v13 = (struct _TP_CALLBACK_ENVIRON_V3 *)(v10 + 8);
  }
  else
  {
    v13 = 0;
  }
  if ( !TrySubmitThreadpoolCallback(Private::WorkItemBase::WorkCallback, (PVOID)*a1, v13) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v17);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v17);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ScopeGuard::Dismiss((ScopeGuard *)v23);
  if ( *((_QWORD *)&v10 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
    }
  }
  ScopeGuard::~ScopeGuard((ScopeGuard *)v23);
  v15 = (volatile signed __int32 *)a1[1];
  if ( v15 && !_InterlockedDecrement(v15 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
    if ( !_InterlockedDecrement(v15 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
}

```

## disassembly

```asm
0x140066d28  push    rbp
0x140066d2a  push    rbx
0x140066d2b  push    rsi
0x140066d2c  push    rdi
0x140066d2d  push    r14
0x140066d2f  push    r15
0x140066d31  lea     rbp, [rsp-2Fh]
0x140066d36  sub     rsp, 0C8h
0x140066d3d  mov     rax, cs:__security_cookie
0x140066d44  xor     rax, rsp
0x140066d47  mov     [rbp+57h+var_40], rax
0x140066d4b  mov     rdi, rcx
0x140066d4e  mov     [rbp+57h+var_B0], rcx
0x140066d52  mov     rax, [rcx]
0x140066d55  mov     byte ptr [rax+18h], 1
0x140066d59  mov     rax, [rcx]
0x140066d5c  mov     dword ptr [rax+1Ch], 0
0x140066d63  mov     rax, [rcx+8]
0x140066d67  test    rax, rax
0x140066d6a  jz      short loc_140066D70
0x140066d6c  lock inc dword ptr [rax+8]
0x140066d70  mov     rcx, [rcx]
0x140066d73  mov     rax, [rdi+8]
0x140066d77  mov     [rcx+30h], rcx
0x140066d7b  mov     rbx, [rcx+38h]
0x140066d7f  mov     [rcx+38h], rax
0x140066d83  or      r15d, 0FFFFFFFFh
0x140066d87  test    rbx, rbx
0x140066d8a  jz      short loc_140066DC3
0x140066d8c  mov     eax, r15d
0x140066d8f  lock xadd [rbx+8], eax
0x140066d94  add     eax, r15d
0x140066d97  jnz     short loc_140066DC3
0x140066d99  mov     rax, [rbx]
0x140066d9c  mov     rcx, rbx
0x140066d9f  mov     rax, [rax]
0x140066da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066da7  mov     eax, r15d
0x140066daa  lock xadd [rbx+0Ch], eax
0x140066daf  add     eax, r15d
0x140066db2  jnz     short loc_140066DC3
0x140066db4  mov     rax, [rbx]
0x140066db7  mov     rcx, rbx
0x140066dba  mov     rax, [rax+8]
0x140066dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066dc3  mov     qword ptr [rbp+57h+var_D0], rdi
0x140066dc7  lea     rdx, [rbp+57h+var_D0]
0x140066dcb  lea     rcx, [rbp+57h+var_80]
0x140066dcf  call    ScopeGuard__ScopeGuard__lambda_db7cd3f6d2f340133d3914887c407899___
0x140066dd4  nop
0x140066dd5  mov     rbx, [rdi]
0x140066dd8  xorps   xmm0, xmm0
0x140066ddb  movdqu  [rbp+57h+var_D0], xmm0
0x140066de0  mov     rdx, [rbx+28h]
0x140066de4  test    rdx, rdx
0x140066de7  jz      short loc_140066DFC
0x140066de9  mov     eax, [rdx+8]
0x140066dec  jmp     short loc_140066DF8
0x140066dee  lea     ecx, [rax+1]
0x140066df1  lock cmpxchg [rdx+8], ecx
0x140066df6  jz      short loc_140066E62
0x140066df8  test    eax, eax
0x140066dfa  jnz     short loc_140066DEE
0x140066dfc  mov     rsi, qword ptr [rbp+57h+var_D0]
0x140066e00  mov     rbx, qword ptr [rbp+57h+var_D0+8]
0x140066e04  test    rsi, rsi
0x140066e07  jz      short loc_140066E74
0x140066e09  mov     r14, [rdi]
0x140066e0c  lea     rcx, [rsi+58h]
0x140066e10  mov     rax, [rcx]
0x140066e13  lea     rdx, [rbp+57h+var_C0]
0x140066e17  mov     rax, [rax+30h]
0x140066e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066e20  mov     rcx, [rbp+57h+var_B8]
0x140066e24  mov     rax, [rcx]
0x140066e27  test    rax, rax
0x140066e2a  jz      short loc_140066E34
0x140066e2c  mov     [rax+50h], r14
0x140066e30  mov     rcx, [rbp+57h+var_B8]
0x140066e34  mov     qword ptr [r14+50h], 0
0x140066e3c  mov     rax, [rcx]
0x140066e3f  mov     [r14+58h], rax
0x140066e43  mov     [rcx], r14
0x140066e46  mov     rcx, [rbp+57h+var_C0]
0x140066e4a  test    rcx, rcx
0x140066e4d  jz      short loc_140066E5C
0x140066e4f  mov     rax, [rcx]
0x140066e52  mov     rax, [rax+18h]
0x140066e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066e5b  nop
0x140066e5c  lea     r8, [rsi+8]
0x140066e60  jmp     short loc_140066E77
0x140066e62  mov     rsi, [rbx+20h]
0x140066e66  mov     qword ptr [rbp+57h+var_D0], rsi
0x140066e6a  mov     rbx, [rbx+28h]
0x140066e6e  mov     qword ptr [rbp+57h+var_D0+8], rbx
0x140066e72  jmp     short loc_140066E04
0x140066e74  xor     r8d, r8d; pcbe
0x140066e77  mov     rdx, [rdi]; pv
0x140066e7a  lea     rcx, ?WorkCallback@WorkItemBase@Private@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x140066e81  call    cs:__imp_TrySubmitThreadpoolCallback
0x140066e87  test    eax, eax
0x140066e89  jz      loc_140066F3C
0x140066e8f  lea     rcx, [rbp+57h+var_80]; this
0x140066e93  call    ?Dismiss@ScopeGuard@@QEAAXXZ; ScopeGuard::Dismiss(void)
0x140066e98  nop
0x140066e99  test    rbx, rbx
0x140066e9c  jz      short loc_140066ED6
0x140066e9e  mov     eax, r15d
0x140066ea1  lock xadd [rbx+8], eax
0x140066ea6  add     eax, r15d
0x140066ea9  jnz     short loc_140066ED6
0x140066eab  mov     rax, [rbx]
0x140066eae  mov     rcx, rbx
0x140066eb1  mov     rax, [rax]
0x140066eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066eb9  mov     eax, r15d
0x140066ebc  lock xadd [rbx+0Ch], eax
0x140066ec1  add     eax, r15d
0x140066ec4  jnz     short loc_140066ED6
0x140066ec6  mov     rax, [rbx]
0x140066ec9  mov     rcx, rbx
0x140066ecc  mov     rax, [rax+8]
0x140066ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066ed5  nop
0x140066ed6  lea     rcx, [rbp+57h+var_80]; this
0x140066eda  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x140066edf  nop
0x140066ee0  mov     rbx, [rdi+8]
0x140066ee4  test    rbx, rbx
0x140066ee7  jz      short loc_140066F20
0x140066ee9  mov     eax, r15d
0x140066eec  lock xadd [rbx+8], eax
0x140066ef1  add     eax, r15d
0x140066ef4  jnz     short loc_140066F20
0x140066ef6  mov     rax, [rbx]
0x140066ef9  mov     rcx, rbx
0x140066efc  mov     rax, [rax]
0x140066eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066f04  mov     eax, r15d
0x140066f07  lock xadd [rbx+0Ch], eax
0x140066f0c  add     eax, r15d
0x140066f0f  jnz     short loc_140066F20
0x140066f11  mov     rax, [rbx]
0x140066f14  mov     rcx, rbx
0x140066f17  mov     rax, [rax+8]
0x140066f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066f20  mov     rcx, [rbp+57h+var_40]
0x140066f24  xor     rcx, rsp; StackCookie
0x140066f27  call    __security_check_cookie
0x140066f2c  add     rsp, 0C8h
0x140066f33  pop     r15
0x140066f35  pop     r14
0x140066f37  pop     rdi
0x140066f38  pop     rsi
0x140066f39  pop     rbx
0x140066f3a  pop     rbp
0x140066f3b  retn
0x140066f3c  call    cs:__imp_GetLastError
0x140066f42  nop
0x140066f43  mov     ebx, eax
0x140066f45  test    eax, eax
0x140066f47  jle     short loc_140066F52
0x140066f49  movzx   ebx, ax
0x140066f4c  or      ebx, 80070000h
0x140066f52  lea     rax, WPP_GLOBAL_Control
0x140066f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140066f60  cmp     rcx, rax
0x140066f63  jz      short loc_140066F83
0x140066f65  test    byte ptr [rcx+1Ch], 1
0x140066f69  jz      short loc_140066F83
0x140066f6b  mov     edx, 0Bh
0x140066f70  mov     r9d, ebx
0x140066f73  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x140066f7a  mov     rcx, [rcx+10h]
0x140066f7e  call    WPP_SF_d
0x140066f83  mov     edx, ebx; int
0x140066f85  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140066f89  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140066f8e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140066f95  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140066f99  call    _CxxThrowException_0
```
