# Microsoft::BamoImpl::BamoProxyImpl::Release(void)

- ea: `0x18005fd50`
- end: `0x18005fea8`
- name: `?Release@BamoProxyImpl@BamoImpl@Microsoft@@UEAAKXZ`
- size: `344`
- prototype: `unsigned int __fastcall(Microsoft::BamoImpl::BamoProxyImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18005fd50`
- `0x18005feb0`
- `0x1800e3810`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fd82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fdb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fdf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fd82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fdb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fdf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::BamoImpl::BamoProxyImpl::Release(
        Microsoft::BamoImpl::BamoProxyImpl *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rbp
  Microsoft::BamoImpl::BufferingMessageCallHost *v8; // rbx
  const char *v9; // r9
  signed __int32 v10; // edi
  bool v11; // sf
  int v12; // edi
  __int64 v13; // rsi
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    v6 = *(_QWORD *)(v5 + 24);
    v7 = *(_QWORD *)(v6 + 32);
    if ( *(int *)(v7 + 8) <= 0 )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
      if ( v12 < 0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x33,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
          a4);
      if ( !v12 )
        (*(void (__fastcall **)(Microsoft::BamoImpl::BamoProxyImpl *))(*(_QWORD *)this + 24LL))(this);
    }
    else
    {
      v8 = 0;
      if ( *(_DWORD *)(v7 + 184) != GetCurrentThreadId() )
      {
        v8 = (Microsoft::BamoImpl::BufferingMessageCallHost *)v6;
        if ( v6 )
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 24LL))(*(_QWORD *)(v7 + 16));
        *(_DWORD *)(v7 + 184) = GetCurrentThreadId();
      }
      v10 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
      v11 = v10 - 1 < 0;
      v12 = v10 - 1;
      if ( v11 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x33,
          (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoImplObject.inl",
          v9);
      if ( !v12 )
        (*(void (__fastcall **)(Microsoft::BamoImpl::BamoProxyImpl *))(*(_QWORD *)this + 24LL))(this);
      if ( v8 )
      {
        v13 = *((_QWORD *)v8 + 4);
        if ( *(_DWORD *)(v13 + 184) != GetCurrentThreadId() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x9A3,
            (unsigned int)"d:\\os\\tools\\BamoCodegen\\Inc\\BamoConnection.inl",
            v14);
        *(_DWORD *)(v13 + 184) = 0;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 16) + 32LL))(*(_QWORD *)(v13 + 16));
      }
      if ( v8 )
        Microsoft::BamoImpl::BufferingMessageCallHost::Release(v8);
    }
  }
  else
  {
    return Microsoft::BamoImpl::BufferingMessageCallHost::Release(this);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005fd50  push    rbx
0x18005fd52  push    rbp
0x18005fd53  push    rsi
0x18005fd54  push    rdi
0x18005fd55  sub     rsp, 28h
0x18005fd59  mov     rsi, rcx
0x18005fd5c  mov     rdi, [rcx+10h]
0x18005fd60  test    rdi, rdi
0x18005fd63  jz      loc_18005FE64
0x18005fd69  mov     rdi, [rdi+18h]
0x18005fd6d  mov     rbp, [rdi+20h]
0x18005fd71  cmp     dword ptr [rbp+8], 0
0x18005fd75  jle     loc_18005FE45
0x18005fd7b  xor     ebx, ebx
0x18005fd7d  mov     [rsp+48h+arg_0], rbx
0x18005fd82  call    cs:__imp_GetCurrentThreadId
0x18005fd88  cmp     [rbp+0B8h], eax
0x18005fd8e  jz      short loc_18005FDBD
0x18005fd90  mov     rbx, rdi
0x18005fd93  mov     [rsp+48h+arg_0], rbx
0x18005fd98  test    rdi, rdi
0x18005fd9b  jz      short loc_18005FDA1
0x18005fd9d  lock inc dword ptr [rdi+8]
0x18005fda1  mov     rcx, [rbp+10h]
0x18005fda5  mov     rax, [rcx]
0x18005fda8  mov     rax, [rax+18h]
0x18005fdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdb1  call    cs:__imp_GetCurrentThreadId
0x18005fdb7  mov     [rbp+0B8h], eax
0x18005fdbd  or      edi, 0FFFFFFFFh
0x18005fdc0  lock xadd [rsi+8], edi
0x18005fdc5  add     edi, 0FFFFFFFFh
0x18005fdc8  sets    al
0x18005fdcb  mov     rcx, [rsp+48h]; this
0x18005fdd0  test    al, al
0x18005fdd2  jnz     loc_18005FE84
0x18005fdd8  test    edi, edi
0x18005fdda  jnz     short loc_18005FDEC
0x18005fddc  mov     rax, [rsi]
0x18005fddf  mov     rcx, rsi
0x18005fde2  mov     rax, [rax+18h]
0x18005fde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdeb  nop
0x18005fdec  test    rbx, rbx
0x18005fdef  jz      short loc_18005FE2C
0x18005fdf1  mov     rsi, [rbx+20h]
0x18005fdf5  call    cs:__imp_GetCurrentThreadId
0x18005fdfb  cmp     [rsi+0B8h], eax
0x18005fe01  setnz   al
0x18005fe04  mov     rcx, [rsp+48h]; this
0x18005fe09  test    al, al
0x18005fe0b  jnz     loc_18005FE96
0x18005fe11  mov     dword ptr [rsi+0B8h], 0
0x18005fe1b  mov     rcx, [rsi+10h]
0x18005fe1f  mov     rax, [rcx]
0x18005fe22  mov     rax, [rax+20h]
0x18005fe26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe2b  nop
0x18005fe2c  test    rbx, rbx
0x18005fe2f  jz      short loc_18005FE3A
0x18005fe31  mov     rcx, rbx; this
0x18005fe34  call    ?Release@BufferingMessageCallHost@BamoImpl@Microsoft@@UEAAKXZ; Microsoft::BamoImpl::BufferingMessageCallHost::Release(void)
0x18005fe39  nop
0x18005fe3a  mov     eax, edi
0x18005fe3c  add     rsp, 28h
0x18005fe40  pop     rdi
0x18005fe41  pop     rsi
0x18005fe42  pop     rbp
0x18005fe43  pop     rbx
0x18005fe44  retn
0x18005fe45  or      edi, 0FFFFFFFFh
0x18005fe48  lock xadd [rcx+8], edi
0x18005fe4d  sub     edi, 1
0x18005fe50  js      short loc_18005FE6D
0x18005fe52  test    edi, edi
0x18005fe54  jnz     short loc_18005FE3A
0x18005fe56  mov     rax, [rcx]
0x18005fe59  mov     rax, [rax+18h]
0x18005fe5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe62  jmp     short loc_18005FE3A
0x18005fe64  call    ?Release@BufferingMessageCallHost@BamoImpl@Microsoft@@UEAAKXZ; Microsoft::BamoImpl::BufferingMessageCallHost::Release(void)
0x18005fe69  mov     edi, eax
0x18005fe6b  jmp     short loc_18005FE3A
0x18005fe6d  mov     rcx, [rsp+48h]; this
0x18005fe72  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18005fe79  mov     edx, 33h ; '3'; void *
0x18005fe7e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005fe84  lea     r8, aDOsToolsBamoco_5; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoIm"...
0x18005fe8b  mov     edx, 33h ; '3'; void *
0x18005fe90  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005fe96  lea     r8, aDOsToolsBamoco_9; "d:\\os\\tools\\BamoCodegen\\Inc\\BamoCo"...
0x18005fe9d  mov     edx, 9A3h; void *
0x18005fea2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
