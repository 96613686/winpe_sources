# CProcessEntry::TransmitFile(_EXTENSION_CONTROL_BLOCK *,CAsyncPipeOverlapped *)

- ea: `0x18001f364`
- end: `0x18001f6f6`
- name: `?TransmitFile@CProcessEntry@@AEAAHPEAU_EXTENSION_CONTROL_BLOCK@@PEAUCAsyncPipeOverlapped@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(CProcessEntry *__hidden this, struct _EXTENSION_CONTROL_BLOCK *, struct CAsyncPipeOverlapped *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001ec98`

## callees

- `0x18000b694`
- `0x18000baf0`
- `0x180011b1c`
- `0x180014644`
- `0x18001cae8`
- `0x18001d530`
- `0x18001e680`
- `0x18001f364`
- `0x1800447fc`
- `0x180044984`
- `0x18004d030`
- `0x18004d298`
- `0x18004d754`
- `0x1800653ba`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001f60d`
- `KERNEL32!CloseHandle` at `0x18001f672`
- `KERNEL32!CloseHandle` at `0x18001f60d`
- `KERNEL32!CloseHandle` at `0x18001f672`
- `KERNEL32!lstrlenA` at `0x18001f413`
- `KERNEL32!lstrlenA` at `0x18001f426`
- `KERNEL32!lstrlenA` at `0x18001f413`
- `KERNEL32!lstrlenA` at `0x18001f426`
- `KERNEL32!GetCurrentThreadId` at `0x18001f3fb`
- `KERNEL32!GetCurrentThreadId` at `0x18001f3fb`

## pseudocode

```c
__int64 __fastcall CProcessEntry::TransmitFile(
        CProcessEntry *this,
        struct _EXTENSION_CONTROL_BLOCK *a2,
        struct CAsyncPipeOverlapped *a3)
{
  const CHAR *v3; // r14
  int v4; // ebp
  unsigned int v6; // ebx
  unsigned int v7; // r12d
  DWORD CurrentThreadId; // eax
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ecx
  struct CResponseContext *v15; // rax
  struct CResponseContext *v16; // r15
  int v17; // eax
  __int64 v18; // rcx
  unsigned int v19; // ebp
  unsigned int v20; // r13d
  struct _EXTENSION_CONTROL_BLOCK *v21; // r13
  __int64 v22; // rax
  void *v23; // r9
  int v24; // ebp
  char *v25; // rcx
  unsigned int v26; // r12d
  struct CResponseContext *v28; // rax
  struct CResponseContext *v29; // rbp
  char *v30; // rcx
  unsigned int v31; // [rsp+40h] [rbp-2C8h]
  int v32; // [rsp+44h] [rbp-2C4h]
  unsigned int v33; // [rsp+48h] [rbp-2C0h]
  unsigned int v34; // [rsp+4Ch] [rbp-2BCh]
  int v35; // [rsp+50h] [rbp-2B8h]
  int v36; // [rsp+54h] [rbp-2B4h]
  struct CAsyncPipeOverlapped *Buffer; // [rsp+60h] [rbp-2A8h]
  _BYTE v39[16]; // [rsp+70h] [rbp-298h] BYREF
  CProcessEntry *v40; // [rsp+80h] [rbp-288h]
  struct CAsyncPipeOverlapped *v41; // [rsp+88h] [rbp-280h]
  int v42; // [rsp+90h] [rbp-278h]
  DWORD v43; // [rsp+98h] [rbp-270h]
  struct _EXTENSION_CONTROL_BLOCK *v44; // [rsp+A0h] [rbp-268h]
  unsigned __int16 v45[264]; // [rsp+B0h] [rbp-258h] BYREF

