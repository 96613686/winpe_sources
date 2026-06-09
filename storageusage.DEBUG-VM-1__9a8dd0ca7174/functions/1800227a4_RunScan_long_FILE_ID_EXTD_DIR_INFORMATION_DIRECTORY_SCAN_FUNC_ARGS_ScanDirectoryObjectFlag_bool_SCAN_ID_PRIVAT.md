# RunScan(long (*)(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool),SCAN_ID,PRIVATE_SCAN_SETTINGS &,ulong,void *)

- ea: `0x1800227a4`
- end: `0x180022aad`
- name: `?RunScan@@YAJP6AJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@ZW4SCAN_ID@@AEAUPRIVATE_SCAN_SETTINGS@@KPEAX@Z`
- size: `777`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180019db0`
- `0x18001b550`
- `0x18001b5b0`
- `0x18001b610`
- `0x18001b650`
- `0x18001b790`
- `0x18001b7d0`
- `0x18001b840`
- `0x18001b870`

## callees

- `0x180005c94`
- `0x18000eb18`
- `0x180017af4`
- `0x18001f050`
- `0x18001f9c8`
- `0x18001fa40`
- `0x180020264`
- `0x18002085c`
- `0x1800208fc`
- `0x1800210e4`
- `0x1800222a8`
- `0x1800227a4`
- `0x180022ab4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RunScan(
        __int64 (__fastcall *a1)(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, __int64, __int64),
        int a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  int v8; // edi
  __int64 *v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // r14
  __int64 v12; // r15
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  __int64 v15; // rbx
  char v16; // di
  _OWORD *v17; // rax
  _OWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v21; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE *v22; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+68h] [rbp-A0h]
  __int64 v27; // [rsp+70h] [rbp-98h]
  __int128 v28; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v29; // [rsp+88h] [rbp-80h]
  __int64 *v30; // [rsp+90h] [rbp-78h]
  char *v31; // [rsp+98h] [rbp-70h]
  _QWORD v32[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v33; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-38h]
  __int128 v35; // [rsp+E0h] [rbp-28h]
  int v36; // [rsp+F0h] [rbp-18h]
  _BYTE v37[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v38[16]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v39; // [rsp+128h] [rbp+20h]
  _BYTE v40[752]; // [rsp+408h] [rbp+300h] BYREF
  int v41; // [rsp+730h] [rbp+628h] BYREF

  v41 = a2;
  v21 = 0;
  std::vector<unsigned short const *>::vector<unsigned short const *>(&v25);
  memset_0(v38, 0, 0x2F0u);
  v8 = InitializeDirScanArgs((__int64)v38, v41, a3, a4);
  if ( v8 >= 0 )
  {
    v22 = v38;
    *(_QWORD *)&v28 = &v41;
    *((_QWORD *)&v28 + 1) = &v21;
    v29 = &v22;
    v30 = &v25;
    v31 = (char *)&v21 + 4;
    v9 = DirScanConfigTable;
    do
    {
      v33 = *v9;
      v34 = *(_OWORD *)(v9 + 1);
      v35 = *(_OWORD *)(v9 + 3);
      v36 = *((_DWORD *)v9 + 10);
      std::vector<unsigned short const *>::vector<unsigned short const *>(v37, v9 + 6);
      v37[24] = *((_BYTE *)v9 + 72);
      lambda_f886460d9a995a229958d23684bed484_::operator()((__int64)&v28, (__int64)&v33);
      v9 += 10;
    }
    while ( v9 != g_DefaultLogger );
    if ( HIDWORD(v21) == (_DWORD)v21 )
    {
      v8 = 1920;
    }
    else
    {
      v10 = v25;
      v11 = v26;
      v12 = a5;
      while ( v10 != v11 )
      {
        std::vector<unsigned short const *>::vector<unsigned short const *>(&v23);
        v39 = *(_QWORD *)(v10 + 520);
        v32[0] = v10;
        v32[1] = &v23;
        v13 = *(_QWORD **)(v10 + 528);
        v14 = *(_QWORD **)(v10 + 536);
        while ( v13 != v14 )
          lambda_f60fe7e1e893bb13368af42adc67c2a5_::operator()(v32, *v13++);
        v15 = (__int64)v22;
        v16 = *(_BYTE *)(v10 + 552);
        v28 = 0;
        v29 = 0;
        std::vector<DirQueItem>::_Construct_n<DirQueItem * const &,DirQueItem * const &>(
          &v28,
          0xFC0FC0FC0FC0FC1LL * ((v24 - v23) >> 3),
          &v23,
          &v24);
        v8 = ScanDirectory((const unsigned __int16 *)v10, &v28, v16, a1, v15, v12);
        if ( v8 == -2147023673 )
        {
          std::vector<DirQueItem>::_Tidy(&v23);
          break;
        }
        std::vector<DirQueItem>::_Tidy(&v23);
        v10 += 560;
      }
    }
  }
  v17 = v40;
  v18 = v38;
  v19 = 5;
  do
  {
    *v17 = *v18;
    v17[1] = v18[1];
    v17[2] = v18[2];
    v17[3] = v18[3];
    v17[4] = v18[4];
    v17[5] = v18[5];
    v17[6] = v18[6];
    v17[7] = v18[7];
    v17 += 8;
    v18 += 8;
    --v19;
  }
  while ( v19 );
  *v17 = *v18;
  v17[1] = v18[1];
  v17[2] = v18[2];
  v17[3] = v18[3];
  v17[4] = v18[4];
  v17[5] = v18[5];
  v17[6] = v18[6];
  FreeDirScanArgs(v40, 0, 128);
  if ( v25 )
  {
    std::_Destroy_range<std::allocator<DIR_SCAN_ENTRY>>(v25, v26);
    std::_Deallocate<16>(v25, 16 * ((v27 - v25) >> 4));
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800227a4  mov     rax, rsp
0x1800227a7  mov     [rax+8], rbx
0x1800227ab  mov     [rax+18h], rsi
0x1800227af  mov     [rax+10h], edx
0x1800227b2  push    rbp
0x1800227b3  push    rdi
0x1800227b4  push    r12
0x1800227b6  push    r14
0x1800227b8  push    r15
0x1800227ba  lea     rbp, [rax-618h]
0x1800227c1  sub     rsp, 6F0h
0x1800227c8  mov     ebx, r9d
0x1800227cb  mov     rdi, r8
0x1800227ce  mov     r12, rcx
0x1800227d1  mov     dword ptr [rsp+710h+var_6E0], 0
0x1800227d9  mov     dword ptr [rsp+710h+var_6E0+4], 0
0x1800227e1  lea     rcx, [rsp+710h+var_6B8]
0x1800227e6  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800227eb  nop
0x1800227ec  xor     edx, edx; Val
0x1800227ee  mov     r8d, 2F0h; Size
0x1800227f4  lea     rcx, [rbp+610h+var_600]; void *
0x1800227f8  call    memset_0
0x1800227fd  mov     r9d, ebx
0x180022800  mov     r8, rdi
0x180022803  mov     edx, [rbp+610h+arg_8]
0x180022809  lea     rcx, [rbp+610h+var_600]
0x18002280d  call    ?InitializeDirScanArgs@@YAJPEAUDIRECTORY_SCAN_FUNC_ARGS@@W4SCAN_ID@@AEAUPRIVATE_SCAN_SETTINGS@@K@Z; InitializeDirScanArgs(DIRECTORY_SCAN_FUNC_ARGS *,SCAN_ID,PRIVATE_SCAN_SETTINGS &,ulong)
0x180022812  mov     edi, eax
0x180022814  test    eax, eax
0x180022816  js      loc_1800229AF
0x18002281c  lea     rax, [rbp+610h+var_600]
0x180022820  mov     [rsp+710h+var_6D8], rax
0x180022825  lea     rax, [rbp+610h+arg_8]
0x18002282c  mov     qword ptr [rsp+710h+var_6A8+8], rax
0x180022831  lea     rax, [rsp+710h+var_6E0]
0x180022836  mov     [rsp+710h+var_698], rax
0x18002283b  lea     rax, [rsp+710h+var_6D8]
0x180022840  mov     [rbp+610h+var_690], rax
0x180022844  lea     rax, [rsp+710h+var_6B8]
0x180022849  mov     [rbp+610h+var_688], rax
0x18002284d  lea     rax, [rsp+710h+var_6E0+4]
0x180022852  mov     [rbp+610h+var_680], rax
0x180022856  lea     rbx, ?DirScanConfigTable@@3V?$array@UDIR_SCAN_CONFIG@@$0BE@@std@@A; std::array<DIR_SCAN_CONFIG,20> DirScanConfigTable
0x18002285d  mov     rax, [rbx]
0x180022860  mov     [rbp+610h+var_650], rax
0x180022864  movups  xmm0, xmmword ptr [rbx+8]
0x180022868  movups  [rbp+610h+var_648], xmm0
0x18002286c  movups  xmm1, xmmword ptr [rbx+18h]
0x180022870  movups  [rbp+610h+var_638], xmm1
0x180022874  mov     eax, [rbx+28h]
0x180022877  mov     [rbp+610h+var_628], eax
0x18002287a  lea     rdx, [rbx+30h]
0x18002287e  lea     rcx, [rbp+610h+var_620]
0x180022882  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@AEBV01@@Z; std::vector<ushort const *>::vector<ushort const *>(std::vector<ushort const *> const &)
0x180022887  mov     al, [rbx+48h]
0x18002288a  mov     [rbp+610h+var_608], al
0x18002288d  lea     rdx, [rbp+610h+var_650]
0x180022891  lea     rcx, [rsp+710h+var_6A8+8]
0x180022896  call    _lambda_f886460d9a995a229958d23684bed484___operator__
0x18002289b  add     rbx, 50h ; 'P'
0x18002289f  lea     rax, ?g_DefaultLogger@@3VImageLogger@@A; ImageLogger g_DefaultLogger
0x1800228a6  cmp     rbx, rax
0x1800228a9  jnz     short loc_18002285D
0x1800228ab  mov     eax, dword ptr [rsp+710h+var_6E0]
0x1800228af  cmp     dword ptr [rsp+710h+var_6E0+4], eax
0x1800228b3  jnz     short loc_1800228BF
0x1800228b5  mov     edi, 780h
0x1800228ba  jmp     loc_1800229AF
0x1800228bf  mov     rsi, [rsp+710h+var_6B8]
0x1800228c4  mov     r14, [rsp+710h+var_6B0]
0x1800228c9  mov     r15, [rbp+610h+arg_20]
0x1800228d0  cmp     rsi, r14
0x1800228d3  jz      loc_1800229AF
0x1800228d9  lea     rcx, [rsp+710h+var_6D0]
0x1800228de  call    ??0?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::vector<ushort const *>::vector<ushort const *>(void)
0x1800228e3  nop
0x1800228e4  mov     rax, [rsi+208h]
0x1800228eb  mov     [rbp+610h+var_5F0], rax
0x1800228ef  mov     [rbp+610h+var_660], rsi
0x1800228f3  lea     rax, [rsp+710h+var_6D0]
0x1800228f8  mov     [rbp+610h+var_658], rax
0x1800228fc  mov     rbx, [rsi+210h]
0x180022903  mov     rdi, [rsi+218h]
0x18002290a  jmp     short loc_18002291C
0x18002290c  mov     rdx, [rbx]
0x18002290f  lea     rcx, [rbp+610h+var_660]
0x180022913  call    _lambda_f60fe7e1e893bb13368af42adc67c2a5___operator__
0x180022918  add     rbx, 8
0x18002291c  cmp     rbx, rdi
0x18002291f  jnz     short loc_18002290C
0x180022921  mov     rbx, [rsp+710h+var_6D8]
0x180022926  mov     dil, [rsi+228h]
0x18002292d  xorps   xmm0, xmm0
0x180022930  movdqu  [rsp+710h+var_6A8+8], xmm0
0x180022936  mov     [rbp+610h+var_690], 0
0x18002293e  mov     rdx, [rsp+710h+var_6C8]
0x180022943  sub     rdx, [rsp+710h+var_6D0]
0x180022948  sar     rdx, 3
0x18002294c  mov     rax, 0FC0FC0FC0FC0FC1h
0x180022956  imul    rdx, rax
0x18002295a  lea     r9, [rsp+710h+var_6C8]
0x18002295f  lea     r8, [rsp+710h+var_6D0]
0x180022964  lea     rcx, [rsp+710h+var_6A8+8]
0x180022969  call    ??$_Construct_n@AEBQEAUDirQueItem@@AEBQEAU1@@?$vector@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@AEAAX_KAEBQEAUDirQueItem@@1@Z; std::vector<DirQueItem>::_Construct_n<DirQueItem * const &,DirQueItem * const &>(unsigned __int64,DirQueItem * const &,DirQueItem * const &)
0x18002296e  mov     qword ptr [rsp+710h+var_6E8], r15
0x180022973  mov     [rsp+710h+var_6F0], rbx
0x180022978  mov     r9, r12
0x18002297b  mov     r8b, dil
0x18002297e  lea     rdx, [rsp+710h+var_6A8+8]
0x180022983  mov     rcx, rsi
0x180022986  call    ?ScanDirectory@@YAJPEBGV?$vector@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@_NP6AJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@2@Z4PEAX@Z; ScanDirectory(ushort const *,std::vector<DirQueItem>,bool,long (*)(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool),DIRECTORY_SCAN_FUNC_ARGS *,void *)
0x18002298b  mov     edi, eax
0x18002298d  lea     rcx, [rsp+710h+var_6D0]
0x180022992  cmp     eax, 800704C7h
0x180022997  jz      short loc_1800229AA
0x180022999  call    ?_Tidy@?$vector@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@AEAAXXZ; std::vector<DirQueItem>::_Tidy(void)
0x18002299e  add     rsi, 230h
0x1800229a5  jmp     loc_1800228D0
0x1800229aa  call    ?_Tidy@?$vector@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@AEAAXXZ; std::vector<DirQueItem>::_Tidy(void)
0x1800229af  lea     rax, [rbp+610h+var_310]
0x1800229b6  lea     rcx, [rbp+610h+var_600]
0x1800229ba  mov     edx, 5
0x1800229bf  lea     r8d, [rdx+7Bh]
0x1800229c3  movups  xmm0, xmmword ptr [rcx]
0x1800229c6  movups  xmmword ptr [rax], xmm0
0x1800229c9  movups  xmm1, xmmword ptr [rcx+10h]
0x1800229cd  movups  xmmword ptr [rax+10h], xmm1
0x1800229d1  movups  xmm0, xmmword ptr [rcx+20h]
0x1800229d5  movups  xmmword ptr [rax+20h], xmm0
0x1800229d9  movups  xmm1, xmmword ptr [rcx+30h]
0x1800229dd  movups  xmmword ptr [rax+30h], xmm1
0x1800229e1  movups  xmm0, xmmword ptr [rcx+40h]
0x1800229e5  movups  xmmword ptr [rax+40h], xmm0
0x1800229e9  movups  xmm1, xmmword ptr [rcx+50h]
0x1800229ed  movups  xmmword ptr [rax+50h], xmm1
0x1800229f1  movups  xmm0, xmmword ptr [rcx+60h]
0x1800229f5  movups  xmmword ptr [rax+60h], xmm0
0x1800229f9  movups  xmm1, xmmword ptr [rcx+70h]
0x1800229fd  movups  xmmword ptr [rax+70h], xmm1
0x180022a01  add     rax, r8
0x180022a04  add     rcx, r8
0x180022a07  sub     rdx, 1
0x180022a0b  jnz     short loc_1800229C3
0x180022a0d  movups  xmm0, xmmword ptr [rcx]
0x180022a10  movups  xmmword ptr [rax], xmm0
0x180022a13  movups  xmm1, xmmword ptr [rcx+10h]
0x180022a17  movups  xmmword ptr [rax+10h], xmm1
0x180022a1b  movups  xmm0, xmmword ptr [rcx+20h]
0x180022a1f  movups  xmmword ptr [rax+20h], xmm0
0x180022a23  movups  xmm1, xmmword ptr [rcx+30h]
0x180022a27  movups  xmmword ptr [rax+30h], xmm1
0x180022a2b  movups  xmm0, xmmword ptr [rcx+40h]
0x180022a2f  movups  xmmword ptr [rax+40h], xmm0
0x180022a33  movups  xmm1, xmmword ptr [rcx+50h]
0x180022a37  movups  xmmword ptr [rax+50h], xmm1
0x180022a3b  movups  xmm0, xmmword ptr [rcx+60h]
0x180022a3f  movups  xmmword ptr [rax+60h], xmm0
0x180022a43  lea     rcx, [rbp+610h+var_310]
0x180022a4a  call    ?FreeDirScanArgs@@YAXUDIRECTORY_SCAN_FUNC_ARGS@@@Z; FreeDirScanArgs(DIRECTORY_SCAN_FUNC_ARGS)
0x180022a4f  nop
0x180022a50  mov     rcx, [rsp+710h+var_6B8]
0x180022a55  test    rcx, rcx
0x180022a58  jz      short loc_180022A8F
0x180022a5a  mov     rdx, [rsp+710h+var_6B0]
0x180022a5f  call    ??$_Destroy_range@V?$allocator@UDIR_SCAN_ENTRY@@@std@@@std@@YAXPEAUDIR_SCAN_ENTRY@@QEAU1@AEAV?$allocator@UDIR_SCAN_ENTRY@@@0@@Z; std::_Destroy_range<std::allocator<DIR_SCAN_ENTRY>>(DIR_SCAN_ENTRY *,DIR_SCAN_ENTRY * const,std::allocator<DIR_SCAN_ENTRY> &)
0x180022a64  mov     rcx, [rsp+710h+var_6B8]
0x180022a69  mov     rax, qword ptr [rsp+710h+var_6A8]
0x180022a6e  sub     rax, rcx
0x180022a71  sar     rax, 4
0x180022a75  mov     rdx, 0AF8AF8AF8AF8AF8Bh
0x180022a7f  imul    rax, rdx
0x180022a83  imul    rdx, rax, 230h
0x180022a8a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022a8f  mov     eax, edi
0x180022a91  lea     r11, [rsp+710h+var_20]
0x180022a99  mov     rbx, [r11+30h]
0x180022a9d  mov     rsi, [r11+40h]
0x180022aa1  mov     rsp, r11
0x180022aa4  pop     r15
0x180022aa6  pop     r14
0x180022aa8  pop     r12
0x180022aaa  pop     rdi
0x180022aab  pop     rbp
0x180022aac  retn
```
