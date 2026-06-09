# EvtCreateRenderContext

- ea: `0x180005c60`
- end: `0x180005f10`
- name: `EvtCreateRenderContext`
- size: `688`
- prototype: `EVT_HANDLE __stdcall(DWORD ValuePathsCount, LPCWSTR *ValuePaths, DWORD Flags)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180005c60`
- `0x180006aec`
- `0x180006df4`
- `0x180007010`
- `0x180007180`
- `0x180008bb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d4b`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
EVT_HANDLE __stdcall EvtCreateRenderContext(DWORD ValuePathsCount, LPCWSTR *ValuePaths, DWORD Flags)
{
  const wchar_t **v4; // rsi
  Object *v6; // rdi
  DWORD v7; // ebx
  ValuesRenderContext *v8; // r14
  __int64 v9; // rcx
  unsigned __int64 v10; // rsi
  __int64 v11; // rdx
  Object *v12; // rcx
  void *v13; // rbx
  __int64 i; // rdx
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  int j; // r12d
  unsigned __int64 v19; // r15
  int *v20; // r13
  ValuesRenderContext *v21; // rax
  int v22; // esi
  void *v23; // rax
  RTL_SRWLOCK v24; // r9
  int k; // edx
  __int64 v26; // rcx
  __int64 v27; // rax
  _QWORD v28[11]; // [rsp+20h] [rbp-58h] BYREF

  v4 = ValuePaths;
  v6 = 0;
  LastErrInfo::Reset(*(LastErrInfo **)&ValuePathsCount);
  if ( !Flags )
  {
    if ( v4 && ValuePathsCount )
    {
      for ( i = 0; (unsigned int)i < ValuePathsCount; i = (unsigned int)(i + 1) )
      {
        v16 = v4[i];
        if ( !v16 )
          goto LABEL_3;
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
        if ( !v17 )
          goto LABEL_3;
      }
      goto LABEL_23;
    }
LABEL_3:
    v7 = 87;
    goto LABEL_7;
  }
  if ( Flags - 1 >= 2 || v4 )
    goto LABEL_3;
LABEL_23:
  v28[0] = &g_objectTable;
  AcquireSRWLockExclusive(&g_objectTable);
  for ( j = 0; j < 24; ++j )
  {
    v19 = 24LL * j;
    if ( *(RTL_SRWLOCK *)((char *)&g_objectTable + v19 + 16) )
    {
      v20 = &dword_18004B3AC[v19 / 4];
    }
    else
    {
      v22 = 64 << j;
      v23 = MIDL_user_allocate(saturated_mul(64 << j, 0x10u));
      v24.Ptr = v23;
      if ( !v23 )
        break;
      for ( k = 0; k < v22 - 1; *((_DWORD *)v23 + 2 * v26 + 2) = k )
      {
        v26 = 2LL * (unsigned int)k;
        *((_BYTE *)v23 + 8 * v26) = 0;
        ++k;
      }
      v27 = 2LL * k;
      *((_BYTE *)v24.Ptr + 8 * v27) = 0;
      *((_DWORD *)v24.Ptr + 2 * v27 + 2) = -1;
      v20 = &dword_18004B3AC[v19 / 4];
      dword_18004B3AC[v19 / 4] = 0;
      *(_DWORD *)((char *)&g_objectTable + v19 + 8) = v22;
      *(RTL_SRWLOCK *)((char *)&g_objectTable + v19 + 16) = v24;
      v4 = ValuePaths;
    }
    if ( *v20 != -1 )
    {
      v21 = (ValuesRenderContext *)MIDL_user_allocate(0x38u);
      v28[1] = v21;
      if ( v21 )
        v8 = ValuesRenderContext::ValuesRenderContext(v21, v4, ValuePathsCount, Flags);
      else
        v8 = 0;
      if ( v8 )
      {
        v9 = *v20;
        v10 = (unsigned int)(j << 24) | (unsigned __int64)(((_DWORD)v9 + 1) & 0xFFFFFF);
        v9 *= 2;
        v11 = qword_18004B398[v19 / 8 + 1];
        *v20 = *(_DWORD *)(v11 + 8 * v9 + 8);
        *(_BYTE *)(v11 + 8 * v9) = 1;
        *(_QWORD *)(v11 + 8 * v9 + 8) = v8;
        ++*(_DWORD *)((char *)&g_objectTable + v19 + 24);
        ReleaseSRWLockExclusive(&g_objectTable);
        *((_QWORD *)v8 + 2) = v10;
        _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
        _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
        v6 = v8;
        v28[0] = 0;
        EvtHandleRef::~EvtHandleRef((EvtHandleRef *)v28);
        v7 = 0;
        goto LABEL_7;
      }
      break;
    }
  }
  ReleaseSRWLockExclusive(&g_objectTable);
  v7 = 14;
LABEL_7:
  SetLastError(v7);
  if ( v7 || !v6 )
  {
    v13 = 0;
  }
  else
  {
    v12 = v6;
    v13 = (void *)*((_QWORD *)v6 + 2);
    v6 = 0;
    *((_BYTE *)v12 + 29) = 1;
  }
  if ( v6 )
    Object::HandleRelease(v6);
  return v13;
}

