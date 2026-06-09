# MpUpdateFileWriteHistory

- ea: `0x140059eb0`
- end: `0x14005a39d`
- name: `MpUpdateFileWriteHistory`
- size: `1261`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140001900`
- `0x140003330`

## callees

- `0x140002450`
- `0x140003950`
- `0x1400118d0`
- `0x140011bc0`
- `0x140059eb0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140059f6f`
- `ntoskrnl!PsGetProcessId` at `0x140059f6f`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140059f55`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140059f55`
- `FLTMGR!FltReleaseContext` at `0x14005a1a4`
- `FLTMGR!FltReleaseContext` at `0x14005a1a4`
- `FLTMGR!FltAcquirePushLockShared` at `0x14005a1bc`
- `FLTMGR!FltAcquirePushLockShared` at `0x14005a2c7`
- `FLTMGR!FltAcquirePushLockShared` at `0x14005a1bc`
- `FLTMGR!FltAcquirePushLockShared` at `0x14005a2c7`
- `FLTMGR!FltReleasePushLock` at `0x14005a11c`
- `FLTMGR!FltReleasePushLock` at `0x14005a28f`
- `FLTMGR!FltReleasePushLock` at `0x14005a300`
- `FLTMGR!FltReleasePushLock` at `0x14005a11c`
- `FLTMGR!FltReleasePushLock` at `0x14005a28f`
- `FLTMGR!FltReleasePushLock` at `0x14005a300`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005a169`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005a169`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14005a1ed`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x14005a1ed`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14005a13d`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14005a13d`

## pseudocode

```c
void __fastcall MpUpdateFileWriteHistory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned __int64 *a5)
{
  struct _KPROCESS *RequestorProcess; // rax
  struct _KPROCESS *v10; // rdi
  LONGLONG TimeQuadPart; // rax
  __int64 v12; // rbx
  signed __int64 v13; // rbp
  __int64 v14; // r14
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rbp
  __int64 v18; // rdi
  unsigned __int64 v19; // rax
  __int64 v20; // rtt
  unsigned __int64 v21; // rax
  __int64 v22; // rtt
  int v23; // eax
  unsigned __int16 v24; // ax
  struct _FILE_OBJECT *v25; // rdx
  struct _FLT_INSTANCE *v26; // rcx
  PFLT_CONTEXT v27; // r8
  _BYTE *v28; // rax
  __int64 v29; // rdi
  __int128 v30; // xmm1
  __int64 v31; // rax
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int64 v38; // rdi
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int64 v44; // rdx
  volatile signed __int64 *v45; // r8
  __int64 v46; // rcx
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int64 v54; // rax
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  char v59; // [rsp+20h] [rbp-148h]
  unsigned int ProcessId; // [rsp+30h] [rbp-138h]
  _OWORD v62[14]; // [rsp+40h] [rbp-128h] BYREF
  PFLT_CONTEXT Context; // [rsp+120h] [rbp-48h] BYREF

  memset(v62, 0, 0xDCu);
  v59 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( !a4 || (*(_DWORD *)(a4 + 168) & 1) == 0 && ((v24 = *(_WORD *)(a2 + 2)) == 0 || v24 >= 0xFFFEu) )
        {
          RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
          v10 = RequestorProcess;
          if ( RequestorProcess )
          {
            TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
            v12 = MpFileTimeToUlong64(TimeQuadPart);
            ProcessId = (unsigned int)PsGetProcessId(v10);
            if ( !a4 )
              goto LABEL_7;
            if ( (*(_DWORD *)(a4 + 168) & 1) != 0 )
              return;
            if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) > 0xFFFCu )
            {
              FltAcquirePushLockShared((PULONG_PTR)(a3 + 192));
              v44 = *(_QWORD *)(a3 + 208);
              v45 = (volatile signed __int64 *)(v44 + 32);
              if ( !v44 )
                v45 = (volatile signed __int64 *)(a3 + 176);
              v13 = _InterlockedCompareExchange64(v45, 0, 0);
              FltReleasePushLock((PULONG_PTR)(a3 + 192));
            }
            else
            {
LABEL_7:
              v13 = _InterlockedCompareExchange64((volatile signed __int64 *)(a3 + 176), 0, 0);
            }
            LOBYTE(v62[0]) = 0;
            if ( *(int *)(a3 + 632) > 0 )
            {
              if ( FltSupportsStreamHandleContexts(*(PFILE_OBJECT *)(a2 + 32)) )
              {
                v25 = *(struct _FILE_OBJECT **)(a2 + 32);
                v26 = *(struct _FLT_INSTANCE **)(a2 + 24);
                Context = 0;
                if ( FltGetStreamHandleContext(v26, v25, &Context) >= 0 )
                {
                  v27 = Context;
                  v28 = (_BYTE *)*((_QWORD *)Context + 13);
                  if ( v28 )
                  {
                    v27 = Context;
                    if ( *v28 )
                    {
                      v46 = *((_QWORD *)Context + 13);
                      v47 = *(_OWORD *)(v46 + 16);
                      v62[0] = *(_OWORD *)v46;
                      v48 = *(_OWORD *)(v46 + 32);
                      v62[1] = v47;
                      v49 = *(_OWORD *)(v46 + 48);
                      v62[2] = v48;
                      v50 = *(_OWORD *)(v46 + 64);
                      v62[3] = v49;
                      v51 = *(_OWORD *)(v46 + 80);
                      v62[4] = v50;
                      v52 = *(_OWORD *)(v46 + 96);
                      v62[5] = v51;
                      v53 = *(_OWORD *)(v46 + 112);
                      v46 += 128;
                      v62[6] = v52;
                      v62[7] = v53;
                      v54 = *(_QWORD *)(v46 + 80);
                      v55 = *(_OWORD *)(v46 + 16);
                      v62[8] = *(_OWORD *)v46;
                      v56 = *(_OWORD *)(v46 + 32);
                      v62[9] = v55;
                      v57 = *(_OWORD *)(v46 + 48);
                      v62[10] = v56;
                      v58 = *(_OWORD *)(v46 + 64);
                      v62[11] = v57;
                      v62[12] = v58;
                      *(_QWORD *)&v62[13] = v54;
                      DWORD2(v62[13]) = *(_DWORD *)(v46 + 88);
                    }
                  }
                  FltReleaseContext(v27);
                }
              }
            }
            if ( a5 && *a5 )
            {
              v14 = a1;
              v16 = v13 - *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL);
            }
            else
            {
              v14 = a1;
              v15 = *(_QWORD *)(a1 + 16);
              v16 = *(_QWORD *)(v15 + 40);
              v13 = v16 + *(unsigned int *)(v15 + 24);
            }
            v17 = v13 - 1;
            if ( a4 && (FltAcquirePushLockShared((PULONG_PTR)(a3 + 192)), v29 = *(_QWORD *)(a3 + 208), v59 = 1, v29) )
              v18 = v29 + 72;
            else
              v18 = a3 + 336;
            if ( _InterlockedIncrement((volatile signed __int32 *)(v18 + 48)) == 1 )
              _InterlockedExchange64((volatile __int64 *)v18, v16);
            _InterlockedExchange64((volatile __int64 *)(v18 + 8), v17);
            do
            {
              v19 = *(_QWORD *)(v18 + 16);
              if ( v19 <= v16 )
                break;
              _mm_lfence();
              v20 = *(_QWORD *)(v18 + 16);
            }
            while ( v20 != _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 16), v16, v19) );
            do
            {
              v21 = *(_QWORD *)(v18 + 24);
              if ( v21 >= v17 )
                break;
              _mm_lfence();
              v22 = *(_QWORD *)(v18 + 24);
            }
            while ( v22 != _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 24), v17, v21) );
            _InterlockedAdd64((volatile signed __int64 *)(v18 + 32), *(unsigned int *)(*(_QWORD *)(v14 + 16) + 24LL));
            v23 = *(_DWORD *)(v18 + 64);
            if ( !v23 || ProcessId != v23 )
            {
              *(_DWORD *)(v18 + 64) = ProcessId;
              *(_QWORD *)(v18 + 56) = v12;
            }
            if ( a5 && *a5 )
            {
              _InterlockedAdd64((volatile signed __int64 *)(v18 + 40), *a5);
              _InterlockedOr((volatile signed __int32 *)(v18 + 52), 4u);
            }
            if ( LOBYTE(v62[0]) )
            {
              FltAcquirePushLockExclusive((PULONG_PTR)(a3 + 624));
              v30 = v62[1];
              v31 = *(_QWORD *)&v62[13];
              *(_OWORD *)(v18 + 68) = v62[0];
              v32 = v62[2];
              *(_OWORD *)(v18 + 84) = v30;
              v33 = v62[3];
              *(_OWORD *)(v18 + 100) = v32;
              v34 = v62[4];
              *(_OWORD *)(v18 + 116) = v33;
              v35 = v62[5];
              *(_OWORD *)(v18 + 132) = v34;
              v36 = v62[6];
              *(_OWORD *)(v18 + 148) = v35;
              v37 = v62[7];
              *(_OWORD *)(v18 + 164) = v36;
              v38 = v18 + 196;
              v39 = v62[8];
              *(_OWORD *)(v38 - 16) = v37;
              v40 = v62[9];
              *(_OWORD *)v38 = v39;
              v41 = v62[10];
              *(_OWORD *)(v38 + 16) = v40;
              v42 = v62[11];
              *(_OWORD *)(v38 + 32) = v41;
              v43 = v62[12];
              *(_OWORD *)(v38 + 48) = v42;
              *(_OWORD *)(v38 + 64) = v43;
              *(_QWORD *)(v38 + 80) = v31;
              *(_DWORD *)(v38 + 88) = DWORD2(v62[13]);
              FltReleasePushLock((PULONG_PTR)(a3 + 624));
            }
            else
            {
              *(_BYTE *)(v18 + 68) = 0;
            }
            if ( a4 )
            {
              if ( v59 )
                FltReleasePushLock((PULONG_PTR)(a3 + 192));
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140059eb0  push    rbx
0x140059eb2  push    rsi
0x140059eb3  push    r12
0x140059eb5  push    r13
0x140059eb7  push    r15
0x140059eb9  sub     rsp, 140h
0x140059ec0  mov     rax, cs:__security_cookie
0x140059ec7  xor     rax, rsp
0x140059eca  mov     [rsp+168h+var_40], rax
0x140059ed2  mov     r12, [rsp+168h+arg_20]
0x140059eda  mov     r15, r8
0x140059edd  mov     rsi, rdx
0x140059ee0  mov     [rsp+168h+var_140], rcx
0x140059ee5  mov     rbx, rcx
0x140059ee8  xor     edx, edx; Val
0x140059eea  mov     r8d, 0DCh; Size
0x140059ef0  lea     rcx, [rsp+168h+var_128]; void *
0x140059ef5  mov     r13, r9
0x140059ef8  call    memset
0x140059efd  mov     [rsp+168h+var_148], 0
0x140059f02  test    rbx, rbx
0x140059f05  jz      loc_14005A095
0x140059f0b  test    rsi, rsi
0x140059f0e  jz      loc_14005A095
0x140059f14  test    r15, r15
0x140059f17  jz      loc_14005A095
0x140059f1d  test    r13, r13
0x140059f20  jnz     loc_14005A0E3
0x140059f26  mov     rcx, rbx
0x140059f29  mov     [rsp+168h+var_30], rdi
0x140059f31  call    MpGetRequestorProcess
0x140059f36  mov     rdi, rax
0x140059f39  test    rax, rax
0x140059f3c  jz      loc_14005A08D
0x140059f42  mov     [rsp+168h+arg_18], rbp
0x140059f4a  mov     rcx, rax; Process
0x140059f4d  mov     [rsp+168h+var_38], r14
0x140059f55  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140059f5c  nop     dword ptr [rax+rax+00h]
0x140059f61  mov     rcx, rax
0x140059f64  call    MpFileTimeToUlong64
0x140059f69  mov     rcx, rdi; Process
0x140059f6c  mov     rbx, rax
0x140059f6f  call    cs:__imp_PsGetProcessId
0x140059f76  nop     dword ptr [rax+rax+00h]
0x140059f7b  movzx   ecx, word ptr [rsi+2]
0x140059f7f  mov     qword ptr [rsp+168h+var_138], rax
0x140059f84  test    r13, r13
0x140059f87  jnz     loc_14005A2A0
0x140059f8d  xor     r14d, r14d
0x140059f90  xor     eax, eax
0x140059f92  lock cmpxchg [r15+0B0h], r14
0x140059f9b  mov     rbp, rax
0x140059f9e  mov     [rsp+168h+var_128], 0
0x140059fa3  mov     eax, [r15+278h]
0x140059faa  test    eax, eax
0x140059fac  jg      loc_14005A139
0x140059fb2  test    r12, r12
0x140059fb5  jnz     loc_14005A0C1
0x140059fbb  mov     r14, [rsp+168h+var_140]
0x140059fc0  mov     rax, [r14+10h]
0x140059fc4  mov     rsi, [rax+28h]
0x140059fc8  mov     ebp, [rax+18h]
0x140059fcb  add     rbp, rsi
0x140059fce  dec     rbp
0x140059fd1  test    r13, r13
0x140059fd4  jnz     loc_14005A1B5
0x140059fda  lea     rdi, [r15+150h]
0x140059fe1  mov     eax, 1
0x140059fe6  lock xadd [rdi+30h], eax
0x140059feb  inc     eax
0x140059fed  cmp     eax, 1
0x140059ff0  jz      loc_14005A0B6
0x140059ff6  mov     rax, rbp
0x140059ff9  xchg    rax, [rdi+8]
0x140059ffd  nop     dword ptr [rax]
0x14005a000  mov     rax, [rdi+10h]
0x14005a004  cmp     rax, rsi
0x14005a007  jbe     short loc_14005A014
0x14005a009  lfence
0x14005a00c  lock cmpxchg [rdi+10h], rsi
0x14005a012  jnz     short loc_14005A000
0x14005a014  mov     rax, [rdi+18h]
0x14005a018  cmp     rax, rbp
0x14005a01b  jnb     short loc_14005A028
0x14005a01d  lfence
0x14005a020  lock cmpxchg [rdi+18h], rbp
0x14005a026  jnz     short loc_14005A014
0x14005a028  mov     rax, [r14+10h]
0x14005a02c  mov     ecx, [rax+18h]
0x14005a02f  lock add [rdi+20h], rcx
0x14005a034  mov     eax, [rdi+40h]
0x14005a037  mov     rcx, qword ptr [rsp+168h+var_138]
0x14005a03c  test    eax, eax
0x14005a03e  jz      loc_14005A12D
0x14005a044  cmp     ecx, eax
0x14005a046  jnz     loc_14005A12D
0x14005a04c  test    r12, r12
0x14005a04f  jz      short loc_14005A064
0x14005a051  mov     rax, [r12]
0x14005a055  test    rax, rax
0x14005a058  jz      short loc_14005A064
0x14005a05a  lock add [rdi+28h], rax
0x14005a05f  lock or dword ptr [rdi+34h], 4
0x14005a064  movzx   eax, [rsp+168h+var_128]
0x14005a069  test    al, al
0x14005a06b  jnz     loc_14005A1E6
0x14005a071  mov     [rdi+44h], al
0x14005a074  test    r13, r13
0x14005a077  jnz     loc_14005A10A
0x14005a07d  mov     rbp, [rsp+168h+arg_18]
0x14005a085  mov     r14, [rsp+168h+var_38]
0x14005a08d  mov     rdi, [rsp+168h+var_30]
0x14005a095  mov     rcx, [rsp+168h+var_40]
0x14005a09d  xor     rcx, rsp; StackCookie
0x14005a0a0  call    __security_check_cookie
0x14005a0a5  add     rsp, 140h
0x14005a0ac  pop     r15
0x14005a0ae  pop     r13
0x14005a0b0  pop     r12
0x14005a0b2  pop     rsi
0x14005a0b3  pop     rbx
0x14005a0b4  retn
0x14005a0b6  mov     rax, rsi
0x14005a0b9  xchg    rax, [rdi]
0x14005a0bc  jmp     loc_140059FF6
0x14005a0c1  cmp     qword ptr [r12], 0
0x14005a0c6  jz      loc_140059FBB
0x14005a0cc  mov     r14, [rsp+168h+var_140]
0x14005a0d1  mov     rsi, rbp
0x14005a0d4  mov     rax, [r14+10h]
0x14005a0d8  mov     ecx, [rax+18h]
0x14005a0db  sub     rsi, rcx
0x14005a0de  jmp     loc_140059FCE
0x14005a0e3  mov     eax, [r13+0A8h]
0x14005a0ea  test    al, 1
0x14005a0ec  jnz     short loc_14005A095
0x14005a0ee  movzx   eax, word ptr [rsi+2]
0x14005a0f2  test    ax, ax
0x14005a0f5  jz      loc_140059F26
0x14005a0fb  mov     ecx, 0FFFEh
0x14005a100  cmp     ax, cx
0x14005a103  jb      short loc_14005A095
0x14005a105  jmp     loc_140059F26
0x14005a10a  cmp     [rsp+168h+var_148], 0
0x14005a10f  jz      loc_14005A07D
0x14005a115  lea     rcx, [r15+0C0h]; PushLock
0x14005a11c  call    cs:__imp_FltReleasePushLock
0x14005a123  nop     dword ptr [rax+rax+00h]
0x14005a128  jmp     loc_14005A07D
0x14005a12d  mov     [rdi+40h], ecx
0x14005a130  mov     [rdi+38h], rbx
0x14005a134  jmp     loc_14005A04C
0x14005a139  mov     rcx, [rsi+20h]; FileObject
0x14005a13d  call    cs:__imp_FltSupportsStreamHandleContexts
0x14005a144  nop     dword ptr [rax+rax+00h]
0x14005a149  test    al, al
0x14005a14b  jz      loc_140059FB2
0x14005a151  mov     rdx, [rsi+20h]; FileObject
0x14005a155  lea     r8, [rsp+168h+Context]; Context
0x14005a15d  mov     rcx, [rsi+18h]; Instance
0x14005a161  mov     [rsp+168h+Context], r14
0x14005a169  call    cs:__imp_FltGetStreamHandleContext
0x14005a170  nop     dword ptr [rax+rax+00h]
0x14005a175  test    eax, eax
0x14005a177  js      loc_140059FB2
0x14005a17d  mov     r8, [rsp+168h+Context]
0x14005a185  mov     rax, [r8+68h]
0x14005a189  test    rax, rax
0x14005a18c  jz      short loc_14005A1A1
0x14005a18e  movzx   eax, byte ptr [rax]
0x14005a191  mov     r8, [rsp+168h+Context]
0x14005a199  test    al, al
0x14005a19b  jnz     loc_14005A311
0x14005a1a1  mov     rcx, r8; Context
0x14005a1a4  call    cs:__imp_FltReleaseContext
0x14005a1ab  nop     dword ptr [rax+rax+00h]
0x14005a1b0  jmp     loc_140059FB2
0x14005a1b5  lea     rcx, [r15+0C0h]; PushLock
0x14005a1bc  call    cs:__imp_FltAcquirePushLockShared
0x14005a1c3  nop     dword ptr [rax+rax+00h]
0x14005a1c8  mov     rdi, [r15+0D0h]
0x14005a1cf  mov     [rsp+168h+var_148], 1
0x14005a1d4  test    rdi, rdi
0x14005a1d7  jz      loc_140059FDA
0x14005a1dd  add     rdi, 48h ; 'H'
0x14005a1e1  jmp     loc_140059FE1
0x14005a1e6  lea     rcx, [r15+270h]; PushLock
0x14005a1ed  call    cs:__imp_FltAcquirePushLockExclusive
0x14005a1f4  nop     dword ptr [rax+rax+00h]
0x14005a1f9  lea     rdx, [rsp+168h+var_128]
0x14005a1fe  movups  xmm0, xmmword ptr [rdx]
0x14005a201  lea     rcx, [r15+270h]; PushLock
0x14005a208  movups  xmm1, xmmword ptr [rdx+10h]
0x14005a20c  lea     rdx, [rdx+80h]
0x14005a213  mov     rax, [rdx+50h]
0x14005a217  movups  xmmword ptr [rdi+44h], xmm0
0x14005a21b  movups  xmm0, xmmword ptr [rdx-60h]
0x14005a21f  movups  xmmword ptr [rdi+54h], xmm1
0x14005a223  movups  xmm1, xmmword ptr [rdx-50h]
0x14005a227  movups  xmmword ptr [rdi+64h], xmm0
0x14005a22b  movups  xmm0, xmmword ptr [rdx-40h]
0x14005a22f  movups  xmmword ptr [rdi+74h], xmm1
0x14005a233  movups  xmm1, xmmword ptr [rdx-30h]
0x14005a237  movups  xmmword ptr [rdi+84h], xmm0
0x14005a23e  movups  xmm0, xmmword ptr [rdx-20h]
0x14005a242  movups  xmmword ptr [rdi+94h], xmm1
0x14005a249  movups  xmm1, xmmword ptr [rdx-10h]
0x14005a24d  movups  xmmword ptr [rdi+0A4h], xmm0
0x14005a254  sub     rdi, 0FFFFFFFFFFFFFF3Ch
0x14005a25b  movups  xmm0, xmmword ptr [rdx]
0x14005a25e  movups  xmmword ptr [rdi-10h], xmm1
0x14005a262  movups  xmm1, xmmword ptr [rdx+10h]
0x14005a266  movups  xmmword ptr [rdi], xmm0
0x14005a269  movups  xmm0, xmmword ptr [rdx+20h]
0x14005a26d  movups  xmmword ptr [rdi+10h], xmm1
0x14005a271  movups  xmm1, xmmword ptr [rdx+30h]
0x14005a275  movups  xmmword ptr [rdi+20h], xmm0
0x14005a279  movups  xmm0, xmmword ptr [rdx+40h]
0x14005a27d  movups  xmmword ptr [rdi+30h], xmm1
0x14005a281  movups  xmmword ptr [rdi+40h], xmm0
0x14005a285  mov     [rdi+50h], rax
0x14005a289  mov     eax, [rdx+58h]
0x14005a28c  mov     [rdi+58h], eax
0x14005a28f  call    cs:__imp_FltReleasePushLock
0x14005a296  nop     dword ptr [rax+rax+00h]
0x14005a29b  jmp     loc_14005A074
0x14005a2a0  mov     eax, [r13+0A8h]
0x14005a2a7  test    al, 1
0x14005a2a9  jnz     loc_14005A07D
0x14005a2af  dec     cx
0x14005a2b2  mov     eax, 0FFFCh
0x14005a2b7  cmp     cx, ax
0x14005a2ba  jbe     loc_140059F8D
0x14005a2c0  lea     rcx, [r15+0C0h]; PushLock
0x14005a2c7  call    cs:__imp_FltAcquirePushLockShared
0x14005a2ce  nop     dword ptr [rax+rax+00h]
0x14005a2d3  mov     rdx, [r15+0D0h]
0x14005a2da  lea     rax, [r15+0B0h]
0x14005a2e1  test    rdx, rdx
0x14005a2e4  lea     r8, [rdx+20h]
0x14005a2e8  cmovz   r8, rax
0x14005a2ec  xor     r14d, r14d
0x14005a2ef  xor     eax, eax
0x14005a2f1  lock cmpxchg [r8], r14
0x14005a2f6  lea     rcx, [r15+0C0h]; PushLock
0x14005a2fd  mov     rbp, rax
0x14005a300  call    cs:__imp_FltReleasePushLock
0x14005a307  nop     dword ptr [rax+rax+00h]
0x14005a30c  jmp     loc_140059F9E
0x14005a311  mov     rcx, [r8+68h]
0x14005a315  lea     rdx, [rsp+168h+var_128]
0x14005a31a  lea     rdx, [rdx+80h]
0x14005a321  movups  xmm0, xmmword ptr [rcx]
0x14005a324  movups  xmm1, xmmword ptr [rcx+10h]
0x14005a328  movups  xmmword ptr [rdx-80h], xmm0
0x14005a32c  movups  xmm0, xmmword ptr [rcx+20h]
0x14005a330  movups  xmmword ptr [rdx-70h], xmm1
0x14005a334  movups  xmm1, xmmword ptr [rcx+30h]
0x14005a338  movups  xmmword ptr [rdx-60h], xmm0
0x14005a33c  movups  xmm0, xmmword ptr [rcx+40h]
0x14005a340  movups  xmmword ptr [rdx-50h], xmm1
0x14005a344  movups  xmm1, xmmword ptr [rcx+50h]
0x14005a348  movups  xmmword ptr [rdx-40h], xmm0
0x14005a34c  movups  xmm0, xmmword ptr [rcx+60h]
0x14005a350  movups  xmmword ptr [rdx-30h], xmm1
0x14005a354  movups  xmm1, xmmword ptr [rcx+70h]
0x14005a358  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14005a35c  movups  xmmword ptr [rdx-20h], xmm0
0x14005a360  movups  xmmword ptr [rdx-10h], xmm1
0x14005a364  mov     rax, [rcx+50h]
0x14005a368  movups  xmm0, xmmword ptr [rcx]
0x14005a36b  movups  xmm1, xmmword ptr [rcx+10h]
0x14005a36f  movups  xmmword ptr [rdx], xmm0
0x14005a372  movups  xmm0, xmmword ptr [rcx+20h]
0x14005a376  movups  xmmword ptr [rdx+10h], xmm1
0x14005a37a  movups  xmm1, xmmword ptr [rcx+30h]
0x14005a37e  movups  xmmword ptr [rdx+20h], xmm0
0x14005a382  movups  xmm0, xmmword ptr [rcx+40h]
0x14005a386  movups  xmmword ptr [rdx+30h], xmm1
0x14005a38a  movups  xmmword ptr [rdx+40h], xmm0
0x14005a38e  mov     [rdx+50h], rax
0x14005a392  mov     eax, [rcx+58h]
0x14005a395  mov     [rdx+58h], eax
0x14005a398  jmp     loc_14005A1A1
```
