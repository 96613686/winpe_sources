# CQlFilteringSink::Test(CWbemObject *,QL_LEVEL_1_RPN_EXPRESSION *,CWbemNamespace *)

- ea: `0x18000b4c0`
- end: `0x18000ba79`
- name: `?Test@CQlFilteringSink@@SAHPEAVCWbemObject@@PEAUQL_LEVEL_1_RPN_EXPRESSION@@PEAVCWbemNamespace@@@Z`
- size: `1465`
- prototype: `__int64 __fastcall(struct CWbemObject *, struct QL_LEVEL_1_RPN_EXPRESSION *, struct CWbemNamespace *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b4a0`

## callees

- `0x18000b3a0`
- `0x18000b4c0`
- `0x18000ba80`
- `0x18008846c`
- `0x18008a658`

## import_xrefs

- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b694`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b73c`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b85b`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b8e3`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b90f`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b99e`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b694`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b73c`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b85b`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b8e3`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b90f`
- `wbemcomn!?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z` at `0x18000b99e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b4fe`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b4fe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b541`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b5da`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b541`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000b5da`
- `wbemcomn!GetMemLogObject` at `0x18000b6a6`
- `wbemcomn!GetMemLogObject` at `0x18000b74e`
- `wbemcomn!GetMemLogObject` at `0x18000b7ee`
- `wbemcomn!GetMemLogObject` at `0x18000b869`
- `wbemcomn!GetMemLogObject` at `0x18000b91d`
- `wbemcomn!GetMemLogObject` at `0x18000b9b9`
- `wbemcomn!GetMemLogObject` at `0x18000ba19`
- `wbemcomn!GetMemLogObject` at `0x18000b6a6`
- `wbemcomn!GetMemLogObject` at `0x18000b74e`
- `wbemcomn!GetMemLogObject` at `0x18000b7ee`
- `wbemcomn!GetMemLogObject` at `0x18000b869`
- `wbemcomn!GetMemLogObject` at `0x18000b91d`
- `wbemcomn!GetMemLogObject` at `0x18000b9b9`
- `wbemcomn!GetMemLogObject` at `0x18000ba19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b6b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b75c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b7fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b877`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b92b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b9c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ba27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b6b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b75c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b7fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b877`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b92b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b9c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ba27`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CQlFilteringSink::Test(
        struct CWbemObject *a1,
        struct QL_LEVEL_1_RPN_EXPRESSION *a2,
        struct CWbemNamespace *a3)
{
  unsigned int v5; // r15d
  int v6; // esi
  __int64 v7; // rdi
  _OWORD *v8; // rax
  void *v9; // rbx
  int v10; // eax
  int v12; // r12d
  struct QL_LEVEL_1_TOKEN *v13; // rdx
  int v14; // eax
  struct IWbemPropertySource *v15; // rcx
  unsigned int v16; // esi
  int v17; // ecx
  int v18; // edx
  int v19; // edi
  int v20; // ecx
  __int64 v21; // rax
  int v22; // edi
  void *v23; // rax
  CMemoryLog *v24; // rax
  int v25; // edx
  void *v26; // rax
  CMemoryLog *v27; // rax
  int v28; // ecx
  unsigned int v29; // edx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v31; // rax
  void *v32; // rax
  CMemoryLog *v33; // rax
  void *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  int v37; // [rsp+20h] [rbp-20h] BYREF
  int v38; // [rsp+24h] [rbp-1Ch]
  _OWORD *v39; // [rsp+28h] [rbp-18h]
  int v40; // [rsp+30h] [rbp-10h]
  int pExceptionObject; // [rsp+98h] [rbp+58h] BYREF

  v5 = 32;
  v37 = 32;
  v6 = 128;
  v40 = 128;
  LODWORD(v7) = -1;
  v38 = -1;
  v8 = CWin32DefaultArena::WbemMemAlloc(0x80u);
  v9 = v8;
  v39 = v8;
  if ( !v8 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  v8[3] = 0;
  v8[4] = 0;
  v8[5] = 0;
  v8[6] = 0;
  v8[7] = 0;
  v10 = *((_DWORD *)a2 + 2);
  if ( !v10 )
  {
    CWin32DefaultArena::WbemMemFree(v9);
    return 1;
  }
  v12 = 0;
  if ( v10 > 0 )
  {
    do
    {
      v13 = (struct QL_LEVEL_1_TOKEN *)(*((_QWORD *)a2 + 2) + ((__int64)v12 << 7));
      v14 = *(_DWORD *)v13;
      if ( *(_DWORD *)v13 == 2 )
      {
        v17 = *((_DWORD *)v9 + (unsigned int)v7);
        v38 = v7 - 1;
        v18 = *((_DWORD *)v9 + (unsigned int)(v7 - 1));
        v19 = v7 - 2;
        v38 = v19;
        if ( v17 != 1 )
        {
          if ( v17 == 3 )
            goto LABEL_19;
LABEL_18:
          if ( v18 == 3 )
          {
LABEL_19:
            v7 = (unsigned int)(v19 + 1);
            if ( (_DWORD)v7 == v5 )
            {
              v5 += v6;
              v32 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
              v9 = v32;
              if ( !v32 )
              {
                v35 = GetMemLogObject();
                CMemoryLog::Write(v35, -2);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                    "CX_MemoryException()");
                }
                throw (CX_MemoryException *)&pExceptionObject;
              }
              v37 = v5;
              v39 = v32;
            }
            v38 = v7;
            *((_DWORD *)v9 + v7) = 3;
            goto LABEL_13;
          }
          v7 = (unsigned int)(v19 + 1);
          if ( (_DWORD)v7 == v5 )
          {
            v5 += v6;
            v26 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
            v9 = v26;
            if ( !v26 )
            {
              v31 = GetMemLogObject();
              CMemoryLog::Write(v31, -2);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  11,
                  WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&pExceptionObject;
            }
LABEL_62:
            v37 = v5;
            v39 = v26;
          }
LABEL_26:
          v38 = v7;
          *((_DWORD *)v9 + v7) = 0;
          goto LABEL_13;
        }
        if ( v18 != 1 )
          goto LABEL_18;
        v7 = (unsigned int)(v19 + 1);
        if ( (_DWORD)v7 == v5 )
        {
          v5 += v6;
          v23 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
          v9 = v23;
          if ( !v23 )
          {
            v24 = GetMemLogObject();
            CMemoryLog::Write(v24, -2);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                "CX_MemoryException()");
            }
            throw (CX_MemoryException *)&pExceptionObject;
          }
          goto LABEL_71;
        }
      }
      else
      {
        if ( v14 != 1 )
        {
          if ( v14 != 3 )
          {
            if ( v14 == 4 )
            {
              if ( a1 )
                v15 = (struct CWbemObject *)((char *)a1 + 16);
              else
                v15 = 0;
              pExceptionObject = CQlFilteringSink::EvaluateToken(v15, v13, a3);
              if ( (_DWORD)v7 + 1 == v5 )
              {
                v5 += v6;
                v34 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
                v9 = v34;
                if ( !v34 )
                {
                  v36 = GetMemLogObject();
                  CMemoryLog::Write(v36, -2);
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_s(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      11,
                      WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                      "CX_MemoryException()");
                  }
                  throw (CX_MemoryException *)&pExceptionObject;
                }
                v37 = v5;
                v39 = v34;
              }
              LODWORD(v7) = v7 + 1;
              v38 = v7;
              *((_DWORD *)v9 + (unsigned int)v7) = pExceptionObject;
            }
            goto LABEL_13;
          }
          v28 = *((_DWORD *)v9 + (unsigned int)v7);
          v38 = v7 - 1;
          if ( v28 == 1 )
          {
            v29 = 0;
          }
          else if ( v28 == 3 )
          {
LABEL_49:
            v29 = 3;
          }
          else
          {
            v29 = 1;
          }
          CStack::Push((CStack *)&v37, v29);
          v6 = v40;
          v9 = v39;
          LODWORD(v7) = v38;
          v5 = v37;
          goto LABEL_13;
        }
        v20 = *((_DWORD *)v9 + (unsigned int)v7);
        v21 = (unsigned int)(v7 - 1);
        v22 = v7 - 2;
        v38 = v22;
        if ( v20 != 1 )
        {
          v25 = *((_DWORD *)v9 + v21);
          if ( v25 != 1 )
          {
            if ( v20 == 3 || v25 == 3 )
              goto LABEL_49;
            v7 = (unsigned int)(v22 + 1);
            if ( (_DWORD)v7 == v5 )
            {
              v5 += v6;
              v26 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
              v9 = v26;
              if ( !v26 )
              {
                v27 = GetMemLogObject();
                CMemoryLog::Write(v27, -2);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                    "CX_MemoryException()");
                }
                throw (CX_MemoryException *)&pExceptionObject;
              }
              goto LABEL_62;
            }
            goto LABEL_26;
          }
        }
        v7 = (unsigned int)(v22 + 1);
        if ( (_DWORD)v7 == v5 )
        {
          v5 += v6;
          v23 = CWin32DefaultArena::WbemMemReAlloc(v9, 4LL * v5);
          v9 = v23;
          if ( !v23 )
          {
            v33 = GetMemLogObject();
            CMemoryLog::Write(v33, -2);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids,
                "CX_MemoryException()");
            }
            throw (CX_MemoryException *)&pExceptionObject;
          }
LABEL_71:
          v37 = v5;
          v39 = v23;
        }
      }
      v38 = v7;
      *((_DWORD *)v9 + v7) = 1;
LABEL_13:
      ++v12;
    }
    while ( v12 < *((_DWORD *)a2 + 2) );
  }
  v16 = *((_DWORD *)v9 + (unsigned int)v7);
  v38 = v7 - 1;
  CWin32DefaultArena::WbemMemFree(v9);
  if ( v16 == 3 )
    return 0;
  else
    return v16;
}

```

