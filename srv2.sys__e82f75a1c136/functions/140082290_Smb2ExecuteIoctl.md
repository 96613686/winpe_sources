# Smb2ExecuteIoctl

- ea: `0x140082290`
- end: `0x1400828e2`
- name: `Smb2ExecuteIoctl`
- size: `1618`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: ``

## callers

- `0x14006d800`
- `0x140074860`

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
- `0x14006e6d0`
- `0x1400700a8`
- `0x1400703fc`
- `0x140071f38`
- `0x140082290`
- `0x1400828f0`
- `0x140082ae0`
- `0x140082f60`
- `0x140086110`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082837`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140082837`
- `ntoskrnl!NtSetInformationFile` at `0x14008260b`
- `ntoskrnl!NtSetInformationFile` at `0x14008260b`

## string_xrefs

- `0x140082818`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v5; // ecx
  __int64 v6; // r8
  __int64 v7; // r9
  ULONG v8; // r9d
  struct _NAMED_PIPE_CREATE_PARAMETERS *v9; // r8
  __int64 v10; // rcx
  struct _FILE_OBJECT *v11; // rdx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  _DWORD *v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  _DWORD *v18; // r8
  int v19; // r9d
  struct _IO_STATUS_BLOCK *v20; // rbx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int64 v25; // rdx
  bool v26; // zf
  __int64 v27; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  int FileInformationClass; // [rsp+20h] [rbp-48h]
  void *FileInformationClassa; // [rsp+20h] [rbp-48h]
  ULONG v36; // [rsp+28h] [rbp-40h]
  unsigned int v37; // [rsp+70h] [rbp+8h] BYREF

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
            v8 = *(_DWORD *)(v2 + 204);
            v9 = *(struct _NAMED_PIPE_CREATE_PARAMETERS **)(v2 + 216);
            v10 = *(_QWORD *)(a1 + 64);
            v11 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v2 + 80) + 96LL);
            v36 = *(_DWORD *)(v2 + 200);
            FileInformationClassa = *(void **)(v2 + 224);
            v37 = 0;
            v12 = Smb2RkfFsctl(v10, v11, v9, v8, FileInformationClassa, v36, &v37);
            v7 = (unsigned int)v12;
            a2 = v37;
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
            Smb2ReferenceObjectFromHandle(a1, a2, v6, v7);
            Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
            v25 = *(_QWORD *)(v2 + 88);
            *(_QWORD *)(v2 + 80) = 0;
            return Smb2ExecuteFSIoctl(a1, v25);
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
          v14 = Smb2PreGoAsync2Ex(a1, 0, v6, v7);
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
        v26 = *(_DWORD *)(a1 + 8) == 5;
        *(_QWORD *)(a1 + 48) = Smb2ExecuteIoctlCallback;
        *(_DWORD *)(a1 + 72) = 1;
        if ( v26 )
        {
          LOBYTE(FileInformationClass) = 1;
          LOBYTE(a2) = 1;
          SRV2_PERF_ENTER_EX(a1 + 584, a2, 391, "Srv2PostToThreadPool", FileInformationClass);
        }
        v27 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 144LL);
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v27 + 8LL * CurrentNodeNumber + 8), a1 + 32, 0);
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
        a2 = *(_QWORD *)(v2 + 216);
        *(_QWORD *)a2 = *(_QWORD *)(*(_QWORD *)(v2 + 336) + 88LL);
        *(_QWORD *)(a2 + 8) = *(_QWORD *)(v2 + 344);
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(v2 + 352);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(v2 + 360);
        *(_DWORD *)(v2 + 204) = 32;
      }
      else if ( v5 == 623592 )
      {
        a2 = *(_QWORD *)(v2 + 216);
        *(_QWORD *)a2 = *(_QWORD *)(v2 + 336);
        *(_QWORD *)(a2 + 8) = *(_QWORD *)(*(_QWORD *)(v2 + 344) + 88LL);
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(v2 + 352);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(v2 + 360);
        *(_QWORD *)(a2 + 32) = *(_QWORD *)(v2 + 368);
        *(_DWORD *)(a2 + 40) = *(_DWORD *)(v2 + 376);
        *(_DWORD *)(v2 + 204) = 48;
      }
      goto LABEL_78;
    }
    if ( *(_QWORD *)(v2 + 168) != -1 || (LOBYTE(v6) = 1, v14 = Smb2PreGoAsync2Ex(a1, 0, v6, 623592), v14 >= 0) )
    {
      *(_DWORD *)(a1 + 72) = 1;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteIoctlCallback;
      Smb2GoAsyncForSyncCall(a1, a2, v6, v7);
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
              v17 = Smb2MarkFileForResilientOperation(v16, **(unsigned int **)(v2 + 216), *(_QWORD *)(v2 + 32), 623592);
              *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = v17;
              *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = 0;
              if ( v17 >= 0 )
                Smb2SetConnectionKeepalive(*(_QWORD *)(a1 + 96), 2);
              goto LABEL_58;
            }
            *(_DWORD *)(*(_QWORD *)(a1 + 120) + 48LL) = 0;
            goto LABEL_54;
          case 0x140370u:
            Smb2XmrCtlCreateRdmaMapping(a1, a2, 623428, 623592);
            return 259;
        }
        goto LABEL_78;
      }
      a2 = 1163287;
      goto LABEL_62;
    }
    goto LABEL_25;
  }
  v21 = v5 - 1327196;
  if ( v21 )
  {
    v22 = v21 - 8;
    if ( !v22 )
    {
      v29 = *(_QWORD *)(a1 + 120);
      v30 = *(_QWORD *)(*(_QWORD *)(v2 + 160) + 24LL);
      v31 = *(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL);
      v37 = *(_DWORD *)(v2 + 200);
      v32 = Smb2ShareEnumerateSnapShots(v31, v30, &v37, 623592);
      v33 = v37;
      *(_DWORD *)(v29 + 48) = v32;
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL) = v33;
      goto LABEL_58;
    }
    v23 = v22 - 142;
    if ( v23 )
    {
      v24 = v23 - 201;
      if ( !v24 )
      {
        if ( *(_DWORD *)(a1 + 72) == 1 )
        {
          Smb2RetrieveHashData(a1);
          return 259;
        }
        goto LABEL_80;
      }
      if ( v24 != 16183 )
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
0x140082290  push    rbx
0x140082292  push    rbp
0x140082293  push    rsi
0x140082294  push    rdi
0x140082295  sub     rsp, 48h
0x140082299  mov     rdi, [rcx+230h]
0x1400822a0  xor     ebp, ebp
0x1400822a2  mov     rax, [rcx+78h]
0x1400822a6  mov     rsi, rcx
0x1400822a9  mov     [rax+8], rbp
0x1400822ad  cmp     [rdi+0C4h], bpl
0x1400822b4  jz      short loc_1400822C0
0x1400822b6  call    Smb2ExecuteFilelessFSIoctl
0x1400822bb  jmp     loc_1400828D8
0x1400822c0  mov     ecx, [rdi+0C0h]
0x1400822c6  mov     r8d, 98344h
0x1400822cc  mov     r9d, 983E8h
0x1400822d2  cmp     ecx, r8d
0x1400822d5  ja      loc_140082532
0x1400822db  jz      loc_140082432
0x1400822e1  mov     edx, 90304h
0x1400822e6  cmp     ecx, edx
0x1400822e8  ja      loc_140082407
0x1400822ee  jz      loc_140082684
0x1400822f4  mov     eax, ecx
0x1400822f6  sub     eax, 900FCh
0x1400822fb  jz      loc_1400823DA
0x140082301  sub     eax, 148h
0x140082306  jz      loc_14008246B
0x14008230c  sub     eax, 6Bh ; 'k'
0x14008230f  jz      short loc_140082331
0x140082311  sub     eax, 19h
0x140082314  jz      loc_14008246B
0x14008231a  sub     eax, 1Ch
0x14008231d  jz      loc_14008246B
0x140082323  cmp     eax, 1Ch
0x140082326  jnz     loc_1400827C8
0x14008232c  jmp     loc_140082696
0x140082331  mov     rdx, [rdi+50h]
0x140082335  lea     rax, [rsp+68h+arg_0]
0x14008233a  mov     r9d, [rdi+0CCh]
0x140082341  mov     r8, [rdi+0D8h]
0x140082348  mov     rcx, [rsi+40h]
0x14008234c  mov     rdx, [rdx+60h]
0x140082350  mov     [rsp+68h+var_38], rax
0x140082355  mov     eax, [rdi+0C8h]
0x14008235b  mov     [rsp+68h+var_40], eax
0x14008235f  mov     rax, [rdi+0E0h]
0x140082366  mov     qword ptr [rsp+68h+FileInformationClass], rax
0x14008236b  mov     [rsp+68h+arg_0], ebp
0x14008236f  call    Smb2RkfFsctl
0x140082374  mov     rcx, [rsi+78h]
0x140082378  mov     r9d, eax
0x14008237b  mov     edx, [rsp+68h+arg_0]
0x14008237f  mov     [rcx+30h], eax
0x140082382  mov     rcx, [rsi+78h]
0x140082386  mov     [rcx+38h], rdx
0x14008238a  test    eax, eax
0x14008238c  jns     loc_14008261A
0x140082392  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140082399  lea     rax, WPP_GLOBAL_Control
0x1400823a0  cmp     rcx, rax
0x1400823a3  jz      loc_14008261A
0x1400823a9  test    dword ptr [rcx+2Ch], 100000h
0x1400823b0  jz      loc_14008261A
0x1400823b6  cmp     byte ptr [rcx+29h], 1
0x1400823ba  jb      loc_14008261A
0x1400823c0  mov     rcx, [rcx+18h]
0x1400823c4  lea     r8, WPP_25cf415aefb83845ad58b9e2e2620ddb_Traceguids
0x1400823cb  mov     edx, 65h ; 'e'
0x1400823d0  call    WPP_SF_d
0x1400823d5  jmp     loc_14008261A
0x1400823da  mov     rax, [rdi+0D8h]
0x1400823e1  movups  xmm0, xmmword ptr [rdi+150h]
0x1400823e8  movups  xmmword ptr [rax], xmm0
0x1400823eb  movsd   xmm1, qword ptr [rdi+160h]
0x1400823f3  movsd   qword ptr [rax+10h], xmm1
0x1400823f8  mov     dword ptr [rdi+0CCh], 18h
0x140082402  jmp     loc_1400827C8
0x140082407  mov     eax, ecx
0x140082409  mov     edx, 90364h
0x14008240e  sub     eax, edx
0x140082410  jz      loc_140082684
0x140082416  sub     eax, 3Ch ; '<'
0x140082419  jz      short loc_14008246B
0x14008241b  sub     eax, 3EC4h
0x140082420  jz      short loc_140082432
0x140082422  sub     eax, 3FA4h
0x140082427  jz      short loc_140082432
0x140082429  cmp     eax, 60h ; '`'
0x14008242c  jnz     loc_1400827C8
0x140082432  cmp     [rdi+2], bpl
0x140082436  jnz     loc_1400826DD
0x14008243c  cmp     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFFFh
0x140082444  jnz     loc_1400826BE
0x14008244a  mov     r8b, 1
0x14008244d  xor     edx, edx
0x14008244f  mov     rcx, rsi
0x140082452  call    Smb2PreGoAsync2Ex
0x140082457  test    eax, eax
0x140082459  jns     loc_1400826BE
0x14008245f  mov     rcx, [rsi+78h]
0x140082463  mov     [rcx+30h], eax
0x140082466  jmp     loc_14008259E
0x14008246b  mov     eax, ecx
0x14008246d  mov     rbx, rbp
0x140082470  and     eax, 3
0x140082473  jz      short loc_140082484
0x140082475  sub     eax, 1
0x140082478  jz      short loc_140082484
0x14008247a  sub     eax, 1
0x14008247d  jz      short loc_140082484
0x14008247f  cmp     eax, 1
0x140082482  jnz     short loc_14008248B
0x140082484  mov     rbx, [rdi+0D8h]
0x14008248b  mov     r8d, [rdi+0CCh]
0x140082492  cmp     ecx, 903A0h
0x140082498  jnz     short loc_1400824B3
0x14008249a  cmp     r8d, 10h
0x14008249e  jb      short loc_1400824D9
0x1400824a0  cmp     dword ptr [rbx], 101h
0x1400824a6  jnz     short loc_1400824D9
0x1400824a8  cmp     dword ptr [rbx+0Ch], 791400Ch
0x1400824af  jz      short loc_1400824D2
0x1400824b1  jmp     short loc_1400824D9
0x1400824b3  lea     rax, [rdi+0D4h]
0x1400824ba  mov     rdx, rbx
0x1400824bd  lea     r9, [rdi+0D0h]
0x1400824c4  mov     qword ptr [rsp+68h+FileInformationClass], rax
0x1400824c9  call    CsvIsTunneledIoExpectedToTakeLongTime
0x1400824ce  test    al, al
0x1400824d0  jz      short loc_1400824D9
0x1400824d2  mov     byte ptr [rdi+0C7h], 1
0x1400824d9  mov     edx, [rdi+0C0h]
0x1400824df  cmp     edx, 90244h
0x1400824e5  jz      short loc_1400824F3
0x1400824e7  cmp     edx, 902C8h
0x1400824ed  jnz     loc_140082684
0x1400824f3  test    rbx, rbx
0x1400824f6  jz      loc_140082684
0x1400824fc  cmp     dword ptr [rdi+0CCh], 14h
0x140082503  jb      loc_140082684
0x140082509  mov     eax, [rbx]
0x14008250b  sub     eax, 1000000h
0x140082510  cmp     eax, 1
0x140082513  ja      loc_140082684
0x140082519  cmp     dword ptr [rbx+10h], 90308h
0x140082520  jnz     loc_140082684
0x140082526  mov     byte ptr [rdi+0C6h], 1
0x14008252d  jmp     loc_140082684
0x140082532  mov     eax, 140374h
0x140082537  cmp     ecx, eax
0x140082539  ja      loc_140082793
0x14008253f  jz      loc_140082786
0x140082545  mov     eax, ecx
0x140082547  sub     eax, r9d
0x14008254a  jz      loc_140082432
0x140082550  sub     eax, 83C2Fh
0x140082555  jz      loc_14008267F
0x14008255b  sub     eax, 24061h
0x140082560  jz      loc_14008262C
0x140082566  sub     eax, 74h ; 't'
0x140082569  jz      short loc_1400825DD
0x14008256b  sub     eax, 0E8h
0x140082570  jz      short loc_14008258A
0x140082572  cmp     eax, 19Ch
0x140082577  jnz     loc_1400827C8
0x14008257d  mov     rcx, rsi
0x140082580  call    Smb2XmrCtlCreateRdmaMapping
0x140082585  jmp     loc_140082622
0x14008258a  mov     rcx, [rdi+48h]
0x14008258e  cmp     [rcx+0F2h], bpl
0x140082595  jz      short loc_1400825A8
0x140082597  mov     rax, [rsi+78h]
0x14008259b  mov     [rax+30h], ebp
0x14008259e  mov     rax, [rsi+78h]
0x1400825a2  mov     [rax+38h], rbp
0x1400825a6  jmp     short loc_14008261A
0x1400825a8  mov     rdx, [rdi+0D8h]
0x1400825af  mov     r8, [rdi+20h]
0x1400825b3  mov     edx, [rdx]
0x1400825b5  call    Smb2MarkFileForResilientOperation
0x1400825ba  mov     rcx, [rsi+78h]
0x1400825be  mov     [rcx+30h], eax
0x1400825c1  mov     rcx, [rsi+78h]
0x1400825c5  mov     [rcx+38h], rbp
0x1400825c9  test    eax, eax
0x1400825cb  js      short loc_14008261A
0x1400825cd  mov     rcx, [rsi+60h]
0x1400825d1  mov     edx, 2
0x1400825d6  call    Smb2SetConnectionKeepalive
0x1400825db  jmp     short loc_14008261A
0x1400825dd  mov     rax, [rdi+0A0h]
0x1400825e4  mov     [rsp+68h+FileInformationClass], 24h ; '$'; FileInformationClass
0x1400825ec  mov     r8, [rax+18h]; FileInformation
0x1400825f0  mov     r9d, [r8+8]
0x1400825f4  mov     [r8], rbp
0x1400825f7  add     r9d, 0Ch; Length
0x1400825fb  mov     rbx, [rsi+78h]
0x1400825ff  mov     rcx, [rdi+50h]
0x140082603  lea     rdx, [rbx+30h]; IoStatusBlock
0x140082607  mov     rcx, [rcx+58h]; FileHandle
0x14008260b  call    cs:__imp_NtSetInformationFile
0x140082612  nop     dword ptr [rax+rax+00h]
0x140082617  mov     [rbx+30h], eax
0x14008261a  mov     rcx, rsi
0x14008261d  call    Smb2ContinueIoctl
0x140082622  mov     eax, 103h
0x140082627  jmp     loc_1400828D8
0x14008262c  mov     rax, [rdi+0A0h]
0x140082633  mov     rdx, [rax+18h]
0x140082637  mov     rax, [rdi+48h]
0x14008263b  mov     rcx, [rax+130h]
0x140082642  mov     [rdx+10h], rcx
0x140082646  mov     rax, [rdi+48h]
0x14008264a  mov     rcx, [rax+138h]
0x140082651  mov     [rdx+8], rcx
0x140082655  mov     rax, [rdi+48h]
0x140082659  mov     rcx, [rax+140h]
0x140082660  mov     [rdx], rcx
0x140082663  mov     [rdx+18h], ebp
0x140082666  mov     [rdx+1Ch], bpl
0x14008266a  mov     rax, [rsi+78h]
0x14008266e  mov     [rax+30h], ebp
0x140082671  mov     rax, [rsi+78h]
0x140082675  mov     qword ptr [rax+38h], 20h ; ' '
0x14008267d  jmp     short loc_14008261A
0x14008267f  mov     edx, 11C017h
0x140082684  cmp     edx, 902E4h
0x14008268a  jnz     short loc_140082696
0x14008268c  cmp     dword ptr [rsi+48h], 1
0x140082690  jnz     loc_1400827F4
0x140082696  cmp     qword ptr [rdi+0A8h], 0FFFFFFFFFFFFFFFFh
0x14008269e  jnz     loc_1400827C8
0x1400826a4  mov     r8b, 1
0x1400826a7  xor     edx, edx
0x1400826a9  mov     rcx, rsi
0x1400826ac  call    Smb2PreGoAsync2Ex
0x1400826b1  test    eax, eax
0x1400826b3  js      loc_14008245F
0x1400826b9  jmp     loc_1400827C8
0x1400826be  lea     rax, Smb2ExecuteIoctlCallback
0x1400826c5  mov     dword ptr [rsi+48h], 1
0x1400826cc  mov     rcx, rsi
0x1400826cf  mov     [rsi+30h], rax
0x1400826d3  call    Smb2GoAsyncForSyncCall
0x1400826d8  jmp     loc_140082622
0x1400826dd  cmp     ecx, r8d
0x1400826e0  jnz     short loc_140082727
0x1400826e2  mov     rax, [rdi+150h]
0x1400826e9  mov     rdx, [rdi+0D8h]
0x1400826f0  mov     rcx, [rax+58h]
0x1400826f4  mov     [rdx], rcx
0x1400826f7  mov     rax, [rdi+158h]
0x1400826fe  mov     [rdx+8], rax
0x140082702  mov     rax, [rdi+160h]
0x140082709  mov     [rdx+10h], rax
0x14008270d  mov     rax, [rdi+168h]
0x140082714  mov     [rdx+18h], rax
0x140082718  mov     dword ptr [rdi+0CCh], 20h ; ' '
0x140082722  jmp     loc_1400827C8
0x140082727  cmp     ecx, r9d
0x14008272a  jnz     loc_1400827C8
0x140082730  mov     rax, [rdi+150h]
0x140082737  mov     rdx, [rdi+0D8h]
0x14008273e  mov     [rdx], rax
0x140082741  mov     rax, [rdi+158h]
0x140082748  mov     rcx, [rax+58h]
0x14008274c  mov     [rdx+8], rcx
0x140082750  mov     rax, [rdi+160h]
0x140082757  mov     [rdx+10h], rax
0x14008275b  mov     rax, [rdi+168h]
0x140082762  mov     [rdx+18h], rax
0x140082766  mov     rax, [rdi+170h]
0x14008276d  mov     [rdx+20h], rax
0x140082771  mov     eax, [rdi+178h]
0x140082777  mov     [rdx+28h], eax
0x14008277a  mov     dword ptr [rdi+0CCh], 30h ; '0'
0x140082784  jmp     short loc_1400827C8
0x140082786  mov     rcx, rsi
0x140082789  call    Smb2XmrCtlReleaseRdmaMapping
0x14008278e  jmp     loc_140082622
0x140082793  sub     ecx, 14405Ch
0x140082799  jz      loc_1400828B5
0x14008279f  sub     ecx, 8
0x1400827a2  jz      loc_140082876
0x1400827a8  sub     ecx, 8Eh
0x1400827ae  jz      loc_140082869
0x1400827b4  sub     ecx, 0C9h
0x1400827ba  jz      short loc_1400827EE
0x1400827bc  cmp     ecx, 3F37h
0x1400827c2  jz      loc_140082869
0x1400827c8  mov     rcx, rsi
0x1400827cb  call    Smb2ReferenceObjectFromHandle
0x1400827d0  mov     rcx, [rdi+50h]; P
0x1400827d4  call    Smb2DereferenceHandle
0x1400827d9  mov     rdx, [rdi+58h]
0x1400827dd  mov     rcx, rsi
0x1400827e0  mov     [rdi+50h], rbp
0x1400827e4  call    Smb2ExecuteFSIoctl
  ... truncated ...
```
