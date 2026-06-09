# Storage::CVolumeInfoEnum::Next(tagVOLUMEINFO *)

- ea: `0x180001ed0`
- end: `0x1800023a4`
- name: `?Next@CVolumeInfoEnum@Storage@@UEAAJPEAUtagVOLUMEINFO@@@Z`
- size: `1236`
- prototype: `int(Storage::CVolumeInfoEnum *__hidden this, struct tagVOLUMEINFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001ed0`
- `0x180003570`
- `0x1800140f0`
- `0x180016fa0`
- `0x180019280`
- `0x1800235a8`
- `0x18002b958`
- `0x18002c010`
- `0x18002c094`
- `0x180032b38`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000230b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000233d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800022f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000230b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000233d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002353`

## pseudocode

```c
__int64 __fastcall Storage::CVolumeInfoEnum::Next(Storage::CVolumeInfoEnum *this, struct tagVOLUMEINFO *a2)
{
  __int64 v2; // rdi
  int v4; // r14d
  _DWORD *v5; // r15
  __int64 v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  int BasicInfo; // ebx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  unsigned int v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  unsigned int v28; // [rsp+40h] [rbp-C0h]
  unsigned int v29; // [rsp+50h] [rbp-B0h]
  unsigned int v30[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v31[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v33[40]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 Src[14]; // [rsp+160h] [rbp+60h] BYREF
  int v35; // [rsp+17Ch] [rbp+7Ch]
  int v36; // [rsp+194h] [rbp+94h]
  int v37; // [rsp+198h] [rbp+98h]
  unsigned __int16 v38[242]; // [rsp+19Ch] [rbp+9Ch] BYREF
  unsigned __int16 v39[56]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v40[272]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int16 v41[272]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v42[272]; // [rsp+830h] [rbp+730h] BYREF
  unsigned __int16 v43[264]; // [rsp+A50h] [rbp+950h] BYREF

  v2 = *((_QWORD *)this + 2);
  v4 = 1;
  v5 = 0;
  v6 = *(_QWORD *)(v2 + 32);
  v7 = (struct _RTL_CRITICAL_SECTION *)(v6 + 8);
  if ( !v6 )
    v7 = 0;
  EnterCriticalSection(v7);
  v8 = *(_QWORD *)(v2 + 16);
  if ( v8 )
  {
    if ( *(_DWORD *)(v2 + 24) && *(_QWORD *)(v8 + 16) )
      goto LABEL_12;
    v8 = *(_QWORD *)(v8 + 24);
    if ( v8 )
    {
      while ( !*(_QWORD *)(v8 + 16) )
      {
        v8 = *(_QWORD *)(v8 + 24);
        if ( !v8 )
          goto LABEL_11;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    }
LABEL_11:
    CRefCounted::Release(*(CRefCounted **)(v2 + 16));
    *(_QWORD *)(v2 + 16) = v8;
    if ( v8 )
    {
LABEL_12:
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v8 + 16) + 24LL));
      v5 = *(_DWORD **)(v8 + 16);
      v4 = 0;
    }
    *(_DWORD *)(v2 + 24) = 0;
  }
  v9 = *(_QWORD *)(v2 + 32);
  v10 = (struct _RTL_CRITICAL_SECTION *)(v9 + 8);
  if ( !v9 )
    v10 = 0;
  LeaveCriticalSection(v10);
  if ( v4 == 1 )
    return 1;
  memset_0(Src, 0, 0x130u);
  v30[0] = 0;
  memset_0(a2, 0, 0xA0u);
  BasicInfo = Storage::CVolume::GetBasicInfo((Storage::CVolume *)(v5 + 8), (struct Storage::VOLUMEBASICINFO *)Src);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  *(_DWORD *)a2 = -1163005939;
  BasicInfo = CNamedElemHelper::GetName((CNamedElemHelper *)(v5 + 8), v43, 0x104u, v30);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  BasicInfo = Storage::CVolume::GetVolumeConstInfo(
                (Storage::CVolume *)(v5 + 8),
                v39,
                v12,
                (unsigned int *)a2 + 1,
                (unsigned int *)a2 + 2,
                (unsigned int *)a2 + 3);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  *((_DWORD *)a2 + 13) = v37;
  *((_DWORD *)a2 + 12) = v36;
  *((_DWORD *)a2 + 14) = v35;
  BasicInfo = StringCchCopyW((unsigned __int16 *)a2 + 30, 9u, v38);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  BasicInfo = Storage::CVolume::GetVolumeMediaInfo(
                (Storage::CVolume *)(v5 + 8),
                v33,
                (_DWORD)a2 + 16,
                v32,
                v25,
                (unsigned int *)a2 + 8,
                (unsigned int *)a2 + 9,
                (unsigned int *)a2 + 10,
                (unsigned int *)a2 + 11,
                (unsigned int *)a2 + 4,
                (unsigned int *)a2 + 5,
                (unsigned int *)a2 + 6,
                (unsigned int *)a2 + 7);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  Src[0] = 0;
  v31[0] = 0;
  v40[0] = 0;
  v41[0] = 0;
  v42[0] = 0;
  BasicInfo = Storage::CVolume::GetIconAndLabelInfo(
                (Storage::CVolume *)(v5 + 8),
                Src,
                v13,
                v31,
                v26,
                v40,
                v27,
                v41,
                v28,
                v42,
                v29);
  if ( BasicInfo < 0 )
    goto LABEL_41;
  if ( Src[0] )
  {
    BasicInfo = DupOleString(Src);
    if ( BasicInfo < 0 )
      goto LABEL_41;
  }
  if ( v31[0] )
  {
    BasicInfo = DupOleString(v31);
    if ( BasicInfo < 0 )
      goto LABEL_41;
  }
  if ( v40[0] && (BasicInfo = DupOleString(v40), BasicInfo < 0)
    || v41[0] && (BasicInfo = DupOleString(v41), BasicInfo < 0)
    || v42[0] && (BasicInfo = DupOleString(v42), BasicInfo < 0)
    || (BasicInfo = DupOleString(v43), BasicInfo < 0)
    || (BasicInfo = DupOleString(v39), BasicInfo < 0)
    || (BasicInfo = DupOleString(v33), BasicInfo < 0)
    || (BasicInfo = DupOleString(v32), BasicInfo < 0) )
  {
LABEL_41:
    v14 = (void *)*((_QWORD *)a2 + 10);
    if ( v14 )
    {
      CoTaskMemFree(v14);
      *((_QWORD *)a2 + 10) = 0;
    }
    v15 = (void *)*((_QWORD *)a2 + 11);
    if ( v15 )
    {
      CoTaskMemFree(v15);
      *((_QWORD *)a2 + 11) = 0;
    }
    v16 = (void *)*((_QWORD *)a2 + 12);
    if ( v16 )
    {
      CoTaskMemFree(v16);
      *((_QWORD *)a2 + 12) = 0;
    }
    v17 = (void *)*((_QWORD *)a2 + 13);
    if ( v17 )
    {
      CoTaskMemFree(v17);
      *((_QWORD *)a2 + 13) = 0;
    }
    v18 = (void *)*((_QWORD *)a2 + 15);
    if ( v18 )
    {
      CoTaskMemFree(v18);
      *((_QWORD *)a2 + 15) = 0;
    }
    v19 = (void *)*((_QWORD *)a2 + 16);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      *((_QWORD *)a2 + 16) = 0;
    }
    v20 = (void *)*((_QWORD *)a2 + 17);
    if ( v20 )
    {
      CoTaskMemFree(v20);
      *((_QWORD *)a2 + 17) = 0;
    }
    v21 = (void *)*((_QWORD *)a2 + 18);
    if ( v21 )
    {
      CoTaskMemFree(v21);
      *((_QWORD *)a2 + 18) = 0;
    }
    v22 = (void *)*((_QWORD *)a2 + 19);
    if ( v22 )
    {
      CoTaskMemFree(v22);
      *((_QWORD *)a2 + 19) = 0;
    }
    v23 = (void *)*((_QWORD *)a2 + 14);
    if ( v23 )
      CoTaskMemFree(v23);
    memset_0(a2, 0, 0xA0u);
  }
  else if ( v5[809]
         && (int)PnPHelper::CHWDeviceInst::GetDevNodeName((PnPHelper::CHWDeviceInst *)(v5 + 670), Src, 0xC8u) >= 0
         && (int)DupOleString(Src) < 0 )
  {
    *((_QWORD *)a2 + 14) = 0;
  }
  CRefCounted::Release((CRefCounted *)(v5 + 4));
  return (unsigned int)BasicInfo;
}

