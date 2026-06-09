# SDB_POOL_CONFIG::SelectDrives(SC_PICK_CONTEXT *,ulong,ulong,_LIST_ENTRY *,uchar,uchar)

- ea: `0x140025078`
- end: `0x140025603`
- name: `?SelectDrives@SDB_POOL_CONFIG@@QEAAJPEAVSC_PICK_CONTEXT@@KKPEAU_LIST_ENTRY@@EE@Z`
- size: `1419`
- prototype: `__int64 __fastcall(SDB_POOL_CONFIG *__hidden this, struct SC_PICK_CONTEXT *, unsigned int, unsigned int, struct _LIST_ENTRY *, char, char)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14000d300`
- `0x140028130`
- `0x140028500`
- `0x140029848`

## callees

- `0x14000ba20`
- `0x14001b5c0`
- `0x14001ccf0`
- `0x14001d290`
- `0x14001d6a0`
- `0x14001d960`
- `0x140025078`
- `0x1400268c0`
- `0x140061354`
- `0x1400667fc`
- `0x1400b6cb0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400250d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400250d1`

## pseudocode

```c
__int64 __fastcall SDB_POOL_CONFIG::SelectDrives(
        SDB_POOL_CONFIG *this,
        struct SC_PICK_CONTEXT *a2,
        unsigned int a3,
        unsigned int a4,
        struct _LIST_ENTRY *a5,
        char a6,
        char a7)
{
  _DWORD *v7; // rax
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  int v12; // ebp
  _QWORD *Pool2; // rax
  _QWORD *v14; // r14
  int v15; // ebx
  SDB_POOL_CONFIG *v16; // rcx
  __int64 *i; // r8
  __int64 *RecordByType; // rax
  __int64 *v19; // rsi
  unsigned int v20; // edx
  SDB_POOL_CONFIG *v21; // rcx
  __int64 *v22; // rdi
  __int64 v23; // rdi
  int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rcx
  _QWORD *v27; // r8
  unsigned int v28; // eax
  struct _LIST_ENTRY *v29; // rsi
  struct _LIST_ENTRY *v30; // rdi
  __int64 FaultDomainId; // r13
  __int64 v32; // r12
  struct SDB_DRIVE *v33; // rbp
  _OWORD *v34; // r15
  _QWORD *v35; // rax
  struct _LIST_ENTRY *j; // rdx
  char *v37; // r8
  struct _LIST_ENTRY *v38; // r8
  struct _LIST_ENTRY *k; // rcx
  char *v40; // rdx
  char v41; // al
  bool v42; // zf
  char *v43; // rax
  struct _LIST_ENTRY *Blink; // rax
  char v45; // r8
  char *v46; // rax
  struct _LIST_ENTRY *v47; // rax
  struct _LIST_ENTRY *v48; // rax
  char **v49; // rdx
  struct _LIST_ENTRY *v50; // rdx
  unsigned int v51; // edx
  __int64 v52; // rcx
  char v54; // [rsp+30h] [rbp-68h]
  char v55; // [rsp+31h] [rbp-67h]
  char v56; // [rsp+32h] [rbp-66h]
  unsigned int v57; // [rsp+34h] [rbp-64h]
  unsigned int v58; // [rsp+38h] [rbp-60h]
  unsigned int v59; // [rsp+3Ch] [rbp-5Ch]
  int v60; // [rsp+40h] [rbp-58h]
  unsigned int v61; // [rsp+44h] [rbp-54h]

  v7 = (_DWORD *)*((_QWORD *)a2 + 3);
  v10 = v7[7];
  v11 = v7[5];
  v12 = v7[4];
  v61 = v7[6];
  v57 = v10;
  v59 = v11;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 488, 1482190931);
  if ( !Pool2
    || (v14 = Pool2 + 1,
        *Pool2 = 12,
        `vector constructor iterator'(Pool2 + 1, 0x28u, 0xCu, (void *(*)(void *))SC_LIST::SC_LIST),
        !v14) )
  {
    v15 = -1073741670;
LABEL_95:
    if ( !a6 || v15 != -1073740703 )
      ScFreeLists(a5);
    return (unsigned int)v15;
  }
  v15 = 0;
  v16 = this;
  for ( i = 0; ; i = v19 )
  {
    RecordByType = SDB_POOL_CONFIG::GetRecordByType((__int64)v16, 2, i);
    v19 = RecordByType;
    if ( !RecordByType )
      break;
    v15 = SDB_RECORD::PreTouch((SDB_RECORD *)RecordByType, 0);
    if ( v15 < 0 )
      goto LABEL_33;
    v22 = v19 + 5;
    if ( (*((_BYTE *)v19 + 30) & 1) == 0 )
      v22 = v19 + 4;
    v23 = *v22;
    v24 = *(_DWORD *)(v23 + 252);
    if ( (v24 & 1) != 0
      && (v24 & 2) == 0
      && (!v12 || v12 == 3 || *(_DWORD *)(v23 + 108) == v12)
      && (v10 == 1 || SDB_DRIVE::GetFaultDomainId(v23, v10))
      && (v11 == 1 || SDB_DRIVE::GetFaultDomainId(v23, v11))
      && (!a7 || SDB_DRIVE::GetFaultDomainId(v23, v61)) )
    {
      v25 = SDB_POOL_CONFIG::WhichBucket(v21, (struct SDB_DRIVE *)v23, *((_QWORD *)a2 + 1), 0);
      if ( v25 != -1 )
      {
        v26 = (__int64)&v14[5 * v25 + 2];
        v27 = *(_QWORD **)(v26 + 8);
        if ( *v27 != v26 )
LABEL_93:
          __fastfail(3u);
        *(_QWORD *)(v23 + 256) = v26;
        *(_QWORD *)(v23 + 264) = v27;
        *v27 = v23 + 256;
        *(_QWORD *)(v26 + 8) = v23 + 256;
        ++LODWORD(v14[5 * v25 + 4]);
      }
    }
    v16 = this;
  }
  v60 = 0;
  v55 = 0;
  v28 = a3;
  v29 = 0;
  v30 = 0;
  v58 = a3;
  FaultDomainId = 0;
  v54 = 0;
  v56 = 0;
  v32 = 0;
