# CProcessEntry::FlushCore(_EXTENSION_CONTROL_BLOCK *,CAsyncPipeOverlapped *)

- ea: `0x18001d078`
- end: `0x18001d3bf`
- name: `?FlushCore@CProcessEntry@@AEAAHPEAU_EXTENSION_CONTROL_BLOCK@@PEAUCAsyncPipeOverlapped@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(CProcessEntry *this, struct _EXTENSION_CONTROL_BLOCK *, struct CAsyncPipeOverlapped *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001ec98`

## callees

- `0x18000baf0`
- `0x180011c10`
- `0x180011c60`
- `0x180011d00`
- `0x180011e00`
- `0x18001cae8`
- `0x18001d078`
- `0x18001e680`
- `0x18001f72c`
- `0x1800447fc`
- `0x180044984`
- `0x18004d350`
- `0x18004d754`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18001d133`
- `KERNEL32!lstrlenA` at `0x18001d146`
- `KERNEL32!lstrlenA` at `0x18001d133`
- `KERNEL32!lstrlenA` at `0x18001d146`
- `KERNEL32!GetCurrentThreadId` at `0x18001d11e`
- `KERNEL32!GetCurrentThreadId` at `0x18001d11e`

## pseudocode

```c
__int64 __fastcall CProcessEntry::FlushCore(
        CProcessEntry *this,
        struct _EXTENSION_CONTROL_BLOCK *a2,
        struct CAsyncPipeOverlapped *a3)
{
  int v3; // r15d
  const CHAR *v4; // rsi
  int v6; // ebp
  unsigned int v7; // edi
  int LastWin32Error; // r13d
  unsigned int v11; // esi
  unsigned int v12; // ebp
  DWORD CurrentThreadId; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  struct CResponseContext *v18; // rax
  struct CResponseContext *v19; // r15
  void *v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // r8d
  struct CResponseContext *v25; // r15
  int v26; // r8d
  unsigned int v27; // [rsp+40h] [rbp-88h]
  int v28; // [rsp+44h] [rbp-84h]
  int v29; // [rsp+48h] [rbp-80h]
  _BYTE v30[16]; // [rsp+50h] [rbp-78h] BYREF
  CProcessEntry *v31; // [rsp+60h] [rbp-68h]
  struct CAsyncPipeOverlapped *v32; // [rsp+68h] [rbp-60h]
  int v33; // [rsp+70h] [rbp-58h]
  DWORD v34; // [rsp+78h] [rbp-50h]
  struct _EXTENSION_CONTROL_BLOCK *v35; // [rsp+80h] [rbp-48h]
  int v36; // [rsp+E8h] [rbp+20h]

