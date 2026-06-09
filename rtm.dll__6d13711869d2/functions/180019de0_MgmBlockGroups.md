# MgmBlockGroups

- ea: `0x180019de0`
- end: `0x18001a34e`
- name: `MgmBlockGroups`
- size: `1390`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x18001958c`
- `0x180019de0`
- `0x18001aa4c`
- `0x18001b548`
- `0x18001bc4c`
- `0x18001db88`
- `0x18001dcbc`
- `0x18001e374`
- `0x18001e4b0`
- `0x18001f11c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a0a6`
- `KERNEL32!HeapFree` at `0x18001a0a6`

## string_xrefs

- `0x18001a192`: `Invoked Prune Alert for protocol %x, %x`
- `0x18001a133`: `Protocol (%d, %d) not present for interface %d`

## pseudocode

```c
__int64 __fastcall MgmBlockGroups(unsigned int a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  __int64 v9; // rsi
  _DWORD *v10; // r14
  __int64 v11; // rdi
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // ecx
  _DWORD *v17; // rax
  _DWORD *v18; // rbx
  int v19; // edx
  _QWORD *v20; // rsi
  _QWORD *v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 ProtocolEntry; // rax
  __int64 v26; // rsi
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[4]; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v28 = 0;
  v31 = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"ENTERED MgmBlockGroups (%lx - %lx) on %lx", a1, a2, a3);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v33);
  }
  AcquireReadLock(&qword_18002B9B8);
  v9 = 32LL * (a3 % dword_18002B92C);
  v32 = v9;
  AcquireReadLock((char *)qword_18002B9E8 + v9 + 16);
  v30 = 0;
  if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v9, a3, a4, &v30) && (v10 = v30) != 0 )
  {
    AcquireWriteLock(&qword_18002BA10);
    MergeTempAndMasterGroupLists(&qword_18002BA00);
    ReleaseWriteLock(&qword_18002BA10);
    AcquireReadLock(&qword_18002BA30);
    v11 = qword_18002BA20;
    if ( (__int64 *)qword_18002BA20 != &qword_18002BA20 )
    {
      v12 = (unsigned __int8)a2;
      LODWORD(v30) = (unsigned __int8)a2;
      while ( 1 )
      {
        v13 = *(_DWORD *)(v11 + 32);
        v14 = v13 & 0xFF00;
        v15 = (unsigned __int8)v13 - v12;
        if ( (unsigned __int8)v13 == v12 )
        {
          v15 = v14 - (a2 & 0xFF00);
          if ( v14 == (a2 & 0xFF00) )
          {
            v15 = (v13 & 0xFF0000) - (a2 & 0xFF0000);
            if ( (v13 & 0xFF0000) == (a2 & 0xFF0000) )
              v15 = ((v13 >> 8) & 0xFF0000) - ((a2 >> 8) & 0xFF0000);
          }
        }
        if ( v15 > 0 )
          break;
        v16 = (unsigned __int8)v13 - (unsigned __int8)a1;
        if ( !v16 )
        {
          v16 = v14 - (a1 & 0xFF00);
          if ( v14 == (a1 & 0xFF00) )
          {
            v16 = (v13 & 0xFF0000) - (a1 & 0xFF0000);
            if ( (v13 & 0xFF0000) == (a1 & 0xFF0000) )
              v16 = ((v13 >> 8) & 0xFF0000) - ((a1 >> 8) & 0xFF0000);
          }
        }
        if ( v16 >= 0 )
        {
          AcquireWriteLock(v11 + 40);
          MergeTempAndMasterSourceLists(v11);
          v17 = (_DWORD *)(v11 + 72);
          v18 = *(_DWORD **)(v11 + 72);
          while ( 1 )
          {
            if ( v18 == v17 )
            {
              ReleaseWriteLock(v11 + 40);
              break;
            }
            if ( (unsigned int)FindOutInterfaceEntry(
                                 (int)v18 + 48,
                                 v10[4],
                                 v10[5],
                                 v10[6],
                                 v10[7],
                                 (__int64)v29,
                                 (__int64)&v31) )
              ScopeIfAndInvokeCallbacks(v11, v18, v31);
            if ( v18[28] )
            {
              v19 = v10[4];
              if ( v18[28] == v19 && v18[29] == v10[5] )
              {
                v20 = v18 + 22;
                if ( (_QWORD *)*v20 == v20 )
                  goto LABEL_41;
                while ( 1 )
                {
                  v21 = (_QWORD *)*v20;
                  if ( (_QWORD *)*v20 == v20 )
                    break;
                  if ( (_QWORD *)v21[1] != v20 || (v22 = *v21, *(_QWORD **)(*v21 + 8LL) != v21) )
                    __fastfail(3u);
                  *v20 = v22;
                  *(_QWORD *)(v22 + 8) = v20;
                  HeapFree(hHeap, 0, v21);
                }
                v18[20] = 0;
              }
              else
              {
                if ( !(unsigned int)FindOutInterfaceEntry(
                                      (int)v18 + 88,
                                      v19,
                                      v10[5],
                                      v10[6],
                                      v10[7],
                                      (__int64)v29,
                                      (__int64)&v31) )
                  goto LABEL_41;
                DeleteOutInterfaceEntry(v31, v23);
                if ( v18[20]-- != 1 )
                  goto LABEL_40;
              }
              ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, (unsigned int)v18[34], (unsigned int)v18[35]);
              v26 = ProtocolEntry;
              if ( ProtocolEntry )
              {
                if ( *(_QWORD *)(ProtocolEntry + 56) )
                {
                  if ( qword_18002B8A8 )
                  {
                    LOWORD(v33) = 0;
                    FormatRRASErrorString(
                      &v33,
                      L"Invoked Prune Alert for protocol %x, %x",
                      *(unsigned int *)(ProtocolEntry + 16),
                      *(unsigned int *)(ProtocolEntry + 20));
                    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                      gMgmEtwContext,
                      qword_18002B8A8,
                      &v33);
                  }
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, unsigned int *))(v26 + 56))(
                    (unsigned int)v18[26],
                    (unsigned int)v18[27],
                    *(unsigned int *)(v11 + 32),
                    *(unsigned int *)(v11 + 36),
                    v18[28],
                    v18[29],
                    0,
                    &v28);
                }
LABEL_40:
                AddMfeToForwarder(v11, v18, v28);
                goto LABEL_41;
              }
              if ( qword_18002B8A8 )
              {
                LOWORD(v33) = 0;
                LODWORD(v27) = a3;
                FormatRRASErrorString(
                  &v33,
                  L"Protocol (%d, %d) not present for interface %d",
                  (unsigned int)v18[34],
                  (unsigned int)v18[35],
                  v27);
                ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v33);
              }
            }
