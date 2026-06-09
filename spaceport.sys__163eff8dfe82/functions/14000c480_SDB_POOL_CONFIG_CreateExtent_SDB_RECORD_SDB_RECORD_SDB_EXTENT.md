# SDB_POOL_CONFIG::CreateExtent(SDB_RECORD *,SDB_RECORD *,SDB_EXTENT *)

- ea: `0x14000c480`
- end: `0x14000c61c`
- name: `?CreateExtent@SDB_POOL_CONFIG@@QEAAJPEAVSDB_RECORD@@0PEAVSDB_EXTENT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, struct SDB_RECORD *, struct SDB_RECORD *, struct SDB_EXTENT *)`
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c6b0`
- `0x140028870`
- `0x1400608f8`
- `0x140062778`
- `0x1400637e0`
- `0x140064320`
- `0x140064b64`

## callees

- `0x14000c480`
- `0x14000c630`
- `0x14000ed60`
- `0x14005e918`
- `0x14005e9b4`
- `0x1400638b8`
- `0x140068150`
- `0x1400b3544`
- `0x1400b6cb0`
- `0x1400b7e00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c4ff`
- `ntoskrnl!ExAllocatePool2` at `0x14000c4ff`

## pseudocode

```c
__int64 __fastcall SDB_POOL_CONFIG::CreateExtent(
        SDB_RECORD **this,
        struct SDB_RECORD *a2,
        struct SDB_RECORD *a3,
        struct SDB_EXTENT *a4)
{
  struct SDB_RECORD *v5; // rsi
  SDB_SPACE *v8; // r14
  SDB_RECORD *RecordByRecordId; // rbx
  __int64 result; // rax
  SDB_DRIVE *v11; // r15
  __int64 v12; // rcx
  __int64 Pool2; // rax
  struct SDB_OBJECT *v14; // rbx
  unsigned __int64 v15; // rcx
  _WORD *v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // rsi
  int inserted; // edi
  unsigned int RecordId; // eax
  unsigned int v21; // edx
  SDB_RECORD *v22; // rsi
  __int64 v23; // rcx