  v3 = *((_DWORD *)a3 + 23);
  v4 = (char *)a3 + 112;
  v6 = *((_DWORD *)a3 + 27);
  v7 = 0;
  v27 = v3;
  LastWin32Error = 0;
  v29 = *((_DWORD *)a3 + 19);
  v28 = v6;
  if ( !CheckFlushCoreBufferForSecurity(a3) )
  {
    _InterlockedAdd(&g_lSecurityIssueBug129921_e, 1u);
    LastWin32Error = -2147418113;
LABEL_3:
    v11 = 0;
LABEL_39:
    if ( !LastWin32Error )
      return v11;
    return v7;
  }
  *((_DWORD *)a3 + 23) = v6;
  v12 = 1;
  if ( (unsigned int)CProcessEntry::UseTransmitFile() && (*((_DWORD *)a3 + 24) > 1u || *((_DWORD *)a3 + 26)) )
  {
    memset_0(v30, 0, 0x40u);
    v31 = this;
    v32 = a3;
    v33 = 1;
    CurrentThreadId = GetCurrentThreadId();
    v35 = a2;
    v34 = CurrentThreadId;
    v14 = lstrlenA(v4);
    v15 = *((unsigned int *)a3 + 24);
    if ( v14 >= (unsigned int)v15 )
      *v4 = 0;
    v16 = lstrlenA(&v4[v15]);
    v17 = *((_DWORD *)a3 + 25);
    if ( v16 >= v17 )
    {
      v4[*((unsigned int *)a3 + 24)] = 0;
      v17 = *((_DWORD *)a3 + 25);
    }
    if ( &v4[v17 + *((_DWORD *)a3 + 24) + *((unsigned int *)a3 + 26)] > (const CHAR *)a3
                                                                      + *((unsigned int *)a3 + 13)
                                                                      + 76 )
      *((_DWORD *)a3 + 26) = 0;
    v18 = CResponseContextHolder::Add((const struct CResponseContext *)v30);
    v19 = v18;
    if ( !v18 )
    {
      LastWin32Error = -2147024882;
      goto LABEL_3;
    }
    v20 = (void *)*(int *)v18;
    v36 = (int)v20;
    _InterlockedAdd((volatile signed __int32 *)this + 40, 1u);
    if ( g_iAsyncOption == 2 )
    {
      v21 = *((unsigned int *)a3 + 24);
      if ( (unsigned int)v21 > 1 )
      {
        EcbWriteHeaders(a2, v4, &v4[v21], v27);
        LODWORD(v21) = *((_DWORD *)a3 + 24);
        LODWORD(v20) = v36;
      }
      v22 = EcbWriteBytesAsync(
              a2,
              (void *)&v4[(unsigned int)(*((_DWORD *)a3 + 25) + v21)],
              *((_DWORD *)a3 + 26),
              OnWriteBytesComplete,
              (void *)(int)v20);
    }
    else if ( v27 || !v4 || *((_DWORD *)a3 + 24) <= 1u )
    {
      v22 = EcbWriteBytesUsingTransmitFile(
              a2,
              v4,
              &v4[*((unsigned int *)a3 + 24)],
              v27,
              (void *)&v4[*((_DWORD *)a3 + 24) + *((_DWORD *)a3 + 25)],
              *((_DWORD *)a3 + 26),
              OnWriteBytesComplete,
              v20);
    }
    else
    {
      if ( !(unsigned int)EcbWriteHeaders(a2, v4, &v4[*((unsigned int *)a3 + 24)], 0) )
      {
        LastWin32Error = GetLastWin32Error();
        goto LABEL_3;
      }
      v23 = *((_DWORD *)a3 + 26);
      if ( !v23 )
      {
        v11 = 0;
        goto LABEL_31;
      }
      v22 = EcbWriteBytesUsingTransmitFile(
              a2,
              0,
              0,
              0,
              (void *)&v4[*((_DWORD *)a3 + 24) + *((_DWORD *)a3 + 25)],
              v23,
              OnWriteBytesComplete,
              (void *)v36);
    }
    v11 = v22;
    if ( v22 )
    {
      if ( *((_DWORD *)v19 + 9) )
      {
LABEL_32:
        CResponseContextHolder::Remove(v36);
        if ( *((_DWORD *)v19 + 9) == 2 )
          CAsyncPipe::ReturnBuffer((CProcessEntry *)((char *)this + 80), a3);
        else
          v12 = 0;
        MemFree(v19);
        _InterlockedDecrement((volatile signed __int32 *)this + 40);
        return v12;
      }
      _InterlockedAdd(&g_lNumAsyncPending, 1u);
    }
LABEL_31:
    if ( !*((_DWORD *)v19 + 9) )
    {
      *((_DWORD *)v19 + 8) = 0;
      if ( !v11 )
      {
        v25 = CResponseContextHolder::Remove(v36);
        if ( v25 )
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 40);
          CAsyncPipe::ReturnBuffer((CProcessEntry *)((char *)this + 80), a3);
          MemFree(v25);
          _InterlockedDecrement((volatile signed __int32 *)this + 40);
          CProcessEntry::OnRequestComplete(this, v29, a2, v28);
          v11 = 1;
        }
      }
      goto LABEL_39;
    }
    goto LABEL_32;
  }
  if ( *((_DWORD *)a3 + 24) > 1u )
    EcbWriteHeaders(a2, v4, &v4[*((unsigned int *)a3 + 24)], v3);
  v26 = *((_DWORD *)a3 + 26);
  if ( v26 )
    EcbWriteBytes(a2, (void *)&v4[*((_DWORD *)a3 + 24) + *((_DWORD *)a3 + 25)], v26);
  return 0;
}