## disassembly

```asm
0x18000b4c0  mov     [rsp-38h+arg_0], rbx
0x18000b4c5  mov     [rsp-38h+arg_10], r8
0x18000b4ca  push    rbp
0x18000b4cb  push    rsi
0x18000b4cc  push    rdi
0x18000b4cd  push    r12
0x18000b4cf  push    r13
0x18000b4d1  push    r14
0x18000b4d3  push    r15
0x18000b4d5  mov     rbp, rsp
0x18000b4d8  sub     rsp, 40h
0x18000b4dc  mov     r14, rdx
0x18000b4df  mov     r13, rcx
0x18000b4e2  mov     r15d, 20h ; ' '
0x18000b4e8  mov     [rbp+var_20], r15d
0x18000b4ec  mov     esi, 80h
0x18000b4f1  mov     [rbp+var_10], esi
0x18000b4f4  mov     edi, 0FFFFFFFFh
0x18000b4f9  mov     [rbp+var_1C], edi
0x18000b4fc  mov     ecx, esi
0x18000b4fe  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000b504  mov     rbx, rax
0x18000b507  mov     [rbp+var_18], rax
0x18000b50b  test    rax, rax
0x18000b50e  jz      loc_18000B7EE
0x18000b514  xorps   xmm0, xmm0
0x18000b517  movups  xmmword ptr [rax], xmm0
0x18000b51a  movups  xmmword ptr [rax+10h], xmm0
0x18000b51e  movups  xmmword ptr [rax+20h], xmm0
0x18000b522  movups  xmmword ptr [rax+30h], xmm0
0x18000b526  movups  xmmword ptr [rax+40h], xmm0
0x18000b52a  movups  xmmword ptr [rax+50h], xmm0
0x18000b52e  movups  xmmword ptr [rax+60h], xmm0
0x18000b532  movups  xmmword ptr [rax+70h], xmm0
0x18000b536  mov     eax, [r14+8]
0x18000b53a  test    eax, eax
0x18000b53c  jnz     short loc_18000B564
0x18000b53e  mov     rcx, rbx
0x18000b541  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b547  mov     eax, 1
0x18000b54c  mov     rbx, [rsp+40h+arg_0]
0x18000b554  add     rsp, 40h
0x18000b558  pop     r15
0x18000b55a  pop     r14
0x18000b55c  pop     r13
0x18000b55e  pop     r12
0x18000b560  pop     rdi
0x18000b561  pop     rsi
0x18000b562  pop     rbp
0x18000b563  retn
0x18000b564  xor     r12d, r12d
0x18000b567  test    eax, eax
0x18000b569  jle     short loc_18000B5CD
0x18000b56b  movsxd  rdx, r12d
0x18000b56e  shl     rdx, 7
0x18000b572  add     rdx, [r14+10h]; struct QL_LEVEL_1_TOKEN *
0x18000b576  mov     eax, [rdx]
0x18000b578  cmp     eax, 2
0x18000b57b  jz      short loc_18000B5EC
0x18000b57d  cmp     eax, 1
0x18000b580  jz      loc_18000B62D
0x18000b586  cmp     eax, 3
0x18000b589  jz      loc_18000B7AE
0x18000b58f  cmp     eax, 4
0x18000b592  jnz     short loc_18000B5C4
0x18000b594  test    r13, r13
0x18000b597  jz      loc_18000B98A
0x18000b59d  lea     rcx, [r13+10h]; struct IWbemPropertySource *
0x18000b5a1  mov     r8, [rbp+arg_10]; struct CWbemNamespace *
0x18000b5a5  call    ?EvaluateToken@CQlFilteringSink@@SAHPEAUIWbemPropertySource@@AEAUQL_LEVEL_1_TOKEN@@PEAVCWbemNamespace@@@Z; CQlFilteringSink::EvaluateToken(IWbemPropertySource *,QL_LEVEL_1_TOKEN &,CWbemNamespace *)
0x18000b5aa  mov     [rbp+pExceptionObject], eax
0x18000b5ad  lea     ecx, [rdi+1]
0x18000b5b0  cmp     ecx, r15d
0x18000b5b3  jz      loc_18000B991
0x18000b5b9  inc     edi
0x18000b5bb  mov     [rbp+var_1C], edi
0x18000b5be  mov     ecx, [rbp+pExceptionObject]
0x18000b5c1  mov     [rbx+rdi*4], ecx
0x18000b5c4  inc     r12d
0x18000b5c7  cmp     r12d, [r14+8]
0x18000b5cb  jl      short loc_18000B56B
0x18000b5cd  mov     eax, edi
0x18000b5cf  mov     esi, [rbx+rax*4]
0x18000b5d2  dec     edi
0x18000b5d4  mov     [rbp+var_1C], edi
0x18000b5d7  mov     rcx, rbx
0x18000b5da  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000b5e0  cmp     esi, 3
0x18000b5e3  jz      short loc_18000B626
0x18000b5e5  mov     eax, esi
0x18000b5e7  jmp     loc_18000B54C
0x18000b5ec  mov     eax, edi
0x18000b5ee  mov     ecx, [rbx+rax*4]
0x18000b5f1  lea     eax, [rdi-1]
0x18000b5f4  mov     [rbp+var_1C], eax
0x18000b5f7  mov     edx, [rbx+rax*4]
0x18000b5fa  add     edi, 0FFFFFFFEh
0x18000b5fd  mov     [rbp+var_1C], edi
0x18000b600  cmp     ecx, 1
0x18000b603  jz      short loc_18000B67B
0x18000b605  cmp     ecx, 3
0x18000b608  jz      short loc_18000B60F
0x18000b60a  cmp     edx, 3
0x18000b60d  jnz     short loc_18000B661
0x18000b60f  inc     edi
0x18000b611  cmp     edi, r15d
0x18000b614  jz      loc_18000B8D6
0x18000b61a  mov     [rbp+var_1C], edi
0x18000b61d  mov     dword ptr [rbx+rdi*4], 3
0x18000b624  jmp     short loc_18000B5C4
0x18000b626  xor     eax, eax
0x18000b628  jmp     loc_18000B54C
0x18000b62d  mov     eax, edi
0x18000b62f  mov     ecx, [rbx+rax*4]
0x18000b632  lea     eax, [rdi-1]
0x18000b635  mov     [rbp+var_1C], eax
0x18000b638  add     edi, 0FFFFFFFEh
0x18000b63b  mov     [rbp+var_1C], edi
0x18000b63e  cmp     ecx, 1
0x18000b641  jnz     loc_18000B706
0x18000b647  inc     edi
0x18000b649  cmp     edi, r15d
0x18000b64c  jz      loc_18000B902
0x18000b652  mov     [rbp+var_1C], edi
0x18000b655  mov     dword ptr [rbx+rdi*4], 1
0x18000b65c  jmp     loc_18000B5C4
0x18000b661  inc     edi
0x18000b663  cmp     edi, r15d
0x18000b666  jz      loc_18000B84E
0x18000b66c  mov     [rbp+var_1C], edi
0x18000b66f  mov     dword ptr [rbx+rdi*4], 0
0x18000b676  jmp     loc_18000B5C4
0x18000b67b  cmp     edx, 1
0x18000b67e  jnz     short loc_18000B60A
0x18000b680  inc     edi
0x18000b682  cmp     edi, r15d
0x18000b685  jnz     short loc_18000B652
0x18000b687  add     r15d, esi
0x18000b68a  mov     edx, r15d
0x18000b68d  shl     rdx, 2
0x18000b691  mov     rcx, rbx
0x18000b694  call    cs:__imp_?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z; CWin32DefaultArena::WbemMemReAlloc(void *,unsigned __int64)
0x18000b69a  mov     rbx, rax
0x18000b69d  test    rax, rax
0x18000b6a0  jnz     loc_18000B97D
0x18000b6a6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b6ac  mov     edx, 0FFFFFFFEh
0x18000b6b1  mov     rcx, rax
0x18000b6b4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b6ba  lea     rax, WPP_GLOBAL_Control
0x18000b6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6c8  cmp     rcx, rax
0x18000b6cb  jz      short loc_18000B6F5
0x18000b6cd  test    byte ptr [rcx+1Ch], 1
0x18000b6d1  jz      short loc_18000B6F5
0x18000b6d3  cmp     byte ptr [rcx+19h], 2
0x18000b6d7  jb      short loc_18000B6F5
0x18000b6d9  mov     edx, 0Bh
0x18000b6de  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000b6e5  lea     r8, WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids
0x18000b6ec  mov     rcx, [rcx+10h]
0x18000b6f0  call    WPP_SF_s
0x18000b6f5  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000b6fc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b700  call    _CxxThrowException_0
0x18000b706  mov     edx, [rbx+rax*4]
0x18000b709  cmp     edx, 1
0x18000b70c  jz      loc_18000B647
0x18000b712  cmp     ecx, 3
0x18000b715  jz      loc_18000B7E3
0x18000b71b  cmp     edx, 3
0x18000b71e  jz      loc_18000B7E3
0x18000b724  inc     edi
0x18000b726  cmp     edi, r15d
0x18000b729  jnz     loc_18000B66C
0x18000b72f  add     r15d, esi
0x18000b732  mov     edx, r15d
0x18000b735  shl     rdx, 2
0x18000b739  mov     rcx, rbx
0x18000b73c  call    cs:__imp_?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z; CWin32DefaultArena::WbemMemReAlloc(void *,unsigned __int64)
0x18000b742  mov     rbx, rax
0x18000b745  test    rax, rax
0x18000b748  jnz     loc_18000B8C9
0x18000b74e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b754  mov     edx, 0FFFFFFFEh
0x18000b759  mov     rcx, rax
0x18000b75c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b762  lea     rax, WPP_GLOBAL_Control
0x18000b769  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b770  cmp     rcx, rax
0x18000b773  jz      short loc_18000B79D
0x18000b775  test    byte ptr [rcx+1Ch], 1
0x18000b779  jz      short loc_18000B79D
0x18000b77b  cmp     byte ptr [rcx+19h], 2
0x18000b77f  jb      short loc_18000B79D
0x18000b781  mov     edx, 0Bh
0x18000b786  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000b78d  lea     r8, WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids
0x18000b794  mov     rcx, [rcx+10h]
0x18000b798  call    WPP_SF_s
0x18000b79d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000b7a4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b7a8  call    _CxxThrowException_0
0x18000b7ae  mov     eax, edi
0x18000b7b0  mov     ecx, [rbx+rax*4]
0x18000b7b3  dec     edi
0x18000b7b5  mov     [rbp+var_1C], edi
0x18000b7b8  cmp     ecx, 1
0x18000b7bb  jz      short loc_18000B7EA
0x18000b7bd  cmp     ecx, 3
0x18000b7c0  jz      short loc_18000B7E3
0x18000b7c2  mov     edx, 1; unsigned int
0x18000b7c7  lea     rcx, [rbp+var_20]; this
0x18000b7cb  call    ?Push@CStack@@QEAAXK@Z; CStack::Push(ulong)
0x18000b7d0  mov     esi, [rbp+var_10]
0x18000b7d3  mov     rbx, [rbp+var_18]
0x18000b7d7  mov     edi, [rbp+var_1C]
0x18000b7da  mov     r15d, [rbp+var_20]
0x18000b7de  jmp     loc_18000B5C4
0x18000b7e3  mov     edx, 3
0x18000b7e8  jmp     short loc_18000B7C7
0x18000b7ea  xor     edx, edx
0x18000b7ec  jmp     short loc_18000B7C7
0x18000b7ee  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b7f4  mov     edx, 0FFFFFFFEh
0x18000b7f9  mov     rcx, rax
0x18000b7fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b802  lea     rax, WPP_GLOBAL_Control
0x18000b809  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b810  cmp     rcx, rax
0x18000b813  jz      short loc_18000B83D
0x18000b815  test    byte ptr [rcx+1Ch], 1
0x18000b819  jz      short loc_18000B83D
0x18000b81b  cmp     byte ptr [rcx+19h], 2
0x18000b81f  jb      short loc_18000B83D
0x18000b821  mov     edx, 0Ah
0x18000b826  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000b82d  lea     r8, WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids
0x18000b834  mov     rcx, [rcx+10h]
0x18000b838  call    WPP_SF_s
0x18000b83d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000b844  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b848  call    _CxxThrowException_0
0x18000b84e  add     r15d, esi
0x18000b851  mov     edx, r15d
0x18000b854  shl     rdx, 2
0x18000b858  mov     rcx, rbx
0x18000b85b  call    cs:__imp_?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z; CWin32DefaultArena::WbemMemReAlloc(void *,unsigned __int64)
0x18000b861  mov     rbx, rax
0x18000b864  test    rax, rax
0x18000b867  jnz     short loc_18000B8C9
0x18000b869  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b86f  mov     edx, 0FFFFFFFEh
0x18000b874  mov     rcx, rax
0x18000b877  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b87d  lea     rax, WPP_GLOBAL_Control
0x18000b884  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b88b  cmp     rcx, rax
0x18000b88e  jz      short loc_18000B8B8
0x18000b890  test    byte ptr [rcx+1Ch], 1
0x18000b894  jz      short loc_18000B8B8
0x18000b896  cmp     byte ptr [rcx+19h], 2
0x18000b89a  jb      short loc_18000B8B8
0x18000b89c  mov     edx, 0Bh
0x18000b8a1  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000b8a8  lea     r8, WPP_0bde2fe716c2386d25030eaa999f487c_Traceguids
0x18000b8af  mov     rcx, [rcx+10h]
0x18000b8b3  call    WPP_SF_s
0x18000b8b8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000b8bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000b8c3  call    _CxxThrowException_0
0x18000b8c9  mov     [rbp+var_20], r15d
0x18000b8cd  mov     [rbp+var_18], rax
0x18000b8d1  jmp     loc_18000B66C
0x18000b8d6  add     r15d, esi
0x18000b8d9  mov     edx, r15d
0x18000b8dc  shl     rdx, 2
0x18000b8e0  mov     rcx, rbx
0x18000b8e3  call    cs:__imp_?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z; CWin32DefaultArena::WbemMemReAlloc(void *,unsigned __int64)
0x18000b8e9  mov     rbx, rax
0x18000b8ec  test    rax, rax
0x18000b8ef  jz      loc_18000B9B9
0x18000b8f5  mov     [rbp+var_20], r15d
0x18000b8f9  mov     [rbp+var_18], rax
0x18000b8fd  jmp     loc_18000B61A
0x18000b902  add     r15d, esi
0x18000b905  mov     edx, r15d
0x18000b908  shl     rdx, 2
0x18000b90c  mov     rcx, rbx
0x18000b90f  call    cs:__imp_?WbemMemReAlloc@CWin32DefaultArena@@SAPEAXPEAX_K@Z; CWin32DefaultArena::WbemMemReAlloc(void *,unsigned __int64)
0x18000b915  mov     rbx, rax
0x18000b918  test    rax, rax
0x18000b91b  jnz     short loc_18000B97D
0x18000b91d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b923  mov     edx, 0FFFFFFFEh
0x18000b928  mov     rcx, rax
0x18000b92b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b931  lea     rax, WPP_GLOBAL_Control
0x18000b938  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b93f  cmp     rcx, rax
  ... truncated ...
```
