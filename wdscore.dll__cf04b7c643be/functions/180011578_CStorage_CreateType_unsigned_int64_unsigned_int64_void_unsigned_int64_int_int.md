# CStorage::CreateType(unsigned __int64,unsigned __int64,void *,unsigned __int64,int,int)

- ea: `0x180011578`
- end: `0x1800117fe`
- name: `?CreateType@CStorage@@QEAAPEAVCTypeManager@@_K0PEAX0HH@Z`
- size: `646`
- prototype: `struct CTypeManager *__fastcall(CStorage *__hidden this, unsigned __int64, unsigned __int64, void *, unsigned __int64, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180016950`

## callees

- `0x180001144`
- `0x18000f638`
- `0x180010e44`
- `0x180011578`
- `0x180011ef4`
- `0x180017598`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800117d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800117d6`

## pseudocode

```c
struct CTypeManager *__fastcall CStorage::CreateType(
        const unsigned __int16 **this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        int a6,
        int a7)
{
  unsigned __int64 v8; // rdx
  __int64 v9; // rbx
  CTypeManager *v10; // rdi
  unsigned int i; // r14d
  int v12; // r12d
  CTypeManager *v13; // rax
  __int64 v14; // rdx
  unsigned int v15; // edx
  int v16; // ebx
  CTypeManager *v17; // rax
  unsigned __int64 v18; // r8
  void *v19; // r9
  unsigned int v20; // edx
  __int64 v21; // rax
  __int64 v22; // rdx
  struct CObjectName *v24; // [rsp+20h] [rbp-40h]
  struct CMemoryManager *v25; // [rsp+30h] [rbp-30h]
  unsigned __int64 v26; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int64 v27; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+58h] BYREF

  v27 = a3;
  v26 = a2;
  v28 = 0;
  (*(void (__fastcall **)(struct IKernel32Interface *, const unsigned __int16 *, __int64))(*(_QWORD *)g_Kernel32 + 416LL))(
    g_Kernel32,
    *this,
    0xFFFFFFFFLL);
  if ( a7 )
    CStorage::DeleteType((CStorage *)this, v8);
  v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, __int64, __int64 *))(*(_QWORD *)this[8] + 16LL))(
         this[8],
         0,
         256,
         &v28);
  v10 = 0;
  if ( v9 )
  {
    for ( i = 0; ; ++i )
    {
      v12 = a6;
      if ( i >= *(_DWORD *)(v9 + 20) )
        break;
      if ( *(_QWORD *)(v9 + 40LL * i + 24) == 0x4D53424C4B425244LL )
      {
        v13 = (CTypeManager *)operator new(0x28u);
        v27 = (unsigned __int64)v13;
        v10 = v13;
        if ( v13 )
        {
          *((_QWORD *)v13 + 3) = 0;
          *(_QWORD *)v13 = 0;
          *((_QWORD *)v13 + 1) = 0;
          *((_QWORD *)v13 + 2) = 0;
          *((_QWORD *)v13 + 4) = 0;
        }
        else
        {
          v10 = 0;
        }
        if ( (unsigned int)CTypeManager::Open(
                             v10,
                             v14,
                             *(_QWORD *)(v9 + 40LL * i + 32),
                             *(_QWORD *)(v9 + 40LL * i + 48),
                             this + 7,
                             this[1],
                             (struct CMemoryManager *)(this + 9),
                             v12) )
        {
          if ( !*((_DWORD *)this + 11) )
            ++*(_QWORD *)(v9 + 40LL * i + 40);
        }
        else
        {
          if ( v10 )
            CTypeManager::`scalar deleting destructor'(v10, v15);
          v10 = 0;
        }
        break;
      }
    }
    v16 = *(_DWORD *)(v9 + 20);
    (*(void (__fastcall **)(const unsigned __int16 *, __int64))(*(_QWORD *)this[8] + 24LL))(this[8], v28);
    if ( i != v16 || *((_DWORD *)this + 11) )
    {
      if ( !v10 )
        goto LABEL_27;
    }
    else
    {
      v17 = (CTypeManager *)operator new(0x28u);
      v27 = (unsigned __int64)v17;
      v10 = v17;
      if ( !v17 )
      {
LABEL_22:
        v10 = 0;
        goto LABEL_27;
      }
      *((_QWORD *)v17 + 3) = 0;
      *(_QWORD *)v17 = 0;
      *((_QWORD *)v17 + 1) = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 4) = 0;
      v27 = 0;
      v25 = (struct CMemoryManager *)this[1];
      v26 = 0;
      if ( !(unsigned int)CTypeManager::Create(
                            v17,
                            (unsigned __int64)&v27,
                            v18,
                            v19,
                            (unsigned __int64)v24,
                            (struct CObjectName *)(this + 7),
                            (const unsigned __int16 *)v25,
                            (struct CMemoryManager *)(this + 9),
                            &v27,
                            &v26,
                            v12) )
      {
        CTypeManager::`scalar deleting destructor'(v10, v20);
        goto LABEL_22;
      }
      v21 = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, __int64, __int64 *))(*(_QWORD *)this[8] + 16LL))(
              this[8],
              0,
              256,
              &v28);
      if ( v21 )
      {
        v22 = 5LL * *(unsigned int *)(v21 + 20);
        *(_QWORD *)(v21 + 8 * v22 + 24) = 0x4D53424C4B425244LL;
        *(_QWORD *)(v21 + 8 * v22 + 32) = v27;
        *(_QWORD *)(v21 + 8 * v22 + 48) = v26;
        *(_QWORD *)(v21 + 8 * v22 + 40) = 1;
        *(_QWORD *)(v21 + 8 * v22 + 56) = 0;
        ++*(_DWORD *)(v21 + 20);
        (*(void (__fastcall **)(const unsigned __int16 *, __int64))(*(_QWORD *)this[8] + 24LL))(this[8], v28);
      }
    }
    ++*((_DWORD *)this + 29);
  }