```

## disassembly

```asm
0x18001d078  mov     [rsp+arg_0], rbx
0x18001d07d  push    rbp
0x18001d07e  push    rsi
0x18001d07f  push    rdi
0x18001d080  push    r12
0x18001d082  push    r13
0x18001d084  push    r14
0x18001d086  push    r15
0x18001d088  sub     rsp, 90h
0x18001d08f  mov     r15d, [r8+5Ch]
0x18001d093  lea     rsi, [r8+70h]
0x18001d097  mov     eax, [r8+4Ch]
0x18001d09b  mov     r14, rcx
0x18001d09e  mov     ebp, [r8+6Ch]
0x18001d0a2  xor     edi, edi
0x18001d0a4  mov     rcx, r8; struct CAsyncPipeOverlapped *
0x18001d0a7  mov     [rsp+0C8h+var_88], r15d
0x18001d0ac  mov     r13d, edi
0x18001d0af  mov     [rsp+0C8h+var_80], eax
0x18001d0b3  mov     rbx, r8
0x18001d0b6  mov     [rsp+0C8h+var_84], ebp
0x18001d0ba  mov     r12, rdx
0x18001d0bd  call    ?CheckFlushCoreBufferForSecurity@@YAHPEAUCAsyncPipeOverlapped@@@Z; CheckFlushCoreBufferForSecurity(CAsyncPipeOverlapped *)
0x18001d0c2  test    eax, eax
0x18001d0c4  jnz     short loc_18001D0DD
0x18001d0c6  lea     ebp, [rdi+1]
0x18001d0c9  lock add cs:?g_lSecurityIssueBug129921_e@@3JA, ebp; long g_lSecurityIssueBug129921_e
0x18001d0d0  mov     r13d, 8000FFFFh
0x18001d0d6  mov     esi, edi
0x18001d0d8  jmp     loc_18001D364
0x18001d0dd  mov     [rbx+5Ch], ebp
0x18001d0e0  call    ?UseTransmitFile@CProcessEntry@@CAHXZ; CProcessEntry::UseTransmitFile(void)
0x18001d0e5  mov     ebp, 1
0x18001d0ea  test    eax, eax
0x18001d0ec  jz      loc_18001D36E
0x18001d0f2  cmp     [rbx+60h], ebp
0x18001d0f5  ja      short loc_18001D100
0x18001d0f7  cmp     [rbx+68h], edi
0x18001d0fa  jz      loc_18001D36E
0x18001d100  xor     edx, edx; Val
0x18001d102  lea     rcx, [rsp+0C8h+var_78]; void *
0x18001d107  lea     r8d, [rdx+40h]; Size
0x18001d10b  call    memset_0
0x18001d110  mov     [rsp+0C8h+var_68], r14
0x18001d115  mov     [rsp+0C8h+var_60], rbx
0x18001d11a  mov     [rsp+0C8h+var_58], ebp
0x18001d11e  call    cs:__imp_GetCurrentThreadId
0x18001d124  mov     rcx, rsi; lpString
0x18001d127  mov     [rsp+0C8h+var_48], r12
0x18001d12f  mov     [rsp+0C8h+var_50], eax
0x18001d133  call    cs:__imp_lstrlenA
0x18001d139  mov     ecx, [rbx+60h]
0x18001d13c  cmp     eax, ecx
0x18001d13e  jb      short loc_18001D143
0x18001d140  mov     [rsi], dil
0x18001d143  add     rcx, rsi; lpString
0x18001d146  call    cs:__imp_lstrlenA
0x18001d14c  mov     ecx, [rbx+64h]
0x18001d14f  cmp     eax, ecx
0x18001d151  jb      short loc_18001D15D
0x18001d153  mov     eax, [rbx+60h]
0x18001d156  mov     [rax+rsi], dil
0x18001d15a  mov     ecx, [rbx+64h]
0x18001d15d  mov     eax, [rbx+60h]
0x18001d160  mov     edx, [rbx+68h]
0x18001d163  add     eax, ecx
0x18001d165  add     rax, rsi
0x18001d168  lea     rcx, [rbx+4Ch]
0x18001d16c  add     rdx, rax
0x18001d16f  mov     eax, [rbx+34h]
0x18001d172  add     rcx, rax
0x18001d175  cmp     rdx, rcx
0x18001d178  jbe     short loc_18001D17D
0x18001d17a  mov     [rbx+68h], edi
0x18001d17d  lea     rcx, [rsp+0C8h+var_78]; struct CResponseContext *
0x18001d182  call    ?Add@CResponseContextHolder@@SAPEAUCResponseContext@@AEBU2@@Z; CResponseContextHolder::Add(CResponseContext const &)
0x18001d187  mov     r15, rax
0x18001d18a  test    rax, rax
0x18001d18d  jnz     short loc_18001D19A
0x18001d18f  mov     r13d, 8007000Eh
0x18001d195  jmp     loc_18001D0D6
0x18001d19a  movsxd  rax, dword ptr [rax]
0x18001d19d  mov     [rsp+0C8h+arg_18], eax
0x18001d1a4  lock add [r14+0A0h], ebp
0x18001d1ac  cmp     cs:?g_iAsyncOption@@3HA, 2; int g_iAsyncOption
0x18001d1b3  jnz     short loc_18001D200
0x18001d1b5  mov     edx, [rbx+60h]
0x18001d1b8  cmp     edx, ebp
0x18001d1ba  jbe     short loc_18001D1DA
0x18001d1bc  mov     r9d, [rsp+0C8h+var_88]; int
0x18001d1c1  lea     r8, [rsi+rdx]; char *
0x18001d1c5  mov     rdx, rsi; char *
0x18001d1c8  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d1cb  call    ?EcbWriteHeaders@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD1H@Z; EcbWriteHeaders(_EXTENSION_CONTROL_BLOCK *,char const *,char const *,int)
0x18001d1d0  mov     edx, [rbx+60h]
0x18001d1d3  mov     eax, [rsp+0C8h+arg_18]
0x18001d1da  add     edx, [rbx+64h]
0x18001d1dd  lea     r9, ?OnWriteBytesComplete@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z; void (*)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)
0x18001d1e4  mov     r8d, [rbx+68h]; int
0x18001d1e8  add     rdx, rsi; void *
0x18001d1eb  movsxd  rcx, eax
0x18001d1ee  mov     [rsp+0C8h+var_A8], rcx; void *
0x18001d1f3  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d1f6  call    ?EcbWriteBytesAsync@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEAXHP6AX01KK@Z1@Z; EcbWriteBytesAsync(_EXTENSION_CONTROL_BLOCK *,void *,int,void (*)(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong),void *)
0x18001d1fb  jmp     loc_18001D2B7
0x18001d200  mov     edx, [rsp+0C8h+var_88]
0x18001d204  test    edx, edx
0x18001d206  jnz     short loc_18001D27B
0x18001d208  test    rsi, rsi
0x18001d20b  jz      short loc_18001D27B
0x18001d20d  cmp     [rbx+60h], ebp
0x18001d210  jbe     short loc_18001D27B
0x18001d212  mov     r8d, [rbx+60h]
0x18001d216  xor     r9d, r9d; int
0x18001d219  add     r8, rsi; char *
0x18001d21c  mov     rdx, rsi; char *
0x18001d21f  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d222  call    ?EcbWriteHeaders@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD1H@Z; EcbWriteHeaders(_EXTENSION_CONTROL_BLOCK *,char const *,char const *,int)
0x18001d227  test    eax, eax
0x18001d229  jnz     short loc_18001D238
0x18001d22b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18001d230  mov     r13d, eax
0x18001d233  jmp     loc_18001D0D6
0x18001d238  mov     r8d, [rbx+68h]
0x18001d23c  test    r8d, r8d
0x18001d23f  jz      loc_18001D2CC
0x18001d245  mov     edx, [rbx+64h]
0x18001d248  lea     rax, ?OnWriteBytesComplete@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z; OnWriteBytesComplete(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)
0x18001d24f  add     edx, [rbx+60h]
0x18001d252  xor     r9d, r9d
0x18001d255  movsxd  rcx, [rsp+0C8h+arg_18]
0x18001d25d  add     rdx, rsi
0x18001d260  mov     [rsp+0C8h+var_90], rcx
0x18001d265  mov     [rsp+0C8h+var_98], rax
0x18001d26a  mov     [rsp+0C8h+var_A0], r8d
0x18001d26f  xor     r8d, r8d
0x18001d272  mov     [rsp+0C8h+var_A8], rdx
0x18001d277  xor     edx, edx
0x18001d279  jmp     short loc_18001D2AF
0x18001d27b  mov     r8d, [rbx+60h]
0x18001d27f  mov     r9d, edx; int
0x18001d282  mov     r10d, [rbx+64h]
0x18001d286  mov     rdx, rsi; char *
0x18001d289  mov     [rsp+0C8h+var_90], rax; void *
0x18001d28e  add     r10d, r8d
0x18001d291  lea     rax, ?OnWriteBytesComplete@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z; OnWriteBytesComplete(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)
0x18001d298  add     r10, rsi
0x18001d29b  mov     [rsp+0C8h+var_98], rax; void (*)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)
0x18001d2a0  add     r8, rsi; lpString
0x18001d2a3  mov     eax, [rbx+68h]
0x18001d2a6  mov     [rsp+0C8h+var_A0], eax; int
0x18001d2aa  mov     [rsp+0C8h+var_A8], r10; void *
0x18001d2af  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d2b2  call    ?EcbWriteBytesUsingTransmitFile@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD1HPEAXHP6AX02KK@Z2@Z; EcbWriteBytesUsingTransmitFile(_EXTENSION_CONTROL_BLOCK *,char const *,char const *,int,void *,int,void (*)(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong),void *)
0x18001d2b7  mov     esi, eax
0x18001d2b9  test    eax, eax
0x18001d2bb  jz      short loc_18001D2CE
0x18001d2bd  cmp     [r15+24h], edi
0x18001d2c1  jnz     short loc_18001D2D4
0x18001d2c3  lock add cs:?g_lNumAsyncPending@@3JA, ebp; long g_lNumAsyncPending
0x18001d2ca  jmp     short loc_18001D2CE
0x18001d2cc  mov     esi, edi
0x18001d2ce  cmp     [r15+24h], edi
0x18001d2d2  jz      short loc_18001D30E
0x18001d2d4  mov     ecx, [rsp+0C8h+arg_18]; int
0x18001d2db  call    ?Remove@CResponseContextHolder@@SAPEAUCResponseContext@@J@Z; CResponseContextHolder::Remove(long)
0x18001d2e0  cmp     dword ptr [r15+24h], 2
0x18001d2e5  jnz     short loc_18001D2F5
0x18001d2e7  lea     rcx, [r14+50h]; this
0x18001d2eb  mov     rdx, rbx; struct CAsyncPipeOverlapped *
0x18001d2ee  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001d2f3  jmp     short loc_18001D2F7
0x18001d2f5  mov     ebp, edi
0x18001d2f7  mov     rcx, r15; lpMem
0x18001d2fa  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001d2ff  lock dec dword ptr [r14+0A0h]
0x18001d307  mov     eax, ebp
0x18001d309  jmp     loc_18001D3A4
0x18001d30e  mov     [r15+20h], edi
0x18001d312  test    esi, esi
0x18001d314  jnz     short loc_18001D364
0x18001d316  mov     ecx, [rsp+0C8h+arg_18]; int
0x18001d31d  call    ?Remove@CResponseContextHolder@@SAPEAUCResponseContext@@J@Z; CResponseContextHolder::Remove(long)
0x18001d322  mov     r15, rax
0x18001d325  test    rax, rax
0x18001d328  jz      short loc_18001D364
0x18001d32a  lock dec dword ptr [r14+0A0h]
0x18001d332  lea     rcx, [r14+50h]; this
0x18001d336  mov     rdx, rbx; struct CAsyncPipeOverlapped *
0x18001d339  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18001d33e  mov     rcx, r15; lpMem
0x18001d341  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001d346  mov     r9d, [rsp+0C8h+var_84]; int
0x18001d34b  mov     r8, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d34e  mov     edx, [rsp+0C8h+var_80]; int
0x18001d352  mov     rcx, r14; this
0x18001d355  lock dec dword ptr [r14+0A0h]
0x18001d35d  call    ?OnRequestComplete@CProcessEntry@@QEAAXJPEAU_EXTENSION_CONTROL_BLOCK@@H@Z; CProcessEntry::OnRequestComplete(long,_EXTENSION_CONTROL_BLOCK *,int)
0x18001d362  mov     esi, ebp
0x18001d364  test    r13d, r13d
0x18001d367  cmovz   edi, esi
0x18001d36a  mov     eax, edi
0x18001d36c  jmp     short loc_18001D3A4
0x18001d36e  cmp     [rbx+60h], ebp
0x18001d371  jbe     short loc_18001D388
0x18001d373  mov     r8d, [rbx+60h]
0x18001d377  mov     r9d, r15d; int
0x18001d37a  add     r8, rsi; char *
0x18001d37d  mov     rdx, rsi; char *
0x18001d380  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d383  call    ?EcbWriteHeaders@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD1H@Z; EcbWriteHeaders(_EXTENSION_CONTROL_BLOCK *,char const *,char const *,int)
0x18001d388  mov     r8d, [rbx+68h]; int
0x18001d38c  test    r8d, r8d
0x18001d38f  jz      short loc_18001D3A2
0x18001d391  mov     edx, [rbx+64h]
0x18001d394  mov     rcx, r12; struct _EXTENSION_CONTROL_BLOCK *
0x18001d397  add     edx, [rbx+60h]
0x18001d39a  add     rdx, rsi; void *
0x18001d39d  call    ?EcbWriteBytes@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEAXH@Z; EcbWriteBytes(_EXTENSION_CONTROL_BLOCK *,void *,int)
0x18001d3a2  xor     eax, eax
0x18001d3a4  mov     rbx, [rsp+0C8h+arg_0]
0x18001d3ac  add     rsp, 90h
0x18001d3b3  pop     r15
0x18001d3b5  pop     r14
0x18001d3b7  pop     r13
0x18001d3b9  pop     r12
0x18001d3bb  pop     rdi
0x18001d3bc  pop     rsi
0x18001d3bd  pop     rbp
0x18001d3be  retn
```
