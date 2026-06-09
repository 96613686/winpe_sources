# VMX_PACK::AttemptGrowDiskMbr(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14004b3dc`
- end: `0x14004bab7`
- name: `?AttemptGrowDiskMbr@VMX_PACK@@AEAAXPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `1755`
- prototype: `void __fastcall(VMX_PACK *__hidden this, struct VMX_RECORD *, struct _DISK_GEOMETRY *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14004b130`

## callees

- `0x140005f80`
- `0x140005fb0`
- `0x140007600`
- `0x140007b08`
- `0x1400099d8`
- `0x140009f7c`
- `0x140009fcc`
- `0x14002b0c4`
- `0x140033958`
- `0x140044ac4`
- `0x140047c7c`
- `0x1400483bc`
- `0x1400484a4`
- `0x140048830`
- `0x140048fa0`
- `0x140049b04`
- `0x14004b3dc`
- `0x1400587d4`

## pseudocode

```c
void __fastcall VMX_PACK::AttemptGrowDiskMbr(
        VMX_PACK *this,
        struct VMX_RECORD *a2,
        struct _DISK_GEOMETRY *a3,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a4)
{
  __int64 v7; // rsi
  unsigned int *v8; // rcx
  __int64 v9; // rbp
  unsigned __int64 v10; // rbx
  __int64 v11; // r12
  int LengthInfo; // eax
  unsigned __int64 v13; // r13
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rbx
  LARGE_INTEGER v17; // r13
  __int64 v18; // rcx
  unsigned __int64 QuadPart; // rax
  unsigned __int64 v20; // rbp
  LARGE_INTEGER v21; // r9
  LARGE_INTEGER StartingOffset; // rcx
  unsigned __int64 v23; // r12
  __int64 v24; // rdx
  BYTE PartitionType; // al
  __int64 v26; // r10
  unsigned __int64 v27; // r8
  __m128i v28; // xmm6
  int DynamicPartitions; // eax
  VMX_NOTIFICATION_QUEUE *v30; // r10
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // rax
  void *v34; // rdi
  int v35; // eax
  VMX_NOTIFICATION_QUEUE *v36; // r10
  __int64 v37; // rdx
  __int64 v38; // r9
  struct VMX_LOG_COPY *v39; // rax
  struct VMX_LOG_COPY *v40; // rbp
  int v41; // eax
  VMX_NOTIFICATION_QUEUE *v42; // r10
  __int64 v43; // rdx
  __int64 v44; // r9
  char v45; // bl
  int v46; // ebx
  unsigned int v47; // edx
  unsigned int v48; // edx
  VMX_LOG_COPY *v49; // rcx
  __int64 v50; // [rsp+20h] [rbp-68h]
  __int64 v51; // [rsp+20h] [rbp-68h]
  unsigned __int64 v52; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int64 v53; // [rsp+30h] [rbp-58h]
  _QWORD *v54; // [rsp+98h] [rbp+10h]

  v52 = 0;
  v7 = *(_QWORD *)(*((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5) + 128LL);
  v8 = *(unsigned int **)(v7 + 16);
  v54 = *(_QWORD **)(v7 + 88);
  v9 = v54[19];
  v10 = v8[9];
  v11 = v54[20];
  LengthInfo = VMX_DISK_DEVICE::GetLengthInfo((VMX_DISK_DEVICE *)v8, &v52);
  if ( LengthInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        222,
        WPP_b525482092043ba595507d12d78e6f73_Traceguids,
        (unsigned int)LengthInfo);
    }
    return;
  }
  v13 = v10;
  v53 = v10;
  v14 = v10;
  v15 = v10;
  v16 = v52;
  v17.QuadPart = v9 * v13;
  v18 = v11 * v14;
  QuadPart = v18 + v17.QuadPart;
  if ( v52 < v18 + v17.QuadPart )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 223, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
    }
    return;
  }
  v20 = v17.QuadPart + 2 * v18;
  v21.QuadPart = v52 - v18;
  if ( v52 < v20 )
    v21 = v17;
  v50 = v54[17];
  StartingOffset = v21;
  v23 = v15 * (v50 + v54[18]);
  v24 = 0;
  do
  {
    if ( (unsigned int)v24 >= a4->PartitionCount )
      break;
    PartitionType = a4->PartitionEntry[v24].Mbr.PartitionType;
    if ( PartitionType != 0xA0 && PartitionType != 0x84 && PartitionType != 39 && PartitionType != 18 )
    {
      LOBYTE(QuadPart) = PartitionType + 34;
      if ( (unsigned __int8)QuadPart > 0x20u )
        continue;
      v26 = 0x100000201LL;
      if ( !_bittest64(&v26, QuadPart) )
        continue;
    }
    QuadPart = a4->PartitionEntry[v24].StartingOffset.QuadPart;
    if ( QuadPart >= v23 && QuadPart < StartingOffset.QuadPart )
      StartingOffset = a4->PartitionEntry[v24].StartingOffset;
    v24 = (unsigned int)(v24 + 1);
  }
  while ( (unsigned int)v24 < 4 );
  if ( StartingOffset.QuadPart != v23 || v52 >= v20 )
  {
    v27 = v53;
    v54[19] = v21.QuadPart / v53;
    v51 = v27 * v50;
    v54[18] = (StartingOffset.QuadPart - v51) / v27;
    v28 = _mm_unpacklo_epi64(
            (__m128i)((v21.QuadPart - v17.QuadPart) / v27),
            (__m128i)((v21.QuadPart - v17.QuadPart) / v27));
    *(__m128i *)(v7 + 64) = _mm_add_epi64(v28, _mm_loadu_si128((const __m128i *)(v7 + 64)));
    if ( StartingOffset.QuadPart != v23 )
    {
      DynamicPartitions = VMX_PHYSICAL_DISK::CreateDynamicPartitions((VMX_PHYSICAL_DISK *)v7, a2, a3, a4);
      if ( DynamicPartitions < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
        {
          goto LABEL_89;
        }
        v31 = 224;
        goto LABEL_33;
      }
    }
    if ( v16 < v20 )
    {
      if ( (int)VMX_PHYSICAL_DISK::WriteMetadata((VMX_PHYSICAL_DISK *)v7, 1u) >= 0 )
        return;
      goto LABEL_89;
    }
    DynamicPartitions = VMX_PHYSICAL_DISK::ZeroPrivateRegion((VMX_PHYSICAL_DISK *)v7, 0);
    if ( DynamicPartitions < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_89;
      }
      v31 = 225;
LABEL_33:
      v32 = (unsigned int)DynamicPartitions;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v30 + 3), v31, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v32);
