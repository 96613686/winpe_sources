# DBLockManager::AreLocksHeld(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *,int *)

- ea: `0x180050d00`
- end: `0x180050eaf`
- name: `?AreLocksHeld@DBLockManager@@UEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@PEAH@Z`
- size: `431`
- prototype: `__int64 __fastcall(DBLockManager *__hidden this, const struct CallerId *, unsigned int, const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *, const enum DB_LOCK_TYPE *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180050d00`
- `0x18006f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050e35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050e35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050d4f`

## string_xrefs

- `0x180050d60`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180050e14`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180050e52`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180050e75`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBLockManager::AreLocksHeld(
        DBLockManager *this,
        const struct CallerId *a2,
        unsigned int a3,
        const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *a4,
        const enum DB_LOCK_TYPE *a5,
        int *a6)
{
  int v10; // ebp
  __int64 v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rax
  int v14; // r15d
  __int64 v15; // rcx
  unsigned int i; // eax
  __int64 v17; // rdx
  int v18; // eax
  _DWORD *v19; // rax
  _DWORD *v20; // rdx
  bool v21; // zf
  __int64 v23; // [rsp+60h] [rbp+8h]
  int v24; // [rsp+70h] [rbp+18h]

  if ( !a3 )
  {
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
      1098);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v10 = 0;
    v12 = 0;
    goto LABEL_23;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v24 = 0;
  do
  {
    v13 = 4 * v11;
    v14 = *(_DWORD *)((char *)a4 + v13);
    v23 = v13;
    if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        661);
    if ( v14 == 2147483640 )
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        664);
    for ( i = 0; i < *((_DWORD *)this + 14); ++i )
    {
      v17 = 56LL * i;
      v15 = *((_QWORD *)this + 8);
      if ( v14 == *(_DWORD *)(v17 + v15) )
      {
        v15 += v17;
        v18 = *(_DWORD *)(v15 + 4);
        if ( v18 == 1 )
        {
          if ( *(_DWORD *)a2 == *(_DWORD *)(v15 + 8) && *((_DWORD *)a2 + 1) == *(_DWORD *)(v15 + 12) )
LABEL_19:
            ++v12;
        }
        else if ( v18 == 2 && !*(_DWORD *)((char *)a5 + v23) )
        {
          v19 = *(_DWORD **)(v15 + 24);
          v20 = *(_DWORD **)(v15 + 32);
          while ( v19 != v20 )
          {
            if ( v19[2] )
            {
              v15 = *(unsigned int *)a2;
              if ( *v19 == (_DWORD)v15 )
              {
                v15 = *((unsigned int *)a2 + 1);
                if ( v19[1] == (_DWORD)v15 )
                  goto LABEL_19;
              }
            }
            v19 += 3;
          }
        }
        break;
      }
    }
    v11 = (unsigned int)(v24 + 1);
    v24 = v11;
  }
  while ( (unsigned int)v11 < a3 );
  v21 = a3 == v12;
  if ( a3 < v12 )
  {
    Log_AssertionEvent(
      v15,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
      1117);
LABEL_23:
    v21 = a3 == v12;
  }
  LOBYTE(v10) = v21;
  *a6 = v10;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return 0;
}

```

## disassembly