  v3 = (char *)a3 + 112;
  v4 = *((_DWORD *)a3 + 27);
  v6 = 0;
  v36 = *((_DWORD *)a3 + 19);
  v7 = 0;
  v35 = v4;
  if ( !(unsigned int)CheckFlushCoreBufferForSecurity(a3) || *((_DWORD *)a3 + 26) < 0xAu )
    goto LABEL_36;
  *((_DWORD *)a3 + 23) = v4;
  memset_0(v39, 0, 0x40u);
  v40 = this;
  v42 = 1;
  v41 = a3;
  CurrentThreadId = GetCurrentThreadId();
  v44 = a2;
  v43 = CurrentThreadId;
  v11 = lstrlenA(v3);
  v12 = *((unsigned int *)a3 + 24);
  if ( v11 >= (unsigned int)v12 )
    *v3 = 0;
  v13 = lstrlenA(&v3[v12]);
  v14 = *((_DWORD *)a3 + 25);
  if ( v13 >= v14 )
  {
    v3[*((unsigned int *)a3 + 24)] = 0;
    v14 = *((_DWORD *)a3 + 25);
  }
  if ( &v3[v14 + *((_DWORD *)a3 + 24) + *((unsigned int *)a3 + 26)] > (const CHAR *)a3 + *((unsigned int *)a3 + 13) + 76 )
    *((_DWORD *)a3 + 26) = 0;
  v15 = CResponseContextHolder::Add((const struct CResponseContext *)v39);
  v16 = v15;
  if ( !v15 )
    goto LABEL_10;
  v32 = *(_DWORD *)v15;
  _InterlockedAdd((volatile signed __int32 *)this + 40, 1u);
  v18 = (unsigned int)(*((_DWORD *)a3 + 24) + *((_DWORD *)a3 + 25));
  v19 = *((_DWORD *)a3 + 26) - 12;
  v31 = *(_DWORD *)&v3[v18];
  v34 = *(_DWORD *)&v3[v18 + 4];
  v33 = *(_DWORD *)&v3[v18 + 8];
  if ( v19 < 2 )
  {
LABEL_36:
    v17 = -2147418113;
    goto LABEL_37;
  }
  v20 = v19 >> 1;
  if ( v19 >> 1 > 0x104 )
  {
    Buffer = CAsyncPipe::GetBuffer((CProcessEntry *)((char *)this + 80), v19 + 2);
    if ( !Buffer )
    {
LABEL_10:
      v17 = -2147024882;
LABEL_37:
      if ( !v17 )
        return v7;
      return v6;
    }
    memcpy_0(Buffer, &v3[*((_DWORD *)a3 + 24) + *((_DWORD *)a3 + 25) + 12], v19);
    v22 = v20 - 1;
    v21 = a2;
    *((_WORD *)Buffer + v22) = 0;
    *((_QWORD *)v16 + 1) = CProcessEntry::GetFileHandle(this, a2, (unsigned __int16 *)Buffer, v19 >> 1, v31);
    CAsyncPipe::ReturnBuffer((CProcessEntry *)((char *)this + 80), Buffer);
  }
  else
  {
    memcpy_0(v45, &v3[v18 + 12], v19);
    if ( 2 * (unsigned __int64)(v20 - 1) >= 0x20A )
      _report_rangecheckfailure();
    v45[v20 - 1] = 0;
    v21 = a2;
    *((_QWORD *)v16 + 1) = CProcessEntry::GetFileHandle(this, a2, v45, v19 >> 1, v31);
  }
  v23 = (void *)*((_QWORD *)v16 + 1);
  if ( v23 == (void *)-1LL )
  {
    if ( v3 && v3[*((unsigned int *)a3 + 24)] )
      ReportHttpErrorIndirect(v21, 0x80000415);
    v24 = v32;
    v7 = 0;
  }
  else
  {
    v24 = v32;
    v7 = EcbTransmitFile(v21, v3, &v3[*((unsigned int *)a3 + 24)], v23, v34, v33, OnWriteBytesComplete, (void *)v32);
  }
  if ( !*((_DWORD *)v16 + 9) )
  {
    *((_DWORD *)v16 + 8) = 0;
    if ( !v7 )
    {
      v28 = CResponseContextHolder::Remove(v24);
      v29 = v28;
      if ( v28 )
      {
        v30 = (char *)*((_QWORD *)v28 + 1);
        if ( (unsigned __int64)(v30 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v30);
        _InterlockedDecrement((volatile signed __int32 *)this + 40);
        CAsyncPipe::ReturnBuffer((CProcessEntry *)((char *)this + 80), a3);
        MemFree(v29);
        _InterlockedDecrement((volatile signed __int32 *)this + 40);
        CProcessEntry::OnRequestComplete(this, v36, v21, v35);
        v7 = 1;
      }
    }
    v17 = 0;
    goto LABEL_37;
  }
  v25 = (char *)*((_QWORD *)v16 + 1);
  if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v25);
  CResponseContextHolder::Remove(v24);
  if ( *((_DWORD *)v16 + 9) == 2 )
  {
    CAsyncPipe::ReturnBuffer((CProcessEntry *)((char *)this + 80), a3);
    v26 = 1;
  }
  else
  {
    v26 = 0;
  }
  MemFree(v16);
  _InterlockedDecrement((volatile signed __int32 *)this + 40);
  return v26;
}

