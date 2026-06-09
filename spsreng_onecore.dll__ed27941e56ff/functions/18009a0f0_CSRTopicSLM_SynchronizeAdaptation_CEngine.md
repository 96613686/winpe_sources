# CSRTopicSLM::SynchronizeAdaptation(CEngine *)

- ea: `0x18009a0f0`
- end: `0x18009a555`
- name: `?SynchronizeAdaptation@CSRTopicSLM@@QEAAJPEAVCEngine@@@Z`
- size: `1125`
- prototype: `__int64 __fastcall(CSRTopicSLM *__hidden this, struct CEngine *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18009b090`

## callees

- `0x180098c00`
- `0x180098e60`
- `0x180099390`
- `0x18009a0f0`
- `0x18009cd50`
- `0x18009e894`
- `0x18009e8ec`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a3f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009a3f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a52f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a52f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a14f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a14f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a3f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a4db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a4f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a3f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a4db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a4f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009a539`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009a539`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a3c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a40a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a4ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a3c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a40a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009a4ba`

## pseudocode

```c
__int64 __fastcall CSRTopicSLM::SynchronizeAdaptation(CSRTopicSLM *this, struct CEngine *a2)
{
  bool v2; // zf
  __int64 result; // rax
  char v6; // r14
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // edi
  unsigned int v11; // r9d
  const unsigned __int16 *v12; // r10
  unsigned __int16 *v13; // r11
  unsigned __int16 *v14; // rax
  char *v15; // r8
  int v16; // ecx
  int v17; // edx
  char *v18; // rax
  char *v19; // r8
  int v20; // ecx
  int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 i; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // edx
  CPPT *v29; // rcx
  _QWORD *v30; // r8
  __int64 j; // rdx
  const unsigned __int16 *v32; // rsi
  int v33; // eax
  CMRU *v34; // rdi
  unsigned int v35; // r14d
  __int64 v36; // rax
  unsigned __int16 *v37; // [rsp+50h] [rbp-10h] BYREF
  LPVOID v38; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v39; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v40; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF

  v2 = *((_BYTE *)this + 240) == 0;
  v40 = 0;
  pv = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( v2 )
  {
    result = CSRTopicSLM::Initialize(this);
    if ( (int)result < 0 )
      return result;
  }
  v6 = 0;
  WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
  v7 = (_QWORD *)*((_QWORD *)this + 21);
  if ( v7 )
  {
    v8 = v7[6];
    v9 = *(_QWORD *)(v8 + 80) - *(_QWORD *)((char *)v7 + 316);
    if ( !v9 )
      v9 = *(_QWORD *)(v8 + 88) - *(_QWORD *)((char *)v7 + 324);
    if ( !v9 )
      goto LABEL_32;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 2) + 8LL))(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 11),
          &v39);
  if ( v10 >= 0 )
  {
    v10 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, LPVOID *, unsigned int *, _DWORD))this
             + 2))(
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 11),
            2,
            *(unsigned int *)(*((_QWORD *)this + 19) + 632LL),
            0,
            &pv,
            &v39,
            0);
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147200966 )
    {
      v10 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, unsigned __int16 **, unsigned int *, int))this
               + 2))(
              *((_QWORD *)this + 2),
              *((_QWORD *)this + 11),
              3,
              *(unsigned int *)(*((_QWORD *)this + 19) + 632LL),
              0,
              &v37,
              &v39,
              1);
      if ( ((v10 + 0x80000000) & 0x80000000) != 0 || v10 == -2147200966 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *))(**((_QWORD **)this + 2) + 56LL))(
                *((_QWORD *)this + 2),
                *((_QWORD *)this + 11),
                3,
                &v38);
        if ( v10 >= 0 )
        {
          v11 = v39;
          v12 = (const unsigned __int16 *)pv;
          v13 = v37;
          if ( v39 == *((_DWORD *)this + 47) )
          {
            v14 = (unsigned __int16 *)*((_QWORD *)this + 15);
            if ( !v14 )
              goto LABEL_19;
            v15 = (char *)((_BYTE *)pv - (_BYTE *)v14);
            do
            {
              v16 = *(unsigned __int16 *)&v15[(_QWORD)v14];
              v17 = *v14 - v16;
              if ( v17 )
                break;
              ++v14;
            }
            while ( v16 );
            if ( !v17 )
            {
LABEL_19:
              v18 = (char *)*((_QWORD *)this + 16);
              if ( !v18 )
                goto LABEL_32;
              v19 = (char *)((char *)v37 - v18);
              do
              {
                v20 = *(unsigned __int16 *)&v19[(_QWORD)v18];
                v21 = *(unsigned __int16 *)v18 - v20;
                if ( v21 )
                  break;
                v18 += 2;
              }
              while ( v20 );
              if ( !v21 )
                goto LABEL_32;
            }
          }
          v22 = *((_QWORD *)this + 21);
          if ( v22 )
          {
            *(_OWORD *)(v22 + 316) = *(_OWORD *)(*(_QWORD *)(v22 + 48) + 80LL);
            v12 = (const unsigned __int16 *)pv;
            v13 = v37;
            v11 = v39;
          }
          if ( CSRTopicSLM::ReInitialize(this, a2, v12, v13, v11) >= 0 )
          {
LABEL_29:
            v24 = *((_QWORD *)this + 22);
            v6 = 1;
            EnterCriticalSection((LPCRITICAL_SECTION)v24);
            for ( i = 0; i < *(_QWORD *)(v24 + 48); ++i )
              *(_DWORD *)(*(_QWORD *)(v24 + 88) + 4 * i) = -1;
            *(_DWORD *)(v24 + 104) = 0;
            LeaveCriticalSection((LPCRITICAL_SECTION)v24);
            *((_DWORD *)this + 61) = GetTickCount();
LABEL_32:
            EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 22));
            while ( 1 )
            {
              v26 = *((_QWORD *)this + 22);
              v27 = *(int *)(v26 + 104);
              if ( !(_DWORD)v27 )
                break;
              *(_DWORD *)(v26 + 104) = v27 - 1;
              v28 = *(_DWORD *)(*(_QWORD *)(v26 + 96) + 4 * v27 - 4);
              v29 = (CPPT *)*((_QWORD *)this + 19);
              v40 = v28;
              v10 = CPPT::DeleteWord(v29, v28);
              if ( v10 < 0 )
                goto LABEL_47;
              v6 = 1;
            }
