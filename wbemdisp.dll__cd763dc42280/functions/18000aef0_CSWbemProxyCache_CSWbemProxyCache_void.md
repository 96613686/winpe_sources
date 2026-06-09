# CSWbemProxyCache::~CSWbemProxyCache(void)

- ea: `0x18000aef0`
- end: `0x18000b001`
- name: `??1CSWbemProxyCache@@UEAA@XZ`
- size: `273`
- prototype: `void __fastcall(CSWbemProxyCache *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000aeb0`

## callees

- `0x18000aef0`
- `0x18000b008`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000afda`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afe5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afda`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afe5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af87`

## pseudocode

```c
void __fastcall CSWbemProxyCache::~CSWbemProxyCache(CSWbemProxyCache *this)
{
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rcx
  struct _COAUTHIDENTITY *v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  *(_QWORD *)this = &CSWbemProxyCache::`vftable';
  CSWbemProxyCache::ClearCredentials(this);
  v2 = (OLECHAR *)*((_QWORD *)this + 37);
  if ( v2 )
    SysFreeString(v2);
  v3 = (OLECHAR *)*((_QWORD *)this + 36);
  if ( v3 )
    SysFreeString(v3);
  v4 = (struct _COAUTHIDENTITY *)*((_QWORD *)this + 35);
  if ( v4 )
  {
    WbemFreeAuthIdentity(v4);
    *((_QWORD *)this + 35) = 0;
  }
  v5 = 0;
  v6 = 0;
  do
  {
    _mm_lfence();
    v7 = *(_QWORD *)((char *)this + v6 + 56);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *(_QWORD *)((char *)this + v6 + 56) = 0;
    }
    v8 = *(_QWORD *)((char *)this + v6 + 64);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *(_QWORD *)((char *)this + v6 + 64) = 0;
    }
    v9 = *(_QWORD *)((char *)this + v6 + 72);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)((char *)this + v6 + 72) = 0;
    }
    v10 = *(_QWORD *)((char *)this + v6 + 80);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *(_QWORD *)((char *)this + v6 + 80) = 0;
    }
    ++v5;
    v6 += 32;
  }
  while ( v5 != 7 );
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000aef0  push    rbx
0x18000aef2  push    rbp
0x18000aef3  push    rsi
0x18000aef4  push    rdi
0x18000aef5  sub     rsp, 28h
0x18000aef9  mov     rdi, rcx
0x18000aefc  lea     rax, ??_7CSWbemProxyCache@@6B@; const CSWbemProxyCache::`vftable'
0x18000af03  mov     [rcx], rax
0x18000af06  call    ?ClearCredentials@CSWbemProxyCache@@AEAAXXZ; CSWbemProxyCache::ClearCredentials(void)
0x18000af0b  mov     rcx, [rdi+128h]; bstrString
0x18000af12  test    rcx, rcx
0x18000af15  jnz     loc_18000AFDA
0x18000af1b  mov     rcx, [rdi+120h]; bstrString
0x18000af22  test    rcx, rcx
0x18000af25  jnz     loc_18000AFE5
0x18000af2b  mov     rcx, [rdi+118h]; pv
0x18000af32  xor     ebp, ebp
0x18000af34  test    rcx, rcx
0x18000af37  jnz     loc_18000AFF0
0x18000af3d  mov     rsi, rbp
0x18000af40  mov     rbx, rbp
0x18000af43  lfence
0x18000af46  mov     rcx, [rdi+rbx+38h]
0x18000af4b  test    rcx, rcx
0x18000af4e  jnz     short loc_18000AF8E
0x18000af50  mov     rcx, [rdi+rbx+40h]
0x18000af55  test    rcx, rcx
0x18000af58  jnz     short loc_18000AFA1
0x18000af5a  mov     rcx, [rdi+rbx+48h]
0x18000af5f  test    rcx, rcx
0x18000af62  jnz     short loc_18000AFB4
0x18000af64  mov     rcx, [rdi+rbx+50h]
0x18000af69  test    rcx, rcx
0x18000af6c  jnz     short loc_18000AFC7
0x18000af6e  inc     rsi
0x18000af71  add     rbx, 20h ; ' '
0x18000af75  cmp     rsi, 7
0x18000af79  jnz     short loc_18000AF43
0x18000af7b  lea     rcx, [rdi+10h]
0x18000af7f  add     rsp, 28h
0x18000af83  pop     rdi
0x18000af84  pop     rsi
0x18000af85  pop     rbp
0x18000af86  pop     rbx
0x18000af87  jmp     cs:__imp_DeleteCriticalSection
0x18000af8e  mov     rax, [rcx]
0x18000af91  mov     rax, [rax+10h]
0x18000af95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9a  mov     [rdi+rbx+38h], rbp
0x18000af9f  jmp     short loc_18000AF50
0x18000afa1  mov     rax, [rcx]
0x18000afa4  mov     rax, [rax+10h]
0x18000afa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afad  mov     [rdi+rbx+40h], rbp
0x18000afb2  jmp     short loc_18000AF5A
0x18000afb4  mov     rax, [rcx]
0x18000afb7  mov     rax, [rax+10h]
0x18000afbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afc0  mov     [rdi+rbx+48h], rbp
0x18000afc5  jmp     short loc_18000AF64
0x18000afc7  mov     rax, [rcx]
0x18000afca  mov     rax, [rax+10h]
0x18000afce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd3  mov     [rdi+rbx+50h], rbp
0x18000afd8  jmp     short loc_18000AF6E
0x18000afda  call    cs:__imp_SysFreeString
0x18000afe0  jmp     loc_18000AF1B
0x18000afe5  call    cs:__imp_SysFreeString
0x18000afeb  jmp     loc_18000AF2B
0x18000aff0  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x18000aff5  mov     [rdi+118h], rbp
0x18000affc  jmp     loc_18000AF3D
```