LABEL_89:
      v54[19] = v17.QuadPart / v53;
      v54[18] = (v23 - v51) / v53;
      *(__m128i *)(v7 + 64) = _mm_sub_epi64(_mm_loadu_si128((const __m128i *)(v7 + 64)), v28);
      return;
    }
    if ( !*(_QWORD *)(v7 + 104) )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 226, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
      }
      goto LABEL_89;
    }
    v33 = VMX_ALLOCATED_OBJECT::operator new(40, 258, 1665363286);
    v34 = (void *)v33;
    if ( !v33 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_89;
      }
      v31 = 227;
      v32 = 3221225626LL;
      goto LABEL_34;
    }
    *(_QWORD *)(v33 + 8) = 0;
    *(_QWORD *)(v33 + 16) = 0;
    *(_QWORD *)(v33 + 24) = 0;
    *(_QWORD *)(v33 + 32) = 0;
    *(_QWORD *)v33 = v7;
    *(_QWORD *)(v33 + 8) = *(_QWORD *)(*(_QWORD *)(v7 + 104) + 8LL);
    *(_WORD *)(v33 + 16) = 0;
    *(_DWORD *)(v33 + 18) = 393216;
    *(_QWORD *)(v33 + 24) = 0;
    *(_QWORD *)(v33 + 32) = 0;
    v35 = VMX_RAW_CONFIG::AtomicWrite(*(VMX_RAW_CONFIG **)(*((_QWORD *)this + 2) + 8LL), (struct VMX_CONFIG_COPY *)v33);
    if ( v35 < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_83;
      }
      v37 = 228;
      v38 = (unsigned int)v35;
      goto LABEL_82;
    }
    if ( !*(_QWORD *)(v7 + 112) )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 229, WPP_b525482092043ba595507d12d78e6f73_Traceguids);
      }
      goto LABEL_83;
    }
    v39 = (struct VMX_LOG_COPY *)VMX_ALLOCATED_OBJECT::operator new(48, 66, 1665953110);
    v40 = v39;
    if ( !v39 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_83;
      }
      v37 = 230;
      v38 = 3221225626LL;
