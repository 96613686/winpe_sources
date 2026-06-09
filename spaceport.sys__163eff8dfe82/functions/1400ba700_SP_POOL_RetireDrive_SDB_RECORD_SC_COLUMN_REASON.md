# SP_POOL::RetireDrive(SDB_RECORD *,_SC_COLUMN_REASON)

- ea: `0x1400ba700`
- end: `0x1400baa4a`
- name: `?RetireDrive@SP_POOL@@AEAAJPEAVSDB_RECORD@@W4_SC_COLUMN_REASON@@@Z`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400b9fd0`

## callees

- `0x14000d4c0`
- `0x1400187f0`
- `0x140036514`
- `0x140036628`
- `0x140068110`
- `0x14008c860`
- `0x1400911c4`
- `0x1400ad544`
- `0x1400adb5c`
- `0x1400b3544`
- `0x1400b6cb0`
- `0x1400b9da0`
- `0x1400ba700`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400ba9bd`
- `ntoskrnl!EtwWriteTransfer` at `0x1400ba9bd`

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
0x1400ba700  push    rbp
0x1400ba702  push    rbx
0x1400ba703  push    rsi
0x1400ba704  push    rdi
0x1400ba705  push    r13
0x1400ba707  push    r14
0x1400ba709  lea     rbp, [rsp-78h]
0x1400ba70e  sub     rsp, 178h
0x1400ba715  mov     rax, cs:__security_cookie
0x1400ba71c  xor     rax, rsp
0x1400ba71f  mov     [rbp+0A0h+var_40], rax
0x1400ba723  mov     r13, rcx
0x1400ba726  movzx   esi, r8b
0x1400ba72a  mov     rcx, rdx; this
0x1400ba72d  mov     r14, rdx
0x1400ba730  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba735  mov     rdi, rax
0x1400ba738  cmp     dword ptr [rax+44h], 5
0x1400ba73c  jz      short loc_1400BA74A
0x1400ba73e  cmp     sil, 2
0x1400ba742  jz      short loc_1400BA753
0x1400ba744  cmp     sil, 4
0x1400ba748  jz      short loc_1400BA75F
0x1400ba74a  xor     ebx, ebx
0x1400ba74c  mov     eax, ebx
0x1400ba74e  jmp     loc_1400BAA2D
0x1400ba753  mov     rcx, rdi; struct SDB_DRIVE *
0x1400ba756  call    ?SpIsDriveConnected@@YAEPEAVSDB_DRIVE@@@Z; SpIsDriveConnected(SDB_DRIVE *)
0x1400ba75b  test    al, al
0x1400ba75d  jnz     short loc_1400BA74A
0x1400ba75f  mov     rcx, rdi; this
0x1400ba762  mov     [rsp+1A0h+var_30], r15
0x1400ba76a  call    ?GetDrive@SDB_DRIVE@@QEAAPEAVSC_DRIVE@@XZ; SDB_DRIVE::GetDrive(void)
0x1400ba76f  test    rax, rax
0x1400ba772  jz      short loc_1400BA77D
0x1400ba774  mov     r15, [rax+2A0h]
0x1400ba77b  jmp     short loc_1400BA789
0x1400ba77d  lea     rcx, [rdi+70h]; struct _GUID *
0x1400ba781  call    ?SpFindEnclosureById@@YAPEAVSP_ENCLOSURE@@PEAU_GUID@@@Z; SpFindEnclosureById(_GUID *)
0x1400ba786  mov     r15, rax
0x1400ba789  xor     ebx, ebx
0x1400ba78b  test    r15, r15
0x1400ba78e  jz      short loc_1400BA7F5
0x1400ba790  mov     r8d, [rdi+0E8h]
0x1400ba797  lea     rdx, [rbp+0A0h+var_100]
0x1400ba79b  xorps   xmm0, xmm0
0x1400ba79e  mov     qword ptr [rsp+1A0h+var_138+4], rbx
0x1400ba7a3  movdqu  [rsp+1A0h+var_128+4], xmm0
0x1400ba7a9  mov     dword ptr [rsp+1A0h+var_138], 17h
0x1400ba7b1  mov     rcx, r15
0x1400ba7b4  xorps   xmm2, xmm2
0x1400ba7b7  mov     dword ptr [rsp+1A0h+var_138+0Ch], 2
0x1400ba7bf  movups  xmm0, [rsp+1A0h+var_138]
0x1400ba7c4  mov     dword ptr [rsp+1A0h+var_128], 2
0x1400ba7cc  movups  xmm1, [rsp+1A0h+var_128]
0x1400ba7d1  movdqu  [rbp+0A0h+var_114], xmm2
0x1400ba7d6  movaps  [rbp+0A0h+var_100], xmm0
0x1400ba7da  movups  xmm0, xmmword ptr [rbp-78h]
0x1400ba7de  psrldq  xmm2, 0Ch
0x1400ba7e3  movaps  [rbp+0A0h+var_E0], xmm0
0x1400ba7e7  movaps  [rbp+0A0h+var_F0], xmm1
0x1400ba7eb  movd    [rbp+0A0h+var_D0], xmm2
0x1400ba7f0  call    ?SetIndications@SP_ENCLOSURE@@QEAAJU_SP_ELEMENT_INFO@@K@Z; SP_ENCLOSURE::SetIndications(_SP_ELEMENT_INFO,ulong)
0x1400ba7f5  mov     rdx, r14; struct SDB_RECORD *
0x1400ba7f8  mov     rcx, r13; this
0x1400ba7fb  call    ?ReplaceDrive@SP_POOL@@QEAAJPEAVSDB_RECORD@@@Z; SP_POOL::ReplaceDrive(SDB_RECORD *)
0x1400ba800  test    eax, eax
0x1400ba802  js      loc_1400BAA25
0x1400ba808  xor     edx, edx; struct SDB_OBJECT *
0x1400ba80a  mov     rcx, r14; this
0x1400ba80d  call    ?PreTouch@SDB_RECORD@@QEAAJPEAVSDB_OBJECT@@@Z; SDB_RECORD::PreTouch(SDB_OBJECT *)
0x1400ba812  mov     [rsp+1A0h+var_15C], eax
0x1400ba816  test    eax, eax
0x1400ba818  js      loc_1400BAA25
0x1400ba81e  mov     rcx, r14; this
0x1400ba821  mov     [rsp+1A0h+arg_10], r12
0x1400ba829  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400ba82e  mov     rdi, rax
0x1400ba831  call    ?Touch@SDB_RECORD@@QEAAXXZ; SDB_RECORD::Touch(void)
0x1400ba836  mov     dword ptr [rdi+44h], 5
0x1400ba83d  cmp     sil, 4
0x1400ba841  jnz     short loc_1400BA848
0x1400ba843  or      word ptr [rdi+40h], 1
0x1400ba848  lea     rdx, [rsp+1A0h+var_15C]; int *
0x1400ba84d  mov     rcx, rdi; struct SDB_DRIVE *
0x1400ba850  call    ?SpGetSlotState@@YAEPEAVSDB_DRIVE@@PEAJ@Z; SpGetSlotState(SDB_DRIVE *,long *)
0x1400ba855  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4
0x1400ba85c  mov     r12d, [rsp+1A0h+var_15C]
0x1400ba861  movzx   r14d, al
0x1400ba865  jz      short loc_1400BA87F
0x1400ba867  mov     [rsp+1A0h+var_170], r14d
0x1400ba86c  lea     r9, [rdi+20h]
0x1400ba870  mov     dword ptr [rsp+1A0h+UserData], r12d
0x1400ba875  mov     byte ptr [rsp+1A0h+UserDataCount], sil
0x1400ba87a  call    McTemplateK0juqq_EtwWriteTransfer
0x1400ba87f  mov     ecx, cs:dword_14007F050
0x1400ba885  cmp     ecx, 5
0x1400ba888  jbe     loc_1400BA9C9
0x1400ba88e  mov     rcx, cs:qword_14007F068
0x1400ba895  mov     rdx, 400000000000h
0x1400ba89f  mov     rax, cs:qword_14007F060
0x1400ba8a6  test    rdx, rax
0x1400ba8a9  jz      loc_1400BA9C9
0x1400ba8af  mov     rax, rcx
0x1400ba8b2  and     rax, rdx
0x1400ba8b5  cmp     rax, rcx
0x1400ba8b8  jnz     loc_1400BA9C9
0x1400ba8be  mov     [rsp+1A0h+EventDescriptor.Keyword], rdx
0x1400ba8c3  lea     rax, [rsp+1A0h+var_160]
0x1400ba8c8  mov     [rbp+0A0h+var_50], rax
0x1400ba8cc  lea     rcx, _TraceLoggingMetadata
0x1400ba8d3  mov     [rsp+1A0h+var_160], r14b
0x1400ba8d8  lea     rax, [rsp+1A0h+var_15C]
0x1400ba8dd  mov     [rbp+0A0h+var_60], rax
0x1400ba8e1  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x1400ba8e6  mov     [rsp+1A0h+var_15C], r12d
0x1400ba8eb  lea     rax, [rsp+1A0h+var_158]
0x1400ba8f0  mov     [rbp+0A0h+var_70], rax
0x1400ba8f4  xor     r9d, r9d; RelatedActivityId
0x1400ba8f7  mov     [rsp+1A0h+var_158], esi
0x1400ba8fb  lea     rax, [rdi+20h]
0x1400ba8ff  mov     [rbp+0A0h+var_80], rax
0x1400ba903  xor     r8d, r8d; ActivityId
0x1400ba906  mov     [rsp+1A0h+var_150], 1000000h
0x1400ba90f  lea     rax, [r13+6Ch]
0x1400ba913  mov     [rbp+0A0h+var_90], rax
0x1400ba917  lea     rax, [rsp+1A0h+var_150]
0x1400ba91c  mov     [rbp+0A0h+var_A0], rax
0x1400ba920  movzx   eax, cs:word_140075C0B
0x1400ba927  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], eax
0x1400ba92b  mov     rax, cs:off_14007F058
0x1400ba932  mov     [rbp+0A0h+var_C0.Ptr], rax
0x1400ba936  mov     [rbp+0A0h+var_48], 1
0x1400ba93e  mov     [rbp+0A0h+var_58], 4
0x1400ba946  mov     [rbp+0A0h+var_68], 4
0x1400ba94e  mov     [rbp+0A0h+var_78], 10h
0x1400ba956  mov     [rbp+0A0h+var_88], 10h
0x1400ba95e  mov     [rbp+0A0h+var_98], 8
0x1400ba966  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], 0B000000h
0x1400ba96e  movzx   eax, word ptr [rax]
0x1400ba971  mov     [rbp+0A0h+var_C0.Size], eax
0x1400ba974  lea     rax, byte_140075C15
0x1400ba97b  mov     [rbp+0A0h+var_B0], rax
0x1400ba97f  lea     rax, _TraceLoggingMetadataEnd
0x1400ba986  sub     eax, ecx
0x1400ba988  mov     dword ptr [rbp+0A0h+var_C0.0Ch], 2
0x1400ba98f  mov     [rbp+0A0h+var_A8], 5Ah ; 'Z'
0x1400ba996  mov     [rbp+0A0h+var_A4], 1
0x1400ba99d  mov     [rsp+1A0h+var_154], eax
0x1400ba9a1  mov     eax, [rsp+1A0h+var_154]
0x1400ba9a5  mov     rcx, cs:RegHandle; RegHandle
0x1400ba9ac  lea     rax, [rbp+0A0h+var_C0]
0x1400ba9b0  mov     [rsp+1A0h+UserData], rax; UserData
0x1400ba9b5  mov     [rsp+1A0h+UserDataCount], 8; UserDataCount
0x1400ba9bd  call    cs:__imp_EtwWriteTransfer
0x1400ba9c4  nop     dword ptr [rax+rax+00h]
0x1400ba9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba9d0  lea     rax, WPP_GLOBAL_Control
0x1400ba9d7  cmp     rcx, rax
0x1400ba9da  jz      short loc_1400BAA1B
0x1400ba9dc  mov     eax, [rcx+2Ch]
0x1400ba9df  test    al, 10h
0x1400ba9e1  jz      short loc_1400BAA1B
0x1400ba9e3  cmp     byte ptr [rcx+29h], 3
0x1400ba9e7  jb      short loc_1400BAA1B
0x1400ba9e9  test    r15, r15
0x1400ba9ec  jz      short loc_1400BA9F4
0x1400ba9ee  add     r15, 10h
0x1400ba9f2  jmp     short loc_1400BA9FB
0x1400ba9f4  lea     r15, GUID_NULL
0x1400ba9fb  mov     rcx, [rcx+18h]
0x1400ba9ff  lea     r9, [rdi+20h]
0x1400baa03  mov     [rsp+1A0h+var_168], r14d
0x1400baa08  mov     [rsp+1A0h+var_170], r12d
0x1400baa0d  mov     [rsp+1A0h+UserData], r15
0x1400baa12  mov     [rsp+1A0h+UserDataCount], esi
0x1400baa16  call    WPP_SF__guid_L_guid_dd
0x1400baa1b  mov     r12, [rsp+1A0h+arg_10]
0x1400baa23  mov     eax, ebx
0x1400baa25  mov     r15, [rsp+1A0h+var_30]
0x1400baa2d  mov     rcx, [rbp+0A0h+var_40]
0x1400baa31  xor     rcx, rsp; StackCookie
0x1400baa34  call    __security_check_cookie
0x1400baa39  add     rsp, 178h
0x1400baa40  pop     r14
0x1400baa42  pop     r13
0x1400baa44  pop     rdi
0x1400baa45  pop     rsi
0x1400baa46  pop     rbx
0x1400baa47  pop     rbp
0x1400baa48  retn
```
