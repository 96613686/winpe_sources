# Get_getcontenttype(DAV_RESOURCE *,DAV_PROPERTY *,LIVE_ADDITIONAL_DATA *)

- ea: `0x18000b3b0`
- end: `0x18000b501`
- name: `?Get_getcontenttype@@YAJPEAVDAV_RESOURCE@@PEAVDAV_PROPERTY@@PEAULIVE_ADDITIONAL_DATA@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct DAV_RESOURCE *, struct DAV_PROPERTY *, struct LIVE_ADDITIONAL_DATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b3b0`
- `0x18000bb20`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b4da`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b4da`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b3f7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000b3f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b4d0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b4d0`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000b4a9`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000b4a9`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000b3df`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000b3df`

## pseudocode

```c
__int64 __fastcall Get_getcontenttype(
        struct DAV_RESOURCE *a1,
        struct DAV_PROPERTY *a2,
        struct LIVE_ADDITIONAL_DATA *a3)
{
  __int64 v6; // rax
  __int64 (__fastcall ***v7)(_QWORD, void *); // rax
  STATIC_META_STORED_CONTEXT *v8; // rbx
  const unsigned __int16 *v9; // rax
  const char **v10; // rdx
  int v12; // [rsp+30h] [rbp-39h] BYREF
  int v13; // [rsp+34h] [rbp-35h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v15; // [rsp+58h] [rbp-11h]
  _BYTE v16[56]; // [rsp+70h] [rbp+7h] BYREF

  STRA::STRA((STRA *)v16);
  v12 = 0;
  v13 = 0;
  STRU::STRU((STRU *)v14);
  if ( (*(_BYTE *)a3 & 0x10) == 0 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 5) + 160LL))(*((_QWORD *)a1 + 5));
    v7 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    v8 = (STATIC_META_STORED_CONTEXT *)(**v7)(v7, g_DavModuleContext);
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct DAV_RESOURCE *))(*(_QWORD *)a1 + 16LL))(a1);
    if ( STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(v8, v9, (struct STRA *)v16, &v12, &v13) >= 0 )
    {
      v10 = (const char **)v16;
      if ( (v12 || (v10 = (const char **)(((unsigned __int64)v8 + 312) & -(__int64)(*((_DWORD *)v8 + 93) != 0))) != 0)
        && (int)STRU::CopyA((STRU *)v14, v10[4]) >= 0 )
      {
        (*(void (__fastcall **)(struct DAV_PROPERTY *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, v15, 0, 0);
      }
    }
  }
  STRU::~STRU((STRU *)v14);
  STRA::~STRA((STRA *)v16);
  return 0;
}

```

## disassembly

```asm
0x18000b3b0  mov     [rsp-8+arg_10], rbx
0x18000b3b5  push    rbp
0x18000b3b6  push    rsi
0x18000b3b7  push    rdi
0x18000b3b8  lea     rbp, [rsp-47h]
0x18000b3bd  sub     rsp, 0B0h
0x18000b3c4  mov     rax, cs:__security_cookie
0x18000b3cb  xor     rax, rsp
0x18000b3ce  mov     [rbp+57h+var_18], rax
0x18000b3d2  mov     rsi, rcx
0x18000b3d5  mov     rbx, r8
0x18000b3d8  lea     rcx, [rbp+57h+var_50]
0x18000b3dc  mov     rdi, rdx
0x18000b3df  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000b3e5  lea     rcx, [rbp+57h+var_88]
0x18000b3e9  mov     [rbp+57h+var_90], 0
0x18000b3f0  mov     [rbp+57h+var_8C], 0
0x18000b3f7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000b3fd  test    byte ptr [rbx], 10h
0x18000b400  jnz     loc_18000B4CC
0x18000b406  mov     rcx, [rsi+28h]
0x18000b40a  mov     rax, [rcx]
0x18000b40d  mov     rax, [rax+0A0h]
0x18000b414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b419  mov     rdx, rax
0x18000b41c  mov     rcx, [rax]
0x18000b41f  mov     rax, [rcx+18h]
0x18000b423  mov     rcx, rdx
0x18000b426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b42b  mov     rcx, rax
0x18000b42e  mov     rdx, [rax]
0x18000b431  mov     rax, [rdx]
0x18000b434  mov     rdx, cs:?g_DavModuleContext@@3PEAXEA; void * g_DavModuleContext
0x18000b43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b440  mov     rdx, [rsi]
0x18000b443  mov     rbx, rax
0x18000b446  mov     rcx, rsi
0x18000b449  mov     rax, [rdx+10h]
0x18000b44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b452  mov     rdx, rax; unsigned __int16 *
0x18000b455  lea     r9, [rbp+57h+var_90]; int *
0x18000b459  lea     rax, [rbp+57h+var_8C]
0x18000b45d  mov     rcx, rbx; this
0x18000b460  lea     r8, [rbp+57h+var_50]; struct STRA *
0x18000b464  mov     [rsp+0C0h+var_A0], rax; int *
0x18000b469  call    ?SelectMimeMappingForFileExt@STATIC_META_STORED_CONTEXT@@QEAAJPEBGPEAVSTRA@@PEAH2@Z; STATIC_META_STORED_CONTEXT::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)
0x18000b46e  test    eax, eax
0x18000b470  js      short loc_18000B4CC
0x18000b472  mov     r8d, [rbp+57h+var_90]
0x18000b476  lea     rdx, [rbp+57h+var_50]
0x18000b47a  test    r8d, r8d
0x18000b47d  jnz     short loc_18000B4A1
0x18000b47f  mov     eax, [rbx+174h]
0x18000b485  lea     rcx, [rbx+138h]
0x18000b48c  neg     eax
0x18000b48e  lea     eax, [r8+1]
0x18000b492  sbb     rdx, rdx
0x18000b495  and     rdx, rcx
0x18000b498  cmovnz  r8d, eax
0x18000b49c  test    r8d, r8d
0x18000b49f  jz      short loc_18000B4CC
0x18000b4a1  mov     rdx, [rdx+20h]
0x18000b4a5  lea     rcx, [rbp+57h+var_88]
0x18000b4a9  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000b4af  test    eax, eax
0x18000b4b1  js      short loc_18000B4CC
0x18000b4b3  mov     rax, [rdi]
0x18000b4b6  xor     r9d, r9d
0x18000b4b9  mov     rdx, [rbp+57h+var_68]
0x18000b4bd  xor     r8d, r8d
0x18000b4c0  mov     rcx, rdi
0x18000b4c3  mov     rax, [rax+40h]
0x18000b4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cc  lea     rcx, [rbp+57h+var_88]
0x18000b4d0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b4d6  lea     rcx, [rbp+57h+var_50]
0x18000b4da  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000b4e0  xor     eax, eax
0x18000b4e2  mov     rcx, [rbp+57h+var_18]
0x18000b4e6  xor     rcx, rsp; StackCookie
0x18000b4e9  call    __security_check_cookie
0x18000b4ee  mov     rbx, [rsp+0C0h+arg_10]
0x18000b4f6  add     rsp, 0B0h
0x18000b4fd  pop     rdi
0x18000b4fe  pop     rsi
0x18000b4ff  pop     rbp
0x18000b500  retn
```