LABEL_82:
      WPP_SF_d(*((_QWORD *)v36 + 3), v37, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v38);
      goto LABEL_83;
    }
    *(_OWORD *)v39 = 0;
    *((_OWORD *)v39 + 1) = 0;
    *((_OWORD *)v39 + 2) = 0;
    v41 = VMX_LOG_COPY::Initialize(
            v39,
            (struct VMX_PHYSICAL_DISK *)v7,
            *(struct VMX_COPY **)(*(_QWORD *)(v7 + 96) + 56LL));
    if ( v41 < 0 )
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_74;
      }
      v43 = 231;
      v44 = (unsigned int)v41;
LABEL_73:
      WPP_SF_d(*((_QWORD *)v42 + 3), v43, WPP_b525482092043ba595507d12d78e6f73_Traceguids, v44);
LABEL_74:
      VMX_LOG::Acquire(*((VMX_LOG **)this + 3));
      VMX_LOG::RemoveLogCopy(*((VMX_LOG **)this + 3), v40);
      VMX_LOG::Release(*((VMX_LOG **)this + 3));
      VMX_LOG_COPY::`scalar deleting destructor'(v40, v47);
LABEL_83:
      VMX_ALLOCATED_OBJECT::operator delete(v34);
      goto LABEL_89;
    }
    VMX_LOG::Acquire(*((VMX_LOG **)this + 3));
    VMX_LOG::AddLogCopy(*((VMX_LOG **)this + 3), (VMX_LOG **)v40);
    v45 = *((_BYTE *)v40 + 45);
    VMX_LOG::Release(*((VMX_LOG **)this + 3));
    if ( !v45 )
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_74;
      }
      v43 = 232;
      v44 = v45 == 0 ? 0xC0000001 : 0;
      goto LABEL_73;
    }
    v46 = VMX_PHYSICAL_DISK::WriteMetadata((VMX_PHYSICAL_DISK *)v7, 0);
    if ( v46 < 0 )
    {
      VMX_PHYSICAL_DISK::ZeroSectors((VMX_PHYSICAL_DISK *)v7, *(_QWORD *)(v7 + 64), 1u);
      VMX_PHYSICAL_DISK::ZeroSectors((VMX_PHYSICAL_DISK *)v7, *(_QWORD *)(v7 + 72), 1u);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
      {
        goto LABEL_74;
      }
      v43 = 233;
      v44 = (unsigned int)v46;
      goto LABEL_73;
    }
    VMX_ALLOCATED_OBJECT::operator delete(*(void **)(v7 + 104));
    *(_QWORD *)(v7 + 104) = v34;
    VMX_PACK::UpdateCounters(this);
    VMX_LOG::Acquire(*((VMX_LOG **)this + 3));
    VMX_LOG::RemoveLogCopy(*((VMX_LOG **)this + 3), *(struct VMX_LOG_COPY **)(v7 + 112));
    VMX_LOG::Release(*((VMX_LOG **)this + 3));
    v49 = *(VMX_LOG_COPY **)(v7 + 112);
    if ( v49 )
      VMX_LOG_COPY::`scalar deleting destructor'(v49, v48);
    *(_QWORD *)(v7 + 112) = v40;
  }
}

