# NonYieldSystemInformation::InitNonYieldSystemInformation(void)

- ea: `0x100407030`
- end: `0x100407481`
- name: `?InitNonYieldSystemInformation@NonYieldSystemInformation@@QEAA?AW4SOS_RESULT@@XZ`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100416770`

## callees

- `0x100407030`
- `0x100408160`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040709f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100407136`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004071c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040709f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100407136`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004071c8`
- `sqldk!SystemThread_TlsOffset` at `0x100407084`
- `sqldk!SystemThread_TlsOffset` at `0x10040711b`
- `sqldk!SystemThread_TlsOffset` at `0x1004071ad`
- `sqldk!SystemThread_TlsIndex` at `0x10040707b`
- `sqldk!SystemThread_TlsIndex` at `0x100407112`
- `sqldk!SystemThread_TlsIndex` at `0x1004071a4`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x1004070de`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100407173`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100407207`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x1004070de`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100407173`
- `sqldk!?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z` at `0x100407207`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x100407042`

## pseudocode

```c
__int64 __fastcall NonYieldSystemInformation::InitNonYieldSystemInformation(_QWORD *a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  __int64 v4; // rbp
  _QWORD *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _WORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int16 v13; // ax
  bool v14; // zf
  _WORD *v15; // rax
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int16 v18; // ax
  _WORD *v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // rcx
  __int16 v22; // ax
  _WORD *v23; // rax
  __int64 v24; // rdx
  _WORD *v25; // rcx
  __int16 v26; // ax
  _WORD *v27; // rax
  __int64 v28; // rdx
  _WORD *v29; // rcx
  __int16 v30; // ax
  _WORD *v31; // rax
  __int64 v32; // rdx
  _WORD *v33; // rcx
  __int16 v34; // ax
  _WORD *v35; // rax
  char *v36; // rdx
  signed __int64 v37; // r9
  __int16 v38; // cx
  char *v39; // rcx
  __int64 result; // rax

  v2 = SOS_PublicGlobals::sm_NodeManager[5];
  if ( v2 && (*(_BYTE *)(v2 + 1568) & 0x10) != 0 )
    v2 = 0;
  a1[3] = 0;
  a1[19993] = -1;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v3 = (_QWORD *)SOS_RingBuffer::Create(44, 568, SQLSOS_NonYieldProcessTableRecord::sm_NumberOfRecords);
  v4 = v2 + 96;
  v5 = v3;
  if ( !v3 )
  {
    *a1 = 0;
    return 0x80000000LL;
  }
  *v3 = 0;
  v3[1] = 0;
  TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(v2 + 96, v3);
  *a1 = v5;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v6 = (_QWORD *)SOS_RingBuffer::Create(45, 64, SQLSOS_NonYieldThreadTableRecord::sm_NumberOfRecords);
  v7 = v6;
  if ( !v6 )
  {
    a1[1] = 0;
    return 0x80000000LL;
  }
  *v6 = 0;
  v6[1] = 0;
  TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(v4, v6);
  a1[1] = v7;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v8 = (_QWORD *)SOS_RingBuffer::Create(46, 336, SQLSOS_NonYieldCopiedStackRecord::sm_NumberOfRecords);
  v9 = v8;
  if ( !v8 )
  {
    a1[2] = 0;
    return 0x80000000LL;
  }
  *v8 = 0;
  v8[1] = 0;
  TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(v4, v8);
  v10 = a1 + 7;
  a1[2] = v9;
  v11 = 2048;
  v12 = 2048;
  do
  {
    if ( v12 == -2147481598 )
      break;
    v13 = *(_WORD *)((char *)v10 + (char *)L"\\PhysicalDisk(_Total)\\Avg. Disk Queue Length" - (char *)(a1 + 7));
    if ( !v13 )
      break;
    *v10++ = v13;
    --v12;
  }
  while ( v12 );
  v14 = v12 == 0;
  v15 = v10 - 1;
  v16 = 2048;
  if ( !v14 )
    v15 = v10;
  v17 = a1 + 522;
  *v15 = 0;
  do
  {
    if ( v16 == -2147481598 )
      break;
    v18 = *(_WORD *)((char *)v17 + (char *)L"\\PhysicalDisk(_Total)\\% Disk Time" - (char *)(a1 + 522));
    if ( !v18 )
      break;
    *v17++ = v18;
    --v16;
  }
  while ( v16 );
  v14 = v16 == 0;
  v19 = v17 - 1;
  v20 = 2048;
  if ( !v14 )
    v19 = v17;
  v21 = a1 + 1037;
  *v19 = 0;
  do
  {
    if ( v20 == -2147481598 )
      break;
    v22 = *(_WORD *)((char *)v21 + (char *)L"\\Memory\\Pages/sec" - (char *)(a1 + 1037));
    if ( !v22 )
      break;
    *v21++ = v22;
    --v20;
  }
  while ( v20 );
  v14 = v20 == 0;
  v23 = v21 - 1;
  v24 = 2048;
  if ( !v14 )
    v23 = v21;
  v25 = a1 + 1552;
  *v23 = 0;
  do
  {
    if ( v24 == -2147481598 )
      break;
    v26 = *(_WORD *)((char *)v25 + (char *)L"\\Memory\\Pages Output/sec" - (char *)(a1 + 1552));
    if ( !v26 )
      break;
    *v25++ = v26;
    --v24;
  }
  while ( v24 );
  v14 = v24 == 0;
  v27 = v25 - 1;
  v28 = 2048;
  if ( !v14 )
    v27 = v25;
  v29 = a1 + 2067;
  *v27 = 0;
  do
  {
    if ( v28 == -2147481598 )
      break;
    v30 = *(_WORD *)((char *)v29 + (char *)L"\\Memory\\Pages Input/sec" - (char *)(a1 + 2067));
    if ( !v30 )
      break;
    *v29++ = v30;
    --v28;
  }
  while ( v28 );
  v14 = v28 == 0;
  v31 = v29 - 1;
  v32 = 2048;
  if ( !v14 )
    v31 = v29;
  v33 = a1 + 2582;
  *v31 = 0;
  do
  {
    if ( v32 == -2147481598 )
      break;
    v34 = *(_WORD *)((char *)v33 + (char *)L"\\Memory\\Available Bytes" - (char *)(a1 + 2582));
    if ( !v34 )
      break;
    *v33++ = v34;
    --v32;
  }
  while ( v32 );
  v14 = v32 == 0;
  v35 = v33 - 1;
  v36 = (char *)(a1 + 3097);
  if ( !v14 )
    v35 = v33;
  v37 = (char *)L"\\Paging File(_Total)\\% Usage" - v36;
  *v35 = 0;
  do
  {
    if ( v11 == -2147481598 )
      break;
    v38 = *(_WORD *)&v36[v37];
    if ( !v38 )
      break;
    *(_WORD *)v36 = v38;
    v36 += 2;
    --v11;
  }
  while ( v11 );
  v39 = v36 - 2;
  result = 0;
  if ( v11 )
    v39 = v36;
  *(_WORD *)v39 = 0;
  return result;
}

```

