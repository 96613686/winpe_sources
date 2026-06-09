# CRegistryChangeListener_CreateInstance(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *,IRegistryChangeListener * *)

- ea: `0x180073e80`
- end: `0x180073fb0`
- name: `?CRegistryChangeListener_CreateInstance@@YAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3PEAPEAUIRegistryChangeListener@@@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180060d60`

## callees

- `0x180002ae4`
- `0x18000dafc`
- `0x180073e08`
- `0x180073e80`
- `0x1800740f4`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x180073f43`
- `SHLWAPI!__imp_QISearch` at `0x180073f43`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180073f5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180073f5d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073f74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073f74`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener_CreateInstance(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        void **ppv)
{
  _DWORD *v7; // rax
  void *v8; // rdx
  __int64 v9; // r9
  void *v10; // rbx
  int v11; // edi
  struct _TP_WAIT *v12; // rcx
  struct _TP_WORK *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-18h]

  *ppv = 0;
  v7 = operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v7;
  if ( v7 )
  {
    v7[4] = 1;
    *(_QWORD *)v7 = &CRegistryChangeListener::`vftable'{for `IOleCommandTarget'};
    *((_QWORD *)v7 + 1) = &CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'};
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 5) = 0;
    v7[12] = 0;
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 10) = 0;
    v7[22] = 0;
    _InterlockedIncrement(&g_cLocks);
    v11 = CRegistryChangeListener::_Initialize((__int64)v7, v8, a2, v9, v15, a5);
    if ( v11 < 0
      || (v11 = QISearch(
                  v10,
                  &`CRegistryChangeListener::QueryInterface'::`2'::qit,
                  &GUID_077b0abd_69ee_4ce7_aa79_a3044499881e,
                  ppv),
          v11 < 0) )
    {
      v12 = (struct _TP_WAIT *)*((_QWORD *)v10 + 5);
      if ( v12 )
        SetThreadpoolWait(v12, 0, 0);
      v13 = (struct _TP_WORK *)*((_QWORD *)v10 + 8);
      *((_QWORD *)v10 + 7) = 0;
      if ( v13 )
        SubmitThreadpoolWork(v13);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) == 1 )
    {
      CRegistryChangeListener::~CRegistryChangeListener((CRegistryChangeListener *)v10);
      operator delete(v10);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180073e80  mov     [rsp+arg_0], rbx
0x180073e85  mov     [rsp+arg_8], rsi
0x180073e8a  push    rdi
0x180073e8b  sub     rsp, 30h
0x180073e8f  mov     rsi, [rsp+38h+ppv]
0x180073e94  mov     rdi, rdx
0x180073e97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180073e9e  mov     ecx, 60h ; '`'; unsigned __int64
0x180073ea3  mov     qword ptr [rsi], 0
0x180073eaa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180073eaf  mov     rbx, rax
0x180073eb2  test    rax, rax
0x180073eb5  jz      loc_180073F99
0x180073ebb  lea     rax, ??_7CRegistryChangeListener@@6BIOleCommandTarget@@@; const CRegistryChangeListener::`vftable'{for `IOleCommandTarget'}
0x180073ec2  mov     dword ptr [rbx+10h], 1
0x180073ec9  mov     [rbx], rax
0x180073ecc  lea     rax, ??_7CRegistryChangeListener@@6BIRegistryChangeListener@@@; const CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'}
0x180073ed3  mov     [rbx+8], rax
0x180073ed7  mov     qword ptr [rbx+18h], 0
0x180073edf  mov     qword ptr [rbx+20h], 0
0x180073ee7  mov     qword ptr [rbx+28h], 0
0x180073eef  mov     dword ptr [rbx+30h], 0
0x180073ef6  mov     qword ptr [rbx+40h], 0
0x180073efe  mov     qword ptr [rbx+50h], 0
0x180073f06  mov     dword ptr [rbx+58h], 0
0x180073f0d  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x180073f14  mov     rax, [rsp+38h+arg_20]
0x180073f19  mov     r8, rdi
0x180073f1c  mov     rcx, rbx
0x180073f1f  mov     [rsp+38h+var_10], rax
0x180073f24  call    ?_Initialize@CRegistryChangeListener@@QEAAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3@Z; CRegistryChangeListener::_Initialize(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *)
0x180073f29  mov     edi, eax
0x180073f2b  test    eax, eax
0x180073f2d  js      short loc_180073F4F
0x180073f2f  mov     r9, rsi; ppv
0x180073f32  lea     r8, _GUID_077b0abd_69ee_4ce7_aa79_a3044499881e; riid
0x180073f39  lea     rdx, ?qit@?1??QueryInterface@CRegistryChangeListener@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x180073f40  mov     rcx, rbx; that
0x180073f43  call    cs:__imp_QISearch
0x180073f49  mov     edi, eax
0x180073f4b  test    eax, eax
0x180073f4d  jns     short loc_180073F7A
0x180073f4f  mov     rcx, [rbx+28h]; pwa
0x180073f53  test    rcx, rcx
0x180073f56  jz      short loc_180073F63
0x180073f58  xor     r8d, r8d; pftTimeout
0x180073f5b  xor     edx, edx; h
0x180073f5d  call    cs:__imp_SetThreadpoolWait
0x180073f63  mov     rcx, [rbx+40h]; pwk
0x180073f67  mov     qword ptr [rbx+38h], 0
0x180073f6f  test    rcx, rcx
0x180073f72  jz      short loc_180073F7A
0x180073f74  call    cs:__imp_SubmitThreadpoolWork
0x180073f7a  or      eax, 0FFFFFFFFh
0x180073f7d  lock xadd [rbx+10h], eax
0x180073f82  cmp     eax, 1
0x180073f85  jnz     short loc_180073F9E
0x180073f87  mov     rcx, rbx; this
0x180073f8a  call    ??1CRegistryChangeListener@@AEAA@XZ; CRegistryChangeListener::~CRegistryChangeListener(void)
0x180073f8f  mov     rcx, rbx; lpMem
0x180073f92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180073f97  jmp     short loc_180073F9E
0x180073f99  mov     edi, 8007000Eh
0x180073f9e  mov     rbx, [rsp+38h+arg_0]
0x180073fa3  mov     eax, edi
0x180073fa5  mov     rsi, [rsp+38h+arg_8]
0x180073faa  add     rsp, 30h
0x180073fae  pop     rdi
0x180073faf  retn
```
