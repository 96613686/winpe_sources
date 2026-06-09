# Smb2ExecuteIoctl

- ea: `0x1400822e0`
- end: `0x140082932`
- name: `Smb2ExecuteIoctl`
- size: `1618`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x14006d850`
- `0x1400748b0`

## callees

- `0x140005070`
- `0x140012c30`
- `0x140013660`
- `0x140013810`
- `0x14001beac`
- `0x14001f050`
- `0x14001f6ec`
- `0x1400224b8`
- `0x14002d904`
- `0x14006498c`
- `0x140068f48`
- `0x14006e720`
- `0x1400700f8`
- `0x14007044c`
- `0x140071f88`
- `0x1400822e0`
- `0x140082940`
- `0x140082b30`
- `0x140082fb0`
- `0x140086160`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082887`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082887`
- `ntoskrnl!NtSetInformationFile` at `0x14008265b`
- `ntoskrnl!NtSetInformationFile` at `0x14008265b`

## string_xrefs

- `0x140082868`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v5; // ecx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  _DWORD *v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  _DWORD *v18; // r8
  int v19; // r9d
  struct _IO_STATUS_BLOCK *v20; // rbx
  _QWORD *v21; // rdx
  __int64 v22; // rdx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  struct _FILE_OBJECT *v27; // rdx
  bool v28; // zf
  __int64 v29; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  int FileInformationClass; // [rsp+20h] [rbp-48h]
  FILE_INFORMATION_CLASS FileInformationClassa[2]; // [rsp+20h] [rbp-48h]
  int v38; // [rsp+28h] [rbp-40h]
  unsigned int v39; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
  if ( *(_BYTE *)(v2 + 196) )
    return Smb2ExecuteFilelessFSIoctl();
  v5 = *(_DWORD *)(v2 + 192);
  v6 = 623428;
  v7 = 623592;
  if ( v5 <= 0x98344 )
  {
    if ( v5 != 623428 )
    {
      a2 = 590596;
      if ( v5 <= 0x90304 )
      {
        if ( v5 == 590596 )
          goto LABEL_62;
        if ( v5 == 590076 )
        {
          v13 = *(_QWORD *)(v2 + 216);
          *(_OWORD *)v13 = *(_OWORD *)(v2 + 336);
          *(_QWORD *)(v13 + 16) = *(_QWORD *)(v2 + 352);
          *(_DWORD *)(v2 + 204) = 24;
          goto LABEL_78;
        }
        if ( v5 != 590404 )
        {
          if ( v5 == 590511 )
          {
            v8 = *(unsigned int *)(v2 + 204);
            v9 = *(_QWORD *)(v2 + 216);
            v10 = *(_QWORD *)(a1 + 64);
            v11 = *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL);
            v38 = *(_DWORD *)(v2 + 200);
            *(_QWORD *)FileInformationClassa = *(_QWORD *)(v2 + 224);
            v39 = 0;
            v12 = Smb2RkfFsctl(v10, v11, v9, v8, *(_QWORD *)FileInformationClassa, v38, &v39);
            v7 = (unsigned int)v12;
            a2 = v39;
            *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v12;
            *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = a2;
            if ( v12 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                101,
                WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids,
                (unsigned int)v12);
            }
            goto LABEL_58;
          }
          if ( v5 != 590536 && v5 != 590564 )
          {
            if ( v5 == 590592 )
              goto LABEL_64;
LABEL_78:
            Smb2ReferenceObjectFromHandle(a1);
            Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
            v27 = *(struct _FILE_OBJECT **)(v2 + 88);
            *(_QWORD *)(v2 + 80) = 0;
            return Smb2ExecuteFSIoctl(a1, v27);
          }
        }
LABEL_29:
        v15 = *(_DWORD **)(v2 + 216);
        v6 = *(unsigned int *)(v2 + 204);
        if ( v5 == 590752 )
        {
          if ( (unsigned int)v6 < 0x10 || *v15 != 257 || v15[3] != 126959628 )
            goto LABEL_36;
        }
        else if ( !(unsigned __int8)CsvIsTunneledIoExpectedToTakeLongTime(v5, (_DWORD)v15, v6, (int)v2 + 208, v2 + 212) )
        {
          goto LABEL_36;
        }
        *(_BYTE *)(v2 + 199) = 1;
LABEL_36:
        a2 = *(unsigned int *)(v2 + 192);
        if ( ((_DWORD)a2 == 590404 || (_DWORD)a2 == 590536)
          && v15
          && *(_DWORD *)(v2 + 204) >= 0x14u
          && (unsigned int)(*v15 - 0x1000000) <= 1
          && v15[4] == 590600 )
        {
          *(_BYTE *)(v2 + 198) = 1;
        }
LABEL_62:
        if ( (_DWORD)a2 != 590564 || *(_DWORD *)(a1 + 72) == 1 )
        {
LABEL_64:
          if ( *(_QWORD *)(v2 + 168) != -1 )
            goto LABEL_78;
          LOBYTE(v6) = 1;
          v14 = Smb2PreGoAsync2Ex(a1, 0, v6);
          if ( v14 >= 0 )
            goto LABEL_78;
LABEL_28:
          *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v14;
LABEL_54:
          *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
LABEL_58:
          Smb2ContinueIoctl(a1, a2, v6, v7);
          return 259;
        }
LABEL_80:
        v28 = *(_DWORD *)(a1 + 8) == 5;
        *(_QWORD *)(a1 + 48) = Smb2ExecuteIoctlCallback;
        *(_DWORD *)(a1 + 72) = 1;
        if ( v28 )
        {
          LOBYTE(FileInformationClass) = 1;
          LOBYTE(a2) = 1;
          SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", FileInformationClass);
        }
        v29 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 144LL);
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        RfspThreadPoolNodeQueueWorkItem(
          *(union _SLIST_HEADER **)(v29 + 8LL * CurrentNodeNumber + 8),
          (struct _SLIST_ENTRY *)(a1 + 32),
          0);
        return 259;
      }
      a2 = 590692;
      if ( v5 == 590692 )
        goto LABEL_62;
      if ( v5 == 590752 )
        goto LABEL_29;
      if ( v5 != 606820 && v5 != 623112 && v5 != 623208 )
        goto LABEL_78;
    }
LABEL_25:
    if ( *(_BYTE *)(v2 + 2) )
    {
      if ( v5 == 623428 )
      {
        v21 = *(_QWORD **)(v2 + 216);
        *v21 = *(_QWORD *)(*(_QWORD *)(v2 + 336) + 88LL);
        v21[1] = *(_QWORD *)(v2 + 344);
        v21[2] = *(_QWORD *)(v2 + 352);
        v21[3] = *(_QWORD *)(v2 + 360);
        *(_DWORD *)(v2 + 204) = 32;
      }
      else if ( v5 == 623592 )
      {
        v22 = *(_QWORD *)(v2 + 216);
        *(_QWORD *)v22 = *(_QWORD *)(v2 + 336);
        *(_QWORD *)(v22 + 8) = *(_QWORD *)(*(_QWORD *)(v2 + 344) + 88LL);
        *(_QWORD *)(v22 + 16) = *(_QWORD *)(v2 + 352);
        *(_QWORD *)(v22 + 24) = *(_QWORD *)(v2 + 360);
        *(_QWORD *)(v22 + 32) = *(_QWORD *)(v2 + 368);
        *(_DWORD *)(v22 + 40) = *(_DWORD *)(v2 + 376);
        *(_DWORD *)(v2 + 204) = 48;
      }
      goto LABEL_78;
    }
    if ( *(_QWORD *)(v2 + 168) != -1 || (LOBYTE(v6) = 1, v14 = Smb2PreGoAsync2Ex(a1, 0, v6), v14 >= 0) )
    {
      *(_DWORD *)(a1 + 72) = 1;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteIoctlCallback;
      Smb2GoAsyncForSyncCall(a1, a2);
      return 259;
    }
    goto LABEL_28;
  }
  if ( v5 <= 0x140374 )
  {
    if ( v5 == 1311604 )
    {
      Smb2XmrCtlReleaseRdmaMapping(a1, a2, 623428, 623592);
      return 259;
    }
    if ( v5 != 623592 )
    {
      if ( v5 != 1163287 )
      {
        switch ( v5 )
        {
          case 0x140078u:
            a2 = *(_QWORD *)(*(_QWORD *)(v2 + 160) + 24LL);
            *(_QWORD *)(a2 + 16) = *(_QWORD *)(*(_QWORD *)(v2 + 72) + 304LL);
            *(_QWORD *)(a2 + 8) = *(_QWORD *)(*(_QWORD *)(v2 + 72) + 312LL);
            *(_QWORD *)a2 = *(_QWORD *)(*(_QWORD *)(v2 + 72) + 320LL);
            *(_DWORD *)(a2 + 24) = 0;
            *(_BYTE *)(a2 + 28) = 0;
            *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
            *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 32;
            goto LABEL_58;
          case 0x1400ECu:
            v18 = *(_DWORD **)(*(_QWORD *)(v2 + 160) + 24LL);
            v19 = v18[2];
            *(_QWORD *)v18 = 0;
            v20 = *(struct _IO_STATUS_BLOCK **)(a1 + 120);
            v20[3].Status = NtSetInformationFile(
                              *(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL),
                              v20 + 3,
                              v18,
                              v19 + 12,
                              FileTrackingInformation);
            goto LABEL_58;
          case 0x1401D4u:
            v16 = *(_QWORD *)(v2 + 72);
            if ( !*(_BYTE *)(v16 + 242) )
            {
              v17 = Smb2MarkFileForResilientOperation(v16, **(unsigned int **)(v2 + 216));
              *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v17;
              *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
              if ( v17 >= 0 )
                Smb2SetConnectionKeepalive(*(_QWORD *)(a1 + 96), 2);
              goto LABEL_58;
            }
            *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
            goto LABEL_54;
          case 0x140370u:
            Smb2XmrCtlCreateRdmaMapping((_QWORD *)a1);
            return 259;
        }
        goto LABEL_78;
      }
      a2 = 1163287;
      goto LABEL_62;
    }
    goto LABEL_25;
  }
  v23 = v5 - 1327196;
  if ( v23 )
  {
    v24 = v23 - 8;
    if ( !v24 )
    {
      v31 = *(_QWORD *)(a1 + 120);
      v32 = *(_QWORD *)(*(_QWORD *)(v2 + 160) + 24LL);
      v33 = *(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL);
      v39 = *(_DWORD *)(v2 + 200);
      v34 = Smb2ShareEnumerateSnapShots(v33, v32, &v39, 623592);
      v35 = v39;
      *(_DWORD *)(v31 + 48) = v34;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = v35;
      goto LABEL_58;
    }
    v25 = v24 - 142;
    if ( v25 )
    {
      v26 = v25 - 201;
      if ( !v26 )
      {
        if ( *(_DWORD *)(a1 + 72) == 1 )
        {
          Smb2RetrieveHashData(a1);
          return 259;
        }
        goto LABEL_80;
      }
      if ( v26 != 16183 )
        goto LABEL_78;
    }
    Smb2PerformCopyChunk(a1, a2, 623428, 623592);
    return 259;
  }
  *(_QWORD *)(*(_QWORD *)(v2 + 32) + 8LL) = MEMORY[0xFFFFF78000000014];
  *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x1400822e0  push    rbx
0x1400822e2  push    rbp
0x1400822e3  push    rsi
0x1400822e4  push    rdi
0x1400822e5  sub     rsp, 48h
0x1400822e9  mov     rdi, [rcx+230h]
0x1400822f0  xor     ebp, ebp
0x1400822f2  mov     rax, [rcx+78h]
0x1400822f6  mov     rsi, rcx
0x1400822f9  mov     [rax+8], rbp
0x1400822fd  cmp     [rdi+0C4h], bpl
0x140082304  jz      short loc_140082310
0x140082306  call    Smb2ExecuteFilelessFSIoctl
0x14008230b  jmp     loc_140082928
0x140082310  mov     ecx, [rdi+0C0h]
0x140082316  mov     r8d, 98344h
0x14008231c  mov     r9d, 983E8h
0x140082322  cmp     ecx, r8d
0x140082325  ja      loc_140082582
0x14008232b  jz      loc_140082482
0x140082331  mov     edx, 90304h
0x140082336  cmp     ecx, edx
0x140082338  ja      loc_140082457
0x14008233e  jz      loc_1400826D4
0x140082344  mov     eax, ecx
0x140082346  sub     eax, 900FCh
0x14008234b  jz      loc_14008242A
0x140082351  sub     eax, 148h
0x140082356  jz      loc_1400824BB
0x14008235c  sub     eax, 6Bh ; 'k'
0x14008235f  jz      short loc_140082381
0x140082361  sub     eax, 19h
0x140082364  jz      loc_1400824BB
0x14008236a  sub     eax, 1Ch
0x14008236d  jz      loc_1400824BB
0x140082373  cmp     eax, 1Ch
0x140082376  jnz     loc_140082818
0x14008237c  jmp     loc_1400826E6
0x140082381  mov     rdx, [rdi+50h]
0x140082385  lea     rax, [rsp+68h+arg_0]
0x14008238a  mov     r9d, [rdi+0CCh]
0x140082391  mov     r8, [rdi+0D8h]
0x140082398  mov     rcx, [rsi+40h]
0x14008239c  mov     rdx, [rdx+60h]
0x1400823a0  mov     [rsp+68h+var_38], rax
0x1400823a5  mov     eax, [rdi+0C8h]
0x1400823ab  mov     [rsp+68h+var_40], eax
0x1400823af  mov     rax, [rdi+0E0h]
0x1400823b6  mov     qword ptr [rsp+68h+FileInformationClass], rax
0x1400823bb  mov     [rsp+68h+arg_0], ebp
0x1400823bf  call    Smb2RkfFsctl
0x1400823c4  mov     rcx, [rsi+78h]
0x1400823c8  mov     r9d, eax
0x1400823cb  mov     edx, [rsp+68h+arg_0]
0x1400823cf  mov     [rcx+30h], eax
0x1400823d2  mov     rcx, [rsi+78h]
0x1400823d6  mov     [rcx+38h], rdx
0x1400823da  test    eax, eax
0x1400823dc  jns     loc_14008266A
0x1400823e2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400823e9  lea     rax, WPP_GLOBAL_Control
0x1400823f0  cmp     rcx, rax
0x1400823f3  jz      loc_14008266A
0x1400823f9  test    dword ptr [rcx+2Ch], 100000h
0x140082400  jz      loc_14008266A
0x140082406  cmp     byte ptr [rcx+29h], 1
0x14008240a  jb      loc_14008266A
0x140082410  mov     rcx, [rcx+18h]
0x140082414  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x14008241b  mov     edx, 65h ; 'e'
0x140082420  call    WPP_SF_d
0x140082425  jmp     loc_14008266A
0x14008242a  mov     rax, [rdi+0D8h]
0x140082431  movups  xmm0, xmmword ptr [rdi+150h]
0x140082438  movups  xmmword ptr [rax], xmm0
0x14008243b  movsd   xmm1, qword ptr [rdi+160h]
0x140082443  movsd   qword ptr [rax+10h], xmm1
0x140082448  mov     dword ptr [rdi+0CCh], 18h
0x140082452  jmp     loc_140082818
0x140082457  mov     eax, ecx
0x140082459  mov     edx, 90364h
0x14008245e  sub     eax, edx
0x140082460  jz      loc_1400826D4
0x140082466  sub     eax, 3Ch ; '<'
0x140082469  jz      short loc_1400824BB
0x14008246b  sub     eax, 3EC4h
0x140082470  jz      short loc_140082482
0x140082472  sub     eax, 3FA4h
0x140082477  jz      short loc_140082482
0x140082479  cmp     eax, 60h ; '`'
0x14008247c  jnz     loc_140082818
0x140082482  cmp     [rdi+2], bpl
0x140082486  jnz     loc_14008272D
0x14008248c  cmp     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140082494  jnz     loc_14008270E
0x14008249a  mov     r8b, 1
0x14008249d  xor     edx, edx
0x14008249f  mov     rcx, rsi
0x1400824a2  call    Smb2PreGoAsync2Ex
0x1400824a7  test    eax, eax
0x1400824a9  jns     loc_14008270E
0x1400824af  mov     rcx, [rsi+78h]
0x1400824b3  mov     [rcx+30h], eax
0x1400824b6  jmp     loc_1400825EE
0x1400824bb  mov     eax, ecx
0x1400824bd  mov     rbx, rbp
0x1400824c0  and     eax, 3
0x1400824c3  jz      short loc_1400824D4
0x1400824c5  sub     eax, 1
0x1400824c8  jz      short loc_1400824D4
0x1400824ca  sub     eax, 1
0x1400824cd  jz      short loc_1400824D4
0x1400824cf  cmp     eax, 1
0x1400824d2  jnz     short loc_1400824DB
0x1400824d4  mov     rbx, [rdi+0D8h]
0x1400824db  mov     r8d, [rdi+0CCh]
0x1400824e2  cmp     ecx, 903A0h
0x1400824e8  jnz     short loc_140082503
0x1400824ea  cmp     r8d, 10h
0x1400824ee  jb      short loc_140082529
0x1400824f0  cmp     dword ptr [rbx], 101h
0x1400824f6  jnz     short loc_140082529
0x1400824f8  cmp     dword ptr [rbx+0Ch], 791400Ch
0x1400824ff  jz      short loc_140082522
0x140082501  jmp     short loc_140082529
0x140082503  lea     rax, [rdi+0D4h]
0x14008250a  mov     rdx, rbx
0x14008250d  lea     r9, [rdi+0D0h]
0x140082514  mov     qword ptr [rsp+68h+FileInformationClass], rax
0x140082519  call    CsvIsTunneledIoExpectedToTakeLongTime
0x14008251e  test    al, al
0x140082520  jz      short loc_140082529
0x140082522  mov     byte ptr [rdi+0C7h], 1
0x140082529  mov     edx, [rdi+0C0h]
0x14008252f  cmp     edx, 90244h
0x140082535  jz      short loc_140082543
0x140082537  cmp     edx, 902C8h
0x14008253d  jnz     loc_1400826D4
0x140082543  test    rbx, rbx
0x140082546  jz      loc_1400826D4
0x14008254c  cmp     dword ptr [rdi+0CCh], 14h
0x140082553  jb      loc_1400826D4
0x140082559  mov     eax, [rbx]
0x14008255b  sub     eax, 1000000h
0x140082560  cmp     eax, 1
0x140082563  ja      loc_1400826D4
0x140082569  cmp     dword ptr [rbx+10h], 90308h
0x140082570  jnz     loc_1400826D4
0x140082576  mov     byte ptr [rdi+0C6h], 1
0x14008257d  jmp     loc_1400826D4
0x140082582  mov     eax, 140374h
0x140082587  cmp     ecx, eax
0x140082589  ja      loc_1400827E3
0x14008258f  jz      loc_1400827D6
0x140082595  mov     eax, ecx
0x140082597  sub     eax, r9d
0x14008259a  jz      loc_140082482
0x1400825a0  sub     eax, 83C2Fh
0x1400825a5  jz      loc_1400826CF
0x1400825ab  sub     eax, 24061h
0x1400825b0  jz      loc_14008267C
0x1400825b6  sub     eax, 74h ; 't'
0x1400825b9  jz      short loc_14008262D
0x1400825bb  sub     eax, 0E8h
0x1400825c0  jz      short loc_1400825DA
0x1400825c2  cmp     eax, 19Ch
0x1400825c7  jnz     loc_140082818
0x1400825cd  mov     rcx, rsi
0x1400825d0  call    Smb2XmrCtlCreateRdmaMapping
0x1400825d5  jmp     loc_140082672
0x1400825da  mov     rcx, [rdi+48h]
0x1400825de  cmp     [rcx+0F2h], bpl
0x1400825e5  jz      short loc_1400825F8
0x1400825e7  mov     rax, [rsi+78h]
0x1400825eb  mov     [rax+30h], ebp
0x1400825ee  mov     rax, [rsi+78h]
0x1400825f2  mov     [rax+38h], rbp
0x1400825f6  jmp     short loc_14008266A
0x1400825f8  mov     rdx, [rdi+0D8h]
0x1400825ff  mov     r8, [rdi+20h]
0x140082603  mov     edx, [rdx]
0x140082605  call    Smb2MarkFileForResilientOperation
0x14008260a  mov     rcx, [rsi+78h]
0x14008260e  mov     [rcx+30h], eax
0x140082611  mov     rcx, [rsi+78h]
0x140082615  mov     [rcx+38h], rbp
0x140082619  test    eax, eax
0x14008261b  js      short loc_14008266A
0x14008261d  mov     rcx, [rsi+60h]
0x140082621  mov     edx, 2
0x140082626  call    Smb2SetConnectionKeepalive
0x14008262b  jmp     short loc_14008266A
0x14008262d  mov     rax, [rdi+0A0h]
0x140082634  mov     [rsp+68h+FileInformationClass], 24h ; '$'; FileInformationClass
0x14008263c  mov     r8, [rax+18h]; FileInformation
0x140082640  mov     r9d, [r8+8]
0x140082644  mov     [r8], rbp
0x140082647  add     r9d, 0Ch; Length
0x14008264b  mov     rbx, [rsi+78h]
0x14008264f  mov     rcx, [rdi+50h]
0x140082653  lea     rdx, [rbx+30h]; IoStatusBlock
0x140082657  mov     rcx, [rcx+58h]; FileHandle
0x14008265b  call    cs:__imp_NtSetInformationFile
0x140082662  nop     dword ptr [rax+rax+00h]
0x140082667  mov     [rbx+30h], eax
0x14008266a  mov     rcx, rsi
0x14008266d  call    Smb2ContinueIoctl
0x140082672  mov     eax, 103h
0x140082677  jmp     loc_140082928
0x14008267c  mov     rax, [rdi+0A0h]
0x140082683  mov     rdx, [rax+18h]
0x140082687  mov     rax, [rdi+48h]
0x14008268b  mov     rcx, [rax+130h]
0x140082692  mov     [rdx+10h], rcx
0x140082696  mov     rax, [rdi+48h]
0x14008269a  mov     rcx, [rax+138h]
0x1400826a1  mov     [rdx+8], rcx
0x1400826a5  mov     rax, [rdi+48h]
0x1400826a9  mov     rcx, [rax+140h]
0x1400826b0  mov     [rdx], rcx
0x1400826b3  mov     [rdx+18h], ebp
0x1400826b6  mov     [rdx+1Ch], bpl
0x1400826ba  mov     rax, [rsi+78h]
0x1400826be  mov     [rax+30h], ebp
0x1400826c1  mov     rax, [rsi+78h]
0x1400826c5  mov     qword ptr [rax+38h], 20h ; ' '
0x1400826cd  jmp     short loc_14008266A
0x1400826cf  mov     edx, 11C017h
0x1400826d4  cmp     edx, 902E4h
0x1400826da  jnz     short loc_1400826E6
0x1400826dc  cmp     dword ptr [rsi+48h], 1
0x1400826e0  jnz     loc_140082844
0x1400826e6  cmp     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFFFh
0x1400826ee  jnz     loc_140082818
0x1400826f4  mov     r8b, 1
0x1400826f7  xor     edx, edx
0x1400826f9  mov     rcx, rsi
0x1400826fc  call    Smb2PreGoAsync2Ex
0x140082701  test    eax, eax
0x140082703  js      loc_1400824AF
0x140082709  jmp     loc_140082818
0x14008270e  lea     rax, Smb2ExecuteIoctlCallback
0x140082715  mov     dword ptr [rsi+48h], 1
0x14008271c  mov     rcx, rsi
0x14008271f  mov     [rsi+30h], rax
0x140082723  call    Smb2GoAsyncForSyncCall
0x140082728  jmp     loc_140082672
0x14008272d  cmp     ecx, r8d
0x140082730  jnz     short loc_140082777
0x140082732  mov     rax, [rdi+150h]
0x140082739  mov     rdx, [rdi+0D8h]
0x140082740  mov     rcx, [rax+58h]
0x140082744  mov     [rdx], rcx
0x140082747  mov     rax, [rdi+158h]
0x14008274e  mov     [rdx+8], rax
0x140082752  mov     rax, [rdi+160h]
0x140082759  mov     [rdx+10h], rax
0x14008275d  mov     rax, [rdi+168h]
0x140082764  mov     [rdx+18h], rax
0x140082768  mov     dword ptr [rdi+0CCh], 20h ; ' '
0x140082772  jmp     loc_140082818
0x140082777  cmp     ecx, r9d
0x14008277a  jnz     loc_140082818
0x140082780  mov     rax, [rdi+150h]
0x140082787  mov     rdx, [rdi+0D8h]
0x14008278e  mov     [rdx], rax
0x140082791  mov     rax, [rdi+158h]
0x140082798  mov     rcx, [rax+58h]
0x14008279c  mov     [rdx+8], rcx
0x1400827a0  mov     rax, [rdi+160h]
0x1400827a7  mov     [rdx+10h], rax
0x1400827ab  mov     rax, [rdi+168h]
0x1400827b2  mov     [rdx+18h], rax
0x1400827b6  mov     rax, [rdi+170h]
0x1400827bd  mov     [rdx+20h], rax
0x1400827c1  mov     eax, [rdi+178h]
0x1400827c7  mov     [rdx+28h], eax
0x1400827ca  mov     dword ptr [rdi+0CCh], 30h ; '0'
0x1400827d4  jmp     short loc_140082818
0x1400827d6  mov     rcx, rsi
0x1400827d9  call    Smb2XmrCtlReleaseRdmaMapping
0x1400827de  jmp     loc_140082672
0x1400827e3  sub     ecx, 14405Ch
0x1400827e9  jz      loc_140082905
0x1400827ef  sub     ecx, 8
0x1400827f2  jz      loc_1400828C6
0x1400827f8  sub     ecx, 8Eh
0x1400827fe  jz      loc_1400828B9
0x140082804  sub     ecx, 0C9h
0x14008280a  jz      short loc_14008283E
0x14008280c  cmp     ecx, 3F37h
0x140082812  jz      loc_1400828B9
0x140082818  mov     rcx, rsi
0x14008281b  call    Smb2ReferenceObjectFromHandle
0x140082820  mov     rcx, [rdi+50h]; P
0x140082824  call    Smb2DereferenceHandle
0x140082829  mov     rdx, [rdi+58h]
0x14008282d  mov     rcx, rsi
0x140082830  mov     [rdi+50h], rbp
0x140082834  call    Smb2ExecuteFSIoctl
  ... truncated ...
```