```asm
0x180050d00  push    rbx
0x180050d02  push    rbp
0x180050d03  push    rsi
0x180050d04  push    rdi
0x180050d05  push    r12
0x180050d07  push    r13
0x180050d09  push    r14
0x180050d0b  sub     rsp, 20h
0x180050d0f  mov     r13, r9
0x180050d12  mov     esi, r8d
0x180050d15  mov     r12, rdx
0x180050d18  mov     rdi, rcx
0x180050d1b  test    r8d, r8d
0x180050d1e  jz      loc_180050E4C
0x180050d24  add     rcx, 8; lpCriticalSection
0x180050d28  mov     [rsp+58h+arg_8], r15
0x180050d2d  call    cs:__imp_EnterCriticalSection
0x180050d33  xor     ebp, ebp
0x180050d35  mov     eax, ebp
0x180050d37  mov     r14d, ebp
0x180050d3a  mov     [rsp+58h+arg_10], eax
0x180050d3e  lea     rax, ds:0[rax*4]
0x180050d46  mov     r15d, [rax+r13]
0x180050d4a  mov     [rsp+58h+arg_0], rax
0x180050d4f  call    cs:__imp_GetCurrentThreadId
0x180050d55  cmp     [rdi+18h], eax
0x180050d58  jz      short loc_180050D6C
0x180050d5a  mov     r8d, 295h
0x180050d60  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050d67  call    Log_AssertionEvent
0x180050d6c  cmp     r15d, 7FFFFFF8h
0x180050d73  jz      loc_180050E6F
0x180050d79  mov     r8d, [rdi+38h]
0x180050d7d  mov     eax, ebp
0x180050d7f  nop
0x180050d80  cmp     eax, r8d
0x180050d83  jnb     short loc_180050DF2
0x180050d85  mov     ecx, eax
0x180050d87  imul    rdx, rcx, 38h ; '8'
0x180050d8b  mov     rcx, [rdi+40h]
0x180050d8f  cmp     r15d, [rdx+rcx]
0x180050d93  jz      short loc_180050D99
0x180050d95  inc     eax
0x180050d97  jmp     short loc_180050D80
0x180050d99  add     rcx, rdx
0x180050d9c  mov     eax, [rcx+4]
0x180050d9f  cmp     eax, 1
0x180050da2  jz      loc_180050E86
0x180050da8  cmp     eax, 2
0x180050dab  jnz     short loc_180050DF2
0x180050dad  mov     rax, [rsp+58h+arg_0]
0x180050db2  mov     rdx, [rsp+58h+arg_20]
0x180050dba  cmp     [rdx+rax], ebp
0x180050dbd  jnz     short loc_180050DF2
0x180050dbf  mov     rax, [rcx+18h]
0x180050dc3  mov     rdx, [rcx+20h]
0x180050dc7  cmp     rax, rdx
0x180050dca  jz      short loc_180050DF2
0x180050dcc  cmp     [rax+8], ebp
0x180050dcf  jz      loc_180050EA6
0x180050dd5  mov     ecx, [r12]
0x180050dd9  cmp     [rax], ecx
0x180050ddb  jnz     loc_180050EA6
0x180050de1  mov     ecx, [r12+4]
0x180050de6  cmp     [rax+4], ecx
0x180050de9  jnz     loc_180050EA6
0x180050def  inc     r14d
0x180050df2  mov     eax, [rsp+58h+arg_10]
0x180050df6  inc     eax
0x180050df8  mov     [rsp+58h+arg_10], eax
0x180050dfc  cmp     eax, esi
0x180050dfe  jb      loc_180050D3E
0x180050e04  mov     r15, [rsp+58h+arg_8]
0x180050e09  cmp     esi, r14d
0x180050e0c  jnb     short loc_180050E23
0x180050e0e  mov     r8d, 45Dh
0x180050e14  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050e1b  call    Log_AssertionEvent
0x180050e20  cmp     esi, r14d
0x180050e23  mov     rax, [rsp+58h+arg_28]
0x180050e2b  lea     rcx, [rdi+8]; lpCriticalSection
0x180050e2f  setz    bpl
0x180050e33  mov     [rax], ebp
0x180050e35  call    cs:__imp_LeaveCriticalSection
0x180050e3b  xor     eax, eax
0x180050e3d  add     rsp, 20h
0x180050e41  pop     r14
0x180050e43  pop     r13
0x180050e45  pop     r12
0x180050e47  pop     rdi
0x180050e48  pop     rsi
0x180050e49  pop     rbp
0x180050e4a  pop     rbx
0x180050e4b  retn
0x180050e4c  mov     r8d, 44Ah
0x180050e52  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050e59  call    Log_AssertionEvent
0x180050e5e  lea     rcx, [rdi+8]; lpCriticalSection
0x180050e62  call    cs:__imp_EnterCriticalSection
0x180050e68  xor     ebp, ebp
0x180050e6a  mov     r14d, ebp
0x180050e6d  jmp     short loc_180050E20
0x180050e6f  mov     r8d, 298h
0x180050e75  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050e7c  call    Log_AssertionEvent
0x180050e81  jmp     loc_180050D79
0x180050e86  mov     eax, [rcx+8]
0x180050e89  cmp     [r12], eax
0x180050e8d  jnz     loc_180050DF2
0x180050e93  mov     eax, [rcx+0Ch]
0x180050e96  cmp     [r12+4], eax
0x180050e9b  jnz     loc_180050DF2
0x180050ea1  jmp     loc_180050DEF
0x180050ea6  add     rax, 0Ch
0x180050eaa  jmp     loc_180050DC7
```
