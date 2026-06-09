# Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(uint,uint,void const *,void const *,uint)

- ea: `0x18005ee50`
- end: `0x18005f004`
- name: `?OnItemMessage@ConnectionIndirector@BamoImpl@Microsoft@@UEAAJIIPEBX0I@Z`
- size: `436`
- prototype: `__int64 __fastcall(Microsoft::BamoImpl::ConnectionIndirector *__hidden this, unsigned int, unsigned int, const void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005ee50`
- `0x1800e34bc`
- `0x1800e3810`
- `0x18010d62c`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ee7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005eea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ef0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ee7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005eea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ef0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::ConnectionIndirector::OnItemMessage(
        Microsoft::BamoImpl::ConnectionIndirector *this,
        int a2,
        int a3,
        const void *a4,
        const void *a5,
        unsigned int a6)
{
  char *v10; // rbx
  __int64 v11; // rbp
  const char *v12; // r9
  __int64 v13; // rsi
  _DWORD *i; // rax
  unsigned int v15; // edi
  __int64 v16; // rsi
  const char *v17; // r9
  signed __int32 v18; // edx
  bool v19; // sf
  signed __int32 v20; // edx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v10 = 0;
  v11 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v11 + 184) != GetCurrentThreadId() )
  {
    v10 = (char *)this - 16;
    _InterlockedIncrement((volatile signed __int32 *)this - 2);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 16) + 24LL))(*(_QWORD *)(v11 + 16));
    *(_DWORD *)(v11 + 184) = GetCurrentThreadId();
  }
  v13 = *((_QWORD *)this + 2);
  if ( *(_QWORD *)(v13 + 64) )
  {
    for ( i = *(_DWORD **)(v13 + 192); i != *(_DWORD **)(v13 + 200); ++i )
    {
      if ( *i == a3 )
        goto LABEL_18;
    }
    if ( a4 )
    {
      *(_DWORD *)(v13 + 32) = a2;
      v15 = (*(__int64 (__fastcall **)(const void *, const void *, _QWORD))(*(_QWORD *)a4 + 32LL))(a4, a5, a6);
      *(_DWORD *)(v13 + 32) = 0;
    }
    else
    {
      v22 = Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(
              (Microsoft::BamoImpl::BaseBamoConnectionImpl *)v13,
              -2018375668,
              0);
      v15 = v22;
      if ( v22 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76E,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
          (const char *)(unsigned int)v22,
          v23);
    }
  }
  else
  {
LABEL_18:
    v15 = 0;
  }
  if ( v10 )
  {
    v16 = *((_QWORD *)v10 + 4);
    if ( *(_DWORD *)(v16 + 184) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x9A3,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
        v17);
    *(_DWORD *)(v16 + 184) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 16) + 32LL))(*(_QWORD *)(v16 + 16));
  }
  if ( v10 )
  {
    v18 = _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF);
    v19 = v18 - 1 < 0;
    v20 = v18 - 1;
    if ( v19 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x33,
        (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
        v12);
    if ( !v20 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 24LL))(v10);
  }
  return v15;
}