  v5 = a2;
  v8 = (SDB_SPACE *)*((_QWORD *)a2 + (*((_WORD *)a2 + 15) & 1) + 4);
  LOBYTE(a2) = 2;
  RecordByRecordId = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(
                                     (__int64)this,
                                     (__int64)a2,
                                     *((_DWORD *)a4 + 15));
  result = SDB_RECORD::PreTouch(RecordByRecordId, 0);
  if ( (int)result >= 0 )
  {
    v11 = (SDB_DRIVE *)*((_QWORD *)RecordByRecordId + (*((_WORD *)RecordByRecordId + 15) & 1) + 4);
    v12 = 256;
    if ( !*((_BYTE *)WPP_MAIN_CB.DeviceExtension + 442) )
      v12 = 64;
    Pool2 = ExAllocatePool2(v12, 88, 1698852947);
    v14 = (struct SDB_OBJECT *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 72) = -1;
      *(_QWORD *)(Pool2 + 8) = 0;
      *(_QWORD *)(Pool2 + 16) = 0;
      *(_WORD *)(Pool2 + 24) = 0;
      *(_QWORD *)Pool2 = &SDB_EXTENT::`vftable';
      *(_WORD *)(Pool2 + 76) = 0;
      *(_BYTE *)(Pool2 + 25) = *((_BYTE *)v8 + 25);
      *(_QWORD *)(Pool2 + 32) = *((_QWORD *)a4 + 4);
      *(_QWORD *)(Pool2 + 40) = *((_QWORD *)a4 + 5);
      *(_QWORD *)(Pool2 + 48) = *((_QWORD *)a4 + 6);
      if ( a3 )
      {
        v15 = 4;
        v5 = a3;
        *(_WORD *)(Pool2 + 76) = 4;
      }
      else
      {
        v15 = 0;
      }
      *(_DWORD *)(Pool2 + 56) = *((_DWORD *)v5 + 6);
      *(_DWORD *)(Pool2 + 60) = *((_DWORD *)a4 + 15);
      *(_DWORD *)(Pool2 + 64) = *((_DWORD *)a4 + 16);
      *(_DWORD *)(Pool2 + 68) = *((_DWORD *)a4 + 17);
      LOWORD(v15) = *((_WORD *)a4 + 38) | v15;
      *(_WORD *)(Pool2 + 78) |= 4u;
      *(_WORD *)(Pool2 + 76) = v15;
      v16 = SDB_RECORD::operator new(v15);
      v18 = v16;
      if ( v16 )
      {
        v16[15] |= 4u;
        LOBYTE(v17) = 4;
        *((_QWORD *)v16 + 2) = this;
        *((_BYTE *)v16 + 28) = 4;
        if ( (*((unsigned __int8 (__fastcall **)(SDB_RECORD **, __int64))*this + 10))(this, v17) )
          RecordId = SDB_CONFIG::NextRecordId((SDB_CONFIG *)this);
        else
          RecordId = 0;
        *((_DWORD *)v18 + 6) = RecordId;
        inserted = SDB_RECORD::PreTouch((SDB_RECORD *)v18, v14);
        if ( inserted < 0 )
        {
          SDB_RECORD::`scalar deleting destructor'(v18, v21);
        }
        else
        {
          *(_QWORD *)(*(_QWORD *)&v18[4 * (v18[15] & 1) + 16] + 16LL) = v18;
          *(_BYTE *)(*(_QWORD *)&v18[4 * (v18[15] & 1) + 16] + 24LL) = dword_14006ECC4[2 * *((unsigned int *)this + 12)];
          SDB_RECORD::Touch((SDB_RECORD *)v18);
          inserted = SDB_DRIVE::InsertExtentRecord(v11, (struct SDB_RECORD *)v18);
          if ( inserted >= 0 )
          {
            inserted = SDB_SPACE::InsertExtentRecord(v8, (struct SDB_RECORD *)v18);
            if ( inserted >= 0 )
            {
              v22 = this[34];
              inserted = SDB_RECORD::PreTouch(v22, 0);
              if ( inserted >= 0 )
              {
                v23 = *((_QWORD *)v22 + (*((_WORD *)v22 + 15) & 1) + 4);
                *(_QWORD *)(v23 + 248) += *((_QWORD *)v14 + 4);
              }
            }
          }
        }
      }
      else
      {
        inserted = -1073741670;
      }
      (**(void (__fastcall ***)(struct SDB_OBJECT *, __int64))v14)(v14, 1);
      return (unsigned int)inserted;
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c480  mov     [rsp+arg_10], rbx
0x14000c485  push    rbp
0x14000c486  push    rsi
0x14000c487  push    rdi
0x14000c488  push    r12
0x14000c48a  push    r14
0x14000c48c  sub     rsp, 20h
0x14000c490  movzx   eax, word ptr [rdx+1Eh]
0x14000c494  mov     rbp, r8
0x14000c497  mov     r8d, [r9+3Ch]
0x14000c49b  and     eax, 1
0x14000c49e  mov     rsi, rdx
0x14000c4a1  mov     rdi, r9
0x14000c4a4  mov     r12, rcx
0x14000c4a7  mov     r14, [rdx+rax*8+20h]
0x14000c4ac  mov     dl, 2
0x14000c4ae  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x14000c4b3  xor     edx, edx; struct SDB_OBJECT *
0x14000c4b5  mov     rcx, rax; this
0x14000c4b8  mov     rbx, rax
0x14000c4bb  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x14000c4c0  test    eax, eax
0x14000c4c2  js      loc_14000C5C0
0x14000c4c8  movzx   ecx, word ptr [rbx+1Eh]
0x14000c4cc  mov     edx, 40h ; '@'
0x14000c4d1  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000c4d8  and     ecx, 1
0x14000c4db  mov     [rsp+48h+arg_8], r15
0x14000c4e0  mov     r8d, 65427053h
0x14000c4e6  mov     r15, [rbx+rcx*8+20h]
0x14000c4eb  mov     ecx, 100h
0x14000c4f0  cmp     byte ptr [rax+1BAh], 0
0x14000c4f7  cmovz   ecx, edx
0x14000c4fa  mov     edx, 58h ; 'X'
0x14000c4ff  call    cs:__imp_ExAllocatePool2
0x14000c506  nop     dword ptr [rax+rax+00h]
0x14000c50b  mov     rbx, rax
0x14000c50e  test    rax, rax
0x14000c511  jz      loc_14000C615
0x14000c517  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x14000c51e  mov     [rsp+48h+arg_0], r13
0x14000c523  xor     r13d, r13d
0x14000c526  mov     [rax+8], r13
0x14000c52a  mov     [rax+10h], r13
0x14000c52e  mov     [rax+18h], r13w
0x14000c533  lea     rax, ??_7SDB_EXTENT@@6B@; const SDB_EXTENT::`vftable'
0x14000c53a  mov     [rbx], rax
0x14000c53d  mov     [rbx+4Ch], r13w
0x14000c542  movzx   eax, byte ptr [r14+19h]
0x14000c547  mov     [rbx+19h], al
0x14000c54a  mov     rax, [rdi+20h]
0x14000c54e  mov     [rbx+20h], rax
0x14000c552  mov     rax, [rdi+28h]
0x14000c556  mov     [rbx+28h], rax
0x14000c55a  mov     rax, [rdi+30h]
0x14000c55e  mov     [rbx+30h], rax
0x14000c562  test    rbp, rbp
0x14000c565  jnz     short loc_14000C5D2
0x14000c567  mov     ecx, r13d
0x14000c56a  mov     eax, [rsi+18h]
0x14000c56d  mov     [rbx+38h], eax
0x14000c570  mov     eax, [rdi+3Ch]
0x14000c573  mov     [rbx+3Ch], eax
0x14000c576  mov     eax, [rdi+40h]
0x14000c579  mov     [rbx+40h], eax
0x14000c57c  mov     eax, [rdi+44h]
0x14000c57f  mov     [rbx+44h], eax
0x14000c582  or      cx, [rdi+4Ch]; unsigned __int64
0x14000c586  or      word ptr [rbx+4Eh], 4
0x14000c58b  mov     [rbx+4Ch], cx
0x14000c58f  call    ??2SDB_RECORD@@SAPEAX_K@Z; SDB_RECORD::operator new(unsigned __int64)
0x14000c594  mov     rsi, rax
0x14000c597  test    rax, rax
0x14000c59a  jnz     short loc_14000C5E0
0x14000c59c  mov     edi, 0C000009Ah
0x14000c5a1  mov     rax, [rbx]
0x14000c5a4  mov     edx, 1
0x14000c5a9  mov     rcx, rbx
0x14000c5ac  mov     rax, [rax]
0x14000c5af  call    _guard_dispatch_icall
0x14000c5b4  mov     r13, [rsp+48h+arg_0]
0x14000c5b9  mov     eax, edi
0x14000c5bb  mov     r15, [rsp+48h+arg_8]
0x14000c5c0  mov     rbx, [rsp+48h+arg_10]
0x14000c5c5  add     rsp, 20h
0x14000c5c9  pop     r14
0x14000c5cb  pop     r12
0x14000c5cd  pop     rdi
0x14000c5ce  pop     rsi
0x14000c5cf  pop     rbp
0x14000c5d0  retn
0x14000c5d2  mov     ecx, 4
0x14000c5d7  mov     rsi, rbp
0x14000c5da  mov     [rbx+4Ch], cx
0x14000c5de  jmp     short loc_14000C56A
0x14000c5e0  or      word ptr [rax+1Eh], 4
0x14000c5e5  mov     dl, 4
0x14000c5e7  mov     [rax+10h], r12
0x14000c5eb  mov     rcx, r12
0x14000c5ee  mov     byte ptr [rax+1Ch], 4
0x14000c5f2  mov     rax, [r12]
0x14000c5f6  mov     rax, [rax+50h]
0x14000c5fa  call    _guard_dispatch_icall
0x14000c5ff  test    al, al
0x14000c601  jz      loc_1400694C2
0x14000c607  mov     rcx, r12; this
0x14000c60a  call    ?NextRecordId@SDB_CONFIG@@QEAAKXZ; SDB_CONFIG::NextRecordId(void)
0x14000c60f  nop
0x14000c610  jmp     loc_1400694C5
0x14000c615  mov     eax, 0C000009Ah
0x14000c61a  jmp     short loc_14000C5BB
0x1400694c2  mov     eax, r13d
0x1400694c5  mov     rdx, rbx; struct SDB_OBJECT *
0x1400694c8  mov     [rsi+18h], eax
0x1400694cb  mov     rcx, rsi; this
0x1400694ce  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x1400694d3  mov     edi, eax
0x1400694d5  test    eax, eax
0x1400694d7  js      loc_140069577
0x1400694dd  movzx   eax, word ptr [rsi+1Eh]
0x1400694e1  lea     rcx, dword_14006ECC4
0x1400694e8  and     eax, 1
0x1400694eb  mov     rax, [rsi+rax*8+20h]
0x1400694f0  mov     [rax+10h], rsi
0x1400694f4  movzx   eax, word ptr [rsi+1Eh]
0x1400694f8  mov     r8d, [r12+30h]
0x1400694fd  and     eax, 1
0x140069500  mov     rdx, [rsi+rax*8+20h]
0x140069505  movzx   eax, byte ptr [rcx+r8*8]
0x14006950a  mov     rcx, rsi; this
0x14006950d  mov     [rdx+18h], al
0x140069510  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x140069515  mov     rdx, rsi; struct SDB_RECORD *
0x140069518  mov     rcx, r15; this
0x14006951b  call    ?InsertExtentRecord@SDB_DRIVE@@QEAAJPEAVSDB_RECORD@@@Z; SDB_DRIVE::InsertExtentRecord(SDB_RECORD *)
0x140069520  mov     edi, eax
0x140069522  test    eax, eax
0x140069524  js      loc_14000C5A1
0x14006952a  mov     rdx, rsi; struct SDB_RECORD *
0x14006952d  mov     rcx, r14; this
0x140069530  call    ?InsertExtentRecord@SDB_SPACE@@QEAAJPEAVSDB_RECORD@@@Z; SDB_SPACE::InsertExtentRecord(SDB_RECORD *)
0x140069535  mov     edi, eax
0x140069537  test    eax, eax
0x140069539  js      loc_14000C5A1
0x14006953f  mov     rsi, [r12+110h]
0x140069547  xor     edx, edx; struct SDB_OBJECT *
0x140069549  mov     rcx, rsi; this
0x14006954c  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140069551  mov     edi, eax
0x140069553  test    eax, eax
0x140069555  js      loc_14000C5A1
0x14006955b  movzx   eax, word ptr [rsi+1Eh]
0x14006955f  and     eax, 1
0x140069562  mov     rcx, [rsi+rax*8+20h]
0x140069567  mov     rax, [rbx+20h]
0x14006956b  add     [rcx+0F8h], rax
0x140069572  jmp     loc_14000C5A1
0x140069577  mov     rcx, rsi; P
0x14006957a  call    ??_GSDB_RECORD@@QEAAPEAXI@Z; SDB_RECORD::`scalar deleting destructor'(uint)
0x14006957f  nop
0x140069580  jmp     loc_14000C5A1
```