```

## disassembly

```asm
0x18001f364  mov     [rsp+arg_18], rbx
0x18001f369  push    rbp
0x18001f36a  push    rsi
0x18001f36b  push    rdi
0x18001f36c  push    r12
0x18001f36e  push    r13
0x18001f370  push    r14
0x18001f372  push    r15
0x18001f374  sub     rsp, 2D0h
0x18001f37b  mov     rax, cs:__security_cookie
0x18001f382  xor     rax, rsp
0x18001f385  mov     [rsp+308h+var_48], rax
0x18001f38d  mov     eax, [r8+4Ch]
0x18001f391  lea     r14, [r8+70h]
0x18001f395  mov     ebp, [r8+6Ch]
0x18001f399  mov     rsi, rcx
0x18001f39c  xor     ebx, ebx
0x18001f39e  mov     [rsp+308h+var_2B0], rdx
0x18001f3a3  mov     rcx, r8; struct CAsyncPipeOverlapped *
0x18001f3a6  mov     [rsp+308h+var_2B4], eax
0x18001f3aa  mov     r12d, ebx
0x18001f3ad  mov     [rsp+308h+var_2B8], ebp
0x18001f3b1  mov     rdi, r8
0x18001f3b4  mov     r15, rdx
0x18001f3b7  call    ?CheckFlushCoreBufferForSecurity@@YAHPEAUCAsyncPipeOverlapped@@@Z; CheckFlushCoreBufferForSecurity(CAsyncPipeOverlapped *)
0x18001f3bc  test    eax, eax
0x18001f3be  jz      loc_18001F6B8
0x18001f3c4  cmp     dword ptr [rdi+68h], 0Ah
0x18001f3c8  jb      loc_18001F6B8
0x18001f3ce  xor     edx, edx; Val
0x18001f3d0  mov     [rdi+5Ch], ebp
0x18001f3d3  lea     r8d, [rbx+40h]; Size
0x18001f3d7  lea     rcx, [rsp+308h+var_298]; void *
0x18001f3dc  call    memset_0
0x18001f3e1  lea     ebp, [rbx+1]
0x18001f3e4  mov     [rsp+308h+var_288], rsi
0x18001f3ec  mov     [rsp+308h+var_278], ebp
0x18001f3f3  mov     [rsp+308h+var_280], rdi
0x18001f3fb  call    cs:__imp_GetCurrentThreadId
0x18001f401  mov     rcx, r14; lpString
0x18001f404  mov     [rsp+308h+var_268], r15
0x18001f40c  mov     [rsp+308h+var_270], eax
0x18001f413  call    cs:__imp_lstrlenA
0x18001f419  mov     ecx, [rdi+60h]
0x18001f41c  cmp     eax, ecx
0x18001f41e  jb      short loc_18001F423
0x18001f420  mov     [r14], bl
0x18001f423  add     rcx, r14; lpString
0x18001f426  call    cs:__imp_lstrlenA
0x18001f42c  mov     ecx, [rdi+64h]
0x18001f42f  cmp     eax, ecx
0x18001f431  jb      short loc_18001F43D
0x18001f433  mov     eax, [rdi+60h]
0x18001f436  mov     [rax+r14], bl
0x18001f43a  mov     ecx, [rdi+64h]
0x18001f43d  mov     eax, [rdi+60h]
0x18001f440  mov     edx, [rdi+68h]
0x18001f443  add     eax, ecx
0x18001f445  add     rax, r14
0x18001f448  lea     rcx, [rdi+4Ch]
0x18001f44c  add     rdx, rax
0x18001f44f  mov     eax, [rdi+34h]
0x18001f452  add     rcx, rax
0x18001f455  cmp     rdx, rcx
0x18001f458  jbe     short loc_18001F45D
0x18001f45a  mov     [rdi+68h], ebx
0x18001f45d  lea     rcx, [rsp+308h+var_298]; struct CResponseContext *
0x18001f462  call    ?Add@CResponseContextHolder@@SAPEAUCResponseContext@@AEBU2@@Z; CResponseContextHolder::Add(CResponseContext const &)
0x18001f467  mov     r15, rax
0x18001f46a  test    rax, rax
0x18001f46d  jnz     short loc_18001F479
0x18001f46f  mov     eax, 8007000Eh
0x18001f474  jmp     loc_18001F6BD
0x18001f479  mov     eax, [rax]
0x18001f47b  mov     [rsp+308h+var_2C4], eax
0x18001f47f  lock add [rsi+0A0h], ebp
0x18001f486  mov     eax, [rdi+64h]
0x18001f489  add     eax, [rdi+60h]
0x18001f48c  mov     ebp, [rdi+68h]
0x18001f48f  mov     ecx, eax
0x18001f491  sub     ebp, 0Ch
0x18001f494  mov     eax, [rax+r14]
0x18001f498  mov     [rsp+308h+var_2C8], eax
0x18001f49c  mov     eax, [rcx+r14+4]
0x18001f4a1  mov     [rsp+308h+var_2BC], eax
0x18001f4a5  mov     eax, [rcx+r14+8]
0x18001f4aa  mov     [rsp+308h+var_2C0], eax
0x18001f4ae  cmp     ebp, 2
0x18001f4b1  jb      loc_18001F6B8
0x18001f4b7  mov     r13d, ebp
0x18001f4ba  shr     r13d, 1
0x18001f4bd  cmp     r13d, 104h
0x18001f4c4  ja      short loc_18001F522
0x18001f4c6  lea     rdx, [r14+0Ch]
0x18001f4ca  mov     r8d, ebp; Size
0x18001f4cd  add     rdx, rcx; Src
0x18001f4d0  lea     rcx, [rsp+308h+var_258]; void *
0x18001f4d8  call    memcpy_0
0x18001f4dd  lea     ecx, [r13-1]
0x18001f4e1  add     rcx, rcx
0x18001f4e4  cmp     rcx, 20Ah
0x18001f4eb  jnb     loc_18001F6F0
0x18001f4f1  mov     eax, [rsp+308h+var_2C8]
0x18001f4f5  lea     r8, [rsp+308h+var_258]; unsigned __int16 *
0x18001f4fd  mov     r9d, r13d; unsigned int
0x18001f500  mov     [rsp+rcx+308h+var_258], bx
0x18001f508  mov     r13, [rsp+308h+var_2B0]
0x18001f50d  mov     rcx, rsi; this
0x18001f510  mov     rdx, r13; struct _EXTENSION_CONTROL_BLOCK *
0x18001f513  mov     [rsp+308h+var_2E8], eax; unsigned int
0x18001f517  call    ?GetFileHandle@CProcessEntry@@AEAAPEAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAGKK@Z; CProcessEntry::GetFileHandle(_EXTENSION_CONTROL_BLOCK *,ushort *,ulong,ulong)
0x18001f51c  mov     [r15+8], rax
0x18001f520  jmp     short loc_18001F590
0x18001f522  lea     rcx, [rsi+50h]; this
0x18001f526  lea     edx, [rbp+2]; unsigned int
0x18001f529  call    ?GetBuffer@CAsyncPipe@@QEAAPEAUCAsyncPipeOverlapped@@K@Z; CAsyncPipe::GetBuffer(ulong)
0x18001f52e  mov     [rsp+308h+var_2A8], rax
0x18001f533  mov     rcx, rax; void *
0x18001f536  test    rax, rax
0x18001f539  jz      loc_18001F46F
0x18001f53f  mov     eax, [rdi+64h]
0x18001f542  lea     rdx, [r14+0Ch]
0x18001f546  add     eax, [rdi+60h]
0x18001f549  add     rdx, rax; Src
0x18001f54c  mov     r8d, ebp; Size
0x18001f54f  call    memcpy_0
0x18001f554  mov     r12, [rsp+308h+var_2A8]
0x18001f559  lea     eax, [r13-1]
0x18001f55d  mov     r9d, r13d; unsigned int
0x18001f560  mov     r8, r12; unsigned __int16 *
0x18001f563  mov     r13, [rsp+308h+var_2B0]
0x18001f568  mov     rcx, rsi; this
0x18001f56b  mov     rdx, r13; struct _EXTENSION_CONTROL_BLOCK *
0x18001f56e  mov     [r12+rax*2], bx
0x18001f573  mov     eax, [rsp+308h+var_2C8]
0x18001f577  mov     [rsp+308h+var_2E8], eax; unsigned int
0x18001f57b  call    ?GetFileHandle@CProcessEntry@@AEAAPEAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAGKK@Z; CProcessEntry::GetFileHandle(_EXTENSION_CONTROL_BLOCK *,ushort *,ulong,ulong)
0x18001f580  mov     rdx, r12; struct CAsyncPipeOverlapped *
0x18001f583  mov     [r15+8], rax
0x18001f587  lea     rcx, [rsi+50h]; this
0x18001f58b  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001f590  mov     r9, [r15+8]; void *
0x18001f594  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001f598  jnz     short loc_18001F5BE
0x18001f59a  test    r14, r14
0x18001f59d  jz      short loc_18001F5B5
0x18001f59f  mov     eax, [rdi+60h]
0x18001f5a2  cmp     [rax+r14], bl
0x18001f5a6  jz      short loc_18001F5B5
0x18001f5a8  mov     edx, 80000415h; unsigned int
0x18001f5ad  mov     rcx, r13; struct _EXTENSION_CONTROL_BLOCK *
0x18001f5b0  call    ?ReportHttpErrorIndirect@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@I@Z; ReportHttpErrorIndirect(_EXTENSION_CONTROL_BLOCK *,uint)
0x18001f5b5  mov     ebp, [rsp+308h+var_2C4]
0x18001f5b9  mov     r12d, ebx
0x18001f5bc  jmp     short loc_18001F5F9
0x18001f5be  mov     r8d, [rdi+60h]
0x18001f5c2  lea     rax, ?OnWriteBytesComplete@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z; OnWriteBytesComplete(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)
0x18001f5c9  movsxd  rbp, [rsp+308h+var_2C4]
0x18001f5ce  add     r8, r14; char *
0x18001f5d1  mov     [rsp+308h+var_2D0], rbp; void *
0x18001f5d6  mov     rdx, r14; char *
0x18001f5d9  mov     [rsp+308h+var_2D8], rax; void (*)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)
0x18001f5de  mov     rcx, r13; struct _EXTENSION_CONTROL_BLOCK *
0x18001f5e1  mov     eax, [rsp+308h+var_2C0]
0x18001f5e5  mov     [rsp+308h+var_2E0], eax; unsigned int
0x18001f5e9  mov     eax, [rsp+308h+var_2BC]
0x18001f5ed  mov     [rsp+308h+var_2E8], eax; unsigned int
0x18001f5f1  call    ?EcbTransmitFile@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD1PEAXKKP6AX02KK@Z2@Z; EcbTransmitFile(_EXTENSION_CONTROL_BLOCK *,char const *,char const *,void *,ulong,ulong,void (*)(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong),void *)
0x18001f5f6  mov     r12d, eax
0x18001f5f9  cmp     [r15+24h], ebx
0x18001f5fd  jz      short loc_18001F64C
0x18001f5ff  mov     rcx, [r15+8]; hObject
0x18001f603  lea     rax, [rcx-1]
0x18001f607  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f60b  ja      short loc_18001F613
0x18001f60d  call    cs:__imp_CloseHandle
0x18001f613  mov     ecx, ebp; int
0x18001f615  call    ?Remove@CResponseContextHolder@@SAPEAUCResponseContext@@J@Z; CResponseContextHolder::Remove(long)
0x18001f61a  cmp     dword ptr [r15+24h], 2
0x18001f61f  jnz     short loc_18001F635
0x18001f621  lea     rcx, [rsi+50h]; this
0x18001f625  mov     rdx, rdi; struct CAsyncPipeOverlapped *
0x18001f628  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001f62d  mov     r12d, 1
0x18001f633  jmp     short loc_18001F638
0x18001f635  mov     r12d, ebx
0x18001f638  mov     rcx, r15; lpMem
0x18001f63b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001f640  lock dec dword ptr [rsi+0A0h]
0x18001f647  mov     eax, r12d
0x18001f64a  jmp     short loc_18001F6C5
0x18001f64c  mov     [r15+20h], ebx
0x18001f650  test    r12d, r12d
0x18001f653  jnz     short loc_18001F6B4
0x18001f655  mov     ecx, ebp; int
0x18001f657  call    ?Remove@CResponseContextHolder@@SAPEAUCResponseContext@@J@Z; CResponseContextHolder::Remove(long)
0x18001f65c  mov     rbp, rax
0x18001f65f  test    rax, rax
0x18001f662  jz      short loc_18001F6B4
0x18001f664  mov     rcx, [rax+8]; hObject
0x18001f668  lea     rax, [rcx-1]
0x18001f66c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f670  ja      short loc_18001F678
0x18001f672  call    cs:__imp_CloseHandle
0x18001f678  lock dec dword ptr [rsi+0A0h]
0x18001f67f  lea     rcx, [rsi+50h]; this
0x18001f683  mov     rdx, rdi; struct CAsyncPipeOverlapped *
0x18001f686  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001f68b  mov     rcx, rbp; lpMem
0x18001f68e  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001f693  mov     r9d, [rsp+308h+var_2B8]; int
0x18001f698  mov     r8, r13; struct _EXTENSION_CONTROL_BLOCK *
0x18001f69b  mov     edx, [rsp+308h+var_2B4]; int
0x18001f69f  mov     rcx, rsi; this
0x18001f6a2  lock dec dword ptr [rsi+0A0h]
0x18001f6a9  call    ?OnRequestComplete@CProcessEntry@@QEAAXJPEAU_EXTENSION_CONTROL_BLOCK@@H@Z; CProcessEntry::OnRequestComplete(long,_EXTENSION_CONTROL_BLOCK *,int)
0x18001f6ae  mov     r12d, 1
0x18001f6b4  mov     eax, ebx
0x18001f6b6  jmp     short loc_18001F6BD
0x18001f6b8  mov     eax, 8000FFFFh
0x18001f6bd  test    eax, eax
0x18001f6bf  cmovz   ebx, r12d
0x18001f6c3  mov     eax, ebx
0x18001f6c5  mov     rcx, [rsp+308h+var_48]
0x18001f6cd  xor     rcx, rsp; StackCookie
0x18001f6d0  call    __security_check_cookie
0x18001f6d5  mov     rbx, [rsp+308h+arg_18]
0x18001f6dd  add     rsp, 2D0h
0x18001f6e4  pop     r15
0x18001f6e6  pop     r14
0x18001f6e8  pop     r13
0x18001f6ea  pop     r12
0x18001f6ec  pop     rdi
0x18001f6ed  pop     rsi
0x18001f6ee  pop     rbp
0x18001f6ef  retn
0x18001f6f0  call    __report_rangecheckfailure
```
