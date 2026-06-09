# TdhpGetTraceEventInfo(ulong,ushort,_GUID *,_EVENT_DESCRIPTOR const *,_TRACE_EVENT_INFO *,ulong *)

- ea: `0x180004ca0`
- end: `0x180004fa0`
- name: `?TdhpGetTraceEventInfo@@YAKKGPEAU_GUID@@PEBU_EVENT_DESCRIPTOR@@PEAU_TRACE_EVENT_INFO@@PEAK@Z`
- size: `768`
- prototype: `__int64 __fastcall(unsigned int, __int64, struct _GUID *, const struct _EVENT_DESCRIPTOR *, struct _TRACE_EVENT_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024920`

## callees

- `0x180004ca0`
- `0x180004fb0`
- `0x1800059e8`
- `0x180006660`
- `0x180007720`
- `0x180023b05`
- `0x180024318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004d2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004d93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004d2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004d93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004e0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004e63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004ec6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004e0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004e63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004ec6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ecf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ecf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall TdhpGetTraceEventInfo(
        unsigned int a1,
        __int64 a2,
        struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4,
        struct _TRACE_EVENT_INFO *a5,
        unsigned int *a6)
{
  unsigned __int8 v7; // r10
  unsigned int v8; // r11d
  __int64 v10; // rax
  char v11; // r10
  RTL_SRWLOCK *v12; // rsi
  RTL_SRWLOCK *v13; // rdi
  struct TDH_MOF_INFO *v14; // r14
  unsigned int i; // ebp
  _DWORD *Ptr; // rcx
  RTL_SRWLOCK *v17; // r15
  void *TraceEventInfoFromMofInfo; // rsi
  size_t v19; // rax
  struct _TRACE_EVENT_INFO *v20; // rcx
  unsigned int v21; // ebx
  unsigned __int8 v22; // al
  unsigned int j; // r8d
  __int64 v24; // rcx
  char v25; // al
  struct TDH_MOF_INFO *v27; // rdi
  HANDLE v28; // rax
  RTL_SRWLOCK *v29; // r8
  HANDLE ProcessHeap; // rax
  size_t Size[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v33; // [rsp+A0h] [rbp+18h] BYREF

  v7 = 0;
  Size[0] = 0;
  v8 = 0;
  v33 = 0;
  do
  {
    v10 = v8 + 3;
    v11 = __ROL1__(
            *((_BYTE *)&a3->Data1 + v8 + 2)
          ^ __ROL1__(*((_BYTE *)&a3->Data1 + v8 + 1) ^ __ROL1__(*((_BYTE *)&a3->Data1 + v8) ^ v7, 3), 3),
            3);
    v8 += 4;
    v7 = __ROL1__(*((_BYTE *)&a3->Data1 + v10) ^ v11, 3);
  }
  while ( v8 < 0x10 );
  v12 = (RTL_SRWLOCK *)((char *)g_TdhCache + 64 * (unsigned __int64)v7);
LABEL_4:
  AcquireSRWLockShared(v12);
  v13 = 0;
  v14 = 0;
  for ( i = 0; i < 7; ++i )
  {
    Ptr = v12[i + 1].Ptr;
    v17 = &v12[i];
    if ( Ptr )
    {
      if ( Ptr[2] == a3->Data1
        && Ptr[3] == *(_DWORD *)&a3->Data2
        && Ptr[4] == *(_DWORD *)a3->Data4
        && Ptr[5] == *(_DWORD *)&a3->Data4[4] )
      {
        v13 = (RTL_SRWLOCK *)v12[i + 1].Ptr;
        break;
      }
    }
    else
    {
      if ( !v14 )
      {
        v14 = TdhpCacheEntryAllocate(a3);
        if ( !v14 )
        {
LABEL_28:
          ReleaseSRWLockShared(v12);
          AcquireSRWLockExclusive(v12);
          v27 = TdhpFindOrAddEntry((struct TDH_CACHE_BUCKET *)v12, a3, &v33);
          if ( !v27 && !v33 )
            v27 = TdhpCacheEvictAndAddEntry((struct TDH_CACHE_BUCKET *)v12, a3);
          ReleaseSRWLockExclusive(v12);
          if ( !v27 )
            return 8;
          goto LABEL_4;
        }
      }
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&v17[1], (signed __int64)v14, 0) )
      {
        v13 = (RTL_SRWLOCK *)v14;
        goto LABEL_16;
      }
      if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)((char *)v17[1].Ptr + 8), a3) )
      {
        v13 = v29;
        break;
      }
    }
  }
  if ( v13 != (RTL_SRWLOCK *)v14 && v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14);
  }
LABEL_16:
  if ( !v13 )
    goto LABEL_28;
  AcquireSRWLockShared(v13);
  TraceEventInfoFromMofInfo = (void *)TdhpGetTraceEventInfoFromMofInfo(
                                        a1,
                                        (__int64)a4,
                                        (__int64)Size,
                                        1,
                                        (__int64)Size + 4);
  if ( TraceEventInfoFromMofInfo )
  {
    v19 = LODWORD(Size[0]);
    if ( LODWORD(Size[0]) <= *a6 && (v20 = a5) != 0 )
    {
      *a6 = Size[0];
      memcpy_0(v20, TraceEventInfoFromMofInfo, v19);
      v21 = 0;
    }
    else
    {
      *a6 = Size[0];
      v21 = 122;
    }
  }
  else
  {
    v21 = 1168;
  }
  ReleaseSRWLockShared(v13);
  v22 = 0;
  for ( j = 0; j < 0x10; j += 4 )
  {
    v24 = j + 3;
    v25 = __ROL1__(
            *((_BYTE *)&v13[1].Ptr + j + 2)
          ^ __ROL1__(*((_BYTE *)&v13[1].Ptr + j + 1) ^ __ROL1__(*((_BYTE *)&v13[1].Ptr + j) ^ v22, 3), 3),
            3);
    v22 = __ROL1__(*((_BYTE *)&v13[1].Ptr + v24) ^ v25, 3);
  }
  ReleaseSRWLockShared((PSRWLOCK)g_TdhCache + 8 * (unsigned __int64)v22);
  if ( HIDWORD(Size[0]) )
  {
    if ( TraceEventInfoFromMofInfo )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, TraceEventInfoFromMofInfo);
    }
  }
  return v21;
}

```