LABEL_27:
  ReleaseMutex((HANDLE)*this);
  return v10;
}

```

## disassembly

```asm
0x180011578  mov     rax, rsp
0x18001157b  mov     [rax+8], rbx
0x18001157f  mov     [rax+20h], r9
0x180011583  mov     [rax+18h], r8
0x180011587  mov     [rax+10h], rdx
0x18001158b  push    rbp
0x18001158c  push    rsi
0x18001158d  push    rdi
0x18001158e  push    r12
0x180011590  push    r13
0x180011592  push    r14
0x180011594  push    r15
0x180011596  mov     rbp, rsp
0x180011599  sub     rsp, 60h
0x18001159d  mov     rsi, rcx
0x1800115a0  xor     r13d, r13d
0x1800115a3  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800115aa  or      r8d, 0FFFFFFFFh
0x1800115ae  mov     [rbp+arg_18], r13
0x1800115b2  mov     rdx, [rsi]
0x1800115b5  mov     rax, [rcx]
0x1800115b8  mov     rax, [rax+1A0h]
0x1800115bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115c4  cmp     [rbp+arg_30], r13d
0x1800115c8  jz      short loc_1800115D2
0x1800115ca  mov     rcx, rsi; this
0x1800115cd  call    ?DeleteType@CStorage@@QEAAH_K@Z; CStorage::DeleteType(unsigned __int64)
0x1800115d2  mov     rcx, [rsi+40h]
0x1800115d6  lea     r9, [rbp+arg_18]
0x1800115da  xor     edx, edx
0x1800115dc  mov     r8d, 100h
0x1800115e2  mov     rax, [rcx]
0x1800115e5  mov     rax, [rax+10h]
0x1800115e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ee  mov     rbx, rax
0x1800115f1  mov     rdi, r13
0x1800115f4  test    rax, rax
0x1800115f7  jz      loc_1800117D3
0x1800115fd  mov     r14d, r13d
0x180011600  mov     rcx, 4D53424C4B425244h
0x18001160a  mov     r12d, [rbp+arg_28]
0x18001160e  cmp     r14d, [rbx+14h]
0x180011612  jnb     loc_1800116AC
0x180011618  mov     eax, r14d
0x18001161b  lea     r15, [rax+rax*4]
0x18001161f  cmp     [rbx+r15*8+18h], rcx
0x180011624  jz      short loc_18001162B
0x180011626  inc     r14d
0x180011629  jmp     short loc_18001160A
0x18001162b  mov     ecx, 28h ; '('; Size
0x180011630  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011635  mov     [rbp+arg_10], rax
0x180011639  mov     rdi, rax
0x18001163c  test    rax, rax
0x18001163f  jz      short loc_180011656
0x180011641  mov     [rax+18h], r13
0x180011645  mov     [rax], r13
0x180011648  mov     [rax+8], r13
0x18001164c  mov     [rax+10h], r13
0x180011650  mov     [rax+20h], r13
0x180011654  jmp     short loc_180011659
0x180011656  mov     rdi, r13
0x180011659  mov     r9, [rbx+r15*8+30h]; unsigned __int64
0x18001165e  lea     rax, [rsi+48h]
0x180011662  mov     r8, [rbx+r15*8+20h]; unsigned __int64
0x180011667  lea     rcx, [rsi+38h]
0x18001166b  mov     dword ptr [rsp+60h+var_28], r12d; int
0x180011670  mov     [rsp+60h+var_30], rax; struct CMemoryManager *
0x180011675  mov     rax, [rsi+8]
0x180011679  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18001167e  mov     [rsp+60h+var_40], rcx; unsigned __int64
0x180011683  mov     rcx, rdi; this
0x180011686  call    ?Open@CTypeManager@@QEAAH_K00AEAVCObjectName@@PEBGPEAVCMemoryManager@@H@Z; CTypeManager::Open(unsigned __int64,unsigned __int64,unsigned __int64,CObjectName &,ushort const *,CMemoryManager *,int)
0x18001168b  test    eax, eax
0x18001168d  jnz     short loc_1800116A1
0x18001168f  test    rdi, rdi
0x180011692  jz      short loc_18001169C
0x180011694  mov     rcx, rdi; this
0x180011697  call    ??_GCTypeManager@@QEAAPEAXI@Z; CTypeManager::`scalar deleting destructor'(uint)
0x18001169c  mov     rdi, r13
0x18001169f  jmp     short loc_1800116AC
0x1800116a1  cmp     [rsi+2Ch], r13d
0x1800116a5  jnz     short loc_1800116AC
0x1800116a7  inc     qword ptr [rbx+r15*8+28h]
0x1800116ac  mov     rcx, [rsi+40h]
0x1800116b0  mov     rdx, [rbp+arg_18]
0x1800116b4  mov     ebx, [rbx+14h]
0x1800116b7  mov     rax, [rcx]
0x1800116ba  mov     rax, [rax+18h]
0x1800116be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c3  cmp     r14d, ebx
0x1800116c6  jnz     loc_1800117CB
0x1800116cc  cmp     [rsi+2Ch], r13d
0x1800116d0  jnz     loc_1800117CB
0x1800116d6  mov     ecx, 28h ; '('; Size
0x1800116db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800116e0  mov     [rbp+arg_10], rax
0x1800116e4  mov     rdi, rax
0x1800116e7  test    rax, rax
0x1800116ea  jz      short loc_180011756
0x1800116ec  mov     [rax+18h], r13
0x1800116f0  mov     [rax], r13
0x1800116f3  mov     [rax+8], r13
0x1800116f7  mov     [rax+10h], r13
0x1800116fb  mov     [rax+20h], r13
0x1800116ff  test    rax, rax
0x180011702  jz      loc_1800117D3
0x180011708  mov     [rsp+60h+var_10], r12d; int
0x18001170d  lea     rdx, [rbp+arg_8]
0x180011711  mov     [rsp+60h+var_18], rdx; unsigned __int64 *
0x180011716  lea     rax, [rsi+48h]
0x18001171a  lea     rdx, [rbp+arg_10]; unsigned __int64
0x18001171e  mov     [rbp+arg_10], r13
0x180011722  mov     [rsp+60h+var_20], rdx; unsigned __int64 *
0x180011727  lea     rcx, [rsi+38h]
0x18001172b  mov     [rsp+60h+var_28], rax; struct CMemoryManager *
0x180011730  mov     rax, [rsi+8]
0x180011734  mov     [rsp+60h+var_30], rax; unsigned __int16 *
0x180011739  mov     [rsp+60h+var_38], rcx; struct CObjectName *
0x18001173e  mov     rcx, rdi; this
0x180011741  mov     [rbp+arg_8], r13
0x180011745  call    ?Create@CTypeManager@@QEAAH_K0PEAX0AEAVCObjectName@@PEBGPEAVCMemoryManager@@AEA_K5H@Z; CTypeManager::Create(unsigned __int64,unsigned __int64,void *,unsigned __int64,CObjectName &,ushort const *,CMemoryManager *,unsigned __int64 &,unsigned __int64 &,int)
0x18001174a  test    eax, eax
0x18001174c  jnz     short loc_18001175B
0x18001174e  mov     rcx, rdi; this
0x180011751  call    ??_GCTypeManager@@QEAAPEAXI@Z; CTypeManager::`scalar deleting destructor'(uint)
0x180011756  mov     rdi, r13
0x180011759  jmp     short loc_1800117D3
0x18001175b  mov     rcx, [rsi+40h]
0x18001175f  lea     r9, [rbp+arg_18]
0x180011763  xor     edx, edx
0x180011765  mov     r8d, 100h
0x18001176b  mov     rax, [rcx]
0x18001176e  mov     rax, [rax+10h]
0x180011772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011777  test    rax, rax
0x18001177a  jz      short loc_1800117D0
0x18001177c  mov     ecx, [rax+14h]
0x18001177f  lea     rdx, [rcx+rcx*4]
0x180011783  mov     rcx, 4D53424C4B425244h
0x18001178d  mov     [rax+rdx*8+18h], rcx
0x180011792  mov     rcx, [rbp+arg_10]
0x180011796  mov     [rax+rdx*8+20h], rcx
0x18001179b  mov     rcx, [rbp+arg_8]
0x18001179f  mov     [rax+rdx*8+30h], rcx
0x1800117a4  mov     qword ptr [rax+rdx*8+28h], 1
0x1800117ad  mov     [rax+rdx*8+38h], r13
0x1800117b2  inc     dword ptr [rax+14h]
0x1800117b5  mov     rcx, [rsi+40h]
0x1800117b9  mov     rdx, [rbp+arg_18]
0x1800117bd  mov     rax, [rcx]
0x1800117c0  mov     rax, [rax+18h]
0x1800117c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117c9  jmp     short loc_1800117D0
0x1800117cb  test    rdi, rdi
0x1800117ce  jz      short loc_1800117D3
0x1800117d0  inc     dword ptr [rsi+74h]
0x1800117d3  mov     rcx, [rsi]; hMutex
0x1800117d6  call    cs:__imp_ReleaseMutex
0x1800117dd  nop     dword ptr [rax+rax+00h]
0x1800117e2  mov     rbx, [rsp+60h+arg_0]
0x1800117ea  mov     rax, rdi
0x1800117ed  add     rsp, 60h
0x1800117f1  pop     r15
0x1800117f3  pop     r14
0x1800117f5  pop     r13
0x1800117f7  pop     r12
0x1800117f9  pop     rdi
0x1800117fa  pop     rsi
0x1800117fb  pop     rbp
0x1800117fc  retn
```
