# CSsdpService::HrInitialize(_SSDP_MESSAGE_EX *,ulong,void * *)

- ea: `0x180018804`
- end: `0x180018c4f`
- name: `?HrInitialize@CSsdpService@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z`
- size: `1099`
- prototype: `int(CSsdpService *__hidden this, struct _SSDP_MESSAGE_EX *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018590`

## callees

- `0x180005be0`
- `0x180006880`
- `0x180008eb8`
- `0x180018804`
- `0x180018c58`
- `0x180018ec4`
- `0x180018f38`
- `0x18001905c`
- `0x180019850`
- `0x1800271fc`
- `0x180027bc4`
- `0x180029df0`
- `0x18002fe28`
- `0x18003623c`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800189f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018a91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b1e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018bb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800189f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018a91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018b1e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018bb4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b39`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b67`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b39`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018b67`

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
0x180018804  mov     [rsp+arg_8], rbx
0x180018809  mov     [rsp+arg_10], rbp
0x18001880e  push    rsi
0x18001880f  push    rdi
0x180018810  push    r12
0x180018812  push    r14
0x180018814  push    r15
0x180018816  sub     rsp, 20h
0x18001881a  mov     r14, r9
0x18001881d  mov     r12d, r8d
0x180018820  mov     rsi, rdx
0x180018823  mov     rdi, rcx
0x180018826  mov     rcx, cs:WPP_GLOBAL_Control
0x18001882d  lea     r15, WPP_GLOBAL_Control
0x180018834  lea     rbx, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001883b  mov     bpl, 8
0x18001883e  cmp     rcx, r15
0x180018841  jz      short loc_180018872
0x180018843  test    [rcx+1Ch], bpl
0x180018847  jz      short loc_180018872
0x180018849  cmp     qword ptr [rdx+18h], 0
0x18001884e  lea     r9, Format
0x180018855  mov     rcx, [rcx+10h]
0x180018859  mov     r8, rbx
0x18001885c  cmovnz  r9, [rdx+18h]
0x180018861  mov     edx, 0Bh
0x180018866  call    WPP_SF_s
0x18001886b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018872  cmp     cs:?g_fCheckedRegistry@@3HA, 0; int g_fCheckedRegistry
0x180018879  jnz     short loc_180018891
0x18001887b  call    ?CheckRegistryForMinMaxLifetime@@YAXXZ; CheckRegistryForMinMaxLifetime(void)
0x180018880  mov     rcx, cs:WPP_GLOBAL_Control
0x180018887  mov     cs:?g_fCheckedRegistry@@3HA, 1; int g_fCheckedRegistry
0x180018891  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x180018897  cmp     [rsi+2Ch], eax
0x18001889a  jbe     short loc_1800188CA
0x18001889c  cmp     rcx, r15
0x18001889f  jz      short loc_1800188BE
0x1800188a1  test    [rcx+1Ch], bpl
0x1800188a5  jz      short loc_1800188BE
0x1800188a7  mov     rcx, [rcx+10h]
0x1800188ab  mov     edx, 0Ch
0x1800188b0  mov     r8, rbx
0x1800188b3  call    WPP_SF_
0x1800188b8  mov     eax, cs:?g_nMaxLifetime@@3IA; uint g_nMaxLifetime
0x1800188be  mov     [rsi+2Ch], eax
0x1800188c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188c8  jmp     short loc_1800188CD
0x1800188ca  mov     eax, [rsi+2Ch]
0x1800188cd  mov     edx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x1800188d3  cmp     eax, edx
0x1800188d5  jnb     short loc_1800188FC
0x1800188d7  cmp     rcx, r15
0x1800188da  jz      short loc_1800188F9
0x1800188dc  test    [rcx+1Ch], bpl
0x1800188e0  jz      short loc_1800188F9
0x1800188e2  mov     rcx, [rcx+10h]
0x1800188e6  mov     edx, 0Dh
0x1800188eb  mov     r8, rbx
0x1800188ee  call    WPP_SF_
0x1800188f3  mov     edx, cs:?g_nMinLifetime@@3IA; uint g_nMinLifetime
0x1800188f9  mov     [rsi+2Ch], edx
0x1800188fc  lea     rbp, [rdi+70h]
0x180018900  mov     rdx, rsi; struct _SSDP_MESSAGE_EX *
0x180018903  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180018906  call    ?HrInitializeSsdpRequestFromMessage@@YAJPEAU_SSDP_REQUEST@@PEBU_SSDP_MESSAGE_EX@@@Z; HrInitializeSsdpRequestFromMessage(_SSDP_REQUEST *,_SSDP_MESSAGE_EX const *)
0x18001890b  mov     ebx, eax
0x18001890d  test    eax, eax
0x18001890f  js      loc_180018BC7
0x180018915  mov     eax, [rsi+2Ch]
0x180018918  lea     r15, [rdi+118h]
0x18001891f  mov     [rdi+68h], eax
0x180018922  mov     rcx, r15; this
0x180018925  mov     rdx, [rsi+18h]; char *
0x180018929  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x18001892e  mov     dword ptr [rdi+64h], 3
0x180018935  lea     rax, String2; "*"
0x18001893c  mov     [rdi+108h], r12d
0x180018943  lea     rcx, aMicrosoftWindo; "Microsoft-Windows/10.0 UPnP/1.0 UPnP-De"...
0x18001894a  mov     [rdi+110h], r14
0x180018951  lea     rdx, [rsp+48h+Block]; char **
0x180018956  mov     qword ptr [r14], 0
0x18001895d  mov     [rdi+78h], rax
0x180018961  mov     rax, [rdi+0C0h]
0x180018968  mov     [rsp+48h+Block], 0
0x180018971  mov     [rax+88h], rcx
0x180018978  lea     rcx, aSsdpAlive; "ssdp:alive"
0x18001897f  mov     rax, [rdi+0C0h]
0x180018986  mov     [rax+10h], rcx
0x18001898a  mov     rcx, rbp; struct _SSDP_REQUEST *
0x18001898d  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x180018992  test    eax, eax
0x180018994  jnz     short loc_1800189D8
0x180018996  mov     r9d, 80004005h
0x18001899c  mov     ebx, r9d
0x18001899f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189a6  lea     r15, WPP_GLOBAL_Control
0x1800189ad  cmp     rcx, r15
0x1800189b0  jz      loc_180018BC7
0x1800189b6  test    byte ptr [rcx+1Ch], 1
0x1800189ba  jz      loc_180018BC7
0x1800189c0  lea     edx, [rax+0Eh]
0x1800189c3  mov     rcx, [rcx+10h]
0x1800189c7  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x1800189ce  call    WPP_SF_d
0x1800189d3  jmp     loc_180018BC7
0x1800189d8  mov     rdx, [rsp+48h+Block]; char *
0x1800189dd  lea     rcx, [rdi+0C8h]; this
0x1800189e4  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x1800189e9  mov     rcx, [rsp+48h+Block]; Block
0x1800189ee  mov     ebx, eax
0x1800189f0  call    cs:__imp_free
0x1800189f7  nop     dword ptr [rax+rax+00h]
0x1800189fc  test    ebx, ebx
0x1800189fe  js      loc_180018BC0
0x180018a04  mov     rcx, [rdi+0C0h]
0x180018a0b  lea     rdx, [rdi+120h]; struct _TypeVersion *
0x180018a12  mov     rcx, [rcx+8]; char *
0x180018a16  call    ?SsdpGetTypeVersion@@YAXPEBDPEAU_TypeVersion@@@Z; SsdpGetTypeVersion(char const *,_TypeVersion *)
0x180018a1b  mov     rax, [rdi+0C0h]
0x180018a22  lea     rcx, aSsdpByebye; "ssdp:byebye"
0x180018a29  lea     rdx, [rsp+48h+Block]; char **
0x180018a2e  mov     [rsp+48h+Block], 0
0x180018a37  mov     [rax+10h], rcx
0x180018a3b  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180018a3e  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x180018a43  test    eax, eax
0x180018a45  jnz     short loc_180018A79
0x180018a47  mov     r9d, 80004005h
0x180018a4d  mov     ebx, r9d
0x180018a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a57  lea     r15, WPP_GLOBAL_Control
0x180018a5e  cmp     rcx, r15
0x180018a61  jz      loc_180018BC7
0x180018a67  test    byte ptr [rcx+1Ch], 1
0x180018a6b  jz      loc_180018BC7
0x180018a71  lea     edx, [rax+0Fh]
0x180018a74  jmp     loc_1800189C3
0x180018a79  mov     rdx, [rsp+48h+Block]; char *
0x180018a7e  lea     rcx, [rdi+0D0h]; this
0x180018a85  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180018a8a  mov     rcx, [rsp+48h+Block]; Block
0x180018a8f  mov     ebx, eax
0x180018a91  call    cs:__imp_free
0x180018a98  nop     dword ptr [rax+rax+00h]
0x180018a9d  test    ebx, ebx
0x180018a9f  js      loc_180018BC0
0x180018aa5  mov     rax, [rdi+0C0h]
0x180018aac  lea     rcx, Format
0x180018ab3  lea     rdx, [rsp+48h+Block]; char **
0x180018ab8  mov     [rax+90h], rcx
0x180018abf  mov     rcx, rbp; struct _SSDP_REQUEST *
0x180018ac2  mov     [rsp+48h+Block], 0
0x180018acb  call    ?ComposeSsdpResponse@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpResponse(_SSDP_REQUEST const *,char * *)
0x180018ad0  test    eax, eax
0x180018ad2  jnz     short loc_180018B06
0x180018ad4  mov     r9d, 80004005h
0x180018ada  mov     ebx, r9d
0x180018add  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ae4  lea     r15, WPP_GLOBAL_Control
0x180018aeb  cmp     rcx, r15
0x180018aee  jz      loc_180018BC7
0x180018af4  test    byte ptr [rcx+1Ch], 1
0x180018af8  jz      loc_180018BC7
0x180018afe  lea     edx, [rax+10h]
0x180018b01  jmp     loc_1800189C3
0x180018b06  mov     rdx, [rsp+48h+Block]; char *
0x180018b0b  lea     rcx, [rdi+0D8h]; this
0x180018b12  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180018b17  mov     rcx, [rsp+48h+Block]; Block
0x180018b1c  mov     ebx, eax
0x180018b1e  call    cs:__imp_free
0x180018b25  nop     dword ptr [rax+rax+00h]
0x180018b2a  test    ebx, ebx
0x180018b2c  js      loc_180018BC0
0x180018b32  mov     ebp, 7
0x180018b37  mov     ecx, ebp; Size
0x180018b39  call    cs:__imp_malloc
0x180018b40  nop     dword ptr [rax+rax+00h]
0x180018b45  mov     rsi, rax
0x180018b48  test    rax, rax
0x180018b4b  jz      short loc_180018BC0
0x180018b4d  lea     r8, aDoeach; "doeach"
0x180018b54  mov     edx, ebp; unsigned __int64
0x180018b56  mov     rcx, rax; char *
0x180018b59  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180018b5e  test    eax, eax
0x180018b60  js      short loc_180018BB1
0x180018b62  mov     ecx, 0B0h; Size
0x180018b67  call    cs:__imp_malloc
0x180018b6e  nop     dword ptr [rax+rax+00h]
0x180018b73  test    rax, rax
0x180018b76  jz      short loc_180018BB1
0x180018b78  mov     rdx, rsi; char *
0x180018b7b  mov     rcx, rax; this
0x180018b7e  call    ??0CSsdpByebye@@QEAA@PEAD@Z; CSsdpByebye::CSsdpByebye(char *)
0x180018b83  mov     r14, rax
0x180018b86  test    rax, rax
0x180018b89  jz      short loc_180018BB1
0x180018b8b  mov     rdx, r15; struct CUString *
0x180018b8e  mov     rcx, rax; this
0x180018b91  call    ?AssignUSN@CSsdpByebye@@QEAAXAEAVCUString@@@Z; CSsdpByebye::AssignUSN(CUString &)
0x180018b96  mov     rdx, r14; struct CWorkItem *
0x180018b99  call    ?DoForEach@CStaleWorkItemsTracking@@QEAAXPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::DoForEach(CWorkItem *)
0x180018b9e  mov     rcx, [r14]
0x180018ba1  lea     edx, [rbp-6]
0x180018ba4  mov     rax, [rcx]
0x180018ba7  mov     rcx, r14
0x180018baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018baf  jmp     short loc_180018BC0
0x180018bb1  mov     rcx, rsi; Block
0x180018bb4  call    cs:__imp_free
0x180018bbb  nop     dword ptr [rax+rax+00h]
0x180018bc0  lea     r15, WPP_GLOBAL_Control
0x180018bc7  mov     rax, [rdi+0C0h]
0x180018bce  test    rax, rax
0x180018bd1  jz      short loc_180018BFF
0x180018bd3  mov     qword ptr [rax+10h], 0
0x180018bdb  mov     rax, [rdi+0C0h]
0x180018be2  mov     qword ptr [rax+90h], 0
0x180018bed  mov     rax, [rdi+0C0h]
0x180018bf4  mov     qword ptr [rax+88h], 0
0x180018bff  mov     qword ptr [rdi+78h], 0
0x180018c07  test    ebx, ebx
0x180018c09  jz      short loc_180018C35
0x180018c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c12  cmp     rcx, r15
0x180018c15  jz      short loc_180018C35
0x180018c17  test    byte ptr [rcx+1Ch], 1
0x180018c1b  jz      short loc_180018C35
0x180018c1d  mov     rcx, [rcx+10h]
0x180018c21  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180018c28  mov     edx, 11h
0x180018c2d  mov     r9d, ebx
0x180018c30  call    WPP_SF_d
0x180018c35  mov     rbp, [rsp+48h+arg_10]
0x180018c3a  mov     eax, ebx
0x180018c3c  mov     rbx, [rsp+48h+arg_8]
0x180018c41  add     rsp, 20h
0x180018c45  pop     r15
0x180018c47  pop     r14
0x180018c49  pop     r12
0x180018c4b  pop     rdi
0x180018c4c  pop     rsi
0x180018c4d  retn
```