LABEL_41:
            v18 = *(_DWORD **)v18;
            v17 = (_DWORD *)(v11 + 72);
          }
        }
        v11 = *(_QWORD *)v11;
        if ( (__int64 *)v11 == &qword_18002BA20 )
          break;
        v12 = (int)v30;
      }
      v9 = v32;
    }
    ReleaseReadLock(&qword_18002BA30);
  }
  else if ( qword_18002B8A8 )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"Interface %lx not found", a3);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v33);
  }
  ReleaseReadLock((char *)qword_18002B9E8 + v9 + 16);
  InvokeOutstandingCallbacks();
  ReleaseReadLock(&qword_18002B9B8);
  LeaveMgmWorker();
  if ( qword_18002B8A8 )
  {
    LOWORD(v33) = 0;
    LODWORD(v27) = a3;
    FormatRRASErrorString(&v33, L"LEAVING MgmBlockGroups (%lx - %lx) on %lx\n", a1, a2, v27);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v33);
  }
  return 0;
}

```

## disassembly

```asm
0x180019de0  mov     [rsp-8+arg_18], rbx
0x180019de5  push    rbp
0x180019de6  push    rsi
0x180019de7  push    rdi
0x180019de8  push    r12
0x180019dea  push    r13
0x180019dec  push    r14
0x180019dee  push    r15
0x180019df0  lea     rbp, [rsp-780h]
0x180019df8  sub     rsp, 880h
0x180019dff  mov     rax, cs:__security_cookie
0x180019e06  xor     rax, rsp
0x180019e09  mov     [rbp+7B0h+var_40], rax
0x180019e10  xor     edi, edi
0x180019e12  mov     r13d, r8d
0x180019e15  mov     r15d, edx
0x180019e18  mov     [rsp+8B0h+var_860], edi
0x180019e1c  mov     r12d, ecx
0x180019e1f  mov     [rsp+8B0h+var_850], rdi
0x180019e24  xor     edx, edx; Val
0x180019e26  mov     [rsp+8B0h+var_840], edi
0x180019e2a  mov     r8d, 7FCh; Size
0x180019e30  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180019e35  mov     ebx, r9d
0x180019e38  call    memset_0
0x180019e3d  call    EnterMgmAPI
0x180019e42  test    eax, eax
0x180019e44  jnz     short loc_180019E50
0x180019e46  mov     eax, 3EBh
0x180019e4b  jmp     loc_18001A324
0x180019e50  cmp     cs:qword_18002B8A8, rdi
0x180019e57  jz      short loc_180019E99
0x180019e59  mov     r9d, r15d
0x180019e5c  mov     word ptr [rsp+8B0h+var_840], di
0x180019e61  mov     r8d, r12d
0x180019e64  mov     dword ptr [rsp+8B0h+var_890], r13d
0x180019e69  lea     rdx, aEnteredMgmbloc; "ENTERED MgmBlockGroups (%lx - %lx) on %"...
0x180019e70  lea     rcx, [rsp+8B0h+var_840]
0x180019e75  call    FormatRRASErrorString
0x180019e7a  mov     rdx, cs:qword_18002B8A8
0x180019e81  lea     r8, [rsp+8B0h+var_840]
0x180019e86  mov     rcx, cs:gMgmEtwContext
0x180019e8d  mov     rax, cs:gMgmTemplateFunc
0x180019e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e99  lea     rcx, qword_18002B9B8
0x180019ea0  call    AcquireReadLock
0x180019ea5  mov     rcx, cs:qword_18002B9E8
0x180019eac  xor     edx, edx
0x180019eae  mov     eax, r13d
0x180019eb1  add     rcx, 10h
0x180019eb5  div     cs:dword_18002B92C
0x180019ebb  mov     esi, edx
0x180019ebd  shl     rsi, 5
0x180019ec1  add     rcx, rsi
0x180019ec4  mov     [rsp+8B0h+var_848], rsi
0x180019ec9  call    AcquireReadLock
0x180019ece  mov     rcx, cs:qword_18002B9E8
0x180019ed5  lea     r9, [rsp+8B0h+var_858]
0x180019eda  add     rcx, rsi
0x180019edd  mov     [rsp+8B0h+var_858], rdi
0x180019ee2  mov     r8d, ebx
0x180019ee5  mov     edx, r13d
0x180019ee8  call    FindIfEntry
0x180019eed  test    eax, eax
0x180019eef  jz      loc_18001A26F
0x180019ef5  mov     r14, [rsp+8B0h+var_858]
0x180019efa  test    r14, r14
0x180019efd  jz      loc_18001A26F
0x180019f03  lea     rcx, qword_18002BA10
0x180019f0a  call    AcquireWriteLock
0x180019f0f  lea     rcx, qword_18002BA00
0x180019f16  call    MergeTempAndMasterGroupLists
0x180019f1b  lea     rcx, qword_18002BA10
0x180019f22  call    ReleaseWriteLock
0x180019f27  lea     rcx, qword_18002BA30
0x180019f2e  call    AcquireReadLock
0x180019f33  mov     rdi, cs:qword_18002BA20
0x180019f3a  lea     rax, qword_18002BA20
0x180019f41  cmp     rdi, rax
0x180019f44  jz      loc_18001A25F
0x180019f4a  movzx   eax, r15b
0x180019f4e  mov     r11d, 0FF00h
0x180019f54  mov     dword ptr [rsp+8B0h+var_858], eax
0x180019f58  mov     r10d, 0FF0000h
0x180019f5e  mov     r8d, [rdi+20h]
0x180019f62  mov     r9d, r8d
0x180019f65  movzx   ecx, r8b
0x180019f69  and     r9d, r11d
0x180019f6c  mov     edx, ecx
0x180019f6e  sub     edx, eax
0x180019f70  jnz     short loc_180019FA3
0x180019f72  mov     eax, r15d
0x180019f75  mov     edx, r9d
0x180019f78  and     eax, r11d
0x180019f7b  sub     edx, eax
0x180019f7d  jnz     short loc_180019FA3
0x180019f7f  mov     edx, r8d
0x180019f82  mov     eax, r15d
0x180019f85  and     edx, r10d
0x180019f88  and     eax, r10d
0x180019f8b  sub     edx, eax
0x180019f8d  jnz     short loc_180019FA3
0x180019f8f  mov     edx, r8d
0x180019f92  mov     eax, r15d
0x180019f95  shr     edx, 8
0x180019f98  shr     eax, 8
0x180019f9b  and     edx, r10d
0x180019f9e  and     eax, r10d
0x180019fa1  sub     edx, eax
0x180019fa3  test    edx, edx
0x180019fa5  jg      loc_18001A25A
0x180019fab  movzx   eax, r12b
0x180019faf  sub     ecx, eax
0x180019fb1  jnz     short loc_180019FE4
0x180019fb3  mov     eax, r12d
0x180019fb6  mov     ecx, r9d
0x180019fb9  and     eax, r11d
0x180019fbc  sub     ecx, eax
0x180019fbe  jnz     short loc_180019FE4
0x180019fc0  mov     ecx, r8d
0x180019fc3  mov     eax, r12d
0x180019fc6  and     ecx, r10d
0x180019fc9  and     eax, r10d
0x180019fcc  sub     ecx, eax
0x180019fce  jnz     short loc_180019FE4
0x180019fd0  mov     ecx, r8d
0x180019fd3  mov     eax, r12d
0x180019fd6  shr     ecx, 8
0x180019fd9  shr     eax, 8
0x180019fdc  and     ecx, r10d
0x180019fdf  and     eax, r10d
0x180019fe2  sub     ecx, eax
0x180019fe4  test    ecx, ecx
0x180019fe6  js      loc_18001A23B
0x180019fec  lea     rcx, [rdi+28h]
0x180019ff0  call    AcquireWriteLock
0x180019ff5  mov     rcx, rdi
0x180019ff8  call    MergeTempAndMasterSourceLists
0x180019ffd  lea     rax, [rdi+48h]
0x18001a001  mov     rbx, [rax]
0x18001a004  jmp     loc_18001A21D
0x18001a009  mov     r9d, [r14+18h]
0x18001a00d  lea     rax, [rsp+8B0h+var_850]
0x18001a012  mov     edx, [r14+10h]
0x18001a016  lea     rcx, [rbx+30h]
0x18001a01a  mov     r8d, [r14+14h]
0x18001a01e  mov     [rsp+8B0h+var_880], rax
0x18001a023  lea     rax, [rsp+8B0h+var_85C]
0x18001a028  mov     [rsp+8B0h+var_888], rax
0x18001a02d  mov     eax, [r14+1Ch]
0x18001a031  mov     dword ptr [rsp+8B0h+var_890], eax
0x18001a035  call    FindOutInterfaceEntry
0x18001a03a  test    eax, eax
0x18001a03c  jz      short loc_18001A04E
0x18001a03e  mov     r8, [rsp+8B0h+var_850]
0x18001a043  mov     rdx, rbx
0x18001a046  mov     rcx, rdi
0x18001a049  call    ScopeIfAndInvokeCallbacks
0x18001a04e  cmp     dword ptr [rbx+70h], 0
0x18001a052  jz      loc_18001A216
0x18001a058  mov     edx, [r14+10h]
0x18001a05c  cmp     [rbx+70h], edx
0x18001a05f  jnz     short loc_18001A0B7
0x18001a061  mov     eax, [r14+14h]
0x18001a065  cmp     [rbx+74h], eax
0x18001a068  jnz     short loc_18001A0B7
0x18001a06a  lea     rsi, [rbx+58h]
0x18001a06e  cmp     [rsi], rsi
0x18001a071  jz      loc_18001A216
0x18001a077  mov     r8, [rsi]; lpMem
0x18001a07a  cmp     r8, rsi
0x18001a07d  jz      short loc_18001A0AE
0x18001a07f  cmp     [r8+8], rsi
0x18001a083  jnz     loc_18001A253
0x18001a089  mov     rax, [r8]
0x18001a08c  cmp     [rax+8], r8
0x18001a090  jnz     loc_18001A253
0x18001a096  mov     [rsi], rax
0x18001a099  xor     edx, edx; dwFlags
0x18001a09b  mov     [rax+8], rsi
0x18001a09f  mov     rcx, cs:hHeap; hHeap
0x18001a0a6  call    cs:__imp_HeapFree
0x18001a0ac  jmp     short loc_18001A077
0x18001a0ae  mov     dword ptr [rbx+50h], 0
0x18001a0b5  jmp     short loc_18001A100
0x18001a0b7  mov     r9d, [r14+18h]
0x18001a0bb  lea     rax, [rsp+8B0h+var_850]
0x18001a0c0  mov     r8d, [r14+14h]
0x18001a0c4  lea     rcx, [rbx+58h]
0x18001a0c8  mov     [rsp+8B0h+var_880], rax
0x18001a0cd  lea     rax, [rsp+8B0h+var_85C]
0x18001a0d2  mov     [rsp+8B0h+var_888], rax
0x18001a0d7  mov     eax, [r14+1Ch]
0x18001a0db  mov     dword ptr [rsp+8B0h+var_890], eax
0x18001a0df  call    FindOutInterfaceEntry
0x18001a0e4  test    eax, eax
0x18001a0e6  jz      loc_18001A216
0x18001a0ec  mov     rcx, [rsp+8B0h+var_850]
0x18001a0f1  call    DeleteOutInterfaceEntry
0x18001a0f6  add     dword ptr [rbx+50h], 0FFFFFFFFh
0x18001a0fa  jnz     loc_18001A206
0x18001a100  mov     r8d, [rbx+8Ch]
0x18001a107  lea     rcx, qword_18002B9A8
0x18001a10e  mov     edx, [rbx+88h]
0x18001a114  call    GetProtocolEntry
0x18001a119  mov     rsi, rax
0x18001a11c  test    rax, rax
0x18001a11f  jnz     short loc_18001A17B
0x18001a121  cmp     cs:qword_18002B8A8, rax
0x18001a128  jz      loc_18001A216
0x18001a12e  mov     word ptr [rsp+8B0h+var_840], ax
0x18001a133  lea     rdx, aProtocolDDNotP; "Protocol (%d, %d) not present for inter"...
0x18001a13a  mov     r9d, [rbx+8Ch]
0x18001a141  lea     rcx, [rsp+8B0h+var_840]
0x18001a146  mov     r8d, [rbx+88h]
0x18001a14d  mov     dword ptr [rsp+8B0h+var_890], r13d
0x18001a152  call    FormatRRASErrorString
0x18001a157  mov     rdx, cs:qword_18002B8A8
0x18001a15e  lea     r8, [rsp+8B0h+var_840]
0x18001a163  mov     rcx, cs:gMgmEtwContext
0x18001a16a  mov     rax, cs:gMgmTemplateFunc
0x18001a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a176  jmp     loc_18001A216
0x18001a17b  cmp     qword ptr [rax+38h], 0
0x18001a180  jz      loc_18001A206
0x18001a186  cmp     cs:qword_18002B8A8, 0
0x18001a18e  jz      short loc_18001A1CF
0x18001a190  xor     eax, eax
0x18001a192  lea     rdx, aInvokedPruneAl; "Invoked Prune Alert for protocol %x, %x"
0x18001a199  mov     word ptr [rsp+8B0h+var_840], ax
0x18001a19e  lea     rcx, [rsp+8B0h+var_840]
0x18001a1a3  mov     r9d, [rsi+14h]
0x18001a1a7  mov     r8d, [rsi+10h]
0x18001a1ab  call    FormatRRASErrorString
0x18001a1b0  mov     rdx, cs:qword_18002B8A8
0x18001a1b7  lea     r8, [rsp+8B0h+var_840]
0x18001a1bc  mov     rcx, cs:gMgmEtwContext
0x18001a1c3  mov     rax, cs:gMgmTemplateFunc
0x18001a1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1cf  mov     ecx, [rbx+74h]
0x18001a1d2  lea     rax, [rsp+8B0h+var_860]
0x18001a1d7  mov     r9d, [rdi+24h]
0x18001a1db  mov     r8d, [rdi+20h]
0x18001a1df  mov     edx, [rbx+6Ch]
0x18001a1e2  mov     [rsp+8B0h+var_878], rax
0x18001a1e7  mov     rax, [rsi+38h]
0x18001a1eb  mov     dword ptr [rsp+8B0h+var_880], 0
0x18001a1f3  mov     dword ptr [rsp+8B0h+var_888], ecx
0x18001a1f7  mov     ecx, [rbx+70h]
0x18001a1fa  mov     dword ptr [rsp+8B0h+var_890], ecx
0x18001a1fe  mov     ecx, [rbx+68h]
0x18001a201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a206  mov     r8d, [rsp+8B0h+var_860]
0x18001a20b  mov     rdx, rbx
0x18001a20e  mov     rcx, rdi
0x18001a211  call    AddMfeToForwarder
0x18001a216  mov     rbx, [rbx]
0x18001a219  lea     rax, [rdi+48h]
0x18001a21d  cmp     rbx, rax
0x18001a220  jnz     loc_18001A009
0x18001a226  lea     rcx, [rdi+28h]
0x18001a22a  call    ReleaseWriteLock
0x18001a22f  mov     r10d, 0FF0000h
0x18001a235  mov     r11d, 0FF00h
0x18001a23b  mov     rdi, [rdi]
0x18001a23e  lea     rax, qword_18002BA20
0x18001a245  cmp     rdi, rax
0x18001a248  jz      short loc_18001A25A
0x18001a24a  mov     eax, dword ptr [rsp+8B0h+var_858]
0x18001a24e  jmp     loc_180019F5E
0x18001a253  mov     ecx, 3
0x18001a258  int     29h; Win8: RtlFailFast(ecx)
0x18001a25a  mov     rsi, [rsp+8B0h+var_848]
0x18001a25f  lea     rcx, qword_18002BA30
0x18001a266  call    ReleaseReadLock
0x18001a26b  xor     edi, edi
0x18001a26d  jmp     short loc_18001A2B0
0x18001a26f  cmp     cs:qword_18002B8A8, rdi
0x18001a276  jz      short loc_18001A2B0
0x18001a278  mov     r8d, r13d
0x18001a27b  mov     word ptr [rsp+8B0h+var_840], di
0x18001a280  lea     rdx, aInterfaceLxNot; "Interface %lx not found"
0x18001a287  lea     rcx, [rsp+8B0h+var_840]
0x18001a28c  call    FormatRRASErrorString
0x18001a291  mov     rdx, cs:qword_18002B8A8
0x18001a298  lea     r8, [rsp+8B0h+var_840]
0x18001a29d  mov     rcx, cs:gMgmEtwContext
0x18001a2a4  mov     rax, cs:gMgmTemplateFunc
0x18001a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2b0  mov     rcx, cs:qword_18002B9E8
0x18001a2b7  add     rcx, 10h
0x18001a2bb  add     rcx, rsi
0x18001a2be  call    ReleaseReadLock
0x18001a2c3  call    InvokeOutstandingCallbacks
0x18001a2c8  lea     rcx, qword_18002B9B8
0x18001a2cf  call    ReleaseReadLock
0x18001a2d4  call    LeaveMgmWorker
0x18001a2d9  cmp     cs:qword_18002B8A8, rdi
0x18001a2e0  jz      short loc_18001A322
0x18001a2e2  mov     r9d, r15d
  ... truncated ...
```