```

## disassembly

```asm
0x180005c60  mov     [rsp+arg_10], r8d
0x180005c65  mov     [rsp+arg_8], rdx
0x180005c6a  push    rbx
0x180005c6b  push    rsi
0x180005c6c  push    rdi
0x180005c6d  push    r12
0x180005c6f  push    r13
0x180005c71  push    r14
0x180005c73  push    r15
0x180005c75  sub     rsp, 40h
0x180005c79  mov     ebx, r8d
0x180005c7c  mov     rsi, rdx
0x180005c7f  mov     r14d, ecx
0x180005c82  xor     edi, edi
0x180005c84  mov     [rsp+78h+arg_18], rdi
0x180005c8c  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180005c91  mov     eax, ebx
0x180005c93  test    ebx, ebx
0x180005c95  jz      loc_180005D93
0x180005c9b  sub     eax, 1
0x180005c9e  jz      loc_180005DDC
0x180005ca4  cmp     eax, 1
0x180005ca7  jz      loc_180005DDC
0x180005cad  mov     ebx, 57h ; 'W'
0x180005cb2  jmp     loc_180005D49
0x180005cb7  mov     r9d, [rsp+78h+arg_10]; unsigned int
0x180005cbf  mov     r8d, r14d; unsigned int
0x180005cc2  mov     rdx, rsi; wchar_t **
0x180005cc5  mov     rcx, rax; this
0x180005cc8  call    ??0ValuesRenderContext@@QEAA@PEAPEB_WKK@Z; ValuesRenderContext::ValuesRenderContext(wchar_t const * *,ulong,ulong)
0x180005ccd  mov     r14, rax
0x180005cd0  lea     rdx, [rbx+10h]
0x180005cd4  add     rdx, r15
0x180005cd7  test    r14, r14
0x180005cda  jz      loc_180005E54
0x180005ce0  movsxd  rcx, dword ptr [r13+0]
0x180005ce4  lea     esi, [rcx+1]
0x180005ce7  and     esi, 0FFFFFFh
0x180005ced  shl     r12d, 18h
0x180005cf1  mov     eax, r12d
0x180005cf4  or      rsi, rax
0x180005cf7  add     rcx, rcx
0x180005cfa  mov     rdx, [rdx]
0x180005cfd  mov     eax, [rdx+rcx*8+8]
0x180005d01  mov     [r13+0], eax
0x180005d05  mov     byte ptr [rdx+rcx*8], 1
0x180005d09  mov     [rdx+rcx*8+8], r14
0x180005d0e  inc     dword ptr [r15+rbx+18h]
0x180005d13  mov     rcx, rbx; SRWLock
0x180005d16  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d1c  mov     [r14+10h], rsi
0x180005d20  lock inc dword ptr [r14+8]
0x180005d25  lock inc dword ptr [r14+18h]
0x180005d2a  mov     rax, rdi
0x180005d2d  mov     rdi, r14
0x180005d30  mov     [rsp+78h+arg_18], r14
0x180005d38  mov     [rsp+78h+var_58], rax
0x180005d3d  lea     rcx, [rsp+78h+var_58]; this
0x180005d42  call    ??1EvtHandleRef@@QEAA@XZ; EvtHandleRef::~EvtHandleRef(void)
0x180005d47  xor     ebx, ebx
0x180005d49  mov     ecx, ebx; dwErrCode
0x180005d4b  call    cs:__imp_SetLastError
0x180005d51  test    ebx, ebx
0x180005d53  jnz     loc_180005E67
0x180005d59  test    rdi, rdi
0x180005d5c  jz      loc_180005E67
0x180005d62  mov     rcx, rdi
0x180005d65  mov     rbx, [rdi+10h]
0x180005d69  xor     edi, edi
0x180005d6b  mov     eax, 1
0x180005d70  xchg    al, [rcx+1Dh]
0x180005d73  test    rdi, rdi
0x180005d76  jz      short loc_180005D80
0x180005d78  mov     rcx, rdi; this
0x180005d7b  call    ?HandleRelease@Object@@AEAAXXZ; Object::HandleRelease(void)
0x180005d80  mov     rax, rbx
0x180005d83  add     rsp, 40h
0x180005d87  pop     r15
0x180005d89  pop     r14
0x180005d8b  pop     r13
0x180005d8d  pop     r12
0x180005d8f  pop     rdi
0x180005d90  pop     rsi
0x180005d91  pop     rbx
0x180005d92  retn
0x180005d93  test    rsi, rsi
0x180005d96  jz      loc_180005CAD
0x180005d9c  test    r14d, r14d
0x180005d9f  jz      loc_180005CAD
0x180005da5  xor     edx, edx
0x180005da7  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005dae  xchg    ax, ax
0x180005db0  cmp     edx, r14d
0x180005db3  jnb     short loc_180005DEC
0x180005db5  mov     rcx, [rsi+rdx*8]
0x180005db9  test    rcx, rcx
0x180005dbc  jz      loc_180005CAD
0x180005dc2  mov     rax, r13
0x180005dc5  inc     rax
0x180005dc8  cmp     word ptr [rcx+rax*2], 0
0x180005dcd  jnz     short loc_180005DC5
0x180005dcf  test    rax, rax
0x180005dd2  jz      loc_180005CAD
0x180005dd8  inc     edx
0x180005dda  jmp     short loc_180005DB0
0x180005ddc  test    rsi, rsi
0x180005ddf  jnz     loc_180005CAD
0x180005de5  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005dec  lea     rbx, ?g_objectTable@@3VObjectTable@@A; ObjectTable g_objectTable
0x180005df3  mov     [rsp+78h+var_58], rbx
0x180005df8  mov     rcx, rbx; SRWLock
0x180005dfb  call    cs:__imp_AcquireSRWLockExclusive
0x180005e01  nop
0x180005e02  xor     r12d, r12d
0x180005e05  cmp     r12d, 18h
0x180005e09  jge     short loc_180005E54
0x180005e0b  movsxd  rax, r12d
0x180005e0e  lea     rcx, [rax+rax*2]
0x180005e12  lea     r15, ds:0[rcx*8]
0x180005e1a  cmp     qword ptr [r15+rbx+10h], 0
0x180005e20  jz      short loc_180005E6E
0x180005e22  lea     r13, [rbx+1Ch]
0x180005e26  add     r13, r15
0x180005e29  cmp     dword ptr [r13+0], 0FFFFFFFFh
0x180005e2e  jz      loc_180005EEC
0x180005e34  mov     ecx, 38h ; '8'; size
0x180005e39  call    MIDL_user_allocate
0x180005e3e  mov     [rsp+78h+var_50], rax
0x180005e43  test    rax, rax
0x180005e46  jnz     loc_180005CB7
0x180005e4c  xor     r14d, r14d
0x180005e4f  jmp     loc_180005CD0
0x180005e54  mov     rcx, rbx; SRWLock
0x180005e57  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e5d  mov     ebx, 0Eh
0x180005e62  jmp     loc_180005D49
0x180005e67  xor     ebx, ebx
0x180005e69  jmp     loc_180005D73
0x180005e6e  mov     ecx, r12d
0x180005e71  mov     esi, 40h ; '@'
0x180005e76  shl     esi, cl
0x180005e78  movsxd  rcx, esi
0x180005e7b  mov     eax, 10h
0x180005e80  mul     rcx
0x180005e83  cmovb   rax, r13
0x180005e87  mov     rcx, rax; size
0x180005e8a  call    MIDL_user_allocate
0x180005e8f  mov     r9, rax
0x180005e92  test    rax, rax
0x180005e95  jz      short loc_180005E54
0x180005e97  xor     edx, edx
0x180005e99  lea     r8d, [rsi-1]
0x180005e9d  test    r8d, r8d
0x180005ea0  jle     short loc_180005EB6
0x180005ea2  mov     ecx, edx
0x180005ea4  add     rcx, rcx
0x180005ea7  mov     byte ptr [rax+rcx*8], 0
0x180005eab  inc     edx
0x180005ead  mov     [rax+rcx*8+8], edx
0x180005eb1  cmp     edx, r8d
0x180005eb4  jl      short loc_180005EA2
0x180005eb6  movsxd  rax, edx
0x180005eb9  add     rax, rax
0x180005ebc  mov     byte ptr [r9+rax*8], 0
0x180005ec1  mov     [r9+rax*8+8], r13d
0x180005ec6  lea     r13, [rbx+1Ch]
0x180005eca  add     r13, r15
0x180005ecd  mov     dword ptr [r13+0], 0
0x180005ed5  mov     [r15+rbx+8], esi
0x180005eda  mov     [r15+rbx+10h], r9
0x180005edf  mov     rsi, [rsp+78h+arg_8]
0x180005ee7  jmp     loc_180005E29
0x180005eec  inc     r12d
0x180005eef  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180005ef6  jmp     loc_180005E05
0x180005efb  mov     ebx, [rsp+78h+arg_10]
0x180005f02  mov     rdi, [rsp+78h+arg_18]
0x180005f0a  jmp     loc_180005D49
```