## disassembly

```asm
0x100407030  mov     [rsp+arg_8], rbx
0x100407035  mov     [rsp+arg_10], rbp
0x10040703a  push    rsi
0x10040703b  push    rdi
0x10040703c  push    r14
0x10040703e  sub     rsp, 30h
0x100407042  mov     rax, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x100407049  xor     r14d, r14d
0x10040704c  mov     rdi, rcx
0x10040704f  mov     rbx, [rax+28h]
0x100407053  test    rbx, rbx
0x100407056  jz      short loc_100407063
0x100407058  test    byte ptr [rbx+620h], 10h
0x10040705f  cmovnz  rbx, r14
0x100407063  mov     [rcx+18h], r14
0x100407067  mov     qword ptr [rcx+270C8h], 0FFFFFFFFFFFFFFFFh
0x100407072  mov     rdx, gs:58h
0x10040707b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100407082  mov     ecx, [rax]
0x100407084  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040708b  mov     esi, [rax]
0x10040708d  add     rsi, [rdx+rcx*8]
0x100407091  mov     rax, [rsi+100h]
0x100407098  test    rax, rax
0x10040709b  jnz     short loc_1004070AC
0x10040709d  xor     ecx, ecx
0x10040709f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004070a5  mov     rax, [rsi+100h]
0x1004070ac  mov     rax, [rax+3E0h]
0x1004070b3  xor     r9d, r9d
0x1004070b6  mov     r8d, cs:?sm_NumberOfRecords@SQLSOS_NonYieldProcessTableRecord@@0KA; ulong SQLSOS_NonYieldProcessTableRecord::sm_NumberOfRecords
0x1004070bd  mov     edx, 238h
0x1004070c2  mov     rcx, [rax+140h]
0x1004070c9  lea     rax, ?SerializeRecord@SQLSOS_NonYieldProcessTableRecord@@SAXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@Z; SQLSOS_NonYieldProcessTableRecord::SerializeRecord(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x1004070d0  mov     [rsp+48h+var_20], rcx
0x1004070d5  lea     ecx, [r9+2Ch]
0x1004070d9  mov     [rsp+48h+var_28], rax
0x1004070de  call    cs:__imp_?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z; SOS_RingBuffer::Create(RINGBUFFER_TYPE,ulong,ulong,ulong,void (*)(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *),IMemObj *)
0x1004070e4  lea     rbp, [rbx+60h]
0x1004070e8  mov     rsi, rax
0x1004070eb  test    rax, rax
0x1004070ee  jz      loc_100407466
0x1004070f4  mov     rdx, rax
0x1004070f7  mov     [rax], r14
0x1004070fa  mov     rcx, rbp
0x1004070fd  mov     [rax+8], r14
0x100407101  call    ?AppendElem@?$TList@VSOS_Node@@VSOS_RingBuffer@@$0A@UTListSLock@@@@QEAAXPEAVSOS_RingBuffer@@@Z; TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(SOS_RingBuffer *)
0x100407106  mov     [rdi], rsi
0x100407109  mov     rdx, gs:58h
0x100407112  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100407119  mov     ecx, [rax]
0x10040711b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100407122  mov     ebx, [rax]
0x100407124  add     rbx, [rdx+rcx*8]
0x100407128  mov     rax, [rbx+100h]
0x10040712f  test    rax, rax
0x100407132  jnz     short loc_100407143
0x100407134  xor     ecx, ecx
0x100407136  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040713c  mov     rax, [rbx+100h]
0x100407143  mov     rax, [rax+3E0h]
0x10040714a  xor     r9d, r9d
0x10040714d  mov     r8d, cs:?sm_NumberOfRecords@SQLSOS_NonYieldThreadTableRecord@@0KA; ulong SQLSOS_NonYieldThreadTableRecord::sm_NumberOfRecords
0x100407154  mov     rcx, [rax+140h]
0x10040715b  lea     edx, [r9+40h]
0x10040715f  mov     [rsp+48h+var_20], rcx
0x100407164  lea     rax, ?SerializeRecord@SQLSOS_NonYieldThreadTableRecord@@SAXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@Z; SQLSOS_NonYieldThreadTableRecord::SerializeRecord(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x10040716b  lea     ecx, [rdx-13h]
0x10040716e  mov     [rsp+48h+var_28], rax
0x100407173  call    cs:__imp_?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z; SOS_RingBuffer::Create(RINGBUFFER_TYPE,ulong,ulong,ulong,void (*)(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *),IMemObj *)
0x100407179  mov     rbx, rax
0x10040717c  test    rax, rax
0x10040717f  jz      loc_100407460
0x100407185  mov     rdx, rax
0x100407188  mov     [rax], r14
0x10040718b  mov     rcx, rbp
0x10040718e  mov     [rax+8], r14
0x100407192  call    ?AppendElem@?$TList@VSOS_Node@@VSOS_RingBuffer@@$0A@UTListSLock@@@@QEAAXPEAVSOS_RingBuffer@@@Z; TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(SOS_RingBuffer *)
0x100407197  mov     [rdi+8], rbx
0x10040719b  mov     rdx, gs:58h
0x1004071a4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004071ab  mov     ecx, [rax]
0x1004071ad  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004071b4  mov     ebx, [rax]
0x1004071b6  add     rbx, [rdx+rcx*8]
0x1004071ba  mov     rax, [rbx+100h]
0x1004071c1  test    rax, rax
0x1004071c4  jnz     short loc_1004071D5
0x1004071c6  xor     ecx, ecx
0x1004071c8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004071ce  mov     rax, [rbx+100h]
0x1004071d5  mov     rax, [rax+3E0h]
0x1004071dc  xor     r9d, r9d
0x1004071df  mov     r8d, cs:?sm_NumberOfRecords@SQLSOS_NonYieldCopiedStackRecord@@0KA; ulong SQLSOS_NonYieldCopiedStackRecord::sm_NumberOfRecords
0x1004071e6  mov     edx, 150h
0x1004071eb  mov     rcx, [rax+140h]
0x1004071f2  lea     rax, ?SerializeRecord@SQLSOS_NonYieldCopiedStackRecord@@SAXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@Z; SQLSOS_NonYieldCopiedStackRecord::SerializeRecord(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x1004071f9  mov     [rsp+48h+var_20], rcx
0x1004071fe  lea     ecx, [r9+2Eh]
0x100407202  mov     [rsp+48h+var_28], rax
0x100407207  call    cs:__imp_?Create@SOS_RingBuffer@@CAPEAV1@W4RINGBUFFER_TYPE@@KKKP6AXPEAVSOS_RingBufferRecord@@PEA_W_KPEAPEA_WPEA_K@ZPEAVIMemObj@@@Z; SOS_RingBuffer::Create(RINGBUFFER_TYPE,ulong,ulong,ulong,void (*)(SOS_RingBufferRecord *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *),IMemObj *)
0x10040720d  mov     rbx, rax
0x100407210  test    rax, rax
0x100407213  jz      loc_10040745A
0x100407219  mov     rdx, rax
0x10040721c  mov     [rax], r14
0x10040721f  mov     rcx, rbp
0x100407222  mov     [rax+8], r14
0x100407226  call    ?AppendElem@?$TList@VSOS_Node@@VSOS_RingBuffer@@$0A@UTListSLock@@@@QEAAXPEAVSOS_RingBuffer@@@Z; TList<SOS_Node,SOS_RingBuffer,0,TListSLock>::AppendElem(SOS_RingBuffer *)
0x10040722b  lea     rcx, [rdi+38h]
0x10040722f  mov     [rdi+10h], rbx
0x100407233  mov     r8d, 800h
0x100407239  lea     r9, aPhysicaldiskTo_0; "\\PhysicalDisk(_Total)\\Avg. Disk Queue"...
0x100407240  mov     edx, r8d
0x100407243  sub     r9, rcx
0x100407246  nop     word ptr [rax+rax+00000000h]
0x100407250  lea     rax, [rdx+7FFFF7FEh]
0x100407257  test    rax, rax
0x10040725a  jz      short loc_100407273
0x10040725c  movzx   eax, word ptr [r9+rcx]
0x100407261  test    ax, ax
0x100407264  jz      short loc_100407273
0x100407266  mov     [rcx], ax
0x100407269  add     rcx, 2
0x10040726d  sub     rdx, 1
0x100407271  jnz     short loc_100407250
0x100407273  test    rdx, rdx
0x100407276  lea     rax, [rcx-2]
0x10040727a  lea     r9, aPhysicaldiskTo; "\\PhysicalDisk(_Total)\\% Disk Time"
0x100407281  mov     rdx, r8
0x100407284  cmovnz  rax, rcx
0x100407288  lea     rcx, [rdi+1050h]
0x10040728f  sub     r9, rcx
0x100407292  mov     [rax], r14w
0x100407296  nop     word ptr [rax+rax+00000000h]
0x1004072a0  lea     rax, [rdx+7FFFF7FEh]
0x1004072a7  test    rax, rax
0x1004072aa  jz      short loc_1004072C3
0x1004072ac  movzx   eax, word ptr [r9+rcx]
0x1004072b1  test    ax, ax
0x1004072b4  jz      short loc_1004072C3
0x1004072b6  mov     [rcx], ax
0x1004072b9  add     rcx, 2
0x1004072bd  sub     rdx, 1
0x1004072c1  jnz     short loc_1004072A0
0x1004072c3  test    rdx, rdx
0x1004072c6  lea     rax, [rcx-2]
0x1004072ca  lea     r9, aMemoryPagesSec; "\\Memory\\Pages/sec"
0x1004072d1  mov     rdx, r8
0x1004072d4  cmovnz  rax, rcx
0x1004072d8  lea     rcx, [rdi+2068h]
0x1004072df  sub     r9, rcx
0x1004072e2  mov     [rax], r14w
0x1004072e6  nop     word ptr [rax+rax+00000000h]
0x1004072f0  lea     rax, [rdx+7FFFF7FEh]
0x1004072f7  test    rax, rax
0x1004072fa  jz      short loc_100407313
0x1004072fc  movzx   eax, word ptr [r9+rcx]
0x100407301  test    ax, ax
0x100407304  jz      short loc_100407313
0x100407306  mov     [rcx], ax
0x100407309  add     rcx, 2
0x10040730d  sub     rdx, 1
0x100407311  jnz     short loc_1004072F0
0x100407313  test    rdx, rdx
0x100407316  lea     rax, [rcx-2]
0x10040731a  lea     r9, aMemoryPagesOut; "\\Memory\\Pages Output/sec"
0x100407321  mov     rdx, r8
0x100407324  cmovnz  rax, rcx
0x100407328  lea     rcx, [rdi+3080h]
0x10040732f  sub     r9, rcx
0x100407332  mov     [rax], r14w
0x100407336  nop     word ptr [rax+rax+00000000h]
0x100407340  lea     rax, [rdx+7FFFF7FEh]
0x100407347  test    rax, rax
0x10040734a  jz      short loc_100407363
0x10040734c  movzx   eax, word ptr [r9+rcx]
0x100407351  test    ax, ax
0x100407354  jz      short loc_100407363
0x100407356  mov     [rcx], ax
0x100407359  add     rcx, 2
0x10040735d  sub     rdx, 1
0x100407361  jnz     short loc_100407340
0x100407363  test    rdx, rdx
0x100407366  lea     rax, [rcx-2]
0x10040736a  lea     r9, aMemoryPagesInp; "\\Memory\\Pages Input/sec"
0x100407371  mov     rdx, r8
0x100407374  cmovnz  rax, rcx
0x100407378  lea     rcx, [rdi+4098h]
0x10040737f  sub     r9, rcx
0x100407382  mov     [rax], r14w
0x100407386  nop     word ptr [rax+rax+00000000h]
0x100407390  lea     rax, [rdx+7FFFF7FEh]
0x100407397  test    rax, rax
0x10040739a  jz      short loc_1004073B3
0x10040739c  movzx   eax, word ptr [r9+rcx]
0x1004073a1  test    ax, ax
0x1004073a4  jz      short loc_1004073B3
0x1004073a6  mov     [rcx], ax
0x1004073a9  add     rcx, 2
0x1004073ad  sub     rdx, 1
0x1004073b1  jnz     short loc_100407390
0x1004073b3  test    rdx, rdx
0x1004073b6  lea     rax, [rcx-2]
0x1004073ba  lea     r9, aMemoryAvailabl; "\\Memory\\Available Bytes"
0x1004073c1  mov     rdx, r8
0x1004073c4  cmovnz  rax, rcx
0x1004073c8  lea     rcx, [rdi+50B0h]
0x1004073cf  sub     r9, rcx
0x1004073d2  mov     [rax], r14w
0x1004073d6  nop     word ptr [rax+rax+00000000h]
0x1004073e0  lea     rax, [rdx+7FFFF7FEh]
0x1004073e7  test    rax, rax
0x1004073ea  jz      short loc_100407403
0x1004073ec  movzx   eax, word ptr [r9+rcx]
0x1004073f1  test    ax, ax
0x1004073f4  jz      short loc_100407403
0x1004073f6  mov     [rcx], ax
0x1004073f9  add     rcx, 2
0x1004073fd  sub     rdx, 1
0x100407401  jnz     short loc_1004073E0
0x100407403  test    rdx, rdx
0x100407406  lea     rax, [rcx-2]
0x10040740a  lea     rdx, [rdi+60C8h]
0x100407411  cmovnz  rax, rcx
0x100407415  lea     r9, aPagingFileTota; "\\Paging File(_Total)\\% Usage"
0x10040741c  sub     r9, rdx
0x10040741f  mov     [rax], r14w
0x100407423  lea     rax, [r8+7FFFF7FEh]
0x10040742a  test    rax, rax
0x10040742d  jz      short loc_100407446
0x10040742f  movzx   ecx, word ptr [r9+rdx]
0x100407434  test    cx, cx
0x100407437  jz      short loc_100407446
0x100407439  mov     [rdx], cx
0x10040743c  add     rdx, 2
0x100407440  sub     r8, 1
0x100407444  jnz     short loc_100407423
0x100407446  test    r8, r8
0x100407449  lea     rcx, [rdx-2]
0x10040744d  mov     eax, r14d
0x100407450  cmovnz  rcx, rdx
0x100407454  mov     [rcx], r14w
0x100407458  jmp     short loc_10040746E
0x10040745a  mov     [rdi+10h], rbx
0x10040745e  jmp     short loc_100407469
0x100407460  mov     [rdi+8], rbx
0x100407464  jmp     short loc_100407469
0x100407466  mov     [rdi], rsi
0x100407469  mov     eax, 80000000h
0x10040746e  mov     rbx, [rsp+48h+arg_8]
0x100407473  mov     rbp, [rsp+48h+arg_10]
0x100407478  add     rsp, 30h
0x10040747c  pop     r14
0x10040747e  pop     rdi
0x10040747f  pop     rsi
0x100407480  retn
```