```

## disassembly

```asm
0x18005ee50  mov     [rsp+arg_8], rbx
0x18005ee55  mov     [rsp+arg_10], rbp
0x18005ee5a  push    rsi
0x18005ee5b  push    rdi
0x18005ee5c  push    r12
0x18005ee5e  push    r14
0x18005ee60  push    r15; int
0x18005ee62  sub     rsp, 20h
0x18005ee66  mov     r14, r9
0x18005ee69  mov     r15d, r8d
0x18005ee6c  mov     r12d, edx
0x18005ee6f  mov     rsi, rcx
0x18005ee72  xor     ebx, ebx
0x18005ee74  mov     [rsp+48h+arg_0], rbx
0x18005ee79  mov     rbp, [rcx+10h]
0x18005ee7d  call    cs:__imp_GetCurrentThreadId
0x18005ee83  cmp     [rbp+0B8h], eax
0x18005ee89  jz      short loc_18005EEB4
0x18005ee8b  lea     rbx, [rsi-10h]
0x18005ee8f  mov     [rsp+48h+arg_0], rbx
0x18005ee94  lock inc dword ptr [rsi-8]
0x18005ee98  mov     rcx, [rbp+10h]
0x18005ee9c  mov     rax, [rcx]
0x18005ee9f  mov     rax, [rax+18h]
0x18005eea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eea8  call    cs:__imp_GetCurrentThreadId
0x18005eeae  mov     [rbp+0B8h], eax
0x18005eeb4  mov     rsi, [rsi+10h]
0x18005eeb8  cmp     qword ptr [rsi+40h], 0
0x18005eebd  jz      loc_18005EFA1
0x18005eec3  mov     rax, [rsi+0C0h]
0x18005eeca  cmp     rax, [rsi+0C8h]
0x18005eed1  jnz     loc_18005EF93
0x18005eed7  test    r14, r14
0x18005eeda  jz      loc_18005EFA8
0x18005eee0  mov     [rsi+20h], r12d
0x18005eee4  mov     rax, [r14]
0x18005eee7  mov     r8d, [rsp+48h+arg_28]
0x18005eeec  mov     rdx, [rsp+48h+arg_20]
0x18005eef1  mov     rcx, r14
0x18005eef4  mov     rax, [rax+20h]
0x18005eef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eefd  mov     edi, eax
0x18005eeff  mov     dword ptr [rsi+20h], 0
0x18005ef06  test    rbx, rbx
0x18005ef09  jz      short loc_18005EF46
0x18005ef0b  mov     rsi, [rbx+20h]
0x18005ef0f  call    cs:__imp_GetCurrentThreadId
0x18005ef15  cmp     [rsi+0B8h], eax
0x18005ef1b  setnz   al
0x18005ef1e  mov     rcx, [rsp+48h]; this
0x18005ef23  test    al, al
0x18005ef25  jnz     loc_18005EFE0
0x18005ef2b  mov     dword ptr [rsi+0B8h], 0
0x18005ef35  mov     rcx, [rsi+10h]
0x18005ef39  mov     rax, [rcx]
0x18005ef3c  mov     rax, [rax+20h]
0x18005ef40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef45  nop
0x18005ef46  test    rbx, rbx
0x18005ef49  jz      short loc_18005EF7A
0x18005ef4b  or      edx, 0FFFFFFFFh
0x18005ef4e  lock xadd [rbx+8], edx
0x18005ef53  add     edx, 0FFFFFFFFh
0x18005ef56  sets    al
0x18005ef59  mov     rcx, [rsp+48h]; this
0x18005ef5e  test    al, al
0x18005ef60  jnz     loc_18005EFF2
0x18005ef66  test    edx, edx
0x18005ef68  jnz     short loc_18005EF7A
0x18005ef6a  mov     rcx, [rbx]
0x18005ef6d  mov     rax, [rcx+18h]
0x18005ef71  mov     rcx, rbx
0x18005ef74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef79  nop
0x18005ef7a  mov     eax, edi
0x18005ef7c  mov     rbx, [rsp+48h+arg_8]
0x18005ef81  mov     rbp, [rsp+48h+arg_10]
0x18005ef86  add     rsp, 20h
0x18005ef8a  pop     r15
0x18005ef8c  pop     r14
0x18005ef8e  pop     r12
0x18005ef90  pop     rdi
0x18005ef91  pop     rsi
0x18005ef92  retn
0x18005ef93  cmp     [rax], r15d
0x18005ef96  jz      short loc_18005EFA1
0x18005ef98  add     rax, 4
0x18005ef9c  jmp     loc_18005EECA
0x18005efa1  xor     edi, edi
0x18005efa3  jmp     loc_18005EF06
0x18005efa8  xor     r8d, r8d; unsigned int
0x18005efab  mov     edx, 87B2080Ch; int
0x18005efb0  mov     rcx, rsi; this
0x18005efb3  call    ?TrackError@BaseBamoConnectionImpl@BamoImpl@Microsoft@@QEAAJJI@Z; Microsoft::BamoImpl::BaseBamoConnectionImpl::TrackError(long,uint)
0x18005efb8  mov     edi, eax
0x18005efba  test    eax, eax
0x18005efbc  jns     loc_18005EF06
0x18005efc2  mov     rcx, [rsp+48h]; this
0x18005efc7  mov     r9d, eax; char *
0x18005efca  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18005efd1  mov     edx, 76Eh; void *
0x18005efd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005efdb  jmp     loc_18005EF06
0x18005efe0  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18005efe7  mov     edx, 9A3h; void *
0x18005efec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005eff2  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18005eff9  mov     edx, 33h ; '3'; void *
0x18005effe  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