LABEL_36:
            v30 = (_QWORD *)*((_QWORD *)this + 22);
            for ( j = 0; j < v30[6]; ++j )
            {
              v32 = *(const unsigned __int16 **)(v30[9] + 8 * j);
              if ( v32 && *(_DWORD *)(v30[11] + 4 * j) == -1 )
              {
                v33 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int64, unsigned int *))(**((_QWORD **)this + 19) + 16LL))(
                        *((_QWORD *)this + 19),
                        v32,
                        *(unsigned __int16 *)(v30[10] + 4 * j),
                        2,
                        &v40);
                v34 = (CMRU *)*((_QWORD *)this + 22);
                if ( v33 < 0 )
                {
                  CMRU::Delete(v34, v32);
                }
                else
                {
                  v35 = v40;
                  EnterCriticalSection((LPCRITICAL_SECTION)v34);
                  v36 = CMRU::Find(v34, v32);
                  if ( v36 >= 0 )
                    *(_DWORD *)(*((_QWORD *)v34 + 11) + 4 * v36) = v35;
                  LeaveCriticalSection((LPCRITICAL_SECTION)v34);
                  v6 = 1;
                }
                goto LABEL_36;
              }
            }
            LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 22));
            v10 = v6 == 0;
            goto LABEL_47;
          }
          CSRTopicSLM::BackoffToCoreLM(this);
          v10 = CSRTopicSLM::ReInitialize(
                  this,
                  *(struct CEngine **)(*((_QWORD *)this + 19) + 24LL),
                  0,
                  0,
                  *((_DWORD *)this + 47));
          if ( v10 >= 0 )
          {
            v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 19) + 24LL) + 16LL);
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, int, int))(*(_QWORD *)v23 + 152LL))(
              v23,
              0,
              0,
              0,
              *((_QWORD *)this + 11),
              6,
              3);
            goto LABEL_29;
          }
        }
      }
    }
  }