```

## disassembly

```asm
0x180001ed0  mov     [rsp-8+arg_10], rbx
0x180001ed5  mov     [rsp-8+arg_18], rsi
0x180001eda  push    rbp
0x180001edb  push    rdi
0x180001edc  push    r12
0x180001ede  push    r14
0x180001ee0  push    r15
0x180001ee2  lea     rbp, [rsp-0B70h]
0x180001eea  sub     rsp, 0C70h
0x180001ef1  mov     rax, cs:__security_cookie
0x180001ef8  xor     rax, rsp
0x180001efb  mov     [rbp+0B90h+var_30], rax
0x180001f02  mov     rdi, [rcx+10h]
0x180001f06  xor     r12d, r12d
0x180001f09  mov     rsi, rdx
0x180001f0c  mov     r14d, 1
0x180001f12  mov     r15d, r12d
0x180001f15  mov     rdx, [rdi+20h]
0x180001f19  test    rdx, rdx
0x180001f1c  lea     rcx, [rdx+8]
0x180001f20  cmovz   rcx, r12; lpCriticalSection
0x180001f24  call    cs:__imp_EnterCriticalSection
0x180001f2a  mov     rbx, [rdi+10h]
0x180001f2e  test    rbx, rbx
0x180001f31  jz      short loc_180001F82
0x180001f33  cmp     [rdi+18h], r12d
0x180001f37  jz      short loc_180001F3F
0x180001f39  cmp     [rbx+10h], r12
0x180001f3d  jnz     short loc_180001F6F
0x180001f3f  mov     rbx, [rbx+18h]
0x180001f43  test    rbx, rbx
0x180001f46  jz      short loc_180001F5D
0x180001f48  cmp     [rbx+10h], r12
0x180001f4c  jnz     short loc_180001F59
0x180001f4e  mov     rbx, [rbx+18h]
0x180001f52  test    rbx, rbx
0x180001f55  jnz     short loc_180001F48
0x180001f57  jmp     short loc_180001F5D
0x180001f59  lock inc dword ptr [rbx+8]
0x180001f5d  mov     rcx, [rdi+10h]; this
0x180001f61  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180001f66  mov     [rdi+10h], rbx
0x180001f6a  test    rbx, rbx
0x180001f6d  jz      short loc_180001F7E
0x180001f6f  mov     rax, [rbx+10h]
0x180001f73  lock inc dword ptr [rax+18h]
0x180001f77  mov     r15, [rbx+10h]
0x180001f7b  mov     r14d, r12d
0x180001f7e  mov     [rdi+18h], r12d
0x180001f82  mov     rdx, [rdi+20h]
0x180001f86  test    rdx, rdx
0x180001f89  lea     rcx, [rdx+8]
0x180001f8d  cmovz   rcx, r12; lpCriticalSection
0x180001f91  call    cs:__imp_LeaveCriticalSection
0x180001f97  cmp     r14d, 1
0x180001f9b  jz      loc_180002376
0x180001fa1  xor     edx, edx; Val
0x180001fa3  lea     rcx, [rbp+0B90h+Src]; void *
0x180001fa7  mov     r8d, 130h; Size
0x180001fad  call    memset_0
0x180001fb2  xor     edx, edx; Val
0x180001fb4  mov     [rsp+0C90h+var_C20], r12d
0x180001fb9  mov     r8d, 0A0h; Size
0x180001fbf  mov     rcx, rsi; void *
0x180001fc2  call    memset_0
0x180001fc7  lea     rdx, [rbp+0B90h+Src]; struct Storage::VOLUMEBASICINFO *
0x180001fcb  lea     rcx, [r15+20h]; this
0x180001fcf  call    ?GetBasicInfo@CVolume@Storage@@QEAAJPEAUVOLUMEBASICINFO@2@@Z; Storage::CVolume::GetBasicInfo(Storage::VOLUMEBASICINFO *)
0x180001fd4  mov     ebx, eax
0x180001fd6  test    eax, eax
0x180001fd8  js      loc_180002287
0x180001fde  lea     r9, [rsp+0C90h+var_C20]; unsigned int *
0x180001fe3  mov     dword ptr [rsi], 0BAADF00Dh
0x180001fe9  mov     r8d, 104h; unsigned int
0x180001fef  lea     rdx, [rbp+0B90h+var_240]; unsigned __int16 *
0x180001ff6  lea     rcx, [r15+20h]; this
0x180001ffa  call    ?GetName@CNamedElemHelper@@QEAAJPEAGKPEAK@Z; CNamedElemHelper::GetName(ushort *,ulong,ulong *)
0x180001fff  mov     ebx, eax
0x180002001  test    eax, eax
0x180002003  js      loc_180002287
0x180002009  lea     rax, [rsi+0Ch]
0x18000200d  lea     rcx, [rsi+8]
0x180002011  mov     [rsp+0C90h+var_C68], rax; unsigned int *
0x180002016  mov     [rsp+0C90h+var_C70], rcx; unsigned int
0x18000201b  lea     r9, [rsi+4]; unsigned int *
0x18000201f  lea     rcx, [r15+20h]; this
0x180002023  lea     rdx, [rbp+0B90h+var_910]; unsigned __int16 *
0x18000202a  call    ?GetVolumeConstInfo@CVolume@Storage@@QEAAJPEAGKPEAK11@Z; Storage::CVolume::GetVolumeConstInfo(ushort *,ulong,ulong *,ulong *,ulong *)
0x18000202f  mov     ebx, eax
0x180002031  test    eax, eax
0x180002033  js      loc_180002287
0x180002039  mov     eax, [rbp+0B90h+var_AF8]
0x18000203f  lea     rcx, [rsi+3Ch]; unsigned __int16 *
0x180002043  mov     [rsi+34h], eax
0x180002046  lea     r8, [rbp+0B90h+var_AF4]; unsigned __int16 *
0x18000204d  mov     eax, [rbp+0B90h+var_AFC]
0x180002053  mov     edx, 9; unsigned __int64
0x180002058  mov     [rsi+30h], eax
0x18000205b  mov     eax, [rbp+0B90h+var_B14]
0x18000205e  mov     [rsi+38h], eax
0x180002061  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002066  mov     ebx, eax
0x180002068  test    eax, eax
0x18000206a  js      loc_180002287
0x180002070  lea     rax, [rsi+1Ch]
0x180002074  mov     [rsp+0C90h+var_C30], rax; unsigned int *
0x180002079  lea     rcx, [rsi+18h]
0x18000207d  mov     [rsp+0C90h+var_C38], rcx; unsigned int *
0x180002082  lea     rdx, [rsi+14h]
0x180002086  mov     [rsp+0C90h+var_C40], rdx; unsigned int
0x18000208b  lea     r8, [rsi+10h]; unsigned int
0x18000208f  mov     [rsp+0C90h+var_C48], r8; unsigned int *
0x180002094  lea     r9, [rsi+2Ch]
0x180002098  mov     [rsp+0C90h+var_C50], r9; unsigned int
0x18000209d  lea     r10, [rsi+28h]
0x1800020a1  mov     [rsp+0C90h+var_C58], r10; unsigned int *
0x1800020a6  lea     r11, [rsi+24h]
0x1800020aa  mov     [rsp+0C90h+var_C60], r11; unsigned int
0x1800020af  lea     rbx, [rsi+20h]
0x1800020b3  lea     r9, [rbp+0B90h+var_BC0]; unsigned __int16 *
0x1800020b7  mov     [rsp+0C90h+var_C68], rbx; unsigned int *
0x1800020bc  lea     rdx, [rbp+0B90h+var_B80]; unsigned __int16 *
0x1800020c0  lea     rcx, [r15+20h]; this
0x1800020c4  call    ?GetVolumeMediaInfo@CVolume@Storage@@QEAAJPEAGK0KPEAK1111111@Z; Storage::CVolume::GetVolumeMediaInfo(ushort *,ulong,ushort *,ulong,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x1800020c9  mov     ebx, eax
0x1800020cb  test    eax, eax
0x1800020cd  js      loc_180002287
0x1800020d3  lea     rax, [rbp+0B90h+var_460]
0x1800020da  mov     [rbp+0B90h+Src], r12w
0x1800020df  mov     [rsp+0C90h+var_C48], rax; unsigned __int16 *
0x1800020e4  lea     r9, [rbp+0B90h+var_C10]; unsigned __int16 *
0x1800020e8  lea     rax, [rbp+0B90h+var_680]
0x1800020ef  mov     [rbp+0B90h+var_C10], r12w
0x1800020f4  mov     [rsp+0C90h+var_C58], rax; unsigned __int16 *
0x1800020f9  lea     rdx, [rbp+0B90h+Src]; unsigned __int16 *
0x1800020fd  lea     rax, [rbp+0B90h+var_8A0]
0x180002104  mov     [rbp+0B90h+var_8A0], r12w
0x18000210c  lea     rcx, [r15+20h]; this
0x180002110  mov     [rsp+0C90h+var_C68], rax; unsigned __int16 *
0x180002115  mov     [rbp+0B90h+var_680], r12w
0x18000211d  mov     [rbp+0B90h+var_460], r12w
0x180002125  call    ?GetIconAndLabelInfo@CVolume@Storage@@QEAAJPEAGK0K0K0K0K@Z; Storage::CVolume::GetIconAndLabelInfo(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong)
0x18000212a  mov     ebx, eax
0x18000212c  test    eax, eax
0x18000212e  js      loc_180002287
0x180002134  cmp     [rbp+0B90h+Src], r12w
0x180002139  jz      short loc_180002152
0x18000213b  lea     rdx, [rsi+78h]
0x18000213f  lea     rcx, [rbp+0B90h+Src]; Src
0x180002143  call    DupOleString
0x180002148  mov     ebx, eax
0x18000214a  test    eax, eax
0x18000214c  js      loc_180002287
0x180002152  cmp     [rbp+0B90h+var_C10], r12w
0x180002157  jz      short loc_180002173
0x180002159  lea     rdx, [rsi+80h]
0x180002160  lea     rcx, [rbp+0B90h+var_C10]; Src
0x180002164  call    DupOleString
0x180002169  mov     ebx, eax
0x18000216b  test    eax, eax
0x18000216d  js      loc_180002287
0x180002173  cmp     [rbp+0B90h+var_8A0], r12w
0x18000217b  jz      short loc_18000219A
0x18000217d  lea     rdx, [rsi+88h]
0x180002184  lea     rcx, [rbp+0B90h+var_8A0]; Src
0x18000218b  call    DupOleString
0x180002190  mov     ebx, eax
0x180002192  test    eax, eax
0x180002194  js      loc_180002287
0x18000219a  cmp     [rbp+0B90h+var_680], r12w
0x1800021a2  jz      short loc_1800021C1
0x1800021a4  lea     rdx, [rsi+90h]
0x1800021ab  lea     rcx, [rbp+0B90h+var_680]; Src
0x1800021b2  call    DupOleString
0x1800021b7  mov     ebx, eax
0x1800021b9  test    eax, eax
0x1800021bb  js      loc_180002287
0x1800021c1  cmp     [rbp+0B90h+var_460], r12w
0x1800021c9  jz      short loc_1800021E8
0x1800021cb  lea     rdx, [rsi+98h]
0x1800021d2  lea     rcx, [rbp+0B90h+var_460]; Src
0x1800021d9  call    DupOleString
0x1800021de  mov     ebx, eax
0x1800021e0  test    eax, eax
0x1800021e2  js      loc_180002287
0x1800021e8  lea     rdx, [rsi+50h]
0x1800021ec  lea     rcx, [rbp+0B90h+var_240]; Src
0x1800021f3  call    DupOleString
0x1800021f8  mov     ebx, eax
0x1800021fa  test    eax, eax
0x1800021fc  js      loc_180002287
0x180002202  lea     rdx, [rsi+58h]
0x180002206  lea     rcx, [rbp+0B90h+var_910]; Src
0x18000220d  call    DupOleString
0x180002212  mov     ebx, eax
0x180002214  test    eax, eax
0x180002216  js      short loc_180002287
0x180002218  lea     rdx, [rsi+60h]
0x18000221c  lea     rcx, [rbp+0B90h+var_B80]; Src
0x180002220  call    DupOleString
0x180002225  mov     ebx, eax
0x180002227  test    eax, eax
0x180002229  js      short loc_180002287
0x18000222b  lea     rdx, [rsi+68h]
0x18000222f  lea     rcx, [rbp+0B90h+var_BC0]; Src
0x180002233  call    DupOleString
0x180002238  mov     ebx, eax
0x18000223a  test    eax, eax
0x18000223c  js      short loc_180002287
0x18000223e  cmp     [r15+0CA4h], r12d
0x180002245  jz      loc_180002369
0x18000224b  lea     rcx, [r15+0A78h]; this
0x180002252  mov     r8d, 0C8h; unsigned int
0x180002258  lea     rdx, [rbp+0B90h+Src]; unsigned __int16 *
0x18000225c  call    ?GetDevNodeName@CHWDeviceInst@PnPHelper@@QEAAJPEAGK@Z; PnPHelper::CHWDeviceInst::GetDevNodeName(ushort *,ulong)
0x180002261  test    eax, eax
0x180002263  js      loc_180002369
0x180002269  lea     rdx, [rsi+70h]
0x18000226d  lea     rcx, [rbp+0B90h+Src]; Src
0x180002271  call    DupOleString
0x180002276  test    eax, eax
0x180002278  jns     loc_180002369
0x18000227e  mov     [rsi+70h], r12
0x180002282  jmp     loc_180002369
0x180002287  mov     rcx, [rsi+50h]; pv
0x18000228b  test    rcx, rcx
0x18000228e  jz      short loc_18000229A
0x180002290  call    cs:__imp_CoTaskMemFree
0x180002296  mov     [rsi+50h], r12
0x18000229a  mov     rcx, [rsi+58h]; pv
0x18000229e  test    rcx, rcx
0x1800022a1  jz      short loc_1800022AD
0x1800022a3  call    cs:__imp_CoTaskMemFree
0x1800022a9  mov     [rsi+58h], r12
0x1800022ad  mov     rcx, [rsi+60h]; pv
0x1800022b1  test    rcx, rcx
0x1800022b4  jz      short loc_1800022C0
0x1800022b6  call    cs:__imp_CoTaskMemFree
0x1800022bc  mov     [rsi+60h], r12
0x1800022c0  mov     rcx, [rsi+68h]; pv
0x1800022c4  test    rcx, rcx
0x1800022c7  jz      short loc_1800022D3
0x1800022c9  call    cs:__imp_CoTaskMemFree
0x1800022cf  mov     [rsi+68h], r12
0x1800022d3  mov     rcx, [rsi+78h]; pv
0x1800022d7  test    rcx, rcx
0x1800022da  jz      short loc_1800022E6
0x1800022dc  call    cs:__imp_CoTaskMemFree
0x1800022e2  mov     [rsi+78h], r12
0x1800022e6  mov     rcx, [rsi+80h]; pv
0x1800022ed  test    rcx, rcx
0x1800022f0  jz      short loc_1800022FF
0x1800022f2  call    cs:__imp_CoTaskMemFree
0x1800022f8  mov     [rsi+80h], r12
0x1800022ff  mov     rcx, [rsi+88h]; pv
0x180002306  test    rcx, rcx
0x180002309  jz      short loc_180002318
0x18000230b  call    cs:__imp_CoTaskMemFree
0x180002311  mov     [rsi+88h], r12
0x180002318  mov     rcx, [rsi+90h]; pv
0x18000231f  test    rcx, rcx
0x180002322  jz      short loc_180002331
0x180002324  call    cs:__imp_CoTaskMemFree
0x18000232a  mov     [rsi+90h], r12
0x180002331  mov     rcx, [rsi+98h]; pv
0x180002338  test    rcx, rcx
0x18000233b  jz      short loc_18000234A
0x18000233d  call    cs:__imp_CoTaskMemFree
0x180002343  mov     [rsi+98h], r12
0x18000234a  mov     rcx, [rsi+70h]; pv
0x18000234e  test    rcx, rcx
0x180002351  jz      short loc_180002359
0x180002353  call    cs:__imp_CoTaskMemFree
0x180002359  xor     edx, edx; Val
0x18000235b  mov     r8d, 0A0h; Size
0x180002361  mov     rcx, rsi; void *
0x180002364  call    memset_0
0x180002369  lea     rcx, [r15+10h]; this
0x18000236d  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002372  mov     eax, ebx
0x180002374  jmp     short loc_180002379
0x180002376  mov     eax, r14d
0x180002379  mov     rcx, [rbp+0B90h+var_30]
0x180002380  xor     rcx, rsp; StackCookie
0x180002383  call    __security_check_cookie
0x180002388  lea     r11, [rsp+0C90h+var_20]
0x180002390  mov     rbx, [r11+40h]
0x180002394  mov     rsi, [r11+48h]
0x180002398  mov     rsp, r11
0x18000239b  pop     r15
0x18000239d  pop     r14
0x18000239f  pop     r12
0x1800023a1  pop     rdi
0x1800023a2  pop     rbp
0x1800023a3  retn
```