LABEL_91:
  v20 = v59;
  while ( 1 )
  {
    if ( !v28 )
      goto LABEL_33;
    if ( (unsigned int)v32 <= 0xA )
    {
      do
      {
        v33 = SDB_POOL_CONFIG::SelectRandomDrive(this, (struct SC_LIST *)&v14[5 * v32]);
        if ( v33 )
          goto LABEL_37;
        v32 = (unsigned int)(v32 + 1);
      }
      while ( (unsigned int)v32 <= 0xA );
      v28 = v58;
      v20 = v59;
    }
    if ( v10 == v20 )
    {
      if ( v28 > *((_DWORD *)a2 + 4) )
        goto LABEL_32;
    }
    else
    {
      v56 = 1;
    }
    v33 = SDB_POOL_CONFIG::SelectRandomDrive(this, (struct SC_LIST *)(v14 + 55));
    if ( !v33 )
    {
LABEL_32:
      v15 = -1073740703;
      goto LABEL_33;
    }
LABEL_37:
    v34 = 0;
    if ( v57 == 1 )
    {
      v41 = v55;
LABEL_60:
      if ( !v41 )
      {
        v43 = (char *)SC_ENV::Allocate(0x40u, 0x58587053u, 0, 0);
        v30 = (struct _LIST_ENTRY *)v43;
        if ( !v43 )
          break;
        *((_QWORD *)v43 + 1) = v43;
        *(_QWORD *)v43 = v43;
        *((_QWORD *)v43 + 3) = v43 + 16;
        *((_QWORD *)v43 + 2) = v43 + 16;
        *((_DWORD *)v43 + 8) = 0;
        if ( FaultDomainId )
          *(_OWORD *)(v43 + 40) = *(_OWORD *)FaultDomainId;
        Blink = a5->Blink;
        if ( Blink->Flink != a5 )
          goto LABEL_93;
        v30->Flink = a5;
        v30->Blink = Blink;
        Blink->Flink = v30;
        a5->Blink = v30;
      }
      goto LABEL_66;
    }
    v55 = 0;
    v54 = 0;
    FaultDomainId = SDB_DRIVE::GetFaultDomainId(v33, v57);
    v35 = (_QWORD *)SDB_DRIVE::GetFaultDomainId(v33, v61);
    v34 = v35;
    for ( j = a5->Flink; ; j = j->Flink )
    {
      if ( j == a5 )
      {
        v41 = 0;
        goto LABEL_54;
      }
      v30 = j;
      v37 = (char *)j[2].Blink - *(_QWORD *)FaultDomainId;
      if ( !v37 )
        v37 = (char *)j[3].Flink - *(_QWORD *)(FaultDomainId + 8);
      if ( !v37 )
        break;
    }
    if ( a7 )
    {
      v38 = j + 1;
      for ( k = j[1].Flink; k != v38; k = k->Flink )
      {
        v29 = k;
        v40 = (char *)k[2].Blink - *v35;
        if ( !v40 )
          v40 = (char *)k[3].Flink - v35[1];
        if ( !v40 )
        {
          v54 = 1;
          break;
        }
      }
    }
    v41 = 1;
    v55 = 1;
LABEL_54:
    if ( !v56 || v60 != *((_DWORD *)a2 + 4) )
      goto LABEL_60;
    v20 = v59;
    v42 = v41 == 0;
    v28 = v58;
    if ( v42 || !LOBYTE(v30[3].Blink) )
      goto LABEL_24;
LABEL_66:
    v45 = v54;
    if ( !a7 || v54 )
      goto LABEL_71;
    v46 = (char *)SC_ENV::Allocate(0x40u, 0x58587053u, 0, 0);
    v29 = (struct _LIST_ENTRY *)v46;
    if ( !v46 )
      break;
    *((_QWORD *)v46 + 1) = v46;
    *(_QWORD *)v46 = v46;
    *((_QWORD *)v46 + 3) = v46 + 16;
    *((_QWORD *)v46 + 2) = v46 + 16;
    *((_DWORD *)v46 + 8) = 0;
    *(_OWORD *)(v46 + 40) = *v34;
    v47 = v30[1].Blink;
    if ( v47->Flink != &v30[1] )
      goto LABEL_93;
    v45 = 0;
    v29->Flink = v30 + 1;
    v29->Blink = v47;
    v47->Flink = v29;
    v30[1].Blink = v29;
    ++LODWORD(v30[2].Flink);
LABEL_71:
    if ( v56 && !LOBYTE(v30[3].Blink) )
    {
      ++v60;
      LOBYTE(v30[3].Blink) = 1;
    }
    v48 = (struct _LIST_ENTRY *)((char *)v33 + 256);
    if ( !a7 )
    {
      v50 = v30[1].Blink;
      if ( v50->Flink != &v30[1] )
        goto LABEL_93;
      v48->Flink = v30 + 1;
      *((_QWORD *)v33 + 33) = v50;
      v50->Flink = v48;
      v30[1].Blink = v48;
LABEL_80:
      ++LODWORD(v30[2].Flink);
      goto LABEL_81;
    }
    v49 = (char **)v29[1].Blink;
    if ( *v49 != (char *)&v29[1] )
      goto LABEL_93;
    v48->Flink = v29 + 1;
    *((_QWORD *)v33 + 33) = v49;
    *v49 = (char *)v48;
    v29[1].Blink = v48;
    ++LODWORD(v29[2].Flink);
    if ( v45 )
      goto LABEL_80;
LABEL_81:
    v20 = v59;
    v28 = --v58;
    if ( v57 != 1 )
    {
      if ( LODWORD(v30[2].Flink) == a4 )
      {
        v10 = v57;
        SDB_POOL_CONFIG::DiscardDrives(a4, v14, (unsigned int)v32, v57, FaultDomainId);
        goto LABEL_90;
      }
      if ( v59 != 1 )
      {
        FaultDomainId = SDB_DRIVE::GetFaultDomainId(v33, v59);
        SDB_POOL_CONFIG::DiscardDrives(v52, v14, (unsigned int)v32, v51, FaultDomainId);
        goto LABEL_89;
      }
      if ( a7 )
      {
        v28 = v58;
        if ( LODWORD(v29[2].Flink) == a3 >> 2 )
        {
          SDB_POOL_CONFIG::DiscardDrives(a4, v14, (unsigned int)v32, v61, v34);
LABEL_89:
          v10 = v57;
LABEL_90:
          v28 = v58;
          goto LABEL_91;
        }
      }
    }
LABEL_24:
    v10 = v57;
  }
  v15 = -1073741670;
