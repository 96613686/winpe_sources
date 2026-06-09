# CLocalDisconnectPlugin::SetAuthenticationBuffer(uchar *,ulong)

- ea: `0x18005b4f0`
- end: `0x18005b5f5`
- name: `?SetAuthenticationBuffer@CLocalDisconnectPlugin@@UEAAJPEAEK@Z`
- size: `261`
- prototype: `int(CLocalDisconnectPlugin *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a74`
- `0x180026138`
- `0x18005b4f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18005b587`
- `msvcrt!memcpy_s` at `0x18005b587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b53a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b5af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b53a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b5af`

## string_xrefs

- `0x18005b560`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`
- `0x18005b5ba`: `shell\cpls\usercpl\taskflows\plugins\localdisconnectplugin.cpp`

## pseudocode

```c
__int64 __fastcall CLocalDisconnectPlugin::SetAuthenticationBuffer(
        CLocalDisconnectPlugin *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  void **v3; // rbx
  unsigned __int64 v4; // r15
  _BYTE *v5; // r9
  _DWORD *v6; // rdi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  void **v11; // r14
  int v12; // eax
  unsigned int v13; // esi
  void *v15; // rcx
  void *v16; // rcx
  __int64 v17; // rdx
  _BYTE *v18; // rax
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = (void **)((char *)this + 80);
  v4 = a3;
  v5 = (_BYTE *)*((_QWORD *)this + 10);
  v6 = (_DWORD *)((char *)this + 88);
  if ( v5 )
  {
    v9 = (unsigned int)*v6;
    v10 = v5;
    if ( *v6 )
    {
      do
      {
        *v10++ = 0;
        --v9;
      }
      while ( v9 );
      v11 = (void **)((char *)this + 80);
    }
    else
    {
      v11 = v3;
    }
    CoTaskMemFree(v5);
  }
  else
  {
    v11 = (void **)((char *)this + 80);
  }
  v12 = CTCoAllocPolicy::Alloc(this, 1u, v4, v3);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v15 = *v11;
    *v6 = v4;
    if ( memcpy_s(v15, v4, a2, v4) )
    {
      v16 = *v3;
      if ( *v3 )
      {
        v17 = (unsigned int)*v6;
        v18 = *v3;
        if ( *v6 )
        {
          do
          {
            *v18++ = 0;
            --v17;
          }
          while ( v17 );
        }
        CoTaskMemFree(v16);
      }
      *v3 = 0;
      *v6 = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
        (const char *)0x80004005LL,
        v19);
      return 2147500037LL;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\plugins\\localdisconnectplugin.cpp",
      (const char *)(unsigned int)v12,
      v19);
    return v13;
  }
}

```

## disassembly

```asm
0x18005b4f0  push    rbx
0x18005b4f2  push    rbp
0x18005b4f3  push    rsi
0x18005b4f4  push    rdi
0x18005b4f5  push    r12
0x18005b4f7  push    r14
0x18005b4f9  push    r15; int
0x18005b4fb  sub     rsp, 20h
0x18005b4ff  lea     rbx, [rcx+50h]
0x18005b503  mov     r15d, r8d
0x18005b506  mov     r9, [rbx]
0x18005b509  lea     rdi, [rcx+58h]
0x18005b50d  mov     r12, rdx
0x18005b510  mov     r14, rcx
0x18005b513  test    r9, r9
0x18005b516  jz      short loc_18005B542
0x18005b518  mov     ecx, [rdi]
0x18005b51a  mov     rax, r9
0x18005b51d  test    rcx, rcx
0x18005b520  jz      short loc_18005B534
0x18005b522  mov     byte ptr [rax], 0
0x18005b525  inc     rax
0x18005b528  sub     rcx, 1
0x18005b52c  jnz     short loc_18005B522
0x18005b52e  add     r14, 50h ; 'P'
0x18005b532  jmp     short loc_18005B537
0x18005b534  mov     r14, rbx
0x18005b537  mov     rcx, r9; pv
0x18005b53a  call    cs:__imp_CoTaskMemFree
0x18005b540  jmp     short loc_18005B545
0x18005b542  mov     r14, rbx
0x18005b545  mov     r9, rbx; void **
0x18005b548  mov     r8, r15; unsigned __int64
0x18005b54b  mov     edx, 1; unsigned int
0x18005b550  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18005b555  mov     esi, eax
0x18005b557  test    eax, eax
0x18005b559  jns     short loc_18005B578
0x18005b55b  mov     rcx, [rsp+58h]; this
0x18005b560  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b567  mov     r9d, eax; char *
0x18005b56a  mov     edx, 0C8h; void *
0x18005b56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b574  mov     eax, esi
0x18005b576  jmp     short loc_18005B5E6
0x18005b578  mov     rcx, [r14]; Destination
0x18005b57b  mov     r9, r15; SourceSize
0x18005b57e  mov     r8, r12; Source
0x18005b581  mov     [rdi], r15d
0x18005b584  mov     rdx, r15; DestinationSize
0x18005b587  call    cs:__imp_memcpy_s
0x18005b58d  test    eax, eax
0x18005b58f  jz      short loc_18005B5E4
0x18005b591  mov     rcx, [rbx]; pv
0x18005b594  test    rcx, rcx
0x18005b597  jz      short loc_18005B5B5
0x18005b599  mov     edx, [rdi]
0x18005b59b  mov     rax, rcx
0x18005b59e  test    rdx, rdx
0x18005b5a1  jz      short loc_18005B5AF
0x18005b5a3  mov     byte ptr [rax], 0
0x18005b5a6  inc     rax
0x18005b5a9  sub     rdx, 1
0x18005b5ad  jnz     short loc_18005B5A3
0x18005b5af  call    cs:__imp_CoTaskMemFree
0x18005b5b5  mov     rcx, [rsp+58h]; this
0x18005b5ba  lea     r8, aShellCplsUserc; "shell\\cpls\\usercpl\\taskflows\\plugin"...
0x18005b5c1  mov     qword ptr [rbx], 0
0x18005b5c8  mov     edx, 0D1h; void *
0x18005b5cd  mov     ebx, 80004005h
0x18005b5d2  mov     dword ptr [rdi], 0
0x18005b5d8  mov     r9d, ebx; char *
0x18005b5db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b5e0  mov     eax, ebx
0x18005b5e2  jmp     short loc_18005B5E6
0x18005b5e4  xor     eax, eax
0x18005b5e6  add     rsp, 20h
0x18005b5ea  pop     r15
0x18005b5ec  pop     r14
0x18005b5ee  pop     r12
0x18005b5f0  pop     rdi
0x18005b5f1  pop     rsi
0x18005b5f2  pop     rbp
0x18005b5f3  pop     rbx
0x18005b5f4  retn
```
