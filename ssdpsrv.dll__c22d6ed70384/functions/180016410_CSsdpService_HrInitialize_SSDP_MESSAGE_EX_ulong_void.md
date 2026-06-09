# CSsdpService::HrInitialize(_SSDP_MESSAGE_EX *,ulong,void * *)

- ea: `0x180016410`
- end: `0x180016832`
- name: `?HrInitialize@CSsdpService@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z`
- size: `1058`
- prototype: `__int64 __fastcall(CSsdpService *this, struct _SSDP_MESSAGE_EX *, int, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800161b4`

## callees

- `0x180004340`
- `0x180005588`
- `0x1800079ac`
- `0x180016410`
- `0x180016838`
- `0x180016a90`
- `0x180016b00`
- `0x180016c14`
- `0x180017400`
- `0x1800255a8`
- `0x180025e50`
- `0x180028000`
- `0x18002dcf4`
- `0x1800337b8`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800165fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016697`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001671e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001679e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800165fc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016697`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001671e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001679e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001672f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016757`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001672f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016757`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrInitialize(CSsdpService *this, struct _SSDP_MESSAGE_EX *a2, int a3, void **a4)
{
  LPCSTR v8; // rcx
  const size_t *v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // edx
  int v12; // ebx
  __int64 v13; // rax
  LPCSTR v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  char *v17; // rax
  char *v18; // rsi
  CSsdpByebye *v19; // rax
  CSsdpByebye *v20; // rax
  struct CWorkItem *v21; // r14
  CStaleWorkItemsTracking *v22; // rcx
  __int64 v23; // rax
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    v9 = &Format;
    if ( *((_QWORD *)a2 + 3) )
      v9 = (const size_t *)*((_QWORD *)a2 + 3);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, v9);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !g_fCheckedRegistry )
  {
    CheckRegistryForMinMaxLifetime();
    v8 = WPP_GLOBAL_Control;
    g_fCheckedRegistry = 1;
  }
  v10 = g_nMaxLifetime;
  if ( *((_DWORD *)a2 + 11) <= g_nMaxLifetime )
  {
    v10 = *((_DWORD *)a2 + 11);
  }
  else
  {
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (v8[28] & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 12, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
      v10 = g_nMaxLifetime;
    }
    *((_DWORD *)a2 + 11) = v10;
    v8 = WPP_GLOBAL_Control;
  }
  v11 = g_nMinLifetime;
  if ( v10 < g_nMinLifetime )
  {
    if ( v8 != (LPCSTR)&WPP_GLOBAL_Control && (v8[28] & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 13, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
      v11 = g_nMinLifetime;
    }
    *((_DWORD *)a2 + 11) = v11;
  }
  v12 = HrInitializeSsdpRequestFromMessage((CSsdpService *)((char *)this + 112), a2);
  if ( v12 >= 0 )
  {
    *((_DWORD *)this + 26) = *((_DWORD *)a2 + 11);
    CUString::HrAssign((CSsdpService *)((char *)this + 280), *((const char **)a2 + 3));
    *((_DWORD *)this + 25) = 3;
    *((_DWORD *)this + 66) = a3;
    *((_QWORD *)this + 34) = a4;
    *a4 = 0;
    *((_QWORD *)this + 15) = "*";
    v13 = *((_QWORD *)this + 24);
    Block = 0;
    *(_QWORD *)(v13 + 136) = "Microsoft-Windows/10.0 UPnP/1.0 UPnP-Device-Host/1.0";
    *(_QWORD *)(*((_QWORD *)this + 24) + 16LL) = "ssdp:alive";
    if ( (unsigned int)ComposeSsdpRequest((CSsdpService *)((char *)this + 112), (char **)&Block) )
    {
      v12 = CUString::HrAssign((CSsdpService *)((char *)this + 200), (const char *)Block);
      free(Block);
      if ( v12 >= 0 )
      {
        SsdpGetTypeVersion(*(const char **)(*((_QWORD *)this + 24) + 8LL), (CSsdpService *)((char *)this + 288));
        v16 = *((_QWORD *)this + 24);
        Block = 0;
        *(_QWORD *)(v16 + 16) = "ssdp:byebye";
        if ( (unsigned int)ComposeSsdpRequest((CSsdpService *)((char *)this + 112), (char **)&Block) )
        {
          v12 = CUString::HrAssign((CSsdpService *)((char *)this + 208), (const char *)Block);
          free(Block);
          if ( v12 >= 0 )
          {
            *(_QWORD *)(*((_QWORD *)this + 24) + 144LL) = &Format;
            Block = 0;
            if ( (unsigned int)ComposeSsdpResponse((CSsdpService *)((char *)this + 112), (char **)&Block) )
            {
              v12 = CUString::HrAssign((CSsdpService *)((char *)this + 216), (const char *)Block);
              free(Block);
              if ( v12 >= 0 )
              {
                v17 = (char *)malloc(7u);
                v18 = v17;
                if ( v17 )
                {
                  if ( (int)StringCbCopyA(v17, 7u, "doeach") >= 0
                    && (v19 = (CSsdpByebye *)malloc(0xB0u)) != 0
                    && (v20 = CSsdpByebye::CSsdpByebye(v19, v18), (v21 = v20) != 0) )
                  {
                    CSsdpByebye::AssignUSN(v20, (CSsdpService *)((char *)this + 280));
                    CStaleWorkItemsTracking::DoForEach(v22, v21);
                    (**(void (__fastcall ***)(struct CWorkItem *, __int64))v21)(v21, 1);
                  }
                  else
                  {
                    free(v18);
                  }
                }
              }
            }
            else
            {
              v12 = -2147467259;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
              {
                v15 = 16;
                goto LABEL_24;
              }
            }
          }
        }
        else
        {
          v12 = -2147467259;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          {
            v15 = 15;
            goto LABEL_24;
          }
        }
      }
    }
    else
    {
      v12 = -2147467259;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v15 = 14;
LABEL_24:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, 2147500037LL);
      }
    }
  }
  v23 = *((_QWORD *)this + 24);
  if ( v23 )
  {
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(*((_QWORD *)this + 24) + 144LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 24) + 136LL) = 0;
  }
  *((_QWORD *)this + 15) = 0;
  if ( v12 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180016410  mov     [rsp+arg_8], rbx
0x180016415  mov     [rsp+arg_10], rbp
0x18001641a  push    rsi
0x18001641b  push    rdi
0x18001641c  push    r12
0x18001641e  push    r14
0x180016420  push    r15
0x180016422  sub     rsp, 20h
0x180016426  mov     r14, r9
0x180016429  mov     r12d, r8d
0x18001642c  mov     rsi, rdx
0x18001642f  mov     rdi, rcx
0x180016432  mov     rcx, cs:WPP_GLOBAL_Control
0x180016439  lea     r15, WPP_GLOBAL_Control
0x180016440  lea     rbx, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180016447  mov     bpl, 8
0x18001644a  cmp     rcx, r15
0x18001644d  jz      short loc_18001647E
0x18001644f  test    [rcx+1Ch], bpl
0x180016453  jz      short loc_18001647E
0x180016455  cmp     qword ptr [rdx+18h], 0
0x18001645a  lea     r9, Format
0x180016461  mov     rcx, [rcx+10h]
0x180016465  mov     r8, rbx
0x180016468  cmovnz  r9, [rdx+18h]
0x18001646d  mov     edx, 0Bh
0x180016472  call    WPP_SF_s
0x180016477  mov     rcx, cs:WPP_GLOBAL_Control
0x18001647e  cmp     cs:?g_fCheckedRegistry@@3HA, 0; int g_fCheckedRegistry
0x180016485  jnz     short loc_18001649D
0x180016487  call    ?CheckRegistryForMinMaxLifetime@@YAXXZ; CheckRegistryForMinMaxLifetime(void)
0x18001648c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016493  mov     cs:?g_fCheckedRegistry@@3HA, 1; int g_fCheckedRegistry
0x18001649d  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800164a3  cmp     [rsi+2Ch], eax
0x1800164a6  jbe     short loc_1800164D6
0x1800164a8  cmp     rcx, r15
0x1800164ab  jz      short loc_1800164CA
0x1800164ad  test    [rcx+1Ch], bpl
0x1800164b1  jz      short loc_1800164CA
0x1800164b3  mov     rcx, [rcx+10h]
0x1800164b7  mov     edx, 0Ch
0x1800164bc  mov     r8, rbx
0x1800164bf  call    WPP_SF_
0x1800164c4  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800164ca  mov     [rsi+2Ch], eax
0x1800164cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164d4  jmp     short loc_1800164D9
0x1800164d6  mov     eax, [rsi+2Ch]
0x1800164d9  mov     edx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x1800164df  cmp     eax, edx
0x1800164e1  jnb     short loc_180016508
0x1800164e3  cmp     rcx, r15
0x1800164e6  jz      short loc_180016505
0x1800164e8  test    [rcx+1Ch], bpl
0x1800164ec  jz      short loc_180016505
0x1800164ee  mov     rcx, [rcx+10h]
0x1800164f2  mov     edx, 0Dh
0x1800164f7  mov     r8, rbx
0x1800164fa  call    WPP_SF_
0x1800164ff  mov     edx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x180016505  mov     [rsi+2Ch], edx
0x180016508  lea     rbp, [rdi+70h]
0x18001650c  mov     rdx, rsi; struct _SSDP_MESSAGE_EX *
0x18001650f  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180016512  call    ?HrInitializeSsdpRequestFromMessage@@YAJPEAU_SSDP_REQUEST@@PEBU_SSDP_MESSAGE_EX@@@Z; HrInitializeSsdpRequestFromMessage(_SSDP_REQUEST *,_SSDP_MESSAGE_EX const *)
0x180016517  mov     ebx, eax
0x180016519  test    eax, eax
0x18001651b  js      loc_1800167AB
0x180016521  mov     eax, [rsi+2Ch]
0x180016524  lea     r15, [rdi+118h]
0x18001652b  mov     [rdi+68h], eax
0x18001652e  mov     rcx, r15; this
0x180016531  mov     rdx, [rsi+18h]; char *
0x180016535  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x18001653a  mov     dword ptr [rdi+64h], 3
0x180016541  lea     rax, String2; "*"
0x180016548  mov     [rdi+108h], r12d
0x18001654f  lea     rcx, aMicrosoftWindo; "Microsoft-Windows/10.0 UPnP/1.0 UPnP-De"...
0x180016556  mov     [rdi+110h], r14
0x18001655d  lea     rdx, [rsp+48h+Block]; char **
0x180016562  mov     qword ptr [r14], 0
0x180016569  mov     [rdi+78h], rax
0x18001656d  mov     rax, [rdi+0C0h]
0x180016574  mov     [rsp+48h+Block], 0
0x18001657d  mov     [rax+88h], rcx
0x180016584  lea     rcx, aSsdpAlive; "ssdp:alive"
0x18001658b  mov     rax, [rdi+0C0h]
0x180016592  mov     [rax+10h], rcx
0x180016596  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180016599  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x18001659e  test    eax, eax
0x1800165a0  jnz     short loc_1800165E4
0x1800165a2  mov     r9d, 80004005h
0x1800165a8  mov     ebx, r9d
0x1800165ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165b2  lea     r15, WPP_GLOBAL_Control
0x1800165b9  cmp     rcx, r15
0x1800165bc  jz      loc_1800167AB
0x1800165c2  test    byte ptr [rcx+1Ch], 1
0x1800165c6  jz      loc_1800167AB
0x1800165cc  lea     edx, [rax+0Eh]
0x1800165cf  mov     rcx, [rcx+10h]
0x1800165d3  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x1800165da  call    WPP_SF_d
0x1800165df  jmp     loc_1800167AB
0x1800165e4  mov     rdx, [rsp+48h+Block]; char *
0x1800165e9  lea     rcx, [rdi+0C8h]; this
0x1800165f0  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x1800165f5  mov     rcx, [rsp+48h+Block]; Block
0x1800165fa  mov     ebx, eax
0x1800165fc  call    cs:__imp_free
0x180016602  test    ebx, ebx
0x180016604  js      loc_1800167A4
0x18001660a  mov     rcx, [rdi+0C0h]
0x180016611  lea     rdx, [rdi+120h]; struct _TypeVersion *
0x180016618  mov     rcx, [rcx+8]; char *
0x18001661c  call    ?SsdpGetTypeVersion@@YAXPEBDPEAU_TypeVersion@@@Z; SsdpGetTypeVersion(char const *,_TypeVersion *)
0x180016621  mov     rax, [rdi+0C0h]
0x180016628  lea     rcx, aSsdpByebye; "ssdp:byebye"
0x18001662f  lea     rdx, [rsp+48h+Block]; char **
0x180016634  mov     [rsp+48h+Block], 0
0x18001663d  mov     [rax+10h], rcx
0x180016641  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180016644  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x180016649  test    eax, eax
0x18001664b  jnz     short loc_18001667F
0x18001664d  mov     r9d, 80004005h
0x180016653  mov     ebx, r9d
0x180016656  mov     rcx, cs:WPP_GLOBAL_Control
0x18001665d  lea     r15, WPP_GLOBAL_Control
0x180016664  cmp     rcx, r15
0x180016667  jz      loc_1800167AB
0x18001666d  test    byte ptr [rcx+1Ch], 1
0x180016671  jz      loc_1800167AB
0x180016677  lea     edx, [rax+0Fh]
0x18001667a  jmp     loc_1800165CF
0x18001667f  mov     rdx, [rsp+48h+Block]; char *
0x180016684  lea     rcx, [rdi+0D0h]; this
0x18001668b  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180016690  mov     rcx, [rsp+48h+Block]; Block
0x180016695  mov     ebx, eax
0x180016697  call    cs:__imp_free
0x18001669d  test    ebx, ebx
0x18001669f  js      loc_1800167A4
0x1800166a5  mov     rax, [rdi+0C0h]
0x1800166ac  lea     rcx, Format
0x1800166b3  lea     rdx, [rsp+48h+Block]; char **
0x1800166b8  mov     [rax+90h], rcx
0x1800166bf  mov     rcx, rbp; struct _SSDP_REQUEST *
0x1800166c2  mov     [rsp+48h+Block], 0
0x1800166cb  call    ?ComposeSsdpResponse@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpResponse(_SSDP_REQUEST const *,char * *)
0x1800166d0  test    eax, eax
0x1800166d2  jnz     short loc_180016706
0x1800166d4  mov     r9d, 80004005h
0x1800166da  mov     ebx, r9d
0x1800166dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166e4  lea     r15, WPP_GLOBAL_Control
0x1800166eb  cmp     rcx, r15
0x1800166ee  jz      loc_1800167AB
0x1800166f4  test    byte ptr [rcx+1Ch], 1
0x1800166f8  jz      loc_1800167AB
0x1800166fe  lea     edx, [rax+10h]
0x180016701  jmp     loc_1800165CF
0x180016706  mov     rdx, [rsp+48h+Block]; char *
0x18001670b  lea     rcx, [rdi+0D8h]; this
0x180016712  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180016717  mov     rcx, [rsp+48h+Block]; Block
0x18001671c  mov     ebx, eax
0x18001671e  call    cs:__imp_free
0x180016724  test    ebx, ebx
0x180016726  js      short loc_1800167A4
0x180016728  mov     ebp, 7
0x18001672d  mov     ecx, ebp; Size
0x18001672f  call    cs:__imp_malloc
0x180016735  mov     rsi, rax
0x180016738  test    rax, rax
0x18001673b  jz      short loc_1800167A4
0x18001673d  lea     r8, aDoeach; "doeach"
0x180016744  mov     edx, ebp; unsigned __int64
0x180016746  mov     rcx, rax; char *
0x180016749  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x18001674e  test    eax, eax
0x180016750  js      short loc_18001679B
0x180016752  mov     ecx, 0B0h; Size
0x180016757  call    cs:__imp_malloc
0x18001675d  test    rax, rax
0x180016760  jz      short loc_18001679B
0x180016762  mov     rdx, rsi; char *
0x180016765  mov     rcx, rax; this
0x180016768  call    ??0CSsdpByebye@@QEAA@PEAD@Z; CSsdpByebye::CSsdpByebye(char *)
0x18001676d  mov     r14, rax
0x180016770  test    rax, rax
0x180016773  jz      short loc_18001679B
0x180016775  mov     rdx, r15; struct CUString *
0x180016778  mov     rcx, rax; this
0x18001677b  call    ?AssignUSN@CSsdpByebye@@QEAAXAEAVCUString@@@Z; CSsdpByebye::AssignUSN(CUString &)
0x180016780  mov     rdx, r14; struct CWorkItem *
0x180016783  call    ?DoForEach@CStaleWorkItemsTracking@@QEAAXPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::DoForEach(CWorkItem *)
0x180016788  mov     rcx, [r14]
0x18001678b  lea     edx, [rbp-6]
0x18001678e  mov     rax, [rcx]
0x180016791  mov     rcx, r14
0x180016794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016799  jmp     short loc_1800167A4
0x18001679b  mov     rcx, rsi; Block
0x18001679e  call    cs:__imp_free
0x1800167a4  lea     r15, WPP_GLOBAL_Control
0x1800167ab  mov     rax, [rdi+0C0h]
0x1800167b2  test    rax, rax
0x1800167b5  jz      short loc_1800167E3
0x1800167b7  mov     qword ptr [rax+10h], 0
0x1800167bf  mov     rax, [rdi+0C0h]
0x1800167c6  mov     qword ptr [rax+90h], 0
0x1800167d1  mov     rax, [rdi+0C0h]
0x1800167d8  mov     qword ptr [rax+88h], 0
0x1800167e3  mov     qword ptr [rdi+78h], 0
0x1800167eb  test    ebx, ebx
0x1800167ed  jz      short loc_180016819
0x1800167ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167f6  cmp     rcx, r15
0x1800167f9  jz      short loc_180016819
0x1800167fb  test    byte ptr [rcx+1Ch], 1
0x1800167ff  jz      short loc_180016819
0x180016801  mov     rcx, [rcx+10h]
0x180016805  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001680c  mov     edx, 11h
0x180016811  mov     r9d, ebx
0x180016814  call    WPP_SF_d
0x180016819  mov     rbp, [rsp+48h+arg_10]
0x18001681e  mov     eax, ebx
0x180016820  mov     rbx, [rsp+48h+arg_8]
0x180016825  add     rsp, 20h
0x180016829  pop     r15
0x18001682b  pop     r14
0x18001682d  pop     r12
0x18001682f  pop     rdi
0x180016830  pop     rsi
0x180016831  retn
```
