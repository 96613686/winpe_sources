# CSREngine::GetSerializedState(uchar * *,ulong *,ulong)

- ea: `0x18000c580`
- end: `0x18000c800`
- name: `?GetSerializedState@CSREngine@@UEAAJPEAPEAEPEAKK@Z`
- size: `640`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, unsigned __int8 **, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040b8`
- `0x180004312`
- `0x18000c580`
- `0x180022934`
- `0x18007e84c`
- `0x1800a56a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c6b4`

## pseudocode

```c
__int64 __fastcall CSREngine::GetSerializedState(CSREngine *this, unsigned __int8 **a2, unsigned int *a3)
{
  _DWORD *v4; // rdi
  __int64 v5; // rax
  CSRFrontEnd *v6; // rcx
  int PersistentData; // esi
  int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // rax
  size_t v11; // rbx
  unsigned int v12; // r14d
  size_t v13; // r12
  _DWORD *v14; // rax
  int v15; // eax
  _DWORD *v16; // r15
  void *v17; // rdx
  unsigned __int8 *v18; // rdx
  unsigned int v19; // ecx
  unsigned __int8 *v20; // rdx
  size_t Size; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v23; // [rsp+28h] [rbp-28h] BYREF
  void *Src; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 *v25; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 *v26; // [rsp+40h] [rbp-10h] BYREF

  Size = 0;
  v4 = 0;
  v23 = 0;
  Src = 0;
  v26 = 0;
  v25 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v5 = *((_QWORD *)this + 98);
    if ( v5 && (v6 = *(CSRFrontEnd **)(v5 + 40)) != 0 )
    {
      PersistentData = CSRFrontEnd::GetPersistentData(v6, (const unsigned __int8 **)&Src, (unsigned int *)&Size + 1);
      if ( PersistentData >= 0 )
      {
        PersistentData = CMllr_imp::GetPersistentData(
                           *(CMllr_imp **)(*(_QWORD *)(*((_QWORD *)this + 14) + 144LL) + 16LL),
                           (const unsigned __int8 **)&v26,
                           (unsigned int *)&Size);
        if ( PersistentData >= 0 )
        {
          v8 = *((_DWORD *)this + 212);
          v9 = *(_QWORD *)(*((_QWORD *)this + 14) + 80LL);
          v10 = *((_QWORD *)this + 84);
          *(_DWORD *)(v9 + 128) = *((_DWORD *)this + 215);
          *(_QWORD *)v9 = v10;
          *(_DWORD *)(v9 + 28) = v8;
          PersistentData = CAutoDetect::GetPersistentData(
                             *(CAutoDetect **)(*((_QWORD *)this + 14) + 80LL),
                             (const unsigned __int8 **)&v25,
                             &v23);
          if ( PersistentData >= 0 )
          {
            v11 = HIDWORD(Size);
            v12 = 0;
            if ( HIDWORD(Size) )
              v12 = HIDWORD(Size) + 8;
            v13 = v23;
            if ( v23 )
              v12 += v23 + 8;
            if ( (_DWORD)Size )
              v12 += Size + 8;
            v14 = CoTaskMemAlloc(v12 + 16LL);
            v4 = v14;
            if ( v14 )
            {
              memset_0(v14, 0, v12 + 16LL);
              v15 = 0;
              v4[2] = 0;
              v16 = v4 + 4;
              if ( (_DWORD)v11 )
              {
                v17 = Src;
                if ( Src )
                {
                  *v16 = 0;
                  v4[5] = v11;
                  memcpy_0(v4 + 6, v17, v11);
                  v16 = (_DWORD *)((char *)v4 + v11 + 24);
                  v15 = ++v4[2];
                }
              }
              if ( *((_DWORD *)this + 212) == 1 )
              {
                if ( (_DWORD)v13 )
                {
                  v18 = v25;
                  if ( v25 )
                  {
                    *v16 = 1;
                    v16[1] = v13;
                    memcpy_0(v16 + 2, v18, v13);
                    v16 = (_DWORD *)((char *)v16 + v13 + 8);
                    v15 = ++v4[2];
                  }
                }
              }
              v19 = Size;
              if ( (_DWORD)Size )
              {
                v20 = v26;
                if ( v26 )
                {
                  v16[1] = Size;
                  *v16 = 2;
                  memcpy_0(v16 + 2, v20, v19);
                  v15 = ++v4[2];
                }
              }
              if ( v15 )
              {
                PersistentData = 0;
                v4[1] = 1;
                v4[3] = v12;
                *v4 = -1026497184;
                *a2 = (unsigned __int8 *)v4;
                *a3 = v12 + 16;
                return (unsigned int)PersistentData;
              }
            }
            else
            {
              PersistentData = -2147024882;
            }
          }
        }
      }
    }
    else
    {
      PersistentData = -2147201023;
    }
  }
  else
  {
    PersistentData = -2147024809;
  }
  CoTaskMemFree(v4);
  *a2 = 0;
  *a3 = 0;
  if ( PersistentData >= 0 )
    return 1;
  return (unsigned int)PersistentData;
}