## disassembly

```asm
0x180004ca0  mov     rax, rsp
0x180004ca3  mov     [rax+10h], rbx
0x180004ca7  mov     [rax+8], ecx
0x180004caa  push    rbp
0x180004cab  push    rsi
0x180004cac  push    rdi
0x180004cad  push    r12
0x180004caf  push    r13
0x180004cb1  push    r14
0x180004cb3  push    r15
0x180004cb5  sub     rsp, 50h
0x180004cb9  xor     r15d, r15d
0x180004cbc  mov     r12, r9
0x180004cbf  mov     [rax-44h], r15d
0x180004cc3  xor     r10b, r10b
0x180004cc6  mov     [rax-48h], r15d
0x180004cca  mov     r11d, r15d
0x180004ccd  mov     [rax+18h], r15d
0x180004cd1  mov     rbx, r8
0x180004cd4  movzx   r13d, dx
0x180004cd8  nop     dword ptr [rax+rax+00000000h]
0x180004ce0  mov     eax, r11d
0x180004ce3  xor     r10b, [rax+r8]
0x180004ce7  lea     eax, [r11+1]
0x180004ceb  rol     r10b, 3
0x180004cef  xor     r10b, [rax+r8]
0x180004cf3  lea     eax, [r11+2]
0x180004cf7  rol     r10b, 3
0x180004cfb  xor     r10b, [rax+r8]
0x180004cff  lea     eax, [r11+3]
0x180004d03  rol     r10b, 3
0x180004d07  add     r11d, 4
0x180004d0b  xor     r10b, [rax+r8]
0x180004d0f  rol     r10b, 3
0x180004d13  cmp     r11d, 10h
0x180004d17  jb      short loc_180004CE0
0x180004d19  movzx   esi, r10b
0x180004d1d  shl     rsi, 6
0x180004d21  add     rsi, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180004d28  mov     rcx, rsi; SRWLock
0x180004d2b  call    cs:__imp_AcquireSRWLockShared
0x180004d31  mov     rdi, r15
0x180004d34  mov     r14, r15
0x180004d37  mov     ebp, r15d
0x180004d3a  cmp     ebp, 7
0x180004d3d  jnb     short loc_180004D79
0x180004d3f  mov     eax, ebp
0x180004d41  mov     rcx, [rsi+rax*8+8]
0x180004d46  lea     r15, [rsi+rax*8]
0x180004d4a  test    rcx, rcx
0x180004d4d  jz      loc_180004EA6
0x180004d53  mov     eax, [rbx]
0x180004d55  cmp     [rcx+8], eax
0x180004d58  jnz     short loc_180004D62
0x180004d5a  mov     eax, [rbx+4]
0x180004d5d  cmp     [rcx+0Ch], eax
0x180004d60  jz      short loc_180004D66
0x180004d62  inc     ebp
0x180004d64  jmp     short loc_180004D3A
0x180004d66  mov     eax, [rbx+8]
0x180004d69  cmp     [rcx+10h], eax
0x180004d6c  jnz     short loc_180004D62
0x180004d6e  mov     eax, [rbx+0Ch]
0x180004d71  cmp     [rcx+14h], eax
0x180004d74  jnz     short loc_180004D62
0x180004d76  mov     rdi, rcx
0x180004d79  cmp     rdi, r14
0x180004d7c  jz      short loc_180004D87
0x180004d7e  test    r14, r14
0x180004d81  jnz     loc_180004F87
0x180004d87  test    rdi, rdi
0x180004d8a  jz      loc_180004EC3
0x180004d90  mov     rcx, rdi; SRWLock
0x180004d93  call    cs:__imp_AcquireSRWLockShared
0x180004d99  mov     ecx, [rsp+88h+arg_0]; unsigned int
0x180004da0  lea     rax, [rsp+88h+Size+4]
0x180004da5  mov     [rsp+88h+var_50], rax; __int64
0x180004daa  mov     r9, rbx
0x180004dad  lea     rax, [rsp+88h+Size]
0x180004db2  mov     [rsp+88h+var_58], 1; int
0x180004dba  mov     [rsp+88h+var_60], rax; __int64
0x180004dbf  mov     r8, rdi
0x180004dc2  movzx   edx, r13w
0x180004dc6  mov     [rsp+88h+var_68], r12; __int64
0x180004dcb  call    TdhpGetTraceEventInfoFromMofInfo
0x180004dd0  mov     rsi, rax
0x180004dd3  test    rax, rax
0x180004dd6  jz      loc_180004F75
0x180004ddc  mov     rdx, [rsp+88h+arg_28]
0x180004de4  mov     eax, dword ptr [rsp+88h+Size]
0x180004de8  cmp     eax, [rdx]
0x180004dea  ja      short loc_180004DFD
0x180004dec  mov     rcx, [rsp+88h+arg_20]; void *
0x180004df4  test    rcx, rcx
0x180004df7  jnz     loc_180004E8E
0x180004dfd  mov     [rdx], eax
0x180004dff  mov     ebx, 7Ah ; 'z'
0x180004e04  xor     r15d, r15d
0x180004e07  mov     rcx, rdi; SRWLock
0x180004e0a  call    cs:__imp_ReleaseSRWLockShared
0x180004e10  xor     al, al
0x180004e12  mov     r8d, r15d
0x180004e15  nop     word ptr [rax+rax+00000000h]
0x180004e20  mov     ecx, r8d
0x180004e23  xor     al, [rcx+rdi+8]
0x180004e27  lea     ecx, [r8+1]
0x180004e2b  rol     al, 3
0x180004e2e  xor     al, [rcx+rdi+8]
0x180004e32  lea     ecx, [r8+2]
0x180004e36  rol     al, 3
0x180004e39  xor     al, [rcx+rdi+8]
0x180004e3d  lea     ecx, [r8+3]
0x180004e41  rol     al, 3
0x180004e44  add     r8d, 4
0x180004e48  xor     al, [rcx+rdi+8]
0x180004e4c  rol     al, 3
0x180004e4f  cmp     r8d, 10h
0x180004e53  jb      short loc_180004E20
0x180004e55  movzx   ecx, al
0x180004e58  shl     rcx, 6
0x180004e5c  add     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; SRWLock
0x180004e63  call    cs:__imp_ReleaseSRWLockShared
0x180004e69  cmp     dword ptr [rsp+88h+Size+4], 0
0x180004e6e  jnz     loc_180004F29
0x180004e74  mov     eax, ebx
0x180004e76  mov     rbx, [rsp+88h+arg_8]
0x180004e7e  add     rsp, 50h
0x180004e82  pop     r15
0x180004e84  pop     r14
0x180004e86  pop     r13
0x180004e88  pop     r12
0x180004e8a  pop     rdi
0x180004e8b  pop     rsi
0x180004e8c  pop     rbp
0x180004e8d  retn
0x180004e8e  mov     [rdx], eax
0x180004e90  mov     r8, rax; Size
0x180004e93  mov     rdx, rsi; Src
0x180004e96  call    memcpy_0
0x180004e9b  xor     r15d, r15d
0x180004e9e  mov     ebx, r15d
0x180004ea1  jmp     loc_180004E07
0x180004ea6  test    r14, r14
0x180004ea9  jnz     loc_180004F4B
0x180004eaf  mov     rcx, rbx; struct _GUID *
0x180004eb2  call    ?TdhpCacheEntryAllocate@@YAPEAUTDH_MOF_INFO@@PEBU_GUID@@@Z; TdhpCacheEntryAllocate(_GUID const *)
0x180004eb7  mov     r14, rax
0x180004eba  test    rax, rax
0x180004ebd  jnz     loc_180004F4B
0x180004ec3  mov     rcx, rsi; SRWLock
0x180004ec6  call    cs:__imp_ReleaseSRWLockShared
0x180004ecc  mov     rcx, rsi; SRWLock
0x180004ecf  call    cs:__imp_AcquireSRWLockExclusive
0x180004ed5  lea     r8, [rsp+88h+arg_10]; unsigned int *
0x180004edd  mov     rdx, rbx; struct _GUID *
0x180004ee0  mov     rcx, rsi; struct TDH_CACHE_BUCKET *
0x180004ee3  call    ?TdhpFindOrAddEntry@@YAPEAUTDH_MOF_INFO@@PEAUTDH_CACHE_BUCKET@@PEBU_GUID@@PEAK@Z; TdhpFindOrAddEntry(TDH_CACHE_BUCKET *,_GUID const *,ulong *)
0x180004ee8  mov     rdi, rax
0x180004eeb  test    rax, rax
0x180004eee  jnz     short loc_180004F07
0x180004ef0  cmp     [rsp+88h+arg_10], eax
0x180004ef7  jnz     short loc_180004F07
0x180004ef9  mov     rdx, rbx; struct _GUID *
0x180004efc  mov     rcx, rsi; struct TDH_CACHE_BUCKET *
0x180004eff  call    ?TdhpCacheEvictAndAddEntry@@YAPEAUTDH_MOF_INFO@@PEAUTDH_CACHE_BUCKET@@PEBU_GUID@@@Z; TdhpCacheEvictAndAddEntry(TDH_CACHE_BUCKET *,_GUID const *)
0x180004f04  mov     rdi, rax
0x180004f07  mov     rcx, rsi; SRWLock
0x180004f0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f10  mov     r15d, 0
0x180004f16  test    rdi, rdi
0x180004f19  jnz     loc_180004D28
0x180004f1f  mov     eax, 8
0x180004f24  jmp     loc_180004E76
0x180004f29  test    rsi, rsi
0x180004f2c  jz      loc_180004E74
0x180004f32  call    cs:__imp_GetProcessHeap
0x180004f38  mov     r8, rsi; lpMem
0x180004f3b  xor     edx, edx; dwFlags
0x180004f3d  mov     rcx, rax; hHeap
0x180004f40  call    cs:__imp_HeapFree
0x180004f46  jmp     loc_180004E74
0x180004f4b  xor     eax, eax
0x180004f4d  lock cmpxchg [r15+8], r14
0x180004f53  jz      short loc_180004F7F
0x180004f55  mov     r8, [r15+8]
0x180004f59  mov     rdx, rbx; struct _GUID *
0x180004f5c  lea     rcx, [r8+8]; struct _GUID *
0x180004f60  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004f65  test    eax, eax
0x180004f67  jz      loc_180004D62
0x180004f6d  mov     rdi, r8
0x180004f70  jmp     loc_180004D79
0x180004f75  mov     ebx, 490h
0x180004f7a  jmp     loc_180004E04
0x180004f7f  mov     rdi, r14
0x180004f82  jmp     loc_180004D87
0x180004f87  call    cs:__imp_GetProcessHeap
0x180004f8d  mov     r8, r14; lpMem
0x180004f90  xor     edx, edx; dwFlags
0x180004f92  mov     rcx, rax; hHeap
0x180004f95  call    cs:__imp_HeapFree
0x180004f9b  jmp     loc_180004D87
```