LABEL_47:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v38 )
    CoTaskMemFree(v38);
  if ( v37 )
    CoTaskMemFree(v37);
  ReleaseMutex(*((HANDLE *)this + 1));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18009a0f0  mov     [rsp-28h+arg_8], rbx
0x18009a0f5  push    rbp
0x18009a0f6  push    rsi
0x18009a0f7  push    rdi
0x18009a0f8  push    r13
0x18009a0fa  push    r14
0x18009a0fc  mov     rbp, rsp
0x18009a0ff  sub     rsp, 60h
0x18009a103  cmp     byte ptr [rcx+0F0h], 0
0x18009a10a  mov     rsi, rdx
0x18009a10d  mov     rbx, rcx
0x18009a110  mov     [rbp+arg_10], 0
0x18009a117  mov     [rbp+pv], 0
0x18009a11f  mov     [rbp+var_10], 0
0x18009a127  mov     [rbp+var_8], 0
0x18009a12f  mov     [rbp+arg_0], 0
0x18009a136  jnz     short loc_18009A145
0x18009a138  call    ?Initialize@CSRTopicSLM@@QEAAJXZ; CSRTopicSLM::Initialize(void)
0x18009a13d  test    eax, eax
0x18009a13f  js      loc_18009A541
0x18009a145  mov     rcx, [rbx+8]; hHandle
0x18009a149  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009a14c  xor     r14b, r14b
0x18009a14f  call    cs:__imp_WaitForSingleObject
0x18009a155  mov     rcx, [rbx+0A8h]
0x18009a15c  test    rcx, rcx
0x18009a15f  jz      short loc_18009A186
0x18009a161  mov     rdx, [rcx+30h]
0x18009a165  mov     rax, [rdx+50h]
0x18009a169  sub     rax, [rcx+13Ch]
0x18009a170  jnz     short loc_18009A17D
0x18009a172  mov     rax, [rdx+58h]
0x18009a176  sub     rax, [rcx+144h]
0x18009a17d  test    rax, rax
0x18009a180  jz      loc_18009A403
0x18009a186  mov     rcx, [rbx+10h]
0x18009a18a  lea     r8, [rbp+arg_0]
0x18009a18e  mov     rdx, [rbx+58h]
0x18009a192  mov     rax, [rcx]
0x18009a195  mov     rax, [rax+8]
0x18009a199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a19e  mov     edi, eax
0x18009a1a0  test    eax, eax
0x18009a1a2  js      loc_18009A508
0x18009a1a8  mov     rcx, [rbx+10h]
0x18009a1ac  lea     rdx, [rbp+arg_0]
0x18009a1b0  mov     r9, [rbx+98h]
0x18009a1b7  mov     r8d, 2
0x18009a1bd  mov     [rsp+60h+var_28], 0
0x18009a1c5  mov     [rsp+60h+var_30], rdx
0x18009a1ca  lea     rdx, [rbp+pv]
0x18009a1ce  mov     rax, [rcx]
0x18009a1d1  mov     r9d, [r9+278h]
0x18009a1d8  mov     [rsp+60h+var_38], rdx
0x18009a1dd  mov     rdx, [rbx+58h]
0x18009a1e1  mov     rax, [rax]
0x18009a1e4  mov     [rsp+60h+var_40], 0
0x18009a1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a1f1  mov     r13d, 80000000h
0x18009a1f7  mov     edi, eax
0x18009a1f9  add     eax, r13d
0x18009a1fc  test    r13d, eax
0x18009a1ff  jnz     short loc_18009A20D
0x18009a201  cmp     edi, 8004503Ah
0x18009a207  jnz     loc_18009A508
0x18009a20d  mov     rcx, [rbx+10h]
0x18009a211  lea     rdx, [rbp+arg_0]
0x18009a215  mov     r9, [rbx+98h]
0x18009a21c  mov     r8d, 3
0x18009a222  mov     [rsp+60h+var_28], 1
0x18009a22a  mov     [rsp+60h+var_30], rdx
0x18009a22f  lea     rdx, [rbp+var_10]
0x18009a233  mov     rax, [rcx]
0x18009a236  mov     r9d, [r9+278h]
0x18009a23d  mov     [rsp+60h+var_38], rdx
0x18009a242  mov     rdx, [rbx+58h]
0x18009a246  mov     rax, [rax]
0x18009a249  mov     [rsp+60h+var_40], 0
0x18009a251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a256  mov     edi, eax
0x18009a258  add     eax, r13d
0x18009a25b  test    r13d, eax
0x18009a25e  jnz     short loc_18009A26C
0x18009a260  cmp     edi, 8004503Ah
0x18009a266  jnz     loc_18009A508
0x18009a26c  mov     rcx, [rbx+10h]
0x18009a270  lea     r9, [rbp+var_8]
0x18009a274  mov     rdx, [rbx+58h]
0x18009a278  mov     r8d, 3
0x18009a27e  mov     rax, [rcx]
0x18009a281  mov     rax, [rax+38h]
0x18009a285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a28a  mov     edi, eax
0x18009a28c  test    eax, eax
0x18009a28e  js      loc_18009A508
0x18009a294  mov     r9d, [rbp+arg_0]
0x18009a298  mov     r10, [rbp+pv]
0x18009a29c  mov     r11, [rbp+var_10]
0x18009a2a0  cmp     r9d, [rbx+0BCh]
0x18009a2a7  jnz     short loc_18009A302
0x18009a2a9  mov     rax, [rbx+78h]
0x18009a2ad  test    rax, rax
0x18009a2b0  jz      short loc_18009A2D0
0x18009a2b2  mov     r8, r10
0x18009a2b5  sub     r8, rax
0x18009a2b8  movzx   edx, word ptr [rax]
0x18009a2bb  movzx   ecx, word ptr [rax+r8]
0x18009a2c0  sub     edx, ecx
0x18009a2c2  jnz     short loc_18009A2CC
0x18009a2c4  add     rax, 2
0x18009a2c8  test    ecx, ecx
0x18009a2ca  jnz     short loc_18009A2B8
0x18009a2cc  test    edx, edx
0x18009a2ce  jnz     short loc_18009A302
0x18009a2d0  mov     rax, [rbx+80h]
0x18009a2d7  test    rax, rax
0x18009a2da  jz      loc_18009A403
0x18009a2e0  mov     r8, r11
0x18009a2e3  sub     r8, rax
0x18009a2e6  movzx   edx, word ptr [rax]
0x18009a2e9  movzx   ecx, word ptr [rax+r8]
0x18009a2ee  sub     edx, ecx
0x18009a2f0  jnz     short loc_18009A2FA
0x18009a2f2  add     rax, 2
0x18009a2f6  test    ecx, ecx
0x18009a2f8  jnz     short loc_18009A2E6
0x18009a2fa  test    edx, edx
0x18009a2fc  jz      loc_18009A403
0x18009a302  mov     rcx, [rbx+0A8h]
0x18009a309  test    rcx, rcx
0x18009a30c  jz      short loc_18009A32A
0x18009a30e  mov     rax, [rcx+30h]
0x18009a312  movups  xmm0, xmmword ptr [rax+50h]
0x18009a316  movdqu  xmmword ptr [rcx+13Ch], xmm0
0x18009a31e  mov     r10, [rbp+pv]
0x18009a322  mov     r11, [rbp+var_10]
0x18009a326  mov     r9d, [rbp+arg_0]
0x18009a32a  mov     [rsp+60h+var_40], r9d; unsigned int
0x18009a32f  mov     r8, r10; unsigned __int16 *
0x18009a332  mov     r9, r11; unsigned __int16 *
0x18009a335  mov     rdx, rsi; struct CEngine *
0x18009a338  mov     rcx, rbx; this
0x18009a33b  call    ?ReInitialize@CSRTopicSLM@@QEAAJPEAVCEngine@@PEBG1K@Z; CSRTopicSLM::ReInitialize(CEngine *,ushort const *,ushort const *,ulong)
0x18009a340  test    eax, eax
0x18009a342  jns     short loc_18009A3B8
0x18009a344  mov     rcx, rbx; this
0x18009a347  call    ?BackoffToCoreLM@CSRTopicSLM@@AEAAXXZ; CSRTopicSLM::BackoffToCoreLM(void)
0x18009a34c  mov     rdx, [rbx+98h]
0x18009a353  xor     r9d, r9d; unsigned __int16 *
0x18009a356  mov     eax, [rbx+0BCh]
0x18009a35c  xor     r8d, r8d; unsigned __int16 *
0x18009a35f  mov     rcx, rbx; this
0x18009a362  mov     [rsp+60h+var_40], eax; unsigned int
0x18009a366  mov     rdx, [rdx+18h]; struct CEngine *
0x18009a36a  call    ?ReInitialize@CSRTopicSLM@@QEAAJPEAVCEngine@@PEBG1K@Z; CSRTopicSLM::ReInitialize(CEngine *,ushort const *,ushort const *,ulong)
0x18009a36f  mov     edi, eax
0x18009a371  test    eax, eax
0x18009a373  js      loc_18009A508
0x18009a379  mov     rax, [rbx+98h]
0x18009a380  xor     r9d, r9d
0x18009a383  mov     rdx, [rbx+58h]
0x18009a387  xor     r8d, r8d
0x18009a38a  mov     dword ptr [rsp+60h+var_30], 3
0x18009a392  mov     dword ptr [rsp+60h+var_38], 6
0x18009a39a  mov     rcx, [rax+18h]
0x18009a39e  mov     qword ptr [rsp+60h+var_40], rdx
0x18009a3a3  xor     edx, edx
0x18009a3a5  mov     rcx, [rcx+10h]
0x18009a3a9  mov     rax, [rcx]
0x18009a3ac  mov     rax, [rax+98h]
0x18009a3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a3b8  mov     rdi, [rbx+0B0h]
0x18009a3bf  mov     r14b, 1
0x18009a3c2  mov     rcx, rdi; lpCriticalSection
0x18009a3c5  call    cs:__imp_EnterCriticalSection
0x18009a3cb  xor     ecx, ecx
0x18009a3cd  cmp     [rdi+30h], rcx
0x18009a3d1  jle     short loc_18009A3E7
0x18009a3d3  mov     rax, [rdi+58h]
0x18009a3d7  mov     dword ptr [rax+rcx*4], 0FFFFFFFFh
0x18009a3de  inc     rcx
0x18009a3e1  cmp     rcx, [rdi+30h]
0x18009a3e5  jl      short loc_18009A3D3
0x18009a3e7  mov     rcx, rdi; lpCriticalSection
0x18009a3ea  mov     dword ptr [rdi+68h], 0
0x18009a3f1  call    cs:__imp_LeaveCriticalSection
0x18009a3f7  call    cs:__imp_GetTickCount
0x18009a3fd  mov     [rbx+0F4h], eax
0x18009a403  mov     rcx, [rbx+0B0h]; lpCriticalSection
0x18009a40a  call    cs:__imp_EnterCriticalSection
0x18009a410  mov     rdx, [rbx+0B0h]
0x18009a417  movsxd  rcx, dword ptr [rdx+68h]
0x18009a41b  test    ecx, ecx
0x18009a41d  jz      short loc_18009A44B
0x18009a41f  lea     eax, [rcx-1]
0x18009a422  mov     [rdx+68h], eax
0x18009a425  mov     rax, [rdx+60h]
0x18009a429  mov     edx, [rax+rcx*4-4]; unsigned int
0x18009a42d  mov     rcx, [rbx+98h]; this
0x18009a434  mov     [rbp+arg_10], edx
0x18009a437  call    ?DeleteWord@CPPT@@QEAAJI@Z; CPPT::DeleteWord(uint)
0x18009a43c  mov     edi, eax
0x18009a43e  test    eax, eax
0x18009a440  js      loc_18009A508
0x18009a446  mov     r14b, 1
0x18009a449  jmp     short loc_18009A410
0x18009a44b  mov     r8, [rbx+0B0h]
0x18009a452  xor     edx, edx
0x18009a454  cmp     rdx, [r8+30h]
0x18009a458  jge     loc_18009A4F6
0x18009a45e  mov     rax, [r8+48h]
0x18009a462  mov     rsi, [rax+rdx*8]
0x18009a466  test    rsi, rsi
0x18009a469  jz      short loc_18009A475
0x18009a46b  mov     rax, [r8+58h]
0x18009a46f  cmp     dword ptr [rax+rdx*4], 0FFFFFFFFh
0x18009a473  jz      short loc_18009A47A
0x18009a475  inc     rdx
0x18009a478  jmp     short loc_18009A454
0x18009a47a  mov     rcx, [rbx+98h]
0x18009a481  mov     r9d, 2
0x18009a487  mov     r8, [r8+50h]
0x18009a48b  mov     rax, [rcx]
0x18009a48e  movzx   r8d, word ptr [r8+rdx*4]
0x18009a493  lea     rdx, [rbp+arg_10]
0x18009a497  mov     qword ptr [rsp+60h+var_40], rdx
0x18009a49c  mov     rdx, rsi
0x18009a49f  mov     rax, [rax+10h]
0x18009a4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a4a8  mov     rdi, [rbx+0B0h]
0x18009a4af  mov     rcx, rdi; this
0x18009a4b2  test    eax, eax
0x18009a4b4  js      short loc_18009A4E9
0x18009a4b6  mov     r14d, [rbp+arg_10]
0x18009a4ba  call    cs:__imp_EnterCriticalSection
0x18009a4c0  mov     rdx, rsi; unsigned __int16 *
0x18009a4c3  mov     rcx, rdi; this
0x18009a4c6  call    ?Find@CMRU@@AEAA_JPEBG@Z; CMRU::Find(ushort const *)
0x18009a4cb  test    rax, rax
0x18009a4ce  js      short loc_18009A4D8
0x18009a4d0  mov     rdx, [rdi+58h]
0x18009a4d4  mov     [rdx+rax*4], r14d
0x18009a4d8  mov     rcx, rdi; lpCriticalSection
0x18009a4db  call    cs:__imp_LeaveCriticalSection
0x18009a4e1  mov     r14b, 1
0x18009a4e4  jmp     loc_18009A44B
0x18009a4e9  mov     rdx, rsi; unsigned __int16 *
0x18009a4ec  call    ?Delete@CMRU@@QEAAHPEBG@Z; CMRU::Delete(ushort const *)
0x18009a4f1  jmp     loc_18009A44B
0x18009a4f6  mov     rcx, r8; lpCriticalSection
0x18009a4f9  call    cs:__imp_LeaveCriticalSection
0x18009a4ff  xor     edi, edi
0x18009a501  test    r14b, r14b
0x18009a504  setz    dil
0x18009a508  mov     rcx, [rbp+pv]; pv
0x18009a50c  test    rcx, rcx
0x18009a50f  jz      short loc_18009A517
0x18009a511  call    cs:__imp_CoTaskMemFree
0x18009a517  mov     rcx, [rbp+var_8]; pv
0x18009a51b  test    rcx, rcx
0x18009a51e  jz      short loc_18009A526
0x18009a520  call    cs:__imp_CoTaskMemFree
0x18009a526  mov     rcx, [rbp+var_10]; pv
0x18009a52a  test    rcx, rcx
0x18009a52d  jz      short loc_18009A535
0x18009a52f  call    cs:__imp_CoTaskMemFree
0x18009a535  mov     rcx, [rbx+8]; hMutex
0x18009a539  call    cs:__imp_ReleaseMutex
0x18009a53f  mov     eax, edi
0x18009a541  mov     rbx, [rsp+60h+arg_8]
0x18009a549  add     rsp, 60h
0x18009a54d  pop     r14
0x18009a54f  pop     r13
0x18009a551  pop     rdi
0x18009a552  pop     rsi
0x18009a553  pop     rbp
0x18009a554  retn
```