```

## disassembly

```asm
0x18000c580  mov     [rsp-38h+arg_0], rbx
0x18000c585  mov     [rsp-38h+arg_10], r8
0x18000c58a  mov     [rsp-38h+arg_8], rdx
0x18000c58f  push    rbp
0x18000c590  push    rsi
0x18000c591  push    rdi
0x18000c592  push    r12
0x18000c594  push    r13
0x18000c596  push    r14
0x18000c598  push    r15
0x18000c59a  mov     rbp, rsp
0x18000c59d  sub     rsp, 50h
0x18000c5a1  xor     r15d, r15d
0x18000c5a4  mov     rax, r8
0x18000c5a7  mov     dword ptr [rbp+Size+4], r15d
0x18000c5ab  mov     r13, rcx
0x18000c5ae  mov     dword ptr [rbp+Size], r15d
0x18000c5b2  mov     edi, r15d
0x18000c5b5  mov     [rbp+var_28], r15d
0x18000c5b9  mov     [rbp+Src], r15
0x18000c5bd  mov     [rbp+var_10], r15
0x18000c5c1  mov     [rbp+var_18], r15
0x18000c5c5  test    rdx, rdx
0x18000c5c8  jz      loc_18000C7C0
0x18000c5ce  test    rax, rax
0x18000c5d1  jz      loc_18000C7C0
0x18000c5d7  mov     [rdx], r15
0x18000c5da  mov     [r8], r15d
0x18000c5dd  mov     rax, [rcx+310h]
0x18000c5e4  test    rax, rax
0x18000c5e7  jz      loc_18000C7B9
0x18000c5ed  mov     rcx, [rax+28h]; this
0x18000c5f1  test    rcx, rcx
0x18000c5f4  jz      loc_18000C7B9
0x18000c5fa  lea     r8, [rbp+Size+4]; unsigned int *
0x18000c5fe  lea     rdx, [rbp+Src]; unsigned __int8 **
0x18000c602  call    ?GetPersistentData@CSRFrontEnd@@QEAAJPEAPEBEPEAK@Z; CSRFrontEnd::GetPersistentData(uchar const * *,ulong *)
0x18000c607  mov     esi, eax
0x18000c609  test    eax, eax
0x18000c60b  js      loc_18000C7C5
0x18000c611  mov     rax, [r13+70h]
0x18000c615  lea     r8, [rbp+Size]; unsigned int *
0x18000c619  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x18000c61d  mov     rcx, [rax+90h]
0x18000c624  mov     rcx, [rcx+10h]; this
0x18000c628  call    ?GetPersistentData@CMllr_imp@@QEAAJPEAPEBEPEAK@Z; CMllr_imp::GetPersistentData(uchar const * *,ulong *)
0x18000c62d  mov     esi, eax
0x18000c62f  test    eax, eax
0x18000c631  js      loc_18000C7C5
0x18000c637  mov     rax, [r13+70h]
0x18000c63b  mov     edx, [r13+35Ch]
0x18000c642  mov     ecx, [r13+350h]
0x18000c649  mov     r8, [rax+50h]
0x18000c64d  mov     rax, [r13+2A0h]
0x18000c654  mov     [r8+80h], edx
0x18000c65b  lea     rdx, [rbp+var_18]; unsigned __int8 **
0x18000c65f  mov     [r8], rax
0x18000c662  mov     [r8+1Ch], ecx
0x18000c666  lea     r8, [rbp+var_28]; unsigned int *
0x18000c66a  mov     rcx, [r13+70h]
0x18000c66e  mov     rcx, [rcx+50h]; this
0x18000c672  call    ?GetPersistentData@CAutoDetect@@QEAAJPEAPEBEPEAK@Z; CAutoDetect::GetPersistentData(uchar const * *,ulong *)
0x18000c677  mov     esi, eax
0x18000c679  test    eax, eax
0x18000c67b  js      loc_18000C7C5
0x18000c681  mov     ebx, dword ptr [rbp+Size+4]
0x18000c684  mov     r14d, r15d
0x18000c687  test    ebx, ebx
0x18000c689  jz      short loc_18000C68F
0x18000c68b  lea     r14d, [rbx+8]
0x18000c68f  mov     r12d, [rbp+var_28]
0x18000c693  test    r12d, r12d
0x18000c696  jz      short loc_18000C69F
0x18000c698  add     r14d, 8
0x18000c69c  add     r14d, r12d
0x18000c69f  mov     eax, dword ptr [rbp+Size]
0x18000c6a2  test    eax, eax
0x18000c6a4  jz      short loc_18000C6AD
0x18000c6a6  add     r14d, 8
0x18000c6aa  add     r14d, eax
0x18000c6ad  mov     r15d, r14d
0x18000c6b0  lea     rcx, [r15+10h]; cb
0x18000c6b4  call    cs:__imp_CoTaskMemAlloc
0x18000c6ba  mov     rdi, rax
0x18000c6bd  test    rax, rax
0x18000c6c0  jnz     short loc_18000C6CF
0x18000c6c2  mov     esi, 8007000Eh
0x18000c6c7  xor     r15d, r15d
0x18000c6ca  jmp     loc_18000C7C5
0x18000c6cf  lea     r8, [r15+10h]; Size
0x18000c6d3  xor     edx, edx; Val
0x18000c6d5  mov     rcx, rdi; void *
0x18000c6d8  call    memset_0
0x18000c6dd  xor     eax, eax
0x18000c6df  mov     dword ptr [rdi+8], 0
0x18000c6e6  lea     r15, [rdi+10h]
0x18000c6ea  test    ebx, ebx
0x18000c6ec  jz      short loc_18000C71E
0x18000c6ee  mov     rdx, [rbp+Src]; Src
0x18000c6f2  test    rdx, rdx
0x18000c6f5  jz      short loc_18000C71E
0x18000c6f7  lea     rcx, [r15+8]; void *
0x18000c6fb  mov     [r15], eax
0x18000c6fe  mov     r8, rbx; Size
0x18000c701  mov     [r15+4], ebx
0x18000c705  call    memcpy_0
0x18000c70a  add     r15, 8
0x18000c70e  mov     ecx, 1
0x18000c713  add     r15, rbx
0x18000c716  add     [rdi+8], ecx
0x18000c719  mov     eax, [rdi+8]
0x18000c71c  jmp     short loc_18000C723
0x18000c71e  mov     ecx, 1
0x18000c723  cmp     [r13+350h], ecx
0x18000c72a  jnz     short loc_18000C75E
0x18000c72c  test    r12d, r12d
0x18000c72f  jz      short loc_18000C75E
0x18000c731  mov     rdx, [rbp+var_18]; Src
0x18000c735  test    rdx, rdx
0x18000c738  jz      short loc_18000C75E
0x18000c73a  lea     rcx, [r15+8]; void *
0x18000c73e  mov     dword ptr [r15], 1
0x18000c745  mov     r8, r12; Size
0x18000c748  mov     [r15+4], r12d
0x18000c74c  call    memcpy_0
0x18000c751  add     r15, 8
0x18000c755  add     r15, r12
0x18000c758  inc     dword ptr [rdi+8]
0x18000c75b  mov     eax, [rdi+8]
0x18000c75e  mov     ecx, dword ptr [rbp+Size]
0x18000c761  test    ecx, ecx
0x18000c763  jz      short loc_18000C78B
0x18000c765  mov     rdx, [rbp+var_10]; Src
0x18000c769  test    rdx, rdx
0x18000c76c  jz      short loc_18000C78B
0x18000c76e  mov     [r15+4], ecx
0x18000c772  mov     r8d, ecx; Size
0x18000c775  lea     rcx, [r15+8]; void *
0x18000c779  mov     dword ptr [r15], 2
0x18000c780  call    memcpy_0
0x18000c785  inc     dword ptr [rdi+8]
0x18000c788  mov     eax, [rdi+8]
0x18000c78b  xor     r15d, r15d
0x18000c78e  test    eax, eax
0x18000c790  jz      short loc_18000C7C5
0x18000c792  mov     rax, [rbp+arg_8]
0x18000c796  mov     esi, r15d
0x18000c799  mov     rcx, [rbp+arg_10]
0x18000c79d  mov     dword ptr [rdi+4], 1
0x18000c7a4  mov     [rdi+0Ch], r14d
0x18000c7a8  mov     dword ptr [rdi], 0C2D0E560h
0x18000c7ae  mov     [rax], rdi
0x18000c7b1  lea     eax, [r14+10h]
0x18000c7b5  mov     [rcx], eax
0x18000c7b7  jmp     short loc_18000C7E6
0x18000c7b9  mov     esi, 80045001h
0x18000c7be  jmp     short loc_18000C7C5
0x18000c7c0  mov     esi, 80070057h
0x18000c7c5  mov     rcx, rdi; pv
0x18000c7c8  call    cs:__imp_CoTaskMemFree
0x18000c7ce  mov     rcx, [rbp+arg_10]
0x18000c7d2  test    esi, esi
0x18000c7d4  mov     rax, [rbp+arg_8]
0x18000c7d8  mov     [rax], r15
0x18000c7db  mov     [rcx], r15d
0x18000c7de  mov     ecx, 1
0x18000c7e3  cmovns  esi, ecx
0x18000c7e6  mov     rbx, [rsp+50h+arg_0]
0x18000c7ee  mov     eax, esi
0x18000c7f0  add     rsp, 50h
0x18000c7f4  pop     r15
0x18000c7f6  pop     r14
0x18000c7f8  pop     r13
0x18000c7fa  pop     r12
0x18000c7fc  pop     rdi
0x18000c7fd  pop     rsi
0x18000c7fe  pop     rbp
0x18000c7ff  retn
```