LABEL_33:
  SC_LIST::`vector deleting destructor'((SC_LIST *)v14, v20);
  if ( v15 < 0 )
    goto LABEL_95;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140025078  mov     rax, rsp
0x14002507b  mov     [rax+20h], r9d
0x14002507f  mov     [rax+18h], r8d
0x140025083  mov     [rax+10h], rdx
0x140025087  mov     [rax+8], rcx
0x14002508b  push    rbx
0x14002508c  push    rbp
0x14002508d  push    rsi
0x14002508e  push    rdi
0x14002508f  push    r12
0x140025091  push    r13
0x140025093  push    r14
0x140025095  push    r15
0x140025097  sub     rsp, 58h
0x14002509b  mov     rax, [rdx+18h]
0x14002509f  mov     rdi, rcx
0x1400250a2  mov     r13, rdx
0x1400250a5  mov     r8d, 58587053h
0x1400250ab  mov     edx, 1E8h
0x1400250b0  mov     ecx, [rax+18h]
0x1400250b3  mov     r15d, [rax+1Ch]
0x1400250b7  mov     r12d, [rax+14h]
0x1400250bb  mov     ebp, [rax+10h]
0x1400250be  mov     [rsp+98h+var_54], ecx
0x1400250c2  mov     ecx, 40h ; '@'
0x1400250c7  mov     [rsp+98h+var_64], r15d
0x1400250cc  mov     [rsp+98h+var_5C], r12d
0x1400250d1  call    cs:__imp_ExAllocatePool2
0x1400250d8  nop     dword ptr [rax+rax+00h]
0x1400250dd  test    rax, rax
0x1400250e0  jz      loc_1400255CB
0x1400250e6  mov     r8d, 0Ch; unsigned __int64
0x1400250ec  lea     r14, [rax+8]
0x1400250f0  lea     r9, ??0SC_LIST@@QEAA@XZ; void *(*)(void *)
0x1400250f7  mov     [rax], r8
0x1400250fa  mov     rcx, r14; void *
0x1400250fd  lea     edx, [r8+1Ch]; unsigned __int64
0x140025101  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140025106  test    r14, r14
0x140025109  jz      loc_1400255CB
0x14002510f  xor     ebx, ebx
0x140025111  mov     rcx, rdi
0x140025114  xor     r8d, r8d
0x140025117  mov     dl, 2
0x140025119  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14002511e  mov     rsi, rax
0x140025121  test    rax, rax
0x140025124  jz      loc_140025217
0x14002512a  xor     edx, edx; struct SDB_OBJECT *
0x14002512c  mov     rcx, rax; this
0x14002512f  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x140025134  mov     ebx, eax
0x140025136  test    eax, eax
0x140025138  js      loc_1400252A0
0x14002513e  test    byte ptr [rsi+1Eh], 1
0x140025142  lea     rdi, [rsi+28h]
0x140025146  jnz     short loc_14002514C
0x140025148  lea     rdi, [rsi+20h]
0x14002514c  mov     rdi, [rdi]
0x14002514f  mov     eax, [rdi+0FCh]
0x140025155  test    al, 1
0x140025157  jz      loc_140025207
0x14002515d  test    al, 2
0x14002515f  jnz     loc_140025207
0x140025165  test    ebp, ebp
0x140025167  jz      short loc_140025177
0x140025169  cmp     ebp, 3
0x14002516c  jz      short loc_140025177
0x14002516e  cmp     [rdi+6Ch], ebp
0x140025171  jnz     loc_140025207
0x140025177  cmp     r15d, 1
0x14002517b  jz      short loc_14002518D
0x14002517d  mov     edx, r15d
0x140025180  mov     rcx, rdi
0x140025183  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x140025188  test    rax, rax
0x14002518b  jz      short loc_140025207
0x14002518d  cmp     r12d, 1
0x140025191  jz      short loc_1400251A3
0x140025193  mov     edx, r12d
0x140025196  mov     rcx, rdi
0x140025199  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x14002519e  test    rax, rax
0x1400251a1  jz      short loc_140025207
0x1400251a3  cmp     [rsp+98h+arg_30], 0
0x1400251ab  jz      short loc_1400251BE
0x1400251ad  mov     edx, [rsp+98h+var_54]
0x1400251b1  mov     rcx, rdi
0x1400251b4  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x1400251b9  test    rax, rax
0x1400251bc  jz      short loc_140025207
0x1400251be  mov     r8, [r13+8]; unsigned __int64
0x1400251c2  xor     r9d, r9d; int
0x1400251c5  mov     rdx, rdi; struct SDB_DRIVE *
0x1400251c8  call    ?WhichBucket@SDB_POOL_CONFIG@@QEAAKPEAVSDB_DRIVE@@_KJ@Z; SDB_POOL_CONFIG::WhichBucket(SDB_DRIVE *,unsigned __int64,long)
0x1400251cd  cmp     eax, 0FFFFFFFFh
0x1400251d0  jz      short loc_140025207
0x1400251d2  mov     eax, eax
0x1400251d4  lea     rcx, [r14+10h]
0x1400251d8  lea     rdx, [rax+rax*4]
0x1400251dc  lea     rcx, [rcx+rdx*8]
0x1400251e0  mov     r8, [rcx+8]
0x1400251e4  cmp     [r8], rcx
0x1400251e7  jnz     loc_1400255C4
0x1400251ed  lea     rax, [rdi+100h]
0x1400251f4  mov     [rax], rcx
0x1400251f7  mov     [rax+8], r8
0x1400251fb  mov     [r8], rax
0x1400251fe  mov     [rcx+8], rax
0x140025202  inc     dword ptr [r14+rdx*8+20h]
0x140025207  mov     rcx, [rsp+98h+arg_0]
0x14002520f  mov     r8, rsi
0x140025212  jmp     loc_140025117
0x140025217  xor     al, al
0x140025219  mov     [rsp+98h+var_58], 0
0x140025221  xor     r8b, r8b
0x140025224  mov     [rsp+98h+var_67], al
0x140025228  mov     eax, [rsp+98h+arg_10]
0x14002522f  xor     esi, esi
0x140025231  xor     edi, edi
0x140025233  mov     [rsp+98h+var_60], eax
0x140025237  xor     r13d, r13d
0x14002523a  mov     [rsp+98h+var_68], r8b
0x14002523f  mov     [rsp+98h+var_66], sil
0x140025244  xor     r12d, r12d
0x140025247  jmp     loc_1400255B1
0x14002524c  mov     r15d, [rsp+98h+var_64]
0x140025251  test    eax, eax
0x140025253  jz      short loc_1400252A0
0x140025255  cmp     r12d, 0Ah
0x140025259  ja      short loc_140025289
0x14002525b  lea     rcx, [r12+r12*4]
0x14002525f  lea     rdx, [r14+rcx*8]; struct SC_LIST *
0x140025263  mov     rcx, [rsp+98h+arg_0]; this
0x14002526b  call    ?SelectRandomDrive@SDB_POOL_CONFIG@@QEAAPEAVSDB_DRIVE@@PEAVSC_LIST@@@Z; SDB_POOL_CONFIG::SelectRandomDrive(SC_LIST *)
0x140025270  mov     rbp, rax
0x140025273  test    rax, rax
0x140025276  jnz     short loc_1400252D6
0x140025278  inc     r12d
0x14002527b  cmp     r12d, 0Ah
0x14002527f  jbe     short loc_14002525B
0x140025281  mov     eax, [rsp+98h+var_60]
0x140025285  mov     edx, [rsp+98h+var_5C]; unsigned int
0x140025289  cmp     r15d, edx
0x14002528c  jnz     short loc_1400252B5
0x14002528e  mov     rcx, [rsp+98h+arg_8]
0x140025296  cmp     eax, [rcx+10h]
0x140025299  jbe     short loc_1400252BA
0x14002529b  mov     ebx, 0C0000461h
0x1400252a0  mov     rcx, r14; this
0x1400252a3  call    ??_ESC_LIST@@QEAAPEAXI@Z; SC_LIST::`vector deleting destructor'(uint)
0x1400252a8  test    ebx, ebx
0x1400252aa  js      loc_1400255D0
0x1400252b0  jmp     loc_1400255EF
0x1400252b5  mov     [rsp+98h+var_66], 1
0x1400252ba  mov     rcx, [rsp+98h+arg_0]; this
0x1400252c2  lea     rdx, [r14+1B8h]; struct SC_LIST *
0x1400252c9  call    ?SelectRandomDrive@SDB_POOL_CONFIG@@QEAAPEAVSDB_DRIVE@@PEAVSC_LIST@@@Z; SDB_POOL_CONFIG::SelectRandomDrive(SC_LIST *)
0x1400252ce  mov     rbp, rax
0x1400252d1  test    rax, rax
0x1400252d4  jz      short loc_14002529B
0x1400252d6  mov     ecx, [rsp+98h+var_64]
0x1400252da  xor     r15d, r15d
0x1400252dd  cmp     ecx, 1
0x1400252e0  jz      loc_1400253B4
0x1400252e6  xor     al, al
0x1400252e8  mov     [rsp+98h+var_67], r15b
0x1400252ed  mov     edx, ecx
0x1400252ef  mov     [rsp+98h+var_68], al
0x1400252f3  mov     rcx, rbp
0x1400252f6  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x1400252fb  mov     edx, [rsp+98h+var_54]
0x1400252ff  mov     rcx, rbp
0x140025302  mov     r13, rax
0x140025305  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x14002530a  mov     r9, [rsp+98h+arg_20]
0x140025312  mov     r15, rax
0x140025315  mov     rdx, [r9]
0x140025318  cmp     rdx, r9
0x14002531b  jz      short loc_14002537D
0x14002531d  mov     r8, [rdx+28h]
0x140025321  mov     rdi, rdx
0x140025324  sub     r8, [r13+0]
0x140025328  jnz     short loc_140025332
0x14002532a  mov     r8, [rdx+30h]
0x14002532e  sub     r8, [r13+8]
0x140025332  test    r8, r8
0x140025335  jz      short loc_14002533C
0x140025337  mov     rdx, [rdx]
0x14002533a  jmp     short loc_140025318
0x14002533c  cmp     [rsp+98h+arg_30], 0
0x140025344  jz      short loc_140025375
0x140025346  lea     r8, [rdx+10h]
0x14002534a  mov     rcx, [r8]
0x14002534d  cmp     rcx, r8
0x140025350  jz      short loc_140025375
0x140025352  mov     rdx, [rcx+28h]
0x140025356  mov     rsi, rcx
0x140025359  sub     rdx, [rax]
0x14002535c  jnz     short loc_140025366
0x14002535e  mov     rdx, [rcx+30h]
0x140025362  sub     rdx, [rax+8]
0x140025366  test    rdx, rdx
0x140025369  jz      short loc_140025370
0x14002536b  mov     rcx, [rcx]
0x14002536e  jmp     short loc_14002534D
0x140025370  mov     [rsp+98h+var_68], 1
0x140025375  mov     al, 1
0x140025377  mov     [rsp+98h+var_67], al
0x14002537b  jmp     short loc_140025381
0x14002537d  mov     al, [rsp+98h+var_67]
0x140025381  cmp     [rsp+98h+var_66], 0
0x140025386  jz      short loc_1400253B8
0x140025388  mov     rdx, [rsp+98h+arg_8]
0x140025390  mov     ecx, [rsp+98h+var_58]
0x140025394  cmp     ecx, [rdx+10h]
0x140025397  jnz     short loc_1400253B8
0x140025399  mov     edx, [rsp+98h+var_5C]
0x14002539d  test    al, al
0x14002539f  mov     eax, [rsp+98h+var_60]
0x1400253a3  jz      loc_14002524C
0x1400253a9  cmp     byte ptr [rdi+38h], 0
0x1400253ad  jnz     short loc_140025427
0x1400253af  jmp     loc_14002524C
0x1400253b4  mov     al, [rsp+98h+var_67]
0x1400253b8  test    al, al
0x1400253ba  jnz     short loc_140025427
0x1400253bc  xor     r9d, r9d; unsigned int
0x1400253bf  xor     r8d, r8d; unsigned __int8
0x1400253c2  mov     edx, 58587053h; unsigned int
0x1400253c7  lea     ecx, [r9+40h]; unsigned __int64
0x1400253cb  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400253d0  mov     rdi, rax
0x1400253d3  test    rax, rax
0x1400253d6  jz      loc_1400255BA
0x1400253dc  mov     [rax+8], rax
0x1400253e0  lea     rcx, [rax+10h]
0x1400253e4  mov     [rax], rax
0x1400253e7  mov     [rax+18h], rcx
0x1400253eb  mov     [rcx], rcx
0x1400253ee  mov     dword ptr [rax+20h], 0
0x1400253f5  test    r13, r13
0x1400253f8  jz      short loc_140025404
0x1400253fa  movups  xmm0, xmmword ptr [r13+0]
0x1400253ff  movdqu  xmmword ptr [rax+28h], xmm0
0x140025404  mov     r9, [rsp+98h+arg_20]
0x14002540c  mov     rax, [r9+8]
0x140025410  cmp     [rax], r9
0x140025413  jnz     loc_1400255C4
0x140025419  mov     [rdi], r9
0x14002541c  mov     [rdi+8], rax
0x140025420  mov     [rax], rdi
0x140025423  mov     [r9+8], rdi
0x140025427  cmp     [rsp+98h+arg_30], 0
0x14002542f  mov     r8b, [rsp+98h+var_68]
0x140025434  jz      short loc_1400254A4
0x140025436  test    r8b, r8b
0x140025439  jnz     short loc_1400254A4
0x14002543b  xor     r9d, r9d; unsigned int
0x14002543e  xor     r8d, r8d; unsigned __int8
0x140025441  mov     edx, 58587053h; unsigned int
0x140025446  lea     ecx, [r9+40h]; unsigned __int64
0x14002544a  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14002544f  mov     rsi, rax
0x140025452  test    rax, rax
0x140025455  jz      loc_1400255BA
0x14002545b  mov     [rax+8], rax
0x14002545f  lea     rcx, [rax+10h]
0x140025463  mov     [rax], rax
0x140025466  mov     [rax+18h], rcx
0x14002546a  mov     [rcx], rcx
0x14002546d  lea     rcx, [rdi+10h]
0x140025471  mov     dword ptr [rax+20h], 0
0x140025478  movups  xmm0, xmmword ptr [r15]
0x14002547c  movdqu  xmmword ptr [rax+28h], xmm0
0x140025481  mov     rax, [rcx+8]
0x140025485  cmp     [rax], rcx
0x140025488  jnz     loc_1400255C4
0x14002548e  mov     r8b, [rsp+98h+var_68]
0x140025493  mov     [rsi], rcx
0x140025496  mov     [rsi+8], rax
0x14002549a  mov     [rax], rsi
0x14002549d  mov     [rcx+8], rsi
0x1400254a1  inc     dword ptr [rdi+20h]
0x1400254a4  cmp     [rsp+98h+var_66], 0
0x1400254a9  jz      short loc_1400254B9
0x1400254ab  cmp     byte ptr [rdi+38h], 0
0x1400254af  jnz     short loc_1400254B9
0x1400254b1  inc     [rsp+98h+var_58]
0x1400254b5  mov     byte ptr [rdi+38h], 1
0x1400254b9  cmp     [rsp+98h+arg_30], 0
0x1400254c1  lea     rax, [rbp+100h]
0x1400254c8  jz      short loc_1400254F3
0x1400254ca  lea     rcx, [rsi+10h]
0x1400254ce  mov     rdx, [rcx+8]
0x1400254d2  cmp     [rdx], rcx
0x1400254d5  jnz     loc_1400255C4
0x1400254db  mov     [rax], rcx
0x1400254de  mov     [rax+8], rdx
0x1400254e2  mov     [rdx], rax
  ... truncated ...
```