```

## disassembly

```asm
0x14004b3dc  mov     rax, rsp
0x14004b3df  mov     [rax+8], rbx
0x14004b3e3  mov     [rax+18h], r8
0x14004b3e7  push    rbp
0x14004b3e8  push    rsi
0x14004b3e9  push    rdi
0x14004b3ea  push    r12
0x14004b3ec  push    r13
0x14004b3ee  push    r14
0x14004b3f0  push    r15
0x14004b3f2  sub     rsp, 50h
0x14004b3f6  mov     qword ptr [rax-60h], 0
0x14004b3fe  mov     r14, rcx
0x14004b401  movaps  xmmword ptr [rax-48h], xmm6
0x14004b405  mov     r15, rdx
0x14004b408  movzx   eax, word ptr [rdx+40h]
0x14004b40c  mov     rdi, r9
0x14004b40f  and     eax, 1
0x14004b412  mov     rax, [rdx+rax*8+28h]
0x14004b417  lea     rdx, [rsp+88h+var_60]; PVOID
0x14004b41c  mov     rsi, [rax+80h]
0x14004b423  mov     rax, [rsi+58h]
0x14004b427  mov     rcx, [rsi+10h]; this
0x14004b42b  mov     [rsp+88h+arg_8], rax
0x14004b433  mov     rbp, [rax+98h]
0x14004b43a  mov     ebx, [rcx+24h]
0x14004b43d  mov     r12, [rax+0A0h]
0x14004b444  call    ?GetLengthInfo@VMX_DISK_DEVICE@@QEAAJPEAU_GET_LENGTH_INFORMATION@@@Z; VMX_DISK_DEVICE::GetLengthInfo(_GET_LENGTH_INFORMATION *)
0x14004b449  test    eax, eax
0x14004b44b  jns     short loc_14004B499
0x14004b44d  mov     r10, cs:WPP_GLOBAL_Control
0x14004b454  lea     rcx, WPP_GLOBAL_Control
0x14004b45b  cmp     r10, rcx
0x14004b45e  jz      loc_14004BA99
0x14004b464  mov     edx, [r10+2Ch]
0x14004b468  test    dl, 8
0x14004b46b  jz      loc_14004BA99
0x14004b471  cmp     byte ptr [r10+29h], 3
0x14004b476  jb      loc_14004BA99
0x14004b47c  mov     rcx, [r10+18h]
0x14004b480  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b487  mov     edx, 0DEh
0x14004b48c  mov     r9d, eax
0x14004b48f  call    WPP_SF_d
0x14004b494  jmp     loc_14004BA99
0x14004b499  mov     r13, rbx
0x14004b49c  mov     [rsp+88h+var_58], rbx
0x14004b4a1  mov     rcx, rbx
0x14004b4a4  mov     r8, rbx
0x14004b4a7  mov     rbx, [rsp+88h+var_60]
0x14004b4ac  imul    r13, rbp
0x14004b4b0  imul    rcx, r12
0x14004b4b4  lea     rax, [rcx+r13]
0x14004b4b8  cmp     rbx, rax
0x14004b4bb  jnb     short loc_14004B505
0x14004b4bd  mov     r9, cs:WPP_GLOBAL_Control
0x14004b4c4  lea     rcx, WPP_GLOBAL_Control
0x14004b4cb  cmp     r9, rcx
0x14004b4ce  jz      loc_14004BA99
0x14004b4d4  mov     eax, [r9+2Ch]
0x14004b4d8  test    al, 8
0x14004b4da  jz      loc_14004BA99
0x14004b4e0  cmp     byte ptr [r9+29h], 3
0x14004b4e5  jb      loc_14004BA99
0x14004b4eb  mov     rcx, [r9+18h]
0x14004b4ef  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b4f6  mov     edx, 0DFh
0x14004b4fb  call    WPP_SF_
0x14004b500  jmp     loc_14004BA99
0x14004b505  mov     r10, [rsp+88h+arg_8]
0x14004b50d  lea     rbp, ds:0[rcx*2]
0x14004b515  mov     r11d, [rdi+4]
0x14004b519  add     rbp, r13
0x14004b51c  mov     r9, rbx
0x14004b51f  sub     r9, rcx
0x14004b522  mov     rcx, [r10+88h]
0x14004b529  cmp     rbx, rbp
0x14004b52c  mov     r12, [r10+90h]
0x14004b533  cmovb   r9, r13
0x14004b537  mov     [rsp+88h+var_68], rcx
0x14004b53c  add     r12, rcx
0x14004b53f  mov     rcx, r9
0x14004b542  imul    r12, r8
0x14004b546  xor     edx, edx
0x14004b548  cmp     edx, r11d
0x14004b54b  jnb     short loc_14004B597
0x14004b54d  lea     r8, [rdx+rdx*8]
0x14004b551  add     r8, r8
0x14004b554  mov     al, [rdi+r8*8+50h]
0x14004b559  cmp     al, 0A0h
0x14004b55b  jz      short loc_14004B57F
0x14004b55d  cmp     al, 84h
0x14004b55f  jz      short loc_14004B57F
0x14004b561  cmp     al, 27h ; '''
0x14004b563  jz      short loc_14004B57F
0x14004b565  cmp     al, 12h
0x14004b567  jz      short loc_14004B57F
0x14004b569  add     al, 22h ; '"'
0x14004b56b  cmp     al, 20h ; ' '
0x14004b56d  ja      short loc_14004B590
0x14004b56f  mov     r10, 100000201h
0x14004b579  bt      r10, rax
0x14004b57d  jnb     short loc_14004B590
0x14004b57f  mov     rax, [rdi+r8*8+38h]
0x14004b584  cmp     rax, r12
0x14004b587  jb      short loc_14004B590
0x14004b589  cmp     rax, rcx
0x14004b58c  cmovb   rcx, rax
0x14004b590  inc     edx
0x14004b592  cmp     edx, 4
0x14004b595  jb      short loc_14004B548
0x14004b597  mov     r10, [rsp+88h+arg_8]
0x14004b59f  cmp     rcx, r12
0x14004b5a2  jnz     short loc_14004B5AD
0x14004b5a4  cmp     rbx, rbp
0x14004b5a7  jb      loc_14004BA99
0x14004b5ad  mov     r8, [rsp+88h+var_58]
0x14004b5b2  xor     edx, edx
0x14004b5b4  mov     r11, [rsp+88h+var_68]
0x14004b5b9  mov     rax, r9
0x14004b5bc  div     r8
0x14004b5bf  xor     edx, edx
0x14004b5c1  sub     r9, r13
0x14004b5c4  mov     [r10+98h], rax
0x14004b5cb  mov     rax, rcx
0x14004b5ce  imul    r11, r8
0x14004b5d2  sub     rax, r11
0x14004b5d5  mov     [rsp+88h+var_68], r11
0x14004b5da  div     r8
0x14004b5dd  xor     edx, edx
0x14004b5df  mov     [r10+90h], rax
0x14004b5e6  mov     rax, r9
0x14004b5e9  movdqu  xmm0, xmmword ptr [rsi+40h]
0x14004b5ee  div     r8
0x14004b5f1  movq    xmm6, rax
0x14004b5f6  punpcklqdq xmm6, xmm6
0x14004b5fa  movdqa  xmm1, xmm6
0x14004b5fe  paddq   xmm1, xmm0
0x14004b602  movdqu  xmmword ptr [rsi+40h], xmm1
0x14004b607  cmp     rcx, r12
0x14004b60a  jz      short loc_14004B675
0x14004b60c  mov     r8, [rsp+88h+arg_10]; struct _DISK_GEOMETRY *
0x14004b614  mov     r9, rdi; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14004b617  mov     rdx, r15; struct VMX_RECORD *
0x14004b61a  mov     rcx, rsi; this
0x14004b61d  call    ?CreateDynamicPartitions@VMX_PHYSICAL_DISK@@QEAAJPEAVVMX_RECORD@@PEAU_DISK_GEOMETRY@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_PHYSICAL_DISK::CreateDynamicPartitions(VMX_RECORD *,_DISK_GEOMETRY *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14004b622  xor     r15d, r15d
0x14004b625  test    eax, eax
0x14004b627  jns     short loc_14004B678
0x14004b629  mov     r10, cs:WPP_GLOBAL_Control
0x14004b630  lea     rcx, WPP_GLOBAL_Control
0x14004b637  cmp     r10, rcx
0x14004b63a  jz      loc_14004BA5C
0x14004b640  mov     edx, [r10+2Ch]
0x14004b644  test    dl, 8
0x14004b647  jz      loc_14004BA5C
0x14004b64d  cmp     byte ptr [r10+29h], 3
0x14004b652  jb      loc_14004BA5C
0x14004b658  mov     edx, 0E0h
0x14004b65d  mov     r9d, eax
0x14004b660  mov     rcx, [r10+18h]
0x14004b664  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b66b  call    WPP_SF_d
0x14004b670  jmp     loc_14004BA5C
0x14004b675  xor     r15d, r15d
0x14004b678  mov     rcx, rsi; this
0x14004b67b  cmp     rbx, rbp
0x14004b67e  jb      loc_14004BA51
0x14004b684  xor     edx, edx; unsigned __int8
0x14004b686  call    ?ZeroPrivateRegion@VMX_PHYSICAL_DISK@@QEAAJE@Z; VMX_PHYSICAL_DISK::ZeroPrivateRegion(uchar)
0x14004b68b  test    eax, eax
0x14004b68d  jns     short loc_14004B6C5
0x14004b68f  mov     r10, cs:WPP_GLOBAL_Control
0x14004b696  lea     rcx, WPP_GLOBAL_Control
0x14004b69d  cmp     r10, rcx
0x14004b6a0  jz      loc_14004BA5C
0x14004b6a6  mov     edx, [r10+2Ch]
0x14004b6aa  test    dl, 8
0x14004b6ad  jz      loc_14004BA5C
0x14004b6b3  cmp     byte ptr [r10+29h], 3
0x14004b6b8  jb      loc_14004BA5C
0x14004b6be  mov     edx, 0E1h
0x14004b6c3  jmp     short loc_14004B65D
0x14004b6c5  cmp     [rsi+68h], r15
0x14004b6c9  jnz     short loc_14004B713
0x14004b6cb  mov     r9, cs:WPP_GLOBAL_Control
0x14004b6d2  lea     rcx, WPP_GLOBAL_Control
0x14004b6d9  cmp     r9, rcx
0x14004b6dc  jz      loc_14004BA5C
0x14004b6e2  mov     eax, [r9+2Ch]
0x14004b6e6  test    al, 8
0x14004b6e8  jz      loc_14004BA5C
0x14004b6ee  cmp     byte ptr [r9+29h], 3
0x14004b6f3  jb      loc_14004BA5C
0x14004b6f9  mov     rcx, [r9+18h]
0x14004b6fd  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b704  mov     edx, 0E2h
0x14004b709  call    WPP_SF_
0x14004b70e  jmp     loc_14004BA5C
0x14004b713  mov     edx, 102h; unsigned __int64
0x14004b718  mov     ecx, 28h ; '('; unsigned __int64
0x14004b71d  mov     r8d, 63436D56h; unsigned int
0x14004b723  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004b728  mov     rdi, rax
0x14004b72b  test    rax, rax
0x14004b72e  jz      loc_14004BA1F
0x14004b734  mov     [rax+8], r15
0x14004b738  mov     rdx, rdi; struct VMX_CONFIG_COPY *
0x14004b73b  mov     [rax+10h], r15
0x14004b73f  mov     [rax+18h], r15
0x14004b743  mov     [rax+20h], r15
0x14004b747  mov     [rax], rsi
0x14004b74a  mov     rax, [rsi+68h]
0x14004b74e  mov     rcx, [rax+8]
0x14004b752  mov     [rdi+8], rcx
0x14004b756  mov     word ptr [rdi+10h], 0
0x14004b75c  mov     dword ptr [rdi+12h], 60000h
0x14004b763  mov     [rdi+18h], r15
0x14004b767  mov     [rdi+20h], r15
0x14004b76b  mov     rcx, [r14+10h]
0x14004b76f  mov     rcx, [rcx+8]; this
0x14004b773  call    ?AtomicWrite@VMX_RAW_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_RAW_CONFIG::AtomicWrite(VMX_CONFIG_COPY *)
0x14004b778  test    eax, eax
0x14004b77a  jns     short loc_14004B7B8
0x14004b77c  mov     r10, cs:WPP_GLOBAL_Control
0x14004b783  lea     rcx, WPP_GLOBAL_Control
0x14004b78a  cmp     r10, rcx
0x14004b78d  jz      loc_14004BA15
0x14004b793  mov     edx, [r10+2Ch]
0x14004b797  test    dl, 8
0x14004b79a  jz      loc_14004BA15
0x14004b7a0  cmp     byte ptr [r10+29h], 3
0x14004b7a5  jb      loc_14004BA15
0x14004b7ab  mov     edx, 0E4h
0x14004b7b0  mov     r9d, eax
0x14004b7b3  jmp     loc_14004BA05
0x14004b7b8  cmp     [rsi+70h], r15
0x14004b7bc  jnz     short loc_14004B806
0x14004b7be  mov     r9, cs:WPP_GLOBAL_Control
0x14004b7c5  lea     rcx, WPP_GLOBAL_Control
0x14004b7cc  cmp     r9, rcx
0x14004b7cf  jz      loc_14004BA15
0x14004b7d5  mov     eax, [r9+2Ch]
0x14004b7d9  test    al, 8
0x14004b7db  jz      loc_14004BA15
0x14004b7e1  cmp     byte ptr [r9+29h], 3
0x14004b7e6  jb      loc_14004BA15
0x14004b7ec  mov     rcx, [r9+18h]
0x14004b7f0  lea     r8, WPP_b525482092043ba595507d12d78e6f73_Traceguids
0x14004b7f7  mov     edx, 0E5h
0x14004b7fc  call    WPP_SF_
0x14004b801  jmp     loc_14004BA15
0x14004b806  mov     edx, 42h ; 'B'; unsigned __int64
0x14004b80b  mov     r8d, 634C6D56h; unsigned int
0x14004b811  lea     ecx, [rdx-12h]; unsigned __int64
0x14004b814  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14004b819  mov     rbp, rax
0x14004b81c  test    rax, rax
0x14004b81f  jz      loc_14004B9D8
0x14004b825  xorps   xmm0, xmm0
0x14004b828  mov     rdx, rsi; struct VMX_PHYSICAL_DISK *
0x14004b82b  movups  xmmword ptr [rax], xmm0
0x14004b82e  mov     rcx, rax; this
0x14004b831  movups  xmmword ptr [rax+10h], xmm0
0x14004b835  movups  xmmword ptr [rax+20h], xmm0
0x14004b839  mov     r8, [rsi+60h]
0x14004b83d  mov     r8, [r8+38h]; struct VMX_COPY *
0x14004b841  call    ?Initialize@VMX_LOG_COPY@@QEAAJPEAVVMX_PHYSICAL_DISK@@PEAVVMX_COPY@@@Z; VMX_LOG_COPY::Initialize(VMX_PHYSICAL_DISK *,VMX_COPY *)
0x14004b846  test    eax, eax
0x14004b848  jns     short loc_14004B886
0x14004b84a  mov     r10, cs:WPP_GLOBAL_Control
0x14004b851  lea     rcx, WPP_GLOBAL_Control
0x14004b858  cmp     r10, rcx
0x14004b85b  jz      loc_14004B962
0x14004b861  mov     edx, [r10+2Ch]
0x14004b865  test    dl, 8
0x14004b868  jz      loc_14004B962
0x14004b86e  cmp     byte ptr [r10+29h], 3
0x14004b873  jb      loc_14004B962
0x14004b879  mov     edx, 0E7h
0x14004b87e  mov     r9d, eax
0x14004b881  jmp     loc_14004B952
0x14004b886  mov     rcx, [r14+18h]; this
0x14004b88a  call    ?Acquire@VMX_LOG@@QEAAXXZ; VMX_LOG::Acquire(void)
0x14004b88f  mov     rcx, [r14+18h]; this
0x14004b893  mov     rdx, rbp; struct VMX_LOG_COPY *
0x14004b896  call    ?AddLogCopy@VMX_LOG@@QEAAXPEAVVMX_LOG_COPY@@@Z; VMX_LOG::AddLogCopy(VMX_LOG_COPY *)
0x14004b89b  mov     bl, [rbp+2Dh]
0x14004b89e  mov     rcx, [r14+18h]; this
0x14004b8a2  mov     al, bl
0x14004b8a4  neg     al
0x14004b8a6  sbb     r15d, r15d
0x14004b8a9  not     r15d
0x14004b8ac  and     r15d, 0C0000001h
0x14004b8b3  call    ?Release@VMX_LOG@@QEAAXXZ; VMX_LOG::Release(void)
0x14004b8b8  test    bl, bl
0x14004b8ba  jnz     short loc_14004B8F0
0x14004b8bc  mov     r10, cs:WPP_GLOBAL_Control
0x14004b8c3  lea     rcx, WPP_GLOBAL_Control
0x14004b8ca  cmp     r10, rcx
  ... truncated ...
```
