# SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)

- ea: `0x1400ba560`
- end: `0x1400ba8aa`
- name: `?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400b9e30`

## callees

- `0x14000d4c0`
- `0x1400187f0`
- `0x140036454`
- `0x140036568`
- `0x140067fc0`
- `0x14008c860`
- `0x1400911c4`
- `0x1400ad3a4`
- `0x1400ad9bc`
- `0x1400b33a4`
- `0x1400b6b10`
- `0x1400b9c00`
- `0x1400ba560`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400ba81d`
- `ntoskrnl!EtwWriteTransfer` at `0x1400ba81d`

## pseudocode

```c
int __fastcall SP_POOL::RetireDrive(SP_POOL *a1, SDB_RECORD *a2, unsigned __int8 a3)
{
  int v4; // esi
  struct SDB_OBJECT *Object; // rax
  struct SDB_OBJECT *v7; // rdi
  int result; // eax
  struct SC_DRIVE *Drive; // rax
  struct SP_ENCLOSURE *EnclosureById; // r15
  __int64 v11; // r8
  struct SDB_OBJECT *v12; // rdi
  SDB_RECORD *v13; // rcx
  char SlotState; // al
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r12d
  char v19; // r14
  GUID *v20; // r15
  char v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[36]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v28[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+D0h] [rbp-30h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  char *v31; // [rsp+F0h] [rbp-10h]
  int v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+FCh] [rbp-4h]
  __int64 *v34; // [rsp+100h] [rbp+0h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  char *v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  char *v38; // [rsp+120h] [rbp+20h]
  __int64 v39; // [rsp+128h] [rbp+28h]
  _DWORD *v40; // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  int *v42; // [rsp+140h] [rbp+40h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  char *v44; // [rsp+150h] [rbp+50h]
  __int64 v45; // [rsp+158h] [rbp+58h]

  v4 = a3;
  Object = SDB_RECORD::GetObject(a2);
  v7 = Object;
  if ( *((_DWORD *)Object + 17) == 5 )
    return 0;
  if ( (_BYTE)v4 == 2 )
  {
    if ( SpIsDriveConnected(Object) )
      return 0;
  }
  else if ( (_BYTE)v4 != 4 )
  {
    return 0;
  }
  Drive = SDB_DRIVE::GetDrive(v7);
  if ( Drive )
    EnclosureById = (struct SP_ENCLOSURE *)*((_QWORD *)Drive + 84);
  else
    EnclosureById = SpFindEnclosureById((struct _GUID *)v7 + 7);
  if ( EnclosureById )
  {
    v11 = *((unsigned int *)v7 + 58);
    *(_QWORD *)((char *)&v26 + 4) = 0;
    memset(&v27[4], 0, 32);
    LODWORD(v26) = 23;
    HIDWORD(v26) = 2;
    *(_DWORD *)v27 = 2;
    v28[0] = v26;
    v28[2] = *(_OWORD *)&v27[16];
    v28[1] = *(_OWORD *)v27;
    v29 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    SP_ENCLOSURE::SetIndications(EnclosureById, v28, v11);
  }
  result = SP_POOL::ReplaceDrive(a1, a2);
  if ( result >= 0 )
  {
    result = SDB_RECORD::PreTouch(a2, 0);
    v22 = result;
    if ( result >= 0 )
    {
      v12 = SDB_RECORD::GetObject(a2);
      SDB_RECORD::Touch(v13);
      *((_DWORD *)v12 + 17) = 5;
      if ( (_BYTE)v4 == 4 )
        *((_WORD *)v12 + 32) |= 1u;
      SlotState = SpGetSlotState(v12, &v22);
      v18 = v22;
      v19 = SlotState;
      if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
        McTemplateK0juqq_EtwWriteTransfer(v16, v15, v17, (_DWORD)v12 + 32, v4, v22, SlotState);
      if ( (unsigned int)dword_14007F050 > 5 )
      {
        v15 = 0;
        if ( (qword_14007F060 & 0x400000000000LL) != 0 && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
        {
          EventDescriptor.Keyword = 0x400000000000LL;
          v44 = &v21;
          v21 = v19;
          v42 = &v22;
          v22 = v18;
          v40 = v23;
          v23[0] = v4;
          v38 = (char *)v12 + 32;
          v24 = 0x1000000;
          v36 = (char *)a1 + 108;
          v34 = &v24;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_14007F058;
          v45 = 1;
          v43 = 4;
          v41 = 4;
          v39 = 16;
          v37 = 16;
          v35 = 8;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          UserData.Size = *(unsigned __int16 *)off_14007F058;
          v31 = byte_140075C15;
          UserData.Reserved = 2;
          v32 = 90;
          v33 = 1;
          v23[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        if ( EnclosureById )
          v20 = (GUID *)((char *)EnclosureById + 16);
        else
          v20 = &GUID_NULL;
        WPP_SF__guid_L_guid_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          v15,
          v17,
          (_DWORD)v12 + 32,
          v4,
          (__int64)v20,
          v18,
          v19);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400ba560  push    rbp
0x1400ba562  push    rbx
0x1400ba563  push    rsi
0x1400ba564  push    rdi
0x1400ba565  push    r13
0x1400ba567  push    r14
0x1400ba569  lea     rbp, [rsp-78h]
0x1400ba56e  sub     rsp, 178h
0x1400ba575  mov     rax, cs:__security_cookie
0x1400ba57c  xor     rax, rsp
0x1400ba57f  mov     [rbp+0A0h+var_40], rax
0x1400ba583  mov     r13, rcx
0x1400ba586  movzx   esi, r8b
0x1400ba58a  mov     rcx, rdx; this
0x1400ba58d  mov     r14, rdx
0x1400ba590  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba595  mov     rdi, rax
0x1400ba598  cmp     dword ptr [rax+44h], 5
0x1400ba59c  jz      short loc_1400BA5AA
0x1400ba59e  cmp     sil, 2
0x1400ba5a2  jz      short loc_1400BA5B3
0x1400ba5a4  cmp     sil, 4
0x1400ba5a8  jz      short loc_1400BA5BF
0x1400ba5aa  xor     ebx, ebx
0x1400ba5ac  mov     eax, ebx
0x1400ba5ae  jmp     loc_1400BA88D
0x1400ba5b3  mov     rcx, rdi; struct SDB_DRIVE *
0x1400ba5b6  call    ?SpIsDriveConnected@@YAEPEAVSDB_DRIVE@@@Z; SpIsDriveConnected(SDB_DRIVE *)
0x1400ba5bb  test    al, al
0x1400ba5bd  jnz     short loc_1400BA5AA
0x1400ba5bf  mov     rcx, rdi; this
0x1400ba5c2  mov     [rsp+1A0h+var_30], r15
0x1400ba5ca  call    ?GetDrive@SDB_DRIVE@@QEAAPEAVSC_DRIVE@@XZ; SDB_DRIVE::GetDrive(void)
0x1400ba5cf  test    rax, rax
0x1400ba5d2  jz      short loc_1400BA5DD
0x1400ba5d4  mov     r15, [rax+2A0h]
0x1400ba5db  jmp     short loc_1400BA5E9
0x1400ba5dd  lea     rcx, [rdi+70h]; struct _GUID *
0x1400ba5e1  call    ?SpFindEnclosureById@@YAPEAVSP_ENCLOSURE@@PEAU_GUID@@@Z; SpFindEnclosureById(_GUID *)
0x1400ba5e6  mov     r15, rax
0x1400ba5e9  xor     ebx, ebx
0x1400ba5eb  test    r15, r15
0x1400ba5ee  jz      short loc_1400BA655
0x1400ba5f0  mov     r8d, [rdi+0E8h]
0x1400ba5f7  lea     rdx, [rbp+0A0h+var_100]
0x1400ba5fb  xorps   xmm0, xmm0
0x1400ba5fe  mov     qword ptr [rsp+1A0h+var_138+4], rbx
0x1400ba603  movdqu  [rsp+1A0h+var_128+4], xmm0
0x1400ba609  mov     dword ptr [rsp+1A0h+var_138], 17h
0x1400ba611  mov     rcx, r15
0x1400ba614  xorps   xmm2, xmm2
0x1400ba617  mov     dword ptr [rsp+1A0h+var_138+0Ch], 2
0x1400ba61f  movups  xmm0, [rsp+1A0h+var_138]
0x1400ba624  mov     dword ptr [rsp+1A0h+var_128], 2
0x1400ba62c  movups  xmm1, [rsp+1A0h+var_128]
0x1400ba631  movdqu  [rbp+0A0h+var_114], xmm2
0x1400ba636  movaps  [rbp+0A0h+var_100], xmm0
0x1400ba63a  movups  xmm0, xmmword ptr [rbp-78h]
0x1400ba63e  psrldq  xmm2, 0Ch
0x1400ba643  movaps  [rbp+0A0h+var_E0], xmm0
0x1400ba647  movaps  [rbp+0A0h+var_F0], xmm1
0x1400ba64b  movd    [rbp+0A0h+var_D0], xmm2
0x1400ba650  call    ?SetIndications@SP_ENCLOSURE@@QEAAJU_SP_ELEMENT_INFO@@K@Z; SP_ENCLOSURE::SetIndications(_SP_ELEMENT_INFO,ulong)
0x1400ba655  mov     rdx, r14; struct SDB_RECORD *
0x1400ba658  mov     rcx, r13; this
0x1400ba65b  call    ?ReplaceDrive@SP_POOL@@QEAAJPEAVSDB_RECORD@@@Z; SP_POOL::ReplaceDrive(SDB_RECORD *)
0x1400ba660  test    eax, eax
0x1400ba662  js      loc_1400BA885
0x1400ba668  xor     edx, edx; struct SDB_OBJECT *
0x1400ba66a  mov     rcx, r14; this
0x1400ba66d  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x1400ba672  mov     [rsp+1A0h+var_15C], eax
0x1400ba676  test    eax, eax
0x1400ba678  js      loc_1400BA885
0x1400ba67e  mov     rcx, r14; this
0x1400ba681  mov     [rsp+1A0h+arg_10], r12
0x1400ba689  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba68e  mov     rdi, rax
0x1400ba691  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x1400ba696  mov     dword ptr [rdi+44h], 5
0x1400ba69d  cmp     sil, 4
0x1400ba6a1  jnz     short loc_1400BA6A8
0x1400ba6a3  or      word ptr [rdi+40h], 1
0x1400ba6a8  lea     rdx, [rsp+1A0h+var_15C]; int *
0x1400ba6ad  mov     rcx, rdi; struct SDB_DRIVE *
0x1400ba6b0  call    ?SpGetSlotState@@YAEPEAVSDB_DRIVE@@PEAJ@Z; SpGetSlotState(SDB_DRIVE *,long *)
0x1400ba6b5  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x1400ba6bc  mov     r12d, [rsp+1A0h+var_15C]
0x1400ba6c1  movzx   r14d, al
0x1400ba6c5  jz      short loc_1400BA6DF
0x1400ba6c7  mov     [rsp+1A0h+var_170], r14d
0x1400ba6cc  lea     r9, [rdi+20h]
0x1400ba6d0  mov     dword ptr [rsp+1A0h+UserData], r12d
0x1400ba6d5  mov     byte ptr [rsp+1A0h+UserDataCount], sil
0x1400ba6da  call    McTemplateK0juqq_EtwWriteTransfer
0x1400ba6df  mov     ecx, cs:dword_14007F050
0x1400ba6e5  cmp     ecx, 5
0x1400ba6e8  jbe     loc_1400BA829
0x1400ba6ee  mov     rcx, cs:qword_14007F068
0x1400ba6f5  mov     rdx, 400000000000h
0x1400ba6ff  mov     rax, cs:qword_14007F060
0x1400ba706  test    rdx, rax
0x1400ba709  jz      loc_1400BA829
0x1400ba70f  mov     rax, rcx
0x1400ba712  and     rax, rdx
0x1400ba715  cmp     rax, rcx
0x1400ba718  jnz     loc_1400BA829
0x1400ba71e  mov     [rsp+1A0h+EventDescriptor.Keyword], rdx
0x1400ba723  lea     rax, [rsp+1A0h+var_160]
0x1400ba728  mov     [rbp+0A0h+var_50], rax
0x1400ba72c  lea     rcx, _TraceLoggingMetadata
0x1400ba733  mov     [rsp+1A0h+var_160], r14b
0x1400ba738  lea     rax, [rsp+1A0h+var_15C]
0x1400ba73d  mov     [rbp+0A0h+var_60], rax
0x1400ba741  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x1400ba746  mov     [rsp+1A0h+var_15C], r12d
0x1400ba74b  lea     rax, [rsp+1A0h+var_158]
0x1400ba750  mov     [rbp+0A0h+var_70], rax
0x1400ba754  xor     r9d, r9d; RelatedActivityId
0x1400ba757  mov     [rsp+1A0h+var_158], esi
0x1400ba75b  lea     rax, [rdi+20h]
0x1400ba75f  mov     [rbp+0A0h+var_80], rax
0x1400ba763  xor     r8d, r8d; ActivityId
0x1400ba766  mov     [rsp+1A0h+var_150], 1000000h
0x1400ba76f  lea     rax, [r13+6Ch]
0x1400ba773  mov     [rbp+0A0h+var_90], rax
0x1400ba777  lea     rax, [rsp+1A0h+var_150]
0x1400ba77c  mov     [rbp+0A0h+var_A0], rax
0x1400ba780  movzx   eax, cs:word_140075C0B
0x1400ba787  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x1400ba78b  mov     rax, cs:off_14007F058
0x1400ba792  mov     [rbp+0A0h+var_C0.Ptr], rax
0x1400ba796  mov     [rbp+0A0h+var_48], 1
0x1400ba79e  mov     [rbp+0A0h+var_58], 4
0x1400ba7a6  mov     [rbp+0A0h+var_68], 4
0x1400ba7ae  mov     [rbp+0A0h+var_78], 10h
0x1400ba7b6  mov     [rbp+0A0h+var_88], 10h
0x1400ba7be  mov     [rbp+0A0h+var_98], 8
0x1400ba7c6  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], 0B000000h
0x1400ba7ce  movzx   eax, word ptr [rax]
0x1400ba7d1  mov     [rbp+0A0h+var_C0.Size], eax
0x1400ba7d4  lea     rax, byte_140075C15
0x1400ba7db  mov     [rbp+0A0h+var_B0], rax
0x1400ba7df  lea     rax, _TraceLoggingMetadataEnd
0x1400ba7e6  sub     eax, ecx
0x1400ba7e8  mov     dword ptr [rbp+0A0h+var_C0.0Ch], 2
0x1400ba7ef  mov     [rbp+0A0h+var_A8], 5Ah ; 'Z'
0x1400ba7f6  mov     [rbp+0A0h+var_A4], 1
0x1400ba7fd  mov     [rsp+1A0h+var_154], eax
0x1400ba801  mov     eax, [rsp+1A0h+var_154]
0x1400ba805  mov     rcx, cs:RegHandle; RegHandle
0x1400ba80c  lea     rax, [rbp+0A0h+var_C0]
0x1400ba810  mov     [rsp+1A0h+UserData], rax; UserData
0x1400ba815  mov     [rsp+1A0h+UserDataCount], 8; UserDataCount
0x1400ba81d  call    cs:__imp_EtwWriteTransfer
0x1400ba824  nop     dword ptr [rax+rax+00h]
0x1400ba829  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba830  lea     rax, WPP_GLOBAL_Control
0x1400ba837  cmp     rcx, rax
0x1400ba83a  jz      short loc_1400BA87B
0x1400ba83c  mov     eax, [rcx+2Ch]
0x1400ba83f  test    al, 10h
0x1400ba841  jz      short loc_1400BA87B
0x1400ba843  cmp     byte ptr [rcx+29h], 3
0x1400ba847  jb      short loc_1400BA87B
0x1400ba849  test    r15, r15
0x1400ba84c  jz      short loc_1400BA854
0x1400ba84e  add     r15, 10h
0x1400ba852  jmp     short loc_1400BA85B
0x1400ba854  lea     r15, GUID_NULL
0x1400ba85b  mov     rcx, [rcx+18h]
0x1400ba85f  lea     r9, [rdi+20h]
0x1400ba863  mov     [rsp+1A0h+var_168], r14d
0x1400ba868  mov     [rsp+1A0h+var_170], r12d
0x1400ba86d  mov     [rsp+1A0h+UserData], r15
0x1400ba872  mov     [rsp+1A0h+UserDataCount], esi
0x1400ba876  call    WPP_SF__guid_L_guid_dd
0x1400ba87b  mov     r12, [rsp+1A0h+arg_10]
0x1400ba883  mov     eax, ebx
0x1400ba885  mov     r15, [rsp+1A0h+var_30]
0x1400ba88d  mov     rcx, [rbp+0A0h+var_40]
0x1400ba891  xor     rcx, rsp; StackCookie
0x1400ba894  call    __security_check_cookie
0x1400ba899  add     rsp, 178h
0x1400ba8a0  pop     r14
0x1400ba8a2  pop     r13
0x1400ba8a4  pop     rdi
0x1400ba8a5  pop     rsi
0x1400ba8a6  pop     rbx
0x1400ba8a7  pop     rbp
0x1400ba8a8  retn
```
